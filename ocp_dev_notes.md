# OCP daily dev notes

[Deploy](deploy.html) Steps for deployment to production and staging.

[KnowWho Import](/know_who_import.html) Everything needed for the KnowWho import.

[Cicero Import](/cicero_import.html) Everything needed for the CA and AU Cicero imports.


## Thu, Sep 30 2021
### prepping for knowwho import

#### Know Who Data Location for download
Know who data is downloaded via ftp.

Either copy and paste this url into a browser window:
```
ftp://205.134.170.180
```
Or, click to go to this section of the Dev doc to find the link to click, https://docs.google.com/document/d/1mG8TRVEyglQeQfrGsnnYRsxP5zJewE_hxa0IYPnR0bs/edit#heading=h.kpbi96mjbov7

Your FTP login credentials are:
User Name: ftp_oneclick
Password: he77kv48

Bring up an additional browser window and drag over the two csv zip files to store in code/KnowWhoImports locally on my Mac.

Double click to unzip.

Fedlet_11_csv
Stateleg_11_csv

#### steps to backup, copy to correct locations, and checkin
```
git checkout master
git pull

mv lib/import_data/us/federal/* lib/import_data/us/backup/federal
mv lib/import_data/us/state/* lib/import_data/us/backup/state

cp ../KnowWhoImports/fedleg_l1_csv_092721/Committees.csv lib/import_data/us/federal
cp ../KnowWhoImports/fedleg_l1_csv_092721/DistrictLUT.csv lib/import_data/us/federal
cp ../KnowWhoImports/fedleg_l1_csv_092721/Members.csv lib/import_data/us/federal
cp ../KnowWhoImports/fedleg_l1_csv_092721/Offices.csv lib/import_data/us/federal
cp ../KnowWhoImports/fedleg_l1_csv_092721/Assignments.csv lib/import_data/us/federal

cp ../KnowWhoImports/stateleg_l1_csv_092721/Assignments.csv lib/import_data/us/state
cp ../KnowWhoImports/stateleg_l1_csv_092721/Committees.csv lib/import_data/us/state
cp ../KnowWhoImports/stateleg_l1_csv_092721/DistrictLUT.csv lib/import_data/us/state
cp ../KnowWhoImports/stateleg_l1_csv_092721/Members.csv lib/import_data/us/state
cp ../KnowWhoImports/stateleg_l1_csv_092721/Offices.csv lib/import_data/us/state

git add lib/import_data/
git commit -m "KnowWho Import Data for 9-27-21"
git push
```

#### deploy master to prod (look at pinned message in slack)

#### link to instructions for how to do the actual KnowWho import on prod
https://gist.github.com/sprestage/5d7fd086b6555b3268db408e56c04eba#friday-6-august-2021


### copy cicero sql files to prod
```
scp -i ~/.ssh/id_rsa ../../one-click-politics/docker/postgres/*CA.sql ubuntu@ec2-184-72-246-33.compute-1.amazonaws.com:~/australia/sep2021
```

```
NewDistrict.find_in_batches(batch_size: 50) do |batch|
  batch.each do |district|
    puts district.ocd_id
  end
end
```

## Mon, 13 Sep 2021
### deploy to production
(says Dave) please deploy to the pre-production/nb box after major deploys to production (e.g. deploys with db migrations), so if you run a major deploy to chara via DEPLOY=chara branch=master cap deploy please follow it up with a deploy to the nb box via DEPLOY=pre_prod branch=master cap deploy.

### PR 384
Once PR-384 (by Dave) goes to production, update local docker
```
you should be able to update your “basic” docker image by running:
aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin 104377796283.dkr.ecr.us-east-1.amazonaws.com

docker pull 104377796283.dkr.ecr.us-east-1.amazonaws.com/ocp/development:basic

after that, whenever you run docker-compose build ocp it should use the new “basic” image.  the changes i’ve made should be back-compatible with postgres 9.6, so it shouldn’t be necessary to tinker with database exports or anything yet

since the pull request is now part of master, please make sure to run these two commands on your local environments
aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin 104377796283.dkr.ecr.us-east-1.amazonaws.com

docker pull 104377796283.dkr.ecr.us-east-1.amazonaws.com/ocp/development:basic

before building your ocp image via docker-compose build ocp.

```

## Fri, 10 Sep 2021
### Analytics notes
```
+40521    @promoter_id = params[:promoter_id]
+    @promoter = PromoterUser.find(@promoter_id)
+13763, 13755, 13803,     @promoted_messages = PromotedMessage.where(creator_id: @promoter_id)
+count = 9,
+
+69, Conversion.where(promoted_message_id: 13803).count
+
+irb(main):009:0> pm.email_activity
+=> 21
+irb(main):010:0> pm.total_activity
+=> 21
+4 twitter_activity: 0,
+2 call_activity: 0,
+1 email_activity: 21,
+5 total_activity: 21
+conversion_activity: 69
+3 video_activity: 0,
+
+1 emails
+2 calls
+3 videos
+4 tweets
+5 total actions
+visits
+
+binding.pry
```


## Thu, 9 Sep 2021
### environment variables
for production and staging

```
sudo vi /home/deploy/apps/ocp/shared/config/application.yml

sudo nginx -s reload
```

## Thu, 26 Aug 2021
### covid
Got my second vaccine today.  Kai got his first.  Yeay!

### more good Dave advice for prod
hi guys, it looks like the agents are in a corrupted state again where too many of them stuck around after the last stop_daemons.  just a reminder to check production for any agents still lingering around after you call stop_daemons by calling
```ps aux | grep agent```
and turning them off by passing their $process_id numbers to
```sudo kill -9 $process_id ```


## Wed, 25 Aug 2021
### deployment advice
from Dave:

hey guys, just a reminder that after you change an env like PUBLISH_DELIVERY_RECEIPTS, you need to restart the services referencing it for the change to be locked in, because the rails environment only checks application.yml at startup.  that means if something in the webserver code is checking the env, restart the webserver with sudo nginx -s reload.  if something in the agents code is checking the env, restart the agents.  

### troubleshooting
from Dave:
- if it’s a 500 you should be able to check newrelic for the stacktrace
- if it’s a 502, are we hitting the redis usage cap again?
- one of the tickets i linked above has instructions on how to check redis usage from the console, or you can look in aws
- you could check and see how many messages are sitting in the queues and whether the pileup of emails is related


## Mon, 23 Aug 2021
```
rails generate migration AddTwitterEnabledToPromoterUsers twitter_enabled:boolean
```


## Sat, 21 Aug 2021


## Wed, 18 Aug 2021
### Twitter info
Here, https://gist.github.com/sprestage/5d7fd086b6555b3268db408e56c04eba#twitter


## Tuesday, 17 Aug 2021
### standup
I explained the problems with the specs for the invalid address fix.  

When testing the invalid email address fix, the spec correctly populates Step 1, then gets the error message prompting for a correct email address while remaining on the Step 1 page.

When testing the invalid street address fix, the spec appears to correctly populate Step 1, but then gets no error message and brings up Step 2.  When testing this by hand, I see that the fix is in place and the user is required to enter a vaild street address with the Next button inactivated, which is the correct behavior that the spec does not see.


## Monday, 16 Aug 2021

### standup
Friday I worked on the front end portion of the Address field fix.  I’m working on the specs now.  Then onto Twitter and wrapping up the review of Alex’s PR.

#### Friday I:
- got my PR done for the CWC error logging fix with some tests added/fixed
- fought my environment, breaking and re-fixing it when actually the problem was in the tests.  Fixed it one last time, then re-implemented the address error fix, then the tests, piece by piece.  
#### Today I plan to:
- test the fix for the invalid address and get the specs working
- work on Twitter
- wrap up review of Alex's PR


