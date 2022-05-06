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
user = 39519
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
