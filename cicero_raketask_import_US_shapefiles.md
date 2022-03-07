## Instructions from update_us.rake

Before using rake import_cicero_us_shapefiles, you'll need to import Cicero's latest shapefiles into the new_districts table

**Step 1.**  Start with shp2pgsql calls to convert the two relevant .shp files into usable .sql:
```
sudo shp2pgsql -s 4326 -g us_geom /Users/dt/Downloads/cicero_us_districts/district_statelower_us.shp public.new_districts > STATELOWER_US.sql
sudo shp2pgsql -s 4326 -g us_geom /Users/dt/Downloads/cicero_us_districts/district_nationallower_us.shp public.new_districts > NATIONALLOWER_US.sql

shp2pgsql -t 2D -s 4326 -g us_geom cicero_us_state_and_federal_districts/district_stateupper_us.shp public.new_districts > STATEUPPER_US.sql
shp2pgsql -t 2D -s 4326 -g us_geom cicero_us_state_and_federal_districts/district_statelower_us.shp public.new_districts > STATELOWER_US.sql
shp2pgsql -t 2D -s 4326 -g us_geom cicero_us_state_and_federal_districts/district_nationallower_us.shp public.new_districts > NATIONALLOWER_US.sql

```
The national upper shapes are just the state/territory boundaries themselves, which we won't need to match against lats and lons.

**Step 2.**  For each of the .sql files generated, delete the first few lines of sql, until you get to the INSERT INTO statements.

Susan added: Copy the sql files to staging/production

```
cd ~/us/
mkdir 2022_02_28

sudo chmod 775 2022_02_28/
sudo chown ubuntu 2022_02_28/
sudo chgrp ubuntu 2022_02_28/
```

# STOP!!!  DISCONNECT FROM YOUR VPN FIRST!!!
staging - 938hg3kk
```
scp -i ~/.ssh/ ../CiceroImports/us/*US.sql ubuntu@ec2-54-235-144-131.compute-1.amazonaws.com:~/us/2022_02_28
```
prod - 938hg3kk
```
scp -i ~/.ssh/id_rsa *US.sql ubuntu@prod.oneclickpolitics.com:~/us/2022_02_28
```

   The preceding lines are used to set up our new_districts table, and we won't need them - we're going to do this with the NewDistrict.reset_table command.

**Step 3.**  Now use .reset_table to give us the precise new_districts table we need:
```
NewDistrict.reset_table :columns => { :district_i => :string, :state => :string, :district_t => :float, :subtype => :string, :valid_from => :string, :valid_to => :string, :ocd_id => :string }
```

**Step 4.**  Now use psql to import these .sql shape records into the new_districts table.  Give the correct database endpoint after argument -h

Production
```
psql -U ocp -d ocp_new -h new-postgres12-7.c8rvchfbyjh2.us-east-1.rds.amazonaws.com -f ~/us/2022_02_28/STATELOWER_US.sql
psql -U ocp -d ocp_new -h new-postgres12-7.c8rvchfbyjh2.us-east-1.rds.amazonaws.com -f ~/us/2022_02_28/STATEUPPER_US.sql
psql -U ocp -d ocp_new -h new-postgres12-7.c8rvchfbyjh2.us-east-1.rds.amazonaws.com -f ~/us/2022_02_28/NATIONALLOWER_US.sql
```

Staging
```
psql -U ocp -d ocp_new -h new-staging-127.c8rvchfbyjh2.us-east-1.rds.amazonaws.com -f ~/us/jan2022/STATELOWER_US.sql
psql -U ocp -d ocp_new -h new-staging-127.c8rvchfbyjh2.us-east-1.rds.amazonaws.com -f ~/us/jan2022/STATEUPPER_US.sql
psql -U ocp -d ocp_new -h new-staging-127.c8rvchfbyjh2.us-east-1.rds.amazonaws.com -f ~/us/jan2022/NATIONALLOWER_US.sql
```

- If running this locally with docker, you may want to insert the sql files into your docker/postgres/ folder and run the following commands instead:
```
     docker-compose exec postgres psql -U ocp -d ocp -f /ocp/postgres/STATELOWER_US.sql
     docker-compose exec postgres psql -U ocp -d ocp -f /ocp/postgres/STATEUPPER_US.sql
     docker-compose exec postgres psql -U ocp -d ocp -f /ocp/postgres/NATIONALLOWER_US.sql
```

**Step 5.**  Now you should be able to run import_cicero_us_shapefiles.  Use the record flag to make changes to the database.
```
bundle exec rake import_cicero_us_shapefiles RAILS_ENV=production

bundle exec rake import_cicero_us_shapefiles[record] RAILS_ENV=production
```
You can include the noconvert flag if you don't need to convert us_geom to geom.