## Friday, 13 Aug 2021
### standup
- Approved Shams’ PR.  
- Got most of the way through Alex’s (unfinished) CWC integration PR, so it’ll be quicker when the work is complete.
- Thank you, Alex, for mentioning the oddities in the CWC error messages.  The process of implementing the exceptions and other captures of CWC errors meant that the cwc_message wasn’t being created, so it couldn’t be displayed in the logs.  I went back a step and am logging the agent_message instead, to correct for this problem in the logs.  I’ll have a PR ready for that shortly.  We can push that today, which I’m largely against on the principle that Friday pushes are a bad idea.  Also some tests were added/fixed, so it isn’t only log messages.
- Today I will get back to the front end portion of the invalid address fix.  
- And, I hope, also to the Twitter stuff, though that last may be a stretch.  

I’m heading out today by 3:00 Central time for our beach trip


## Thursday, 12 Aug 2021

### today's plan
- Take a look at Alex and Shams PRs
- Work on the front end work for the Invalid Address Issue.
- Take a look at the logs since yesterday’s deployment.

### logs, email exception
3:53
Time to check the logs and investigate the CWC email error that came through.  

4:08 PM
There is an email exception.  Make sure the backend captured this correctly so nothing was sent to CWC.  August 12, 2021 10:31:55.965

### Alex's PR
10:59 AM
Spent some time working my way through Alex’s PR.  Taking it in chunks since it is not yet complete.

3:53 PM
Got most of the way through Alex’s PR.  I’ll finish the last 4 files tomorrow as I’m going crosseyed from reviewing both Shams and Alex’s PRs.


## Wednesday, 11 August 2021

### Twitter
tech@oneclickpolitics.com, use 1password, phone number for question 6128452310.  log into twitter account

change our app to use the new keys

need to log the tweets so we can track the number of tweets (and the offenders who cause trouble)

### invalid address work
PR for the backend work of the Invalid Address CWC issue, ON-1238, is ready for review, https://github.com/one-click-politics/one-click-politics/pull/345

I split this into two tickets for the backend work and the frontend work (ON-1281).


## Tuesday, 10 August 2021
### new thing coming
I only heard the very last bit of this when Maged said my name.  Something about the question of is there a list of ISPs that are blocked.  I will sync with Maged when he finishes his initial info dive on this.

Been pretty busy these last few days, so haven't kept up these notes, but also very productive.

### status
yesterday:
- I finished the invalid delivery id work for another CWC error.  (if details: very occasionally, the generated delivery id for a cwc message was too short and we’d receive an error from the CWC).  Small fix, really.  PR is posted in Engineering.  
- I started in on the Address Invalid CWC error.

today:
- Working on the Address Invalid CWC error.  Unless something unexpected turns up, I’ll have the PR ready today.  
- look at Alex’s PR

### office codes
I was looking at the logs to see how if anything new showed up for CWC since yesterday’s push.  So, we have a fresh list of the currently supported office codes:

Log details (~439 currently active offices).  

I’ll branch off of master and remove the log messages right after standup.  Done.  https://github.com/one-click-politics/one-click-politics/pull/342.  I created a Jira for tracking, ON-1279. The office codes we are storing in fixtures.rb are still up to date after 13 months.  I added a comment to this effect.

message CWC CLIENT OFFICES AVAILABLE - [“HAK00”, “HAL01", “HAL02”, “HAL03", “HAL04”, “HAL05", “HAL06”, “HAL07", “HAR01”, “HAR02", “HAR03”, “HAR04", “HAZ01”, “HAZ02", “HAZ03”, “HAZ04", “HAZ05”, “HAZ06", “HAZ07”, “HAZ08", “HAZ09”, “HCA01", “HCA02”, “HCA03", “HCA04”, “HCA05", “HCA06”, “HCA07", “HCA08”, “HCA09", “HCA10”, “HCA11", “HCA12”, “HCA13", “HCA14”, “HCA15", “HCA16”, “HCA17", “HCA18”, “HCA19", “HCA20”, “HCA21", “HCA22”, “HCA23", “HCA24”, “HCA25", “HCA26”, “HCA27", “HCA28”, “HCA29", “HCA30”, “HCA31", “HCA32”, “HCA33", “HCA34”, “HCA35", “HCA36”, “HCA37", “HCA38”, “HCA39", “HCA40”, “HCA41", “HCA42”, “HCA43", “HCA44”, “HCA45", “HCA46”, “HCA47", “HCA48”, “HCA49", “HCA50”, “HCA51", “HCA52”, “HCA53", “HCO01”, “HCO02", “HCO03”, “HCO04", “HCO05”, “HCO06", “HCO07”, “HCT01", “HCT02”, “HCT03", “HCT04”, “HCT05", “HDC00”, “HDE00", “HFL01”, “HFL02", “HFL03”, “HFL04", “HFL05”, “HFL06", “HFL07”, “HFL08", “HFL09”, “HFL10", “HFL11”, “HFL12", “HFL13”, “HFL14", “HFL15”, “HFL16", “HFL17”, “HFL18", “HFL19”, “HFL20", “HFL21”, “HFL22", “HFL23”, “HFL24", “HFL25”, “HFL26", “HFL27”, “HGA01", “HGA02”, “HGA03", “HGA04”, “HGA05", “HGA06”, “HGA07", “HGA08”, “HGA09", “HGA10”, “HGA11", “HGA12”, “HGA13", “HGA14”, “HGU00", “HHI01”, “HHI02", “HIA01”, “HIA02", “HIA03”, “HIA04", “HID01”, “HID02", “HIL01”, “HIL02", “HIL03”, “HIL04", “HIL05”, “HIL06", “HIL07”, “HIL08", “HIL09”, “HIL10", “HIL11”, “HIL12", “HIL13”, “HIL14", “HIL15”, “HIL16", “HIL17”, “HIL18", “HIN01”, “HIN02", “HIN03”, “HIN04", “HIN05”, “HIN06", “HIN07”, “HIN08", “HIN09”, “HKS01", “HKS02”, “HKS03", “HKS04”, “HKY01", “HKY02”, “HKY03", “HKY04”, “HKY05", “HKY06”, “HLA01", “HLA02”, “HLA03", “HLA04”, “HLA05", “HLA06”, “HMA01", “HMA02”, “HMA03", “HMA04”, “HMA05", “HMA06”, “HMA07", “HMA08”, “HMA09", “HMD01”, “HMD02", “HMD03”, “HMD04", “HMD05”, “HMD06", “HMD07”, “HMD08", “HME01”, “HME02", “HMI01”, “HMI02", “HMI03”, “HMI04", “HMI05”, “HMI06", “HMI07”, “HMI08", “HMI09”, “HMI10", “HMI11”, “HMI12", “HMI13”, “HMI14", “HMN01”, “HMN02", “HMN03”, “HMN04", “HMN05”, “HMN06", “HMN07”, “HMN08", “HMO01”, “HMO02", “HMO03”, “HMO04", “HMO05”, “HMO06", “HMO07”, “HMO08", “HMS01”, “HMS02", “HMS03”, “HMS04", “HMT00”, “HNC01", “HNC02”, “HNC03", “HNC04”, “HNC05", “HNC06”, “HNC07", “HNC08”, “HNC09", “HNC10”, “HNC11", “HNC12”, “HNC13", “HND00”, “HNE01", “HNE02”, “HNE03", “HNH01”, “HNH02", “HNJ01”, “HNJ02", “HNJ03”, “HNJ04", “HNJ05”, “HNJ06", “HNJ07”, “HNJ08", “HNJ09”, “HNJ10", “HNJ11”, “HNJ12", “HNM01”, “HNM02", “HNM03”, “HNV01", “HNV02”, “HNV03", “HNV04”, “HNY01", “HNY02”, “HNY03", “HNY04”, “HNY05", “HNY06”, “HNY07", “HNY08”, “HNY09", “HNY10”, “HNY11", “HNY12”, “HNY13", “HNY14”, “HNY15", “HNY16”, “HNY17", “HNY18”, “HNY19", “HNY20”, “HNY21", “HNY22”, “HNY23", “HNY24”, “HNY25", “HNY26”, “HNY27", “HOH01”, “HOH02", “HOH03”, “HOH04", “HOH05”, “HOH06", “HOH07”, “HOH08", “HOH09”, “HOH10", “HOH11”, “HOH12", “HOH13”, “HOH14", “HOH15”, “HOH16", “HOK01”, “HOK02", “HOK03”, “HOK04", “HOK05”, “HOR01", “HOR02”, “HOR03", “HOR04”, “HOR05", “HPA01”, “HPA02", “HPA03”, “HPA04", “HPA05”, “HPA06", “HPA07”, “HPA08", “HPA09”, “HPA10", “HPA11”, “HPA12", “HPA13”, “HPA14", “HPA15”, “HPA16", “HPA17”, “HPA18", “HPR00”, “HRI01", “HRI02”, “HSC01", “HSC02”, “HSC03", “HSC04”, “HSC05", “HSC06”, “HSC07", “HSD00”, “HTN01", “HTN02”, “HTN03", “HTN04”, “HTN05", “HTN06”, “HTN07", “HTN08”, “HTN09", “HTX01”, “HTX02", “HTX03”, “HTX04", “HTX05”, “HTX06", “HTX07”, “HTX08", “HTX09”, “HTX10", “HTX11”, “HTX12", “HTX13”, “HTX14", “HTX15”, “HTX16", “HTX17”, “HTX18", “HTX19”, “HTX20", “HTX21”, “HTX22", “HTX23”, “HTX24", “HTX25”, “HTX26", “HTX27”, “HTX28", “HTX29”, “HTX30", “HTX31”, “HTX32", “HTX33”, “HTX34", “HTX35”, “HTX36", “HUT01”, “HUT02", “HUT03”, “HUT04", “HVA01”, “HVA02", “HVA03”, “HVA04", “HVA05”, “HVA06", “HVA07”, “HVA08", “HVA09”, “HVA10", “HVA11”, “HVI00", “HVT00”, “HWA01", “HWA02”, “HWA03", “HWA04”, “HWA05", “HWA06”, “HWA07", “HWA08”, “HWA09", “HWA10”, “HWI01", “HWI02”, “HWI03", “HWI04”, “HWI05", “HWI06”, “HWI07", “HWI08”, “HWV01", “HWV02”, “HWV03", “HWY00”, “MP00"] (edited)


