# OCP daily dev notes
This doc will have unchecked tasks in the past.  These are either obsolete, or have been moved to the current day.  This is a different style from my personal tracking journal which either checks them or moves them to the current day.  The goal in this doc is to preserve my status report for later reference, so that is where the unchecked are likely to be preserved.


```
irb(main):011:0> e = h.keep_if
=> #<Enumerator: {"12643"=>0, "36311"=>0, "38991"=>1, "39521"=>0, "23691"=>0, "39516"=>1, "39529"=>0, "39518"=>0, "39168"=>0, "39169"=>240237, "39171"=>0, "39170"=>0, "39082"=>0, "39282"=>0, "39288"=>7, "29631"=>0, "40468"=>0, "319"=>0, "7320"=>0, "25179"=>1200, "12537"=>0, "12174"=>4, "40476"=>0, "24403"=>0, "39610"=>0, "39523"=>5, "39517"=>18, "39524"=>3, "39520"=>2, "39528"=>60, "39522"=>29, "39519"=>10, "40066"=>1, "40449"=>0, "40326"=>4, "40553"=>0, "40563"=>0, "40581"=>9, "36120"=>0, "40592"=>0, "40601"=>0, "40645"=>0, "40654"=>0, "36896"=>0, "37916"=>0, "37862"=>0, "38023"=>0, "10958"=>0, "35975"=>0, "37990"=>0, "39667"=>0, "39538"=>0, "39387"=>1, "39543"=>0, "39634"=>0, "20176"=>14512, "39674"=>0, "39549"=>0, "39653"=>0, "39556"=>0, "16660"=>0, "39754"=>1, "13607"=>330, "39686"=>289, "39811"=>0, "39557"=>0, "39846"=>0, "39850"=>0, "39703"=>6, "39911"=>0, "7225"=>1, "39967"=>0, "40015"=>0, "40021"=>0, "39960"=>0, "39896"=>0, "40196"=>0, "40190"=>5, "40218"=>0, "40796"=>0}:keep_if>

irb(main):012:0> e.each { |key, value| value != 0 }
=> {"38991"=>1, "39516"=>1, "39169"=>240237, "39288"=>7, "25179"=>1200, "12174"=>4, "39523"=>5, "39517"=>18, "39524"=>3, "39520"=>2, "39528"=>60, "39522"=>29, "39519"=>10, "40066"=>1, "40326"=>4, "40581"=>9, "39387"=>1, "20176"=>14512, "39754"=>1, "13607"=>330, "39686"=>289, "39703"=>6, "7225"=>1, "40190"=>5}

data = {"12643"=>nil, "36311"=>nil, "38991"=>135, "39521"=>nil}
e = data.keep_if
e.each { |key, value| !value.nil? }

foo = h.keep_if.each { |key, value| !value.nil? }
```

logger.info("NationBuilder person_data for advocate: #{data.delete_if { |_, val| val.nil? }}")


## Fri, Feb 4 2022
- [x] ON-1641 - remote Kris Koenen's admin access to the OCP admin portal
- [x] ON-1640 - create Jira and stop sync for NRA, promoter user 39169
- [ ] ON-1639 - CA/AU/US cicero import <- I need to break this into 3 different tickets to track the work, but I used just the one in order to checkin the .csv files and get the onto production.  Canada import is complete.  Working on AU import.
- [ ] With a brief re-review and approval from Shams, ON-1617 Omit all nil fields in person_data sent to NationBuilder is ready for merge and deployment.  https://github.com/one-click-politics/one-click-politics/pull/559
- [ ] ON-1620 to add Senate Dems/Repubs and House Dems/Repubs is in progress
  - [x] implemented at the national level
  - [ ] tests are in progress for national
- [ ] email to confirm with Darren and if so, create a second ticket
  - [ ] implement at the state level
  - [ ] implement tests for state


## Thu, Feb 3 2022
**Question**
- Do we create a Jira for every Zendesk ticket we research, even when there are no code modifications involved?  YES

**Yesterday I**
- finished second half of Hager's big UK PR; let me know when you are ready for re-review (which should be quick)
- wrote up questions and potential solutions for two of the ZD tickets (1155 & 767)
- BLOCKED (need response from Maged) ON-1636: Training video update (ZD-1155)
+ researched and wrote up my findings in response to https://oneclickpolitics.zendesk.com/agent/tickets/1231 aka the lat/lng ticket
- reviewed Alex's PRs, which catches me up on PR review for this brief moment

**Today I plan to**
- [x] ON-1641 - remote Kris Koenen's admin access to the OCP admin portal
- [x] ON-1640 - create Jira and stop sync for NRA, promoter user 39169
- [ ] ON-1639 - US cicero import
- [ ] create Jira for ZD-767: Advocate upload
- [ ] prep file for Advocate upload
- [ ] check in and merge file for Advocate upload
- [ ] perform Advocate upload
- [ ] With a brief re-review and approval from Shams, ON-1617 Omit all nil fields in person_data sent to NationBuilder is ready for merge and deployment.  https://github.com/one-click-politics/one-click-politics/pull/559
- [ ] ON-1620 to add Senate Dems/Repubs and House Dems/Repubs is in progress
  - [x] implemented at the national level
  - [ ] tests are in progress for national
- [ ] email to confirm with Darren and if so, create a second ticket
  - [ ] implement at the state level
  - [ ] implement tests for state


## Wed, Feb 2 2022
**Yesterday I**
- ON-1634 merge and deployed the extended video size for CA Cancer Society
- reviewed a pile of PRs that had accumulated; I'm about halfway through the big UK PR, Hager
- created ON-1636: Training video update <- I've done the legwork and have a couple different solutions along with several questions.  Maged, I've written them up in the ticket, or we can meet since I'd like to share screen or have you looking at production to clarify some of the questions.
- I was looking at ZD 767 for advocate upload and I notice that this ticket is 10 months old.  Is this something still desired to be uploaded?  Promotor ID 40237
- Are we doing Cicero US imports weekly?  What about CA & AU?

