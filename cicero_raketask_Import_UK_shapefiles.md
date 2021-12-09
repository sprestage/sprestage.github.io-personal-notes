## Instructions from update_united_kingdom.rake

Before using rake import_cicero_united_kingdom_shapefiles, you'll need to import Cicero's latest shapefiles into the new_districts table

**Step 1.**  Start with shp2pgsql calls to convert the two relevant .shp files into usable .sql:
```
sudo shp2pgsql -t 2D -s 4326 -g uk_geom /Users/susanprestage/code/UK_data/cicero_uk_districts/cicero_uk_districts.shp public.new_districts > DISTRICTS_uk.sql
```
   The national upper shapes are just the state/territory boundaries themselves, which we won't need to match against lats and lons.

**Step 2.**  For each of the .sql files generated, delete the first few lines of sql, until you get to the INSERT INTO statements.

Susan added: Copy the sql files to staging/production

# STOP!!!  DISCONNECT FROM YOUR VPN FIRST!!!
staging - 938hg3kk
```
scp -i ~/.ssh/ ../CiceroImports/united_kingdom/*UK.sql ubuntu@ec2-54-235-144-131.compute-1.amazonaws.com:~/united_kingdom/sep2021
```
prod - 938hg3kk
```
scp -i ~/.ssh/id_rsa ../../one-click-politics/docker/postgres/*UK.sql ubuntu@ec2-184-72-246-33.compute-1.amazonaws.com:~/united_kingdom/sep2021
```

   The preceding lines are used to set up our new_districts table, and we won't need them - we're going to do this with the NewDistrict.reset_table command.

**Step 3.**  Now use .reset_table to give us the precise new_districts table we need:
```
 NewDistrict.reset_table :uk_geom_srid => '4326', :columns => { :district_i => :string, :city => :string, :state => :string, :district_t => :float, :subtype => :string, :valid_from => :string, :valid_to => :string, :ocd_id => :string }
```

**Step 4.**  Now use psql to import these .sql shape records into the new_districts table.  Give the correct database endpoint after argument -h

Production
```
psql -U ocp -d ocp_new -h new-production-2.c8rvchfbyjh2.us-east-1.rds.amazonaws.com -f ~/united_kingdom/sep2021/DISTRICTS_UK.sql
```
Staging
```
psql -U ocp -d ocp_new -h new-staging-127.c8rvchfbyjh2.us-east-1.rds.amazonaws.com -f ~/united_kingdom/sep2021/DISTRICTS_UK.sql
```
Locally with docker, put the sql files into your docker/postgres/ folder and run the following commands instead:
```
     docker-compose exec postgres psql -U ocp -d ocp -f /ocp/postgres/DISTRICTS_UK.sql
```

**Step 5.**  Now you should be able to run import_cicero_united_kingdom_shapefiles.  Use the [record] flag to make changes to the database.
```
bundle exec rake import_cicero_united_kingdom_shapefiles RAILS_ENV=production

bundle exec rake import_cicero_united_kingdom_shapefiles[record] RAILS_ENV=production
```