## Friday, 6 August 2021

- need to correctly branch ON-1237 (delivery_id) off of master
- then change branch back to ON-1235 (inactive office)
- add logged messages in the office code validator within the validate method in client.rb
- checkin the above and flag Alex and Nate for PR finalization with planned release on Monday

### end

My first KnowWho import.

Log into prod:
```
ssh_prod
```

Open up the production rails console
```
cd /home/deploy/apps/ocp/current
bundle exec rails c production
```

Here are the files
```
ls -l /home/deploy/apps/ocp/current/lib/import_data/us/federal/
ls -l /home/deploy/apps/ocp/current/lib/import_data/us/state/
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



3pm make international transfer.

5pm call Danny about
- getting someone to cut lock off of the deposito

5pm call Kevin about
- advice about broken windshield

Order allergy meds


15672 guest/guest as the user/password



## Thu, 5 Aug 2021
### invalid email issue
Further information on the invalid email issue still showing up in the logs after the front end fix was pushed to production:
It was suggested in standup today that the reason this keeps happening is that the SenderProfile is an existing one and so the old email is automatically used and not entered through the UI.  I can confirm the UI in prod is validating the email.  I can also confirm that the offending invalid email addresses are SenderProfiles created before the fix was pushed to production.

#### Potential solutions:
- Create a rake task to run an email validation on all SenderProfiles in production and flag those with issues or set them to an empty string or ?  Pro: This will catch all possible future Invalid Email CWC errors.  Con: There are 17 million SP records in prod.  This seems a solution that would want some though to see if it is worth it.
- Have Susan or DevOps keep an eye on the logs and fix the SenderProfile for each invalid email that comes through the logs.  There have only been 13 different invalid emails in the last 90 days (which account for 29 errors logged).  Pro: The emails look straightforward to correct, so very low effort.  Con: I have not yet seen the same invalid email address come in on different days, so this seems like closing the barn door after the horses have escaped.



## Tue, 3 Aug 2021
Maged said in standup that the HDC98 deliver should indeed just be thrown onto the floor by the back end, (because the business needs all offices to be displayed on the front end).  Time to wrap up this issue and get the PR out.

We need New Relic to send us email alerts then alerts are triggered.  Maybe look at elastic to see if they can do this.  Maaged asked me to look again to see if we can't get this set on New



## Mon, 2 Aug 2021
### Current status of the inactive office issue.
#### Back end:  
I’ve coded a capture of the issue that throws an exception and logs the issue.  I will finish the tests and get this finalized in the PR.

#### Front end:
Together, Alex and I could not find where the office HDC98 is coming from.  He suggested that this may be a case where if the CWC fails, the next possible methods of sending (fax or email) should be used according to priority order.  Once we discover what that priority order should be.  

#### House CWC in general:  
We need an offices endpoint that returns the active offices. Also, we need a current copy of the CWC API documentation.  Looking at the www.house.gov site about CWC, I see that we should have received “Technical information relevant to your firm’s participation and use of the CWC Service” when our CWC Application was approved.  With your approval, I would like to email CWCVendors@mail.house.gov to explain that we need a new copy of this documentation.

```
[2] pry(#<CwcHandler>)> message = client.create_message(cwc_message)
=> #<Cwc::Message:0x00000015233038
 @constituent=
  {:prefix=>"Mx",
   :first_name=>"Jane",
   :last_name=>"Everyman",
   :address=>["1000 Providence Highway"],
   :city=>"Norwood",
   :state_abbreviation=>"MA",
   :zip=>"02062",
   :email=>"jeveryman@oneclickpolitics.com",
   :phone=>"617-555-0000",
   :address_validation=>true,
   :email_validation=>true},
 @delivery=
  {:agent=>
    {:name=>"testing_delivery_agent",
     :ack_email=>"testing_delivery_ack@email.com",
     :contact_name=>"testing_agent_contact",
     :contact_email=>"testing_agent_contact@email.com",
     :contact_phone=>"202-800-8877"},
   :organization=>{},
   :campaign_id=>"c775788b4db45b59989df2c70fdbf7895f0de12023618a38f5c0a417b7f3699e"},
 @delivery_id="hhhtbil0cwpwr2yr6vrt3yebwaigvxc0",
 @message=
  {:subject=>"Save the whales 1",
   :library_of_congress_topics=>["Congress"],
   :constituent_message=>"From blue baleena to the mighty Melvilleian white, beautiful sea monsters, every one.",
   :more_info=>"",
   :bills=>[]},
 @recipient={:member_office=>"HDC98", :is_response_requested=>true}>
[3] pry(#<CwcHandler>)> valid = client.validate(message)
=> true
[4] pry(#<CwcHandler>)> status = client.deliver(message)
=> true
```



## Thu, 29 Jul 2021

I've gotten rather stuck and would value your input.

### First part (trying to get the office codes from the CWC API from within the test/dev environment)
In client.rb we have this
```
    def offices
      if options[:host] =~ %r{^https://cwc.house.gov}
          Cwc::OfficeCodes.map{ |code| Office.new(code) }
      else
        response = RestClient.get action("/offices")
        JSON.parse(response.body).map{ |code| Office.new(code) }
      end
    end
```
We both initially thought that this was querying the CWC API to get the current office codes.  But it is not.  

I have found that if             
```        Cwc::OfficeCodes.map{ |code| Office.new(code) }
```
then we get the list of office codes defined in app/services/cwc/fixtures.rb

else
```        response = RestClient.get action("/offices")
           JSON.parse(response.body).map{ |code| Office.new(code) }
```
then we get the list of office codes defined in spec/support/fake_apis/fixtures/offices.json.  This seems odd.  To verify that this `.get` is internal, I turned off my wifi before I did the `.get` with the same results as before.  Both ways of retrieving the office codes do not turn up the offending office code, HDC98.  

### Second part (trying to get the office codes from the CWC API from within the production environment)
I've successfully been able to ssh into prod and also to get the rails console to work.  I can make various DB queries also.  But I cannot figure out how to set up a call (get) to the CWC API.  I'm able to set a binding.pry in my dev environment to break out into the client (client.rb) or the CWC handler (cwc_handler.rb) to send the message to the CWC API.

### tunnelblick
I investigated tunnelblick and it is just an open source VPN.  VPNs are lovely, I use ExpressVPN myself to tell the world I'm in Seattle instead of Panama.  That said, the isn't a way to have a VPN give your computer an IP address you define for yourself.  The best they can do is issue you an IP that defines you as coming from a given area.

### testing
I'm not convinced the CWC test API is throwing an error for this issue.  

The CWC's test API does not return the offending inactive office code, HDC98.  However, what we need to see is what is returned by the actual CWC API.  And that API uses a whitelist that only has production's IP address.  The information in the Dev Doc is very spare on this issue.  Fernando was the last person to work on this area.  I'm considering a rake task that I can put on prod to get this information.



Question: I could not find a front end component to the HDC98, inactive office, issue.  I tried working in the front end to re-create this as well as looking through the code.  I would love to pair with someone who either knows where to find this or is willing to dive in with me.  If there is a front end component, I'll create a Jira ticket to cover the work.

Look into Alex's CWC work for the delivery_id issue.  He found some weirdness going on and re-wrote some of it.

Get the CWC response for the office codes and send that off to Maged to handle from a business perspective.


## Wed, 28 Jul 2021
### Today's plan
- [x] Fix test for invalid email backend work, ON-1250
- [x] Finish reviewing the CWC API PR for Alex
- [x] Finish the "Message delivery is not enabled for HDC98" fix on the back end, ON-1235.
- [x] Implement test for HDC98 fix.
- [x] Create a PR for the HDC98 (backend) fix, https://github.com/one-click-politics/one-click-politics/pull/331
- [ ] Work with someone to try to find a front end component for the HDC98 issue.
- [ ] Start investigating what is needed for ON-1237, CWC errors: "The 'DeliveryId' element is invalid".

### What I did yesterday
- Wrapped up the work on the back end portion of the Email validation work and get the PR created.
- Changed the New Relic alerts to capture the new CWC error message work pushed to prod on Friday.
- No new Jira tickets were needed as all CWC errors are being captured.  I'll be watching for new data on existing tickets, but so far the 5 new errors are well understood errors (3 are for invalid email, for example).
- Started looking into the next CWC error Jira ticket, "Message delivery is not enabled for HDC98" (ON-1235).



## Tue, 27 Jul 2021
So, while trying to figure out how to test my fix for HDC98, I realized that I'm not actually testing anything for backend email validation.  Need to make sure that the message contains the invalid email for the test as I am not clear that this is happening yet even though the test passes and appears to do a useful test.  Since an invalid email is not being set in the test data, I don't know why this test passes.  Must investigate.  

### What I plan for today
- [x] wrap up the work on the back end portion of the Email validation work and get the PR created
- [x] set up the alerts for the new CWC error message work pushed to prod on Friday
- [ ] look into the next CWC error Jira ticket, probably, "Message delivery is not enabled for HDC98" (ON-1235)
- [x] create any new Jira tickets needed if there are CWC errors not yet captured; no work needed here

5 new errors since the 19th.  3 are the email error for two different senders.  1 is the delivery not enabled error for HDC98.  1 is a 503 error.  

### What I did yesterday
- [x] create a PR for the Email validation work
- [x] split the ON-1234 ticket for the Email validation into front end and back end work
- [x] start the work on the back end portion of the Email validation work
- [x] reviewed Shams' PR

### standup
**What I did yesterday**
- Split the ON-1234 ticket for the Email validation into frontend and backend work.  
- Created the PR for the work on the Email validation of the widget (front end).  
- Extracted out the new tests from the existing monolithic test file.
- Started the work on the back end portion of the Email validation.
- Reviewed Shams' PR.

**Today's plan**
- Wrap up the work on the back end portion of the Email validation work and get the PR created.
- Set up the alerts for the new CWC error message work pushed to prod on Friday
- Create any new Jira tickets needed if there are CWC errors not yet captured
- stretch goal: Look into the next CWC error Jira ticket, probably, "Message delivery is not enabled for HDC98" (ON-1235)


## Mon, 26 Jul 2021
### What I did today
- [x] create a PR for the Email validation work
- [x] split the ON-1234 ticket for the Email validation into front end and back end work
- [x] start the work on the back end portion of the Email validation work
- [ ] set up the alerts for the new CWC error message work pushed to prod on Friday
- [ ] create any new Jira tickets needed if there are CWC errors not yet captured
- [ ] look into the next CWC error Jira ticket, probably, "Message delivery is not enabled for HDC98" (ON-1235)
- [x] reviewed Shams' PR

The back end work is mostly done.  I want to take a deeper look at the messages_controller to see if I need to put anything there.  The fixes are in the cwc_handler.rb since that is also where a lack of phone number is captured with an error.  Test put in the cwc_handler_spec.rb likewise.


## Fri, 23 Jul 2021
### What I did today
Spent the better half of the day pairing with Nate on the Cicero importing issue.  In the latter half of the day, I finished up the coding on the Email validation issue in the widget.  This is checked in.

### What I plan to do Monday
- [ ] create a PR for the Email validation work
- [ ] split the ON-1234 ticket for the Email validation into front end and back end work
- [ ] start the work on the back end portion of the Email validation work
- [ ] set up the alerts for the new CWC error message work pushed to prod on Friday
- [ ] create any new Jira tickets needed if there are CWC errors not yet captured
- [ ] look into the next CWC error Jira ticket, probably, "Message delivery is not enabled for HDC98" (ON-1235)


## Thu, 22 Jul 2021

Well that was unexpected.  So, I did a brute force thing and put a bit of easily recognizable text in each "Please enter a valid email address" message throughout the code to find where the one showing up in the widget was coming from.  This is in /app/services/phone_widget_handler.rb and comes up when you click Next to go on to Step 2.  

### questions to answer
- where to better validate Email in the widget.  I think there are two places.  One happens as soon as you click out of the Email field.  Then second happens when you try to click Next.
- where to confirm validation of Email in the backend.
- which spec tests step 1 Email validation in the widget.
- which spec tests the backend for validation of widget sent Email.

### things to note and observe
Need to check (account.rb) if a new account is created when there is an invalid email address used in step 1 of the widget.  In the console, check the count of Account before then after step 1.  This will tell me if validating on account creation is the right place to check things on the backend.  ...  On further research, I think that it is a SenderProfile that is the important datatype being created.  It is a Message being created using the widget and message.rb says that it `belongs_to :sender, :class_name => 'SenderProfile'`.

(messages_controller.rb) also has validation going on.  Take a further look at `def all_validations_pass` and see if additional email validation can be set up.  The `@form = :staged` line suggests that the account is created, but not yet saved at the end of step 1.  

(app/services/signature_handler.rb) I'm not sure how this ties in, but I think it does.  A signature is a filled out widget form, if I understand things correctly.  It also populates the SenderProfile with values.

### existing email validation
/app/concerns/emailable.rb contains the regex for email validation.  /spec/concerns/emailable_spec.rb tests this.  The problem email addresses have been added to this and are all well covered by the email validation.  This tells me that whereever the Email validation problem is, it is not using Emailable.

### Nate
- PR for ON-1233, https://github.com/one-click-politics/one-click-politics/pull/326/files.  Is there a way we can set the logger tag to the calling class and thus be able to DRY up all those logger methods?  Just a thought since I twitch every time I see them in a PR.
- Watch him do the csv import.

### Alex
- Walk through where to implement the REGEX for email validation.


## Wed, 21 Jul 2021
```
/app/assets/javascript/widgets.js.erb
```

In standup, I mentioned that I'm weak in the front end and was encouraged to post questions in Slack as it appears that everyone else is stronger here.  Alex particularly raised his hand, so I might PM him when I feel particularly lame but otherwise post in @engineering channel.

### Plan for today
Start working on the Jira tickets for existing CWC errors.

### What I did yesterday
Finished the 8 Jira tickets representing all the CWC errors currently being logged.  Created New Relic alerts for each of those errors.  Reviewed Alex and Nate's PRs.

### docker
Important comand for getting rid of the clutter that docker leaves lying around.
```
docker image prune
docker system prune
```


## Tue, 20 Jul 2021
A total of 8 tickets were created, one for each type of CWC deliver error currently found in logging.  Learned how to create alerts in New Relic, based on the existing CWC alert.  Added myself to the small list (Nate, Maged, Eric) to receive all alerts for issues in CWC delivery.  I generally set these alerts for a single instance, since they generally only had a few (under 10) instances in the last 90 days.  I added metrics to each Jira ticket indicating how many alerts we have seen and when during the last 90 days to use as prioritization for the tickets if needed.  

These 8 tickets (and alerts) represented 129 CWC Handler logged errors.  

### Plan for today
Review Nate and Alex's PRs.  Make edits resulting from comments on my PR.  Finish creating Jira tickets for each type of CWC error found in current logging.  Create alerts for each type of CWC error found in current logging.


## Mon, 19 Jul 2021
Spent the day becoming familiar with each of the different types of CWC error.  Also became familiar with searching for each of these types of errors in New Relic.  Created Jira tickets for 6 of the errors so far, under the Epic, ON-1225 for "Identify and resolve delivery issues", https://oneclickpolitics.atlassian.net/browse/ON-1225.

### Plan for today
Create Jira tickets for existing CWC errors.

### What I did yesterday
I finished ON-1228 as well on Friday and got the PR created.  


## Fri, 16 Jul 2021
Yeay, finished ON-1228 as well.  Checked everything in.  Created the PR, https://github.com/one-click-politics/one-click-politics/pull/325.

1:45pm update: If I'm not mistaken, I've just finished both ON-1226 (cwc.rb) and ON-1227 (cwc_handler.rb).  I still need to create the two branches and get each checked in.  Then I can move on the ON-1228, re-implementing the CWC validation in the cwc_handler.rb file.  Tempted to just create a branch for the epic, ON-1225, since I'd rather see it all code reviewed and pushed to production simultaneously, though I can see an argument against it too, since tasks for adding the alerts associated with this code are under that epic as well.  Things are flexible here, so I can probably just use ON-1225 (the epic)

### ON-1226, Improve cwc.rb logging
I'm not finding anything called "campaign id".  I believe `@promoted_message_id=137` of the `agent_message` is the desired id.  Nope, wrong.  Found it.  Here's how to access the pieces of data needed:

#### succeeded and failed
- campaign id: `cwc_handler.cwc_message[:campaign_id]`    <- in cwc.rb
- who sent it (by email): `agent_message.from_email.split("@")[0]`    <- in cwc.rb
- agent type (cwc): `"cwc"`    <- in cwc.rb

#### failed only
Log message for Failed CWC delivery should  capture why the CWC delivery failed:
- CWC's response error code: ` `    <- in cwc_handler.rb
- CWC's response message body: ` `    <- in cwc_handler.rb
- what we sent to CWC: `agent_message`    <- in cwc.rb

How we are logging now:
```
      Rails.logger.error("CWC Handler error message: (#{message})")
      Rails.logger.error("CWC Handler error processing: (#{e.message}, #{e.errors})")
```

From the logs (Elastic)
```
CWC Handler error message: (#<Cwc::Message:0x00559d485ada08>)
13:37:36.240
CWC Handler error processing: (Cwc::BadRequest, ["The 'Email' element is invalid - The value 'anncook111@gmail' is invalid according to its datatype 'email_type' - The Pattern constraint failed.", "The 'Email' element is invalid - The value 'anncook111@gmail' is invalid according to its datatype 'email_type' - The Pattern constraint failed."])
```

## Thu, 15 Jul 2021

### Plan for tomorrow
Start in on the first Jira task, improve logging for cwc.rb.

### What I did today
Today was all about figuring out what the Jira tickets would be.  Met with Maged to go over the various details to make sure my understanding was in line with his vision.  Finished the day by getting the Epic and associated Tasks created in Jira, with a clear understanding of what needs to be done.

Jiras
- Improve cwc.rb logging
- Improve cwc_handler.rb logging
- Re-implement CWC validation; log reason/reason if success=false

### Meet with Maged and Alex
Planning the Jira tickets and going through the details of what is the improvement we are trying to effect.  The solution is two sides of the same coin.  The goal is to capture the issues with deliveries when they happen and create Jira tickets towards investigating/fixing/changing in order to correct for failures in deliveries.  To do this, the plan is to add relevent logging then create alerts to watch for these logged errors.  When errors are logged, the info needed to track the issue needs to be included in the logs.

#### log messages for succeeded/failed delivery
succeeded cwc delivery log message should contain:
- campaign id
- who sent it (by email)
- agent type (cwc)

failed cwc deliver log message should contain
- campaign id
- who sent it (by email)
- agent type (cwc)
AND
We need to capture why the CWC delivery failed:
- CWC's response error code
- CWC's response message body
- what we sent to CWC

Also take a look at NewRelic for examples of what the CWC's responses look like.  (in Alerts/AI I think?)

#### areas that need logging
- cwc.rb
- cwc_handler.rb
    - look at def cwc_message
    - look at the rescues
- take a look at mq_message.rb for STATUS_SUCCESS, STATUS_QUEUED, etc.

#### create alerts in NewRelic
- Create alerts on one of the errors so we can create Jiras to start clearing up these issues one by one.

#### Elastic
Use Elastic (using 1password to access) to view and search logs.  I had a terrible 15 minutes when I couldn't figure out my password.  I finally figured it out and have taken steps so I don't run into this issue again.  `mp` is the key.  

A good phrase to use to look for issues in the logs is "CWC Handler error processing".

### binding.pry info
I was having trouble looking at the `agent_message` as a whole.  When trying to `puts`, I could only access different bits of data by naming them individually (defined in mq_message, like `agent_message.sender_email`.  And when using `agent_message` in a puts, only the id is printed.  The command needed here is `agent_message.inspect`, with many thanks to Alex for solving this dilemna for me in the meeting.

### Pre Prod
Pre prod is a box on AWS that Eric uses that can be used when a developer is struggling with their local docker container.  New deployments can be made generally without interrupting what Eric is doing.

### Jira plan draft

#### story
Improve logging for CWC - The goal is to have sufficient information logged for later diagnosis of failed deliveries.

#### tasks
- determine information needed for diagnosis of failed deliveries (sender name, sender email, constituent yes/no, recipients?)
- which steps need logging (mq_message.rb, dispatcher.rb, cwc.rb, receiver.rb, I ???)
    - dispatcher: `log("User message created: #{user_message.attributes}"))` Do we want all messages logged?
    - cwc: This one is trickier, as I don't see the way to print out all of `agent_message`; so, which pieces of information do we need for diagnosis?  If we aren't logging all the message data in the dispatcher, then we'll need more info here.
- I THINK NO: tests for logging?
- after new logging is deployed to production, add alerts (NewRelic watching the logs, or how do we do this?)

## Wed, 14 Jul 2021

2:30p Today's task is figuring out the what and where and how of the logging work I'll be doing.  At tomorrow's stand up we'll talk about the breakdown into tasks and helping each other discover what tasks we might have missed.  Today's work is to get to a point where I understand what I'll need to do to accomplish my planned work.

- read CWC section of Dev doc.
- read CWC API doc created by Nate.
- try to find the areas in the code that handle the CWC API calls and find the existing logging (possibly ask Maged or Nate where they look at the prod site's logging that Maged showed us that had the client id info but not much else for a success=failed item.

8:45a Good breakfast, started laundry, washed. some dishes, mocha in hand and water.  Ready to go.

### Front end, admin, and delivery system code tour from Nate for Susan/Alex/Shams

messages once click controller is the beginning of the delivery from the widget
@handler is step one

edit.html shows the steps (1, 2, & 3, i think)

campaigns in the UI = promoted message in the code

messages_controller.rb has step_one

signature without a send is a staged conversion

Maybe delivery handler is where the message for the dispatcher queue.  def deliver_message for creating email message

conversion.rb instantiates the agents  <- this is the start of creating the stuff for the dispatcher queue YEAY

### admin on prod
```
Admin on production PW:
PaNaM4123!
```
www.oneclickpolitics.com/admin
username: sprestage@oneclickpolitics.com

User #28 is the test account

### Planning meeting with Maged, Nate, Alex, and Shams
Want to implement ES to support analytics.  And to get our data out of the .csvs (sender data)
```attribute: city, String,
attribute: city, String, mapping: {fields: {raw: {type: "keyword"}}}    <- for ElasticSearch (ES)
```
oneclickpolitics/ ... /analytics/campaigns


Starts in posts_controller.rb (the nested one in /one_click)
Need to creat ES object to send to the new API for analytics.

Need to better (much) log when we have issues from the CWC API (the US Senate API).  Just get a signature number with no further information.  I think this is what Maged wants me to work on.


Logs present but worthless
logs needed but don't exist
logs that exist but overwhelm with crap

1. enhance the logs
2. connect the logs to new relic alerts

CWC is the first agent to have log improvement <- this is Susan's project initially, then others will do other agents
then implement the alert in New Relic .. there is an example here that was just created by Maged(work w/ Maged or Eric for this step)

Eventually, the Analytics server will be more of a front end to the current monolith (delivery system).  This will be Shamps and Alex's project.

### Basic plan for today

Follow a message through the delivery system from Conversion to Dispatcher Queue to ....¿Agent Queues?..... and finally to Receiver Queue.

From signature to CWC or email.

What is a Conversion vs a Signature.


## Tue, 13 Jul 2021
### Plan for tomorrow
Hoping for server tour (Maged?) and delivery tour (Nate, but he says he doesn't know it well) after standup tomorrow.  Might be wishful thinking.  I need to figure out how to follow a message through the delivery system from Conversion to Dispatcher Queue to ....¿Agent Queues?..... and finally to Receiver Queue.

### What I did today
Finished the day on p52/139 (hmmm, that total went up a page today).  Did a lot of going through relevent code for MQ messaging, agents, and the delivery process.  Took until 2pm to get my container issue resolved and to establish the workaround for testing.  

### Testing
During standup I mentioned I had only found one test for agents so far, `spec/controllers/api_spec.rb`.  It turns out I needed to search on something other than `agent` or `api`.  Alex had tried `rabbit` and came up with 4 more tests for me in `spec/features/rabbitmq_deliveries/`

### Container issues and resolution
Shortly after standup, I realized that no tests were working.  Took the container down, but then couldn't get it to work correctly thereafter.  A variety of attempts and weird errors later I learned to:

  1. delete the Gemfile.lock
  2. run `docker-compose build --no-cache ocp`
  3. run `docker-compose run ocp bundle install`
```
rm Gemfile.lock
docker-compose build --no-cache ocp
docker-compose run ocp bundle install
```
The important step I was missing is that `ocp` usually needs to be rebuilt, especially after deleting the Gemfile.lock.  

### Testing
The container is up and running again, but I cannot successfully run tests locally.  The test(s) do nothing, which is to say that I can call them, but the command returns with zero delay and no messages, errors, or any other indication that something has happened.  Looks like this:

```susanprestage@Susans-MBP one-click-politics % docker-compose exec ocp bundle exec rake db:test:prepare          
susanprestage@Susans-MBP one-click-politics % docker-compose exec ocp bundle exec rspec spec/models/district_spec.rb          
susanprestage@Susans-MBP one-click-politics % docker-compose exec ocp bundle exec rspec spec/models/*
```
To confirm, the docker container is indeed up when the tests are being run.  However, I can run the tests directly in the container.  First, bash into the container.  Don't forget the prepare the test DB.  Then run test(s).

```
susanprestage@Susans-MacBook-Pro one-click-politics % docker-compose exec ocp bash      
root@90b12c7ddf4c:/ocp# rake db:test:prepare
root@90b12c7ddf4c:/ocp# rspec spec/models/district_spec.rb
```

Maged wants to meet to plan next bit of work, but got called away on a tech emergency.  He's pleased we worked together to solve this technical challenge though and doesn't seem worried that I cannot run locally.  Running the tests from the docker container is sufficient for my needs as well, so while it is weird, I can live with weird.

### Delivery

Starts with Conversion, `app/models/conversion.rb` which decides which agents and queues to pass delivery instructions onto.
First destination is the Dispatch Queue, `lib/agents/dispatcher`.  The Receiver Queue is the final destination for archival (for completed deliveries) or to send failed deliveries back into the queues for retries.


## Mon, 12 Jul 2021

Finishing the day at the beginning p42/138 at 6pm.  This covers the deliver process which deserves fresh attention in the morning.

Relaxed day.  Took many little breaks to move my body and let my brain digest.  This is definitely the stull I'll be working on, so it is worth taking time to let it soak in.  I'm also diving in and out of the code as well as the readmes for gem repos in github.  I have an increasingly good perspective on what is going on.  I still want a tour.  Tomorrow or maybe Wednesday, I'll inquire at standup.

### our agents and RabbitMQ
This is the ruby gem being used for RabbitMQ, https://github.com/ruby-amqp/amqp.  Good README explaining everything and worth reading.  Also checked out https://github.com/eventmachine/eventmachine.  Also, this is an even better explanation of queueing and how amqp works, https://www.rabbitmq.com/tutorials/amqp-concepts.html

A question I'm interested in is where are the queues being hosted?  I believe the answer is in the `/config/amqp.yml` file: `production:
  host: localhost
`
It seems to me that this style of our server hosting the queues is a bad idea in the longer term and a solution of remote hosting of the queues should be considered in our future more robust and stable system.

RabbitMQ basically answers the same needs as the SNS and SQS systems on AWS, messaging middleware.

4pm.  Only on p38/138, but that is with also looking at relevent code, figuring out which files are pertinent to this, reviewing the readmes for the 2 relevant gems, amqp and eventmachine, finding the test file and failing to successfully run it.  Wheee!

In the context of starting the node_agent and node_controller locally, it is mentioned to check out the web server and the local agent logs.  `/log/nodeagent.log` or `/log/nodecontroller.log`

Note: Agents send stuff out.  I don't want to start them up before I have more knowledge.  I think, once I have a good foundation, I'll ask Maged (or Nate if he knows how) to give me a tour and talk about the existing tests and when is involved to run them.  The test file `/spec/controllers/api_spec.rb` does not give any indication that tests are running.  In the meantime, here is my best guess of how to run the agents, based on what I've been reading in the Dev doc.

#### guess for how to run agents locally
the below order is the order they must be started and stopped”

```> bundle exec ruby ./daemon/node_controller.rb start
> bundle exec ruby ./daemon/node_agent.rb start

> bundle exec ruby ./daemon/node_agent.rb stop
> bundle exec ruby ./daemon/node_controller.rb stop
```

Note that the agents will start in “production” mode locally - they will load whatever is in the production section of your app_config.yml. We can’t figure out how to have them start in development mode. If you want to start an agent in development mode you should start that agent independently like so:

```>AGENT_ENV=development RAILS_ENV=development bundle exec ruby script/agent api -priority_class B development
```

Create an ocp superuser to make this issue go away:

```> psql postgres
> CREATE ROLE ocp SUPERUSER;
> ALTER ROLE ocp WITH LOGIN INHERIT CREATEROLE CREATEDB;
```

Also - If starting the agents above gives you an error about permissions for a pids folder you need to create a pids folder as a root folder for your app.  **Do not commit this folder to github**

- [ ] Eventually, get the link to the “OCP Server Admin” Document, since that sounds useful, but possibly not for my current agent work.

### Question:
What is the difference between /daemon/node_agent.rb and /lib/agent/node_agent.rb.  Same question for node_controller.rb.  This duality is referenced in the Dev doc, but not really explained.  I have some level of intuition on what's going on, but I don't think I'm quite catching it.

#### beware that often, only most the agents will be stopped successfully
To see if any agents are still running after your stop call, you can check the admin/queues page.

If it shows a nonzero count in any queue, you'll want to stop them via the console.

Console in, and list all running processes with the path `/script/agent`

`ps aux | grep "script/agent"`

#### OHM message objects stored redis
Many of our messaging objects are stored as hash maps (OHM) in Redis instead of our DB.  An example of a basic query to see all InternalMessage objects in Redis at any moment is `OCP::InternalMessage.all`

To see the list of objects returned by a find call just append .to_a - for example:
```> OCP::InternalMessage.find(parent_uuid: "db45b4f7-f6c7-49f8-b7b7-6621e2daf4c1").to_a
```

### files for mailer stuff Nate was working on
```ocp_base_mailer.rb  
notifier_spec.rb  
notifier.rb  
loggable.rb.  
```


## Fri, 9 Jul 2021

I think that on Monday, I'll intersperse reading up on RabbitMQ agents with finding and reviewing the associated code in /lib/agents

5:05, p35&36/138. Getting into the RabbitMQ Agents.  Remember Maged mentioned agents as being key to the delivery process.  I'll take my time with this section since it looks key to my understanding of what I'll be working on very shortly.  It is also the next **10** pages, so take this in pieces.  I'm reading right away that these agents work on stuff in queues and seem to me at first glance to be like the workers I'd worked on at Sportrocket.  I very much see why Maged is pointing me in this direction.  Ok, done for the day.  

### Question:
- I'm seeing references to "The API" in the sections referring to conversions.  What functionality is currently in "The API".  Looks like conversions are what "The API" handles?  As we add more APIs, we'll want a good name for this one and to change the references in the Dev doc to reflect that new naming convention.

4:45, p33/138.  Getting into constituency stuff now.

### Question:
- Is the District object still enormous because of the `the_geom` column?  I'm guessing so but I want to see if the implementation on this has changed, since it seems awkward, but possible in a way that doesn't have a good workaround.  Though I like the idea of a Districts API with the sole function of returning `the_geom` data when queried.  Possible good workaround as long as it is fast enough.  This is a question/discussion with Maged, I think.  Or a well written question in the Dev slack channel.

2:45, p27/138.  Feels like it is going slowly.  I hope to get another 10-15 pages.  Also want to take some time to go through some code today.  Plenty of time after a good lunch and my mocha at hand.  I'll update in an hour or so to see where I've gotten to.

Met with Maged this morning.  Sounds like my understanding so far of the size of the system, the need to make it smaller and more modern by breaking off pieces into micro services and APIs according to areas of functionality is spot on.  

I took brief and scattered notes in a PM to myself in Slack.  Most of my attention was on the exchange of ideas and information, not on note taking.  I've rewritten the notes here to enhance my understandig for the future, especially since these are the areas in which I am likely to be working in the coming weeks and should be kept in mind as I become familiar with the code and the Dev doc.

Also, I came out of the meeting with Maged feeling very much that my skills and understanding of the existing system and where we need to take our system are spot on.  Feeling very good about my ability to contribute well to the team and the company.

### Meeting with Maged notes

#### biggest pain points
Delivery (of email, fax, webform, cwc, api) and Analytics are the biggest areas of pain and need for the business.  

#### logging in delivery process `/lib/agents`
There are many problems with logging.  These fall into 3 categories.  Logs not where they should be.  The logs are present but contain no return messages.  The logs are there but caontain no useful info, like only id numbers.

Alerts need to be added for when deliveries are failing (especially CWC!).  The agents are what need logging soonest, especially CWC.  The delivery may trace back to the relevent models and controllers, too, but mostly it is the library agents (email, fax, webform, cwc, api) in `/lib/agents`.  Ideally, the logging to be added will follow step by step through the process of delivery.  This should is to address the extreme pain of trying to diagnose delivery failure, which is often not possible currently.  Interestingly, I felt like I was getting distracted by a lot of little things outside of work yesterday, but in hindsight, I realize that with all the documentation reading and bits of research as a result of my readings, those distracted moments were largely my brain stepping back and digesting before diving back in.  So, yesterday was full and more occupied than I realized in the moment.

#### analytics

It was mentioned that CSV files or tables were (or should? be) used for Analytics.

Analytics need to track who was the target and how many messages were delivered.  Additionally, the current tracking of views includes web crawlers and the edits to the page which should be omitted entirely or the views analytics is useless.  Additionally, views should also be tracked by Google Analytics instead of our code.

There is a plan to convert Analytics into its own API over the next couple of weeks.

Example: a signed petition generates email plus CWC.  This creates a delivery for each.  These should start in a Pending state then progress through states until Failed (due to well logged and alerted error) or Succeeded.  

Something about elastic search (nosql) for aggregates.

See PMs for me for the morning of this day to see the original notes.


## Thu, 8 Jul 2021

Hmmmmm.  There does not appear to be a constituency section, though it is mentioned several times in the `More on Recipients` section of `Basic Database Objects`.

p22/138 in Dev doc as of 4pm today.  Trying hard to pay attention to more important and relevant sections while only skimming other sections.  Oh right, I need to look at that list of important sections I received from Nate.

#### Important Dev Doc sections
```
Constituency
Basic Database Objects
RabbitMQ
Delivery Process through RabbitMQ
Reporting Rake Tasks
Third Party #NationBuilder
Conversions
OneClick Widget
```

How to get rails and ruby versions from docker container.
```
  docker-compose exec ocp bundle exec rails --version    
  docker-compose exec ocp bundle exec ruby --version
```

How to get Postgres and PostGis versions from docker container.
```
  docker-compose exec ocp bundle exec psql -V psql  
  docker-compose exec postgres bash -c "psql -U ocp ocp -c 'SELECT PostGIS_full_version();'"
```

https://oneclickpolitics.atlassian.net/browse/ON-1206

Today is dev doc reading, https://docs.google.com/document/d/1mG8TRVEyglQeQfrGsnnYRsxP5zJewE_hxa0IYPnR0bs, as a way to learn about all the various aspects of our system.  Updating anything I see that needs it.  Also, planning about how to break up this monolithic document into working pieces, while keeping the information very accessible, probably using Confluence.


8:30-12:00, 1:30- (aim for 6pm). Actual hours today were in pieces.  I realized later that this was because I was digesting a lot of new material.  I kept reviewing into the evening, interspersed with dinner preparation breaks and a lovely dinner with an early bedtime.  In hindsight, I realized that far from the shorted day I had feared I'd worked, that I actually had worked an extra long day if I factor in the times I was doing food prep or feeding kitties as time I was also thinking about and digesting Dev doc material.  In a normal office, these would have been moments where I went to walk around the block or walk to coffee or something while my mind worked in the background

In a little late today and also had a call with Erich Baumann, my longtime friend out of touch for almost 20 years.  I plan to work a bit late to make sure I cover my hours.


Over time, keep an eye on how much space is available on my drive.  Apparently docker images don't clean up well and start to clutter up a local drive.  Something to watch out for.  Remember that `df` is the command for disk capacity stuff.  And `docker image ls` will show the local repository of docker images.

```
susanprestage@Susans-MBP one-click-politics % df
Filesystem                              512-blocks      Used  Available Capacity iused      ifree %iused  Mounted on
/dev/disk1s1s1                          1953595632  29904632 1650388536     2%  553757 9767424403    0%   /
devfs                                          396       396          0   100%     686          0  100%   /dev
/dev/disk1s5                            1953595632  10485800 1650388536     1%       5 9767978155    0%   /System/Volumes/VM
/dev/disk1s3                            1953595632    558592 1650388536     1%     824 9767977336    0%   /System/Volumes/Preboot
/dev/disk1s6                            1953595632       456 1650388536     1%      17 9767978143    0%   /System/Volumes/Update
/dev/disk1s2                            1953595632 260640704 1650388536    14%  986877 9766991283    0%   /System/Volumes/Data
map auto_home                                    0         0          0   100%       0          0  100%   /System/Volumes/Data/home
/Applications/WhatsApp.app              1953595632  81010232 1840498584     5%  895466 9767082694    0%   /private/var/folders/xs/h3lhzlf13w77vtvw7w31p6_40000gn/T/AppTranslocation/D679049D-D903-4BD5-A553-29CF8675C599
/dev/disk2s1                               2048000    602184    1445816    30%     364 4294966915    0%   /Volumes/Skype
/dev/disk3s1                               3917744   3290904     626840    84%   22624 4294944655    0%   /Volumes/Docker
/Users/susanprestage/Downloads/Atom.app 1953595632 204322424 1710901120    11%  985528 9766992632    0%   /private/var/folders/xs/h3lhzlf13w77vtvw7w31p6_40000gn/T/AppTranslocation/2D2615D8-FCCD-4B9C-9DC5-75C945D17FBA
susanprestage@Susans-MBP one-click-politics % docker image ls
REPOSITORY                                                     TAG            IMAGE ID       CREATED        SIZE
ocp/development                                                latest         4a73aa89ea98   3 hours ago    1.91GB
postgis/postgis                                                9.6-2.5        3681dd4db503   40 hours ago   333MB
rabbitmq                                                       3-management   415614b8c071   7 days ago     252MB
104377796283.dkr.ecr.us-east-1.amazonaws.com/ocp/development   latest         7aa14f9e0627   8 days ago     2.29GB
104377796283.dkr.ecr.us-east-1.amazonaws.com/ocp/development   basic          d8d7e11a5c1b   8 days ago     1.16GB
alpine/git                                                     latest         b8f176fa3f0d   6 weeks ago    25.1MB
redis                                                          3.0.5          c72f1dae54bf   5 years ago    109MB
```


## Wed, 7 Jul, 2021

Received my HR stuff.  Mostly straightforward.  Reading through docs and getting signed up to QuickBooks for W2...which is currently asking what my IL Withholding should be.  Working with John figure that out.  

The new db dump is taking a long time for Nate.  No surprise as yesterday proved to me that this data is large.

Actual hours: 8:15-12, 1:00-5:15

Getting a feel for the codebase.  This project has a staggering schema.rb file.  I think this and probably the routes.rb file as well will be the roadmaps to the overall architecture and how to break pieces off of this monolith bit by bit until there is nothing let but something straightforward to finally migrate to something more modern than `rails 3.2.22.5` and `ruby 2.2.10p489`.  Maged is a strong advocate for this and is keenly aware of the towering tech debt of this monolith.  Nate says Maged was talking about 10-15% of time chipping away at this with the rest dedicated to new (with supporting tests).  

That's another thing.  There are a **lot** of tests in the project.  Also, all in rspec, not a bad thing, just a thing.  Also, Nate comes from a minispec background which makes me happy.  He seems to write clean test code without unnecessary extras.

This is the dev doc.  13.5 screens of sections in the right hand outline.  First 1.5 were quite relevent and good to know.  Slowly review doc in spare moments, mostly skimming, to be aware what is there so I can find answers later as questions come up.  It appears to be a comprehensive explanation covering **EVERY** aspect of this project.  https://docs.google.com/document/d/1mG8TRVEyglQeQfrGsnnYRsxP5zJewE_hxa0IYPnR0bs/edit#

These are the docker instructions.  I've gotten to the **Terminals_and_tasks** section, which is halfway through.  This covers all the installation stuff, how to run docker commands, run the migrations, do database creation/deletion/migration, and run tests all in the docker containers that I did yesterday and today.  https://docs.google.com/document/d/1EM7pIJSCQl4UzwaLWNOG1G1wGbHfOd3UXIRsqqh6ACo/edit?ts=60e4c33b

A lot of time spent:
- doing the new sql db dump (Nate)
- uploading the new sql file to dropbox, **17.8 G** (Nate)
- downloading the sql file from dropbox (Susan)
- populating the db with the new data (Susan)

After all that, I was able to successully migrate.  Or rather, run the migrate command with no errors and no actual migrations since I was using a fresh db dump.

Got my ssh keys set up for staging and prod.

Done with setup.  Spent the remainder of the day pairing on the mailer logging task, ON-1204.


## Tue, 6 Jul, 2021

### First day at OneClickPolitics

- Find out what short version of the company name is used by the folks on the engineering team.

#### Planned hours
```
8-12 morning
12-1 lunch
1-5 afternoon
```

Each of the above times may slip as much as 30 minutes depending on the day, but the above is what I'm aiming for.  I plan to take the full hour for lunch to spend with Kai, to do chores, but mostly to do food prep and planning for both lunch and dinner.

Timing plan is working perfectly.  I'm aiming for 8am each morning, that way if I'm late, I'm still starting by 8:30, which wraps up my day by 5-5:30.  

Installed Docker.  Got Jira account set up.  Very useful doc here on OCP Docker setup, https://docs.google.com/document/d/1EM7pIJSCQl4UzwaLWNOG1G1wGbHfOd3UXIRsqqh6ACo/edit?ts=60e4c33b

Got most set up, but ran into problems with duplicated columns as a result of loading first the no_data sql followed by the with_data sql.  After trying to drop each column, Dave realized it was the big list, not just a few.  We stopped a bit after 5 with the plan for Nate to help me tomorrow to drop the existing database, then take a dump of his db data, then have me load that in.

I was able to successully run a couple rspec tests, so some good progress has been made.

Actual hours: 8:05-12:00, 1:05-5:15
