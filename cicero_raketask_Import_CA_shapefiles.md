## Instructions from update_canada.rake

Before using rake import_cicero_canada_shapefiles, you'll need to import Cicero's latest shapefiles into the new_districts table

**Step 1.**  Start with shp2pgsql calls to convert the two relevant .shp files into usable .sql:
```
shp2pgsql -s 4326 -g ca_geom cicero_ca_districts/district_statelower_ca.shp public.new_districts > STATELOWER_CA.sql
shp2pgsql -s 4326 -g ca_geom cicero_ca_districts/district_nationallower_ca.shp public.new_districts > NATIONALLOWER_CA.sql
```
The national upper shapes are just the state/territory boundaries themselves, which we won't need to match against lats and lons.

**Step 2.**  For each of the .sql files generated, delete the first few lines of sql, until you get to the INSERT INTO statements.

Susan added: Copy the sql files to staging/production

# STOP!!!  DISCONNECT FROM YOUR VPN FIRST!!!
staging - 938hg3kk
```
scp -i ~/.ssh/ ../CiceroImports/canada/*CA.sql ubuntu@ec2-54-235-144-131.compute-1.amazonaws.com:~/canada/oct2021
```
prod - 938hg3kk
```
scp -i ~/.ssh/id_rsa *CA.sql ubuntu@prod.oneclickpolitics.com:~/canada/2022_05
```

   The preceding lines are used to set up our new_districts table, and we won't need them - we're going to do this with the NewDistrict.reset_table command.

**Step 3.**  Now use .reset_table to give us the precise new_districts table we need:
```
NewDistrict.reset_table :ca_geom_srid => '4326', :columns => { :district_i => :string, :state => :string, :district_t => :float, :subtype => :string, :valid_from => :string, :valid_to => :string, :ocd_id => :string }
```

**Step 4.**  Now use psql to import these .sql shape records into the new_districts table.  Give the correct database endpoint after argument -h

Production
```
 psql -U ocp -d ocp_new -h new-postgres12-7.c8rvchfbyjh2.us-east-1.rds.amazonaws.com -f ~/canada/oct2021/STATELOWER_CA.sql
 psql -U ocp -d ocp_new -h new-postgres12-7.c8rvchfbyjh2.us-east-1.rds.amazonaws.com -f ~/canada/oct2021/NATIONALLOWER_CA.sql
```

Staging
```
psql -U ocp -d ocp_new -h new-staging-127.c8rvchfbyjh2.us-east-1.rds.amazonaws.com -f ~/canada/oct2021/STATELOWER_CA.sql
psql -U ocp -d ocp_new -h new-staging-127.c8rvchfbyjh2.us-east-1.rds.amazonaws.com -f ~/canada/oct2021/NATIONALLOWER_CA.sql
```

- If running this locally with docker, you may want to insert the sql files into your docker/postgres/ folder and run the following commands instead:
```
     docker-compose exec postgres psql -U ocp -d ocp -f /ocp/postgres/STATELOWER_CA.sql
     docker-compose exec postgres psql -U ocp -d ocp -f /ocp/postgres/NATIONALLOWER_CA.sql
```

**Step 5.**  Now you should be able to run import_cicero_canada_shapefiles.  Use the record flag to make changes to the database.
```
bundle exec rake import_cicero_canada_shapefiles RAILS_ENV=production

bundle exec rake import_cicero_canada_shapefiles[record] RAILS_ENV=production
```
You can include the noconvert flag if you don't need to convert ca_geom to geom.
