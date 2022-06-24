## Various commands for everything NationBuilder

### count how many conversions need tag sync
```
@epoch = '2019-06-18T23:19'
@epoch_id ||= Conversion.where("created_at > ?", @epoch).first.try(:id) || 1
@apocalypse = '3000-12-31T23:19'
@apocalypse_id ||= Conversion.where("created_at > ?", @apocalypse).first.try(:id) || Conversion.last.try(:id) || 1000000000

Dir[Rails.root.join("lib/nation_builder_client/**/*.rb")].each {|f| require f}
Dir[Rails.root.join("lib/jobs/nation_builder_sync/**/*.rb")].each {|f| require f}

promoter = PromoterUser.find 39528

promoter.conversions.where('conversions.id >= ?', @epoch_id).where('conversions.id <= ?', @apocalypse_id).where('conversions.promoted_message_id IS NOT NULL').includes(:promoted_message).includes(advocate_profile: [:advocate_for_promoters, :state, :external_connections]).where('conversions.nation_builder_tag_synced = ?', false).where('conversions.nation_builder_unsyncable = ?', false).where('advocate_for_promoters.opt_in_id IS NOT NULL').count
```

### how to go from slug to promoter user id in order to confirm syncs are succeeding
```
slug = 'mofc'
Authentication.where(uid: "mofc")
Account.find 7032094
agency = Agency.where(account_id: 7032094).last

promoter_user_id = agency.id
promoter_user_name = agency.name
```

### checking for NB slug and token authentication credentials in our system
```
user = 40793
PromoterUser.find(user).master_account.authentications

PromoterUser.where(agency_id: user)
```

### search for recent NB syncs for this promoter
```
NationBuilderSynchronizeCall.where(promoter_user_id: user).where("created_at > ?", 7.days.ago)
```

### our OCP NB credentials for our own syncing
These are good for practicing calls in the NB API website
```
slug: oneclickpolitics, token: 1467df86991cc7567d23d6555880b1afedccacdd7bb2fe9f326325bf12203c52
=> [#<Authentication id: 435, account_id: 4367, provider: "nation_builder", uid: "oneclickpolitics", created_at: "2013-09-13 01:54:26", updated_at: "2017-04-23 18:47:18", active: nil, token: "1467df86991cc7567d23d6555880b1afedccacdd7bb2fe9f326...", expires_at: nil, refresh_token: nil, write_access: true, instance_url: nil, extra: nil>]
```

### run a sync for a given promoter
```
user = 39516
RAILS_ENV=production bundle exec rake nation_builder_sync:sync_one[39516] &
bundle exec rake nation_builder_sync:sync_one[
] RAILS_ENV=production
```

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

### who are the NB sync promoters
```
promoter_ids = []
NationBuilderSync.syncable_promoters.each do |promoter|
  promoter_ids.append promoter.id
end
irb(main):029:0> promoter_ids
=> [12643, 36311, 38991, 39521, 23691, 39516, 39529, 39518, 39168, 39169, 39171, 39170, 39082, 39282, 39288, 29631, 40468, 319, 7320, 25179, 12537, 12174, 40476, 24403, 39610, 39523, 39517, 39524, 39520, 39528, 39522, 39519, 40066, 40449, 40326, 40553, 40563, 40581, 36120, 40592, 40601, 40645, 40654, 36896, 37916, 37862, 38023, 10958, 35975, 37990, 39667, 39538, 39387, 39543, 39634, 20176, 39674, 39549, 39653, 39556, 16660, 39754, 13607, 39686, 39811, 39557, 39846, 39850, 39703, 39911, 7225, 39967, 40015, 40021, 39960, 39896, 40196, 40190, 40218, 40796
```

#### how many conversions for all NB sync promoters
Remember to set up the constants such as @epoch before running the commands below
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
Remember to set up the constants such as @epoch before running the commands below
```
promoter = PromoterUser.find 40793
promoter = PromoterUser.find 20176
promoter = PromoterUser.find 39516

promoter.conversions.includes(advocate_profile: [:advocate_for_promoters, :state, :external_connections]).where('conversions.id >= ?', @epoch_id).where('conversions.id <= ?', @apocalypse_id).where('conversions.nation_builder_email_synced = ?', false).where('conversions.nation_builder_unsyncable = ?', false).where('advocate_for_promoters.opt_in_id IS NOT NULL').count
```

