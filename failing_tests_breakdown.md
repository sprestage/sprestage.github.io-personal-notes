# Total tests failing
180 as of 4pm, Jun 7

# simple test runs
see end of file for tests that only fail in bulk runs


## rspec ./spec/libs/nodb/
Try these individually since I saw a lot of failures here when run in bulk as spec/libs

36 examples, 0 failures

Coverage report generated for RSpec to /ocp/coverage. 12652 / 34302 LOC (36.88%) covered.


## rspec ./spec/libs/neon_client/
Try these individually since I saw a lot of failures here when run in bulk as spec/libs

172 examples, 0 failures, 1 pending

Coverage report generated for RSpec to /ocp/coverage. 13339 / 35105 LOC (38.0%) covered.


## rspec ./spec/libs/nation_builder_sync/
Try these individually since I saw a lot of failures here when run in bulk as spec/libs

Finished in 2 minutes 54.8 seconds (files took 41.3 seconds to load)
274 examples, 0 failures

Coverage report generated for RSpec to /ocp/coverage. 13427 / 35430 LOC (37.9%) covered.
Fri Jun 10 20:57:14 UTC 2022


## rspec ./spec/libs/importer_modules/
Try these individually since I saw a lot of failures here when run in bulk as spec/libs

1085 examples, 0 failures, 5 pending

Coverage report generated for RSpec to /ocp/coverage. 17720 / 38965 LOC (45.48%) covered.


## spec/concerns

46 examples, 0 failures

Coverage report generated for RSpec to /ocp/coverage. 12011 / 34107 LOC (35.22%) covered.


## spec/controllers

752 examples, 0 failures, 2 pending

Coverage report generated for RSpec to /ocp/coverage. 19784 / 38069 LOC (51.97%) covered.


## spec/models

990 examples, 0 failures, 2 pending

Coverage report generated for RSpec to /ocp/coverage. 19758 / 39572 LOC (49.93%) covered.


## spec/mailers

3 examples, 0 failures

Coverage report generated for RSpec to /ocp/coverage. 11793 / 33937 LOC (34.75%) covered.


## spec/requests

55 examples, 0 failures

Coverage report generated for RSpec to /ocp/coverage. 12788 / 34219 LOC (37.37%) covered.


## spec/tasks

1 example, 0 failures

Coverage report generated for RSpec to /ocp/coverage. 13258 / 42895 LOC (30.91%) covered.


## spec/features
Finished in 41 minutes 16 seconds (files took 46.8 seconds to load)
2909 examples, 2 failures, 153 pending

Failed examples:

rspec ./spec/features/preserve_newlines_spec.rb:16 # An HTML-based email view preserves newlines
rspec ./spec/features/video_delivery_spec.rb:238 # VideoDeliveryTransaction send_video with a rubberstamped conversion with 1 recipient having 1 web_mail_address creates a service delivery

Coverage report generated for RSpec to /ocp/coverage. 37469 / 50867 LOC (73.66%) covered.
SimpleCov failed with exit 1

Fri Jun 10 19:38:02 UTC 2022


## spec/services

Finished in 4 minutes 49.7 seconds (files took 43.94 seconds to load)
525 examples, 2 failures

Failed examples:

rspec ./spec/services/advocate_universe_service_spec.rb:37 # retrieve advocates for country map successful calls should return advocates for a promoter
rspec ./spec/services/retrieve_activity_stream_spec.rb:34 # retrieve activity stream successful calls retrieves activity stream correctly

Coverage report generated for RSpec to /ocp/coverage. 18356 / 38063 LOC (48.23%) covered.
SimpleCov failed with exit 1
Fri Jun 10 20:37:42 UTC 2022


## spec/libs/*.rb
Try these individually since I saw a lot of failures here when run as spec/libs

536 examples, 232 failures

Failed examples:

