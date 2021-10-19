# KnowWho import

## Prep for KnowWho import

### Location for download of KnowWho data
Know who data is downloaded via ftp.  Click or copy/paste this url into a browser window:

[ftp://205.134.170.180](ftp://205.134.170.180)

Your FTP login credentials are:
```
User Name: ftp_oneclick
Password: he77kv48
```

Bring up an additional browser window and drag over the two csv zip files to store in code/KnowWhoImports locally on my Mac.  They will look something like this:

- fedleg_l1_csv_101821.zip
- stateleg_l1_csv_101821.zip

Double click each of them in Finder locally to unzip.  There will now be two folders that look something like this:

- fedleg_l1_csv_101821/
- stateleg_l1_csv_101821/


#### steps to backup, copy to correct locations, and checkin
```
git checkout master
git pull

mv lib/import_data/us/federal/* lib/import_data/us/backup/federal
mv lib/import_data/us/state/* lib/import_data/us/backup/state

cp ../KnowWhoImports/fedleg_l1_csv_101821/Committees.csv lib/import_data/us/federal
cp ../KnowWhoImports/fedleg_l1_csv_101821/DistrictLUT.csv lib/import_data/us/federal
cp ../KnowWhoImports/fedleg_l1_csv_101821/Members.csv lib/import_data/us/federal
cp ../KnowWhoImports/fedleg_l1_csv_101821/Offices.csv lib/import_data/us/federal
cp ../KnowWhoImports/fedleg_l1_csv_101821/Assignments.csv lib/import_data/us/federal

cp ../KnowWhoImports/stateleg_l1_csv_101821/Assignments.csv lib/import_data/us/state
cp ../KnowWhoImports/stateleg_l1_csv_101821/Committees.csv lib/import_data/us/state
cp ../KnowWhoImports/stateleg_l1_csv_101821/DistrictLUT.csv lib/import_data/us/state
cp ../KnowWhoImports/stateleg_l1_csv_101821/Members.csv lib/import_data/us/state
cp ../KnowWhoImports/stateleg_l1_csv_101821/Offices.csv lib/import_data/us/state

git add lib/import_data/
git commit -m "KnowWho Import Data for 10-18-21"
git push
```

## Deploy master to prod
[Deploy](deploy.html) - Steps for deployment to production and staging.


## Do the actual import on product

Log into prod:
```
ssh_prod
```

Go the the correct directory
```
cd /home/deploy/apps/ocp/current
```

Confirm the files are the new ones copied above
```
ls -l /home/deploy/apps/ocp/current/lib/import_data/us/federal/
ls -l /home/deploy/apps/ocp/current/lib/import_data/us/state/
```

Open up the production rails console
```
bundle exec rails c production
```

The USRecipientImporter (lib/importer_modules/us_importers.rb) object diffs the reps listed in /import_data against the existing database and prepares updates.  

Run .match() first to find changed seats, and then attempt a first .import() to see any anticipated problems.  If no problems are reported, then run .import() again with the flag :record => true to make changes to the database.  

This is currently tested in spec/libs/united_states_import_spec.rb

```
require ('importer_modules/united_states/us_importers')
importer = Importer::USRecipientImporter.instance  
importer.match :except_states => ['PR','AS','VI','GU','MP']
```

Look for problems matching.  If none, then
```
importer.all_problems
```

Comm upper errors are ok.
Chamber lower American Samoa, Puerto Rico, Virgin Islands, Guam if there is vacancy that’s fine too.

You can run the following to check which states are having issues:
```
states_arr = []
importer.all_problems[:district_matcher].last.each do |str|
  states_arr << str.split(', state ').last.slice(0, 2)
end
puts states_arr.uniq.join(", ")
```

If the results only include AS, GU, PR, VI, MP (American Samoa, Guam, Puerto Rico, Virgin Islands, Northern Mariana Islands), then you should be good to continue.

(if no meaningful problems are found, then:)
```
importer.import :addresses_options => {:except => ['webform']}
importer.import(:record => true, :addresses_options => {:except => ['webform']})
```

Next, to update US committees and committee assignments, use the USCommitteeMatcher and USAssignmentImporter objects:
```
c = Importer::USCommitteeMatcher.instance
c.import_and_update_committees
c.import_and_update_committees :record => true
```

Then clean out old committees
```
c.inactivate_old_committees
c.inactivate_old_committees :record => true
```

Then update committee relationships
```
c.import_committee_relationships
c.import_committee_relationships :record => true
```

Then clean the committee relationships
```
c.clean_committee_relationships
c.clean_committee_relationships :record => true


a = Importer::USAssignmentImporter.instance
a.import
a.import :record => true
```
