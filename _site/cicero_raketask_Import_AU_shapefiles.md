## Instructions from update_australia.rake

Before using rake import_cicero_austrlia_shapefiles, you'll need to import Cicero's latest shapefiles into the new_districts table

**Step 1.**  Start with shp2pgsql calls to convert the two relevant .shp files into usable .sql:
```
     sudo shp2pgsql -t 2D -s 4326 -g au_geom /Users/dt/Downloads/cicero_au_districts/district_statelower_au.shp public.new_districts > STATELOWER_AU.sql
     sudo shp2pgsql -t 2D -s 4326 -g au_geom /Users/dt/Downloads/cicero_au_districts/district_stateupper_au.shp public.new_districts > STATEUPPER_AU.sql
     sudo shp2pgsql -t 2D -s 4326 -g au_geom /Users/dt/Downloads/cicero_au_districts/district_nationallower_au.shp public.new_districts > NATIONALLOWER_AU.sql
     sudo shp2pgsql -t 2D -s 4326 -g au_geom /Users/dt/Downloads/cicero_au_districts/district_nationalupper_au.shp public.new_districts > NATIONALUPPER_AU.sql
```
   The national upper shapes are just the state/territory boundaries themselves, which we won't need to match against lats and lons.

**Step 2.**  For each of the .sql files generated, delete the first few lines of sql, until you get to the INSERT INTO statements.

Susan added: Copy the sql files to staging/production (/938hg3kk)

staging - 938hg3kk
```
scp -i ~/.ssh/ ../CiceroImports/australia/*AU.sql ubuntu@ec2-54-235-144-131.compute-1.amazonaws.com:~/australia/sep2021
```
prod - 938hg3kk
```
scp -i ~/.ssh/id_rsa ../../one-click-politics/docker/postgres/*AU.sql ubuntu@ec2-184-72-246-33.compute-1.amazonaws.com:~/australia/sep2021
```

   The preceding lines are used to set up our new_districts table, and we won't need them - we're going to do this with the NewDistrict.reset_table command.

**Step 3.**  Now use .reset_table to give us the precise new_districts table we need:
```
 NewDistrict.reset_table :au_geom_srid => '4326', :columns => { :district_i => :string, :city => :string, :state => :string, :district_t => :float, :subtype => :string, :valid_from => :string, :valid_to => :string, :ocd_id => :string }
```

**Step 4.**  Now use psql to import these .sql shape records into the new_districts table.  Give the correct database endpoint after argument -h

Production
```
psql -U ocp -d ocp_new -h new-production-2.c8rvchfbyjh2.us-east-1.rds.amazonaws.com -f ~/australia/sep2021/STATELOWER_AU.sql
psql -U ocp -d ocp_new -h new-production-2.c8rvchfbyjh2.us-east-1.rds.amazonaws.com -f ~/australia/sep2021/STATEUPPER_AU.sql
psql -U ocp -d ocp_new -h new-production-2.c8rvchfbyjh2.us-east-1.rds.amazonaws.com -f ~/australia/sep2021/NATIONALLOWER_AU.sql
psql -U ocp -d ocp_new -h new-production-2.c8rvchfbyjh2.us-east-1.rds.amazonaws.com -f ~/australia/sep2021/NATIONALUPPER_AU.sql
```
Staging
```
psql -U ocp -d ocp_new -h new-staging-127.c8rvchfbyjh2.us-east-1.rds.amazonaws.com -f ~/australia/sep2021/STATELOWER_AU.sql
psql -U ocp -d ocp_new -h new-staging-127.c8rvchfbyjh2.us-east-1.rds.amazonaws.com -f ~/australia/sep2021/STATEUPPER_AU.sql
psql -U ocp -d ocp_new -h new-staging-127.c8rvchfbyjh2.us-east-1.rds.amazonaws.com -f ~/australia/sep2021/NATIONALLOWER_AU.sql
psql -U ocp -d ocp_new -h new-staging-127.c8rvchfbyjh2.us-east-1.rds.amazonaws.com -f ~/australia/sep2021/NATIONALUPPER_AU.sql
```
Locally with docker, put the sql files into your docker/postgres/ folder and run the following commands instead:
```
     docker-compose exec postgres psql -U ocp -d ocp -f /ocp/postgres/STATELOWER_AU.sql
     docker-compose exec postgres psql -U ocp -d ocp -f /ocp/postgres/STATEUPPER_AU.sql
     docker-compose exec postgres psql -U ocp -d ocp -f /ocp/postgres/NATIONALLOWER_AU.sql
     docker-compose exec postgres psql -U ocp -d ocp -f /ocp/postgres/NATIONALUPPER_AU.sql
```

**Step 5.**  Now you should be able to run import_cicero_canada_shapefiles.  Use the [record] flag to make changes to the database.
```
bundle exec rake import_cicero_australia_shapefiles

bundle exec rake import_cicero_australia_shapefiles[record]
```