rspec ./spec/libs/agg_legislator_tables_updater_spec.rb:120 # Updating agg legislator tables the inner agg methods connection to archive_db successfully runs insert_dummy_data_legislator_promoted_message_activity_archive_db AND update_agg_legislator_promoted_message_activity_by_day_from_archive_db for multiple days
rspec ./spec/libs/agg_legislator_tables_updater_spec.rb:200 # Updating agg legislator tables the inner agg methods connection to archive_db successfully updates update_agg_legislator_promoted_message_activity_by_day_from_archive_db for multi_content columns
rspec ./spec/libs/agg_legislator_tables_updater_spec.rb:278 # Updating agg legislator tables the inner agg methods connection to ocp_db when calls run for multiple days promoted_message level ETLs successfully runs insert_dummy_data_legislator_promoted_message_activity_ocp_db AND agg_legislator_promoted_message_specific_activity_by_day AND update_non_agg_columns_for_agg_legislator_promoted_message_activity_by_day for multiple days
rspec ./spec/libs/agg_legislator_tables_updater_spec.rb:446 # Updating agg legislator tables the inner agg methods connection to ocp_db when calls run for multiple days promoter level ETLs successfully runs insert_dummy_data_agg_legislator_promoter_activity_by_day AND update_agg_legislator_promoter_activity_by_day
rspec ./spec/libs/agg_legislator_tables_updater_spec.rb:578 # Updating agg legislator tables the inner agg methods connection to ocp_db when calls run for multiple days promoter level ETLs successfully updates with update_agg_legislator_promoter_activity_by_day for multi_content
rspec ./spec/libs/agg_legislator_tables_updater_spec.rb:656 # Updating agg legislator tables the inner agg methods connection to ocp_db when run on one day only will insert values for one day
rspec ./spec/libs/agg_profile_tables_updater_spec.rb:42 # Updating agg profile tables Top level ETL methods logs errors raised in inner methods of update_advocate_profile_tables_through_time
rspec ./spec/libs/agg_profile_tables_updater_spec.rb:80 # Updating agg profile tables Inner SQL should correctly insert_non_email_data_agg_promoted_message_by_advocate_activity
rspec ./spec/libs/agg_profile_tables_updater_spec.rb:143 # Updating agg profile tables Inner SQL should correctly insert_email_dummy_data_agg_promoted_message_by_advocate_activity
rspec ./spec/libs/agg_profile_tables_updater_spec.rb:211 # Updating agg profile tables Inner SQL should correctly update_non_email_data_agg_promoted_message_by_advocate_activity AND update_email_data_agg_promoted_message_by_advocate_activity
rspec ./spec/libs/agg_profile_tables_updater_spec.rb:352 # Updating agg profile tables Inner SQL should run update_advocate_for_promoters_activity
rspec ./spec/libs/agg_profile_tables_updater_spec.rb:429 # Updating agg profile tables Inner SQL should clean_agg_promoted_message_by_advocate_activity
rspec ./spec/libs/bad_address_updater_spec.rb:22 # BadAddressUpdater get_qualified_addresses a good EmailAddress
rspec ./spec/libs/bad_address_updater_spec.rb:28 # BadAddressUpdater get_qualified_addresses an EmailAddress updated recently
rspec ./spec/libs/bad_address_updater_spec.rb:34 # BadAddressUpdater get_qualified_addresses an EmailAddress for an inactive Recipient
rspec ./spec/libs/bad_address_updater_spec.rb:40 # BadAddressUpdater get_qualified_addresses an EmailAddress with .bad_address_type='Permanent...'
rspec ./spec/libs/bad_address_updater_spec.rb:45 # BadAddressUpdater get_qualified_addresses an EmailAddress with none of the above
rspec ./spec/libs/bad_address_updater_spec.rb:54 # BadAddressUpdater call updates .bad_address_flg=false
rspec ./spec/libs/bad_address_updater_spec.rb:58 # BadAddressUpdater call blanks .bad_address_type
rspec ./spec/libs/cache_advocates_for_country_map_spec.rb:12 # cache advocates for country map successful calls should log time for successful daily_advocates_for_map_cache_update
rspec ./spec/libs/cache_advocates_for_country_map_spec.rb:23 # cache advocates for country map successful calls should successfully run daily_advocates_for_map_cache_update
rspec ./spec/libs/cache_advocates_for_country_map_spec.rb:52 # cache advocates for country map errors should log errors when failed call to daily_advocates_for_map_cache_update
rspec ./spec/libs/import_advocates_spec.rb:30 # ImportAdvocates with a custom field processes all rows
rspec ./spec/libs/import_advocates_spec.rb:38 # ImportAdvocates with a custom field running creates an 'Initial Import' message
rspec ./spec/libs/import_advocates_spec.rb:42 # ImportAdvocates with a custom field running creates a CustomField
rspec ./spec/libs/import_advocates_spec.rb:46 # ImportAdvocates with a custom field running adds the custom field to the 'Initial Import' message
rspec ./spec/libs/import_advocates_spec.rb:50 # ImportAdvocates with a custom field running doesn't add the custom field to other messages
rspec ./spec/libs/import_advocates_spec.rb:58 # ImportAdvocates with a custom field when the first row throws an exception stops the sync
rspec ./spec/libs/import_bioguide_ids_spec.rb:23 # ImportBioguideIds creates a problem if there is no recipient found
rspec ./spec/libs/import_bioguide_ids_spec.rb:38 # ImportBioguideIds when there are recipients with matching fec_ids but not matching offices creates a problem
rspec ./spec/libs/import_bioguide_ids_spec.rb:55 # ImportBioguideIds when there are recipients with matching fec_ids and matching offices but multiple recipient matches creates a problem
rspec ./spec/libs/import_bioguide_ids_spec.rb:62 # ImportBioguideIds when there are recipients with matching fec_ids and matching offices (one recipient match) doesn't create a problem
rspec ./spec/libs/import_bioguide_ids_spec.rb:67 # ImportBioguideIds when there are recipients with matching fec_ids and matching offices (one recipient match) doesn't save the bioguide_ids by default
rspec ./spec/libs/import_bioguide_ids_spec.rb:75 # ImportBioguideIds when there are recipients with matching fec_ids and matching offices (one recipient match) with record: true saves the bioguide_ids
rspec ./spec/libs/import_city_council_districts_spec.rb:14 # import city council districts successful calls to ImportCityCouncilDistricts should create a new 'District' object when a District object doesn't already exist for that City Council Ward
rspec ./spec/libs/import_city_council_districts_spec.rb:44 # import city council districts successful calls to ImportCityCouncilDistricts should update current 'District' object with new geom when a District object already exists for that City Council Ward
rspec ./spec/libs/import_city_council_districts_spec.rb:88 # import city council districts failed calls to RetrieveLegislatorAggregateData should respond with an error for when no geom_name passed in
rspec ./spec/libs/import_city_council_districts_spec.rb:94 # import city council districts failed calls to RetrieveLegislatorAggregateData should respond with an error for when no abbreviation passed in
rspec ./spec/libs/import_city_council_districts_spec.rb:100 # import city council districts failed calls to RetrieveLegislatorAggregateData should respond with an error for when no state_fips_code passed in
rspec ./spec/libs/import_city_council_districts_spec.rb:106 # import city council districts failed calls to RetrieveLegislatorAggregateData should respond with an error for when no city_name passed in
rspec ./spec/libs/import_city_council_districts_spec.rb:112 # import city council districts failed calls to RetrieveLegislatorAggregateData should respond with an error for when no possible_city_names passed in
rspec ./spec/libs/import_city_council_districts_spec.rb:118 # import city council districts failed calls to RetrieveLegislatorAggregateData should respond with an error for when no district_identifier_column passed in
rspec ./spec/libs/import_city_council_districts_spec.rb:124 # import city council districts failed calls to RetrieveLegislatorAggregateData should respond with an error for when no state_id passed in
rspec ./spec/libs/import_legislator_profiles_spec.rb:31 # ImportLegislatorProfiles with level: 'state' gets the state CSV's
rspec ./spec/libs/import_legislator_profiles_spec.rb:39 # ImportLegislatorProfiles with the default (no level parameter)' gets the federal CSV's
rspec ./spec/libs/import_legislator_profiles_spec.rb:47 # ImportLegislatorProfiles with the default (no record parameter) does not update any fields
rspec ./spec/libs/import_legislator_profiles_spec.rb:57 # ImportLegislatorProfiles with 'record: true' updates the recipient's title field
rspec ./spec/libs/import_legislator_profiles_spec.rb:62 # ImportLegislatorProfiles with 'record: true' creates a RecipientBio
rspec ./spec/libs/import_legislator_profiles_spec.rb:96 # ImportLegislatorProfiles with 'record: true' creates 3 RecipientOffices
rspec ./spec/libs/import_legislator_profiles_spec.rb:101 # ImportLegislatorProfiles with 'record: true' fills in the RecipientOffice fields
rspec ./spec/libs/import_legislator_profiles_spec.rb:113 # ImportLegislatorProfiles with 'record: true' creates 14 Staffers
rspec ./spec/libs/import_legislator_profiles_spec.rb:118 # ImportLegislatorProfiles with 'record: true' fills in the Staffer fields
rspec ./spec/libs/import_legislator_profiles_spec.rb:79 # ImportLegislatorProfiles with 'record: true' with an existing RecipientBio doesn't create a new RecipientBio
rspec ./spec/libs/import_legislator_profiles_spec.rb:84 # ImportLegislatorProfiles with 'record: true' with an existing RecipientBio updates the RecipientBio
rspec ./spec/libs/import_legislator_profiles_spec.rb:89 # ImportLegislatorProfiles with 'record: true' with an existing RecipientBio doesn't overwrite an existing value with a blank one
rspec ./spec/libs/import_legislator_profiles_spec.rb:137 # ImportLegislatorProfiles with 'record: true' when the same person appears twice in one row creates one Staffer for each
rspec ./spec/libs/import_legislator_profiles_spec.rb:152 # ImportLegislatorProfiles clear_existing_profiles should destroy all recipient bios, staffers, and recipient offices
rspec ./spec/libs/import_nation_builder_events_spec.rb:79 # import nation builder events works
rspec ./spec/libs/import_nation_builder_events_spec.rb:89 # import nation builder events creates a NationBuilderEvent object
rspec ./spec/libs/import_nation_builder_events_spec.rb:101 # import nation builder events doesn't create a NationBuilderEvent is one already exists
rspec ./spec/libs/message_promoter_and_agency_agg_updater_spec.rb:23 # Updating promoter agg columns Top level method logs errors raised in inner methods of update_message_promoter_and_agency_agg_columns
rspec ./spec/libs/message_promoter_and_agency_agg_updater_spec.rb:67 # Updating promoter agg columns Inner sql calls should successfully update_message_agg_activity_columns
rspec ./spec/libs/message_promoter_and_agency_agg_updater_spec.rb:95 # Updating promoter agg columns Inner sql calls should successfully update_message_conversion_activity_columns
rspec ./spec/libs/message_promoter_and_agency_agg_updater_spec.rb:108 # Updating promoter agg columns Inner sql calls should successfully update_promoter_agg_activity_columns
rspec ./spec/libs/message_promoter_and_agency_agg_updater_spec.rb:153 # Updating promoter agg columns Inner sql calls should successfully update_promoter_total_campaigns_column
rspec ./spec/libs/message_promoter_and_agency_agg_updater_spec.rb:167 # Updating promoter agg columns Inner sql calls should successfully update_promoter_total_advocates_column
rspec ./spec/libs/message_promoter_and_agency_agg_updater_spec.rb:181 # Updating promoter agg columns Inner sql calls should successfully insert_dummy_data_agg_agency_total_activity
rspec ./spec/libs/message_promoter_and_agency_agg_updater_spec.rb:204 # Updating promoter agg columns Inner sql calls should successfully update_offices_activity_sum_for_agg_agency_total_activity
rspec ./spec/libs/message_promoter_and_agency_agg_updater_spec.rb:255 # Updating promoter agg columns Inner sql calls should successfully add_individual_agency_activity_to_agg_agency_total_activity
rspec './spec/libs/model_cleaner_spec.rb[1:1:1:1:1:1]' # ModelCleaner for NationBuilderSynchronizeCalls behaves like a model cleaner with a last successful record after the cutoff destroys before the cutoff
rspec './spec/libs/model_cleaner_spec.rb[1:1:1:1:1:2]' # ModelCleaner for NationBuilderSynchronizeCalls behaves like a model cleaner with a last successful record after the cutoff doesn't destroy after the cutoff
rspec './spec/libs/model_cleaner_spec.rb[1:1:1:1:2:1]' # ModelCleaner for NationBuilderSynchronizeCalls behaves like a model cleaner with a last successful record before the cutoff destroys before the record
rspec './spec/libs/model_cleaner_spec.rb[1:1:1:1:2:2]' # ModelCleaner for NationBuilderSynchronizeCalls behaves like a model cleaner with a last successful record before the cutoff doesn't destroy after the record
rspec './spec/libs/model_cleaner_spec.rb[1:1:1:1:3:1]' # ModelCleaner for NationBuilderSynchronizeCalls behaves like a model cleaner with a last successful record running doesn't destroy other Promoters' records
rspec './spec/libs/model_cleaner_spec.rb[1:1:1:1:3:2]' # ModelCleaner for NationBuilderSynchronizeCalls behaves like a model cleaner with a last successful record running doesn't destroy other model_types
rspec './spec/libs/model_cleaner_spec.rb[1:2:1:1:1:1]' # ModelCleaner for CSVSynchronizeCalls behaves like a model cleaner with a last successful record after the cutoff destroys before the cutoff
rspec './spec/libs/model_cleaner_spec.rb[1:2:1:1:1:2]' # ModelCleaner for CSVSynchronizeCalls behaves like a model cleaner with a last successful record after the cutoff doesn't destroy after the cutoff
rspec './spec/libs/model_cleaner_spec.rb[1:2:1:1:2:1]' # ModelCleaner for CSVSynchronizeCalls behaves like a model cleaner with a last successful record before the cutoff destroys before the record
rspec './spec/libs/model_cleaner_spec.rb[1:2:1:1:2:2]' # ModelCleaner for CSVSynchronizeCalls behaves like a model cleaner with a last successful record before the cutoff doesn't destroy after the record
rspec './spec/libs/model_cleaner_spec.rb[1:2:1:1:3:1]' # ModelCleaner for CSVSynchronizeCalls behaves like a model cleaner with a last successful record running doesn't destroy other Promoters' records
rspec './spec/libs/model_cleaner_spec.rb[1:2:1:1:3:2]' # ModelCleaner for CSVSynchronizeCalls behaves like a model cleaner with a last successful record running doesn't destroy other model_types
rspec './spec/libs/model_cleaner_spec.rb[1:3:1:1:1:1]' # ModelCleaner for NoDBTransactions behaves like a model cleaner with a last successful record after the cutoff destroys before the cutoff
rspec './spec/libs/model_cleaner_spec.rb[1:3:1:1:1:2]' # ModelCleaner for NoDBTransactions behaves like a model cleaner with a last successful record after the cutoff doesn't destroy after the cutoff
rspec './spec/libs/model_cleaner_spec.rb[1:3:1:1:2:1]' # ModelCleaner for NoDBTransactions behaves like a model cleaner with a last successful record before the cutoff destroys before the record
rspec './spec/libs/model_cleaner_spec.rb[1:3:1:1:2:2]' # ModelCleaner for NoDBTransactions behaves like a model cleaner with a last successful record before the cutoff doesn't destroy after the record
rspec './spec/libs/model_cleaner_spec.rb[1:3:1:1:3:1]' # ModelCleaner for NoDBTransactions behaves like a model cleaner with a last successful record running doesn't destroy other Promoters' records
rspec './spec/libs/model_cleaner_spec.rb[1:3:1:1:3:2]' # ModelCleaner for NoDBTransactions behaves like a model cleaner with a last successful record running doesn't destroy other model_types
rspec ./spec/libs/nimble_scheduled_sync_spec.rb:12 # Running a Nimble Scheduled Sync without a Nimble authentication does not call 'for' on a NimbleTransaction
rspec ./spec/libs/nimble_scheduled_sync_spec.rb:23 # Running a Nimble Scheduled Sync with one Nimble authentications calls delegate on a NimbleTransaction with false
rspec ./spec/libs/nimble_scheduled_sync_spec.rb:27 # Running a Nimble Scheduled Sync with one Nimble authentications calls 'for' on a NimbleTransaction and passes in promoter
rspec ./spec/libs/nimble_scheduled_sync_spec.rb:31 # Running a Nimble Scheduled Sync with one Nimble authentications refreshes the access token
rspec ./spec/libs/nimble_scheduled_sync_spec.rb:35 # Running a Nimble Scheduled Sync with one Nimble authentications passes the new access token to the Transaction
rspec ./spec/libs/nimble_scheduled_sync_spec.rb:39 # Running a Nimble Scheduled Sync with one Nimble authentications sends an email if there's an exception
rspec ./spec/libs/nimble_scheduled_sync_spec.rb:57 # Running a Nimble Scheduled Sync with two Nimble authentications calls NimbleTransaction.for() twice
rspec './spec/libs/redeliver_campaign_conversions_spec.rb[1:1:1:1:1]' # RedeliverCampaignConversions successful calls with a :status parameter :status = done_no_targets passes the status to the filter
rspec './spec/libs/redeliver_campaign_conversions_spec.rb[1:1:1:1:2]' # RedeliverCampaignConversions successful calls with a :status parameter :status = done_no_targets redelivers matching Conversions
rspec './spec/libs/redeliver_campaign_conversions_spec.rb[1:1:1:1:3]' # RedeliverCampaignConversions successful calls with a :status parameter :status = done_no_targets doesn't redeliver other Conversions
rspec './spec/libs/redeliver_campaign_conversions_spec.rb[1:1:1:2:1]' # RedeliverCampaignConversions successful calls with a :status parameter :status = done_all_failed passes the status to the filter
rspec './spec/libs/redeliver_campaign_conversions_spec.rb[1:1:1:2:2]' # RedeliverCampaignConversions successful calls with a :status parameter :status = done_all_failed redelivers matching Conversions
rspec './spec/libs/redeliver_campaign_conversions_spec.rb[1:1:1:2:3]' # RedeliverCampaignConversions successful calls with a :status parameter :status = done_all_failed doesn't redeliver other Conversions
rspec './spec/libs/redeliver_campaign_conversions_spec.rb[1:1:1:3:1]' # RedeliverCampaignConversions successful calls with a :status parameter :status = done_some_failed passes the status to the filter
rspec './spec/libs/redeliver_campaign_conversions_spec.rb[1:1:1:3:2]' # RedeliverCampaignConversions successful calls with a :status parameter :status = done_some_failed redelivers matching Conversions
rspec './spec/libs/redeliver_campaign_conversions_spec.rb[1:1:1:3:3]' # RedeliverCampaignConversions successful calls with a :status parameter :status = done_some_failed doesn't redeliver other Conversions
rspec './spec/libs/redeliver_campaign_conversions_spec.rb[1:1:1:4:1]' # RedeliverCampaignConversions successful calls with a :status parameter :status = finished passes the status to the filter
rspec './spec/libs/redeliver_campaign_conversions_spec.rb[1:1:1:4:2]' # RedeliverCampaignConversions successful calls with a :status parameter :status = finished redelivers matching Conversions
rspec './spec/libs/redeliver_campaign_conversions_spec.rb[1:1:1:4:3]' # RedeliverCampaignConversions successful calls with a :status parameter :status = finished doesn't redeliver other Conversions
rspec './spec/libs/redeliver_campaign_conversions_spec.rb[1:1:1:5:1]' # RedeliverCampaignConversions successful calls with a :status parameter :status = stale passes the status to the filter
rspec './spec/libs/redeliver_campaign_conversions_spec.rb[1:1:1:5:2]' # RedeliverCampaignConversions successful calls with a :status parameter :status = stale redelivers matching Conversions
rspec './spec/libs/redeliver_campaign_conversions_spec.rb[1:1:1:5:3]' # RedeliverCampaignConversions successful calls with a :status parameter :status = stale doesn't redeliver other Conversions
rspec './spec/libs/redeliver_campaign_conversions_spec.rb[1:1:1:6:1]' # RedeliverCampaignConversions successful calls with a :status parameter :status = ongoing passes the status to the filter
rspec './spec/libs/redeliver_campaign_conversions_spec.rb[1:1:1:6:2]' # RedeliverCampaignConversions successful calls with a :status parameter :status = ongoing redelivers matching Conversions
rspec './spec/libs/redeliver_campaign_conversions_spec.rb[1:1:1:6:3]' # RedeliverCampaignConversions successful calls with a :status parameter :status = ongoing doesn't redeliver other Conversions
rspec './spec/libs/redeliver_campaign_conversions_spec.rb[1:1:1:7:1]' # RedeliverCampaignConversions successful calls with a :status parameter :status = not_verified passes the status to the filter
rspec './spec/libs/redeliver_campaign_conversions_spec.rb[1:1:1:7:2]' # RedeliverCampaignConversions successful calls with a :status parameter :status = not_verified redelivers matching Conversions
rspec './spec/libs/redeliver_campaign_conversions_spec.rb[1:1:1:7:3]' # RedeliverCampaignConversions successful calls with a :status parameter :status = not_verified doesn't redeliver other Conversions
rspec './spec/libs/redeliver_campaign_conversions_spec.rb[1:1:1:8:1]' # RedeliverCampaignConversions successful calls with a :status parameter :status = not_submitted passes the status to the filter
rspec './spec/libs/redeliver_campaign_conversions_spec.rb[1:1:1:8:2]' # RedeliverCampaignConversions successful calls with a :status parameter :status = not_submitted redelivers matching Conversions
rspec './spec/libs/redeliver_campaign_conversions_spec.rb[1:1:1:8:3]' # RedeliverCampaignConversions successful calls with a :status parameter :status = not_submitted doesn't redeliver other Conversions
rspec './spec/libs/redeliver_campaign_conversions_spec.rb[1:1:1:9:1]' # RedeliverCampaignConversions successful calls with a :status parameter :status = duplicate passes the status to the filter
rspec './spec/libs/redeliver_campaign_conversions_spec.rb[1:1:1:9:2]' # RedeliverCampaignConversions successful calls with a :status parameter :status = duplicate redelivers matching Conversions
rspec './spec/libs/redeliver_campaign_conversions_spec.rb[1:1:1:9:3]' # RedeliverCampaignConversions successful calls with a :status parameter :status = duplicate doesn't redeliver other Conversions
rspec './spec/libs/redeliver_campaign_conversions_spec.rb[1:1:1:10:1]' # RedeliverCampaignConversions successful calls with a :status parameter :status = not_staged passes the status to the filter
rspec './spec/libs/redeliver_campaign_conversions_spec.rb[1:1:1:10:2]' # RedeliverCampaignConversions successful calls with a :status parameter :status = not_staged redelivers matching Conversions
rspec './spec/libs/redeliver_campaign_conversions_spec.rb[1:1:1:10:3]' # RedeliverCampaignConversions successful calls with a :status parameter :status = not_staged doesn't redeliver other Conversions
rspec './spec/libs/redeliver_campaign_conversions_spec.rb[1:1:1:11:1]' # RedeliverCampaignConversions successful calls with a :status parameter :status = no_recipients passes the status to the filter
rspec './spec/libs/redeliver_campaign_conversions_spec.rb[1:1:1:11:2]' # RedeliverCampaignConversions successful calls with a :status parameter :status = no_recipients redelivers matching Conversions
rspec './spec/libs/redeliver_campaign_conversions_spec.rb[1:1:1:11:3]' # RedeliverCampaignConversions successful calls with a :status parameter :status = no_recipients doesn't redeliver other Conversions
rspec ./spec/libs/redeliver_campaign_conversions_spec.rb:70 # RedeliverCampaignConversions successful calls calls to generate_and_send_message should call generate_and_send_message on a good conversion in its time frame for its message
rspec ./spec/libs/redeliver_campaign_conversions_spec.rb:79 # RedeliverCampaignConversions successful calls calls to generate_and_send_message should not call generate_and_send_message on a good conversion outside the time frame
rspec ./spec/libs/redeliver_campaign_conversions_spec.rb:89 # RedeliverCampaignConversions successful calls calls to generate_and_send_message should not call generate_and_send_message on a bad conversion with a different message
rspec ./spec/libs/redeliver_campaign_conversions_spec.rb:103 # RedeliverCampaignConversions successful calls recalculate_recipients should pass the correct recipients to UpdateConversionRecipients
rspec ./spec/libs/redeliver_campaign_conversions_spec.rb:110 # RedeliverCampaignConversions successful calls recalculate_recipients should pass the correct recipients for multi_content to UpdateConversionRecipients
rspec ./spec/libs/redeliver_campaign_conversions_spec.rb:119 # RedeliverCampaignConversions successful calls recalculate_recipients should update the conversion rubberstamped column to true if it is false and promoted_message.disable_email_verifications is true
rspec ./spec/libs/redeliver_campaign_conversions_spec.rb:129 # RedeliverCampaignConversions successful calls recalculate_recipients should not update conversion rubberstamped column if recipients is blank
rspec ./spec/libs/redeliver_campaign_conversions_spec.rb:143 # RedeliverCampaignConversions successful calls Creating and updating RedeliverCampaignConversionsTask should successfully create a RedeliverCampaignConversionsTask object and associated conversions to it
rspec ./spec/libs/redeliver_campaign_conversions_spec.rb:162 # RedeliverCampaignConversions unsuccessful calls should respond with an error when message_id blank
rspec ./spec/libs/redeliver_campaign_conversions_spec.rb:167 # RedeliverCampaignConversions unsuccessful calls should respond with an error when start_time blank
rspec ./spec/libs/redeliver_campaign_conversions_spec.rb:172 # RedeliverCampaignConversions unsuccessful calls should respond with an error when end_time blank
rspec ./spec/libs/redeliver_campaign_conversions_spec.rb:177 # RedeliverCampaignConversions unsuccessful calls should respond with an error when recalculate_recipients true but no selected_recipient on promoted_message
rspec ./spec/libs/redeliver_campaign_conversions_spec.rb:187 # RedeliverCampaignConversions unsuccessful calls should respond with an error when results of selector.update_conversion_with_recipients are not processed
rspec ./spec/libs/redeliver_campaign_conversions_spec.rb:200 # RedeliverCampaignConversions Redeliver conversions not to include finished conversions
rspec ./spec/libs/redeliver_campaign_conversions_spec.rb:204 # RedeliverCampaignConversions Redeliver conversions to include some failed conversions
rspec ./spec/libs/redeliver_campaign_conversions_spec.rb:208 # RedeliverCampaignConversions Redeliver conversions to include all failed conversions
rspec ./spec/libs/redeliver_error_conversions_spec.rb:8 # RedeliverErrorConversions unsuccessful calls should respond with an error when no conversions are found
rspec ./spec/libs/redeliver_error_conversions_spec.rb:13 # RedeliverErrorConversions unsuccessful calls should respond with an error when no start_time are found
rspec ./spec/libs/redeliver_error_conversions_spec.rb:18 # RedeliverErrorConversions unsuccessful calls should respond with an error when no end_time are found
rspec ./spec/libs/redeliver_error_conversions_spec.rb:23 # RedeliverErrorConversions unsuccessful calls should respond with an error when end_time is before start_time
rspec ./spec/libs/redeliver_error_conversions_spec.rb:35 # RedeliverErrorConversions successful calls with a start time calls generate_and_send_message on a conversion which was queued after the start_time but before the end_time
rspec ./spec/libs/redeliver_error_conversions_spec.rb:41 # RedeliverErrorConversions successful calls with a start time doesn't call generate_and_send_message on a conversion which was queued before the start time
rspec ./spec/libs/redeliver_error_conversions_spec.rb:47 # RedeliverErrorConversions successful calls with a start time creates a RedeliverErrorConversionsTask object
rspec ./spec/libs/redistrict_advocates_for_district_or_state_spec.rb:14 # RedistrictAdvocatesForDistrictOrState Successful Calls for a state returns the correct standard outputs
rspec ./spec/libs/redistrict_advocates_for_district_or_state_spec.rb:21 # RedistrictAdvocatesForDistrictOrState Successful Calls for a state only calls update_districts for advocates in state
rspec ./spec/libs/redistrict_advocates_for_district_or_state_spec.rb:35 # RedistrictAdvocatesForDistrictOrState Successful Calls for a district returns the correct standard outputs
rspec ./spec/libs/redistrict_advocates_for_district_or_state_spec.rb:42 # RedistrictAdvocatesForDistrictOrState Successful Calls for a district only calls update_districts for advocates in district
rspec ./spec/libs/redistrict_advocates_for_district_or_state_spec.rb:63 # RedistrictAdvocatesForDistrictOrState Unsuccessful Calls should respond with an error when no state/district for ID
rspec ./spec/libs/replaced_target_updater_spec.rb:13 # ReplacedTargetUpdater new loads replaced targets
rspec ./spec/libs/replaced_target_updater_spec.rb:17 # ReplacedTargetUpdater new maps replaced targets to replacements
rspec ./spec/libs/replaced_target_updater_spec.rb:29 # ReplacedTargetUpdater new with older targets pairs the latest target from the same district
rspec ./spec/libs/replaced_target_updater_spec.rb:39 # ReplacedTargetUpdater new without a district pairs targets with the same first or last name
rspec ./spec/libs/replaced_target_updater_spec.rb:67 # ReplacedTargetUpdater call for a replaced_target gets an affected message
rspec ./spec/libs/replaced_target_updater_spec.rb:71 # ReplacedTargetUpdater call for a replaced_target doesn't get unaffected messages
rspec ./spec/libs/replaced_target_updater_spec.rb:82 # ReplacedTargetUpdater call record = false doesn't update affected messages
rspec ./spec/libs/replaced_target_updater_spec.rb:97 # ReplacedTargetUpdater call record = true updates affected messages
rspec ./spec/libs/replaced_target_updater_spec.rb:103 # ReplacedTargetUpdater call record = true doesn't update unaffected messages
rspec ./spec/libs/sync_signatures_csv_spec.rb:17 # Sync Signatures CSV Errors marks transaction as failed and sends slack notification if error with service call
rspec ./spec/libs/sync_signatures_csv_spec.rb:48 # Sync Signatures CSV Full Results if a LocalTransaction exists with an end_cutoff_date_time with no new Custom Fields appends the new record
rspec ./spec/libs/sync_signatures_csv_spec.rb:71 # Sync Signatures CSV Full Results if a LocalTransaction exists with an end_cutoff_date_time with new Custom Fields overwrites existing records and includes custom fields
rspec './spec/libs/sync_signatures_csv_spec.rb[1:2:2:1:1:1:1:1:1]' # Sync Signatures CSV Full Results with 30 older signatures and 10 recent signatures processing a set_sync_size of 29 with a BatchedQuery block size of 10 the Transaction behaves like a Transaction with set_sync_size returns set_sync_size rows
rspec './spec/libs/sync_signatures_csv_spec.rb[1:2:2:1:1:1:1:1:2]' # Sync Signatures CSV Full Results with 30 older signatures and 10 recent signatures processing a set_sync_size of 29 with a BatchedQuery block size of 10 the Transaction behaves like a Transaction with set_sync_size uses the timestamp from the last row
rspec './spec/libs/sync_signatures_csv_spec.rb[1:2:2:1:1:1:1:1:3]' # Sync Signatures CSV Full Results with 30 older signatures and 10 recent signatures processing a set_sync_size of 29 with a BatchedQuery block size of 10 the Transaction behaves like a Transaction with set_sync_size uses the id from the last row
rspec './spec/libs/sync_signatures_csv_spec.rb[1:2:2:1:1:1:1:2:1:1]' # Sync Signatures CSV Full Results with 30 older signatures and 10 recent signatures processing a set_sync_size of 29 with a BatchedQuery block size of 10 the Transaction a follow-up Transaction with set_sync_size 5 behaves like a Transaction with set_sync_size returns set_sync_size rows
rspec './spec/libs/sync_signatures_csv_spec.rb[1:2:2:1:1:1:1:2:1:2]' # Sync Signatures CSV Full Results with 30 older signatures and 10 recent signatures processing a set_sync_size of 29 with a BatchedQuery block size of 10 the Transaction a follow-up Transaction with set_sync_size 5 behaves like a Transaction with set_sync_size uses the timestamp from the last row
rspec './spec/libs/sync_signatures_csv_spec.rb[1:2:2:1:1:1:1:2:1:3]' # Sync Signatures CSV Full Results with 30 older signatures and 10 recent signatures processing a set_sync_size of 29 with a BatchedQuery block size of 10 the Transaction a follow-up Transaction with set_sync_size 5 behaves like a Transaction with set_sync_size uses the id from the last row
rspec './spec/libs/sync_signatures_csv_spec.rb[1:2:2:1:1:2:1:1:1]' # Sync Signatures CSV Full Results with 30 older signatures and 10 recent signatures processing a set_sync_size of 29 with a BatchedQuery block size of 300 the Transaction behaves like a Transaction with set_sync_size returns set_sync_size rows
rspec './spec/libs/sync_signatures_csv_spec.rb[1:2:2:1:1:2:1:1:2]' # Sync Signatures CSV Full Results with 30 older signatures and 10 recent signatures processing a set_sync_size of 29 with a BatchedQuery block size of 300 the Transaction behaves like a Transaction with set_sync_size uses the timestamp from the last row
rspec './spec/libs/sync_signatures_csv_spec.rb[1:2:2:1:1:2:1:1:3]' # Sync Signatures CSV Full Results with 30 older signatures and 10 recent signatures processing a set_sync_size of 29 with a BatchedQuery block size of 300 the Transaction behaves like a Transaction with set_sync_size uses the id from the last row
rspec './spec/libs/sync_signatures_csv_spec.rb[1:2:2:1:1:2:1:2:1:1]' # Sync Signatures CSV Full Results with 30 older signatures and 10 recent signatures processing a set_sync_size of 29 with a BatchedQuery block size of 300 the Transaction a follow-up Transaction with set_sync_size 5 behaves like a Transaction with set_sync_size returns set_sync_size rows
rspec './spec/libs/sync_signatures_csv_spec.rb[1:2:2:1:1:2:1:2:1:2]' # Sync Signatures CSV Full Results with 30 older signatures and 10 recent signatures processing a set_sync_size of 29 with a BatchedQuery block size of 300 the Transaction a follow-up Transaction with set_sync_size 5 behaves like a Transaction with set_sync_size uses the timestamp from the last row
rspec './spec/libs/sync_signatures_csv_spec.rb[1:2:2:1:1:2:1:2:1:3]' # Sync Signatures CSV Full Results with 30 older signatures and 10 recent signatures processing a set_sync_size of 29 with a BatchedQuery block size of 300 the Transaction a follow-up Transaction with set_sync_size 5 behaves like a Transaction with set_sync_size uses the id from the last row
rspec './spec/libs/sync_signatures_csv_spec.rb[1:2:2:1:2:1:1:1:1]' # Sync Signatures CSV Full Results with 30 older signatures and 10 recent signatures processing a set_sync_size of 31 with a BatchedQuery block size of 10 the Transaction behaves like a Transaction with set_sync_size returns set_sync_size rows
rspec './spec/libs/sync_signatures_csv_spec.rb[1:2:2:1:2:1:1:1:2]' # Sync Signatures CSV Full Results with 30 older signatures and 10 recent signatures processing a set_sync_size of 31 with a BatchedQuery block size of 10 the Transaction behaves like a Transaction with set_sync_size uses the timestamp from the last row
rspec './spec/libs/sync_signatures_csv_spec.rb[1:2:2:1:2:1:1:1:3]' # Sync Signatures CSV Full Results with 30 older signatures and 10 recent signatures processing a set_sync_size of 31 with a BatchedQuery block size of 10 the Transaction behaves like a Transaction with set_sync_size uses the id from the last row
rspec './spec/libs/sync_signatures_csv_spec.rb[1:2:2:1:2:2:1:1:1]' # Sync Signatures CSV Full Results with 30 older signatures and 10 recent signatures processing a set_sync_size of 31 with a BatchedQuery block size of 300 the Transaction behaves like a Transaction with set_sync_size returns set_sync_size rows
rspec './spec/libs/sync_signatures_csv_spec.rb[1:2:2:1:2:2:1:1:2]' # Sync Signatures CSV Full Results with 30 older signatures and 10 recent signatures processing a set_sync_size of 31 with a BatchedQuery block size of 300 the Transaction behaves like a Transaction with set_sync_size uses the timestamp from the last row
rspec './spec/libs/sync_signatures_csv_spec.rb[1:2:2:1:2:2:1:1:3]' # Sync Signatures CSV Full Results with 30 older signatures and 10 recent signatures processing a set_sync_size of 31 with a BatchedQuery block size of 300 the Transaction behaves like a Transaction with set_sync_size uses the id from the last row
rspec ./spec/libs/sync_signatures_csv_spec.rb:306 # Sync Signatures CSV Full Results with 40 randomized opt-in/opt-out signatures with a BatchedQuery block size of 10 processing 15, then 20, then 5 adds all 40 unique signatures
rspec './spec/libs/sync_signatures_csv_spec.rb[1:2:3:1:1:2:1:1:1:1]' # Sync Signatures CSV Full Results with 40 randomized opt-in/opt-out signatures with a BatchedQuery block size of 10 processing 15, then 20, then 5 the Transactions Transaction 1 behaves like a Transaction with set_sync_size the cutoff date matches this transaction's last row
rspec './spec/libs/sync_signatures_csv_spec.rb[1:2:3:1:1:2:1:1:2:1]' # Sync Signatures CSV Full Results with 40 randomized opt-in/opt-out signatures with a BatchedQuery block size of 10 processing 15, then 20, then 5 the Transactions Transaction 1 behaves like a Transaction with set_sync_size the cutoff id matches this transaction's last row
rspec './spec/libs/sync_signatures_csv_spec.rb[1:2:3:1:1:2:1:1:3:1]' # Sync Signatures CSV Full Results with 40 randomized opt-in/opt-out signatures with a BatchedQuery block size of 10 processing 15, then 20, then 5 the Transactions Transaction 1 behaves like a Transaction with set_sync_size the result count matches the set_sync_size
rspec './spec/libs/sync_signatures_csv_spec.rb[1:2:3:1:1:2:2:1:1:1]' # Sync Signatures CSV Full Results with 40 randomized opt-in/opt-out signatures with a BatchedQuery block size of 10 processing 15, then 20, then 5 the Transactions Transaction 2 behaves like a Transaction with set_sync_size the cutoff date matches this transaction's last row
rspec './spec/libs/sync_signatures_csv_spec.rb[1:2:3:1:1:2:2:1:2:1]' # Sync Signatures CSV Full Results with 40 randomized opt-in/opt-out signatures with a BatchedQuery block size of 10 processing 15, then 20, then 5 the Transactions Transaction 2 behaves like a Transaction with set_sync_size the cutoff id matches this transaction's last row
rspec './spec/libs/sync_signatures_csv_spec.rb[1:2:3:1:1:2:2:1:3:1]' # Sync Signatures CSV Full Results with 40 randomized opt-in/opt-out signatures with a BatchedQuery block size of 10 processing 15, then 20, then 5 the Transactions Transaction 2 behaves like a Transaction with set_sync_size the result count matches the set_sync_size
rspec './spec/libs/sync_signatures_csv_spec.rb[1:2:3:1:1:2:3:1:1:1]' # Sync Signatures CSV Full Results with 40 randomized opt-in/opt-out signatures with a BatchedQuery block size of 10 processing 15, then 20, then 5 the Transactions Transaction 3 behaves like a Transaction with set_sync_size the cutoff date matches this transaction's last row
rspec './spec/libs/sync_signatures_csv_spec.rb[1:2:3:1:1:2:3:1:2:1]' # Sync Signatures CSV Full Results with 40 randomized opt-in/opt-out signatures with a BatchedQuery block size of 10 processing 15, then 20, then 5 the Transactions Transaction 3 behaves like a Transaction with set_sync_size the cutoff id matches this transaction's last row
rspec './spec/libs/sync_signatures_csv_spec.rb[1:2:3:1:1:2:3:1:3:1]' # Sync Signatures CSV Full Results with 40 randomized opt-in/opt-out signatures with a BatchedQuery block size of 10 processing 15, then 20, then 5 the Transactions Transaction 3 behaves like a Transaction with set_sync_size the result count matches the set_sync_size
rspec ./spec/libs/sync_signatures_csv_spec.rb:354 # Sync Signatures CSV Full Results with 40 randomized opt-in/opt-out signatures with a BatchedQuery block size of 100 processing 15, then 20, then 5 adds all 40 unique signatures
rspec './spec/libs/sync_signatures_csv_spec.rb[1:2:3:2:1:2:1:1:1:1]' # Sync Signatures CSV Full Results with 40 randomized opt-in/opt-out signatures with a BatchedQuery block size of 100 processing 15, then 20, then 5 the Transactions Transaction 1 behaves like a Transaction with set_sync_size the cutoff date matches this transaction's last row
rspec './spec/libs/sync_signatures_csv_spec.rb[1:2:3:2:1:2:1:1:2:1]' # Sync Signatures CSV Full Results with 40 randomized opt-in/opt-out signatures with a BatchedQuery block size of 100 processing 15, then 20, then 5 the Transactions Transaction 1 behaves like a Transaction with set_sync_size the cutoff id matches this transaction's last row
rspec './spec/libs/sync_signatures_csv_spec.rb[1:2:3:2:1:2:1:1:3:1]' # Sync Signatures CSV Full Results with 40 randomized opt-in/opt-out signatures with a BatchedQuery block size of 100 processing 15, then 20, then 5 the Transactions Transaction 1 behaves like a Transaction with set_sync_size the result count matches the set_sync_size
rspec './spec/libs/sync_signatures_csv_spec.rb[1:2:3:2:1:2:2:1:1:1]' # Sync Signatures CSV Full Results with 40 randomized opt-in/opt-out signatures with a BatchedQuery block size of 100 processing 15, then 20, then 5 the Transactions Transaction 2 behaves like a Transaction with set_sync_size the cutoff date matches this transaction's last row
rspec './spec/libs/sync_signatures_csv_spec.rb[1:2:3:2:1:2:2:1:2:1]' # Sync Signatures CSV Full Results with 40 randomized opt-in/opt-out signatures with a BatchedQuery block size of 100 processing 15, then 20, then 5 the Transactions Transaction 2 behaves like a Transaction with set_sync_size the cutoff id matches this transaction's last row
rspec './spec/libs/sync_signatures_csv_spec.rb[1:2:3:2:1:2:2:1:3:1]' # Sync Signatures CSV Full Results with 40 randomized opt-in/opt-out signatures with a BatchedQuery block size of 100 processing 15, then 20, then 5 the Transactions Transaction 2 behaves like a Transaction with set_sync_size the result count matches the set_sync_size
rspec './spec/libs/sync_signatures_csv_spec.rb[1:2:3:2:1:2:3:1:1:1]' # Sync Signatures CSV Full Results with 40 randomized opt-in/opt-out signatures with a BatchedQuery block size of 100 processing 15, then 20, then 5 the Transactions Transaction 3 behaves like a Transaction with set_sync_size the cutoff date matches this transaction's last row
rspec './spec/libs/sync_signatures_csv_spec.rb[1:2:3:2:1:2:3:1:2:1]' # Sync Signatures CSV Full Results with 40 randomized opt-in/opt-out signatures with a BatchedQuery block size of 100 processing 15, then 20, then 5 the Transactions Transaction 3 behaves like a Transaction with set_sync_size the cutoff id matches this transaction's last row
rspec './spec/libs/sync_signatures_csv_spec.rb[1:2:3:2:1:2:3:1:3:1]' # Sync Signatures CSV Full Results with 40 randomized opt-in/opt-out signatures with a BatchedQuery block size of 100 processing 15, then 20, then 5 the Transactions Transaction 3 behaves like a Transaction with set_sync_size the result count matches the set_sync_size
rspec ./spec/libs/sync_signatures_csv_spec.rb:396 # Sync Signatures CSV Full Results with 40 randomized opt-in/opt-out signatures syncing :set_sync_size=5 has 5 lines
rspec ./spec/libs/sync_signatures_csv_spec.rb:403 # Sync Signatures CSV Full Results with 40 randomized opt-in/opt-out signatures syncing :set_sync_size=5 then syncing all has 40 lines
rspec ./spec/libs/sync_signatures_csv_spec.rb:415 # Sync Signatures CSV Full Results with 40 randomized opt-in/opt-out signatures syncing :set_sync_size=5 then syncing all with 20 more sigs syncing :set_sync_size=5 has 45 lines
rspec ./spec/libs/sync_signatures_csv_spec.rb:422 # Sync Signatures CSV Full Results with 40 randomized opt-in/opt-out signatures syncing :set_sync_size=5 then syncing all with 20 more sigs syncing :set_sync_size=5 then syncing all has 60 lines
rspec ./spec/libs/sync_signatures_csv_spec.rb:428 # Sync Signatures CSV Full Results with 40 randomized opt-in/opt-out signatures syncing :set_sync_size=5 then syncing all with 20 more sigs syncing :set_sync_size=5 then syncing all the Transactions have the correct counts
rspec ./spec/libs/sync_signatures_csv_spec.rb:465 # Sync Signatures CSV Full Results with 40 randomized opt-in/opt-out signatures syncing :set_sync_size=5 for back-compatibility syncing via timestamp with 20 more sigs syncing :set_sync_size=5 has 45 lines
rspec ./spec/libs/sync_signatures_csv_spec.rb:471 # Sync Signatures CSV Full Results with 40 randomized opt-in/opt-out signatures syncing :set_sync_size=5 for back-compatibility syncing via timestamp with 20 more sigs syncing :set_sync_size=5 the new LocalTransaction adds id stamps
rspec ./spec/libs/sync_signatures_csv_spec.rb:515 # Sync Signatures CSV Demo Vs. Non-Demo User results for demo users when we exceed the cutoff the signatures .CSV link returns a CSV
rspec ./spec/libs/sync_signatures_csv_spec.rb:525 # Sync Signatures CSV Demo Vs. Non-Demo User results for demo users when we exceed the cutoff the signatures .CSV link the returned CSV limits us to 50 email signatures
rspec ./spec/libs/sync_signatures_csv_spec.rb:555 # Sync Signatures CSV Demo Vs. Non-Demo User results for non-demo users when we exceed the cutoff the signatures .CSV link returns a CSV
rspec ./spec/libs/sync_signatures_csv_spec.rb:565 # Sync Signatures CSV Demo Vs. Non-Demo User results for non-demo users when we exceed the cutoff the signatures .CSV link the returned CSV doesn't limit us to 50 email signatures
rspec ./spec/libs/sync_signatures_csv_spec.rb:592 # Sync Signatures CSV facebook_handle and twitter_handle display the CSV includes the social media handles
rspec ./spec/libs/sync_signatures_csv_spec.rb:610 # Sync Signatures CSV Opt Out vs. Opt In behavior an opt-out signature
rspec ./spec/libs/sync_signatures_csv_spec.rb:611 # Sync Signatures CSV Opt Out vs. Opt In behavior an opt-out signature
rspec ./spec/libs/sync_signatures_csv_spec.rb:612 # Sync Signatures CSV Opt Out vs. Opt In behavior an opt-out signature
rspec ./spec/libs/sync_signatures_csv_spec.rb:617 # Sync Signatures CSV Opt Out vs. Opt In behavior an opt-in signature
rspec ./spec/libs/sync_signatures_csv_spec.rb:618 # Sync Signatures CSV Opt Out vs. Opt In behavior an opt-in signature
rspec ./spec/libs/sync_signatures_csv_spec.rb:619 # Sync Signatures CSV Opt Out vs. Opt In behavior an opt-in signature
rspec ./spec/libs/sync_signatures_csv_spec.rb:629 # Sync Signatures CSV with conversion address columns like conversion_line1, conversion_city etc. displays ConventionalServiceSend address columns if one exists on a conversion object
rspec ./spec/libs/sync_signatures_csv_spec.rb:656 # SignatureCSVGenerator generates a forward-compatible CSVSynchronizeCall
rspec ./spec/libs/sync_signatures_csv_spec.rb:661 # SignatureCSVGenerator takes arrays of promoter ids
rspec ./spec/libs/sync_signatures_csv_spec.rb:667 # SignatureCSVGenerator takes individual promoter ids
rspec ./spec/libs/sync_signatures_csv_spec.rb:672 # SignatureCSVGenerator doesn't take unpaid promoters
rspec ./spec/libs/sync_signatures_csv_spec.rb:686 # SignatureCSVGenerator#generate_until_current_for( promoter_user_id ) with 45000 signatures needed with 10000 per call runs five times
rspec ./spec/libs/sync_signatures_csv_spec.rb:700 # SignatureCSVGenerator#generate_until_current_for( promoter_user_id ) with an ongoing global CSVSynchronizeCall proceeds
rspec ./spec/libs/turn_off_twitter_for_promoter_campaigns_spec.rb:35 # TurnOffTwitterForPromoterCampaigns #call with correct params should successfully turn off the Twitter action for campaigns belonging to the provided promoter
rspec ./spec/libs/turn_off_twitter_for_promoter_campaigns_spec.rb:58 # TurnOffTwitterForPromoterCampaigns #call with correct params where a campaign fails to save should log campaigns that failed to save