### NB sync current count
```
irb(main):022:0> promoters_conversion_count_hash
=> {"12643"=>0, "36311"=>0, "38991"=>1, "39521"=>0, "23691"=>0, "39516"=>0, "39529"=>0, "39518"=>0, "39168"=>0, "39170"=>0, "39171"=>0, "39169"=>226119, "39082"=>0, "39282"=>0, "39288"=>0, "29631"=>0, "40468"=>0, "319"=>0, "7320"=>0, "25179"=>0, "12537"=>0, "12174"=>3, "40476"=>0, "24403"=>0, "39610"=>0, "39523"=>5, "39517"=>0, "39524"=>0, "39520"=>0, "39528"=>0, "39522"=>1, "39519"=>0, "40066"=>0, "40449"=>0, "40326"=>0, "40553"=>0, "40563"=>0, "40581"=>0, "36120"=>0, "40592"=>0, "40601"=>0, "40645"=>0, "40654"=>0, "36896"=>0, "37916"=>0, "37862"=>0, "38023"=>0, "10958"=>0, "35975"=>0, "37990"=>0, "39667"=>0, "39538"=>0, "39387"=>0, "39543"=>0, "39634"=>0, "20176"=>7610, "39674"=>0, "39549"=>0, "39653"=>0, "39556"=>0, "16660"=>0, "39754"=>0, "13607"=>0, "39686"=>249, "39811"=>0, "39557"=>0, "39846"=>0, "39850"=>0, "39703"=>0, "39911"=>0, "7225"=>0, "39967"=>0, "40015"=>0, "40021"=>0, "39960"=>0, "39896"=>0, "40196"=>0, "40190"=>0, "40218"=>0, "40796"=>0}
```


```
e = promoters_conversion_count_hash
h = promoters_conversion_count_hash
e = h.keep_if
=> #<Enumerator: {"12643"=>0, "36311"=>0, "38991"=>1, "39521"=>0, "23691"=>0, "39516"=>1, "39529"=>0, "39518"=>0, "39168"=>0, "39169"=>240237, "39171"=>0, "39170"=>0, "39082"=>0, "39282"=>0, "39288"=>7, "29631"=>0, "40468"=>0, "319"=>0, "7320"=>0, "25179"=>1200, "12537"=>0, "12174"=>4, "40476"=>0, "24403"=>0, "39610"=>0, "39523"=>5, "39517"=>18, "39524"=>3, "39520"=>2, "39528"=>60, "39522"=>29, "39519"=>10, "40066"=>1, "40449"=>0, "40326"=>4, "40553"=>0, "40563"=>0, "40581"=>9, "36120"=>0, "40592"=>0, "40601"=>0, "40645"=>0, "40654"=>0, "36896"=>0, "37916"=>0, "37862"=>0, "38023"=>0, "10958"=>0, "35975"=>0, "37990"=>0, "39667"=>0, "39538"=>0, "39387"=>1, "39543"=>0, "39634"=>0, "20176"=>14512, "39674"=>0, "39549"=>0, "39653"=>0, "39556"=>0, "16660"=>0, "39754"=>1, "13607"=>330, "39686"=>289, "39811"=>0, "39557"=>0, "39846"=>0, "39850"=>0, "39703"=>6, "39911"=>0, "7225"=>1, "39967"=>0, "40015"=>0, "40021"=>0, "39960"=>0, "39896"=>0, "40196"=>0, "40190"=>5, "40218"=>0, "40796"=>0}:keep_if>

e = promoters_conversion_count_hash
e.each { |key, value| value != 0 }
=> {"38991"=>1, "39516"=>1, "39169"=>240237, "39288"=>7, "25179"=>1200, "12174"=>4, "39523"=>5, "39517"=>18, "39524"=>3, "39520"=>2, "39528"=>60, "39522"=>29, "39519"=>10, "40066"=>1, "40326"=>4, "40581"=>9, "39387"=>1, "20176"=>14512, "39754"=>1, "13607"=>330, "39686"=>289, "39703"=>6, "7225"=>1, "40190"=>5}

h = {"12643"=>nil, "36311"=>nil, "38991"=>135, "39521"=>nil, "55555"=>"", "44444"=>" "}
h = promoters_conversion_count_hash
e = h.keep_if
e.each { |key, value| !value.nil? }

foo = h.keep_if.each { |key, value| !value.nil? }
```