**Today I plan to**
- [x] send questions to Maged on 2 of the zendesk tix, 1155-training video update & 767-old advocate upload
- [ ] await response from Maged on ZD-1155, training video update
- [ ] await response from Maged on ZD-767, 10 month old advocate upload
- [x] sort out and make Jira ticket for zendesk tix 1231 (lat/lon)
  - [x] research best answers with recent (today's) data
  - [x] responded to the ticket with answers for the two questions (as best as I could translate them):
    - what data is sent to NB for a "petition signer" (Advocate)
    - can you help confirm this feedback from nationbuilder? Does OCP returns a "Check" value in the "Override latitude and longitude" check box in nationbuilder as a default?
- [ ] respond to reviews and merge, ON-1617 Omit all nil fields in person_data sent to NationBuilder #559 <- at end of day (4:45p), only Hager had reviewed, so I prompted folks.  Should be able to wrap this up tomorrow morning.
- [ ] support ticket from Friday (ON-1620) to add Senate Dems/Repubs and House Dems/Repubs
  - [x] implemented at the national level
  - [ ] tests are in progress for national
  - [ ] implement at the state level
  - [ ] implement tests for state
- [ ] BLOCKED (need response from Maged) ON-1636: Training video update (ZD-1155)
- [ ] BLOCKED (need response from Maged) create Jira for ZD-767: Advocate upload
- [x] finished second half of Hager's big UK PR; let me know when you are ready for re-review (which should be quick)

### zendesk 1231
Posted the following to https://oneclickpolitics.zendesk.com/agent/tickets/1231

The OCP system uses the NationBuilder API to sync data for clients.  There is no field provided in the NB API for "Override latitude and longitude".  There is no checkbox as there is no UI.  See this document from NationBuilder for details on use of their API, https://nationbuilder.com/people_api.

These are the fields that OCP sends to NationBuilder to sync petition signers (Advocates):

email, phone, first_name, last_name, middle_name, address1, address2, city, state, zip, country_code, lat, lng

NationBuilders geocoding/re-districting requires the country_code in the data sent to them.  The recent (Nov 2021) conversation with NB about re-districting implied that lat/lng would not alter data at their end, but was not directly stated nor is covered in their API docs.


## Tue, Feb 1 2022
### New priorities
These new priorities just came in from Maged just after noon:
1. ON-1636 training video zendesk 1155, https://oneclickpolitics.atlassian.net/browse/ON-1636  I have reviewed everything and have a list of implementation questions as well as observations about the video.
2. Lat and long issue zendesk 1231
3. advocate upload zendesk 767.  I notice that this ticket is 10 months old.  Is this something still desired to be uploaded?  Promotor ID 40237
4. house/senate grouping jira 1620

#### NationBuilder person_data for advocate:

We use the NationBuilder API to sync data for clients.  There is no field provided in the NB API for "Override latitude and longitude".  There is no checkbox as there is no UI.  See this document from NationBuilder for details on use of their API, https://nationbuilder.com/people_api.

These are the fields that OCP sends to NationBuilder to sync petition signers (Advocates):

{ email, phone, first_name, last_name, middle_name, external_id, home_address {address1, address2, city, state, zip, country_code, lat, lng} }

**Yesterday I**
- ON-1634 ticketed, implemented, PR'ed the extended video size for CA Cancer Society
- ON-1617 PR has just been put up for review.  This is to use .compact or equiquivalent on the person hash (for any field not required) sent for both Recipients and AdvocateProfiles sent to NB.

**Today I plan to**
- [x] ON-1634 merge and deployed the extended video size for CA Cancer Society
- [ ] review the pile of PRs that have accumulate
- [ ] 1 ticket update links for training materials, Maged will send ticket
- [ ] support ticket from Friday (ON-1620) to add Senate Dems/Repubs and House Dems/Repubs

- [ ] wrap up responses to [#529] ON-1580 Rake task to reset conversions for re-sync to NationBuilder


## Mon, Jan 31 2022
**Wednesday I**
- [x] deploy then perform the Advocate Universe Uploads, ON-1605 <- 1st TOP PRIORITY
- [x] ON-1616:  create a single ticket for:
  - do not send opt in flag at all for recipients <- current sprint <- 2nd TOP PRIORITY
  - do not send prefix at all <- current sprint <- 2nd TOP PRIORITY
- [x] ON-1617:  create a ticket for:
  - use .compact or equiquivalent on the entire hash for any field not required <- backlog
- [x] implement ticket ON-1616:  <- 2nd TOP PRIORITY
  - do not send opt in flag at all for recipients
  - do not send prefix at all
- [x] talk to Alex late this afternoon for info handoff for the eventual generification of the advocate import https://oneclickpolitics.atlassian.net/browse/ON-1306

**Today I plan to**
- [x] deploy master to pre-prod
- [ ] 2 tickets on extending video size, Maged will send tickets
- [ ] 1 ticket update links for training materials, Maged will send ticket
- [ ] do ON-1617 to use .compact or equiquivalent on the entire hash for any field not required
- [ ] review the pile of PRs that have accumulated
- [ ] wrap up responses to [#529] ON-1580 Rake task to reset conversions for re-sync to NationBuilder
- [ ] support ticket from Friday (ON-1620) to add Senate Dems/Repubs and House Dems/Repubs

**Coming very soon**
- [ ] today I hope to finish both house and senate <- 3RD TOP PRIORITY (ON-1527: ON-1530 & 1531)
  - [ ] Priority order needs to be changed to this: cwc, email, web, fax
  - [ ] list those who don't have cwc




## Wed, Jan 26, 2022
**Yesterday I**
- finished the Cicero US import, ON-1608
- checked for the missing VA, WA, and MD data; need more info to know what to check for FL
- ON-1614: Jira ticket to improve importer to filter out rows with territories (PR, AS, 3 others)
- ON-1613: also, I keep seeing one particular AU cicero imported recipient failing to NB sync.  I'm going to write up the bug so you can schedule it in sometime soon, Maged:
{"message":"FAILURE for Promoter 20176 (Australian Christian Lobby): 2022-01-25 14:34:11 +0000 - Conversion 25328631 failed to sync Email because Recipient 121877 failed to sync.","@timestamp":"2022-01-25T14:34:11.132+00:00","@version":"1","severity":"ERROR","host":"ip-172-30-1-220","tags":["nation_builder","task","sync"],"environment":"production"}
- did the prep work for the Advocate Universe Upload, ON-1605 <- 1st TOP PRIORITY
  - figured out the instructions from the Dev Doc,
  - added the promoter file specific method
  - tested it locally

Weirdly.  The Advocate import creates SenderProfiles not Advocates.  Should I be concerned?


**Today I plan to**
- [x] deploy then perform the Advocate Universe Uploads, ON-1605 <- 1st TOP PRIORITY
- [x] ON-1616:  create a single ticket for:
  - do not send opt in flag at all for recipients <- current sprint <- 2nd TOP PRIORITY
  - do not send prefix at all <- current sprint <- 2nd TOP PRIORITY
- [x] ON-1617:  create a ticket for:
  - use .compact or equiquivalent on the entire hash for any field not required <- backlog
- [x] implement ticket ON-1616:  <- 2nd TOP PRIORITY
  - do not send opt in flag at all for recipients
  - do not send prefix at all

- [ ] today I hope to finish both house and senate <- 3RD TOP PRIORITY (ON-1527: ON-1530 & 1531)
  - [ ] Priority order needs to be changed to this: cwc, email, web, fax
  - [ ] list those who don't have cwc
- [ ] wrap up responses to [#529] ON-1580 Rake task to reset conversions for re-sync to NationBuilder
- [ ] talk to Alex late this afternoon for info handoff for the eventual generification of the advocate import https://oneclickpolitics.atlassian.net/browse/ON-1306


## Tue, Jan 25 2022

✅ Is present on 25 Jan - Washington State Senate District 27, Yasmin Trudeau - Entered office November 2, 2021

✅ Is present on 25 Jan - Maryland House of Delegates District 15, Linda Foley - Entered office December 17, 2021

✅ Is present on 25 Jan - Virginia House of Delegates District 89, Jackie Glass - Entered office January 12, 2022

I have no info on the missing Florida representative, so I'd have to ballotpedia and walk through all recently elected representatives at every level.  More information would be much better.  I'm going to assume this is good until I hear more.

**Yesterday I**
- pulled examples of Recipient (person_data) that we are sending to NB and wrote up findings and sent to Maged, ON-1599, short version:
  - Yes, we always send party.  I have examples of both R & D that were sent Monday.
  - Yes, we always send prefix.  Since all congress persons have prefix of nil, then we are sending nil.  
- reviewed a couple of quick PRs
- made a ticket for the Advocate Universe Uploads, ON-1605
- got everything copied down from s3, checked in, and merged for the Cicero US import, ON-1608
- this morning I deployed the cicero US data (and Alex's widget changes)
- and am nearly done running the Cicero US import

**Today I plan to**
- [x] finish the Cicero US import, ON-1608
- [x] check for the missing FL, VA, WA, and MD data
- [ ] today I hope to finish both house and senate <- 2ND TOP PRIORITY (ON-1527: ON-1530 & 1531)
  - [ ] Priority order needs to be changed to this: cwc, email, web, fax
  - [ ] list those who don't have cwc
- [ ] at some point I hope to get back to responding to the reviews on the rake task PR for ON-1580
- [ ] do the Advocate Universe Uploads, ON-1605 <- 1st TOP PRIORITY
- [ ] wrap up [#529] ON-1580 Rake task to reset conversions for re-sync to NationBuilder (sprestage)
- [x] ON-1613: also, I keep seeing one particular AU cicero imported recipient failing to NB sync.  I'm going to write up the bug so you can schedule it in sometime soon, Maged:
{"message":"FAILURE for Promoter 20176 (Australian Christian Lobby): 2022-01-25 14:34:11 +0000 - Conversion 25328631 failed to sync Email because Recipient 121877 failed to sync.","@timestamp":"2022-01-25T14:34:11.132+00:00","@version":"1","severity":"ERROR","host":"ip-172-30-1-220","tags":["nation_builder","task","sync"],"environment":"production"}
- [x] ON-1614: Jira ticket to improve importer to filter out rows with territories (PR, AS, 3 others)
```
the longer term fix will likely use the filter_rows method in cicero_us_recipient_importer.rb
so it will add an extra condition that filters out rows that have a state matching the territories
right now it is just filtering out rows with the wrong level and chamber columns
we’d just be adding another line of logic to exclude states that we don’t cover
hmm i think that’s probably the only thing that would need to change to filter out those states

def self.filter_rows(row, &block)
  if [:state, :comm].include? row['level']
    if ['UPPER','LOWER'].include? row['chamber']
      block[]
    end
  end
end
```

```
RAILS_ENV=production bundle exec rake nation_builder_sync:sync_one[39169] &
```

# today's personal items
- [ ] respond to and pay AIB
- [ ] plan covid booster shots
- [ ] order lotion, butt balm, underwear, FloNase,
- [ ] arrange for local allergy meds
- [ ] pack for the beach!

### NationBuilder backlogged syncs (6pm, Mon, Jan 24)
irb(main):029:0> promoter = PromoterUser.find 20176
=> 9625
irb(main):043:0> promoter = PromoterUser.find 39169
=> 226119

### switchboard API info and links

#### basic generation and dockerization
https://github.com/one-click-politics/one-click-embed-test/commit/ce66cb231c6f2cb250bc934a8b006930c6b06950

#### add search method
https://github.com/one-click-politics/ocp-deliveries-api/commit/6ab86e718db708277d07a0125a243841c298f870

#### example that is the deliveries API
https://github.com/one-click-politics/ocp-deliveries-api/commits/master?after=70610f6039e25b49b06f627ad4b985929e43bdd1+34&branch=master

#### basic flow diagram from Maged
switchboard-API.jpg (in my Downloads folder)


##### set up to NB sync method calls on conversions and promoters
```
@epoch = '2019-06-18T23:19'
@epoch_id ||= Conversion.where("created_at > ?", @epoch).first.try(:id) || 1
@apocalypse = '3000-12-31T23:19'
@apocalypse_id ||= Conversion.where("created_at > ?", @apocalypse).first.try(:id) || Conversion.last.try(:id) || 1000000000

Dir[Rails.root.join("lib/nation_builder_client/**/*.rb")].each {|f| require f}
Dir[Rails.root.join("lib/jobs/nation_builder_sync/**/*.rb")].each {|f| require f}
```

### NB sync data
There are a total of 80 promoters that are syncable:
```
NationBuilderSync.syncable_promoters.count
=> 80
```

##### who are the NB sync promoters
```
promoter_ids = []
NationBuilderSync.syncable_promoters.each do |promoter|
  promoter_ids.append promoter.id
end
irb(main):029:0> promoter_ids
=> [12643, 36311, 38991, 39521, 23691, 39516, 39529, 39518, 39168, 39169, 39171, 39170, 39082, 39282, 39288, 29631, 40468, 319, 7320, 25179, 12537, 12174, 40476, 24403, 39610, 39523, 39517, 39524, 39520, 39528, 39522, 39519, 40066, 40449, 40326, 40553, 40563, 40581, 36120, 40592, 40601, 40645, 40654, 36896, 37916, 37862, 38023, 10958, 35975, 37990, 39667, 39538, 39387, 39543, 39634, 20176, 39674, 39549, 39653, 39556, 16660, 39754, 13607, 39686, 39811, 39557, 39846, 39850, 39703, 39911, 7225, 39967, 40015, 40021, 39960, 39896, 40196, 40190, 40218, 40796]
```

##### how many conversions for all NB sync promoters
```
promoters_conversion_count_hash = {}
conversion_count = 0
temp_count = 0
NationBuilderSync.syncable_promoters.each do |promoter|
  temp_count = promoter.conversions.includes(advocate_profile: [:advocate_for_promoters, :state, :external_connections]).where('conversions.id >= ?', @epoch_id).where('conversions.id <= ?', @apocalypse_id).where('conversions.nation_builder_email_synced = ?', false).where('conversions.nation_builder_unsyncable = ?', false).where('conversions.reached_recipient_ids IS NOT NULL').where('advocate_for_promoters.opt_in_id IS NOT NULL').count
  conversion_count += temp_count
  promoters_conversion_count_hash["#{promoter.id}"] = temp_count
  temp_count = 0
end

irb(main):110:0* conversion_count
=> 256736
irb(main):111:0> promoters_conversion_count_hash
=> {"12643"=>0, "36311"=>0, "38991"=>1, "39521"=>0, "23691"=>0, "39516"=>1, "39529"=>0, "39518"=>0, "39168"=>0, "39169"=>240237, "39171"=>0, "39170"=>0, "39082"=>0, "39282"=>0, "39288"=>7, "29631"=>0, "40468"=>0, "319"=>0, "7320"=>0, "25179"=>1200, "12537"=>0, "12174"=>4, "40476"=>0, "24403"=>0, "39610"=>0, "39523"=>5, "39517"=>18, "39524"=>3, "39520"=>2, "39528"=>60, "39522"=>29, "39519"=>10, "40066"=>1, "40449"=>0, "40326"=>4, "40553"=>0, "40563"=>0, "40581"=>9, "36120"=>0, "40592"=>0, "40601"=>0, "40645"=>0, "40654"=>0, "36896"=>0, "37916"=>0, "37862"=>0, "38023"=>0, "10958"=>0, "35975"=>0, "37990"=>0, "39667"=>0, "39538"=>0, "39387"=>1, "39543"=>0, "39634"=>0, "20176"=>14512, "39674"=>0, "39549"=>0, "39653"=>0, "39556"=>0, "16660"=>0, "39754"=>1, "13607"=>330, "39686"=>289, "39811"=>0, "39557"=>0, "39846"=>0, "39850"=>0, "39703"=>6, "39911"=>0, "7225"=>1, "39967"=>0, "40015"=>0, "40021"=>0, "39960"=>0, "39896"=>0, "40196"=>0, "40190"=>5, "40218"=>0, "40796"=>0}
```

##### how many conversions for single NB sync promoter
```
promoter = PromoterUser.find 39169
promoter = PromoterUser.find 20176

promoter.conversions.includes(advocate_profile: [:advocate_for_promoters, :state, :external_connections]).where('conversions.id >= ?', @epoch_id).where('conversions.id <= ?', @apocalypse_id).where('conversions.nation_builder_email_synced = ?', false).where('conversions.nation_builder_unsyncable = ?', false).where('conversions.reached_recipient_ids IS NOT NULL').where('advocate_for_promoters.opt_in_id IS NOT NULL').count
```

### NB sync current count
```
irb(main):022:0> promoters_conversion_count_hash
=> {"12643"=>0, "36311"=>0, "38991"=>1, "39521"=>0, "23691"=>0, "39516"=>0, "39529"=>0, "39518"=>0, "39168"=>0, "39170"=>0, "39171"=>0, "39169"=>226119, "39082"=>0, "39282"=>0, "39288"=>0, "29631"=>0, "40468"=>0, "319"=>0, "7320"=>0, "25179"=>0, "12537"=>0, "12174"=>3, "40476"=>0, "24403"=>0, "39610"=>0, "39523"=>5, "39517"=>0, "39524"=>0, "39520"=>0, "39528"=>0, "39522"=>1, "39519"=>0, "40066"=>0, "40449"=>0, "40326"=>0, "40553"=>0, "40563"=>0, "40581"=>0, "36120"=>0, "40592"=>0, "40601"=>0, "40645"=>0, "40654"=>0, "36896"=>0, "37916"=>0, "37862"=>0, "38023"=>0, "10958"=>0, "35975"=>0, "37990"=>0, "39667"=>0, "39538"=>0, "39387"=>0, "39543"=>0, "39634"=>0, "20176"=>7610, "39674"=>0, "39549"=>0, "39653"=>0, "39556"=>0, "16660"=>0, "39754"=>0, "13607"=>0, "39686"=>249, "39811"=>0, "39557"=>0, "39846"=>0, "39850"=>0, "39703"=>0, "39911"=>0, "7225"=>0, "39967"=>0, "40015"=>0, "40021"=>0, "39960"=>0, "39896"=>0, "40196"=>0, "40190"=>0, "40218"=>0, "40796"=>0}
```


## Mon, Jan 24 2022

### NationBuilder parties, prefixes, and defaults
These results are US specific as I believe I am seeing different behavior for parties and prefixes for Australia.

#### Parties
Looking at Recipients being synced today, I have a Republican and a Democrat.  The data sent to NationBuilder includes the :party field and is populated by "R" or "D", as appropriate.

#### Prefix
Looking at all current active members of US Congress (Recipient.office_all_us_congress.active), none have a prefix set.  Thus, all are sending nil for this field.

#### Defaults
Using the NB API explorer webpage, which is a way to access their API through a basic user interface.  I created a new user with only an email, first_name, and last_name.  These were the defaults set by NB when the following fields were left empty:
        “email_opt_in”: true,
        “party”: null,
        “prefix”: null,


### Possible BUG
- figuring out why this recipient sync is failing Recipient id: 121877, name: "O'Sullivan, Matt"


### NationBuilder recipient examples
Data sent for a Republican US Recipient in a sync today:
```
{"message":"NationBuilder person_data for recipient: {:prefix=>nil, :first_name=>\"James\", :last_name=>\"Lankford\", :middle_name=>nil, :phone=>\"(405) 231-4941\", :party=>\"R\", :work_address=>{:address1=>\"1015 N. Broadway Avenue\", :address2=>nil, :city=>\"Oklahoma City\", :state=>\"OK\", :zip=>\"73102\"}, :email_opt_in=>true}","@timestamp":"2022-01-24T17:03:07.692+00:00","@version":"1","severity":"INFO","host":"ip-172-30-1-220","tags":["nation_builder","task","sync"],"environment":"production"}

=> #<Senator id: 20816, name: "Lankford, James", model_type: "Senator", description: nil, lock_version: 11, created_at: "2013-05-31 01:03:31", updated_at: "2022-01-17 19:24:28", grouping_name: nil, can_receive_flg: true, first_name: "James", last_name: "Lankford", middle_name: nil, prefix: nil, suffix: nil, gender: nil, party_id: 2, state: "OK", constituency: "L", active_flg: true, external_id: nil, site_url: nil, order_num: 0, account_id: nil, office_id: 466, votesmart_id: 124938, title: "US Senator", district_id: nil, parent_votesmart_id: 0, display_rules: nil, country: nil, custom_salutation: "Senator", custom_position: nil, bioguide_id: "L000575", knowwho_code: "22259_284972", photo_path: "Images\\Photos\\FL\\SLankford_James_284972.jpg", inactive_at: nil, knowwho_comid: nil, fec_id: nil, use_web_form_api: false, cicero_code: "81952", full_photo_url: "https://lankford.senate.gov/imo/media/image/Senator...", scwc_office_code: nil, cicero_official_id: "355970", cicero_committee_id: nil>

```

Data sent for a Democrat US Recipient in a sync today:
```
{"message":"NationBuilder person_data for recipient: {:prefix=>nil, :first_name=>\"Priscilla\", :last_name=>\"Dunn\", :middle_name=>nil, :email=>\"priscilla.dunn@alsenate.gov\", :email1=>\"priscilla.dunn@alsenate.gov\", :phone=>\"(205) 426-3795\", :party=>\"D\", :work_address=>{:address1=>\"460 Carriage Hills Drive\", :address2=>nil, :city=>\"Bessemer\", :state=>\"AL\", :zip=>\"35022\"}, :email_opt_in=>true}","@timestamp":"2022-01-24T17:03:11.146+00:00","@version":"1","severity":"INFO","host":"ip-172-30-1-220","tags":["nation_builder","task","sync"],"environment":"production"}

=> #<Recipient id: 61137, name: "Dunn, Priscilla", model_type: nil, description: nil, lock_version: 5, created_at: "2015-03-12 05:42:55", updated_at: "2021-12-20 19:09:45", grouping_name: nil, can_receive_flg: true, first_name: "Priscilla", last_name: "Dunn", middle_name: nil, prefix: nil, suffix: nil, gender: nil, party_id: 1, state: "AL", constituency: "L", active_flg: true, external_id: nil, site_url: nil, order_num: 0, account_id: nil, office_id: 173, votesmart_id: nil, title: "Alabama Senator", district_id: 2131, parent_votesmart_id: 0, display_rules: nil, country: nil, custom_salutation: "Senator", custom_position: nil, bioguide_id: "ALL000011", knowwho_code: "26785_192681", photo_path: "Images\\Photos\\SL\\AL\\SDunn_Priscilla_192681.jpg", inactive_at: nil, knowwho_comid: nil, fec_id: nil, use_web_form_api: false, cicero_code: "6476", full_photo_url: "http://www.legislature.state.al.us/ALISWWW/Senate/S...", scwc_office_code: nil, cicero_official_id: "326540", cicero_committee_id: nil>

```

Data sent for an AU Recipient in a sync today:
```
{"message":"NationBuilder person_data for recipient: {:prefix=>\"\", :first_name=>\"Slade\", :last_name=>\"Brockman\", :middle_name=>\"\", :email=>\"senator.brockman@aph.gov.au\", :email1=>\"senator.brockman@aph.gov.au\", :phone=>\"(02) 6277 3764\", :party=>nil, :work_address=>{:address1=>\"Unit 4, 1 Harper Terrace\", :address2=>\"817 Beeliar Drive\", :city=>\"South Perth\", :state=>\"WA\", :zip=>\"6151\"}, :email_opt_in=>true}","@timestamp":"2022-01-24T17:17:23.233+00:00","@version":"1","severity":"INFO","host":"ip-172-30-1-220","tags":["nation_builder","task","sync"],"environment":"production"}

=> #<Recipient id: 22282, name: "Brockman, Slade", model_type: nil, description: "", lock_version: 7, created_at: "2014-05-15 01:25:57", updated_at: "2020-03-02 17:34:17", grouping_name: "", can_receive_flg: true, first_name: "Slade", last_name: "Brockman", middle_name: "", prefix: "", suffix: "", gender: "", party_id: 112, state: "AU-WA", constituency: "L", active_flg: true, external_id: nil, site_url: "", order_num: 0, account_id: nil, office_id: 492, votesmart_id: nil, title: nil, district_id: nil, parent_votesmart_id: 0, display_rules: nil, country: "Australia", custom_salutation: "Senator", custom_position: nil, bioguide_id: nil, knowwho_code: nil, photo_path: nil, inactive_at: nil, knowwho_comid: nil, fec_id: nil, use_web_form_api: false, cicero_code: "184064", full_photo_url: "https://www.aph.gov.au/api/parliamentarian/30484/im...", scwc_office_code: nil, cicero_official_id: nil, cicero_committee_id: nil>
```

```
conversion_count
=> 236593
```

### NB sync data, 12:19pm
```
=> {
  "12643"=>0, "36311"=>0, "38991"=>1, "39521"=>0, "23691"=>0, "39516"=>0, "39529"=>0, "39518"=>0, "39168"=>0, "39170"=>0, "39171"=>0, "39082"=>0, "39169"=>226119, "39282"=>0, "39288"=>0, "29631"=>0, "40468"=>0, "319"=>0, "7320"=>0, "25179"=>4, "12537"=>0, "12174"=>4, "40476"=>0, "24403"=>0, "39610"=>1, "39523"=>0, "39517"=>0, "39524"=>0, "39520"=>0, "39528"=>0, "39522"=>0, "39519"=>0, "40066"=>0, "40449"=>0, "40326"=>0, "40553"=>0, "40563"=>0, "40581"=>0, "36120"=>0, "40592"=>0, "40601"=>0, "40645"=>0, "40654"=>0, "36896"=>0, "37916"=>0, "37862"=>0, "38023"=>0, "10958"=>0, "35975"=>0, "37990"=>0, "39667"=>0, "39538"=>0, "39387"=>0, "39543"=>0, "39634"=>0, "20176"=>10175, "39674"=>0, "39549"=>0, "39653"=>0, "39556"=>0, "16660"=>0, "39754"=>0, "13607"=>0, "39686"=>289, "39811"=>0, "39557"=>0, "39846"=>0, "39850"=>0, "39703"=>0, "39911"=>0, "7225"=>0, "39967"=>0, "40015"=>0, "40021"=>0, "39960"=>0, "39896"=>0, "40196"=>0, "40190"=>0, "40218"=>0, "40796"=>0}
```


**Friday I**
- wrapped up the phone required bug ON-1584
- reviewed Nate's big PR 495, ON-1487
- late in the day started looking into the prefix bug (NB sync), ON-1599

**Today I plan to**

PRIORITIZE
- [ ] import Cicero data for US
- [ ] what do we send for party

- [x] review Hager's PR right away
- [x] continue looking into the prefix bug (NB sync), ON-1599  <- all data sent to Maged.  It is unclear what the next steps will be.  Wait for him to decide and update me tomorrow morning.
- [x] make a ticket for the Advocate Universe Uploads, ON-1605
- [ ] today I hope to finish both house and senate <- 2ND TOP PRIORITY (ON-1527: ON-1530 & 1531)
  - [ ] Priority order needs to be changed to this: cwc, email, web, fax
  - [ ] list those who don't have cwc
- [ ] at some point I hope to get back to responding to the reviews on the rake task PR for ON-1580
- [ ] do the Advocate Universe Uploads, ON-1605


# today's personal items
- [ ] respond to and pay AIB
- [ ] plan covid booster shots
- [ ] order lotion, butt balm, underwear, FloNase,
- [ ] arrange for local allergy meds


## Fri, Jan 21 2022
### learning - logger, logging, log
Put this at the top of the file and use `logger.info("")` from here on out.  👍
```
require "#{AGENT_ROOT}/lib/loggable" unless defined? REQUIRE_LOGGABLE
```

### another learning
```
module OneClickWidgetApiHelper
  RSpec.shared_context 'with widget setup data' do
```

### ADD THIS:
  Maged Makled  12:07 PM
  forwarded you an issue to work on after you finish the current issues

  just needed to get it done by next Wednesday

  I think it is just a script to run

  Susan Prestage  12:08 PM
  Sounds good.  I’ll add it to the queue and get a Jira written up for it.

**Yesterday I**
- Discovered that the pre-prod aka NB box didn't get the Neon and NB sync crons implemented in the new box; fortunately, I had a copy of what had been there just before the increase in NB sync frequency and was able to reconstruct the crons for this box.  (no ticket here; should there be one for the ongoing NB sync monitoring?)
- Got the phone required fix checked in with a PR.  Resolved my rspec test issues.  This morning I'll make a couple more small changes from PR reviews then get it merged in and deployed by lunchtime. ON-1584
- Checked our data for MD & VA on the prod rails console as well as that received from Cicero.  Found two state delegates missing.  One from each state.  Wrote up findings in ticket, email, and discussion with Maged.  ON-1581
- Wrote up the prefix bug.  ON-1599
- Reviewed Shams' 3 PRs.
- Hand tested phone fix on staging (since I was seeing an odd difference between local and prod for this bug).
- [x] merge to `staging` branch for deployment of the phone fix to staging, ON-1584, for by hand testing since I saw a difference in behavior locally vs prod
- [x] thoroughly test US national phone required fix on staging, ON-1584; I saw a difference in behavior locally vs prod before I made changes
  + us house, us senate, us H committee, us S committee, us group
  + us state house, us state senate, us state H committee, us state S committee, us state group
  + non-us house, non-us senate, non-us H committee, non-us S committee, non-us group
- [x] finish the data assessment for Dave's US import work; I'm on the 2nd ticket of info for this (75% complete?)
  - [x] ON-1581
  - [x] ON-1407

**Today I plan to**
- [x] make a couple more small changes from PR reviews on the phone required fix then get it merged in and deployed by lunchtime. ON-1584
- [ ] look into the prefix bug (NB sync), ON-1599
- [x] need to finish responding to feedback on ON-1584 (non-national phone bug), https://github.com/one-click-politics/one-click-politics/pull/535
- [ ] today I hope to finish both house and senate <- 2ND TOP PRIORITY (ON-1527: ON-1530 & 1531)
  - [ ] Priority order needs to be changed to this: cwc, email, web, fax
  - [ ] list those who don't have cwc
- [ ] at some point I hope to get back to responding to the reviews on the rake task PR for ON-1580
- [x] review Nate's PR 495, ON-1487.  Wow.  Big.  21 files.  My eyes are crossing.


## Thu, Jan 20 2022
### learning
work on learning associations and includes when making calls to the DB.  This is probably like, when you need a message's recipients' data, etc.  <- Shams recommended this in stand up and he is correct.

I found this example in a PR
```
    promoter_user = PromoterUser.find_by_id(params[:promoter_id])
    promoted_message = PromotedMessage.where(id: params[:promoted_message_id], creator_id: params[:promoter_id]).last

TURNED INTO (perhaps not all of which is needed):

    promoted_message = PromotedMessage.includes(:promoter).where(
      id: params[:promoted_message_id],
      creator_id: params[:promoter_id]
    ).last
    promoter_user = promoted_message.try(:promoter)
```

**Yesterday I**
- finished the work on the phone required fix.  it is well tested in UI, less well tested with rspec
- results from VA and MD data assessment.  Looks good at the national level.  I see a single House Delegate missing for each.  <- 2nd PRIORITY
```
MD missing:
Maryland House of Delegates District 15	Linda Foley	Democratic	December 17, 2021  <- confirmed this is missing in prod DB
```
oddly MD present:
Maryland House of Delegates District 25	Karen Toles	Democratic	January 12, 2022  <- I would think that if this was current, so would MS Foley above from December
```
VA missing:
Virginia House of Delegates District 89	Jackie Glass	Democratic	January 12, 2022  <- confirmed this is missing in prod DB
```
It is interesting to note that there are Many new delagates from Jan 12, 2022 in VA.  But only the one above is missing.

- [x] need to check in the phone required fix, ON-1584  <- 1st PRIORITY
- [x] MD & VA; check our data on the prod rails console, ON-1581  <- 2nd PRIORITY
- [x] MD & VA; check the data received from Cicero  <- 2nd PRIORITY
- [x] prefix bug needs to be written up <- 3rd PRIORITY, ON-1599
- [x] PR review Shams' 3 PRs
- [x] merge to `staging` branch for deployment of the phone fix to staging, ON-1584, for by hand testing since I saw a difference in behavior locally vs prod
- [x] thoroughly test US national phone required fix on staging, ON-1584; I saw a difference in behavior locally vs prod before I made changes
  + us house, us senate, us H committee, us S committee, us group
  + us state house, us state senate, us state H committee, us state S committee, us state group
  + non-us house, non-us senate, non-us H committee, non-us S committee, non-us group
- [x] finish the data assessment for Dave's US import work; I'm on the 2nd ticket of info for this (75% complete?)
  - [x] ON-1581
  - [x] ON-1407
- [ ] look into the prefix bug (NB sync), ON-1599
- [ ] need to finish responding to feedback on ON-1584 (non-national phone bug), https://github.com/one-click-politics/one-click-politics/pull/535
- [ ] at some point I hope to get back to responding to the reviews on the rake task PR for ON-1580

### problem coming from business through Maged that is still in the rumor and support needs to research stage
- FL state level committee or sub-committee


## Wed, Jan 19 2022
**Yesterday I**
- Made the ticket for the non-national Recipients, ON-1584
- Merged and deployed Dave's PR for Cicero US import, ON-1581
- Ran the US import successfully, ON-1581
- worked on the non-national Recipients bug <- 1ST TOP PRIORITY, ON-1584

Virginia State House is the problematic area for ON-1581

**Today I plan to**
- [ ] wrap up the non-national Recipients bug <- 1ST TOP PRIORITY, ON-1584
- [ ] do the data check portion of the US import ticket, ON-1581 <- 2ND
  - [ ] in addition to VA congress, can you also confirm MD congress
- [ ] NB prefix ?bug? <- 3RD
- [ ] today I hope to finish both house and senate <- 2ND TOP PRIORITY (ON-1527: ON-1530 & 1531)
  - [ ] Priority order needs to be changed to this: cwc, email, web, fax
  - [ ] list those who don't have cwc
- [ ] at some point I hope to get back to responding to the reviews on the rake task PR for ON-1580


## Tue, Jan 18 2022
**Yesterday I**
- create a ticket, checked in & PR'ed the rake task
- finally got back to the recipient delivery address epic; starting with the house <- TOP PRIORITY (ON-1527 & ON-1530)
- Alex found a bug on non-national recipients

two tickets for each:
 - research and action

**Today I plan to**
- [ ] make ticket for the CustomRecipients; then get this fixed <- 1ST TOP PRIORITY, ON-1584
- [ ] today I hope to finish both house and senate <- 2ND TOP PRIORITY (ON-1527: ON-1530 & 1531)
  - [ ] Priority order needs to be changed to this: cwc, email, web, fax
  - [ ] list those who don't have cwc
- [ ] revise as requested and merge the rake task ON-1580
- [ ] Dave: review his PR; then do another cicero import for US <- 3RD TOP PRIORITY, ON-1581

## Mon, Jan 17 2022
not email = video, twitter, _facebook_, phone, _photo_
email = CWC, webform, email, fax, webmail, web address,


**Friday I**
- met with Maged on opt_in a couple times around his meeting with the business
- made sure there is a Jira ticket for the opt_in research, ON-1567
- changed email_opt_in to `true` for all Recipients; Maged confirmed this with Chazz, ON-1578.  Also, strangely, this ticket should be part of the sprint but isn't.  Automation moved it through to done before it entered the sprint so it isn't showing up in my done column 🙃
- merge and deployed the email_opt_in change, ON-1578
- confirmed the phone toggle ticket exists, added it to the epic, & added it to the sprint, ON-1574
- re-ran the MD sync so the Recipients get their email_opt_in changed to true; discovered that re-running doesn't, of course, do anything since there is nothing new.  So I wrote a rake task to change `conversions.nation_builder_email_synced` to false for MD Catholic, 40449, to make that change.  There are roughly 100 conversions this affects.
- create and run a rake task that resets NB syncing for all MD Catholics Conversions; there are less than 100; I see why now as these are all custom recipients.  Only a matter of changing `conversions.nation_builder_email_synced` to false
- re-run the sync after the rake task is run and verify that `email_opt_in` is now `true` for all the recipients

**Today I plan to**
- [x] create a ticket for the rake task
- [x] check in & PR the rake task
- [ ] revise as requested and merge the rake task
- [ ] get back to the recipient delivery address epic <- TOP PRIORITY (ON-1527 & ON-1530)


## Fri, Jan 14 2022
This is concerning.  This should be part of the sprint, https://oneclickpolitics.atlassian.net/browse/ON-1578, but the automation moved it through to done before it entered the sprint so it isn't showing up in my done column 🙃

**Yesterday I**
- Assisted with the NationBuilder box issues, which conveniently tied into gathering data for the opt_in issue for MD Catholic.
- Spent the day on opt_in diagnosis for MD Catholic and NationBuilder.  ON-1567 for this research.

Maged, we should meet so I can bring you up to date on my findings on how opt_in is handled.  As well as discuss the request that is being made by MD Catholic.  I want to confirm what the business and client are asking for.

**Today I plan to**
- [x] Answer any questions on opt_in.
- [x] make sure there is a Jira ticket for the opt_in research, ON-1567
- [x] change email_opt_in to `true` for all Recipients; Maged confirmed this with Chazz, ON-1578
- [x] PR, merge, deploy ON-1578
- [x] find the toggle ticket; add it to the epic; add it to the sprint <- forgot to do this yesterday; nope, I'm wrong.  I did this yesterday here, ON-1574
- [x] re-run the MD sync so the Recipients get their email_opt_in changed to true; hmmm, re-running doesn't, of course, do anything since there is nothing new.  I'm thinking about what would be needed to truly re-run the sync on those conversions.  What makes a conversion synced is this `conversions.nation_builder_email_synced` needs to be false for a conversion to sync.  I could write a very small rake task that pulled all recent (last xxx days) conversions for MD Catholic, 40449, and change the `nation_builder_email_synced` field on those conversions to `false`.
- [x] create and run a rake task that resets NB syncing for all MD Catholics Conversions; there are less than 100; I see why now as these are all custom recipients
- [x] re-run the sync after the rake task is run and verify that `email_opt_in` is now `true` for all the recipients
- [ ] get back to the recipient delivery address epic <- TOP PRIORITY (ON-1527 & ON-1530)

```
desc "Reset NationBuilder campaigns so next sync will pick them up"
task :s_for_nb_resync do
  messages = PromotedMessage.where(creator_id: 40449)
  messages.each do |message|
    conversion_count = 0
    conversions = Conversion.where(promoted_message_id: message.id)
    conversions.each do |conversion|
      conversion_count += 1
      puts "Promoter 40449, PromotedMessage #{conversion.promoted_message_id}, Conversion ##{conversion_count} id:#{conversion.id}, email synced #{conversion.nation_builder_email_synced}, tag synced #{conversion.nation_builder_tag_synced}"
      #conversion.update_attribute(:nation_builder_email_synced, false)
      #conversion.update_attribute(:nation_builder_tag_synced, false)
    end
  end
end

PromotedMessage.where(creator_id: 40449).pluck(:id)
=> [13663, 14706, 14277, 14372, 13512, 14747]

```

### NationBuilder opt_in
Maged: should the NB opt_in research be its own ticket separate from the ticket for whatever change we decide to make?

#### NationBuilder's email_opt_in details:

We only send the `email_opt_in` field when we sync Recipients in order to set it to `false`.  

When we sync Advocates, we NEVER send this field.  However, the NB API defaults this field to `true` when it is not sent.  So, every advocate sync we make will omit this field causing it to be set by the NB API to `"email_opt_in": true`.

Here is an exact AdvocateProfile update made today:
```
{:email=>"modrell211@charter.net", :phone=>"6032064331", :prefix=>nil, :first_name=>"Carol", :last_name=>"Modrell", :middle_name=>nil, :external_id=>6806789, :home_address=>{:address1=>"211 Kearsarge Dr,", :address2=>nil, :city=>"Woodsville", :state=>"NH", :zip=>"03785", :country_code=>"US", :lat=>44.116254, :lng=>-71.958218}}
```

I do not have an example of a new AdvocateProfile being synced.  However, I just signed this campaign, https://oneclickpolitics.com/promoter/25179/messages/13484/edit#.  I hope to sync tonight and have data by morning.  🤞  The NB API page is already loaded to search for my name on this promoter.  <- update Fri 10:30am, 3 syncs later and this still hasn't synced.  Helps me understand the frustrations of the clients of the delays in analytics data.  😂

Re-reading the ticket, it really does look like MD Catholic wants RECIPIENTS to be set to `"email_opt_in": true`.  

Here is the text of the most recent update from MD Catholic:
The issue that Maryland Catholic is experiencing is that target profiles are being opted out of email in NationBuilder when an OCP interaction is logged via the integration. I'm assuming that this could be the intended functionality, as most OCP customers would only want to include advocates (rather than both advocates and targets), in their email blasts. However, MD Catholic wants the targets to be opted in to emails in their database as well. Is there a way that we can customize the integration for this customer to allow for this?


```
user = 28
PromoterUser.find(user).master_account.authentications
PromoterUser.where(agency_id: user)
NationBuilderSynchronizeCall.where(promoter_user_id: user).where("created_at > ?", 7.days.ago)

slug: oneclickpolitics, token: 1467df86991cc7567d23d6555880b1afedccacdd7bb2fe9f326325bf12203c52
=> [#<Authentication id: 435, account_id: 4367, provider: "nation_builder", uid: "oneclickpolitics", created_at: "2013-09-13 01:54:26", updated_at: "2017-04-23 18:47:18", active: nil, token: "1467df86991cc7567d23d6555880b1afedccacdd7bb2fe9f326...", expires_at: nil, refresh_token: nil, write_access: true, instance_url: nil, extra: nil>]

```


## Thu, Jan 13 2022
```
message":"NationBuilder person_data for advocate: {:email=>\"dantella@zoominternet.net\", :phone=>nil, :prefix=>nil, :first_name=>\"ROBERT\", :last_name=>\"P DANTELLA\", :middle_name=>nil, :external_id=>3826749, :home_address=>{:address1=>\"138 WOODBINE DR\", :address2=>nil, :city=>\"CRANBERRY TWP\", :state=>\"PA\", :zip=>\"16066\", :country_code=>\"US\", :lat=>40.716663, :lng=>-80.148722}}","@timestamp":"2022-01-13T21:33:45.025+00:00","@version":"1","severity":"INFO","host":"ip-172-30-1-201","tags":["nation_builder","task","sync"],"environment":"production"}
```

```
message":"NationBuilder person_data for advocate: {:email=>\"sprigg98@gmail.com\", :phone=>\"2172640103\", :prefix=>nil, :first_name=>\"Caleb\", :last_name=>\"Sprigg\", :middle_name=>nil, :external_id=>8000451, :home_address=>{:address1=>\"18715 Cc Hwy\", :address2=>nil, :city=>\"Blackwater\", :state=>\"MO\", :zip=>\"65323\", :country_code=>\"US\", :lat=>38.454863, :lng=>-93.608588}}","@timestamp":"2022-01-13T20:42:24.814+00:00","@version":"1","severity":"INFO","host":"ip-172-30-1-201","tags":["nation_builder","task","sync"],"environment":"production"}
{"
```

Damn.  This is only showing recipients so far.  Changing the logging so it will only show advocates.

Next interesting question.  Why does the process listing show THREE separate instances of the rake running!?!
```
ubuntu@ip-172-30-1-201:/home/deploy/apps/ocp/current$ ps -ef | grep sync
systemd+   628     1  0 17:23 ?        00:00:00 /lib/systemd/systemd-timesyncd
ubuntu   14379   711  0 20:14 pts/3    00:00:00 grep --color=auto sync
ubuntu   24060 24059  0 19:00 ?        00:00:00 /bin/sh -c /bin/bash -l -c 'export PATH="$HOME/../rubyists/.rbenv/shims:$HOME/../rubyists/.rbenv/bin:$PATH"; cd /home/deploy/apps/ocp/current && NEW_RELIC_AGENT_ENABLED=true RAILS_ENV=production bundle exec rake nation_builder_sync:sync_all['39082','2019-06-18T23:19'] --silent'
ubuntu   24061 24060  0 19:00 ?        00:00:00 /bin/bash -l -c export PATH="$HOME/../rubyists/.rbenv/shims:$HOME/../rubyists/.rbenv/bin:$PATH"; cd /home/deploy/apps/ocp/current && NEW_RELIC_AGENT_ENABLED=true RAILS_ENV=production bundle exec rake nation_builder_sync:sync_all[39082,2019-06-18T23:19] --silent
ubuntu   24066 24061 26 19:00 ?        00:19:42 /home/deploy/apps/ocp/shared/bundle/ruby/2.2.0/bin/rake nation_builder_sync:sync_all[39082,2019-06-18T23:19] --silent
ubuntu@ip-172-30-1-201:/home/deploy/apps/ocp/current$
```
When I run this rake at the command line, I only see a single instance.  Could this be contributing to the Too many open files issue?
```
ubuntu@ip-172-30-1-201:/home/deploy/apps/ocp/current$ ps -ef | grep sync
systemd+   628     1  0 17:23 ?        00:00:00 /lib/systemd/systemd-timesyncd
ubuntu   14530   711 18 20:16 pts/3    00:00:42 /home/deploy/apps/ocp/shared/bundle/ruby/2.2.0/bin/rake nation_builder_sync:sync_all[39082,2019-06-18T23:19]
ubuntu   15723   711  0 20:20 pts/3    00:00:00 grep --color=auto sync
```

Here is an AdvocateProfile we send to NB, with the exact person_data hash being sent:
```
{"message":"NationBuilder person_data for advocate:

{:email=>"modrell211@charter.net", :phone=>"6032064331", :prefix=>nil, :first_name=>"Carol", :last_name=>"Modrell", :middle_name=>nil, :external_id=>6806789, :home_address=>{:address1=>"211 Kearsarge Dr,", :address2=>nil, :city=>"Woodsville", :state=>"NH", :zip=>"03785", :country_code=>"US", :lat=>44.116254, :lng=>-71.958218}}

","@timestamp":"2022-01-13T19:31:38.322+00:00","@version":"1","severity":"INFO","host":"ip-172-30-1-201","tags":["nation_builder","task","sync"],"environment":"production"}

 #<SenderProfile id: 18166514, account_id: nil, email: "modrell211@charter.net", first_name: "Carol", last_name: "Modrell", middle_name: nil, line1: "211 Kearsarge Dr,", line2: nil, city: "Woodsville", state_id: 30, phone: nil, zip4: nil, prefix: nil, latitude: 44.116254, longitude: -71.958218, zip: "03785", country: nil, custom_field_ids: nil, custom_values_json: nil, facebook_handle: nil, facebook_token: nil, twitter_handle: nil, twitter_token: nil, confirmed_facebook: nil, confirmed_twitter: nil, confirmed_phone: nil, created_at: "2021-10-28 21:33:37", updated_at: "2021-10-28 21:33:37", twitter_nickname: nil, facebook_nickname: nil, advocate_profile_id: 6806789, imported: false, image: nil, import_uid: nil, external_id: "">

 => [#<OptIn id: 17262517, account_id: nil, promoter_user_id: 25179, created_at: "2021-10-28 21:33:37", updated_at: "2021-10-28 21:33:37", sender_profile_id: 18166514>]

=> [#<Conversion id: 25015889, archive_message_id: nil, sender_id: 18166514, created_at: "2021-10-28 21:33:37", updated_at: "2022-01-13 19:31:38", promoted_message_id: 14435, perishable_token: nil, permitted: false, subject: "OPPOSE U.S. House Bill 2377 (Red Flag/ERPO Legislat...", bodycachd: nil, topic: nil, recipients: "20738:73552:21321", external_message_id: nil, recipient_count: 3, finished_and_archived_to: nil, reached_recipient_count: nil, staged: true, oppose_flag: nil, allow_responses: true, comment: nil, widget_send: true, rubberstamped: false, quorum_gated: nil, preselected_recipients_at_creation: nil, deliveries_sent_at: nil, recipients_calculated_at: "2021-10-28 21:33:38", recipient_ids_always_send_and_local: "20738:73552:21321", reached_recipient_names: nil, recipient_ids_local: "20738:73552:21321", recipient_ids_always_send: "", recipient_ids_expanded: "77660:81660:182954:182696:182707:184015:182732:1827...", disable_email_verifications: true, sender_address_for_recipients: "211 Kearsarge Dr,", sender_city_for_recipients: "Woodsville", sender_zip_for_recipients: "03785", sender_state_id_for_recipients: 30, sender_latitude_for_recipients: 44.116254, sender_longitude_for_recipients: -71.958218, queued_at: nil, reached_recipient_ids: nil, redelivered: false, nation_builder_email_synced: false, nation_builder_tag_synced: true, nation_builder_unsyncable: false, multi_content: false, recipient_ids_expanded_content_one: nil, recipient_ids_expanded_content_two: nil, bodycachd_two: nil, subject_two: nil, reached_recipient_count_content_one: nil, reached_recipient_count_content_two: nil, reached_recipient_names_content_one: nil, reached_recipient_names_content_two: nil, reached_recipient_ids_content_one: nil, reached_recipient_ids_content_two: nil, signature_in_nodb_at: "2021-10-28 21:33:38", signature_in_nodb: true, backup_in_nodb_at: nil, backup_in_nodb: nil>]
```
This promoted message has no optin box on the campaign.  Does this mean we auto-opt-in?  <- ANSWER IS YES
```
=> #<PromotedMessage id: 14435, message_id: nil, promoted_from: nil, promoted_by: nil, created_at: "2021-10-27 19:38:24", updated_at: "2021-11-03 16:06:19", creator_id: 25179, goal: 3000, front_page_flg: nil, external_message_id: nil, uuid: nil, bodycachd: "As your constituent, a gun rights advocate, and a s...", subject: "OPPOSE U.S. House Bill 2377 (Red Flag/ERPO Legislat...", topic: "Congress", total_cnt: nil, processed_cnt: nil, shared_flg: nil, require_address: true, require_zip_only: false, require_phone: false, call_to_action: "<p>U.S. House Bill 2377 is making waves in D.C. &nb...", constituents_only: true, editable_widgets: true, widget_height: nil, widget_width: nil, country: nil, enable_comments_flg: false, hosted_at_url: "", internal_campaign_name: "U.S. House Bill 2377 (Red Flag/ERPO)", alternate_delivery_header: nil, donation_url: "https://secure.anedot.com/firearmspolicycoalition/d...", widget_redirect: true, remove_fb_link: nil, disable_email_verifications: true, custom_share_url: "", allow_opting_out: false, recipients_text: "", banner: nil, image: nil, model_type: nil, quorum_edit_token: nil, built_in_image: nil, custom_field_ids: nil, custom_fields_json: nil, call_sheet: "", phone_recipients_text: "", widget_font_family: nil, widget_background: "#0E0A3C", widget_button: "#FF6300", widget_font: "#FFFFFF", custom_widget_flg: true, tweet_text: "", socmed_recipients_text: nil, socmed_link: nil, share_tweet_text: "", share_tweet_via: "", share_facebook_text: nil, custom_campaign_image: "0EC2C8E9-75D4-45A0-A92D-C3238299D805.jpeg", recorded_greeting: nil, oneclick_recipients_text: "Use FPC's convenient constituent outreach tool belo...", oneclick_title: "Americans Have Due Process Rights! Tell Congress to...", facebook_text: nil, recorded_greeting_sid: nil, twitter_activity: 0, call_activity: 0, email_activity: 24234, total_activity: 24234, email_action_flg: true, social_action_flg: nil, phone_action_flg: false, conversion_activity: 11802, international_signatures: false, campaign_page_title: "Protect Your Second and Fourth Amendment Rights By ...", campaign_page_template: "topimg", video_action_flg: false, draft_kings_photo_campaign: nil, show_identity: true, show_counter: false, altstyles: false, opt_in_text: "", disable_email_verifications_last_switched: nil, kiosk_mode: false, show_actions_progress: true, video_activity: 0, multi_content: false, video_text: "", video_opt_in_text: "", cwc_campaign_id: "25b0ba2ec0a414cddabc1c2f330de251354be594f7ebc3c19a4...", bodycachd_two: nil, subject_two: nil, content_one_name: nil, content_two_name: nil, disabled: false>

```
However, this is for an update.  I don't think we are sending opt_in when updating an existing sender_profile.  Especially since we don't appear to update this in our own system.  The OptIn model with the SenderProfile doesn't seem to have a way to deactivate, unless it is by setting the sender_profile_id to nil.  Likely, since 1 in 7 are this way in prod. However, when I unchecked the box in order to opt out, nothing was updated.  :(



**Yesterday I**
- got the both phone required PRs approved and merged (ON-1538, 39, & 40)
- got everything deployed this morning; agents are back up and the queues are looking good
- met with Maged to discuss the plan for MD Catholic <- I need to create a ticket for this
- I'm still in process of determining exactly what we are sending to NB regarding `email_opt_in` <- serious magic going on here with the OptIn model and opt_in_sharing, but I made a leap of progress this morning on where we are storing it, but it doesn't seem consistent.  Like when the same sender profile signs again but opts out, nothing is changed it seems in the back end, meaning once a signer has opted in, they can't change to opting out.



**Today I plan to**
- [ ] try to quickly wrap up the question of opting in and what we then send to NB, 1st; get back to Maged on this as soon as I figure this out.  Try for ASAP this morning, then send to Maged what is being sent for opt in.  NationBuilder wants this at this point, so it is CRITICAL.
- [ ] get back to the recipient delivery address epic <- TOP PRIORITY (ON-1527 & ON-1530), 3rd


## Wed, Jan 12 2022
Shams knows how to set up rabbitmq locally to get deliveries working from end to end.  If I ever need this.

**Yesterday I**
- code complete on frontend, backend, and testing for the phone required
- PR for back end is awaiting the merge for the front end
- looked at MD Catholic,

**Today I plan to**
- working actively with folks to get through the PR reviews so I can get things deployed for business to see
- [x] get the front end phone required change PR approved and merged
- [x] get the back end phone required change checked in and PR'ed
- [x] get the back end phone required change PR approved and merged
- [x] get the phone required changes deployed <- FIRST THING TOMORROW
- [x] meet with Maged to discuss the plan for MD Catholic, https://oneclickpolitics.atlassian.net/browse/ON-1567
  - add new advocates as opted out
  - leave the opt-in status unchanged when the advocates already exists in the database.
  - MD Catholic wants the advocates to be opted in to emails whether existing or new
- [ ] determine exactly what we are sending to NB regarding `email_opt_in` <- serious magic going on here with the OptIn model and opt_in_sharing
- [ ] get back to the recipient delivery address epic <- TOP PRIORITY
- [x] Fix my admin password on staging/prod

### Test bugs introduced by shams:

https://github.com/one-click-politics/one-click-politics/pull/510 broke 7 tests.  I checked out master just before this merge and confirmed:
```
rspec ./spec/controllers/promoter/messages_controller_spec.rb:54 # Promoter::MessagesController all actions #index renders html and assigns instance variables
rspec ./spec/controllers/promoter/messages_controller_spec.rb:63 # Promoter::MessagesController all actions #index renders js
rspec ./spec/controllers/promoter/messages_controller_spec.rb:143 # Promoter::MessagesController all actions #retire renders js and sets flash notice on successful retire
rspec ./spec/controllers/promoter/messages_controller_spec.rb:170 # Promoter::MessagesController all actions #retire redirects_to index on html render
rspec ./spec/controllers/promoter/messages_controller_spec.rb:178 # Promoter::MessagesController all actions #resume renders js and sets flash notice on successful resume
rspec ./spec/controllers/promoter/messages_controller_spec.rb:212 # Promoter::MessagesController all actions #resume redirects_to index on html render
rspec ./spec/controllers/promoter/messages_controller_spec.rb:220 # Promoter::MessagesController all actions #duplicate renders js and sets flash notice on successful duplication
```

## Tue, Jan 11 2022
**Yesterday I**
- implemented the phone required message for groups
- found 7 tests in the messages_controller_spec.rb that were broken in Friday's merge of Shams' PR 510
- finalizing the tests for the phone required addition, should have the PR by lunch
- I got lucky and have already reviewed Hager's pull request unless I should re-review.

**Today I plan to**
- the back end portion of the phone required ticket is done and just needs tests
- this afternoon I hope to get back to the recipient delivery address epic <- TOP PRIORITY

- Fix my admin password on staging  

### new work from Maged
- assess the Maryland Catholic ticket with an eye towards the solution and time estimate
- get the phone stuff deployed


## Mon, Jan 10 2022
**Friday I**
- Investigated the syncs and by the time I looked (after a restart of the system by Eric), all was working correctly.
- Implemented for the front end portion of requiring phone for a US national level target, ON-1539, for:
  - house
  - senate
  - committees
- This morning I checked up on the weekend syncs and it looks like the every 6 hour NB syncs are running with no recurrance of last week's issue

**Today I plan to**
- Need to implement
  - groups
- Fix my admin password on staging  
- Need to think how to implement the front end tests
- Need to think how to implement the back end tests

Maybe give Eric a call and 15 mins of my time to aid his ruby challenges.

## Fri, Jan 7 2022
**Yesterday I**
- Followed up the missing phone number issue, researching and answering Chazz's questions.
- Changed the missing phone number task into and epic, and created two more tickets under that epic to handle the requiring of phone numbers for US campaigns targeting at the national level, for both front end and back end changes.
- started on the front end task for the US national level target requirement for phone number, ON-1539

**Today I plan to**
- finish the front end task for the US national level target requirement for phone number, ON-1539
- started on the back end task for the US national level target requirement for phone number, ON-1539
- then maybe get back to the first recipient delivery address task, The House, ON-1530

Based on messages from Dave, I will also take a look at the NB syncs from the last couple of days and see what is (or isn't) going on.


## Thu, Jan 6 2022
**Yesterday I**
- Spent the day chasing why 60% of the deliveries were failing for Yamaha's Foraging Fish campaign.  After many dead ends for cause, I turned to Alex, who later brought in Shams for Elastic Search assistance.  We finally discovered the biggest of the three separate issues was the lack of phone numbers.  This was targetting the house, which uses the CWC, which requires those phone numbers.  ON-1529

**Today I**
- [x] expect I'll be looking into Chazz's follow up questions and potentially making an addition to our API (¿who is familiar with our API and can they walk me through it briefly?):
  - [x] Does our API currently accept phone numbers for third party import of data into our system?  Chazz believes the answer to this is no.  If/when we do, he'll require all third party vendors to collect a phone number for these types of campaigns.
  - [x] Chazz has noticed in the past that when the campaign settings have the "no phone number required" button selected, signatures will pass through our API without incident. However, if it is turned ON, then our system refuses to accept the new signatures.
- [x] change original ticket to an epic with two tasks, one for front end, one for back end.  ON-1538 Require phone numbers for US campaigns targeting at the national level.
- [x] create front end task for the US national level target requirement for phone number, ON-1539
- [x] create back end task for the US national level target requirement for phone number, ON-1540
- [x] start front end task for the US national level target requirement for phone numberj, ON-1539
- [ ] then maybe get back to the first recipient delivery address task, The House, ON-

### use postman to verify with our API that:
#### tried both with phone required = off and with phone required = on
- the phone is sendable to the API.  I have confirmed that no error is received when the phone is included. Succeeds with and without dashes.
- the phone is stored when sent to the API aka is the phone being used
- wrote up these details and sent to Chazz and Darren.
- asked Maged if a Jira ticket should be created for this work:
  - add a check for any campaign targeting US recipients at the national level to require phone numbers from the signers.
If so, when the promoter tries to add a US national level target on a campaign that has phone numbers required switched off, they should get a warning only, or should the phone required automatically switched back on, perhaps with a warning this has been changed?


## Wed, Jan 5 2022
**Yesterday I**
- wrapped up the last estimates for the recipient delivery address tasks, epic, ON-1527
- created Jira tickets for those tasks, ON-1530 to ON-1537
- finished various PR reviews
- Interrupted everything for #1, the pixel addition.  Got that done, PR'ed, and deployed.  ON-1528
- Then interrupted everything for #2, this: why have 1800/3000 deliveries failed for Foraging Fish Campaign for Yamaha Promoter ID 40719. < look at the new Cicero data and see if this campaign is using new or old contact data.  Initial assessment by Alex suggests that this is running into a lack of...  ON-1529
- Still working on that last when everything was interrupted for #3, the NoDB sync and csv download issue.

**Today I plan to**
- get back to #2 in the morning, or if there is no Dave, we'll need to dive in the code to figure out #3.
- then back to the first recipient delivery address task, The House, ON-1530

Recipient.find 40719


## Tue, Jan 4 2022
Start squashing commits, so there is just one per feature.  For me, this mostly applies to refactoring and PR review changes.

**Yesterday I**
- did a little pairing with Nate on rubocop
- got the NB fix deployed.  the too many open files issue still occurs
- did a lot of PR review
- I've written up the Jira for the recipient delivery address epic with a breakdown of all the tasks including estimates; I still need to create the actual Jira tickets for the tasks under that epic.  

**Today I plan to**
- add tracking pixels, ON-1528
- why have 1800 deliveries failed for Foraging Fish Campaign for Yamaha Promoter ID 40719
- finishing the PR reviews
- wrap up the last estimates for the recipient delivery address tasks
- create the recipient delivery address tasks

Fibonacci (..1,2,3,5,8,13) ~= [2,4,8,16-24,...] in hours (if the fibonacci # is more than 5, the task is too big.  And 5 is often too big)

(F3) 1. Find House delivery addresses and priorities.  Top should be cwc.  Confirm this.  All of the House are supposed to be using cwc. 435 Recipients (1/2 day for analysis, 1/2 day for script, 2-4 hours to write up the summary)  

(F3) 2. Find Senate delivery addresses and priorities.  At last check, only 29 members are using cwc.  Confirm this is #1 priority address for delivery.  100 Recipients (1/2 day for analysis, 1-2 hours to write up the summary)

(F3) 3. Who can we not deliver to at all because they have no viable addresses?  Does non-viable address here mean that no address works, or does it mean nothing works except fax? (1/2 day for analysis, 2-4 hours to write up the summary) <- if this needs a script, the additional 2 hours is build into the summary write up estimate

(F3) 4. Find Recipients who have webforms but no steps to do the webform. Is this web form address un-deliverable for any other reason?  (1/2 day for analysis, 2-4 hours to write up the summary)  <- if this needs a script, the additional 2 hours is build into the summary write up estimate

(F5) 5. When Recipient has a web address, can we produce the steps for the webform? (1 day for analysis, 1-2 days for step production)

6. Identify all those for whom fax is the only method of delivery.

7. People marked as bad email by amazon (aws)...what can we do to correct the not_delivered_to.  Once we mark as bad, does/can this get reset over time?

8. we want to send #7 through a service for email verification; Maged used briteverify.  And sent me this link, https://get.validity.com/bv-demo/

## Mon, Jan 3 2022
**Thursday I**
- Discovered a bug that was failing the syncing on a number of campaigns.  This was due to a singly used REGEX stuck in the NB sync code that was not permitting an apostrophe in an email address.  For Australian recipients, this can be a problem.  I fixed it, the PR has been reviewed, I'd like to get it deployed **this morning**.
- The above slowed me down, so **today** I'll be finishing putting together the epic ticket and estimations for the various tasks of recipient delivery address analysis
- I'll also be reviewing the results of the long weekend of many syncs to see how things went.  I saw a couple CAT failures come through, but no more than I would expect.
- Review a couple of Shams' PRs that slack pinged me about this morning

1. find house, should be cwc.  confirm this, all are supposed to be using cwc (1/2 day for analysis, 1/2 day for script, 1-2 hours to write up the summary)
2. senate, only 29 members are using.  confirm this is #1 priority
3. who can we not deliver to at all; no viable addresses
4. people who have webforms but no steps to do the webform. is this address un-deliverable in any other fashion
5. person has web address, can we produce the steps for the webform
6. identify all those for whom fax is the only method of delivery
7. people marked as bad email by amazon (aws)...what can we do to correct the not_delivered_to.  Once we mark as bad, does/can this get reset over time?
8. we want to send #7 through a service for email verification; Maged used briteverify.  And sent me this link, https://get.validity.com/bv-demo/


## Thu, Dec 30 2021
**Yesterday I**
- met with Maged to plan for the US recipient delivery data collecting
- deployed the fix for the sync's extra_data field
- looked at the results from the last 3 sync crons since yesterday and found a bug!
- emailed NationBuilder
- found a bug when we prep for a NB sync where we are rejecting valid recipient addresses if they contain an apostrophe.  Big problem in AU with names like O'Donohue, etc.  This is causing many campaign syncing failures.  Not sure yet how many that is, but I was seeing many sync failures for campaigns to the same recipient.

**Today I plan to**
US recipient research project


## Wed, Dec 29 2021
### last night's NB sync failures:
20176
25179
39169
39520
39522, fully caught up 29 Dec, 2021, 11am

user = 20176
PromoterUser.find(user).master_account.authentications
acl
d111b8b049646b592799ae69da9eba4fdbee7e39fe03dbf9e23278fbb3df2ae7

**Yesterday I**
- Got a late start due to a power and internet outage.  Fortunately got power back before noon, so I was able to work out may day, just shifted later.  
- Paired with Eric and Alex (with Nate listening in) until we got deployment to the NationBuilder (pre-prod) to work.  It appears that the deployment script did not like the elastic IP for the rabbit mq server.  This issue should only occur if the rabbit server has been rebooted since the last deployment.  
- Changed the NB sync cron to every 6 hours, `0 5,11,17,23 * * *`.  
- Found and fixed an error in how I was adding to the sync's .extra_data field which the NB sync is now using to track the (major) steps it has taken in the sync.  PR is here, https://github.com/one-click-politics/one-click-politics/pull/513

**Today I plan to**
- deploy the fix for the sync's extra_data field
- look at the results from the last 3 sync crons since yesterday

- [x] email to NB
  - we are increasing our sync cron from 1 every 24 hours to 1 every 6 hours, with a possible planned increase to 1 every 3 hours.
  - please increase our rate limitation from 250 calls per 10 seconds


## Tue, Dec 28 2021
### additional work
- [ ] create a ticket to create a migration to change the length limit for the .log and .extra_data fields on SynchronizeCalls
- [ ] saw a zendesk come through on a NationBuilder issue I plan to take a look at once prod console is working

### new work upcoming:
pre-work: epic ticket and estimations for the various tasks
1. find house, should be cwc.  confirm this, all are supposed to be using cwc (1/2 day for analysis, 1/2 day for script, 1-2 hours to write up the summary)
2. senate, only 29 members are using.  confirm this is #1 priority
3. who can we not deliver to at all; no viable addresses
4. people who have webforms but no steps to do the webform. is this address un-deliverable in any other fashion
5. person has web address, can we produce the steps for the webform
6. identify all those for whom fax is the only method of delivery
7. people marked as bad email by amazon (aws)...what can we do to correct the not_delivered_to.  Once we mark as bad, does/can this get reset over time?
8. we want to send #7 through a service for email verification; Maged used briteverify.  

recipient analysis, find the non-cwc users
failed deliveries due to web forms, need to figure out how to do That
who is unreachable at all

### longterm NationBuilder Jira ticket tracking the steps needed to do the improvements that NationBuilder syncing will need to run reliably
https://oneclickpolitics.atlassian.net/browse/ON-1293

### troubleshooting production issues document
https://docs.google.com/document/d/1dGrvRMmDjdsfqcnqUJoz1iAGoEjW6wYE7deH6AiyJm8/edit

### current tasks
- [x] Work with someone to get the pre-prod deployment issue sorted.  Posted pre-prod update to @engineering.  Blocked until I get some help.
- [ ] Send that email to NationBuilder as it was awaiting the list of the most affected promoters (which was the last thing I did last night before the pre-prod deployment issues).
- [x] Change sync cron to every 6 hours, `0 5,11,17,23 * * *`.  

From:
```
0 23 * * *        rake nation_builder_sync:sync_all['39082','2019-06-18T23:19'] --silent'
```
To:
```
0 5,11,17,23 * * *          rake nation_builder_sync:sync_all['39082','2019-06-18T23:19'] --silent'
```

### Power/internet outage notification to team
_I had to drive over to Sugar and Spice to use their internet with 15% battery remaining on my laptop.  Terrible night to forget to plug in my laptop._

Hi folks.  Power is out and this time that means cell connectivity as well.  Sadly, I did not plug my computer in last night, so this also means I'll be running out of laptop shortly.

Depending on how long it takes the power to return, I'll either:
  - start work as soon as the power returns and work late to make up the time
  - start work as soon as the power returns working the rest of the day and calling the morning a half day off
  - take the day as a full day off and spend the time with Kai who is very bored with no power/internet/computer


### Official data needed to create a person on NationBuilder
{ "person": {
"email": "melanie.faraday+3@gmail.com",
"first_name": "Melanie",
"last_name": "Faraday"
} }

        "email_opt_in": true,   <- nothing was sent; this is the NB default when nothing is sent for this field
        "party": null,   <- nothing was sent; this is the NB default when nothing is sent for this field
        "prefix": null,   <- nothing was sent; this is the NB default when nothing is sent for this field


### Today's status:
**Yesterday I**
- Spent the morning reviewing various PRs for Shams and Hager.
- Responded to reviews, merged, and deployed both:
  - NB sync.extra_data (ON-1507)  
  - exception handling for notifier (ON-1510)
- Identified the 6 promoters most affected by NB syncing issues.
- Wrote up the email to NationBuilder about increasing the 250 limit on the above 6 promoters.  Included information about our plan to increase our sync interval to every 6 hours.  I have confirmed this limitation is by slug and not a blanket limitation.  

**Today I plan to**
- Work with someone to get the pre-prod deployment issue sorted.
- Send that email to NationBuilder as it was awaiting the list of the most affected promoters (which was the last thing I did last night before the pre-prod deployment issues).
- Change sync cron to every 6 hours.


## Mon, Dec 27 2021
**Thursday I**
- created a ticket for the logging additions, ON-1507
- put out a PR for more logging additions to NB syncs, https://github.com/one-click-politics/one-click-politics/pull/506
- created ticket for notifier call exception handling, ON-1510
- wrapped the notifier calls that are crashing the entire sync into some exception handling, https://github.com/one-click-politics/one-click-politics/pull/507

**Today I plan to**
- [x] review various PRs for Shams and Hager
- [x] respond to reviews, merge, and deploy both:
  - NB sync.extra_data (ON-1507)  
  - exception handling for notifier (ON-1510)
- [x] identify 2-10 promoters most affected by NB syncing issues
- [ ] Ask NB to increase our 250 limit.  <- send message about out every 6 hours syncing plan; ask to increase limit to brian builder  (ask what is this maximum); read through Alex's Jira ticket on this first to confirm the limitation.  Also, this is a slug limitation not a blanket limitation, so determine which slugs need this improvement.
- [ ] Change sync cron to every 6 hours.
- [ ] I also think I need to set up log rotation for the NationBuilder logs since those are in heavy use at the moment.  Info from Dave tells me this is set up and straightforward.
- [ ] create a ticket for NB log rotation

- [ ] create a ticket to create a migration to change the length limit for the .log and .extra_data fields on SynchronizeCalls
- [ ] saw a zendesk come through on a NationBuilder issue I plan to take a look at once prod console is working

Good morning Brian,

This is Susan from OneClickPolitics.  

I would like to increase our 250 calls per 10 seconds limit.  My understanding is that it is possible for this to be a blanket change for all of our calls to your API on behalf of all our clients, is that correct?   

Additionally, we currently run the syncing of our clients daily at 2300 UTC.  We are increasing that to every six hours with a possible increase towards every three hours and wanted you to know of the increase coming through.

Thank you for your time, Brian.  Best regards and happy holidays.

Susan Prestage
OneClickPolitics


## Fri, Dec 24 2021
### Paid Holiday, Christmas observed


## Thu, Dec 23 2021
**Yesterday I**
- worked on getting things ready for checkin plus Rubocop cleanup

- Ask NB to increase our 250 limit.  <- send message about out every 6 hours syncing plan; ask to increase limit to brian builder  (ask what is this maximum); read through Alex's Jira ticket on this first to confirm the limitation.  Also, this is a slug limitation not a blanket limitation, so determine which slugs need this improvement.
- And sync every 6 hours.

**Today I plan to**
- [x] create a ticket for the logging additions, ON-1507
- [x] put out a PR for more logging additions to NB syncs, https://github.com/one-click-politics/one-click-politics/pull/506
- [x] wrap the notifier calls that are crashing the entire sync into some exception handling, https://github.com/one-click-politics/one-click-politics/pull/507
- [x] create ticket for notifier call exception handling, ON-1510
- [ ] I also think I need to set up log rotation for the NationBuilder logs since those are in heavy use at the moment.  Info from Dave tells me this is set up and straightforward.
- [ ] create a ticket for NB log rotation

- [ ] create a ticket to create a migration to change the length limit for the .log and .extra_data fields on SynchronizeCalls
- [ ] saw a zendesk come through on a NationBuilder issue I plan to take a look at once prod console is working

### new work upcoming:
recipient analysis, find the non-cwc users
failed deliveries due to web forms, need to figure out how to do That
who is unreachable at all


## Wed, Dec 22 2021

### conversion call for NationBuilder sync:
```
promoter = PromoterUser.find 25179
promoter = PromoterUser.find 39610
@epoch = '2019-06-18T23:19'
@epoch_id ||= Conversion.where("created_at > ?", @epoch).first.try(:id) || 1
@apocalypse = '3000-12-31T23:19'
@apocalypse_id ||= Conversion.where("created_at > ?", @apocalypse).first.try(:id) || Conversion.last.try(:id) || 1000000000
QUERY_LIMIT = 10000

# get_service_deliveries_for_sync
@service_delivery_epoch_id ||= ServiceDelivery.where("created_at > ?", @epoch).first.try(:id) || 1
@service_delivery_apocalypse_id ||= ServiceDelivery.where("created_at < ?", @apocalypse).last.try(:id) || ServiceDelivery.last.try(:id) || 1000000000

promoted_message_count = promoter.promoted_messages.count

count = 0
promoted_message_count.times do |x|
  promoted_message = promoter.promoted_messages(promoted_message_count)[x]

  pm_count = promoted_message.service_deliveries.includes(sender_profile: {advocate_profile: [:advocate_for_promoters, :state, :external_connections]}).includes(:conversion).includes(recipient: [:recipient_addresses, :party]).where('service_deliveries.id >= ?', @service_delivery_epoch_id).where('service_deliveries.id <= ?', @service_delivery_apocalypse_id).where('service_deliveries.nation_builder_synced = ?', false).where('service_deliveries.nation_builder_unsyncable = ?', false).where("(service_deliveries.delivery_type IN ('Twitter','Phone')) OR (service_deliveries.model_type = 'VideoServiceDelivery')").where('sender_profiles.advocate_profile_id IS NOT NULL').where('advocate_for_promoters.opt_in_id IS NOT NULL').count

  count += pm_count
end

promoter.promoted_messages.each do |promoted_message|
  pm_count = promoted_message.service_deliveries.includes(sender_profile: {advocate_profile: [:advocate_for_promoters, :state, :external_connections]}).includes(:conversion).includes(recipient: [:recipient_addresses, :party]).where('service_deliveries.id >= ?', @service_delivery_epoch_id).where('service_deliveries.id <= ?', @service_delivery_apocalypse_id).where('service_deliveries.nation_builder_synced = ?', false).where('service_deliveries.nation_builder_unsyncable = ?', false).where("(service_deliveries.delivery_type IN ('Twitter','Phone')) OR (service_deliveries.model_type = 'VideoServiceDelivery')").where('sender_profiles.advocate_profile_id IS NOT NULL').where('advocate_for_promoters.opt_in_id IS NOT NULL').count
  count += pm_count
end
```


### status
**Yesterday I**
- Deployed the logo swap (from IAPPA to Yamaha).
- Created a Jira ticket and wrote up the details of what we send in the various calls to the NationBuilder API during the course of our nightly sync.  This includes the service delivery portion and a full explanation of the steps we take for data collation as well as each API call we make to do a full sync.  This also includes the limitations imposed by us or NB.  Here https://oneclickpolitics.atlassian.net/browse/ON-1505

**Today I plan to**
- [ ] create a ticket for the logging additions
- [ ] put out a PR for more logging additions to NB syncs
- [ ] wrap the notifier calls that are crashing the entire sync into some exception handling
- [ ] create ticket for notifier call exception handling
- [ ] I also think I need to set up log rotation for the NationBuilder logs since those are in heavy use at the moment.  Info from Dave tells me this is set up and straightforward.
- [ ] create a ticket for NB log rotation

- [ ] create a ticket to create a migration to change the length limit for the .log and .extra_data fields on SynchronizeCalls
- [ ] saw a zendesk come through on a NationBuilder issue I plan to take a look at once prod console is working


## Tue, Dec 21 2021

**Friday I**
- [x] send reminder email to the business to decide if they:
  - like the data we currently send to tag a campaign (the name of the campaign)
  - prefer we use different data
  - want to implement a new feature where what is sent as a tag is configurable by the client
- [x] send Maged the CATASTROPHIC error stack trace and how to run the single sync for the error promoter
- [x] changed client logo from IAPPA to Yamaha, checked in, PR created
- [x] Worked on putting together exactly what info we send to the NationBuilder API for each call made during syncing.  (every field and where the data came from in our system)
  - [x] AdvocateProfile
  - [x] Recipient

**Today I plan to**
- [x] continue to put together exactly what information (every field and where the data came from in our system) that we send to the NationBuilder API for each call made during syncing
  - sync advocate contact to recipient
  - Tags
  - Authentication
  - Anything other data I can find that we send over.
- [x] dive into the service delivery portion of the NB syncs for the data needed for the NB API calls
- [x] research what other limitations we have for NationBuilder in addition to:  <- I'm watching for these as I'm collecting data above
  - 250 calls per 10 seconds (NB limitation)
  - 10,000 conversions per promoter per night
  - RESULTS: I can find no other limitations.  Interestingly, I also cannot find the slowdown we implemented for the 250 calls per 10 seconds that I keep hearing about.  I see where we added error handling/logging about 2 years ago for when we hit the rate limit, but nothing that changes the timing of how we send.  
- [ ] create a ticket for the logging additions
- [ ] put out a PR for more logging additions to NB syncs
- [ ] wrap the notifier calls that are crashing the entire sync into some exception handling
- [ ] create ticket for notifier call exception handling
- [x] create research ticket to track the information I'm collecting
- [ ] I also think I need to set up log rotation for the NationBuilder logs since those are in heavy use at the moment.  Info from Dave tells me this is set up and straightforward.
- [ ] create a ticket for NB log rotation
- [ ] create a ticket to create a migration to change the length limit for the .log and .extra_data fields on SynchronizeCalls


## Mon, Dec 20 2021
** sick day **

I've no focus today and I'm sleepy.  Going to take a day for mental health and de-stressing.


## Fri, Dec 17 2021
### mark_unsyncable
A conversion is marked unsyncable=true if:
  - promoter user doesn't have valid authentication with NB
  - person is unsyncable  (advocate or very unlikely a recipient)
      person.mark_unsyncable!(:nation_builder, 'email_is_invalid', @promoter)
      person.mark_unsyncable!(:nation_builder, 'email_is_invalid', @promoter)
      person.mark_unsyncable!(:nation_builder, 'county_id_file_missing', @promoter)
      person.mark_unsyncable!(:nation_builder, 'profile_website_not_real_url', @promoter)
      person.mark_unsyncable!(:nation_builder, 'billing_address_phone_unmber_cannot_be_blank', @promoter)
      person.mark_unsyncable!(:nation_builder, 'recruiter_name_with_email_should_not_be_the_same_person', @promoter)
      person.mark_unsyncable!(:nation_builder, 'custom_value_married_is_not_valid', @promoter)
      person.mark_unsyncable!(:nation_builder, 'email_has_already_been_taken', @promoter)
      person.mark_unsyncable!(:nation_builder, 'username_is_already_taken', @promoter)
      person.mark_unsyncable!(:nation_builder, 'zip_is_too_short', @promoter)
      person.mark_unsyncable!(:nation_builder, 'phone_number_invalid', @promoter)
    when /base You must supply at least a first and last name, an email address, or a phone number\./
      person.mark_unsyncable!(:nation_builder, 'missing_required_values', @promoter)

### sync recipient
Recipient data needed from our system
  Recipient.prefix
  Recipient.first_name
  Recipient.last_name
  Recipient.middle_name
  Recipient.email_addresses <- has many
  Recipient.phone_addresses <- has many
  Recipient.party
  Recipient.district_address
    DistrictAddress.line1
    DistrictAddress.line2
    DistrictAddress.city
    DistrictAddress.state
    DistrictAddress.zip
  Recipient.external_connections <- need this to create a contact the advocate for this recipient

Call to the NB API, if new recipient
`post("people", {person: person_data})`

Call to the NB API, if recipient exists
`put("people/#{person_id}", {person: person_data})`

where person_data:
```
{:prefix=>nil,
 :first_name=>nil,
 :last_name=>nil,
 :middle_name=>nil,
 :email=>"test1@ocp.com",
 :email1=>"test1@ocp.com",
 :phone=>"202-225-5601",
 :party=>"R",
 :work_address=>{:address1=>nil, :address2=>nil, :city=>nil, :state=>nil, :zip=>"02062"},
 :email_opt_in=>false}
```

### sync advocate
AdvocateProfile data needed from our system
  AdvocateProfile.id
  AdvocateProfile.email
  AdvocateProfile.phone
  AdvocateProfile.line1
  AdvocateProfile.line2
  AdvocateProfile.city
  AdvocateProfile.state
  AdvocateProfile.zip
  AdvocateProfile.country <- not sent, but needed to determine country_code
  AdvocateProfile.country_code
  AdvocateProfile.latitude
  AdvocateProfile.longitude
  AdvocateProfile.external_connections

Call to the NB API, if new advocate
`post("people", {person: person_data})`

Call to the NB API, if advocate exists
`put("people/#{person_id}", {person: person_data})`

where person_data:
```
{:email=>"test_advocate_5@example.com",
 :phone=>nil,
 :prefix=>nil,
 :first_name=>nil,
 :last_name=>nil,
 :middle_name=>nil,
 :external_id=>14562,
 :home_address=>
  {:address1=>nil, :address2=>nil, :city=>nil, :state=>nil, :zip=>nil,
   :country_code=>nil, :lat=>nil, :lng=>nil}}
```

### sync advocate contact to recipient
Data needed to sync advocate to recipient; provided by with default values or earlier sync steps
  recipient_nation_builder_id         <- we have this from the just performed recipient sync
  advocate_profile_nation_builder_id  <- we have this from the just performed advocate sync
  contact_type_id                     <- this is generated from NATION_BUILDER_CONTACT_TYPE
  method                              <- 'email' or other service_delivery_method
  status                              <- 'Left Message'  This appears hardcoded
Conversion data needed from our system
  note  <- conversion.subject

Call to the NB API:
`post("people/#{recipient_id}/contacts", {contact: contact_data})`

where contact_data =
```
{:sender_id=>223456,
 :type_id=>11,
 :status=>'Left Message',
 :method=>'email',
 :note=>'Save the Whales'}
```

### sync tag to advocate
Actual data sent to NB API to create tag on advocate
  advocate_profile_nation_builder_id  <- we have this from the just performed advocate sync
  Conversion.promoted_message.internal_campaign_name

Call to the NB API:
`put("people/#{person_id}/taggings", tag_data)`

where tag_data =
```
{:tag=>'Save the Whales'}
```


- [x] SYNC the advocate for that conversion (update_person or create_person call to NB API)
- [x] SYNC each recipient (update_person or create_person call to NB API)
- [x] SYNC each recipient's contact which is the sending advocate (create_contact call to NB API)
- [x] SYNC the tag (create_tag call to NB API)


### all calls to NationBuilder
lib/nation_builder_client/lib/people.rb
`get("people/#{person_id}")`
`post("people", {person: person_data})`
`put("people/#{person_id}", {person: person_data})`
`put("people/push", {person: person_data})`
`get('people/count')`
`delete("people/#{person_id}")`
`get("people/search?page=#{page}&#{q}")`
`get "people?page=#{page}"`

lib/nation_builder_client/lib/contacts.rb
`post("people/#{recipient_id}/contacts", {contact: contact_data})`

lib/nation_builder_client/lib/tags.rb
`put("people/#{person_id}/taggings", tag_data)`


**Yesterday I**
Researched the question of why aren't we kicking off syncs every day for all promoters with syncs?  The upshot is that we ARE syncing all qualified promoters with qualified new conversions each evening.  That said, we have at least one large promoter who is over a week behind in syncing due to the "too many open files" issue.

**Today I plan to**
- [ ] put together exactly what information (every field and where the data came from in our system) that we send to the NationBuilder API for each call made during syncing
  - [x] AdvocateProfile
  - [x] Recipients
  - Tags
  - Authentication
  - Anything other data I can find that we send over.
- [ ] dive into the service delivery portion of the NB syncs for the data needed for the NB API calls
- [ ] research what other limitations we have for NationBuilder in addition to:
  - 250 calls per 10 seconds (NB limitation)
  - 10,000 conversions per promoter per night
- [ ] create a ticket for the logging additions
- [ ] put out a PR for more logging additions to NB syncs
- [ ] wrap the notifier calls that are crashing the entire sync into some exception handling
- [ ] create ticket for notifier call exception handling
- [ ] create research ticket to track the information I'm collecting
- [ ] I also think I need to set up log rotation for the NationBuilder logs since those are in heavy use at the moment.  Info from Dave tells me this is set up and straightforward.
- [ ] create a ticket for NB log rotation
- [x] send Maged the CATASTROPHIC error stack trace and how to run the single sync for the error promoter
- [ ] create a ticket to create a migration to change the length limit for the .log and .extra_data fields on SynchronizeCalls
- [x] send reminder email to the business to decide if they:
  - like the data we currently send to tag a campaign (the name of the campaign)
  - prefer we use different data
  - want to implement a new feature where what is sent as a tag is configurable by the client
- [x] change client logo from IAPPA to Yamaha, checked in, PR created


## Thu, Dec 16 2021
**Yesterday I**
- Researched the over long syncs.  
With the new logging that has been added (on the sync), these can now be clearly identified:
    - sync = NationBuilderSynchronizeCall.where(status: "In progress").first
    - if sync.log does not contain today's (or yesterday's date), then we can change the status to `failure`

So...cronjob rake task to look for 'In progress' syncs, fail them, and write to the sync.extra_data field that this was marked failed due to being stale.

It does not appear that the sync process is still running in any of these cases, so it does not look like we'll to need to kill the process.

- still looking into the two big failures and would value help:

  - too many open files which causes syncing failures (the CATASTROPHIC failure) for our largest customers on a nightly basis, causing the sync to get further and further behind for these clients.  I've been digging into the stack trace and looking at the code and try to figure out whether some gem that we're using is treating api calls like files or something.  I would value additional perspective on this.

  - sync crashing when notifier is called; I'm not seeing recent changes that are related, yet this is a recent new issue; I would value more direction on this.  

**Today I plan to**
- [ ] continue as best I can on all three critical NB issues

long syncs - Maged - wants to know why these are happening.  I feel they are so rare as to not be an issue and can just be cleaned up.  Alternatively, they can be better monitored now as a result of the step by step logging being done on the sync itself (starting each phase of syncing) and logging to the log file (every call to NB is logged now)

### THE QUESTION I AM RESEARCHING IN THIS MOMENT
Why aren't we kicking off syncs every day for all promoters with syncs?  Details follow, but I'm thinking that we are syncing all qualified promoters with qualified new conversions each evening.  That said, we have at least one large promoter who is over a week behind in syncing due to the "too many open files" issue
  - first, we get all promoters who are:
      - not the master account
      - are tied to NB
      - have a NB token
      - have NB write access

  - second, for each promoter we:
      - create a sync
      - skip them if they already a recent and In progress sync (logging the issue on the new sync we just created...BUT NOT FAILING IT??!?)

      - get conversions for the email sync that:
          - are from June 2019 to now.  I think we should slim the `default_epoch` to the end of 2020.  
          - are not yet synced
          - are not marked un-syncable
          - have reached recipient ids
          - the advocate has not opted out of their data being collected
          - max out at 10,000

          - for each conversion, we then
              - SYNC the advocate for that conversion (update_person or create_person call to NB API)
              - get the recipients for that conversion
                  - SYNC each recipient (update_person or create_person call to NB API)
                  - SYNC each recipient's contact which is the sending advocate (create_contact call to NB API)

      - get conversions for the tag sync that:
          - are from June 2019 to now.  I think we should slim the `default_epoch` to the end of 2020.  
          - the promoted_message_id is not null or empty string <- WE DON'T CHECK THIS FOR EMAIL SYNCS
          - are not yet synced
          - are not marked un-syncable
          - the advocate has not opted out of their data being collected
          - max out at 10,000

          - for each conversion, we then
              - SYNC the advocate (update_person or create_person call to NB API)
              - SYNC the tag (create_tag call to NB API)

##### note: the individual service deliveries are (simplified) conversions split into each recipient)
      - get the service deliveries for the the service delivery sync that:
          - includes the sender_profile and corresponding advocate profile's advocate_for_promoters, state, and external_connections
          - includes the whole conversion
          - includes the recipient's recipient_addresses and party
          - are from June 2019 to now.  I think we should slim the `default_epoch` to the end of 2020.  
          - are not yet synced
          - are not marked un-syncable
          - are delivery_type of Twitter','Phone', or 'VideoServiceDelivery
          - the sender_profiles.advocate_profile_id is not null
          - the advocate has not opted out of their data being collected
          - max out at 10,000

          - for each service delivery (conversion split into 1 per recipient)
                - SYNC the recipient (update_person or create_person call to NB API)
                - SYNC the advocate (update_person or create_person call to NB API)
                - SYNC the recipient's contact which is the sending advocate (create_contact call to NB API)


AdvocateProfile - what do we send, exactly
Recipients - what do we send, exactly
Tag - per conversion

limitations for NB, 250 per 10 seconds <- are there others
how often do we run the sync, every night at 6pm EST, 23:00 UTC

- [ ] look into service deliveries
- [ ] send all fields we send for each (type) of user

- [ ] send error and how to run the single sync for the error promoter

- [ ] create research ticket;

5% increase, $82,000 said Maged, but if the 5% is correct, then this raises my salary to $84,000I 4I


## Wed, Dec 15 2021

### three big NationBuilder issues:

#### over long syncs - ready to report to Maged
These can now be identified by the following characteristics:
- sync = NationBuilderSynchronizeCall.where(status: "In progress").first
- if sync.log does not contain today's (or yesterday's date), then we can change the status to `failure`

So...cronjob rake task to look for 'In progress' syncs

It does not appear that the sync process is still running in any of these cases, so it does not look like we'll to need to kill the process.

#### too many open files
This is the failure that happens to the big promoters.  We aren't doing any file opens in these syncs.  This was the error triggering the CATASTROPHIC failures that was triggering the error emails we are sending to ourselves which was crashing the sync.  

Looking at the last rescue in the sync to try to resolve this issue.

Also, continue to dig into the stack trace and look at the code and try to figure out whether some gem that we're using is treating api calls like files or something.  

#### why is sync crashing when notifier is called
- check what changes (for Rubocop?) might have affected notifier or the calls to notifier <- Nope, not seeing any changes from the last month that should affect notifier or its use in nation_builder_sync.rb.
- not sure what to look at next



**Yesterday I**
- checked in and deployed the patch changes from Monday night's NB sync issues discovered by me and Dave.  Commented out the code sending us error emails which was crashing the entire sync.  This is a temporary patch where the actual error must be fixed and this workaround (commented out email notifiers) must be restored to working order.
- demo of new UI design coming in 2022
- retro
- met with Eric to brainstorm on NationBuilder, particularly the `too many open files` failure that happens to the big promoters
- I have added some lines to store how the sync is progressing on the sync and these now show in the admin pages for synchronize calls.  I'm only seeing one so far and it got stuck in tag syncing and hasn't progressed for the last day and a half.

This morning, i've been working my way through PR reviews...almost done with Hager's PR, then on to Shams'.

**Today I plan to**
- [ ] finish researching the overly long sync issues;


## Tue, Dec 14 2021
- [x] MUST CHECK IN THE FIXES FROM LAST NIGHT'S SYNC!!!

### rubocop tips and tricks
`rubocop -a` can fix smaller issues.  Give this a try.

There is also an "overcommit" that Hager is using that auto-runs Rubocop when you are going to commit to github.

### NationBuilder ideas from Dave
we may need to bring up a box specifically to catch up on the 74,000 campaigns behind client.

**Yesterday I**
researching the overly long sync issues
paired with Dave at length on this

new prs to review

Start with the bottom rescues in sync_all.
Crux of issue: sending the sync error emails to ourselves was crashing the whole sync.  We (Dave and I) monkey patched prod to remove the `notifier.error_notification` lines and the `sync.send(:notifier)...` lines.

Also, here is where to start:
```
but i’d look at “cannot load such file -- action_view/lookup_context” to see if it’s possible to fix the emails
6:40
that, or just wrap the emails themselves in exception handling
6:40
so if it can’t send out the email it doesn’t break the whole sync
6:40
that will probably be easiest and won’t break tests that listen for the emails
```

## Mon, Dec 13 2021
**Friday I**
- researched how to detect a stale overly long sync; reported to Maged on my findings as well as updating the Jira ticket with the same
- read through Dave's import instructions for US to see how it works/reads; the writeup is in this jira https://oneclickpolitics.atlassian.net/browse/ON-1407 the instructions are at the top, plus a ton of comments below tracking what he's doing.  It is also in the comments for the shape file rake task.
- reviewed Dave's cicero US PR in detail; many comments but only because it was huge and I had some ideas based on domain knowledge of cicero and imports for different countries

The new KnowWho data has not yet been pushed, so I'll look for it later today or tomorrow.

**Today I plan to:**
- [ ] work on the overlong syncing solution
- [ ] check KnowWho again after lunch

### tagging status
findings and questions posted to engineering.  link to findings sent to Dave.  Blocked until further direction is found/given.

### overlong syncing status
Summary from the call with Maged at 5pm, Friday.  As each advocate and each tag is synced, we need a field to be updated on the NationBuilderSyncCall so we can tell when the sync is no longer `In progress`.  It may be that the `updated_at` field does this, but we must be sure.

Looking at nation_builder_sync.rb and tags.rb, I'll need to touch the sync from within tags.rb (and email.rb and person.rb and service_delivery.rb) and I'm not sure how.  After all of each of those withing nation_builder_sync.rb, sure.  But within them for each one...that is what I'm trying to figure out.


## Fri, Dec 10 2021

### overly long syncs
The In Progress label is misleading.  Once it is stale after 2 days,

Results from how to detect a stale overly long sync

A stale, overly long sync would be a sync that is still “In progress”.  At the moment, there are only four of these in our system, three are for the same promoter.  All were created before December 5.

NationBuilderSynchronizeCall.where(status: 'In progress')

During the nightly sync, when a promoter has stuff to sync, we detect if that promoter has any ongoing syncs less than 2 days old.  If so, we log that we are skipping their sync.  Ongoing syncs older than 2 days are ignored even if still in progress, meaning that a new sync is created for that promoter.

The next question is how shall we proceed?

### Dave's recommended Nationbuilder (syncing) improvements
Good example for how to do each step of syncing with NationBuilder, but pulling those steps out into their own file.  Here lib/tasks/etl/daily_all_advocate_etls_update.rake

### PR review of ON-1407, US cicero import
Dayum!! Spent from 11 to 1:30 on Dave's big PR review.  Made over 40 comments.  Some trivial, but many with questions based on my understanding of import and cicero.

**Yesterday I**
- looked through the NationBuilder syncs from the night before, confirming that things look good
- checked the new logs for NB sync tags; and I'm confused why tags aren't sent with every sync
- researched what are the business rules; when do we send tags?  Posted the answer in #engineering channel.
- paired with Alex to track down ideas for chasing down the tagging issue
- used those ideas to track the problem conversions from end to end
- wrote a long explanation of what I found and what didn't make sense in my findings and posted it to the engineering channel, flagging Dave and inviting others for possible explanations and better understanding

**This morning I**
- merged and deployed the sync cutoff change to 2 days
- created a Jira ticket to research how to detect a stale overly long sync, https://oneclickpolitics.atlassian.net/browse/ON-1478
- created Jira ticket to implement from the above research how to trigger an email or a restart of an overly long sync that needed to be cut off, https://oneclickpolitics.atlassian.net/browse/ON-1479

**Today I plan to:**
- [x] research how to detect a stale overly long sync; reported to Maged on my findings as well as updating the Jira ticket with the same; kinda waiting to hear how he wants to proceed
- [x] read through Dave's import instructions for US to see how it works/reads; the writeup is in this jira https://oneclickpolitics.atlassian.net/browse/ON-1407 the instructions are at the top, plus a ton of comments below tracking what he's doing.  It is also in the comments for the shape file rake task.
- [x] reviewed Dave's cicero US PR in detail; many comments but only because it was huge and I had some ideas based on domain knowledge of cicero and imports for different countries


## Thu, Dec 9 2021

### handy commands, aws
#### how to scp aws
```
 scp -i ~/.ssh/id_rsa ../../one-click-politics/docker/postgres/*CA.sql ubuntu@ec2-184-72-246-33.compute-1.amazonaws.com:~/canada/oct2021
```

### update for Maged on NationBuilder tags
I did some good pairing with Alex brainstorming additional ideas to track the “lack of tagging” issue for the client complaints in zendesk #1128.

Here are the questions I will work to answer to try to identify problems:

- email - Check how did we deliver for each conversion for that sender profile, (email/phone/etc)?  
- yes - Are they constituents?  If not, then conversion will not be created.
- no - Did the signer only fill out the first step of the widget and click to go to the next step but not do anything, thus not completing the widget.  If so, then would this create a conversion still?  I think no, but want to confirm.
- successfully sent - What about the recipient that has no way to be reached?  The presentation of our analytics would indicate that this succeeded (confirmed by Alex).  But NB would not, since only a successful conversion delivery sends a tag.
- uncertain answer; posted questions in #engineering channel - In lib/jobs/nation_builder_sync/nation_builder_sync.rb:L53-55 there is an ordering for NB syncs.  First are the email conversions, then tags, then service deliveries.  Service deliveries includes video, twitter, and phone.  Are there types of deliveries that are falling through the cracks, causing advocates to not get synced and therefore those advocates do not get tags?
- looks like this isn't the problem - What if a conversion has no associated advocate profile, conversion.advocate_profile.  This is accessed at the beginning of the sync.  The latest conversion I looked at on prod didn’t have one, so this is another thing to investigate.

**Yesterday I**
- merged and deployed the country_code fix and tests
- this morning I took a look at our admin syncs page and I'm seeing no failures and I am seeing successes, which concurs with the lack of emails; after this I'll check the new logs for NB sync tags
- created the Jira, checked in, and PR'ed the logging addition for NationBuilder tags
- wrote an email to business summarizing what we are sending to NB and asking if this is what they want to send or something different, or if they want different possible options (a new feature)
- created a Jira ticket for changing overly long NB sync cutoff from 4 to 2.
- changed cutoff to 2 and created the PR
- reviewed Nate's PR

not email = video, twitter, _facebook_, phone, _photo_
email = CWC, webform, email, fax, webmail, web address,

### Additional ideas for #1128 from Alex
- Check how did we deliver for each conversion for that sender profile, (email/phone/etc)?
- Are they reaching their recipients (are they constituents), because if not, then conversion will not be created.
- Did the signer only fill out the first step of the widget and click to go to the next step but not do anything, thus not completing the widget.  If so, then would this create a conversion still?  I think no, but want to confirm.
- What about the recipient has no way to be reached?  The presentation of our analytics would indicate that this succeeded.  But NB would not, since only a successful conversion sends a tag.
- In lib/jobs/nation_builder_sync/nation_builder_sync.rb:L53-55 there is an ordering for NB syncs.  First are the email conversions, then tags, then service deliveries.  Service deliveries includes video, twitter, and phone.  Are there types of deliveries that are falling through the cracks, causing advocates to not get synced and therefore those advocates do not get tags?

### current state of NationBuilder tagging
This is the situation I'm finding for a client seeing tagging issues that I am hoping you can shed some light upon.  The givens that I am working with are:

- Each campaign should have only one SenderProfile. This is not a limitation defined in the code, it just doesn't make sense to me to have a two different campaigns having the same sender profile.  If not, please help me understand why.
- Assuming that an email sync for a conversion succeeds (conversion.nation_builder_email_synced: true) and that it isn't unsyncable (conversion.nation_builder_unsyncable: false), then my understanding is that the tag sync should occur.

However, I'm seeing a couple things that don't make sense.  

First, I find the conversion that matches the given campaign name and sender profile:
```
conversion.promoted_message.internal_campaign_name = 'US S 2725 Online Firearms Marketplace Immunity Removal' (PromotedMessage 14441)
conversion.sender_id = 17943393 (SenderProfile.email = 'bkwittmeier@gmail.com')
```

I found this conversion, Conversion.id = 24772017

What I don't understand about this conversion is why it has:
  nation_builder_tag_synced: false
when these are:
  conversion.nation_builder_email_synced: true
  conversion.nation_builder_unsyncable: false

Another thing I don't understand is why SenderProfile.id = 17943393 has TWO different conversions (24771995 and 24772017).


PromoterUser: 39610, slug: afa, token: 013c160f46caf07d4b39b9a34efa1a988023b4898f3ef46241070a34f003c598

Confirmed with PromoterUser 39610/39517, PromotedMessage 14441, PromotedMessage.internal_campaign_name: '2021 - HR2377 - Nadler Red Flags - Email'  There are 2694 persons with this tag (GET /tags/:tag/people).

PromoterUser 25179,
PromotedMessage 14061, https://oneclickpolitics.com/promoter/25179/messages/14061/edit
AdvocateProfile 2711448
SenderProfile 4145052, 8673465, 8794569, 8860259, 8897350, 9324451, 11177338, <- ALL FROM 2020 OR EARLIER

17943393-24771995-"CI |Biden Budget AA | 10-13-21"
        -24772017-"US S 2725 Online Firearms Marketplace Immunity Removal" recipients-"20910:21286:21330"
reached_recipient_ids: "20910:21286:21330", redelivered: false, nation_builder_email_synced: true, nation_builder_tag_synced: false, nation_builder_unsyncable: false


18004668-24840197-"CI | Voter Fraud AA | 10-19-21"
18025479-24863443-"US H 5427 Bump Stock NFA"
18128153-24974218-"CI | House Judiciary Red Flags AA |10-25-21"
18131178-24977503-"CI | House Judiciary Red Flags AA |10-25-21"
Conversion
slug: firearmspolicycoalition, token: 986c90c22feceafba5b77844a4b7a0a8053acb35b6b01193462dd3686cf649aa
PromotedMessage.internal_campaign_name: 'US S 2725 Online Firearms Marketplace Immunity Removal'  There are 8877 persons with this tag.  
NB ID: 1711626, Brian K. Wittmeier, bkwittmeier@gmail.com, does not have this tag.
email

PromoterUser 25179,
PromotedMessage 14328, https://oneclickpolitics.com/promoter/25179/messages/14328/edit
slug: firearmspolicycoalition, token: 986c90c22feceafba5b77844a4b7a0a8053acb35b6b01193462dd3686cf649aa
PromotedMessage.internal_campaign_name: 'IL Ghost Gun Bans'  There are 0 persons with this tag.  
NB ID: 1561400, Adam Emery, aemery214@gmail.com, does (not???) have this tag.

PromoterUser 25179,
PromotedMessage 14328, https://oneclickpolitics.com/promoter/25179/messages/14328/edit
slug: firearmspolicycoalition, token: 986c90c22feceafba5b77844a4b7a0a8053acb35b6b01193462dd3686cf649aa
PromotedMessage.internal_campaign_name: 'IL Ghost Gun Bans'  There are 0 persons with this tag.  
NB ID: 1711700, Mike Murphy, murphy@ilhousegop.org, does (not???) have this tag.


**Today I plan to:**
- [x] confirm country_code fix deployed yesterday has corrected the undefined method error
- [x] check the new logs for NB sync tags
- [x] what are the business rules; when do we send tags?  Posted the answer in #engineering channel.
- [x] paired with Alex to track down ideas for chasing down the tagging issue
- [x] used those ideas to track the problem conversions from end to end
- [x] wrote a long explanation of what I found and what didn't make sense in my findings and posted it to the engineering channel, flagging Dave and inviting others for possible explanations and better understanding
- [ ] create Jira ticket to research how to detect a stale overly long sync
trigger an email or a restart of an overly long sync that needed to be cut off
- [ ] create Jira ticket to implement from the above research how to trigger an email or a restart of an overly long sync that needed to be cut off
- [ ] read through Dave's import instructions for US to see how it works/reads; the writeup is in this jira https://oneclickpolitics.atlassian.net/browse/ON-1407 the instructions are at the top, plus a ton of comments below tracking what he's doing.  It is also in the comments for the shape file rake task.


## Wed, Dec 8 2021
**Yesterday I**
- tracked down the undefined method error from the add_country_code method being triggered in the NB syncs by advocates with nil addresses...from petitions; added a check for nil addresses and made a change to not add a country code when the address is nil  (recap: the purpose of adding the country_code is so advocates will be re-districted as needed; however, when there is no address, there will be no districting or re-districting, and thus no country_code needed)  Maged is contacting the business to verify our NB syncing of advocates without addresses.
- created a test to trigger the above issue
- got the fix and the test added to the PR, https://github.com/one-click-politics/one-click-politics/pull/480
- sync'ed the advocates not affected by the above issue (which is the minority of the failures)
- results from the tagging investigation: we are not logging when we send a tag to NB; so when a client asks why a given signer doesn't have that tag in NB, we have no answers other than to confirm the tag is present or absent according to NB.  

This is the crux of the problem with zendesk ticket #1128.  I can confirm that it is the internal_campaign_name that is being sent as a tag for a signer.  

One signer does not have the expected tag and instead is only tagged as a new signer
Another signer's expected tag does not exist as a tag in NationBuilder

I have added some logging to the tags.rb file just before we send the tag off to NB that should help diagnose this further.  Need to create a Jira, check it in, and create a PR for this.

**Today I plan to:**
- [x] Get the country_code stuff merged.  Anyone else want to look and approve first?  ON-1470
- [x] create the Jira, check in, and PR the logging addition for NationBuilder tags, https://oneclickpolitics.atlassian.net/browse/ON-1476
- [x] write email to business summarizing what we are sending to NB and asking if this is what they want to send or something different, or different options (a new feature)
- [ ] read through Dave's import instructions for US to see how it works/reads; the writeup is in this jira https://oneclickpolitics.atlassian.net/browse/ON-1407 the instructions are at the top, plus a ton of comments below tracking what he's doing.  It is also in the comments for the shape file rake task.
- [x] research about the nightly jobs
  - I'm seeing roughly 50 +/- 25 syncs starting each evening at 6pm eastern.
  - the failures are being timed out by NationBuilder
- [x] create Jira ticket to change overly long NB sync cutoff from 4 to 2.
- [x] change cutoff to 2, create PR
- [ ] create Jira ticket to research how to trigger an email or a restart of an overly long sync that needed to be cut off
- [ ] create Jira ticket to implement from the above research how to trigger an email or a restart of an overly long sync that needed to be cut off
- [x] PR review Nate, https://github.com/one-click-politics/one-click-politics/pull/481

### sync research in admin pages
admin pages have a syncs status page for NB and Neon.  All scheduled tasks have these.  There is a check to terminate a sync that takes more than x (4?) days. <- change this to terminate after 48 hours
nationbuilder_unsyncable (makes an external connection call (polymorphic join; ==)

Also, https://oneclickpolitics.com/admin/synchronize_calls/ is a great place to look for failed and succeeded syncs and for any other rake task!!!

### tagging info
From Dave: if no external connection record joined to that advocate, then no sync will occur for tags
This will change nationbuilder_unsyncable to true

### how to research tagging problems
To research tagging problems, in lib/jobs/nation_builder_sync/lib/tags.rb:L57-59 in `def get_conversions_for_tag_sync`
- check the external_connections for an advocate profile to verify existence of the NB id, if it is missing, then that is why the advocate was not tagged.
- check that conversions.nation_builder_unsyncable is false; if it is true, then that is why the advocate was not tagged.

### 7 NationBuilder failures from last night, 7 Dec
Great page for checking failure/success for syncs by promoter, https://oneclickpolitics.com/admin/synchronize_calls
```
7 Dec
39387, 39520, 39524, 39169, 39529   <- BUG with country_code

7225    <- lack of authentication failure
20176   <- normal failure, this was resynced yesterday, 6 Dec
```

I'm seeing roughly 50 +/- 25 syncs starting each evening at 6pm eastern.

### NationBuilder sync failure for PromoterUser 7225
This user has failed to sync due to a lack of authentication.  Dave mentioned that it could be this promoter is slipping through the cracks of `def self.get_promoters` in lib/jobs/nation_builder_sync/nation_builder_sync.rb.  Making a note here since the priority of this is very low compared to other issues


## Tue, Dec 7 2021
**Yesterday I**
- reviewed two small PRs
- rubocop'ed the files I had worked on for country code and reduced the offenses from 292 to 73
- got the country code tests checked in and PR'ed
- KnowWho import ran into troubles downloading and unzipping the state file, so I turned to Nate who got the files downloaded, unzipped, and checked in for me; after that, the import was completed successfully
- I working my way through re-syncing the failed syncs
- I went through the new NB syncing logs.  The good news is that I am seeing many succeeded syncs, but there have been a block of failures every day since Friday.  There are two main reasons the syncs are failing; the usual too many files are open error (this is its own concern, but is a know issue) and a new undefined method error that looks to be introduced with the country_code change but not caught with the new tests

**Today I plan to:**
- [x] investigate the new undefined method error in the NB syncs
- [x] continue re-syncing one by one (in the background while doing other things)  I've put together a list
- [ ] I'd like to read through Dave's import instructions for US to see how it works/reads; is this the writeup I saw in this jira?  https://oneclickpolitics.atlassian.net/browse/ON-1407
- [x] tagging

### current state of NationBuilder tagging
Found where and what we send to NationBuilder's /people/:id/taggings

In lib/jobs/nation_builder_sync/lib/tags.rb:L43
```
conversion.promoted_message.internal_campaign_name
```
PromoterUser: 39610, slug: afa, token: 013c160f46caf07d4b39b9a34efa1a988023b4898f3ef46241070a34f003c598

Confirmed with PromoterUser 39610/39517, PromotedMessage 14441, PromotedMessage.internal_campaign_name: '2021 - HR2377 - Nadler Red Flags - Email'  There are 2694 persons with this tag (GET /tags/:tag/people).

PromoterUser 25179, slug: firearmspolicycoalition, token: 986c90c22feceafba5b77844a4b7a0a8053acb35b6b01193462dd3686cf649aa
PromotedMessage 14061, PromotedMessage.internal_campaign_name: 'US S 2725 Online Firearms Marketplace Immunity Removal'  There are 8877 persons with this tag.  NB ID: 1711626, Brian K. Wittmeier, does not have this tag.

PromoterUser 25179, slug: firearmspolicycoalition, token: 986c90c22feceafba5b77844a4b7a0a8053acb35b6b01193462dd3686cf649aa
PromotedMessage 14328, PromotedMessage.internal_campaign_name: 'IL Ghost Gun Bans'  There are 0 persons with this tag.  NB ID: 1561400, Adam Emery, does (not???) have this tag.

PromoterUser 25179, slug: firearmspolicycoalition, token: 986c90c22feceafba5b77844a4b7a0a8053acb35b6b01193462dd3686cf649aa
PromotedMessage 14328, PromotedMessage.internal_campaign_name: 'IL Ghost Gun Bans'  There are 0 persons with this tag.  NB ID: 1711700, Mike Murphy, does (not???) have this tag.


## Mon, Dec 6 2021
**Friday I**
- changed the faxage creds on prod and bounced the agents; fix confirmed by a flood faxage success emails
- reviewed Sham's PR for the advocate details endpoint
- PR'ed, merged, and deployed the NB sync logging addition to prod
- got tests working for all three new country code related methods.  finished all tests for the first two (checked in).  now that the US example is working for the third method, I'll be finishing the tests for CA & AU in the next hour.  
- also been running rubocop on the files I'm touching and making improvements, which are complete, but need to be checked in.  Rubocop has a lot to say, so I'll be leaving things much better, but not perfect  (try with -A)

**Today I plan to:**
- [x] KnowWho Import (already downloaded)
- [x] as mentioned above, wrapping up the last of the country code tests now that all is working.  The big challenge from last week was getting the fixtures working the way I needed them as well as adding a method to the advocate profile model to make the country code more accessible
- [x] AFTER DEPLOY - I noticed that a number of syncs failed during the nightly cron jobs on Friday/Sat/Sun nights.  I plan to re-run these in the background while I do other work today, unless you feel they should be investigated further; I did notice that Saturday evening's sync triggered an AWS ALARM: "volume read high
- [x] I also plan to look at the logs in hopes to see some patterns from the NB sync logging I added on Friday
- [x] I hope to get to some PR reviewing as well

### KnowWho import
So, the import took a turn for the problematic when I could not download a state file that would unzip.  After fighting with this for 15 or 20 mins, I turned to Nate who got it downloaded, unzipped, and checked in.  Wacky.  Never had problems before.

### failed NB syncs from weekend
Total of 29 failures (15 are duplicates)
```
7 Dec
39387, 39520, 39524, 39169, 39529 <- BUG with country_code
7225 <- lack of authentication failure
20176 <- normal failure, this was resynced yesterday, 6 Dec

6 Dec (, 7 failed)
d 39169 see below        BUG with country_code
d 7225  see below     failing due to a lack of authentication; cannot sync
d 20176 see below     resynced on 12/6
d 39387 see below        BUG with country_code
d 37990 see below     resynced on 12/7
d 39524 see below        BUG with country_code
d 39529 see below        BUG with country_code

5 Dec (78 syncs initiated, 11 failed)   106-183 = 1-78
d 7725        failing due to a lack of authentication; cannot sync
20176     success 12/2, 12/3;     failure 12/5;      resynced on 12/6 with success
d 39387       PromoterUser.find(user).master_account.authentications looks good, but this fails every time with the error: Caused by: OAuth2::Error: : {"code":"not_found","message":"Record not found"}
d 37990   success 12/3;           failure 12/2, 12/5, 12/6;     resynced on 12/7
d 37916   success 12/6;           failure 12/2, 12/3, 12/5;     no resync needed
d 39522   success 12/3, 12/6;     failure 12/2, 12/5;           no resync needed
d 39520   success 12/6;           failure 12/2, 12/3, 12/5;     no resync needed
d 39524   success 12/2, 12/3, 12/6;   failure 12/5;             no resync needed
d 25179   success 12/2, 12/3, 12/4, 12/6;   failure 12/5;       no resync needed
d 39169   success 12/1            failure 12/2 - 12/6         BUG with country_code
d 39529   success 12/2            failure 12/3 - 12/6         BUG with country_code

4 Dec (26 syncs initiated, 2 failed) 80-105
d 39169        BUG with country_code
d 39529        BUG with country_code

3 Dec (79 syncs initiated, 7 failed)  1-79
d 7225 <- WHY DIDN'T THIS KICK OFF ON 4 DEC?
d 39387 <- WHY DIDN'T THIS KICK OFF ON 4 DEC?
d 37916 <- WHY DIDN'T THIS KICK OFF ON 4 DEC?
d 39520 <- WHY DIDN'T THIS KICK OFF ON 4 DEC?
39524 <- WHY DIDN'T THIS KICK OFF ON 4 DEC?       
d 39169        BUG with country_code
39529        BUG with country_code

2 Dec (not stats yet because no logs yet; new logging deployed 3 Dec)
7225
39387
37990
37916
40601
39522
39520
39169        BUG with country_code
25179

user = 39522
PromoterUser.find(user).master_account.authentications
PromoterUser.where(agency_id: user)
NationBuilderSynchronizeCall.where(promoter_user_id: user).where("created_at > ?", 7.days.ago)


exit
RAILS_ENV=production bundle exec rake nation_builder_sync:sync_one[] &
bundle exec rake nation_builder_sync:sync_one[
] RAILS_ENV=production
```


## Fri, Dec 3 2021
### NationBuilder tagging
Found where and what we send to NationBuilder's /people/:id/taggings

In lib/jobs/nation_builder_sync/lib/tags.rb:L43
```
conversion.promoted_message.internal_campaign_name
```

**Yesterday I**
- determined we do have a cron job to sync with NationBuilder daily at 23:00 UTC, 6pm EST
- discovered that we are only logging NB sync failures, so there is no way to track what syncs are started
- responded to country code PR reviews
- merged country code PR
- deployed country code PR
- created a Jira for the country code test work plus the logging additions for NB syncs
- added logging for when a NationBuilder sync starts, since right now all we get are the failures, so it is hard to track what Is happening with syncs
- tried to chase down a test in NB sync that has been failing for over half a year, to no avail.  Made a TODO comment in the code for assistance when I PR this work

**Today I plan to:**
- [ ] put back the non-working tests I have for country code, then reach out for assistance with rspec and testing once I get blocked...should be before lunch, though I have some ideas after my conversation with Maged.
- [ ] tags: go back to the code to verify what we are sending when we PUT to NB's /people/:id/taggings
- [ ] I'd like to PR and deploy the sync logging this morning, Maged.  I want the data from tonight and this weekend's NB syncs to analyze on Monday.
- [ ] re-sync failed syncs from last evening


syncing with NationBuilder; the crontabs are set to run daily.  I'm not seeing the number of failures I would expect in the logs.  I'm also not seeing syncing on the daily basis that I expect.  



## Thu, Dec 2 2021
- make tests for country code
- add logging for sync start
- tags
- syncing with NationBuilder; the crontabs are set to run daily.  I'm not seeing the number of failures I would expect in the logs.  I'm also not seeing syncing on the daily basis that I expect.


**Yesterday I**
- reviewed PRs
- checked in country code work and created PR

**Today I plan to**
- [x] respond to country code PR reviews
- [x] merge country code PR
- [x] deploy country code PR
- [ ] tags: go back to the code to verify what we are sending when we PUT to NB's /people/:id/taggings


## Wed, Dec 1 2021
- re-sync'ed for ticket 1128
- added updates to ticket 1128 with my findings:
  - sync dates and success/fail for November
  - NB data for the advocates being asked about
  - lack of expected tags found on those advocates
  - confusion about the combined data the client provided for two different advocates presented as a single advocate

- [ ] need to continue in the code to determine exactly what we are sending to NB when we create tags.  I though I knew what we are sending, but seeing what data NB has, I am doubting my findings.
- [ ] writeup tags we are sending to NB vs the ones being asked for <- what I'm seeing on NB does not correspond to what I though we were sending; this is why I'm going back to the code to verify
- [ ] finish country code work <- URGENT!!!  finish this as soon as possible
- [ ] PR country code work
- [ ] post in dev channel when country code work PR is ready
- [ ] how often are we supposed to be syncing with NationBuilder
- [ ] investigate crontabs on prod to figure out how ofter we are running the NB syncs


## Tue, Nov 30 2021
- [x] re-sync 1128
```
"success", action: "428 AdvocateProfiles - 0 Recipients - 1556 Emails -...", updated_at: "2021-11-06
"failure", action: "165 AdvocateProfiles - 0 Recipients - 527 Emails - ...", updated_at: "2021-11-16 "success", action: "594 AdvocateProfiles - 79 Recipients - 2251 Emails ...", updated_at: "2021-11-17 "failure", action: "430 AdvocateProfiles - 91 Recipients - 1962 Emails ...", updated_at: "2021-11-19 "success", action: "143 AdvocateProfiles - 0 Recipients - 688 Emails - ...", updated_at: "2021-11-22 "success", action: "15 AdvocateProfiles - 0 Recipients - 101 Emails - 0...", updated_at: "2021-11-25
```
slug = firearmspolicycoalition
api key = 986c90c22feceafba5b77844a4b7a0a8053acb35b6b01193462dd3686cf649aa
firearmspolicycoalition.nationbuilder.com/api/v1/people/1711626?access_token=986c90c22feceafba5b77844a4b7a0a8053acb35b6b01193462dd3686cf649aa

- 1711626         "updated_at": "2021-11-16T21:42",
        "id": 1711626,
        "first_name": "Brian",
        "last_name": "K. Wittmeier",
        "email": "bkwittmeier@gmail.com",
            "address1": "78 Hoot Owl Rd",
            "city": "New Castle",
            "state": "VA",
            "zip": "24127",
        "tags": [
            "new_person"
        ],
- 1561400         "updated_at": "2021-11-04T10:38",
        "id": 1561400,
        "last_name": "Emery",
        "first_name": "Adam",
        "email": "aemery214@gmail.com",
            "address1": null,
            "city": "Chatham",
            "state": "IL",
            "country_code": "US",
            "zip": "62629",
        "tags": [
            "Active National",
            "ActiveNonCA",
            "HR1207_AD",
            "Executive Actions",
            "Biden",
            "unconstitutional",
            "FB AD",
            "David Chipman ATF Nomination",
            "Took Action 2021",
            "i360 append 1001",
            "ta_ana_1104"
        ],
- 1711700         "updated_at": "2021-11-19T15:33",
        "id": 1711700,
        "first_name": "Mike",
        "last_name": "Murphy",
        "email": "murphy@ilhousegop.org",
            "address1": null,
            "city": "Springfield",
            "state": "IL",
            "country_code": "US",
            "zip": "62706",
        "tags": [],



- writeup tags we are sending to NB vs the ones being asked for
- finish country code work
- PR country code work
- post in dev channel when country code work PR is ready

**Monday I**
- reviewed PRs
- did the KnowWho import
- wrote the tests for the lat/long fix
- wrote up the Jira ticket for the lat/long fix
- got the PR ready for the lat/long fix once the tests are ready

**Today I plan to**
- [ ] confirm that the AdvocateProfile is the info sent to NationBuilder, not SenderProfile
- [ ] email business about the lat/long fix coming out
- [ ] review Dave's PR
- [ ] follow up when I receive responses to my PR
- [ ] get back to the tags work (NB zendesk ticket 1128);

can we sent other fields as the tags.  possibly creating a drop down for this.  possibly adding column in the database to track which types of tags we are setting.  is this something customizable in NB or in our stuff.


## Mon, Nov 29 2021
**Wednesday I**
- reviewed a pair of PRs
- learned about NationBuilder tags for the customer doesn't like what we are sending
- mostly figured out where in the code we are setting the tags

**Today I plan to**
- [ ] review PRs
- [ ] KnowWho import
- [ ] write the tests for the lat/long fix
- [ ] write up the Jira ticket for the lat/long fix
- [ ] get the PR ready for the lat/long fix once the tests are ready
- [ ] learn what is the difference between SenderProfile and AdvocateProfile

can we sent other fields as the tags.  possibly creating a drop down for this.  possibly adding column in the database to track which types of tags we are setting.  is this something customizable in NB or in our stuff.


## Wed, Nov 24 2021
**Yesterday I**
- reviewed Hager's PR; congratulations!
- emailed NB with slug of lat/long client (ZD 1012) & updated ticket
- NB responded saying that omiting the lat/long will have no repercussions
- spent much of the rest of the day deep in NationBuilder code and their API docs, learning what we are sending them, what we can retrieve from them and how, and making example calls to see what they are giving to the client who has complaints.  so far, I've exactly reproduced what the customer is getting back from NB, but I'm still working on understanding the tags we are sending and why the customer doesn't like what we are sending
- largely done with the coding on the lat/long fix

**Today I plan to**
- [ ] reviewing a pair of PRs
- [ ] write the tests for the lat/long fix
- [ ] write up the Jira ticket for the lat/long fix
- [ ] get the PR ready for the lat/long fix once the tests are ready
- [ ] working on understanding the tags we are sending and why the customer doesn't like what we are sending


## Tue, Nov 23 2021
### Rubocop
```
bundle exec rubocop lib/
bundle exec rubocop lib/nation_builder_client/
```

### NationBuilder
:create_tag
:create_person
:push_person
:update_person
:contact_builder

ticket #1128
```
Brian K. Wittmeier
78 Hoot Owl Rd, NULL, New Castle, VA 24127
bkwittmeier@gmail.com
NB ID: 1711626
- Synced 2 days ago: Contacted Senators Kaine and Warner, and Rep. Griffith with "Vote Against US S 2725" which should have tagged him with "US S 2725 Online Firearms Marketplace Immunity Removal." Instead, he's just marked as a new person in our nation.
```
email_subject in step 2 of widget: `Vote Against US S 2725`  <----this is the /people/:id/capitals['content']['note'] returned by NB for NB id 1711626 for three signatures on 16 Nov.
campaign name (internal): `US S 2725 Online Firearms Marketplace Immunity Removal`

```
Mike Murphy
Springfield, IL 62629
aemery214@gmail.com
NB ID: 1561400
- Synced 23 Hours Ago (profile first created in NB 6 months ago): Contacted IL Sen Steve McClure and IL Rep Mike Murphy about "OPPOSE Illinois "Ghost Gun" Ban!" and should have been tagged with "IL Ghost Gun Bans."
```
email_subject in step 2 of widget: `OPPOSE Illinois "Ghost Gun" Ban!`  <---this is the /people/:id/capitals['content']['note'] that returned by NB for NB id 1561400 for two signatures on 17 Nov.
campaign name (internal): `IL Ghost Gun Bans`

**Yesterday I**
- met with Hager and Dave for a good long knowledge share, particularly on Districts
- reviewed a couple quick PRs
- did the KnowWho import
- looked through the NationBuilder sync code to be ready to make the lat/long change once we get confirmation back from NB that won't have repercussions, share the slug for that client
- sent an email with an update on all the NB issues to Darren and Dominique

**Today I plan to**
- [x] reviewing Hager's PR on modifying the NewDistrict temporary table; I'm almost done with this
- [ ] this ticket came back again, https://oneclickpolitics.zendesk.com/agent/tickets/1128,  Re-sync performed successfully on 22 Nov.  The ticket was updated with a new issue that the Tags that NB send are not correct.  This is into a level of NationBuilder that I do not know yet, so this will take some time investment to understand.  Perhaps Dave or Nate have a starting point for me on this as it seems beyond simple re-syncing and into the realm of challenging the validity of the date being received from NB.  Follow up with Darren to make sure I know what he's looking for on this one.
- [ ] if I get the NB response, I'll continue with NB zendesk ticket 1012 and remove lat/long from what we send to NB.  slug = 'mnrtl'  Also, the client's `PromoterUser.find(39902).master_account.authentications` shows a `write_access: false`.  I sent another email to NB this morning with the slug of the client and cc'ed Maged.  
- [ ] continue to be available for any knowledge sharing on import that Hager needs
- [ ] set up the basics for the new API
- [ ] let Maged know as soon as I have the new API basics put together as he has the next task waiting


## Mon, Nov 22 2021
**Friday I**
- reviewed Nate's twitter PR pretty carefully since it is a familiar area for me; also checked things out on staging and asked a few questions to confirm functionality
- fixed several failing specs that had been broken by cicero code requirements in the UI from the list Dave provided in ON-1424, https://github.com/one-click-politics/one-click-politics/pull/449, reviewed and merged
- fixed several more failing specs triggered by cwc handler changes and widget UI changes, https://github.com/one-click-politics/one-click-politics/pull/450, ready for review
- NationBuilder zendesk ticket 1106 updated.  These campaigns have been retired since 25 October, so have no activity since then.  Retired widgets do not permit signing and instead display a message that "This campaign has ended and is no longer taking action."
- all other NB zendesk tickets (except one) regarding sync issues have been re-synced and updated with details (this happened Thursday)
- for the final NationBuilder zendesk ticket 1012, https://oneclickpolitics.zendesk.com/agent/tickets/1012, email sent asking for confirmation that removing latitude/longitude from what we send them won't have repercussions
- same ticket, looking into where to remove lat/long from what we send them; L826-7 in spec/libs/nation_builder_sync/people_spec.rb tests this, I think
- create Jira for this work once confirmation is received (or maybe sooner to track the effort in research?)

**Today I plan to**
- [ ] this ticket came back again, https://oneclickpolitics.zendesk.com/agent/tickets/1128, this time it looks like the Tags that NB send are not correct.  This is into a level of NationBuilder that I do not know yet, so this will take some time investment to understand.  Perhaps Dave or Nate have a starting point for me on this as it seems beyond simple re-syncing and into the realm of challenging the validity of the date being received from NB.
- [ ] continue with NB zendesk ticket 1012, looking for where to remove lat/long from what we send to NB (and watch for the email response from NB on the potential repercussions for removing lat/long)
- [ ] continue to be available for any knowledge sharing on import that Hager needs
- [ ] set up the basics for the new API
  - docker
  - ElasticSearch
  - set up the repo
  - Deploy checklist
  - Logrotate
  - SSL
  - Nginx Config
  - install rails 6 locally
  - then do `rails new swtichboard --api-only `
  - then copy over  the dockerfile, dockercompose .env-rc .env-rc.secrets files and configure them for what you need
  - from there you should be able to docker up confirm it runs locally
  - ssh into wherever it's going.. probably a new ec2 at that point
  - clone the repo. look at the .prod_deploy.sh scripts i have on Micro.
  - make one for there.
  - then setup the nginx using micro as an example as well
  - SSl, https://certbot.eff.org/instructions?ws=nginx&os=ubuntu-20
  - logrotate, https://gorails.com/guides/rotating-rails-production-logs-with-logrotate
  - Keep your log files in check as time goes on and make sure they don't fill up your server's disk space


## Fri, Nov 19 2021

#### zendesk ticket 1012, Data sync to NB Promoter ID 39902
- start looking at code for where we send stuff to NB in order to prepare for the lat/long removal from what we send
##### draft of email to nation builder
bpalmer@nationbuilder.com

Brian

Warm regards,
I am Susan with OneClickPolitics.  We have a client that has been troubleshooting issues with one of your folks.  They were told that when we, OCP, send data over for people that include latitude/longitude, auto-redistricting does not occur.  Our client would like us to only send the raw address and no longer send latitude/longitude as well.  I am writing to confirm that omitting the latitude/longitude won't have other possible repercussions.  
Thank you for your time,
Susan Prestage
OneClickPolitics

Darren requests:
```
We noticed that people’s records were not being automatically placed into the correct voting district. Nation Builder, as I understand it, says the issue stems from the way the information is coming over from OCP. The addresses for people are being overridden by their latitude/longitude location. Is it possible for the addresses to be pulled through in a raw form instead of including the lat/long?

We need people’s records to be auto-districted since we send out our email alerts often based on their legislative district.
```
we are being asked if it is possible for a senders address to be send to the NB database instead of the lat/long that we are currently sending, https://oneclickpolitics.zendesk.com/agent/tickets/1012 Maged says yes, this is a BUG, research to confirm first, go into NB libs and remove that bit.  I should contact NB directly to confirm that this change won't break anything else...I'll send the initial email

**Yesterday I**
- did a quick and thorough info share with Alex on new APIs, then tucked away the info to bring back out when I get past the higher priority items 👍
- met with Hager and we walked through the key files for existing cicero import, including the specs and particular tests that I found useful for end-to-end import
- discovered that Slack video conference individual window share does not permit the draw tool
- investigated each of the NationBuilderSynchronizeCall catastrophic failures that have come through email this last three weeks

**Summary of NationBuilder syncs**
  - there have been occasional failures, particularly for big promoters
  - in all cases of failed syncs, re-running the sync succeeded (or succeeded the second time in a single case)

nationbuilder logged erros file in the log folder: nb syncs are on that other, pre-prod.oneclickpolitics.com box for the NB sync logs

**A possible NationBuilder syncing bug???**
  - I have noticed an interesting and possibly concerning thing about the NationBuilder syncs.  It is interesting that a failed sync still shows numbers for `:action`.  These numbers are also not seen as a part of the next succeeded sync...which begs the question of just how this was a `failed` sync?  The reason I say that the numbers are not seen as a part of the next succeeded sync is that I saw a failed sync with higher numbers followed by a successful sync with lower numbers.  I can dig this proof up again if needed.

  What are the parameters on what data we get from NationBuilder?  Do we tell them the cutoff date for the numbers, so the next call starts from there?  If so, how does a failed sync affect this "bookmark"?  My concern is that we are losing our "place" and thus are losing numbers in our totals over time.

  ```
  irb(main):037:0> foo.action
  => "160 AdvocateProfiles - 28 Recipients - 3326 Emails - 0 ServiceDeliveries - 0 Tags"
  ```

**Today I plan to**
- [ ] set up the basics for the new API
  - docker
  - ElasticSearch
  - set up the repo
  - Deploy checklist
  - Logrotate
  - SSL
  - Nginx Config
  - install rails 6 locally
  - then do `rails new swtichboard --api-only `
  - then copy over  the dockerfile, dockercompose .env-rc .env-rc.secrets files and configure them for what you need
  - from there you should be able to docker up confirm it runs locally
  - ssh into wherever it's going.. probably a new ec2 at that point
  - clone the repo. look at the .prod_deploy.sh scripts i have on Micro.
  - make one for there.
  - then setup the nginx using micro as an example as well
  - SSl, https://certbot.eff.org/instructions?ws=nginx&os=ubuntu-20
  - logrotate, https://gorails.com/guides/rotating-rails-production-logs-with-logrotate
  - Keep your log files in check as time goes on and make sure they don't fill up your server's disk space
3169


## Thu, Nov 18 2021
### NationBuilder

#### zendesk ticket 1106, NB sync for Promotor ID 40592
**Update** The most recent conversions are from October, so NB returning zeros is correct.  If the client could give us a link to the page hosting the widget, this issue can be investigated further.  **Need to update the zendesk ticket with this info** -Susan, 6pm Thu

Tried this with Fastly and this is what was seen for both campaigns, which is likely due to their being Retired.:
```
Send Your Comments to DEQ
This campaign has ended and is no longer taking action.
```

**Next step**
Look for activity on prod, since there are all zeros with NationBuilder  

https://oneclickpolitics.zendesk.com/agent/tickets/1106

**Initial assessment**
In the last 7 days, I saw one sync, which was from today, and it had succeeded.  However, when I look at the actions returned from NationBuilder, it shows "0 AdvocateProfiles - 0 Recipients - 0 Emails - 0 ServiceDeliveries - 0 Tags".

PromoterUser 40592 has no active campaigns on our site, https://oneclickpolitics.com/promoter/40592/messages.  The two campaigns listed below, Oregon DEQ Unique Comment (14157) & Oregon DEQ Comment (14132), have been marked as Retired since 25 October, 2021.

#### zendesk ticket 1012, Data sync to NB Promoter ID 39902
- start looking at code for where we send stuff to NB in order to prepare for the lat/long removal from what we send

##### draft of email to nation builder
Good morning,
I am Susan with OneClickPolitics.  We have a client that has been troubleshooting issues with one of your folks.  They were told that when we, OCP, send data over for people that include latitude/longitude, auto-redistricting does not occur.  Our client would like us to only send the raw address and no longer send latitude/longitude as well.  I am writing to confirm that omitting the latitude/longitude won't have other possible repercussions.  
Thank you for your time,
Susan Prestage
OneClickPolitics

Darren requests:
```
We noticed that people’s records were not being automatically placed into the correct voting district. Nation Builder, as I understand it, says the issue stems from the way the information is coming over from OCP. The addresses for people are being overridden by their latitude/longitude location. Is it possible for the addresses to be pulled through in a raw form instead of including the lat/long?

We need people’s records to be auto-districted since we send out our email alerts often based on their legislative district.
```
we are being asked if it is possible for a senders address to be send to the NB database instead of the lat/long that we are currently sending, https://oneclickpolitics.zendesk.com/agent/tickets/1012 Maged says yes, this is a BUG, research to confirm first, go into NB libs and remove that bit.  I should contact NB directly to confirm that this change won't break anything else...I'll send the initial email

#### data on promoters that had catastrophic failures in email

##### 16 November
- 39522 & 39520 only run once a week.  They failed on the on 16 November.  **They were manually rerun on 18 November, both succeeded.**
- 25179 ran on 16 Nov when it failed.  It reran automatically on 17 Nov, successfully.  **No rerun needed.**
- 39169 ran on the 17, 15, 12, & 11 of November.  On the 17th, it failed.  **Manually rerun on 18 November.  The first run failed, which is common for this promoter.  Second time succeeded.**

##### 30 October
- 37916 ran on 17 November but hasn't run since 29 and 31 October otherwise.  It is unclear why this is the case.  Both syncs from October failed.  The 17 Nov sync succeeded.  **No rerun needed.**  

```
<NationBuilderSynchronizeCall id: 293654, promoter_user_id: 37916, status: "failure", action: "160 AdvocateProfiles - 28 Recipients - 3326 Emails ...", model_type: "NationBuilderSynchronizeCall", service_type: nil, created_at: "2021-10-29 00:48:47", updated_at: "2021-10-29 01:02:50", extra_data: nil, log: nil, start_id: nil, end_id: nil, table_name: nil>
```

- 39523, the 17 Nov sync succeeded.  **No rerun needed.**  
```
17 Nov, success
7 Nov, In progress
3 Nov, success
31 Oct, failure
29 Oct, success
```

- 39610, the 17 Nov sync succeeded.  **No rerun needed.**  
```
17 Nov, success
7 Nov, success
3 Nov, success
31 Oct, failure
29 Oct, success
```

- 39171, 13, 14, 15, 16, 17 Nov sync succeeded.  **No rerun needed.**

#### POSSIBLE ISSUE WITH NATIONBUILDER
I find it interesting that a failed sync still shows numbers for `:action`.  These numbers are also not seen as a part of the next succeeded sync...which begs the question of just how this was a `failed` sync?  The reason I say that the numbers are not seen as a part of the next succeeded sync is that I saw a failed sync with higher numbers followed by a successful sync with lower numbers.  I can dig this proof up again if needed.

What are the parameters on what data we get from NationBuilder?  Do we tell them the cutoff date for the numbers, so the next call starts from there?  If so, how does a failed sync affect this "bookmark"?  My concern is that we are losing our "place" and thus are losing numbers in our totals over time.


#### checking NB syncs
How to sync with NationBuilder aka NB sync
```
ssh_prod
cd /home/deploy/apps/ocp/current/
bundle exec rails c production

user = 39522
PromoterUser.find(user).master_account.authentications
PromoterUser.where(agency_id: user)
NationBuilderSynchronizeCall.where(promoter_user_id: user).where("created_at > ?", 7.days.ago)


exit
bundle exec rake nation_builder_sync:sync_one[39522] RAILS_ENV=production
```

**Yesterday I**
- [ ] resolved three NationBuilder issues and am working on the remaining two

**Today I plan to**
- [ ] continue to be available for any knowledge sharing on import that Hager needs
- [ ] set up the basics for the new API
  - docker
  - ElasticSearch
  - set up the repo
  - Deploy checklist
  - Logrotate
  - SSL
  - Nginx Config
  - install rails 6 locally
  - then do `rails new swtichboard --api-only `
  - then copy over  the dockerfile, dockercompose .env-rc .env-rc.secrets files and configure them for what you need
  - from there you should be able to docker up confirm it runs locally
  - ssh into wherever it's going.. probably a new ec2 at that point
  - clone the repo. look at the .prod_deploy.sh scripts i have on Micro.
  - make one for there.
  - then setup the nginx using micro as an example as well
  - SSl, https://certbot.eff.org/instructions?ws=nginx&os=ubuntu-20
  - logrotate, https://gorails.com/guides/rotating-rails-production-logs-with-logrotate
  - Keep your log files in check as time goes on and make sure they don't fill up your server's disk space
- [ ] look to see what NB jobs have failed...emails have been coming through on this
39169

### NationBuilder

#### sync catastrophic failures
- 16 November  39522, 39520, 25179, 39169
- 6 November  39169
- 30 October  37916, 39523, 39610, 39169
- 28 October  37916, 39522, 39171, 39169
- 19 October  37990, 39169
- 15 October  39703, 20176, 39169
- 14 October  39169
- 1 October  25179

Next step here is to look up these PromoterUsers and see
```
user = 39522
PromoterUser.find(user).master_account.authentications
```

possible need to look for the sub-promoters for an agency
```
PromoterUser.where(agency_id: user)
```

then check for last NB syncs for the last 7 days
```
NationBuilderSynchronizeCall.where(promoter_user_id: user).where("created_at > ?", 7.days.ago)
```

When a new sync is needed, this is how to run:
```
bundle exec rake nation_builder_sync:sync_one[39523] RAILS_ENV=production
```

#### zendesk tickets - in progress (2)
- #1106 NB sync for Promotor ID 40592, https://oneclickpolitics.zendesk.com/agent/tickets/1106
In the last 7 days, I saw one sync, which was from today, and it had succeeded.  However, when I look at the actions returned from NationBuilder, it shows "0 AdvocateProfiles - 0 Recipients - 0 Emails - 0 ServiceDeliveries - 0 Tags".

PromoterUser 40592 has no active campaigns on our site, https://oneclickpolitics.com/promoter/40592/messages.  The two campaigns listed below, Oregon DEQ Unique Comment & Oregon DEQ Comment, have been marked as Retired since 25 October, 2021.

- #1012 Data sync to NB Promoter ID 39902
Darren requests:

```
We noticed that people’s records were not being automatically placed into the correct voting district. Nation Builder, as I understand it, says the issue stems from the way the information is coming over from OCP. The addresses for people are being overridden by their latitude/longitude location. Is it possible for the addresses to be pulled through in a raw form instead of including the lat/long?

We need people’s records to be auto-districted since we send out our email alerts often based on their legislative district.
```

we are being asked if it is possible for a senders address to be send to the NB database instead of the lat/long that we are currently sending, https://oneclickpolitics.zendesk.com/agent/tickets/1012 Maged says yes, this is a BUG, research to confirm first, go into NB libs and remove that bit.  I should contact NB directly to confirm that this change won't break anything else...I'll send the initial email

#### zendesk tickets - resolved (3)
- #1130 URGENT NB sync issue for Promoter ID 39610/ Slug afa, https://oneclickpolitics.zendesk.com/agent/tickets/1130  **Resolved and updated 3 November**  Darren updated saying thanks and he'll update if anything changes
- #1128 NB not syncing  Promoter ID 25179, https://oneclickpolitics.zendesk.com/agent/tickets/1128  **Resolved and updated 17 November**  "In the last 7 days, I saw one sync but it had failed.  The slug looked good, so I kicked off another sync, which succeeded.  All looks good and up to date at this moment.  -S"
- #1095 Login w/ NB issue, https://oneclickpolitics.zendesk.com/agent/tickets/1095  **Resolved and updated 17 November**  I see a new campaign created on 3 Nov, 2021, which means the promoter is successfully logging into the system.  Though perhaps not through the NB portal as they would prefer.

The one oddity I noticed is that the client is typing in 'acceaction' as their slug.  Most promoters have slugs that are all lower case, however, this one is in our database with the slug 'ACCEACTION'.  I would recommend the client try the change to a fully capitalized slug.  The video helped diagnose this issue, thank you.  -S


## Wed, Nov 17 2021
**Yesterday I**
- created tickets for the first tasks of the API
- started looking throught the pile of NationBuilder tickets
- injured cat update; caught her too late in the day for any vet availablility, but she is contained and I'm taking her to the vet right after standup and the sprint meeting

**Today I**
- [ ] NationBuilder issues:
  - [ ] we are being asked if it is possible for a senders address to be send to the NB database instead of the lat/long that we are currently sending, https://oneclickpolitics.zendesk.com/agent/tickets/1012 Maged says yes, this is a BUG, research to confirm first, go into NB libs and remove that bit.  I should contact NB directly to confirm that tis change won't break anything else...I'll send the initial email
  - [ ] PromotorUser 11233 unable to login in to OCP via the NB portal, https://oneclickpolitics.zendesk.com/agent/tickets/1095
  - [ ] more NB sync issues (Nov 1, Oct 29, Sep 30) though last message from Darren after I looked into this on Nov 3 was "Thanks for looking into this. I will update you if anything changes."
- [ ] set up the basics for the new API
  - docker
  - ElasticSearch
  - set up the repo
- [ ] continue to be available for any knowledge sharing on import that Hager needs



## Tue, Nov 16 2021
**Yesterday I**
- KnowWho import
- replace MSA with TeamUSA logo on the home page, got the PR created and reviewed, and just finished deploying this to production

**Today I**
- [ ] create tickets for the first tasks of the API
- [ ] set up the basics for the new API
  - docker
  - ElasticSearch
  - set up the repo
- [ ] continue to be available for any knowledge sharing on import that Hager needs
- [ ] injured cat; if I can catch her, I may suddenly be away from my keyboard without warning to take her to the vet
- [ ] send Maged the zendesk/jira tickets from this last week over to Maged


## Mon, Nov 15 2021
### Jira tickets

**Friday I**
- removed Evan from the website and got that pushed to prod
- paired with Alex on a front end issue
- met with Hager with a huge information share
- planned with Maged on the new API
- did thinking and planning on the new API

**Today I**
- [x] KnowWho import
- [x] Replace MSA with TeamUSA logo on the home page
- [ ] create tickets for the first tasks of the API
- [ ] set up the basics for the new API
- [ ] naming of the API (first take recommendations, then hold a vote, then Maged gives final decision)


## Fri, Nov 12 2021
- ocp-core-api
- ocp-enterprise-api
- ocp-mercury-api
- one-click-atc
- ocp-switchboard-api

- set up shell for new API

**Yesterday I**
- review multiple PRs
- deployed current master to production (contained recent PRs from both me and Alex)
- assisted Hager in setup and Cicero imput familiarity
- walked through the instructions for an existing Cicero import of AU/CA data
- confirmed that shp2pgsql successfully generates a district SQL file
- confirmed that the csv_merge.rb (once adjusted for UK naming) works successfully to merge officials with levels and roles

**Today I**
- [ ] break down the work on the new Recipients API into tasks
- [ ] create Jira tickets for the Recipients API tasks
- [x] remove Evan Ashy from the website. ON-1406

## Thu, Nov 11 2021

### Recipients API
- it will also live in Elasticsearch
- the analytics/delivery API is probably a good start
- also think about it from the importer side as well

#### Recipients API - OPEN QUESTIONS
- Importer side: Cicero import or Promoters wanting to import custom recipients?

#### Recipients API - LIST OF TASKS
- figure out how elastic search is implemented in Analytics/Delivery API and do that here; I don't know if this should be the first task, but better to have it first so that the rest of the tasks can be altered as needed by ES
- create docker images
- add elasticsearch model gem
- create Recipients model
- create Recipients controller
- controller - create one
- controller - create many
- controller - index all
- controller - show one
- add search
- add routes
- create API GET
- create API POST (UPDATE?)
- probably don't need a DELETE, just a POST that can change to inactive
- add controller specs
- add rescues, logging, and error logs


**Yesterday I**
- did a formal writeup to Darren, Chazz, Dominique on the situation with the changing shapefiles
- deployed all the AU/CA stuff which includes deactivation rake task refactor
- wrap up all AU/CA data cleanup on prod; the data is looking great; the only reps with initials are those who use only initials in current Cicero data

**Today I**
- [x] review multiple PRs
- [x] deployed current master to production
- [x] top priority is pairing/assisting Hager in setup and Cicero imput familiarity; should demonstrate existing Cicero import of AU/CA


## Wed, Nov 10 2021
**Yesterday I**
- researched the redistricting that is affecting our shapefiles
- got the various AU/CA PRs checked in and ready deployment

**Today I**
- [x] do a formal writeup to Darren, Chazz, Dominique on the situation with the changing shapefiles
- [x] deploy all the AU/CA stuff and run through the cleanup
- [x] deploy the deactivation rake task refactor
- [x] wrap up all AU/CA data cleanup on prod

Zendesk ticket #1124 with the incorrect state representative coming up for a signer in SC.

The US is in the early stages of redistricting as a result of the 2020 US census.  This means that shapefiles on production are not and cannot be fully up to date until the redistricting process is complete in each state and the new shapefiles are "enacted" by each state.  This process is tracked in detail here, https://ballotpedia.org.  This site is updated daily.  Please see below for links to current status of both State Legistature and Congressional redistricting.

**Data from the Census arrival timeline**
August 12, 2021, the U.S. Census Bureau delivered redistricting data to states in a legacy format.  September 16, 2021, the U.S. Census Bureau released data from the 2020 census in an easier-to-use format to state redistricting authorities and the public.

**State Legislature redistricting status**, https://ballotpedia.org/State_legislative_district_maps_implemented_after_the_2020_census As of November 9, 2021, 12 states have adopted legislative district maps, one state’s legislative map is awaiting approval by the state supreme court, one state enacted its legislative boundaries based on Census estimates which will be revised in an upcoming special session, and 36 states have not yet adopted legislative redistricting plans after the 2020 census.

Nationwide, legislative redistricting has been completed for 444 of 1,972 state Senate seats (22.5%) and 1,243 of 5,411 state House seats (23.0%).

**Congressional redistricting status**, https://ballotpedia.org/Status_of_redistricting_after_the_2020_census As of November 9, 2021, 10 states have adopted congressional district maps, six states were apportioned one congressional district (so no congressional redistricting is required) and 34 states have not yet adopted congressional redistricting plans after the 2020 census.

Congressional redistricting has been completed for 99 of the 435 seats (22.7%) in the U.S. House of Representatives.

Additionally, Dave has confirmed that the latitude/longitude of the signer in South Carolina successfully maps to House District 26 and state representative Raye Felder in the new Cicero US data being tested that goes live in the new year.


## Tue, Nov 9 2021
### redistricting and shapefiles
[https://ballotpedia.org/Status_of_redistricting_after_the_2020_census](https://ballotpedia.org/Status_of_redistricting_after_the_2020_census) <- good site for current status of the "enacting" of new maps for congressional and state legislative maps as a result of the 2020 census.

[https://www.scstatehouse.gov/legislatorssearch.php](https://www.scstatehouse.gov/legislatorssearch.php) <- current "mapping"

**Current status of redistricting as a result of the 2020 US census:**

**State Legislature redistricting**
https://ballotpedia.org/State_legislative_district_maps_implemented_after_the_2020_census  As of November 8, 2021, 12 states have adopted legislative district maps, one state's legislative map is awaiting approval by the state supreme court, one state enacted its legislative boundaries based on Census estimates which will be revised in an upcoming special session, and 36 states have not yet adopted legislative redistricting plans after the 2020 census.

Nationwide, legislative redistricting has been completed for 444 of 1,972 state Senate seats (22.5%) and 1,243 of 5,411 state House seats (23.0%).

**Congressional redistricting**
https://ballotpedia.org/Status_of_redistricting_after_the_2020_census  As of November 8, 2021, 10 states have adopted congressional district maps, six states were apportioned one congressional district (so no congressional redistricting is required) and 34 states have not yet adopted congressional redistricting plans after the 2020 census.

Congressional redistricting has been completed for 99 of the 435 seats (22.7%) in the U.S. House of Representatives.

**Yesterday I**
- spoke with Nate and Dave to determine what could be done about the zendesk ticket with the incorrect state representative coming up for a signer in SC (summary below)  Also Dave has just confirmed that this lat/long successfully maps to House District 26 and state rep Raye Felder in the new Cicero US data that goes live in the new year.

THIS: Can Dave provide the encoding that is needed for a shapefile found online.  Maged wants us to find a solution now, not to wait. (there was a NC one in March-ish)

- merged ON-1378 (PR 432), the refactor of the Cicero AU/CA import specs
- made recommended improvements to the deactivation rake task refactor
- KnowWho import

**Today I**
- [ ] looking at PRs, mostly done
- [ ] need final reviews for the deactivation rake task refactor from Maged and Nate, https://github.com/one-click-politics/one-click-politics/pull/429; changes are checked in
- [ ] merge the deactivation rake task refactor, ON-1366
- [ ] deploy the deactivation rake task refactor
- [ ] wrap up all AU/CA data cleanup on prod
- [ ] need the next big task or I'm going to start planning the Recipients API or talking to Alex about which areas he's found broken tests

- dropbox link to the UK data in prep for meeting with Hager (Hogger?) for the UK cicero data import
Nai (UX person)    Maagid

## Mon, Nov 8 2021
**Friday I**
- finished the refactor of the tests for the cicero import name updater
- went back and forth with Darren about delievery details for the NSW AU premier

**Today I**
- [x] Zendesk 1124, https://oneclickpolitics.zendesk.com/agent/tickets/1124
The wrong state rep is bring brought up in the widget for the signer.  See summary below.  Ticket is updated with findings.
- [ ] need final reviews for the deactivation rake task refactor from Maged and Nate, https://github.com/one-click-politics/one-click-politics/pull/429; changes are checked in
- [ ] merge the deactivation rake task refactor, ON-1366
- [x] merged ON-1378 (PR 432), the refactor of the Cicero AU/CA import specs

- [ ] think about how to implement next big project will probably be a Recipients API

### zendesk 1124
Engineering has confirmed that according to geocod.io, this address (and the Lat/Long) put this sender in House District 26 with state rep Raye Felder.

Unfortunately, the live site consistently brings up Bryant, Bruce due to the shapefile.  It appears that our shapefiles for the US are becoming out of date.  Probably due to last year’s census results finally triggering changes.  

The longterm solution is very good.  Cicero provides shapefiles along with the rest of the data, so when we change to Cicero in the new year, we will receive updated shapefiles with which we can get out system back up to date.

However, there is no immediate solution.  Previously, shapefiles for US were something that were found on the internet and imported in.  However, the shapefiles used must be the same as the rest of the shapefiles used, or the mapping will not work as expected.  It has been over a year since this was done for US and is a long and tedious process.  Best recommendation is to hold on until the US Cicero data project is complete and functional.  

The answer to the question of "when will the next data refresh occur" is: no later that the beginning of 2022.  Dave knows of this issue and will do what is possible sooner.


## Fri, Nov 5 2021
### .as_json
https://jsonlint.com/

To use jsonlint on the results from rails console queries, all `.as_json` to the end of the query and the output format will be json that can be parsed by jsonlint.

### Zendesk 1124, https://oneclickpolitics.zendesk.com/agent/tickets/1124
The wrong state rep is bring brought up in the widget for the signer.

The sender’s address is: 1425 Lurecliff Pl, Fort Mill, SC, 29708.  According to https://www.scstatehouse.gov/legislatorssearch.php, this sender’s South Carolina State Representative is: SC House District 26 - R. Raye Felder

According to geocod.io, this address (and the Lat/Long) put this sender in House District 26 with state rep Raye Felder.

Unfortunately, the live site consistently brings up Bryant, Bruce and I cannot determine why.


I created my own widget on the live site.

In the first test, I added both reps (as always send).  The wrong one was the only one displayed in the widget.

In the second test, I added no reps.  The wrong one was the only one displayed in the widget.

### geocode.io
```
user: susan.prestage@gmail.com
password: BseeingU2!
```

Geocode.io calls for the address 1425 Lurecliff Pl, Fort Mill, SC, 29708
```
curl "https://api.geocod.io/v1.6/geocode?q=1425+Lurecliff+Pl%2c+Fort+Mill+SC&fields=stateleg&api_key=8ef516fcc66efb86fe0b6165511cb0b6866ba00"
curl "https://api.geocod.io/v1.6/reverse?q=35.073789,-80.961816&fields=stateleg&api_key=8ef516fcc66efb86fe0b6165511cb0b6866ba00"
```

Example calls to geocode.io
```
curl "https://api.geocod.io/v1.6/geocode?q=1109+N+Highland+St%2c+Arlington+VA&api_key=8ef516fcc66efb86fe0b6165511cb0b6866ba00"
curl "https://api.geocod.io/v1.6/geocode?q=1109+N+Highland+St%2c+Arlington+VA&fields=cd,stateleg&api_key=8ef516fcc66efb86fe0b6165511cb0b6866ba00"
curl "https://api.geocod.io/v1.6/reverse?q=38.886672,-77.094735&fields=cd,stateleg&api_key=8ef516fcc66efb86fe0b6165511cb0b6866ba00"
```

https://dash.geocod.io/apikey

8ef516fcc66efb86fe0b6165511cb0b6866ba00

https://www.geocod.io/docs/#state-legislative-districts


**Yesterday I**
- reviewed a couple of pending PRs
- merged the name updater name update work for CA import, ON-1392
- paired with Alex on the widget Safari issue
- Worked on https://oneclickpolitics.zendesk.com/agent/tickets/1124
  - I can confirm that the sender is being mapped incorrectly to Rep. Bruce Bryant's district, when they should be mapped to R. Raye Felder: https://www.scstatehouse.gov/legislatorssearch.php.  1425 Lurecliff Pl, Fort Mill, SC, 29708
  - Nate: how do we check if KnowWho is mapping someone correctly?  Did you check this last time using Postman calls?  Or is this an error in the shapefiles from KnowWho?  Or?  Also, what is used to "map" a sender, address, lat/long?

  address -> geocoder service (us = geocode.io, au/ca = opencage)
  field for good up until

**Today I**
- [x] 1/2 done with the refactor of the tests for the cicero import name updater with Dave's advice here, https://oneclickpolitics.atlassian.net/browse/ON-1378
- [ ] think about how to implement next big project will probably be a Recipients API
- [ ] need final reviews for the deactivation rake task refactor, https://github.com/one-click-politics/one-click-politics/pull/429; alex has finalized, Nate or Dave haven't looked yet.  Merge when needed but work on other things first.
- [ ] merge the deactivation rake task refactor, ON-1366


## Thu, Nov 4 2021
**Yesterday I**
- researched and updated https://oneclickpolitics.zendesk.com/agent/tickets/1130, regarding NationBuilder syncs...the syncs look good, no older than 31 Oct.  1 of these failed on 31 Oct, so I kicked off a new one, which succeeded.  Full details of when syncs occurred for each of the sub-promoters is listed in the zendesk ticket.  
- responded to PR reviews

**Today I**
- [x] review a couple of pending PRs
- [x] merge the name updater name update work for CA import, ON-1392
- [x] paired with Alex on the widget Safari issue
- [ ] refactor the tests for the cicero import name updater with Dave's advice here, https://oneclickpolitics.atlassian.net/browse/ON-1378 - this should be straightforward but I think I should consider doing this on another branch than the implementation of the name updater
- [ ] https://oneclickpolitics.zendesk.com/agent/tickets/1124
- [ ] think about how to implement next big project will probably be a Recipients API
- [ ] need final reviews for the deactivation rake task refactor, https://github.com/one-click-politics/one-click-politics/pull/429; alex has finalized, Nate or Dave haven't looked yet.  Merge when needed but work on other things first.
- [ ] merge the deactivation rake task refactor, ON-1366

### example elastic search queries
```
{
  "query": {
    "bool": {
      "must":
        [
          {
            "match": {"promoter.id": "13607"}
          }
          {
            "range": {
              "delivery_date": {
                "gte": "2021-10-28",
                "lte": "2021-11-03"
              }
            }
          }
        ]
    }
  },
  "size": 0,
  "aggs": {
    "by_date_medium": {
      "multi_terms": {
        "terms": [{
          "field": "delivery_date.raw"
        }, {
          "field": "medium.raw"
        }]
      }
    },
    "senders_per_day": {
      "date_histogram": {
        "field": "delivery_date",
        "calendar_interval": "day"
      },
      "aggs": {
        "distinct_senders": {
          "cardinality": {
            "field": "sender.email.raw"
          }
        }
      }
    }
  }
}

Shams Baig  9:25 AM
{
  "query": {
    "bool": {
      "must":
        [
          {
            "match": {"promoter.id": "13607"}
          },
          {
            "range": {
              "delivery_date": {
                "gte": "2021-10-28",
                "lte": "2021-11-03"
              }
            }
          }
        ]
    }
  },
  "size": 0,
  "aggs": {
    "by_date_medium": {
      "multi_terms": {
        "terms": [{
          "field": "delivery_date.raw"
        }, {
          "field": "medium.raw"
        }]
      },
      "aggs": {
        "distinct_senders": {
          "cardinality": {
            "field": "sender.email.raw"
          }
        }
      }
    }
  }
}
```

## Wed, Nov 3 2021
**Latest status**
- [ ] refactor the tests for the cicero import name updater with Dave's advice here, https://oneclickpolitics.atlassian.net/browse/ON-1378 - this should be straightforward but I think I should consider doing this on another branch than the implementation of the name updater
- [x] respond to PR reviews

**Yesterday I**
- fixed the 10 CA broken import tests (broken in ON-1391) - I believe this may have something to do with the addition of cicero_codes to several of the factory generated CA recipients
- started and finished the name update work for CA import, ON-1392
- wrote tests for the name update work for CA import, ON-1392
- created PR for name update work for CA import, ON-1392, https://github.com/one-click-politics/one-click-politics/pull/431

**Today I plan to**
- [ ] refactor the tests for the cicero import name updater with Dave's advice here, https://oneclickpolitics.atlassian.net/browse/ON-1378 - this should be straightforward but I think I should consider doing this on another branch than the implementation of the name updater
- [ ] respond to PR reviews


## Tue, Nov 2 2021
**Latest status**
- [ ] fix the 10 CA broken import tests (broken in ON-1391) - I believe this may have something to do with the addition of cicero_codes to several of the factory generated CA recipients
- [ ] start the name update work for CA import
- [ ] write tests for the name update work for CA import


**Yesterday I**
- test out the CA deactivation rake task on staging, branch ON-1366
- test out the CA/AU rake task refactoring on staging, branch ON-1366
- KnowWho import on production in process...
- deploy the (pre-refactored) deactivation rake task to production
- test the deactivation rake task on production to see how the recipient data really looks before touching anything.  Data looks great.  Only 8 without cicero codes and those are only the CA house recipients.
- deploy master to staging to test out the CA UI changes
- test out the CA UI changes for no cicero codes on staging (CustomRecipient vs CA w/ code vs CA w/o code)
- discovered that 10 of the CA import tests were broken with the CA UI changes

**Today I plan to**
- [ ] fix the 10 CA broken import tests (broken in ON-1391) - I believe this may have something to do with the addition of cicero_codes to several of the factory generated CA recipients
- [ ] start the name update work for CA import
- [ ] write tests for the name update work for CA import


## Mon, Nov 1 2021
**Latest status**
- [x] deployed ON-1366 is deployed to staging
- [x] deployed master with latest KnowWho to production
- [x] test out the CA deactivation rake task on staging, branch ON-1366
- [x] test out the CA/AU rake task refactoring on staging, branch ON-1366
- [x] KnowWho import on production in process...
- [x] get the deactivation rake task deployed to production to see how the recipient data really looks before touching anything <- this is already done; doesn't include refactor, but is fine for looking at the data.  Data looks great.  Only 8 without cicero codes and those are only the CA house recipients.
- [x] deploy the (pre-refactored) deactivation rake task to production
- [x] test the deactivation rake task on production to see how the recipient data really looks before touching anything.  Data looks great.  Only 8 without cicero codes and those are only the CA house recipients.
- [x] deploy master to staging to test out the CA UI changes
- [x] test out the CA UI changes for no cicero codes on staging (CustomRecipient vs CA w/ code vs CA w/o code)
- [ ] start the name update work for CA import


**Monday I**
- finished the refactoring of the deactivation rake tasks into a single rake task
- implemented tests of the new method being used by the deactivation rake task
- got the CA deactivation PR deployed to staging for test
- got the CA & AU deactivation refactor branch deployed to staging for test

**Today I plan to**
- [x] test out the CA deactivation rake task on staging
- [x] test out the CA/AU rake task refactoring on staging
- [x] get the deactivation rake task deployed to production to see how the recipient data really looks before touching anything <- this is already done; doesn't include refactor, but is fine for looking at the data
- [x] try to get the CA UI PR merged and deployed to staging as well, depends on PR comments since the PR was created late yesterday, Wed
- [ ] start the name update work for CA import
- [x] KnowWho import


## Fri, Oct 29 2021
**Yesterday I**
- responded to Nate's PR comments
- refactored the deactivation rake tasks for AU and CA to use a service object

**Today I plan to**
- [ ] implement tests of the new service object being used by the deactivation rake tasks
- [ ] get the deactivation PR merged and deployed to staging for test
- [ ] get the deactivation rake task deployed to production to see how the recipient data really looks before touching anything
- [ ] try to get the CA UI PR merged and deployed to staging as well, depends on PR comments since the PR was created late yesterday, Wed
- [ ] start the name update work for CA import
- [ ] LATER (THIS IS FOR THE NAME UPDATE) write the specs for the name update, plus some spec refactoring from the AU work that will be used here being pulled into a spec helper that both specs will use


## Thu, Oct 28 2021
**Yesterday I**
- tested the CA cicero import locally and on staging.  There was an odd error as a result of the odd way they gave us the districts and shapes...first with extra and old districts, then only the new ones.  Nate and I determined that the "errors" were really more "warnings" and the district import was successful.  The actual match and import succeeded with no issues.
- the full CA cicero import on production succeeded with no issues
- made the PR for the deactivation rake task
- did the UI work to no longer show the CA recipients with no cicero code (in the widget editor and widget)
- wrote the specs for the CA UI work; also split out these CA & AU specific tests out of the main widget spec (rather too big)
- made the PR for the CA UI work
- update Jira, move backlog items into sprint
- did some local by hand testing to confirm the UI work for CA recipients with and without codes

**Today I plan to**
- [ ] respond to various PR comments
- [ ] get the deactivation PR merged and deployed to staging for test
- [ ] get the deactivation rake task deployed to production to see how the recipient data really looks before touching anything
- [ ] try to get the CA UI PR merged and deployed to staging as well, depends on PR comments since the PR was created late yesterday, Wed
- [ ] rake task refactoring to use a service object and implement some tests; this gives some direction and pointers to examples, https://oneclickpolitics.atlassian.net/browse/ON-1366
- [ ] start the name update work for CA import


## Wed, Oct 27 2021
**Yesterday I**
- paired with Nate and solved the CA cicero import issues.  It turns out that due to an August election, the shape files had changed for Canada (not AU), but Cicero did not include these updated files in the October drop.  And yes, you do remember correctly that they also forgot the role and level files for both AU & CA.  Since this was only CA, I didn't trip over the issue last week in the midst of the AU import circus.
- wrote up the Jira tickets for the CA data cleanup
  - deactivate those w/o cicero_codes,
  - name update in import,
  - remove those w/o cicero codes from CA UI (widget and edit widget pages)
- reworked to house delivery method report to answer more questions for Maged; looking at the data, I see why he wants this
- wrote the rake task to deactivate CA recipients w/o Cicero codes
- I have downloaded and unzipped the shapefiles that were missing from the CA Cicero import data

**Today I**
- [x] now that we have the shape files, I'll first test the CA cicero import locally, then on staging due to the name update changes which shouldn't affect CA, but I'm cautious
- [x] do the full CA cicero import on production 🤞
- [x] make the PR for the deactivation rake task
- [x] start the UI work for the CA recipients with no cicero code (widget editor and widget)
- [x] specs for the UI work
- [x] update Jira, move backlog items into sprint
- [x] do by hand testing to confirm the UI work for CA recipients of the three types with and without codes
- [ ] rake task refactoring to use a service object and implement some tests; this gives some direction and pointers to examples, https://oneclickpolitics.atlassian.net/browse/ON-1366
- [ ] start the name update work for CA
- [ ] get the deactivation PR merged and deployed to staging for test
- [ ] get the deactivation rake task deployed to production to see how the recipient data really looks before touching anything

- [ ] LATER (THIS IS FOR THE NAME UPDATE) write the specs for the name update, plus some spec refactoring from the AU work that will be used here being pulled into a spec helper that both specs will use


## Tue, Oct 26 2021
**Yesterday I**
- I deactivated the extra AU Heidi that was created to get a client through until we got the new October Cicero data
- I finished the house report.  Which promptly confused Maged.  So I split it into two with better descriptions.
- staging was super slow but that seemed to resolve itself once I spoke with Dave and Eric.  I think staging was scared of them and decided to shape up.  :D
- deployed CA cicero import to staging
- tried to do the CA cicero import locally.  The recipient portion succeeded, but the match portion generated this error:
```
=> {:district_matcher=>[[], ["District record not found for (900157), for state CA-NS, state, LOWER", "District record not found for (900157), for state CA-NS, state, LOWER", "District record not found for (900160), for state CA-NS, state, LOWER", "District record not found for (900160), for state CA-NS, state, LOWER", "District record not found for (900161), for state CA-NS, state, LOWER", "District record not found for (900161), for state CA-NS, state, LOWER", "District record not found for (900163), for state CA-NS, state, LOWER", "District record not found for (900163), for
...
state CA-NS, state, LOWER", "District record not found for (900209), for state CA-NS, state, LOWER", "District record not found for (900211), for state CA-NS, state, LOWER"]], :party_matcher=>[], :office_matcher=>[], :row_checker=>[], :recipient_importer=>[]}
```
- tried to do the CA cicero import on staging.  Got more district errors.  Wrote up all the issues, local and staging, and Slacked Dave and Nate for assistance on Tuesday.  I told them not to respond yesterday (monday).
  - the shapefile import showed many `does not match any existing District` errors
- Also, this morning I saw a second ticket on the safari issue of the widget just spinning after clicking submit.  I've reproduced this locally using Safari 14 and also by simulating version 13 of Safari.

**Today I**
- [ ] hope to solve the CA cicero import issues locally and on staging
- [ ] do the full CA cicero import on production
- [ ] assess efforts for doing to CA what I did with AU (duplication cleanup, deactivating, maybe name update as well).  Below is a guess as I've not gotten into the code, but should be pretty accurate.  If we are adding in refactoring leftover from AU, lets add 1 more day, so 6 days total.
  - 1 day to rework rake file for and to perform deactivation of CA recipients with no cicero code.  Depending on PR comments.  Could drag to 2 days.
  - Duplication cleanup will not be well known until the above rake file is run, but I expect this will fold into the above estimate.
  - Name update, I estimate 2 days to make sure that the specs are in order, plus PR comment responses.
  - Implement same UI changes as for AU to prevent recipients with no cicero code from being displayed in the UI.  1 day
  - Total for all work, 1 week.  3 different tickets, includes specs, and testing on staging.
- [ ] grab a pair of refactoring Jiras that I have pending
- [ ] look for tests to fix


## Mon, Oct 25 2021
**Friday I**
- tested the AU import on staging
- deployed to production
- ran AU deactivation rake task on production, without save, then with save...this turned out to be harder than it should have been as many in the AU House had invalid `state`.  I went through by hand and corrected the state, then ran the rake task successfully.  Since all had a valid duplicate, this was how I got the correct state.
- did the full AU cicero import on production with name update
- tried to do the CA cicero import locally.  The recipient portion succeeded, but the match portion generated this error:
```
=> {:district_matcher=>[[], ["District record not found for (900157), for state CA-NS, state, LOWER", "District record not found for (900157), for state CA-NS, state, LOWER", "District record not found for (900160), for state CA-NS, state, LOWER", "District record not found for (900160), for state CA-NS, state, LOWER", "District record not found for (900161), for state CA-NS, state, LOWER", "District record not found for (900161), for state CA-NS, state, LOWER", "District record not found for (900163), for state CA-NS, state, LOWER", "District record not found for (900163), for
...
state CA-NS, state, LOWER", "District record not found for (900209), for state CA-NS, state, LOWER", "District record not found for (900211), for state CA-NS, state, LOWER"]], :party_matcher=>[], :office_matcher=>[], :row_checker=>[], :recipient_importer=>[]}
```

**Today I plan to**
- [x] also finish house report
- [x] deploy CA cicero import to staging; this is taking a while...mostly the getting back into the rails console
- [ ] run the CA cicero import on staging
  - the shapefile import showed many `does not match any existing District` errors
- [ ] do the full CA cicero import on production
- [ ] grab a pair of refactoring Jiras that I have pending
- [ ] assess efforts for doing to CA what I did with AU (duplication cleanup, deactivating, maybe name update as well)
- [ ] look for tests to fix
- [x] confirm that old HEidi is deactivated.



## Fri, Oct 22 2021
- [ ] this afternoon: look into importer that touches s3.  post to engineering what I find.

### status
**Yesterday I**
- Got Alex's rake task altered to generate the data for the House delivery report.  Ran this locally, then on production and am in the process of putting the data into a text file and updating the Jira with the attachments of the data and the new/altered rake task.
- Discovered that my importing problems were due to the missing _role and _level files that Cicero failed to include.  
- Needed to clean up the data they sent.  Mostly, this was multiple instances extra double quotes in the, call it the description field, of the rows in the .csv data.  Once this was cleaned up, the merge succeeded, giving us importable .csv files which have been checked into master for AU and CA.
- Tried to import locally, but got this weird error when running the matcher:
```
irb(main):005:0> recipient_importer.all_problems # Look at problems
=> {:district_matcher=>[[], []], :party_matcher=>[], :office_matcher=>[["222No Office record found for comm JOINT)\n", "222No Office record found for comm JOINT)\n", "222No Office record found for comm JOINT)\n", "222No Office record found for comm JOINT)\n"]], :row_checker=>[], :recipient_importer=>[]}
```
- Deployed to staging to see if this was only a problem locally.
**Today I plan to**
- [x] test the import on staging
- [x] deploy to production
- [x] run AU deactivation rake task on production, without save, then with save...this turned out to be harder than it should have been as many in the AU House had invalid `state`.  I went through by hand and corrected the state, then ran the rake task successfully.  Since all had a valid duplicate, this was how I got the correct state.
- [x] do full AU cicero import on production with name update
- [ ] do full CA cicero import on production
- [ ] grab a pair of refactoring Jiras that I have pending
- [ ] look for tests to fix


## Thu, Oct 21 2021
the delivery numbers do not match.  work with shams on this once done with the import stuff - the ticket exists (zendesk, I think).  need the ticket number

### status
- I figured out that the problem I was having with the October Cicero import was entirely due to missing two critical files for each of AU and CA.  These are the _level and _role files.  These are the two that are merged with the officials file to get a .csv file with the data expected by our importer.  This was due to the change Cicero made in the presentation of the data as of June.  Wrote up explanation in email for Maged to forward on to Cicero.  Here is hoping they will respond quickly.


## Wed, Oct 20 2021
Felt poorly this morning after liquid diarhea all night.  Spent the day sleeping, dozing, and resting in bed.


## Tue, Oct 19 2021
### current status
- [x] get the DB endpoint needed to run the psql command for shapefile import on staging
- [x] test full AU cicero import on staging, with and without name update
- [ ] do full AU cicero import locally with name update using new Oct data
- [ ] do full AU cicero import on staging with name update using new Oct data
- [ ] run AU deactivation rake task on production, without save, then with save
- [ ] do full AU cicero import on production with name update
- [ ] do full CA cicero import on production
- [ ] ask Alex about his rake task for harvesting CWC senate delivery data
- [ ] convert Alex's rake task for gathering the data for the house
- [ ] grab a pair of refactoring Jiras that I have pending
- [ ] look for tests to fix

### rake file running tips and tricks and advice
If you see the phantomjs/poltergeist error when trying to run a rake task, you need to specify `RAILS_ENV=production`
```
ubuntu@ip-172-30-1-231:/home/deploy/apps/ocp/current$ bundle exec rake import_cicero_australia_shapefiles[record]
...
rake aborted!
LoadError: cannot load such file -- phantomjs/poltergeist
ubuntu@ip-172-30-1-231:/home/deploy/apps/ocp/current$ bundle exec rake import_cicero_australia_shapefiles[record] RAILS_ENV=production
```


## Mon, Oct 18 2021
CWC house who is actually receiving, for real.  
How many are successfully delivered, from the recipients/delivery page
each recipient has a page that show delivery info.  ask alex about his script that harvests this data


### current status
- [x] check in with Alex about his merge before I deploy the widget fix to prod
- [x] KnowWho import
- [x] merge the Clearbrook UI semi-duplication fix and deploy to prod, https://github.com/one-click-politics/one-click-politics/pull/423
- [ ] grab a pair of refactoring Jiras that I have pending
- [ ] look for tests to fix
- [ ] import shapefiles to staging

DO ALL THESE WHEN WE HAVE AU DATA
- [ ] the business decided that yes, I can run the rake to de-activate the AU recipients without cicero code
- [ ] Cicero import, still waiting; 3 of 4 files are inaccessible

### morning status
Friday
- tested the AU name updater without the overwrite flags and confirmed that the names are not updated
- found where the widget semi-duplication was being triggered with the help of Alex
- fixed it, PR'ed it
- was able to reproduce the issue "locally" thus was able to confirm issue on prod and confirm fix on staging.  thanks to Nate for the suggestion to embed the widget code in the dev tools directly in Safari
- added repro and test instructions into the PR and Jira ticket
- tested locally the AU name updater with the overwrite flags and confirmed that the names are appropriately updated

Today
- [ ] Maged: has the business decided that yes, I can run the rake to de-activate the AU recipients without cicero code?
- [ ] KnowWho import
- [ ] Cicero import, if it has come in?
- [ ] Merge the Clearbrook UI semi-duplication fix and deploy to prod, https://github.com/one-click-politics/one-click-politics/pull/423
- [ ] ready for the next big task
- [ ] grab a pair of refactoring Jiras that I have pending
- [ ] look for tests to fix


## Fri, Oct 15 2021
### current status
- [x] test the AU name updater without the overwrite flags and confirmed that the names are not updated
- [x] found where the widget semi-duplication was being triggered with the help of Alex
- [x] fixed it, PR'ed it
- [x] was able to reproduce the issue "locally" thus was able to confirm issue on prod and confirm fix on staging.  thanks to Nate for the suggestion to embed the widget code in the dev tools directly in Safari
- [x] added repro and test instructions into the PR and Jira ticket
- [x] test the AU name updater locally, with the overwrite flags and confirmed that the names are appropriately updated.  I tried this with:
  - both first_name and last_name overwrite false
  - only first_name overwrite true
  - only last_name overwrite true
  - both first_name and last_name overwrite true
- [ ] test the AU name updater on staging, with the overwrite flags and confirmed that the names are appropriately updated

### daily status
Yesterday
- reviewed various PRs
- set up iphone safari simulators, repro'ed bug, iphone and safari is key, also only reproducible on client site...thouogh I tried many ways to do this.  Put together a write up of current status and emailed to Maged, and then @maged in Slack.  Hoping for more Alex assistance in tracking this down as I have some very interesting clues now that I have responsive design mode working in Safari.
- all the AU stuff is merged into master

- [ ] working my way through the cicero import locally
- [ ] I'd like to try staging next
- [x] pairing with Alex this morning on the iphone display issue.  I've seen some clues that may help us understand why/how this semi-duplication is happening.

- [ ] YIKES!  Need to test import locally ASAP!!!


## Thu, Oct 14 2021
### current status
- [ ] review Shams' PRs
- [ ] download xcode and try iphone/chrome and iphone/safari simulators.  Sounds like Nate and Maged have seen some consistency with safari.  Try on my iphone with incognito...after I learn how.
- [ ] run AU importer locally
- [ ] follow up on reviews from folks this morning for both AU PRs.


### status report
- Got all the changes tested and checked in for the two Australia PRs.
- RE: my message from yesterday on the zendest 1101 for the issue with iphone issue for display of their widget.  Maged: update on zendesk 1101: I've brought up the problem page with our widget on my iPhone several times.  The first time, I saw the issue.  All subsequent visits, the issue did not occur.  Who else on the engineering team has an iphone and can they try this link, https://www.clearbrook.org/advocacy/.  My tests were with Chrome.  When I get home, I'll try to get another browser or two on my phone and test further.  Try running this incognito.
- I'd like to run the AU imorter locally on our data from last month

REMEMBER: smaller Jira breakdowns leads to smaller PRs and better (and quicker!) reviews.  Good times!!


## Wed, Oct 13 2021
### current status
- [ ] need to respond and fix bits of ON-1359 (first/last name AU import update) from Dave and Nate's feedback
- [ ] ask for someone to take a look at the two tests in ON-1357 that I don't understand how I broke in ON-1357; search for 'skip do' to find
- [ ] also, ON-1357 is ready for re-review

### status report
- got the ON-1359 branch (first/last name AU import update) cleaned out and ready for Nate's review
- re-worked ON-1357 (AU recipient UI fixes) to DRYing of repetitions across 6 files, thanks Dave and Alex for the recomendations
- Maged: I saw the note about the cicero data arriving next week
- Maged: update on zendesk 1101: I've brought up the problem page with our widget on my iPhone several times.  The first time, I saw the issue.  All subsequent visits, the issue did not occur.  Who else on the engineering team has an iphone and can they try this link, https://www.clearbrook.org/advocacy/.  My tests were with Chrome.  When I get home, I'll try to get another browser or two on my phone and test further.

- [ ] need to respond to feedback for ON-1359 (first/last name AU import update) from Dave and Nate
- [ ] ask for someone to take a look at the two tests in ON-1357 that I don't understand how I broke in ON-1357; search for 'skip do' to find
- [ ] also, ON-1357 is ready for re-review


## Tue, Oct 12 2021
### current status
- [x] revert the ON-1357 files and re-check into ON-1359 so it can be reviewed by Nate; then give Nate a heads up
- [x] Implement Alex's suggestion on ON-1357 for the DRY.  We both admire Dave's recommendation for ON-1357, but it does not actually save that much and adding a lot of higher level rails concepts to it.
- [ ] ask for someone to take a look at the two tests in ON-1357 that I don't understand how I broke in ON-1357; search for 'skip do' to find
- [ ] also, ON-1357 is ready for re-review
- [ ] look into Dave's recommendations for ON-1359
- [ ] make ticket for ongoing spec cleanup
- [ ] review pending PRs
- [ ] WAITING - as of 12:15pm, I am awaiting Nate's review of ON-1359.  Once ready, look into Nate's suggestions for ON-1359
- [ ] WAITING - still waiting for the cicero data for AU (and CA), use this to check
```
aws --profile cicero_user s3 ls --recursive s3://cicero-global-data-us-east-1/OneClickPolitics/

alias ls_cicero="aws --profile cicero_user s3 ls --recursive s3://cicero-global-data-us-east-1/OneClickPolitics/"
```

### status
#### yesterday
- [ ]  I was responding to reviews on the UI.  Mostly done.
#### today
- [ ] make ticket for ongoing spec cleanup
- [ ] need to get ON-1357 merged in so that ON-1359 can be reviewed since it needs rebasing
- [ ] done with ON-1357 except for Dave's recommendation below
- [ ] reviewing PRs
- [ ] responding to PRs
- [ ] what is the status of receiving the cicero data for AU (and CA)?
- [ ] hope to wrap up PRs and get the AU recipient UI fixes and the cicero update of AU recipient names  improvement to the import merged to master this afternoon

- [x] I tried to do KnowWho import on the side, but my internet is making this impossible.  Handed off to Alex in standup.
- [x] notify team that tomorrow morning I will be out also post this in Slack.  I need to head to the city for an appointment.  The hours I worked Sunday should cover this (four times over).  More importantly, since I'm on call, that means I need someone to cover tomorrow morning.  Nate?  Alex?


## Mon, Oct 11 2021

### improvements for the views displaying only AU recipients with cicero codes
The changes Dave suggests are good ones, but I've looked into it and I'm not clear exactly where to put things and implement them.  

I'm pretty sure the method recommended by Dave goes here... ->  /app/helpers/promoted_mesage_helper.rb.  While we probably want this in the helper, for reference this is the controller for the views below, /app/controllers/messages/one_click/posts_controller.rb.

Here is the tree that leads to each piece of the UI affected by the cicero_code limitation.  I've put an arrow next to the 6 files with the repetitions.

- /app/views/promoter/messages/selected_recipients.html.erb
  - _australian_recipients_nav.html.erb
    - _house_recipient_selectors.html.erb  <-
    - _senate_recipient_selectors.html.erb  <-

- /app/views/promoter/messages/state_selector.js.erb
  - _state_selection
    - _state_upper.html.erb  <-
    - _state_lower.html.erb  <-

- /app/views/widgets/oneclick/messages/one_click/posts/index.html.erb
  - _click_to_post.html.erb  <-

- /app/views/promoter/messages/selected_recipients.html.erb
  - _selected_recipients.html.erb
    - _selected_recipients_list.html.erb  <-


#### Changes recommended by Dave
Since we're using similar logic to this in several places, and we might need to change them all at some point, I'm wondering if there's a way to wrap these blocks with a single check defined at the helper level, and then use only one method throughout the views:

```
  def conditionally_show_cicero_recipient(message, recipient, &block)
    if message.country.to_s == 'australia'
      if recipient.cicero_code.present? || recipient.model_type == 'CustomRecipient'
        proc[recipient]
      end
    else
      proc[recipient]
    end
  end
```
which you could then call with message and recipient params to conditionally render a block with a recipient r:

```
conditionally_show_cicero_recipient(@message, recipient) do |r|
<%= render :partial => 'whatever_partial', :locals => { :recipient => r } %>
end
```

It sounds like maybe the logical or check for model_type == 'CustomRecipient' could be part of the logic across the board, since it probably wouldn't cause false positive issues in the Australian target selectors where it's always false?

At any rate, if we wanted to change the logic when we have Cicero reps across the board, we could change just one helper method to implement the changes everywhere.


### rspec and our test suite
I am going to slowly work through running our entire test suite.  Piece by piece, initially.  Then all at once.  The aim here is to find the tests that aren't working on their own, then start working on the tests that don't run in a group.  I plan to have one of the below running most of the time until I'm much more familiar with the problem areas.

#### Found rspec issues
##### twitter related bugs here
```
rspec ./spec/features/widget/nodb_signature_spec.rb:140
rspec ./spec/features/widget/nodb_signature_spec.rb:150
```

#### Last run on Thu, Oct 14, no issues
```
rspec spec/features/widget_setup -fd

```

#### Last run on Thu, Oct 14, with issues
Run with 4 failures.  1 twitter.  2 are tests that run successfully for others in the spec/features/widget_signing/oneclick_widget_spec.rb.  4th is a problem testing the unsubscribe.  
```
rspec spec/features/widget_signing -fd
```

#### Last run on Thu, Oct 14, with group issues only
Run with 15 failures.  12 for end_to_end_messaging_spec.rb, 3 for multi_content_deliveries_spec.rb.  When those two files were run individually, there were no failures.
```
rspec spec/features/rabbitmq_deliveries -fd
```

#### Last run on Mon, Oct 11, no issues
```
rspec spec/features/widget -fd
rspec spec/libs/australia/ -fd
rspec spec/libs/importer_modules/ -fd
```

#### Not yet run
```
rspec spec/libs/ -fd
rspec spec/libs/* -fd
rspec spec/libs/nation_builder_sync/ -fd
rspec spec/libs/neon_client/ -fd
rspec spec/libs/nodb/ -fd
rspec spec/concerns/ -fd
rspec spec/controllers/ -fd
rspec spec/features/ -fd
rspec spec/features/* -fd
rspec spec/libs/ -fd
rspec spec/mailers/ -fd
rspec spec/models/ -fd
rspec spec/pdfs/ -fd
rspec spec/requests/ -fd
rspec spec/routing/ -fd
rspec spec/services/ -fd
rspec spec/services/* -fd
rspec spec/services/admin -fd
rspec spec/services/cwc -fd
rspec spec/services/promoter -fd
rspec spec/support/ -fd
rspec spec/* -fd
```

#### list of failures in spec/features/*
51 failures total, however,
17 in ./spec/features/rabbitmq_deliveries are successful when run individually.
7 in ./spec/features/widget are successful when run individually. (2 fail both ways)

Might find some low hanging fruit here.  Seems to be the bulk of the failures in /spec/features:

./spec/features/help_static_pages_spec.rb
./spec/features/signature_export_spec.rb
./spec/features/video_delivery_spec.rb


rspec './spec/features/help_static_pages_spec.rb[1:1:1:6]' # Help Actions Login active promoter with subscription and paid usage_plan logged in behaves like successful static page loads loads support page
rspec './spec/features/help_static_pages_spec.rb[1:2:1:6]' # Help Actions Login proxied promoter logged in behaves like successful static page loads loads support page
rspec './spec/features/help_static_pages_spec.rb[1:3:1:6]' # Help Actions Login promoter without email_blast_access logged in behaves like successful static page loads loads support page
rspec './spec/features/help_static_pages_spec.rb[1:4:1:6]' # Help Actions Login promoter with twilio_id logged in behaves like successful static page loads loads support page
rspec './spec/features/help_static_pages_spec.rb[1:5:1:6]' # Help Actions Login agency behaves like successful static page loads loads support page
rspec './spec/features/help_static_pages_spec.rb[1:6:1:6]' # Help Actions Login office of agency behaves like successful static page loads loads support page
rspec ./spec/features/rabbitmq_deliveries/email_delivery_end_to_end_spec.rb:110 # Delivery Agent Single recipient Failed delivery delivers to next priority address email -> web address
rspec ./spec/features/rabbitmq_deliveries/end_to_end_messaging_spec.rb:275 # End-to-end tests when there are no web_form_steps for web form when we have a backup email address gracefully fails the web_form send and sends an email
rspec ./spec/features/rabbitmq_deliveries/end_to_end_messaging_spec.rb:490 # End-to-end tests The always-fail form when the web_form fails when we have a backup email address completes an end-to-end send and sets archive_internal_message sent_at and saves archive_message bodycachd
rspec ./spec/features/rabbitmq_deliveries/end_to_end_messaging_spec.rb:834 # End-to-end tests Sending to Custom Recipients with constituents_only on in-city profile to local CustomRecipient completes an end-to-end send
rspec ./spec/features/rabbitmq_deliveries/end_to_end_messaging_spec.rb:896 # End-to-end tests Sending to Custom Recipients with constituents_only on in-state profile to one state CustomRecipient completes an end-to-end send
rspec ./spec/features/rabbitmq_deliveries/end_to_end_messaging_spec.rb:961 # End-to-end tests Sending to Custom Recipients with constituents_only on in-state profile to multiple state CustomRecipients completes an end-to-end send
rspec ./spec/features/rabbitmq_deliveries/end_to_end_messaging_spec.rb:1149 # End-to-end tests Sending to in-district US Congress recipients delivers an email
rspec ./spec/features/rabbitmq_deliveries/end_to_end_messaging_spec.rb:1862 # End-to-end tests End-to-end with Canadian Addresses for an L constituency in Toronto, Ontario when we sign & send the widget from Toronto, Ontario delivers the email directly
rspec ./spec/features/rabbitmq_deliveries/end_to_end_messaging_spec.rb:1956 # End-to-end tests End-to-end with Australian Addresses when we send to all of parliament from North Sydney, NSW delivers to the New South Wales Sen and Rep
rspec ./spec/features/rabbitmq_deliveries/end_to_end_messaging_spec.rb:2053 # End-to-end tests End-to-end with Australian Addresses when we send to all of parliament from Melbourne Ports, Victoria delivers to the Victoria Sen and Rep
rspec ./spec/features/rabbitmq_deliveries/end_to_end_messaging_spec.rb:2295 # End-to-end tests Email deliveries when our message has newline characters when it completes an end-to-end send preserves the newlines in the message body
rspec ./spec/features/rabbitmq_deliveries/end_to_end_messaging_spec.rb:2300 # End-to-end tests Email deliveries when our message has newline characters when it completes an end-to-end send verifies the sender in the message body
rspec ./spec/features/rabbitmq_deliveries/end_to_end_messaging_spec.rb:2471 # End-to-end tests Send with Verification Emails Disabled to a local CustomRecipient completes an end-to-end send
rspec ./spec/features/rabbitmq_deliveries/multi_content_deliveries_spec.rb:149 # Multi-Content Deliveries The messages delivered when we make regular (not batched or collated) deliveries for Email sends a different body and subject to recipients for content_one and content_two
rspec ./spec/features/rabbitmq_deliveries/multi_content_deliveries_spec.rb:420 # Multi-Content Deliveries with overlapping multi-content Groups content_one: All Republicans and content_two: All Senate delivers content_one to Republican Senators, content_two to Democratic Senators
rspec ./spec/features/rabbitmq_deliveries/multi_content_deliveries_spec.rb:476 # Multi-Content Deliveries The archival process saves multi_content archival info on the Conversion
rspec ./spec/features/rabbitmq_deliveries/video_delivery_end_to_end_spec.rb:56 # VideoDeliveryEndToEnd Single recipient sent through webmail after email failed
rspec ./spec/features/selected_recipients_spec.rb:295 # SelectedRecipient with selected_recipient_group 'AR' and constituents_only ...preceded by a recipient id  signing the Conversion
rspec ./spec/features/selected_recipients_spec.rb:296 # SelectedRecipient with selected_recipient_group 'AR' and constituents_only ...preceded by a recipient id  signing the Conversion
rspec ./spec/features/signature_export_spec.rb:40 # Signature Export to CSV with NoDB signatures the promoter pages selecting a start_month and end_month sends an email
rspec ./spec/features/signature_export_spec.rb:62 # Signature Export to CSV with NoDB signatures the promoter pages selecting a start_month and end_month creates a CSV
rspec ./spec/features/signature_export_spec.rb:52 # Signature Export to CSV with NoDB signatures the promoter pages selecting a start_month and end_month visiting 'CSV Exports' shows and links the CSV export
rspec ./spec/features/signature_export_spec.rb:71 # Signature Export to CSV with NoDB signatures the promoter pages selecting a start_month and end_month the CSV parses as a CSV
rspec ./spec/features/signature_export_spec.rb:75 # Signature Export to CSV with NoDB signatures the promoter pages selecting a start_month and end_month the CSV has a header row
rspec ./spec/features/signature_export_spec.rb:84 # Signature Export to CSV with NoDB signatures the promoter pages selecting a start_month and end_month the CSV includes specified records
rspec ./spec/features/signature_export_spec.rb:90 # Signature Export to CSV with NoDB signatures the promoter pages selecting a start_month and end_month the CSV excludes unspecified records
rspec ./spec/features/signature_export_spec.rb:109 # Signature Export to CSV with NoDB signatures the promoter pages UI Links when NoDBTransaction::USE_NODB_SYNCS_IN_UI is flipped to TRUE the reporting pages shows the new CSVs link in the Reporting pages
rspec ./spec/features/signature_export_spec.rb:118 # Signature Export to CSV with NoDB signatures the promoter pages UI Links when NoDBTransaction::USE_NODB_SYNCS_IN_UI is flipped to TRUE the dashboard doesn't show the old CSVs link in the Promoter Sidebar
rspec ./spec/features/signature_export_spec.rb:133 # Signature Export to CSV with NoDB signatures the promoter pages UI Links when NoDBTransaction::USE_NODB_SYNCS_IN_UI is flipped to FALSE the reporting pages shows the beta CSVs link in the Reporting pages
rspec ./spec/features/signature_export_spec.rb:142 # Signature Export to CSV with NoDB signatures the promoter pages UI Links when NoDBTransaction::USE_NODB_SYNCS_IN_UI is flipped to FALSE the dashboard shows the old CSVs link in the Promoter Sidebar
rspec ./spec/features/signature_export_spec.rb:151 # Signature Export to CSV with NoDB signatures the promoter pages UI Links when NoDBTransaction::USE_NODB_SYNCS_IN_UI is flipped to FALSE the old CSVs link links to the new beta CSVs
rspec ./spec/features/video_delivery_spec.rb:184 # VideoDeliveryTransaction send_video with a rubberstamped conversion with 1 recipient having 2 emails when the first email raises a non-email exception sends an agent alert email and doesn't try the second email
rspec ./spec/features/video_delivery_spec.rb:238 # VideoDeliveryTransaction send_video with a rubberstamped conversion with 1 recipient having 1 web_mail_address creates a service delivery
rspec ./spec/features/video_delivery_spec.rb:245 # VideoDeliveryTransaction send_video with a rubberstamped conversion with 1 recipient having 1 web_mail_address doesn't publish back to the receiver
rspec ./spec/features/video_delivery_spec.rb:294 # VideoDeliveryTransaction send_video with a rubberstamped conversion with 1 recipient having 1 web_mail_address and use_web_form_api == true when the request times out still returns a status message
rspec ./spec/features/widget/nodb_signature_spec.rb:34 # One Click Widgets with NoDB signatures enabled with verification off signing creates a NoDB signature
rspec ./spec/features/widget/nodb_signature_spec.rb:40 # One Click Widgets with NoDB signatures enabled with verification off signing the NoDB signature has Authenticated=''
rspec ./spec/features/widget/nodb_signature_spec.rb:62 # One Click Widgets with NoDB signatures enabled with verification off signing clicking 'Submit' after verifying by email the NoDB Signature has Authenticated='yes'
rspec ./spec/features/widget/nodb_signature_spec.rb:101 # One Click Widgets with NoDB signatures enabled with two messages signing and submitting message one creates one signature
rspec ./spec/features/widget/nodb_signature_spec.rb:110 # One Click Widgets with NoDB signatures enabled with two messages signing and submitting message one then signing message two creates another signature
rspec ./spec/features/widget/nodb_signature_spec.rb:116 # One Click Widgets with NoDB signatures enabled with two messages signing and submitting message one then signing message two NoDB Signature one doesn't change
rspec ./spec/features/widget/nodb_signature_spec.rb:126 # One Click Widgets with NoDB signatures enabled with two messages signing and submitting message one then signing message two NoDB Signature two shows new signature info
rspec ./spec/features/widget/nodb_signature_spec.rb:140 # One Click Widgets with NoDB signatures enabled with two messages signing and submitting message one then signing message two authenticating via Twitter the SenderProfile records the uid and sets confirmed_twitter to true
rspec ./spec/features/widget/nodb_signature_spec.rb:150 # One Click Widgets with NoDB signatures enabled with two messages signing and submitting message one then signing message two authenticating via Twitter NoDB Signature two records a twitter_handle
rspec ./spec/features/widget_signing/oneclick_widget_twitter_spec.rb:298 # Twitter transactions Service Calls post_to_all_pages with 2 Twitter pages shows 2 synced




## Thu, Oct 7 2021
### morning status
- [x] Worked through the various PR comments that came in on the UI work yesterday.  
- [x] The PR comments on the UI changes to stop showing the AU recipients without cicero codes led to me discovering FOUR other places this needed to be implemented.  This is done and checked in but needs another review.  Oddly, the rake task somehow got into this review though it had already been reviewed in another PR by Nate and Dave and subsequently merged, so I've responded to most of the comments, but not all.
- [x] Merged and deployed rake task, ON-1355.
- [x] Wrote explanation of consequences to the business of ON-1357...this turned into a writeup of all of the AU data issues and the solutions coming through as well as a heads up for support of the (probably very small) potential consequences of the solutions
- [x] Start running the rake task and looking at the data on production.  I've also generated a report of which AU recipients are to remain unchanged to compare with the lists of AU recipients that are to be de-activated.  With one exception, these are all duplicates, with the older records being de-activated.
- [x] Updated my Jiras
- [ ] The only thing I haven't gotten to is the Cicero import improvement to update first and last names.  Work is mostly done.  I need to get to the specs, ON-1359.  
- [ ] Maged suggested to rebase my branch ON-1357 to get the rake task out of there.  Nate offered his assistance if I run into problems.  


## Wed, Oct 6 2021
### morning status
- [x] Read and responded to Nate's PR reviews of ON-1355 (rake task).
- [x] Finished KnowWho data import.
- [x] Create specs for no longer displaying the non-cicero AU recipients in the UI, ON-1357.
- [x] Create PR for those UI changes, ON-1357.
- [ ] Working through the various PR comments that came in on the UI work yesterday.  Almost done.
- [ ] Merge and deploy rake task, ON-1355.
- [ ] I haven't yet gotten back to the Cicero import improvement to update first and last names.  Work is mostly done.  I need to get to the specs, ON-1359.  
- [ ] Write explanation of consequences to the business of ON-1357.
- [ ] Start running the rake task and looking at the data on production.
- [ ] Update my Jiras

### notes for UI changes for AU recipients with no cicero code
There are 3 bugs in the data and/or code that have been diagnosed as contributing to the issues seen by clients that have led to concerns with Cicero's imported Australia data.  The three diagnosed causes are:

**Bug #1**. Duplications caused by old recipients with no Cicero code present in the database.  

**Bug #2**. Many recipient first names are abbreviated.  These are older, valid records with Cicero codes.  The Australian State Council has most of these.  For example, 'Mason-Cox, M. R.' and 'Ward, N. P.'.  Depending on how the client searches for the recipients, the recipient being looked for will not come up in the UI.  

**Bug #3**. The UI displays recipients that don't have Cicero codes.  No codes mean these recipients don't get updated by the Cicero import and are thus out of date and in all cases but 1 are duplicates of valid recipient records.

Solutions for each of the above are nearly complete.  

**Solution #1**, all recipients with no Cicero code present will be de-activated.  This will affect only 43 recipients.  40 of these are Australia House of Representative recipients that are duplicates.  3 of these are Australia State Assembly recipients.  2 of which are duplicates and 1 isn't a duplicate, but hasn't changed since 2018.  The list of active AU recipients both with and without Cicero code is available if desired.  This fix is ready to switch on with the approval of the Business side.

**Solution #2**, the Australia Cicero import script is being changed to update first and last name.  This will have the additional benefit of updating last names for marriage associated name changes.  This fix is in progress and will be ready in time for the arrival of the new Cicero data on Oct 11.

**Solution #3**, the campaign targeting page will no longer display recipients without Cicero codes, with the exception of custom recipients.  Also, the widget will no longer display these invalid recipients.  This fix is code complete and under engineering review.

There is the possibility that these old and out of date recipient records have already been added to existing campaigns.  This cannot be straightforwardly fixed due to the extreme number of campaigns in the system.  This is a fix going forward for new campaigns as well as for adding recipients to existing campaigns.  

***Support should be aware that if an issue comes in for a recipient no longer being shown in Selected Targets section that was present before this fix goes through, it was almost certainly one of these 43 old and out of date AU recipients.  Support should tell the client to re-add the recipient explaining there was some recent DB cleanup of duplicates.***


## Tue, Oct 5 2021
### morning status
- I got some PRs reviewed.
- I’m partway through the KnowWho data import.
- I got the additional Jira tickets created.
- I’m in the middle of the Cicero import improvement to update first and last names.  Work is mostly done.  I need to get to the specs.
- Hope to merge and deploy this morning; thank you Nate for your planned review of the recipient deactivation rake task.
- The UI fixes are in place for no longer displaying the non-cicero AU recipients; these are the tests I’m working on.

### current status
- [x] Read and respond to Nate's PR revies of ON-1355 (rake task).
- [x] Finish KnowWho data import.
- [x] Update top of ON-1355 (rake task) Jira.
- [ ] I’m in the middle of the Cicero import improvement to update first and last names.  Work is mostly done.  I need to get to the specs, ON-1359.  
- [ ] Merge and deploy rake task, ON-1355.
- [x] Create specs for no longer displaying the non-cicero AU recipients in the UI, ON-1357.
- [x] Create PR for the UI changes, ON-1357.
- [ ] Write explanation of consequences to the business of ON-1357.
- [ ] Addressing PR comments.

### new Jira
Dave made a good suggestion in the PR for the rake task (ON-1355). Improve the deactivate_au_recipients_with_no_cicero_code.rake task by putting the logic into a service object and then write tests against that.  I've created a Jira ticket for this as soon as this rake task gets touched again, if it does, for CA or US data.


## Mon, Oct 4 2021

### status

#### today's todo list
- [x] separate this into three tickets, [ON-1355](https://oneclickpolitics.atlassian.net/browse/ON-1355)
  - [x] rake task to inactivate AU recipients without cicero code, [ON-1355](https://oneclickpolitics.atlassian.net/browse/ON-1355)
  - [x] fix UI displaying active recipients without cicero code (plus specs?), [ON-1357](https://oneclickpolitics.atlassian.net/browse/ON-1357)
  - [x] change AU import to update first/last names (plus specs) [ON-1359](https://oneclickpolitics.atlassian.net/browse/ON-1359)
- [x] I need to review a PR or two
- [x] kick off the KnowWho data import
- [ ] finish the KnowWho data import
- [ ] diving back into Cicero to get the first and last names updated on import, ON-1359
- [ ] I’m going to merge my PR for the rake task de-activating the AU recipients without cicero ids and start using it to look at the data on prod, ON-1355 Get this to Dave asap.
- [ ] check in UI code for ON-1357
- [ ] write up explanation for ON-1357 for the business


### running full rspec test suite
Useful comands for running the full test suite, with and without the slow tests
```
alias test_suite="docker-compose exec ocp bundle exec rspec spec"
alias slow_tests="docker-compose exec ocp bundle exec rspec spec --tag slow_tests"
alias fast_tests="docker-compose exec ocp bundle exec rspec spec --tag '~slow_tests'"
```

## Thu, Sep 30 2021

### useful snippet for batching data on prod console
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


## Wed, 7 Jul 2021

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


## Tue, 6 Jul 2021

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