Coverage report generated for RSpec to /ocp/coverage. 14273 / 39283 LOC (36.33%) covered.
SimpleCov failed with exit 1                                     


# bulk test runs only
## spec/libs
2124 examples, 1654 failures, 6 pending  (1143 are spec/libs/importer_modules which succeed when run in that block; output deleted below)
                                         (271 are spec/libs/nation_builder_sync/ which succeed when run in that block; output deleted below)
                                         (66 are spec/libs/neon_client/ which succeed when run in that block; output deleted below)
                                         (36 are spec/libs/nodb/ which succeed when run in that block; output deleted below)

The tests remaining below only occur in bulk test runs

Failed examples:

rspec ./spec/libs/australia/cicero_id_matcher_spec.rb:100 # Australia::CiceroIdMatcher initialized_object loads stuff correctly loads the federal level db
rspec ./spec/libs/australia/cicero_id_matcher_spec.rb:105 # Australia::CiceroIdMatcher initialized_object loads stuff correctly loads the state level db
rspec ./spec/libs/australia/cicero_id_matcher_spec.rb:136 # Australia::CiceroIdMatcher initialized_object loads stuff correctly loads the federal level csv
rspec ./spec/libs/australia/cicero_id_matcher_spec.rb:141 # Australia::CiceroIdMatcher initialized_object loads stuff correctly loads the state level csv
rspec ./spec/libs/australia/cicero_id_matcher_spec.rb:159 # Australia::CiceroIdMatcher initialized_object matching active full match recipients applies the cicerco_id to federal senators
rspec ./spec/libs/australia/cicero_id_matcher_spec.rb:171 # Australia::CiceroIdMatcher initialized_object matching active full match recipients applies the cicerco_id to federal house

Coverage report generated for RSpec to /ocp/coverage. 19665 / 46938 LOC (41.9%) covered.
SimpleCov failed with exit 1