```
RAILS_ENV=production bundle exec rake nation_builder_sync:sync_one[39169] &
```

## NationBuilder API
Proof that the NB API can successfully accept `prefix`, even custom ones.

PUT Update/people/:id
```
{
  "person": {
    "email": "sprestage7@example.com",
    "prefix": "Captain",
    "last_name": "Susan",
    "first_name": "Prestage",
    "sex": "F",
    "registered_address": {
      "state": "WA",
      "country_code": "US"
    }
  }
}
```

response body
```
{
    "person": {
        "birthdate": null,
        "city_district": null,
        "civicrm_id": null,
        "county_district": null,
        "county_file_id": null,
        "created_at": "2022-06-08T13:54:12-04:00",
        "datatrust_id": null,
        "do_not_call": false,
        "do_not_contact": false,
        "dw_id": null,
        "email": "sprestage7@example.com",
        "email_opt_in": true,
        "employer": null,
        "external_id": null,
        "federal_district": null,
        "fire_district": null,
        "first_name": "Prestage",
        "has_facebook": false,
        "id": 98901,
        "is_twitter_follower": false,
        "is_volunteer": false,
        "judicial_district": null,
        "labour_region": null,
        "last_name": "Susan",
        "linkedin_id": null,
        "mobile": null,
        "mobile_opt_in": null,
        "middle_name": "",
        "nbec_guid": null,
        "ngp_id": null,
        "note": null,
        "occupation": null,
        "party": null,
        "pf_strat_id": null,
        "phone": null,
        "precinct_id": null,
        "primary_address": {
            "address1": null,
            "address2": null,
            "address3": null,
            "city": null,
            "county": null,
            "state": "WA",
            "country_code": "US",
            "zip": null,
            "lat": null,
            "lng": null,
            "fips": null,
            "street_number": null,
            "street_prefix": null,
            "street_name": null,
            "street_type": null,
            "street_suffix": null,
            "unit_number": null,
            "zip4": null,
            "zip5": null,
            "sort_sequence": null,
            "delivery_point": null,
            "lot": null,
            "carrier_route": null
        },
        "profile_image_url_ssl": "https://assets.nationbuilder.com/assets/notifier/profile-avatar.png",
        "recruiter_id": null,
        "rnc_id": null,
        "rnc_regid": null,
        "salesforce_id": null,
        "school_district": null,
        "school_sub_district": null,
        "sex": "F",
        "signup_type": 0,
        "state_file_id": null,
        "state_lower_district": null,
        "state_upper_district": null,
        "support_level": null,
        "supranational_district": null,
        "tags": [],
        "twitter_id": null,
        "twitter_name": null,
        "updated_at": "2022-06-08T13:54:12-04:00",
        "van_id": null,
        "village_district": null,
        "ward": null,
        "work_phone_number": null,
        "active_customer_expires_at": null,
        "active_customer_started_at": null,
        "author": null,
        "author_id": null,
        "auto_import_id": null,
        "availability": null,
        "ballots": [],
        "banned_at": null,
        "billing_address": null,
        "bio": null,
        "call_status_id": null,
        "call_status_name": null,
        "capital_amount_in_cents": 0,
        "children_count": 0,
        "church": null,
        "city_sub_district": null,
        "closed_invoices_amount_in_cents": 0,
        "closed_invoices_count": null,
        "contact_status_id": null,
        "contact_status_name": null,
        "could_vote_status": false,
        "demo": null,
        "donations_amount_in_cents": null,
        "donations_amount_this_cycle_in_cents": null,
        "donations_count": null,
        "donations_count_this_cycle": null,
        "donations_pledged_amount_in_cents": null,
        "donations_raised_amount_in_cents": null,
        "donations_raised_amount_this_cycle_in_cents": null,
        "donations_raised_count": null,
        "donations_raised_count_this_cycle": null,
        "donations_to_raise_amount_in_cents": null,
        "email1": "sprestage7@example.com",
        "email1_is_bad": false,
        "email2": null,
        "email2_is_bad": false,
        "email3": null,
        "email3_is_bad": false,
        "email4": null,
        "email4_is_bad": false,
        "emails": [
            {
                "email_address": "sprestage7@example.com",
                "email_number": 1,
                "is_bad": false,
                "is_primary": true
            }
        ],
        "ethnicity": null,
        "facebook_address": null,
        "facebook_profile_url": null,
        "facebook_updated_at": null,
        "facebook_username": null,
        "fax_number": null,
        "federal_donotcall": false,
        "first_donated_at": null,
        "first_fundraised_at": null,
        "first_invoice_at": null,
        "first_prospect_at": null,
        "first_recruited_at": null,
        "first_supporter_at": "2022-06-08T13:54:12-04:00",
        "first_volunteer_at": null,
        "full_name": "Prestage Susan",
        "home_address": null,
        "import_id": null,
        "inferred_party": null,
        "inferred_support_level": null,
        "invoice_payments_amount_in_cents": 0,
        "invoice_payments_referred_amount_in_cents": 0,
        "invoices_amount_in_cents": 0,
        "invoices_count": null,
        "is_absentee_voter": null,
        "is_active_voter": null,
        "is_deceased": false,
        "is_donor": false,
        "is_dropped_from_file": null,
        "is_early_voter": null,
        "is_fundraiser": false,
        "is_ignore_donation_limits": false,
        "is_leaderboardable": true,
        "is_mobile_bad": false,
        "is_permanent_absentee_voter": null,
        "is_possible_duplicate": false,
        "is_profile_private": false,
        "is_profile_searchable": true,
        "is_prospect": false,
        "is_supporter": true,
        "is_survey_question_private": false,
        "language": null,
        "last_call_id": null,
        "last_contacted_at": null,
        "last_contacted_by": null,
        "last_donated_at": null,
        "last_fundraised_at": null,
        "last_invoice_at": null,
        "last_rule_violation_at": null,
        "legal_name": null,
        "locale": null,
        "mailing_address": null,
        "marital_status": null,
        "media_market_name": null,
        "meetup_id": null,
        "meetup_address": null,
        "mobile_normalized": null,
        "nbec_precinct_code": null,
        "nbec_precinct": null,
        "note_updated_at": null,
        "outstanding_invoices_amount_in_cents": 0,
        "outstanding_invoices_count": null,
        "overdue_invoices_count": 0,
        "page_slug": null,
        "parent": null,
        "parent_id": null,
        "party_member": null,
        "phone_normalized": null,
        "phone_time": null,
        "precinct_code": null,
        "precinct_name": null,
        "prefix": "Captain",
        "previous_party": null,
        "primary_email_id": 1,
        "priority_level": null,
        "priority_level_changed_at": null,
        "profile_content": null,
        "profile_content_html": null,
        "profile_headline": null,
        "received_capital_amount_in_cents": 0,
        "recruiter": null,
        "recruits_count": 0,
        "registered_address": {
            "address1": null,
            "address2": null,
            "address3": null,
            "city": null,
            "county": null,
            "state": "WA",
            "country_code": "US",
            "zip": null,
            "lat": null,
            "lng": null,
            "fips": null,
            "street_number": null,
            "street_prefix": null,
            "street_name": null,
            "street_type": null,
            "street_suffix": null,
            "unit_number": null,
            "zip4": null,
            "zip5": null,
            "sort_sequence": null,
            "delivery_point": null,
            "lot": null,
            "carrier_route": null
        },
        "registered_at": null,
        "religion": null,
        "rule_violations_count": 0,
        "signup_sources": [],
        "spent_capital_amount_in_cents": 0,
        "submitted_address": null,
        "subnations": [],
        "suffix": null,
        "support_level_changed_at": null,
        "support_probability_score": null,
        "township": null,
        "turnout_probability_score": null,
        "twitter_address": null,
        "twitter_description": null,
        "twitter_followers_count": null,
        "twitter_friends_count": null,
        "twitter_location": null,
        "twitter_login": null,
        "twitter_updated_at": null,
        "twitter_website": null,
        "unsubscribed_at": null,
        "user_submitted_address": null,
        "username": null,
        "voter_updated_at": null,
        "warnings_count": 0,
        "website": null,
        "work_address": null
    },
    "precinct": null
}
```
