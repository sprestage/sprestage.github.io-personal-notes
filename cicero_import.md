# Cicero import

### check to see if the new import is ready
# STOP!!!  DISCONNECT FROM YOUR VPN FIRST!!!
```
alias ls_cicero="aws --profile cicero_user s3 ls --recursive s3://cicero-global-data-us-east-1/OneClickPolitics/"
```

### copy cicero sql files to prod
# STOP!!!  DISCONNECT FROM YOUR VPN FIRST!!!
```
scp -i ~/.ssh/id_rsa ../../one-click-politics/docker/postgres/*CA.sql ubuntu@ec2-184-72-246-33.compute-1.amazonaws.com:~/australia/sep2021
```

don't use `new-production-3` like below, use the ip address above:
```
scp -i ~/.ssh/id_rsa docker/postgres/*.sql new-production-3.c8rvchfbyjh2.us-east-1.rds.amazonaws.com:/australia/sep2021
```
54.235.144.131


[Import AU](#to-update-australia)

[Import CA](#to-update-canada)

[Import UK](#to-update-united-kingdom)

---


## Updating Cicero data for Australia, Canada, United Kingdom, and United States

For Australia, Canada, United Kingdom, and United States, our third-party Cicero service provides both shapefiles and recipient .CSVs.  


### To update US

  [Step 1 - Download and extract the shapefiles and .CSVs from our Cicero S3 bucket](#us-step-1) <br>
  [Step 2 - Copy new .CSV files into the corresponding subfolder](#us-step-3) <br>
  [Step 3 - rarely needed - Update US Districts and Shapefiles](#us-step-2) <br>
  [Step 4 - Updating US Recipients](#us-step-4) <br>
  [Step 5 - Troubleshooting ("Party ... not found" messages)](#us-step-5) <br>

  [US name updater testing](#us-name-updater-testing)

#### US Step 1
**Download and extract the shapefiles and .CSVs from our Cicero S3 bucket.**

# STOP!!!  DISCONNECT FROM YOUR VPN FIRST!!!
You'll need the AWS command line client, as well as an AWS profile with appropriate credentials.  On OSX, your credentials file should be saved to:
```
  ~/.aws/credentials  
```

and should include a user with access to our Cicero S3 bucket:
```
  [cicero_user]
  aws_access_key_id = xxx
  aws_secret_access_key = yyy
```

To access the latest Cicero data using these credentials, call:
```
  aws --profile cicero_user s3 ls --recursive s3://cicero-global-data-us-east-1/OneClickPolitics/
```

Retrieve the latest shapefiles by downloading and extracting cicero_us_districts.zip:
```
  aws --profile cicero_user s3 cp s3://cicero-global-data-us-east-1/OneClickPolitics/latest/cicero_us_state_and_federal_districts.zip cicero_us_districts.zip
```

Pull the latest .CSVs by downloading and extracting cicero_us_officials.zip, cicero_us_officials_levels.zip, and cicero_us_officials_roles.zip:
```

  aws --profile cicero_user s3 cp s3://cicero-global-data-us-east-1/OneClickPolitics/latest/cicero_us_state_and_federal_officials.zip cicero_us_officials.zip

  aws --profile cicero_user s3 cp s3://cicero-global-data-us-east-1/OneClickPolitics/latest/cicero_us_state_and_federal_officials_committees.zip cicero_us_officials_committees.zip

  aws --profile cicero_user s3 cp s3://cicero-global-data-us-east-1/OneClickPolitics/latest/cicero_us_state_and_federal_officials_identifiers.zip cicero_us_officials_identifiers.zip

  aws --profile cicero_user s3 cp s3://cicero-global-data-us-east-1/OneClickPolitics/latest/cicero_us_state_and_federal_officials_staff.zip cicero_us_officials_staff.zip

```


#### US Step 2
Unzip these, and rename the .csvs
```
mv cicero_us_state_and_federal_officials_identifiers.csv cicero_us_officials_identifiers.csv
mv cicero_us_state_and_federal_officials.csv cicero_us_officials.csv
mv cicero_us_state_and_federal_officials_committees.csv cicero_us_officials_committees.csv
mv cicero_us_state_and_federal_officials_staff.csv cicero_us_officials_staff.csv

mv ../../one-click-politics/lib/import_data/us/cicero/cicero_us_officials_identifiers.csv ../../one-click-politics/lib/import_data/us/backup
mv ../../one-click-politics/lib/import_data/us/cicero/cicero_us_officials.csv ../../one-click-politics/lib/import_data/us/backup
mv ../../one-click-politics/lib/import_data/us/cicero/cicero_us_officials_committees.csv ../../one-click-politics/lib/import_data/us/backup
mv ../../one-click-politics/lib/import_data/us/cicero/cicero_us_officials_staff.csv ../../one-click-politics/lib/import_data/us/backup

cp cicero_us_officials*.csv ../../one-click-politics/lib/import_data/us/cicero/

cp cicero_us_officials.csv ../../one-click-politics/lib/import_data/us/cicero/
cp cicero_us_officials_committees.csv ../../one-click-politics/lib/import_data/us/cicero/
cp cicero_us_officials_identifiers.csv ../../one-click-politics/lib/import_data/us/cicero/
cp cicero_us_officials_staff.csv ../../one-click-politics/lib/import_data/us/cicero/
```

Lastly, copy these .csv files into lib/import_data/us/cicero/


#### US Step 3 - this step should rarely be needed
**Update US Districts and Shapefiles**
We shouldn’t need to update shapes often, but when it’s necessary to update shapes, download the US shapes from our Cicero source, and follow the instructions in

lib/tasks/update_congress.rake

in the comments above the task :import_cicero_us_shapefiles.

When you reach step 5, skip the section labeled 5 (alt), which includes alternate steps needed on the very first Cicero import.  Just follow the instructions for step 5, listed underneath 5 (alt).


#### US Step 4
**Updating US Recipients**
```
require ('importer_modules/united_states/cicero/cicero_us_importers')
Importer::CiceroUSDistrictMatcher.instance.setup
Importer::CiceroUSRowChecker.instance.setup
Importer::CiceroUSRecipientImporter.instance.setup
Importer::CiceroUSRecipientImporter.instance.match
Importer::CiceroUSRecipientImporter.instance.all_problems
```

Here you'll see a number of problems related to missing districts and parties for Puerto Rico, the Virgin Islands, Guam, etc.  You can ignore these.

```
Importer::CiceroUSRecipientImporter.instance.import
Importer::CiceroUSRecipientImporter.instance.all_problems

Importer::CiceroUSRecipientImporter.instance.import(:record => true)
```

You can then update our list of active committees via:

```
Importer::CiceroUSCommitteeMatcher.instance.setup
Importer::CiceroUSCommitteeMatcher.instance.import_and_update_committees(:record => true)
Importer::CiceroUSCommitteeMatcher.instance.inactivate_old_committees(:record => true)
```

Then, if, and only if, Cicero subcommittee support has been added to the .CSV, you can update the committee relationships.  

(If Cicero subcommittees aren’t in yet, skip these next two lines, and go straight to updating assignments via “Importer::CiceroUSAssignmentImporter.instance.setup.”  You’ll know subcommittees are in the .CSV if the cicero_us_officials_committees.csv file has the subcommittee_of column.)

```
Importer::CiceroUSCommitteeMatcher.instance.import_committee_relationships(:record => true)

Importer::CiceroUSCommitteeMatcher.instance.clean_committee_relationships(:record => true)
```

(^ If subcommittee support isn't in Cicero's .CSVs yet, you can skip the previous two lines.)

And update committee assignments via:

```
Importer::CiceroUSAssignmentImporter.instance.setup
Importer::CiceroUSAssignmentImporter.instance.import(:record => true)
```

Finally, you can use

```
Importer::CiceroUSRecipientImporter.instance.deactivate_non_cicero_us_reps
Importer::CiceroUSRecipientImporter.instance.deactivate_non_cicero_us_reps(:record => true)
```

to deactivate any old non-Cicero US reps lingering in the system.

Newly imported US Congress members will need to have CwcAddress or CwcApiAddress records made for them.

To do this automatically, exit the Rails console, and run the rake tasks:

```
RAILS_ENV=production bundle exec rake cwc_office_code
RAILS_ENV=production bundle exec rake populate_cwc_api_address
```

These tasks shouldn't duplicate or override any existing address records.

#### US RecipientBios and Staffers
You can now update our staffer data by entering the Rails console and running:

```
require ('importer_modules/united_states/cicero/import_cicero_us_legislator_profiles)
```

First, you can clear existing legislator profiles and staffer data:

```
importer = ImportCiceroUSLegislatorProfiles.instance
importer.clear_existing_profiles :clear_active => true
```

Second, import the new data via:    

```
importer.import
importer.import({record: true})
```

These steps will clear and then replace the RecipientBio records that provide legislator profiles, as well as Staffer records, and the RecipientOffice records that designate where they work and join them to Recipients.


### To update Australia:
  [Step 1 - Download and extract the shapefiles and .CSVs from our Cicero S3 bucket](#au-step-1) <br>
  [Step 2 - Update Australian Districts and Shapefiles](#au-step-2) <br>
  [Step 3 - Copy new .CSV files into the corresponding subfolder](#au-step-3) <br>
  [Step 4 - Updating Australian Recipients](#au-step-4) <br>
  [Step 5 - Troubleshooting ("Party ... not found" messages)](#au-step-5) <br>

  [AU name updater testing](#au-name-updater-testing)

#### AU Step 1
**Download and extract the shapefiles and .CSVs from our Cicero S3 bucket.**

# STOP!!!  DISCONNECT FROM YOUR VPN FIRST!!!
You'll need the AWS command line client, as well as an AWS profile with appropriate credentials.  On OSX, your credentials file should be saved to:

```
  ~/.aws/credentials  
```

and should include a user with access to our Cicero S3 bucket:

```
  [cicero_user]
  aws_access_key_id = xxx
  aws_secret_access_key = yyy
```

To access the latest Cicero data using these credentials, call:

```
  aws --profile cicero_user s3 ls --recursive s3://cicero-global-data-us-east-1/OneClickPolitics/
```

Retrieve the latest shapefiles by downloading and extracting cicero_au_districts.zip:

```
  aws --profile cicero_user s3 cp s3://cicero-global-data-us-east-1/OneClickPolitics/latest/cicero_au_districts.zip cicero_au_districts.zip
```

Pull the latest .CSVs by downloading and extracting cicero_au_officials.zip, cicero_au_officials_levels.zip, and cicero_au_officials_roles.zip:

```
  aws --profile cicero_user s3 cp s3://cicero-global-data-us-east-1/OneClickPolitics/latest/cicero_au_officials.zip cicero_au_officials.zip

  aws --profile cicero_user s3 cp s3://cicero-global-data-us-east-1/OneClickPolitics/latest/cicero_au_officials_identifiers.zip cicero_au_officials_identifiers.zip
```

#### AU Step 2
**Update Australian Districts and Shapefiles**

Follow the instructions for import_cicero_australia_shapefiles in update_australia.rake.  [Rakefile instructions](cicero_raketask_import_au_shapefiles.html)

Just remember you will need to put the .sql files into “/docker/postgres/” locally.

#### AU Step 3
**Copy new .CSV files into the corresponding subfolder of:**

```
  lib/import_data
```

You'll want to extract cicero_au_officials.zip and copy the .CSV:

```
  cicero_au_officials.csv
```

into:

```
  One-Click-Politics/lib/import_data/australia/cicero_au_officials.csv
```

replacing any .csv file already there.  

As of March 2021 (and discovered in July 2021), Cicero has split their levels data and roles data out of the main CSV and into each one’s own CSV. This wrought havoc on our normal import process. Maged and Nate found and modified an existing CSV Merger script to recreate the original file’s data, so that we can get by for now. Here’s the file: https://www.dropbox.com/s/ilm7gp9lo4n1c9l/csv_merge.rb?dl=0
The file currently assumes the CSV files are in the same directory as the file. Just run
```
  ruby csv_merge.rb
```
with the correct filenames, and the result.csv should be the new officials csv.
Susan and Nate have also found that there have occasionally been a few troublesome rows - specifically ones with a “level” of “headOfGovernment”. These have sparked an error finding the id for nil:NilClass in the importer_modules.rb file. You can safely delete these rows.

You'll need to update this .CSV on any environment where you plan to update reps.  For this reason, it's best to check this change into source, and deploy to both production and staging.

##### merge troubleshooting
If you see this error:
```
/System/Library/Frameworks/Ruby.framework/Versions/2.6/usr/lib/ruby/2.6.0/csv/parser.rb:869:in `parse_quotable_robust':
Any value after quoted field isn't allowed in line 445. (CSV::MalformedCSVError)
```
it is a result of this string, `'"`, being used in the description field.  In VI, a global search and replace will fix the issue.  `:%s/'"/'/`.  Feel free to go to each line in the editor of your choice to see what I mean.  When you run the merge again, it will stop at the next row with this issue.

#### AU Step 4
**Updating Australian Recipients**

Once you’ve updated cicero_au_officials.csv, complete the imports using the AustraliaRecipientImporter object.

The AustraliaRecipientImporter object in

```
lib/importer_modules/australia/australia_importers.rb
```

operates in much the same way as the US imports described above.  Make sure to import Cicero’s district shapefiles as described above before importing recipients.

```
require ('importer_modules/australia/australia_importers')
```

##### If we need to import any of the parties defined in Importer::Australia.parties
```
party_importer = Importer::AustraliaPartyImporter.instance
party_importer.import
party_importer.import :record => true
```

##### import recipients, but only after we’ve imported our districts
```
recipient_importer = Importer::AustraliaRecipientImporter.instance
recipient_importer.setup
recipient_importer.match
recipient_importer.all_problems # Look at problems
recipient_importer.import
recipient_importer.all_problems # Look at problems
recipient_importer.import :record => true
```

If calling

```
  recipient_importer.all_problems
```

returns "Party ... not found" error messages, you may need to add new Party records to our system, and then attempt the imports again.  

##### import recipients as above, but with last_name, first_name overwrite enabled
```
recipient_importer.import(:overwrite_firstname => true, :overwrite_lastname => false)
recipient_importer.all_problems # Look at problems
recipient_importer.import(:record => true, :overwrite_firstname => true, :overwrite_lastname => false)

```

##### troubleshooting problems with match or import
When running the matcher step, `recipient_importer.match` and see this when looking at `recipient_importer.all_problems`:
```
:office_matcher=>[["No Office record found for comm JOINT)\n", "No Office record found for comm JOINT)\n", "No Office record found for comm JOINT)\n", "No Office record found for comm JOINT)\n", "No Office record found for comm JOINT)\n", "No Office record found for comm JOINT)\n"]]
```
look through the .csv file for weird roles.  There should be only two, in AU anyway, legislatorUpperBody and legislatorLowerBody.  This error was most recently caused (in the October import) by some duplicated headofGovernment rows being added.  Further investigation showed this duplication is being introduced during the merge.  Need to create a Jira to fix this issue in the csv_merge.rb ruby script.

When running the import `recipient_importer.import` and see this when looking at `recipient_importer.all_problems`:
```
:recipient_importer=>[["Row cannot be imported with missing fields", "Row cannot be imported with missing fields"]]
```
This is the same problem as above, just the .import step instead of the .match step.


#### AU Step 5
**"Party ... not found" messages mean that we might be missing Party records from our database, and/or missing party names from our country_definitions.rb file.**

First, for any missing party, make sure the party name and abbreviation appear in the Australia.parties method in:

```
  lib/importer_modules/country_definitions.rb
```

If they don't appear in this list, add them.  Then run the rake task:

```
  RAILS_ENV=production bundle exec rake import_au_parties[record]
```

to make sure all of these parties have a record in our database.  


### Updating Australian Districts and Shapefiles

See steps 1-2, above.

### Updating Australian Recipient Data

See steps 1 and 3-5, above.


#### AU name updater testing
```
recipient_importer.import(:overwrite_firstname => false, :overwrite_lastname => false)
recipient_importer.all_problems # Look at problems
recipient_importer.import(:overwrite_firstname => false, :overwrite_lastname => false, :record => true)

recipient_importer.import(:overwrite_firstname => true, :overwrite_lastname => false)
recipient_importer.all_problems # Look at problems
recipient_importer.import(:overwrite_firstname => true, :overwrite_lastname => false, :record => true)

recipient_importer.import(:overwrite_firstname => false, :overwrite_lastname => true)
recipient_importer.all_problems # Look at problems
recipient_importer.import(:overwrite_firstname => false, :overwrite_lastname => true, :record => true)

recipient_importer.import(:overwrite_firstname => true, :overwrite_lastname => true)
recipient_importer.all_problems # Look at problems
recipient_importer.import(:overwrite_firstname => true, :overwrite_lastname => true, :record => true)
```

---

### To update Canada:
[Step 1 - Download and extract the shapefiles and .CSVs from our Cicero S3 bucket](#ca-step-1) <br>
[Step 2 - Update Australian Districts and Shapefiles](#ca-step-2) <br>
[Step 3 - Copy new .CSV files into the corresponding subfolder](#ca-step-3) <br>
[Step 4 - Updating Australian Recipients](#ca-step-4) <br>
[Step 5 - Troubleshooting ("Party ... not found" messages)](#ca-step-5) <br>

#### CA Step 1
**Download and extract the shapefiles and .CSVs from our Cicero S3 bucket.**

You'll need the AWS command line client, as well as an AWS profile with appropriate credentials.  On OSX, your credentials file should be saved to:

```
  ~/.aws/credentials  
```

and should include a user with access to our Cicero S3 bucket:

```
  [cicero_user]
  aws_access_key_id = xxx
  aws_secret_access_key = yyy
```

To access the latest Cicero data using these credentials, call:

```
  aws --profile cicero_user s3 ls --recursive s3://cicero-global-data-us-east-1/OneClickPolitics/
```

**Retrieve the latest shapefiles** by downloading and extracting cicero_ca_districts.zip:

```
  aws --profile cicero_user s3 cp s3://cicero-global-data-us-east-1/OneClickPolitics/latest/cicero_ca_districts.zip cicero_ca_districts.zip
```

**Pull the latest .CSVs** by downloading and extracting cicero_ca_officials.zip, cicero_ca_officials_roles.zip, and cicero_ca_officials_levels.zip:

```
  aws --profile cicero_user s3 cp s3://cicero-global-data-us-east-1/OneClickPolitics/latest/cicero_ca_officials.zip cicero_ca_officials.zip

aws --profile cicero_user s3 cp s3://cicero-global-data-us-east-1/OneClickPolitics/latest/cicero_ca_officials_roles.zip cicero_ca_officials_roles.zip

aws --profile cicero_user s3 cp s3://cicero-global-data-us-east-1/OneClickPolitics/latest/cicero_ca_officials_levels.zip cicero_ca_officials_levels.zip
```

#### CA Step 2
**Update Canadian Districts and Shapefiles**

Follow the instructions for import_cicero_canada_shapefiles in update_canada.rake.  [Rakefile instructions](cicero_raketask_import_ca_shapefiles.html)

Just remember you will need to insert the .sql files into “/docker/postgres/” locally.

#### CA Step 3
**Copy new .CSV files into the corresponding subfolder of:**

```
  lib/import_data
```

You'll want to extract cicero_ca_officials.zip and copy the .CSV:

```
  cicero_ca_officials.csv
```

into:

```
  One-Click-Politics/lib/import_data/canada/cicero_ca_officials.csv
```

replacing any .csv file already there.  

As of March 2021 (and discovered in July 2021), Cicero has split their levels data and roles data out of the main CSV and into each one’s own CSV. This wrought havoc on our normal import process. Maged and Nate found and modified an existing CSV Merger script to recreate the original file’s data, so that we can get by for now. Here’s the file: https://www.dropbox.com/s/ilm7gp9lo4n1c9l/csv_merge.rb?dl=0
The file currently assumes the CSV files are in the same directory as the file. Just run
```
  ruby csv_merge.rb
```
with the correct filenames, and the result.csv should be the new officials csv.

You'll need to update this .CSV on any environment where you plan to update reps.  For this reason, it's best to check this change into source, and deploy to both production and staging.

##### merge troubleshooting
If you see this error:
```
/System/Library/Frameworks/Ruby.framework/Versions/2.6/usr/lib/ruby/2.6.0/csv/parser.rb:869:in `parse_quotable_robust': Any value after quoted field isn't allowed in line 445. (CSV::MalformedCSVError)
```
it is a result of this string, `'"`, being used in the description field.  In VI, a global search and replace will fix the issue.  `:%s/'"/'/`.

#### CA Step 4
**Updating Canadian Recipients**

Once you’ve updated cicero_ca_officials.csv, complete the imports using the CanadaRecipientImporter object.

The CanadaRecipientImporter object in

```
lib/importer_modules/canada/canada_importers.rb
```

operates in much the same way as the US imports described above.  Make sure to import Cicero’s district shapefiles as described above before importing recipients.

```
require ('importer_modules/canada/canada_importers')
```

##### If we need to import any of the parties defined in Importer::Canada.parties
```
party_importer = Importer::CanadaPartyImporter.instance
party_importer.import
party_importer.import :record => true
```

##### import recipients, but only after we’ve imported our districts
```
recipient_importer = Importer::CanadaRecipientImporter.instance
recipient_importer.setup
recipient_importer.match
recipient_importer.all_problems # Look at problems
recipient_importer.import
recipient_importer.all_problems # Look at problems
recipient_importer.import :record => true
```

If calling
```
  recipient_importer.all_problems
```
returns "Party ... not found" error messages, you may need to add new Party records to our system, and then attempt the imports again.  

#### CA Step 5
**"Party ... not found" messages mean that we might be missing Party records from our database, and/or missing party names from our country_definitions.rb file.**

First, for any missing party, make sure the party name and abbreviation appear in the Canada.parties method in:
```
  lib/importer_modules/country_definitions.rb
```

If they don't appear in this list, add them.  Then run the rake task:
```
  bundle exec rake import_ca_parties[record] RAILS_ENV=production
```
to make sure all of these parties have a record in our database.  

### Updating Canadian Districts and Shapefiles

See steps 1-2 above.


## Notes from my last CA import - LOCAL

```
susanprestage@Susans-MBP code % cd CiceroImports/canada
susanprestage@Susans-MBP canada % ls cicero_ca_districts

susanprestage@Susans-MBP canada % sudo shp2pgsql -s 4326 -g ca_geom ./cicero_ca_districts/district_statelower_ca.shp public.new_districts > STATELOWER_CA.sql
susanprestage@Susans-MBP canada % sudo shp2pgsql -s 4326 -g ca_geom ./cicero_ca_districts/district_nationallower_ca.shp public.new_districts > NATIONALLOWER_CA.sql

susanprestage@Susans-MBP canada % vi NATIONALLOWER_CA.sql
susanprestage@Susans-MBP canada % vi STATELOWER_CA.sql
susanprestage@Susans-MBP canada % mv *.sql ../../docker/postgres
susanprestage@Susans-MBP canada % ls -l ../../docker/postgres
total 389368
 64584 -rw-r--r--  1 susanprestage  staff   33064581 Sep 21 10:29 NATIONALLOWER_CA.sql
324784 -rw-r--r--  1 susanprestage  staff  166287793 Sep 21 10:29 STATELOWER_CA.sql
     0 drwxr-xr-x  3 susanprestage  staff         96 Jul 13 09:36 setup/
susanprestage@Susans-MBP canada % pwd
/Users/susanprestage/code/CiceroImports/canada
susanprestage@Susans-MBP canada % ls -l ../../one-click-politics/docker/postgres
total 835592
190008 -rw-r--r--  1 susanprestage  staff   97281004 Sep 20 10:25 NATIONALLOWER_AU.sql
 83480 -rw-r--r--  1 susanprestage  staff   42739577 Sep 20 10:25 NATIONALUPPER_AU.sql
191832 -rw-r--r--  1 susanprestage  staff   98216343 Sep 20 10:25 STATELOWER_AU.sql
370272 -rw-r--r--  1 susanprestage  staff  189575779 Sep 20 10:25 STATEUPPER_AU.sql
     0 drwxr-xr-x  3 susanprestage  staff         96 Jul 13 09:45 setup/
susanprestage@Susans-MBP canada % mv ../../docker/postgres/*.sql ../../one-click-politics/docker/postgres
susanprestage@Susans-MBP canada % ls -l ../../one-click-politics/docker/postgres                         

susanprestage@Susans-MBP one-click-politics % docker-compose exec postgres psql -U ocp -d ocp -f docker/postgres/STATELOWER_CA.sql
WARNING: Some networks were defined but are not used by any service: my-network-name
docker/postgres/STATELOWER_CA.sql: No such file or directory
susanprestage@Susans-MBP one-click-politics % docker-compose exec postgres psql -U ocp -d ocp -f /ocp/postgres/STATELOWER_CA.sql
WARNING: Some networks were defined but are not used by any service: my-network-name
INSERT 0 1
INSERT 0 1
INSERT 0 1
.
.
.
.

susanprestage@Susans-MBP one-click-politics % docker-compose exec postgres psql -U ocp -d ocp -f /ocp/postgres/NATIONALLOWER_CA.sql
WARNING: Some networks were defined but are not used by any service: my-network-name
INSERT 0 1
INSERT 0 1
.
.
.

susanprestage@Susans-MBP one-click-politics % cd ../CiceroImports/canada                              
susanprestage@Susans-MBP canada % cp ../australia/csv_merge.rb .
susanprestage@Susans-MBP canada % ls
total 186040
     0 cicero_ca_districts/		   568 cicero_ca_officials.zip		   392 cicero_ca_officials_roles.csv
182272 cicero_ca_districts.zip		   368 cicero_ca_officials_levels.csv	    56 cicero_ca_officials_roles.zip
  2328 cicero_ca_officials.csv		    48 cicero_ca_officials_levels.zip	     8 csv_merge.rb
susanprestage@Susans-MBP canada % l csv_merge.rb
8 -rw-r--r--@ 1 susanprestage  staff  1392 Sep 21 10:54 csv_merge.rb
susanprestage@Susans-MBP canada % ruby csv_merge.rb

susanprestage@Susans-MBP canada % vi result.csv
susanprestage@Susans-MBP canada % s
zsh: command not found: s
susanprestage@Susans-MBP canada % ls
total 190152
     0 cicero_ca_districts/		   368 cicero_ca_officials_levels.csv	     8 csv_merge.rb
182272 cicero_ca_districts.zip		    48 cicero_ca_officials_levels.zip	  4112 result.csv
  2328 cicero_ca_officials.csv		   392 cicero_ca_officials_roles.csv
   568 cicero_ca_officials.zip		    56 cicero_ca_officials_roles.zip
susanprestage@Susans-MBP canada % mv result.csv ../../one-click-politics/lib/import_data/canada/cicero_ca_officials.csv


susanprestage@Susans-MBP one-click-politics % docker-compose exec ocp bundle exec rake import_ca_parties\[record\] RAILS_ENV=production

susanprestage@Susans-MBP one-click-politics % ls -l docker/postgres/*CA.sql
 64584 -rw-r--r--  1 susanprestage  staff   33064581 Sep 21 10:29 docker/postgres/NATIONALLOWER_CA.sql
324784 -rw-r--r--  1 susanprestage  staff  166287793 Sep 21 10:29 docker/postgres/STATELOWER_CA.sql
```

## Notes from my last CA import - STAGING


### To update United Kingdom:
  [Step 1 - Download and extract the shapefiles and .CSVs from our Cicero S3 bucket](#uk-step-1) <br>
  [Step 2 - Update United Kingdom Districts and Shapefiles](#uk-step-2) <br>
  [Step 3 - Copy new .CSV files into the corresponding subfolder](#uk-step-3) <br>
  [Step 4 - Updating United Kingdom Recipients](#uk-step-4) <br>
  [Step 5 - Troubleshooting ("Party ... not found" messages)](#uk-step-5) <br>

  [UK name updater testing](#uk-name-updater-testing)

#### UK Step 1
**Download and extract the shapefiles and .CSVs from our Cicero S3 bucket.**

# STOP!!!  DISCONNECT FROM YOUR VPN FIRST!!!
You'll need the AWS command line client, as well as an AWS profile with appropriate credentials.  On OSX, your credentials file should be saved to:

```
  ~/.aws/credentials  
```

and should include a user with access to our Cicero S3 bucket:

```
  [cicero_user]
  aws_access_key_id = xxx
  aws_secret_access_key = yyy
```

To access the latest Cicero data using these credentials, call:

```
  aws --profile cicero_user s3 ls --recursive s3://cicero-global-data-us-east-1/OneClickPolitics/
```

Retrieve the latest shapefiles by downloading and extracting cicero_uk_districts.zip:

```
  aws --profile cicero_user s3 cp s3://cicero-global-data-us-east-1/OneClickPolitics/latest/cicero_uk_districts.zip cicero_uk_districts.zip
```

Pull the latest .CSVs by downloading and extracting cicero_uk_officials.zip, cicero_uk_officials_levels.zip, and cicero_uk_officials_roles.zip:

```
  aws --profile cicero_user s3 cp s3://cicero-global-data-us-east-1/OneClickPolitics/latest/cicero_uk_officials.zip cicero_uk_officials.zip

  aws --profile cicero_user s3 cp s3://cicero-global-data-us-east-1/OneClickPolitics/latest/cicero_uk_officials_levels.zip cicero_uk_officials_levels.zip

  aws --profile cicero_user s3 cp s3://cicero-global-data-us-east-1/OneClickPolitics/latest/cicero_uk_officials_roles.zip cicero_uk_officials_roles.zip
```

#### UK Step 2
**Update United Kingdom Districts and Shapefiles**

Follow the instructions for import_cicero_united_kingdom_shapefiles in update_united_kingdom.rake.  [Rakefile instructions](cicero_raketask_import_uk_shapefiles.html)

Just remember you will need to put the .sql files into “/docker/postgres/” locally.

#### UK Step 3
**Copy new .CSV files into the corresponding subfolder of:**

```
  lib/import_data
```

You'll want to extract cicero_uk_officials.zip and copy the .CSV:

```
  cicero_uk_officials.csv
```

into:

```
  One-Click-Politics/lib/import_data/united_kingdom/cicero_uk_officials.csv
```

replacing any .csv file already there.  

As of March 2021 (and discovered in July 2021), Cicero has split their levels data and roles data out of the main CSV and into each one’s own CSV. This wrought havoc on our normal import process. Maged and Nate found and modified an existing CSV Merger script to recreate the original file’s data, so that we can get by for now. Here’s the file: https://www.dropbox.com/s/ilm7gp9lo4n1c9l/csv_merge.rb?dl=0
The file currently assumes the CSV files are in the same directory as the file. Just run
```
  ruby csv_merge.rb
```
with the correct filenames, and the result.csv should be the new officials csv.
Susan and Nate have also found that there have occasionally been a few troublesome rows - specifically ones with a “level” of “headOfGovernment”. These have sparked an error finding the id for nil:NilClass in the importer_modules.rb file. You can safely delete these rows.

You'll need to update this .CSV on any environment where you plan to update reps.  For this reason, it's best to check this change into source, and deploy to both production and staging.

##### merge troubleshooting
If you see this error:
```
/System/Library/Frameworks/Ruby.framework/Versions/2.6/usr/lib/ruby/2.6.0/csv/parser.rb:869:in `parse_quotable_robust':
Any value after quoted field isn't allowed in line 445. (CSV::MalformedCSVError)
```
it is a result of this string, `'"`, being used in the description field.  In VI, a global search and replace will fix the issue.  `:%s/'"/'/`.  Feel free to go to each line in the editor of your choice to see what I mean.  When you run the merge again, it will stop at the next row with this issue.

#### UK Step 4
**Updating United Kingdom Recipients**

Once you’ve updated cicero_uk_officials.csv, complete the imports using the UnitedKingdomRecipientImporter object.

The UnitedKingdomRecipientImporter object in

```
lib/importer_modules/united_kingdom/united_kingdom_importers.rb
```

operates in much the same way as the US imports described above.  Make sure to import Cicero’s district shapefiles as described above before importing recipients.

```
require ('importer_modules/united_kingdom/united_kingdom_importers')
```

##### If we need to import any of the parties defined in Importer::UnitedKingdom.parties
```
party_importer = Importer::UnitedKingdomPartyImporter.instance
party_importer.import
party_importer.import :record => true
```

##### import recipients, but only after we’ve imported our districts
```
recipient_importer = Importer::UnitedKingdomRecipientImporter.instance
recipient_importer.setup
recipient_importer.match
recipient_importer.all_problems # Look at problems
recipient_importer.import
recipient_importer.all_problems # Look at problems
recipient_importer.import :record => true
```

If calling

```
  recipient_importer.all_problems
```

returns "Party ... not found" error messages, you may need to add new Party records to our system, and then attempt the imports again.  

##### import recipients as above, but with last_name, first_name overwrite enabled
```
recipient_importer.import(:overwrite_firstname => true, :overwrite_lastname => false)
recipient_importer.all_problems # Look at problems
recipient_importer.import(:record => true, :overwrite_firstname => true, :overwrite_lastname => false)

```

##### troubleshooting problems with match or import
When running the matcher step, `recipient_importer.match` and see this when looking at `recipient_importer.all_problems`:
```
:office_matcher=>[["No Office record found for comm JOINT)\n", "No Office record found for comm JOINT)\n", "No Office record found for comm JOINT)\n", "No Office record found for comm JOINT)\n", "No Office record found for comm JOINT)\n", "No Office record found for comm JOINT)\n"]]
```
look through the .csv file for weird roles.  There should be only two, in AU anyway, legislatorUpperBody and legislatorLowerBody.  This error was most recently caused (in the October import) by some duplicated headofGovernment rows being added.  Further investigation showed this duplication is being introduced during the merge.  Need to create a Jira to fix this issue in the csv_merge.rb ruby script.

When running the import `recipient_importer.import` and see this when looking at `recipient_importer.all_problems`:
```
:recipient_importer=>[["Row cannot be imported with missing fields", "Row cannot be imported with missing fields"]]
```
This is the same problem as above, just the .import step instead of the .match step.


#### UK Step 5
**"Party ... not found" messages mean that we might be missing Party records from our database, and/or missing party names from our country_definitions.rb file.**

First, for any missing party, make sure the party name and abbreviation appear in the UnitedKingdom.parties method in:

```
  lib/importer_modules/country_definitions.rb
```

If they don't appear in this list, add them.  Then run the rake task:

```
  RAILS_ENV=production bundle exec rake import_uk_parties[record]
```

to make sure all of these parties have a record in our database.  


### Updating United Kingdom Districts and Shapefiles

See steps 1-2, above.

### Updating United Kingdom Recipient Data

See steps 1 and 3-5, above.


#### AU name updater testing
```
recipient_importer.import(:overwrite_firstname => false, :overwrite_lastname => false)
recipient_importer.all_problems # Look at problems
recipient_importer.import(:overwrite_firstname => false, :overwrite_lastname => false, :record => true)

recipient_importer.import(:overwrite_firstname => true, :overwrite_lastname => false)
recipient_importer.all_problems # Look at problems
recipient_importer.import(:overwrite_firstname => true, :overwrite_lastname => false, :record => true)

recipient_importer.import(:overwrite_firstname => false, :overwrite_lastname => true)
recipient_importer.all_problems # Look at problems
recipient_importer.import(:overwrite_firstname => false, :overwrite_lastname => true, :record => true)

recipient_importer.import(:overwrite_firstname => true, :overwrite_lastname => true)
recipient_importer.all_problems # Look at problems
recipient_importer.import(:overwrite_firstname => true, :overwrite_lastname => true, :record => true)
```

---
