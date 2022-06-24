
---

The below running with `-fd` was killed before the output completed.  Not as useful as I would like.  Next test to run WITHOUT `-fd`.  My goal here is to get the listing of failed spec files and line numbers.  Try this instead `rspec spec --tag ~slow_tests`


---

This is the output when running full test suite.  Includes time started which is June 7, 4:08pm, roughly

Tue Jun  7 21:08:21 UTC 2022
Tue Jun  7 23:12:25 UTC 2022
2:04 (with -fd)

Tue Jun  7 23:50:10 UTC 2022
Wed Jun  8 01:27:09 UTC 2022
1:37 (without -fd)

We'll see if all the output can fit in a single term window and also how long the tests take.  May want to output this all to a file if the terminal window cannot handle the amount of output from the full test suite.


root@d42a15951b34:/ocp# date ; rspec ./spec -fd; date
Tue Jun  7 21:08:21 UTC 2022
/usr/local/bundle/gems/tlsmail-0.0.1/lib/net/smtp.rb:806: warning: already initialized constant Net::SMTPSession
/usr/local/bundle/gems/tlsmail-0.0.1/lib/net/smtp.rb:806: warning: previous definition of SMTPSession was here
/usr/local/bundle/gems/tlsmail-0.0.1/lib/net/pop.rb:687: warning: already initialized constant Net::POP
/usr/local/bundle/gems/tlsmail-0.0.1/lib/net/pop.rb:687: warning: previous definition of POP was here
/usr/local/bundle/gems/tlsmail-0.0.1/lib/net/pop.rb:688: warning: already initialized constant Net::POPSession
/usr/local/bundle/gems/tlsmail-0.0.1/lib/net/pop.rb:688: warning: previous definition of POPSession was here
/usr/local/bundle/gems/tlsmail-0.0.1/lib/net/pop.rb:689: warning: already initialized constant Net::POP3Session
/usr/local/bundle/gems/tlsmail-0.0.1/lib/net/pop.rb:689: warning: previous definition of POP3Session was here
/usr/local/bundle/gems/tlsmail-0.0.1/lib/net/pop.rb:702: warning: already initialized constant Net::APOPSession
/usr/local/bundle/gems/tlsmail-0.0.1/lib/net/pop.rb:702: warning: previous definition of APOPSession was here
Doing `require 'backports'` is deprecated and will not load any backport in the next major release.
Require just the needed backports instead, or 'backports/latest'.
Called 'load' without the :safe option -- defaulting to safe mode.
You can avoid this warning in the future by setting the SafeYAML::OPTIONS[:default_mode] option (to :safe or :unsafe).
WARNING: Skipping key "CLICK_DB_UN". Already set in ENV.
WARNING: Skipping key "CLICK_DB_PW". Already set in ENV.
/ocp/config/initializers/load_config.rb:74: warning: already initialized constant APP_CONFIG
/ocp/config/initializers/load_config.rb:74: warning: previous definition of APP_CONFIG was here
/ocp/config/initializers/load_config.rb:80: warning: already initialized constant STAGING_CONFIG
/ocp/config/initializers/load_config.rb:80: warning: previous definition of STAGING_CONFIG was here
/ocp/config/initializers/load_config.rb:83: warning: already initialized constant RABBIT_CONFIG
/ocp/config/initializers/load_config.rb:83: warning: previous definition of RABBIT_CONFIG was here
/ocp/config/initializers/load_config.rb:85: warning: already initialized constant REDIS_HOST
/ocp/config/initializers/load_config.rb:85: warning: previous definition of REDIS_HOST was here
DEPRECATION WARNING: CarrierWave::MimeTypes is deprecated and will be removed in the future, get the content_type from the SanitizedFile object directly. (will be removed from version 0.11.0). (called from include at /ocp/app/uploaders/image_uploader.rb:13)
/ocp/app/models/custom_recipient.rb:197: warning: duplicated key at line 197 ignored: :state
/ocp/lib/importer_modules/canada/canada.rb:60: warning: duplicated key at line 61 ignored: "Independent"
/ocp/lib/importer_modules/united_states/cicero/cicero_united_states.rb:36: warning: duplicated key at line 37 ignored: "Democratic"
/ocp/lib/importer_modules/united_states/cicero/cicero_united_states.rb:29: warning: duplicated key at line 47 ignored: "Democratic/Farmer/Labor"
/ocp/app/models/contact_congress_test.rb:35: warning: duplicated key at line 42 ignored: :email
/ocp/app/models/contact_congress_test.rb:58: warning: duplicated key at line 65 ignored: :email
/ocp/app/models/new_district.rb:218: warning: duplicated key at line 221 ignored: :name
/ocp/app/models/new_district.rb:226: warning: duplicated key at line 228 ignored: :name
/ocp/app/models/new_district.rb:233: warning: duplicated key at line 235 ignored: :name
/ocp/lib/nodb/nodb_process.rb:22: warning: already initialized constant LocalErrorMessage::INVALID_API_KEY
/ocp/lib/local_process.rb:18: warning: previous definition of INVALID_API_KEY was here
/ocp/lib/nodb/nodb_process.rb:23: warning: already initialized constant LocalErrorMessage::SYNC_ONGOING
/ocp/lib/local_process.rb:19: warning: previous definition of SYNC_ONGOING was here
/ocp/app/services/patch_through_handler.rb:59: warning: duplicated key at line 59 ignored: :promoter_user_id
/ocp/app/services/patch_through_handler.rb:91: warning: duplicated key at line 91 ignored: :promoter_user_id
/ocp/spec/spec_helper.rb:32: warning: already initialized constant AGENT_ROOT
/ocp/config/initializers/amazon.rb:1: warning: previous definition of AGENT_ROOT was here
/ocp/spec/spec_helper.rb:597: warning: already initialized constant PricePoints::DECIMAL_PRICES
/ocp/spec/spec_helper.rb:590: warning: previous definition of DECIMAL_PRICES was here
/ocp/spec/controllers/api_spec.rb:1017: warning: already initialized constant API_KEY
/ocp/spec/controllers/api_spec.rb:10: warning: previous definition of API_KEY was here
/ocp/spec/spec_ses_helper.rb:73: warning: duplicated key at line 81 ignored: "mail"
/ocp/lib/australia_modules.rb:111: warning: duplicated key at line 129 ignored: "Palmer United Party"
/ocp/lib/australia_modules.rb:107: warning: duplicated key at line 130 ignored: "Liberal National Party of Queensland"
/ocp/spec/libs/importer_modules/australia_import_spec.rb:38: warning: duplicated key at line 38 ignored: :cicero_code
/ocp/lib/importer_modules/united_states/cicero/cicero_us_councils_importer.rb:4: warning: already initialized constant CICERO_RECIPIENT_IMPORTER_VERSION
/ocp/lib/importer_modules/united_states/cicero/cicero_us_recipient_importer.rb:4: warning: previous definition of CICERO_RECIPIENT_IMPORTER_VERSION was here
/ocp/spec/libs/neon_client/custom_object_field_spec.rb:108: warning: duplicated key at line 110 ignored: :name
/ocp/spec/libs/neon_client/custom_object_field_spec.rb:131: warning: duplicated key at line 133 ignored: :name
/ocp/spec/libs/neon_client/custom_object_field_spec.rb:154: warning: duplicated key at line 156 ignored: :name
/ocp/spec/libs/neon_client/custom_object_field_spec.rb:178: warning: duplicated key at line 180 ignored: :name
/ocp/spec/models/recipient_spec.rb:1295: warning: duplicated key at line 1295 ignored: :model_type
/ocp/spec/services/add_recipient_to_promoted_message_spec.rb:18: warning: duplicated key at line 20 ignored: :recipients_code
/ocp/spec/services/delivery_handler_spec.rb:13: warning: already initialized constant METHODS
/ocp/spec/services/delivery_handler_spec.rb:13: warning: previous definition of METHODS was here
/ocp/spec/services/delivery_handler_spec.rb:13: warning: already initialized constant METHODS
/ocp/spec/services/delivery_handler_spec.rb:13: warning: previous definition of METHODS was here
/ocp/spec/services/delivery_handler_spec.rb:13: warning: already initialized constant METHODS
/ocp/spec/services/delivery_handler_spec.rb:13: warning: previous definition of METHODS was here
/ocp/spec/services/retrieve_activity_stream_spec.rb:37: warning: duplicated key at line 37 ignored: :service_send_id
Run options: include {:focus=>true}

All examples were filtered out; ignoring {:focus=>true}

Emailable
  email_regex
    should return regex for an email address
    testing individual addresses
      should work with addresses using top level domains between 2 and 4 characters
      should work with international style addresses
      should work with addresses that contain an apostrophe
      should work with addresses using top level domain museum
      should work with addresses using top level domain travel
      should work with addresses using top level domain global
      should work with addresses using top level domain online
      should not work with addresses that have special characters in the email name of the address
      should not work with addresses that have special characters in the domain head of the address
      should not work with addresses that have special characters in the top-level domain of the address
      should not work with addresses using a 1-character top level domain
      should not work with addresses using a top level domain greater than 4 characters
      should not work with addresses with incomplete/malformed domains

ExternalConnectionModelHelper
  #do_sync?(provider, promoter_user)
    should return true if external_connection does not exist
    should return true if external_connection.last_update is nil
    should return the false if record.updated_at is older than @external_connection.last_update
    should return true if external_connection.last_update
        is older than record.updated_at
    should return false if related ExternalConnection is unsyncable?
  #mark_unsyncable!(provider, message, promoter_id)
    should set :error message
    should change :unsyncable? to true
    should change :do_sync? to false
    should change :do_sync? on @record
  #mark_synced!(provider, external_id, promoter_user_id)
    should return external_id
    should create an ExternalConnection if one does not exits
    should set updated_at to the current time
    should work on models that inherit from models
    should set the external_id
  #external_connection_for(provider, promoter_user)
    should return the ExternalConnection for this :provider and PromoterUser
  #external_id_for(provider, promoter_user)
    Should return nil if no ExternalConnection exists for this Record/provider/PromoterUser
    should return external_id for Record/provider/PromterUser
    should return the external id for the relevant provider
    should return the external id for relevant PromoterUser
  #mark_unsyncable!(provider, message, promoter_user)
    should create an ExternalConnection if one does not exits
    should work on models that inherit from models
    should set :error_message
  #unsyncable?
    should return false if error message is nil
    should return true if error_message is not nil

OneClickWidgetApi::Widget
  required_params
    unimplemented
      by default returns empty array
  initialize_attributes
    should configure instance variables as defined in required_params
  self.logger
    behaves like a widget concern logger
      should be correctly configured
  implemented on a service
    logger
      behaves like a widget concern logger
        should be correctly configured
    required_params
      by default returns empty array

TextingAccountContext
  uses credentials for adult shortcode
  uses credentials for long codes and typical shortcode
    when adult keyword is false
    when adult keyword is true and promoter user does not use ez texting

AccountsController
  POST create
    renders sign_up if recaptcha fails
    renders sign_up if save_without_session_maintenance fails
    when coming from a new action form
      creates a promoter user if promoted_message cookie present
      deletes the cookie after promoter and message
      associates the promoter user to the account
      updates the promoted messages id and shared_flg
      delivers activation instructions
    regular sign up
      doesn't create a promoter user
      delivers activation instructions

ActionCenterController
  routing
    should route GET /nra_action_center to/from {:action=>"show", :controller=>"action_center"}
    should route GET /actions/federal to/from {:action=>"actions_list", :state=>"federal", :controller=>"action_center"}
  controller actions
    GET show
      renders successfully
    GET events_list
      renders successfully
    GET event
      renders successfully
    GET actions_list
      renders a federal page when params[:state] == federal
      renders a state page when params[:state] is a state
      renders a blank federal page when params[:state] is not federal or a state
    POST rsvp
      returns successfully
    GET hosted_campaign_page
      renders the hosted_campaign_page with promoted message

Our web-form messaging system
  Admin::AddressesController
    GET parse
      parses correctly
  The OCP::FormHandler model
    parses our dummy web-form correctly

Admin::ApplicationSwitchesController
  #index
    should collect application switches and render index
  #new
    should instantiate a new application switch and render new
  #create
    should create a new application switch and redirect to index
    when validation fails
      should redirect to new app switch page
  #edit
    should find the application switch by id and render edit
    when application switch with id does not exist
      should render index
  #update
    should update existing application switch
    with nonexistent application switch
      should not update and redirect to application switch index
    when failing to update existing application switch
      should render edit for application switch
  #destroy
    should destroy application switch and redirect to index
    for nonexistent application switch
      should redirect to index with error message
    when failing to destroy application switch
      should redirect to index with error message

Admin::BlogArticlesController
  index
    should get index of blogs in admin view
  new
    should render new
  create
    should create new blog article
    with invalid params
      should fail to create a new blog article and render new
  edit
    should render edit
    with invalid params
      should fail to find nonexistent blog article and redirect to admin blog path
  update
    should update article and redirect to admin blog path
    with invalid params
      should fail to update article and render edit
      should fail to update nonexistent article and redirect to admin blog path
  destroy
    should destroy blog article
    fails to destroy blog article and redirects to admin blog article path

Admin::PromoterUsersController
  routing
    should route GET /admin/promoter_users to/from {:action=>"index", :controller=>"admin/promoter_users"}
    should route POST /admin/promoter_users to/from {:action=>"create", :controller=>"admin/promoter_users"}
    should route PUT /admin/promoter_users/1 to/from {:action=>"update", :id=>"1", :controller=>"admin/promoter_users"}
  Admin interface
    index with 30 Promoters
      #index
        displays email
        sorts by paid/free
        sorts by nation_builder
        searches
    #create
      creates an associated Account
      with send_email param enabled
        should deliver email to new promoter user
      failing to save PromoterUser
        should render new page with flash errors for PromoterUser object
      failing to save Account
        should render new page with flash errors for Account object
      without promoter_is_an_agency? parameter
        should render new page with flash error
      with straight_to_edit param enabled
        should render edit page for new promoter
    #update
      renders edit when save successful
      renders edit when save fails
    #update_password
      succeeding
        updates the password and resets the failed login count
        with send_email field set to true
          delivers promoter password change email
      failing
        should render edit page and not update password
    #change_to_agency
      calling the service and succeeding
        should set success flash message and redirect to edit
      calling the service and failing
        should set error flash message for failure and redirect to edit
      calling the service and erroring
        should set error flash message for error and redirect to edit

Admin::RecipientsController
  handles recipient relations
  when we're a senator or congressman
    lets us create recipients
    doesn't let us create recipients without states
    doesn't let us create recipients without districts
    lets us update recipients
    doesn't let us update recipients without states
    doesn't let us update recipients without districts
  when we're a committee
    lets us create recipients without states, parties, or districts
  when we have an existing Congressman
    lets us deactivate recipients

Admin::UserSessionsController
  POST create
    password functionality
      when the correct password is entered
        with less than 5 failed attempts
          redirects to the admin root
          resets the failed_login_count to 0
        with at least 5 failed attempts
          renders the login screen (admin is banned)
      when an incorrect password is entered
        increments failed_login_count for the admin
        with less than 4 failed attempts
          renders the login screen
        with at least 4 failed attempts
          informs the user they have been locked out
          does NOT let them back in after 2 hours
  when logged in as admin over HTTPS
    allows us in
  when not logged in as admin
    redirects

MessagesController
  routing
    should route POST /api/v1/message/create/1 to/from {:action=>"api_create_v1", :promo_id=>"1", :controller=>"messages"}
    should route GET /api/v1/message/edit/1 to/from {:action=>"api_edit_v1", :promo_id=>"1", :controller=>"messages"}
  using SSL
    with API key and id
      if we aren't paying for API service
        #edit.json
          code
            should eq "401"
          message
            should match "Unauthorized"
      #edit.xml
        the response
          should be success
        the format
          should == "application/xml"
        the body
          should have xml tag promoted-message
        with custom fields 'Gender' and 'Town'
          the body
            should have xml tag promoted-message/custom-fields/custom-field[id='6'][name='Gender'][options='M,F']
            should have xml tag promoted-message/custom-fields/custom-field[id='7'][name='Town'][required='true']
      #edit.json
        should not raise Exception
        the response
          should be success
        the format
          should == "application/json"
        the body
          ["status"]
            should eq "success"
        the data
          ["body"]
            should eq "From blue baleena to the mighty Melvilleian white, beautiful sea monsters, every one."
        with custom fields 'Gender' and 'Town'
          the custom field data
            first
              should eq {"name"=>"Gender", "options"=>"M,F", "id"=>"6"}
            last
              should eq {"name"=>"Town", "id"=>"7", "required"=>true}
      #create.xml
        suspends email confirmation/validation
        creates a conversion
        opts in
        the response
          should be success
        the format
          should == "application/xml"
        the body
          should have xml tag conversion
      #create.json
        creates a conversion
        opts in
        the response
          should be success
        the format
          should == "application/json"
        the body
          ["status"]
            should eq "success"
        the data
          ["promoted_message_id"]
            should eq 23247
          ["subject"]
            should eq "Save the whales 30"
          ["body"]
            should eq "From blue baleena to the mighty Melvilleian white, beautiful sea monsters, every one."
      with a phone number
        #create.json
          records the phone
      when we opt-out
        #create.xml
          suspends email confirmation/validation
          opts out
          the response
            should be success
          the format
            should == "application/xml"
          the body
            should have xml tag conversion
        #create.json
          creates a conversion
          opts out
          the response
            should be success
          the format
            should == "application/json"
          the body
            ["status"]
              should eq "success"
          the data
            ["promoted_message_id"]
              should eq 23261
            ["subject"]
              should eq "Save the whales 44"
            ["body"]
              should eq "From blue baleena to the mighty Melvilleian white, beautiful sea monsters, every one."
      if we've already signed
        #create.xml V1
          should have xml tag error
          should match "You have already sent this message"
          should not send again
        #create.json
          should not send again
          ["id"]
            should not be blank
          ["id"]
            should include "You have already sent this message"
    without API key
      #edit.xml
        code
          should eq "401"
        message
          should match "Unauthorized"
      #create.xml
        code
          should eq "401"
        message
          should match "Unauthorized"
    with an API key that doesn't match the id
      edit.xml
        code
          should eq "401"
        message
          should match "Unauthorized"
      edit.json
        code
          should eq "401"
        message
          should match "Unauthorized"
      create.xml
        code
          should eq "401"
        message
          should match "Unauthorized"
      create.json
        code
          should eq "401"
        message
          should match "Unauthorized"
    without promo_id
      #edit.xml V1
        should have xml tag problems/promo-id
        the response
          code
            should eq "400"
      #edit.json
        should not raise Exception
        the response
          code
            should eq "400"
        the format
          should == "application/json"
        the body
          ["status"]
            should eq "fail"
        problems
          ["promo_id"]
            should eq "A message id number should terminate the URL, or a promo_id parameter is required"
      #create.xml V1
        should have xml tag error
        should include "No ID passed into the call. A campaign ID number should terminate the URL."
        should not send a message
      #create.json
        should not send a message
        the response
          code
            should eq "400"
        the body
          ["status"]
            should eq "fail"
        problems
          ["campaign"]
            should eq "No ID passed into the call. A campaign ID number should terminate the URL."
    with the wrong promo_id
      #edit.xml V1
        should have xml tag problems/promo-id
        the response
          code
            should eq "400"
      #edit.json
        the response
          code
            should eq "400"
        the body
          ["status"]
            should eq "fail"
        problems
          ["promo_id"]
            should eq "A message cannot be found with this ID number"
      #create.json
        should not send a message
        the response
          code
            should eq "400"
        the body
          ["status"]
            should eq "fail"
        problems
          ["campaign"]
            should eq "No campaign found with this ID."
      create.xml
        should have xml tag error
        should include "No campaign found with this ID."
        should not send a message
    when zip is too long
      #create.xml V1
        should have xml tag problems/zip
        should not have xml tag problems/address
        should not have xml tag problems/city
        should not have xml tag problems/email
        should have xml tag problems/id
        should not have xml tag problems/name
        should not send a message
      #create.json
        should not send a message
        ["zip"]
          should not be blank
        ["id"]
          should not be blank
        ["address"]
          should be blank
        ["city"]
          should be blank
        ["email"]
          should be blank
        ["name"]
          should be blank
    with a mixed-case email address
      #create.json
        should send a message
        POSTing again with mixed-cases
          ["status"]
            should eq "success"
        POSTing again in lowercase
          ["status"]
            should eq "success"
    without an email address
      #create.json
        should not send a message
        the response
          code
            should eq "400"
        the body
          ["status"]
            should eq "fail"
    when phone is required but omitted
      #create.xml V1
        should have xml tag problems/phone
        should not have xml tag problems/zip
        should not have xml tag problems/address
        should not have xml tag problems/city
        should not have xml tag problems/email
        should have xml tag problems/id
        should not have xml tag problems/name
        should not send a message
      #create.json
        should not send a message
        ["phone"]
          should not be blank
        ["id"]
          should not be blank
        ["zip"]
          should be blank
        ["address"]
          should be blank
        ["city"]
          should be blank
        ["email"]
          should be blank
    when custom 'Gender' and 'Town' are required
      but not supplied
        #create.xml V1
          should not have xml tag problems/phone
          should not have xml tag problems/zip
          should not have xml tag problems/address
          should not have xml tag problems/city
          should not have xml tag problems/email
          should have xml tag problems/id
          should not have xml tag problems/name
          should have xml tag problems/custom-fields/custom-field-402[text()='Gender is required']
          should have xml tag problems/custom-fields/custom-field-405[text()='Town is required']
          should not send a message
        #create.json
          should not send a message
          ["phone"]
            should be blank
          ["zip"]
            should be blank
          ["id"]
            should not be blank
          ["address"]
            should be blank
          ["city"]
            should be blank
          ["email"]
            should be blank
          problems[custom_fields]
            keys
              should include "custom_field_422"
            keys
              should include "custom_field_425"
            values
              should include "Gender is required"
            values
              should include "Town is required"
      and supplied
        #create.xml V1
          should send a message
        #create.json
          should send a message
    When update_conversion_with_recipients raises an error
      xml
        should have xml tag error
        should include "There was an error saving recipients to this conversion."
        should not send a message
      json
        should not send a message
        the response
          code
            should eq "400"
        the body
          ["status"]
            should eq "fail"
        problems
          ["campaign"]
            should eq "There was an error saving recipients to this conversion."
    Setting conversion recipient and multi_content columns
      sets multi_content columns on conversion

Promoter::ProfilesController
  Old API
    using SSL
      with API key and promoter_id
        #profile.xml
          the response
            should be success
          the format
            should == "application/xml"
          the body
            should have xml tag promoter/name
            should have xml tag promoter/call_to_action
            should have xml tag promoter/mission_statement
            should have xml tag promoter/our_work
            should have xml tag promoter/our_values
      without promoter_id
        #profile.xml
          the response
            code
              should eq "400"
          the format
            should == "application/xml"
          the body
            should have xml tag problems/promoter-id
      without API key
        #profile.xml
          should have xml tag error
    without SSL
      #profile.xml
        the response
          should not be success (PENDING: No reason given)
  API v1
    using SSL
      with API key and promoter_id
        #profile.xml
          the response
            should be success
          the format
            should == "application/xml"
          the body
            should have xml tag promoter/name
            should have xml tag promoter/call_to_action
            should have xml tag promoter/mission_statement
            should have xml tag promoter/our_work
            should have xml tag promoter/our_values
        #profile.json
          the response
            should be success
          the format
            should == "application/json"
          the body
            should not raise Exception
            ["status"]
              should eq "success"
            the data
              ["name"]
                should eq "Save the Whales"
              ["call_to_action"]
                should eq "Here is our call to action!"
              ["mission_statement"]
                should eq "Finally, our mission statement."
              ["our_work"]
                should eq "Behold: our work."
              ["our_values"]
                should eq "These are our values."
      without promoter_id
        #profile.xml
          the response
            code
              should eq "400"
          the format
            should == "application/xml"
          the body
            should have xml tag problems/promoter-id
        #profile.json
          the response
            should not be success
            code
              should eq "400"
          the format
            should == "application/json"
          the body
            should not raise Exception
            ["status"]
              should eq "fail"
            the problems
              ["promoter_id"]
                should eq "A promoter_id parameter is required"
      without API key
        #profile.xml
          code
            should eq "401"
          message
            should match "Unauthorized"
        #profile.json
          code
            should eq "401"
          message
            should match "Unauthorized"
    without SSL
      #profile.xml
        the response
          should not be success

AwsController
  Our bounced email webhook
    for a CustomRecipient's EmailAddress
      POST ses_bounce
        the response
          should be success
        the Email
          bad_address_flg
            should equal true
    for two EmailAddress records
      POST ses_bounce
        the response
          should be success
        the first Email
          bad_address_flg
            should equal true
        the second Email
          bad_address_flg
            should equal true
    given a BounceType
      Undetermined
        behaves like a bounce handler
          logs the bounce type
          marks EmailAddress.bad_address_flg=true
          marks EmailAddress.bad_address_type
      Permanent
        Permanent (General)
          behaves like a bounce handler
            logs the bounce type
            marks EmailAddress.bad_address_flg=true
            marks EmailAddress.bad_address_type
        Permanent (No Email)
          behaves like a bounce handler
            logs the bounce type
            marks EmailAddress.bad_address_flg=true
            marks EmailAddress.bad_address_type
        Permanent (Suppressed)
          behaves like a bounce handler
            logs the bounce type
            marks EmailAddress.bad_address_flg=true
            marks EmailAddress.bad_address_type
        Permanent (OnAccountSuppressionList)
          behaves like a bounce handler
            logs the bounce type
            marks EmailAddress.bad_address_flg=true
            marks EmailAddress.bad_address_type
      Transient
        Transient (General)
          behaves like a bounce handler
            logs the bounce type
            marks EmailAddress.bad_address_flg=true
            marks EmailAddress.bad_address_type
        Transient (MailBoxFull)
          behaves like a bounce handler
            logs the bounce type
            marks EmailAddress.bad_address_flg=true
            marks EmailAddress.bad_address_type
        Transient (MessageTooLarge)
          behaves like a bounce handler
            logs the bounce type
            marks EmailAddress.bad_address_flg=true
            marks EmailAddress.bad_address_type
        Transient (ContentRejected)
          behaves like a bounce handler
            logs the bounce type
            marks EmailAddress.bad_address_flg=true
            marks EmailAddress.bad_address_type
        Transient (AttachmentRejected)
          behaves like a bounce handler
            logs the bounce type
            marks EmailAddress.bad_address_flg=true
            marks EmailAddress.bad_address_type
  our data pipeline success webhook
    with a NoDB Pipeline transaction
      POST data_pipeline_success
        deletes the pipeline and sends a notification email

BlankPageForCookiesController
  routing
    should route GET /blank_page_for_cookies to/from {:action=>"show", :controller=>"blank_page_for_cookies"}
  controller actions
    #SHOW
      renders

BlogController
  index
    should get index of blogs
    should get index of blogs with page param
  show
    should show blog article
    with invalid params
      should redirect to blogs page when blog doesnt exist

HelpController
  routing
    should route GET / to/from {:action=>"index", :controller=>"help"}
    should route GET /mission to/from {:action=>"mission", :controller=>"help"}
    should route GET /culture to/from {:action=>"culture", :controller=>"help"}
    should route GET /recognition to/from {:action=>"recognition", :controller=>"help"}
    should route GET /associations to/from {:action=>"associations", :controller=>"help"}
    should route GET /nonprofits to/from {:action=>"nonprofits", :controller=>"help"}
    should route GET /agencies to/from {:action=>"agencies", :controller=>"help"}
    should route GET /startups to/from {:action=>"startups", :controller=>"help"}
    should route GET /corporations to/from {:action=>"corporations", :controller=>"help"}
    should route GET /united-states to/from {:action=>"united_states", :controller=>"help"}
    should route GET /canada to/from {:action=>"canada", :controller=>"help"}
    should route GET /australia to/from {:action=>"australia", :controller=>"help"}
    should route GET /advocacy to/from {:action=>"advocacy", :controller=>"help"}
    should route GET /acquisition to/from {:action=>"acquisition", :controller=>"help"}
    should route GET /advisory to/from {:action=>"advisory", :controller=>"help"}
    should route GET /bill-tracking to/from {:action=>"bill_tracking", :controller=>"help"}
    should route GET /grasstrends to/from {:action=>"grasstrends", :controller=>"help"}
    should route GET /case-studies to/from {:action=>"case_study", :controller=>"help"}
    should route GET /whitepapers to/from {:action=>"whitepapers", :controller=>"help"}
    should route GET /testimonials to/from {:action=>"testimonials", :controller=>"help"}
    should route GET /integrations to/from {:action=>"integrations", :controller=>"help"}
    should route GET /careers to/from {:action=>"careers", :controller=>"help"}
    should route GET /contact-modal to/from {:action=>"contact_us", :displaying=>"modal", :controller=>"help"}
    should route GET /terms to/from {:action=>"show_terms_conditions", :controller=>"help"}

Messages::OneClick::ContactsController
  #edit
    should respond with ok

Messages::OneClick::PostsController
  #create
    when there is no exception raised
      sets the @recipients variable to @handler.add_phone.recipient_objects
    when an exception is raised
      logs the exception
      returns a blank array
      rescues the exception (doesn't bubble up)

Messages::OneClick::VideosController
  routing
    should route POST /widget/oneclick/1/videos to/from {:action=>"create", :id=>"1", :widget=>"oneclick", :controller=>"messages/one_click/videos"}
    should route GET /widget/oneclick/1/videos/new to/from {:action=>"new", :id=>"1", :widget=>"oneclick", :controller=>"messages/one_click/videos"}
    should route GET /widget/oneclick/1/videos/guide to/from {:action=>"guide", :id=>"1", :widget=>"oneclick", :controller=>"messages/one_click/videos"}
    should route GET /video_messages/1 to/from {:action=>"show", :video_id=>"1", :widget=>"oneclick", :controller=>"messages/one_click/videos"}
  #guide
    redirects without a sessioned sender profile
    with a sessioned sender profile
      responds with ok
      redirect when there's an existing video
        redirects to the first page of the widget
  #new
    redirects without a sessioned sender profile
    with a sessioned sender profile
      responds with ok
      redirect
        redirects to the first page of the widget
  #create.json
    redirects without a sessioned sender profile
    with a sessioned sender profile
      passes the sender profile to the OneclickWidgetHandler
      passes the video_token and video_opt_in to add_video
      when the service send is invalid
        responds with an error
      when the service send is valid
        responds with ok
  #show
    responds with ok for html
    responds with ok for js

MessagesController
  routes
    routes visit/:id
  the visits ajax call
    when visiting widgets over Fastly or a CDN
      with a sessioned_profile_id and the load_profile flag
        fetches sender_data

OneClickWidgetApiController
  GET promoted_message_data
    for existing promoter
      with promoted message belonging to promoter
        when request host is not the same as the whitelisted host
          should return forbidden response
        when request host is the same as the whitelisted host
          should return promoted message data needed for one click widget
      with promoted message belonging to another promoter
        should return error json
      with non existing promoted message
        should return error json
      with optin as true and the default message
        should return the default message
      with optin as true and custom optin message set
        should return the custom optin message
      with show actions progress set we should send the progress number and text
        should return the action progress count
        should return the action progress message
    for non existing promoter
      should return error json
  POST submit_sender_data
    with bad promoter info
      should return failure status and message
      should not create new data
    with valid promoter info
      with valid US sender data
        should return recipient data
        should create advocate data
      with sender data including honeypot fields
        zip-confirmation
          should return success response with no other data
          should not create new data
        email-confirmation
          should return success response with no other data
          should not create new data
      with invalid US sender data
        should return failure status
        should not create new data
  POST submit_email_conversion
    with promoter and campaign
      should return success response
      should return correct social urls
  POST patch_call
    should return 200 response
    should make phone service send record for conversion if missing
    when phone service send already exists for conversion
      should find existing phone service send

Promoter::ActionCenter::ActionCenterPagesController
  routing
    should route GET /promoter/1/action_center_pages to/from {:action=>"index", :promoter_id=>"1", :controller=>"promoter/action_center/action_center_pages"}
    should route PUT /promoter/1/action_center_pages/update_all to/from {:action=>"update_all", :promoter_id=>"1", :controller=>"promoter/action_center/action_center_pages"}
    should route GET /promoter/1/action_center_pages/2/edit to/from {:action=>"edit", :promoter_id=>"1", :id=>"2", :controller=>"promoter/action_center/action_center_pages"}
    should route PUT /promoter/1/action_center_pages/2 to/from {:action=>"update", :promoter_id=>"1", :id=>"2", :controller=>"promoter/action_center/action_center_pages"}
    should route PUT /promoter/1/action_center_pages/2/remove_promoted_message to/from {:action=>"remove_promoted_message", :promoter_id=>"1", :id=>"2", :controller=>"promoter/action_center/action_center_pages"}
  controller actions
    with action_center_control_panel set to false
      redirects a user to their dashboard
    with action_center_control_panel set to true
      proxied promoter access
        lets a proxied promoter navigate this controller
      agency and sub-account access
        #index
          should render index
          should set instance variables for agency
          should set instance variables for sub-account
        #update_all
          should update_all
          should redirect_to the action_center_pages index
        #edit
          should render edit template
          should display both the agency and sub-accounts' campaigns
          should split campaigns into assigned and unassigned and order by internal_campaign_name
          with sub-account logged in
            should display both the agency and sub-accounts' campaigns
        #update
          should render update.js
          should assign promoted_message to action_center_page
          should assign instance variables correctly after the update
          with sub-account logged in
            should assign instance variables correctly after the update
        #remove_promoted_message
          should render remove_promoted_message.js
          should remove promoted_message from action_center_page
          should assign instance variables correctly after the remove
          with sub-account logged in
            should assign instance variables correctly after the remove

Promoter::Agency::ActivityDashboardsController
  routing
    should route GET /promoter/1/agency_analytics to/from {:action=>"show", :promoter_id=>"1", :controller=>"promoter/agency/activity_dashboards"}
    should route GET /promoter/1/agency_analytics/sort_offices to/from {:action=>"sort_offices", :promoter_id=>"1", :controller=>"promoter/agency/activity_dashboards"}
  actions
    GET show
      returns http success
      gracefully handles an error
    GET sort_offices
      returns http success
      gracefully handles an error

Promoter::Reporting::AdvocateAggregateGraphsController
  routing
    should route GET /promoter/1/analytics/campaigns to/from {:action=>"show", :promoter_id=>"1", :controller=>"promoter/reporting/advocate_aggregate_graphs"}
    should route POST /promoter/1/analytics/campaigns/data to/from {:action=>"data", :promoter_id=>"1", :controller=>"promoter/reporting/advocate_aggregate_graphs"}
    should route POST /promoter/1/analytics/campaigns/csv to/from {:action=>"csv", :promoter_id=>"1", :controller=>"promoter/reporting/advocate_aggregate_graphs"}
  controller actions
    proxied promoter
      lets a proxied promoter navigate this controller
    regular promoter
      POST CSV
        returns csv format
        renders show on error
      GET show
        returns http success
      POST data
        returns results_data json on successful call (tests default dates too) (FAILED - 1)
        returns error_message json on call with error (FAILED - 2)

Promoter::Reporting::AdvocateExportsController
  routing
    should route GET /promoter/1/advocate_exports to/from {:action=>"index", :promoter_id=>"1", :controller=>"promoter/reporting/advocate_exports"}
    should route GET /promoter/1/advocate_exports/1 to/from {:action=>"show", :promoter_id=>"1", :id=>"1", :controller=>"promoter/reporting/advocate_exports"}
    should route GET /promoter/1/advocate_exports/new to/from {:action=>"new", :promoter_id=>"1", :controller=>"promoter/reporting/advocate_exports"}
    should route POST /promoter/1/advocate_exports to/from {:action=>"create", :promoter_id=>"1", :controller=>"promoter/reporting/advocate_exports"}
  proxied promoter
    lets a proxied promoter navigate this controller
  regular promoter
    GET index
      renders index page with correct variable
    GET show
      returns http success and correct variables for successful calls
      redirects to promoter_advocate_exports_path when error
    GET new
      renders js
    POST create
      creates a new advocate_export and renders js
      displays errors for a failed advocate_export and renders js

Promoter::Reporting::AdvocateForPromotersController
  routing
    should route GET /promoter/1/advocate_profiles to/from {:action=>"index", :promoter_id=>"1", :controller=>"promoter/reporting/advocate_for_promoters"}
    should route GET /promoter/1/advocate_profiles/2 to/from {:action=>"show", :promoter_id=>"1", :id=>"2", :controller=>"promoter/reporting/advocate_for_promoters"}
    should route GET /promoter/1/advocate_profiles/by_email to/from {:action=>"by_email", :promoter_id=>"1", :controller=>"promoter/reporting/advocate_for_promoters"}
  controller actions
    regular promoter
      GET index
        renders js for index call
      GET show
        returns http success and correct variables for successful calls
        returns http success and correct variables for calls with errors
        conglomerates errors correctly if errors on both services

Promoter::Reporting::CountryMapsController
  routing
    should route GET /promoter/1/advocate-universe to/from {:action=>"show", :promoter_id=>"1", :controller=>"promoter/reporting/country_maps"}
    should route GET /promoter/1/advocate-universe/data to/from {:action=>"data", :promoter_id=>"1", :controller=>"promoter/reporting/country_maps"}
    should route GET /promoter/1/advocate-universe/profile_info_by_email to/from {:action=>"profile_info_by_email", :promoter_id=>"1", :controller=>"promoter/reporting/country_maps"}
  controller actions
    proxied promoter
      lets a proxied promoter navigate this controller
    regular promoter
      GET show
        returns http success
      GET data
        returns all data as json on successful call
        returns country map data for a filter
      GET profile_info_by_email
        returns correct json for successful call
        returns error on failed call

Promoter::Reporting::EmailBodiesController
  routing
    should route GET /promoter/1/email_bodies to/from {:action=>"index", :promoter_id=>"1", :controller=>"promoter/reporting/email_bodies"}
    should route GET /promoter/1/email_bodies/2 to/from {:action=>"show", :promoter_id=>"1", :id=>"2", :controller=>"promoter/reporting/email_bodies"}
  controller actions
    proxied promoter
      lets a proxied promoter navigate this controller
    regular promoter
      GET index
        html
          renders blank page for successful index call with promoter's promoted messages
      POST data
        renders data template
      GET show
        rendering and instance variable setting
          js and instance variable setting
            renders successfully without multi_content
            renders successfully with multi_content content_one
            renders successfully with multi_content content_two
          pdf
            renders successfully
            passes content_two to PDF if multi_content content_two

Promoter::Reporting::EmailBodyExportsController
  routing
    should route GET /promoter/1/email_body_exports to/from {:action=>"index", :promoter_id=>"1", :controller=>"promoter/reporting/email_body_exports"}
    should route GET /promoter/1/email_body_exports/1 to/from {:action=>"show", :promoter_id=>"1", :id=>"1", :controller=>"promoter/reporting/email_body_exports"}
    should route GET /promoter/1/email_body_exports/new to/from {:action=>"new", :promoter_id=>"1", :controller=>"promoter/reporting/email_body_exports"}
    should route POST /promoter/1/email_body_exports to/from {:action=>"create", :promoter_id=>"1", :controller=>"promoter/reporting/email_body_exports"}
  proxied promoter
    lets a proxied promoter navigate this controller
  regular promoter
    GET index
      renders index page with correct variable
    GET show
      returns http success and correct variables for successful calls
      redirects to promoter_email_body_exports_path when error
    GET new
      renders js
    POST create
      creates a new email_body_export and renders js
      displays an error for a failed email_body_export and renders js

Promoter::Reporting::LegislatorAggregateGraphsController
  routing
    should route GET /promoter/1/analytics/legislators to/from {:action=>"show", :promoter_id=>"1", :controller=>"promoter/reporting/legislator_aggregate_graphs"}
    should route GET /promoter/1/analytics/legislators/recipients_for_search to/from {:action=>"recipients_for_search", :promoter_id=>"1", :controller=>"promoter/reporting/legislator_aggregate_graphs"}
    should route GET /promoter/1/analytics/legislators/committees_for_search to/from {:action=>"committees_for_search", :promoter_id=>"1", :controller=>"promoter/reporting/legislator_aggregate_graphs"}
    should route GET /promoter/1/analytics/legislators/states_for_search to/from {:action=>"states_for_search", :promoter_id=>"1", :controller=>"promoter/reporting/legislator_aggregate_graphs"}
    should route POST /promoter/1/analytics/legislators/data to/from {:action=>"data", :promoter_id=>"1", :controller=>"promoter/reporting/legislator_aggregate_graphs"}
    should route POST /promoter/1/analytics/legislators/csv to/from {:action=>"csv", :promoter_id=>"1", :controller=>"promoter/reporting/legislator_aggregate_graphs"}
  controller actions
    proxied promoter
      lets a proxied promoter navigate this controller
    regular promoter
      GET show
        returns http success
      POST CSV
        returns CSV format
        returns correct CSV name with return_in_aggregate params
        returns correct CSV name with no return_in_aggregate params
        passes return_in_aggregate as true in to service if params return_in_aggregate present (FAILED - 3)
        renders show on error
        returns an office from level and country (FAILED - 4)
      GET recipients_for_search
        responses
          returns results_data json on successful call (tests assigning office too)
          returns error_message json on call with error
      GET committees_for_search
        responses
          returns results_data json on successful call (tests default dates too)
          returns error_message json on call with error
      GET states_for_search
        responses
          returns results_data json on successful call (tests default dates too)
      POST data
        responses
          returns results_data json on successful call (tests default dates too)
        set_office_instance_variable works
          returns US Senate from params
          returns US House from params
          returns US State Senate from params
          returns US State House from params
          returns Canada Senate from params
          returns Canada House from params
          returns Canada Provincial Assembly from params
          returns Australia Senate from params
          returns Australia House from params
          returns Australia State Council from params
          returns Australia State Assembly from params

Promoter::LegislatorProfilesController
  proxied promoter
    lets a proxied promoter navigate this controller
  regular promoter
    GET #show
      returns http success on an HTML request
      returns http success on a JS request
  legislator_filter
    with default page param
      should collect paginated legislators with filter legislators service and render js
    with passed page param
      should collect paginated legislators with filter legislators service and render js
  legislator_staff_search
    with default page param
      should collect paginated staff with filter staff service and render js
    with passed page param
      should collect paginated staff with filter staff service and render js
  legislator_staff_export
    should deliver staff data for a legislator exported as csv attachment
  legislator_staff_search_export
    should deliver staff data exported as csv attachment
  legislator_filter_export
    should deliver legislator filter data exported as csv attachment
  responsibilities_for_search
    should return responsibilities that match search term as a substring
    with term matching no values
      should return error status and error message

Promoter::MessagesController
  routing
    should route GET /promoter/1/trainings to/from {:action=>"training", :promoter_id=>"1", :controller=>"promoter/messages"}
    should route POST promoter/1/messages/1/duplicate to/from {:action=>"duplicate", :promoter_id=>"1", :id=>"1", :controller=>"promoter/messages"}
  add_recipient
    adds single recipient
  all actions
    #index
      renders html and assigns instance variables
      renders js
    #new
      renders the new template
    #edit
      renders the edit page
    #create
      sets the video_action_flg
    #update
      shows a flash message with the error message when message cant save
      updates the video_action_flg
      updates the video guide text
      allows video_text to be nil or blank
      updates the video opt in text
      allows video_opt_in_text to be nil or blank
      the topic is saved to the promoted message
      updates the country
    #retire
      renders js and sets flash notice on successful retire
      renders js and sets flash error on failed retire
      redirects_to index on html render
    #resume
      renders js and sets flash notice on successful resume
      renders js and sets flash error on failed resume
      renders js and sets flash error if promoter_user hit_solo_tier_message_limit
      redirects_to index on html render
    #duplicate
      renders js and sets flash notice on successful duplication
      renders js and sets flash error on failed duplication
    #state_selector
      extensive testing of the find_state method:
        for 'New York'
          should eq "NY"
        for 'new york'
          should eq "NY"
        for 'NewYork'
          should eq "NY"
        for 'newyork'
          should eq "NY"
        for 'New+York'
          should eq "NY"
        for 'new+york'
          should eq "NY"
      for United States
        with state
          with chamber
            renders js
          without chamber
            renders js
        without state
          renders html
      for Canada
        with state
          with chamber
            renders js
          without chamber
            renders js
        without state
          renders html
      for Australia
        with state
          with chamber
            renders js
          without chamber
            renders js
        without state
          renders html
    #select_recipients
      with state_code params
        renders js
      without state_code_params
        works without chamber
        works with chamber == 'house'
        works with chamber == 'senate'
        works with chamber == 'canada_house'
        works with chamber == 'canada_senate'
        works with chamber == 'Australia House of Representatives'
        works with chamber == 'Australia Senate'
        works with UK House of Representatives
        with CouncilMembers
          with city = 'San Jose' and search='Sam'
            works
            returns only matches inside the city
            doesn't return matches outside of the city
    #add_recipient
      doesn't display a confirmation flash
      with require phone ON (true)
        for US national recipients
          no error flash displays for groups
      with require phone OFF (false)
        for US national recipients
          require phone should start out OFF (false)
          an error flash displays for senate_recipient
          an error flash displays for committees
          an error flash displays for groups
          require phone should be changed to ON (true)
        for US non-national recipients
          require phone should start out OFF (false)
          no error flash for state recipient
          no error flash for custom recipient
          require phone should still be OFF (false)
        for non-US national recipients
          require phone should start out OFF (false)
          no error flash displays for non-US recipient
          no error flash displays for groups
          require phone should still be OFF (false)
      with multi_content true
        groups
          passes the necessary arguments to AddRecipientToPromotedMessage
        with existing SelectedRecipient
          for content_one
            updates existing recipients_code and recipients_code_content_one
            sets recipients_code and recipients_code_content_one to params when none exist
          for content_two
            updates existing recipients_code and recipients_code_content_two
            sets recipients_code and recipients_code_content_two to params when none exist
        without existing SelectedRecipient
          for content_one
            sets recipients_code and recipients_code_content_one
          for content_two
            sets recipients_code and recipients_code_content_one
    #remove_recipient
      with multi_content true
        for content_one
          removes content_one recipients if they are in a list
          removes content_one recipients if there is just one
        for content_two
          removes content_two recipients if they are in a list
          removes content_two recipients if there is just one
    #clear_recipients
      with multi_content false
        clears recipients_code
      with multi_content true
        responds with a 200 if no recipients for selected content
        for content_one
          removes content_one recipients
        for content_two
          removes content_two recipients
    POST #refine_recipients
      for an inactive Senator
        should eq []
      for an inactive House rep
        should eq []
      when params[:committee] == 'house'
        returns American federal committees
      when params[:committee] == 'senate'
        returns American federal committees
    GET #show_committee_members
      renders js
      hides with params[:hide]

Promoter::Nimble::SyncsController
  POST create
    assigns the @error variable on SyncNimble error
    assigns the @error variable on RefreshAccessToken error
    assigns a flash[:notice] on SyncNimble success
    calls SyncNimble with manual: true
    passes the destination_email parameter to the SyncNimble service

Promoter::Agency::OfficesController
  allows an admin user to navigate this controller
  routing
    should route GET /promoter/1/offices to/from {:action=>"index", :promoter_id=>"1", :controller=>"promoter/agency/offices"}
    should route GET /promoter/1/offices/1 to/from {:action=>"show", :promoter_id=>"1", :id=>"1", :controller=>"promoter/agency/offices"}
    should route GET /promoter/1/offices/new to/from {:action=>"new", :promoter_id=>"1", :controller=>"promoter/agency/offices"}
    should route POST /promoter/1/offices to/from {:action=>"create", :promoter_id=>"1", :controller=>"promoter/agency/offices"}
    should route PUT /promoter/1/offices/1 to/from {:action=>"update", :promoter_id=>"1", :id=>"1", :controller=>"promoter/agency/offices"}
    should route POST /promoter/1/offices/1/subscribe to/from {:action=>"subscribe", :promoter_id=>"1", :id=>"1", :controller=>"promoter/agency/offices"}
    should route POST /promoter/1/offices/1/unsubscribe to/from {:action=>"unsubscribe", :promoter_id=>"1", :id=>"1", :controller=>"promoter/agency/offices"}
    should route DELETE /promoter/1/offices/1 to/from {:action=>"destroy", :promoter_id=>"1", :id=>"1", :controller=>"promoter/agency/offices"}
    should route POST /promoter/1/offices/1/pause to/from {:action=>"pause", :promoter_id=>"1", :id=>"1", :controller=>"promoter/agency/offices"}
    should route POST /promoter/1/offices/1/unpause to/from {:action=>"unpause", :promoter_id=>"1", :id=>"1", :controller=>"promoter/agency/offices"}
    should route GET /promoter/1/offices/check_nation_builder to/from {:action=>"check_nation_builder", :promoter_id=>"1", :controller=>"promoter/agency/offices"}

Promoter::PromoterController
  #active_subscription?
    returns false with nil stripe_customer_token
  #nation_builder_test
    GET
      should render template
      should return a successful status
    POST
      should set @message to a waring if no Master Account exists for this PromoterUser
      should set @message to warning if no appropriate Authentication exists
      PromoterUser has approprate Auth
        should assign a success @message if successful
        should assign a success message, if an email collisions validation error occurs
        should assign a fail message, if an auth error occurs
  #api_key
    status is ok
    response has promoter api access key
    returns error message if OCP_API_KEY is wrong (FAILED - 5)
    returns error message if promoter id not found

Promoter::Reporting::ReportingController
  routing
    should route POST /promoter/1/analytics/update_multi_content_selector to/from {:action=>"update_multi_content_selector", :promoter_id=>"1", :controller=>"promoter/reporting/reporting"}
  controller actions
    proxied promoter
      lets a proxied promoter navigate this controller
  regular promoter
    POST update_multi_content_selector
      renders update_multi_content_selector and returns only 'All Content' when no message_ids passed in
      gives correct multi_content_names, sorted alphabetically

Promoter::ActionCenter::SliderPanelsController
  routing
    should route GET /promoter/26423/slider_panels to/from {:action=>"index", :promoter_id=>"26423", :controller=>"promoter/action_center/slider_panels"}
    should route GET /promoter/26424/slider_panels/new to/from {:action=>"new", :promoter_id=>"26424", :controller=>"promoter/action_center/slider_panels"}
    should route POST /promoter/26425/slider_panels to/from {:action=>"create", :promoter_id=>"26425", :controller=>"promoter/action_center/slider_panels"}
    should route GET /promoter/26426/slider_panels/45/edit to/from {:action=>"edit", :promoter_id=>"26426", :id=>"45", :controller=>"promoter/action_center/slider_panels"}
    should route DELETE /promoter/26428/slider_panels/46 to/from {:action=>"destroy", :promoter_id=>"26428", :id=>"46", :controller=>"promoter/action_center/slider_panels"}
  controller actions
    with action_center_control_panel set to false
      redirects a user to their dashboard
    with action_center_control_panel set to true
      proxied promoter access
        lets a proxied promoter navigate this controller
      agency access
        should index
        should edit
        should new
        should create
        should update
        should destroy

Promoter::Agency::SubAccountsController
  routing
    should route GET /promoter/1/sub_accounts/1/edit to/from {:action=>"edit", :promoter_id=>"1", :id=>"1", :controller=>"promoter/agency/sub_accounts"}
    should route PUT /promoter/1/sub_accounts/1 to/from {:action=>"update", :promoter_id=>"1", :id=>"1", :controller=>"promoter/agency/sub_accounts"}
  non_agency promoter
    redirects a promoter who is not an agency
  proxied promoter
    lets a proxied promoter navigate this controller
  agency promoter
    GET edit
      renders js
    PUT update
      successfully renders js on good service call
      displays error if error in service call

Promoter::TextMessageGroupsController
  Get index
    is a success
    renders index template
    proxied promoter
      lets a proxied promoter navigate this controller
  Get new
    is a success
    renders new template
  Delete confirmation renders
    render response
    delete the message via the route.
  Post create
    works
    fails to process group
    raises error and redirects to new path

Promoter::TextMessageKeywordsController
  Get new
    is a success
    renders new template
    proxied promoter
      lets a proxied promoter navigate this controller
  Post create
    is a success
    fails to process and redirects to overview path when promoter user is at their keyword limit
    fails to process and redirects to new keyword path
  Get edit
    is a success
  Post update
    is a success
    fails to process and redirects to edit
    fails to save and redirects to edit

Promoter::TextMessagesController
  Get index
    is a success
    renders index template
    make sure redirection occurs when text messaging turned off
    proxied promoter
      lets a proxied promoter navigate this controller
  Get landing page
    is a success
    renders index template
  Get Overview
    is a success
    renders overview template
    make sure redirection occurs when text messaging turned off
    error pops up on screen if promoter user has too many keywords
  Get landing loads
    is a success
    renders overview template
    make sure redirection occurs when text messaging turned off
  Get New
    is a success
    renders new template
    make sure redirection occurs when text messaging turned off
  routing for reports
    check to see if route exist
    detailed routes

Promoter::UserSessionsController
  POST create
    password functionality
      when the correct password is entered
        with less than 5 failed attempts
          redirects to the promoter's home page
          resets the failed_login_count to 0
        with at least 5 failed attempts
          redirects to the reset password page (promoter is banned)
      when an incorrect password is entered
        increments failed_login_count for the promoter
        with less than 4 failed attempts
          renders the login screen
        with at least 4 failed attempts
          redirects to the reset password page
          informs the user
          lets them back in after 2 hours
    when we log in as a PromoterUser
      if there isn't an associated Account
        creates an account (PENDING: No reason given)
        logs in the promoter
      if there is an associated Account
        creates a promoter user session
    on POST promoter_user_session
      as an Agency
        directs user to agency/offices show
        directs user to agency show

Promoter::VideoServiceSendsController
  proxied promoter
    lets a proxied promoter navigate this controller
  regular promoter
    GET index
      renders the index template
      retrieves the promoter's videos and assigns @promoter_user
      calls VideoServiceSend.for_promoter with correct promoter_id and filters
      includes sender information with the videos
      includes opt in information with the videos
      limits the results to 12
    PUT reject
      with an existing VideoServiceSend
        changes the status of the post to 'REJECTED'
        cannot be updated by the wrong promoter
        with an invalid VideoServiceSend
          returns a 400
    PUT accept
      with an existing VideoServiceSend
        cannot be updated by the wrong promoter
        with an invalid transaction
          returns errors when the VideoServiceDelivery is invalid
          doesn't update the VideoServiceSend's status
        with a valid transaction
          changes the status of the post to 'ACCEPTED'
          initiates a VideoServiceDelivery transaction
          with an invalid VideoServiceSend
            returns a 400

PromoterAdvocateDetailsController
  GET index
    limit and offset are not present
      status is bad request
      returns error message
    limit and offset are present
      status is success
      response has advocate details
      returns empty array when offset is greater than total records

Admin::PromoterUsersController
  rejects the public
  rejects promoters
  rejects users
  lets admins in

Promoter::MessagesController
  rejects the public
  rejects users
  lets the right promoter in
  rejects the wrong promoter
  lets admins in

ServiceSendDetailsController
  GET index
    conversion ids are not present
      status is bad request
      returns error message
    conversion ids are present
      status is success
      response has service send details

SitemapController
  routing
    should route GET /sitemap.xml to/from {:action=>"index", :format=>"xml", :controller=>"sitemap"}

Twilio::CallsController
  using SSL
    with the auth l/p
      passing Twilio's RequestValidator
        #test.json
          code
            should eq "200"
      failing Twilio's RequestValidator
        #test.json
          code
            should eq "401"
    without the auth l/p
      #test.json
        code
          should eq "401"
        message
          should match "Unauthorized"

UserSessionsController
  /UserSessions
    when we log in
      if there is not an associated PromoterUser
        signs in as a user
      if there is an associated PromoterUser
        signs us in as a User

Account Creation
  when a PromoterUser is logged in
    when we fill out the widget
      should have an active PromoterUser session
      should not have an active UserSession
      when we activate our email
        should have an active PromoterUser session
         should not have an active UserSession

admin page
  selecting nation_builder auths
    shows the nation_builder auth (FAILED - 6)
    doesn't show the nimble auth (FAILED - 7)
    assigning the authentication to another promoter
      reassigns the authentication (FAILED - 8)
      changing it back
        returns it (FAILED - 9)

Visiting advocate_aggregate_graphs#show
  renders the graph

Advocate Export to CSV
  validity
    without advocate_export_options
      is invalid
    without destination_email
      is invalid
    without path_name
      is invalid
    with a completed transaction with duplicate path_name
      is valid first run and invalid with a duplicate path_name the second run
    with an in_progress transaction with duplicate path_name
      is not valid
    with invalid characters in the path_name
      is invalid
    with too many characters in the path_name
      is invalid
    with an invalid email
      is invalid
    with valid params with perfect email
      is valid
    with valid params where email has whitespaces that are stripped
      is valid
  inner logic
    creates a new csv and local transaction with success status for valid call to advocate_export (even with whitespaces in the destination_email)
    creates a new transaction with failed status and sends slack notification when error raised in advocate_export

Promoter::Agency::AgencyController
  index
    as an Agency
      lists promoter users
      adding a promoter
        has form for new promoter
        creating a vaild promoter
          renders promoters dashboard
          adds promoter to agency
        creating an invaild Office
          renders password confirmation error
      adding a NationBuilder office
        if an Authentication already exists
          should eq 0
        if NB doesn't list this org uid
          should eq 0
        if the NB org id exists and isn't already Authenticated
          should eq 1
          the dashboard
            should have content "new_nb_org"
    as a non-Agency Promoter
      shows the Agency-only message

an Office
  when unsubscribed
    if the Agency is active
      doesn't show plans
      sees the 'contact Agency' paywall
    if the Agency-reseller offers us tier 'enterprise' and cycle 'six_month'
      should have content "has offered you the following service plan"
      sees the name, duration, and MSRP price
      clicking 'Accept'
        should not have content "has offered you the following service plan"
        should eq "six_month"
      clicking 'No thanks'
        should not have content "has offered you the following service plan"
        should eq "yearly"
  when trialing
    if the Agency is a reseller
      sees a 'trialing' message
      sees the days left in the trial
      clicking to cancel the subscription'
        sees a 'Click here' cancel button
        if we cancel during the demo
          doesn't show the 'Click here' cancel button
          should have content "Your subscription will be cancelled at the end of your demo"
  for an Agency with an Office cap
    if the Agency is paused
      the Office main user
        sees the 'contact Agency' paywall
      an Office coworker
        sees the coworker paywall
    if the Agency is lapsed on Stripe
      the Agency main user
        sees the paywall
      the Office main user
        sees the 'contact Agency' paywall
      an Office coworker
        sees the coworker paywall
    if the Agency is behind on check payments
      the Agency main user
        sees the paywall
      the Office main user
        sees the 'contact Agency' paywall
      an Office coworker
        sees the coworker paywall
    if the Agency is paid up by check
      the Agency main user
        sees the Agency dashboard
      the Office main user
        sees the Promoter dashboard
      an Office coworker
        sees the Promoter dashboard
    if the Agency is active (agency) on Stripe
      the Agency main user
        sees the Agency dashboard
      the Office main user
        sees the Promoter dashboard
      an Office coworker
        sees the Promoter dashboard
    if the Agency is active (enterprise) on Stripe
      the Agency main user
        sees the Agency dashboard
      the Office main user
        sees the Promoter dashboard
      an Office coworker
        sees the Promoter dashboard
  when subscribed at 0$
    if the Agency is a multi-office
      if the Agency is paused
        sees the 'contact Agency' paywall
      if the Agency is missing
        sees the 'contact Agency' paywall
      if the Agency master subscription is lapsed
        sees the 'contact Agency' paywall
      if the Agency is present and subscribed
        if the Agency's purchase for this Office is lapsed
          sees the 'contact Agency' paywall
        if this Office is paused
          sees the 'contact Agency' paywall
        if the Office's subscription is lapsed
          sees the 'contact Agency' paywall
        if the Office's subscription is active
          sees the Promoter dashboard
    if the Agency is a reseller
      if the Agency is paused
        sees the 'contact Agency' paywall
      if the Agency is active
        if the Office is paused
          sees the 'contact Agency' paywall
        if the Office subscription lapses
          sees the 'contact Agency' paywall
        if the Office subscription is active
          sees the Promoter dashboard

Agency
  an unsubscribed Agency
    sees the paywall
    the Agency products page
      offers Agencies
      doesn't offer conventional plans
    PRICING
      for a reseller
        the Master Plan and Subscription
          should eq 16992.0
        added Offices
          should eq 0.3
      for a multi-office
        the Master Plan and Subscription
          should eq 16992.0
        added Offices
          should eq 0.3
      with special offer 833/mo for agency_offices
        the products page
          should match /multi\-office(.*)\$833/i
          should not match /reseller\sagency(.*)\$833/i
        Product#set_price()
          should eq 10000
      with a special offer 833/mo for agency_reseller
        the products page
          should match /reseller\sagency(.*)\$833/i
        Product#set_price()
          should eq 10000
  an Agency with a lapsed Subscription
    sees the paywall
  an Agency with an active subscription
    sees the dashboard
  any Agency
    adding a new Office
      by email
        the Office
          should eq "paid"
          the invivation Email
            should eq "OneClickPolitics Invite from Social Driver"
            should have content "newcustomer@promoter.com"
            should have content "12345"
    Offices without subscriptions
      should have link "Delete"
      clicking 'Delete'
        should eq 1
    with a subscribed Office
      can cancel an Office's subscription
      when canceling an Office's subscription
        should have content "Cancel at Period End true"
        should not have link "Cancel at End"
    when a new Subscription proceeds
      creates an Office Subscription record for the Agency (PENDING: Not yet implemented)
      sets the Office usage_plan = paid (PENDING: Not yet implemented)
      creates an Office Product record for the Agency (PENDING: Not yet implemented)
      creates a Product record for the PromoterUser (PENDING: Not yet implemented)
      creates a Subscription record for the PromoterUser (PENDING: Not yet implemented)
      the Agency's Office Subscription record
        is stamped with the Office name/id (PENDING: Not yet implemented)
        is discounted (PENDING: Not yet implemented)
        resale discount at 25%? (PENDING: Not yet implemented)
      the Agency's Office Product record
        is stamped with the Office name/id (PENDING: Not yet implemented)
        is discounted (PENDING: Not yet implemented)
        resale discount at 25%? (PENDING: Not yet implemented)
      the PromoterUser's Product record
        is free (PENDING: Not yet implemented)
      the PromoterUser's Subscription record
        is free (PENDING: Not yet implemented)
    when a subscription upgrade proceeds
      it updates the records (PENDING: Not yet implemented)
  an Agency for Offices
    can edit Office logins and passwords
    offers the default discount for offices
    subscribing a new 'Enterprise' Office
      doesn't require Office agreement
      the new Product
        should eq 6299
    with a 50% office discount
      offers a 50% discount for offices
      subscribing a new 'Enterprise' Office
        doesn't require Office agreement
        the new Product
          should eq 4499
    with an Office cap
      below the cap
        adding an Office
          has form for new promoter
          creating a vaild promoter
            renders promoters dashboard
            adds promoter to agency
            sets up an active Office
            the new Office
              has a linked Subscription.master_agency_id
              has the 'enterprise' plan
              has the same billing period
            the Agency Desktop
              shows the number of Offices and cap
              doesn't show a 'Delete' button
              shows an 'Edit' button
            clicking 'Edit'
              shows the Office email
              doesn't show an 'Update' plan button
              allows editing the Office name
      at the cap
        the dashboard
          doesn't link 'Add a Sub-Account'
        submitting the 'Add Sub-Account' form
          shows the max capacity message
          doesn't create a new Office
  an Agency as Reseller
    cannot edit Office logins and passwords
    offers the default discount for resellers
    subscribing a new Office to 'Standard'
      requires Office agreement
      if the Agency logs in as the Office
        cannot agree
      when the Office agrees
        should not have content "Waiting on confirmation from promoter"
        the new Product
          should eq 629
        upgrading the subscribed Office to 'Enterprise'
          requires Office agreement
          when the Office agrees
            should not have content "Waiting on confirmation from promoter"
            the new Product
              should eq 6299
    with a 50% discount
      subscribing a new Office to 'Standard'
        requires Office agreement
        if the Agency logs in as the Office
          cannot agree
        when the Office agrees
          should not have content "Waiting on confirmation from promoter"
          the new Product
            should eq 449
          upgrading the subscribed Office to 'Enterprise'
            requires Office agreement
            when the Office agrees
              should not have content "Waiting on confirmation from promoter"
              the new Product
                should eq 4499
    with a subscribed Office
      can pause the Office
  when a sub-account contract renews
    if the agency still exists
      it renews with the agency (PENDING: Not yet implemented)
    if the agency doesn't exist
      it can renew with OCP (PENDING: Not yet implemented)

Changing Subscriptions and Plans
  updating plans
    for an Agency
      Office
        while trialing
          can downgrade the tier
          can downgrade the billing cycle
          changing the plan
            example at ./spec/features/agencies_spec.rb:1377
            remains on day six (PENDING: Not yet implemented)
            preserves the demo expiration date (PENDING: Not yet implemented)
        during an active subscription
          cannot downgrade the tier
          cannot downgrade the billing cycle
          when upgrading
            does not begin in demo mode (PENDING: Not yet implemented)
        when a subscription expires
          can downgrade the tier
          can downgrade the billing_cycle
          on resubscribing
            does not begin in demo mode (PENDING: Not yet implemented)

Alternate message specs
  AlternateMessage
    with the maximum AlternateMessages on one promoted_message_id
      a new AlternateMessage for this promoted_message_id
        is invalid
    with no content_number
      gracefully defaults to 1
    belongs_in_content?
      when passing 1
        returns true for nil, 0, or 1
        returns false for 2
      when passing 2
        returns true for 2
        returns false for nil, 0, or 1
    with obscenity
      is invalid
  Widgets
    with AlternateMessages
      multi-action
        with :editable_widgets FALSE
          selecting an alternate message
            and a valid signature
              keeps the same alternate subject and id
              supplies the alternate body text
              behaves like a widget with alternate messages
                should have css "div#alternate_373 div.alternate_subject", {:visible=>false, :text=>"Alternate Subject One Here", :session_options=>#<Capybara::ReadOnlySessionC...e_aria_label=false, @save_path=#<Pathname:/ocp/tmp/capybara>, @app_host="http://www.example.com">)>}
                should have css "div#alternate_375 div.alternate_body", {:visible=>false, :text=>"Behold the body for alternate message one!", :session_options=>#<Capybara::...e_aria_label=false, @save_path=#<Pathname:/ocp/tmp/capybara>, @app_host="http://www.example.com">)>}
                should have css "div#alternate_378 div.alternate_subject", {:visible=>false, :text=>"This is the Second Alternate Subject", :session_options=>#<Capybara::ReadOn...e_aria_label=false, @save_path=#<Pathname:/ocp/tmp/capybara>, @app_host="http://www.example.com">)>}
                should have css "div#alternate_380 div.alternate_body", {:visible=>false, :text=>"This is the body for alternate message two", :session_options=>#<Capybara::...e_aria_label=false, @save_path=#<Pathname:/ocp/tmp/capybara>, @app_host="http://www.example.com">)>}
                has javascript
              if we send
                the conversion
                  uses the alternate body
            multi-content
              and a valid signature
                doesn't put a content_two alternate in the content_one container
                keeps the same content_one alternate subject and id
                keeps the same content_two alternate subject and id
                supplies the content_one alternate body text
                supplies the content_two alternate body text
                behaves like a widget with alternate messages
                  should have css "div#alternate_395 div.alternate_subject", {:visible=>false, :text=>"Alternate Subject One Here", :session_options=>#<Capybara::ReadOnlySessionC...e_aria_label=false, @save_path=#<Pathname:/ocp/tmp/capybara>, @app_host="http://www.example.com">)>}
                  should have css "div#alternate_397 div.alternate_body", {:visible=>false, :text=>"Behold the body for alternate message one!", :session_options=>#<Capybara::...e_aria_label=false, @save_path=#<Pathname:/ocp/tmp/capybara>, @app_host="http://www.example.com">)>}
                  should have css "div#alternate_400 div.alternate_subject", {:visible=>false, :text=>"This is the Second Alternate Subject", :session_options=>#<Capybara::ReadOn...e_aria_label=false, @save_path=#<Pathname:/ocp/tmp/capybara>, @app_host="http://www.example.com">)>}
                  should have css "div#alternate_402 div.alternate_body", {:visible=>false, :text=>"This is the body for alternate message two", :session_options=>#<Capybara::...e_aria_label=false, @save_path=#<Pathname:/ocp/tmp/capybara>, @app_host="http://www.example.com">)>}
                  has javascript
                if we send
                  the conversion
                    uses the content_one alternate body
                    uses the content_two alternate body
        with :editable_widgets TRUE
          behaves like a widget with alternate messages
            should have css "div#alternate_409 div.alternate_subject", {:visible=>false, :text=>"Alternate Subject One Here", :session_options=>#<Capybara::ReadOnlySessionC...e_aria_label=false, @save_path=#<Pathname:/ocp/tmp/capybara>, @app_host="http://www.example.com">)>}
            should have css "div#alternate_411 div.alternate_body", {:visible=>false, :text=>"Behold the body for alternate message one!", :session_options=>#<Capybara::...e_aria_label=false, @save_path=#<Pathname:/ocp/tmp/capybara>, @app_host="http://www.example.com">)>}
            should have css "div#alternate_414 div.alternate_subject", {:visible=>false, :text=>"This is the Second Alternate Subject", :session_options=>#<Capybara::ReadOn...e_aria_label=false, @save_path=#<Pathname:/ocp/tmp/capybara>, @app_host="http://www.example.com">)>}
            should have css "div#alternate_416 div.alternate_body", {:visible=>false, :text=>"This is the body for alternate message two", :session_options=>#<Capybara::...e_aria_label=false, @save_path=#<Pathname:/ocp/tmp/capybara>, @app_host="http://www.example.com">)>}
            has javascript
          selecting an alternate message
            and a valid signature
              keeps the same alternate subject and id
              supplies the alternate body text
              behaves like a widget with alternate messages
                should have css "div#alternate_423 div.alternate_subject", {:visible=>false, :text=>"Alternate Subject One Here", :session_options=>#<Capybara::ReadOnlySessionC...e_aria_label=false, @save_path=#<Pathname:/ocp/tmp/capybara>, @app_host="http://www.example.com">)>}
                should have css "div#alternate_425 div.alternate_body", {:visible=>false, :text=>"Behold the body for alternate message one!", :session_options=>#<Capybara::...e_aria_label=false, @save_path=#<Pathname:/ocp/tmp/capybara>, @app_host="http://www.example.com">)>}
                should have css "div#alternate_428 div.alternate_subject", {:visible=>false, :text=>"This is the Second Alternate Subject", :session_options=>#<Capybara::ReadOn...e_aria_label=false, @save_path=#<Pathname:/ocp/tmp/capybara>, @app_host="http://www.example.com">)>}
                should have css "div#alternate_430 div.alternate_body", {:visible=>false, :text=>"This is the body for alternate message two", :session_options=>#<Capybara::...e_aria_label=false, @save_path=#<Pathname:/ocp/tmp/capybara>, @app_host="http://www.example.com">)>}
                has javascript
              if we edit the alternate body text
                validly
                  and send
                    the conversion
                      uses the edited body
                invalidly
                  and send
                    shows a validation error
                    if we fix it
                      uses the edited body
              if we send
                the conversion
                  uses the alternate subject
                  uses the alternate body
            an an invalid signature
              keeps the same subject and id
              behaves like a widget with alternate messages
                should have css "div#alternate_445 div.alternate_subject", {:visible=>false, :text=>"Alternate Subject One Here", :session_options=>#<Capybara::ReadOnlySessionC...e_aria_label=false, @save_path=#<Pathname:/ocp/tmp/capybara>, @app_host="http://www.example.com">)>}
                should have css "div#alternate_447 div.alternate_body", {:visible=>false, :text=>"Behold the body for alternate message one!", :session_options=>#<Capybara::...e_aria_label=false, @save_path=#<Pathname:/ocp/tmp/capybara>, @app_host="http://www.example.com">)>}
                should have css "div#alternate_450 div.alternate_subject", {:visible=>false, :text=>"This is the Second Alternate Subject", :session_options=>#<Capybara::ReadOn...e_aria_label=false, @save_path=#<Pathname:/ocp/tmp/capybara>, @app_host="http://www.example.com">)>}
                should have css "div#alternate_452 div.alternate_body", {:visible=>false, :text=>"This is the body for alternate message two", :session_options=>#<Capybara::...e_aria_label=false, @save_path=#<Pathname:/ocp/tmp/capybara>, @app_host="http://www.example.com">)>}
                has javascript
      fluid
        should have css "div#alternate_455 div.alternate_subject", {:visible=>false, :text=>"Alternate Subject One Here", :session_options=>#<Capybara::ReadOnlySessionC...e_aria_label=false, @save_path=#<Pathname:/ocp/tmp/capybara>, @app_host="http://www.example.com">)>}
        should have css "div#alternate_457 div.alternate_body", {:visible=>false, :text=>"Behold the body for alternate message one!", :session_options=>#<Capybara::...e_aria_label=false, @save_path=#<Pathname:/ocp/tmp/capybara>, @app_host="http://www.example.com">)>}
        should have css "div#alternate_460 div.alternate_subject", {:visible=>false, :text=>"This is the Second Alternate Subject", :session_options=>#<Capybara::ReadOn...e_aria_label=false, @save_path=#<Pathname:/ocp/tmp/capybara>, @app_host="http://www.example.com">)>}
        should have css "div#alternate_462 div.alternate_body", {:visible=>false, :text=>"This is the body for alternate message two", :session_options=>#<Capybara::...e_aria_label=false, @save_path=#<Pathname:/ocp/tmp/capybara>, @app_host="http://www.example.com">)>}
        selecting an alternate message
          and a valid signature
            the conversion
              uses the alternate subject (FAILED - 10)
          an an invalid signature
            keeps the same subject and id (FAILED - 11)
            behaves like a widget with alternate messages
              example at ./spec/features/alternate_message_spec.rb:96 (FAILED - 12)
              example at ./spec/features/alternate_message_spec.rb:97 (FAILED - 13)
              example at ./spec/features/alternate_message_spec.rb:98 (FAILED - 14)
              example at ./spec/features/alternate_message_spec.rb:99 (FAILED - 15)
              has javascript (FAILED - 16)
  Deliveries
    Add to the end-to-end message spec? (PENDING: Not yet implemented)
    with an alternate subject and body
      the delivered email
        has the alternate subject
  Editing Messages
    with proxy logged in
      renders the alternate_messages index and shows fields for AlternateMessage
    with main promoter logged in
      has fields for a new AlternateMessage
      has fields for a content_two AlternateMessage
      multi-content
        has two sets of fields for new multi-content AlternateMessages
      with an obscene message
        clicking 'Add'
          doesn't create an alternate
          shows validation errors
      with valid Alternate info
        clicking 'Add'
          creates an alternate
          touches the PromotedMessage
        multi-content
          clicking the content_one 'Add'
            behaves like an alt message creator
              creates an alternate with correct content_number
          clicking the content_two 'Add'
            behaves like an alt message creator
              creates an alternate with correct content_number
      with an Alternate
        shows an Edit button
        shows a Delete button
        entering an invalid edit
          clicking 'Update'
            shows a validation error
            doesn't save
        entering a valid edit
          clicking 'Update'
            saves
            touches the message
            multi-content
              saves with the same content_number
        clicking Delete
          removes the Alternate
          touches the PromotedMessage

Australia page
  australia recipients page
    nav bar
      should have content "Parliament"
    house members
      should have content "House of Representatives"
      lists AU house members
      lists party abbreviation
    senate members
      should have content "Senate"
      lists AU senate members
      lists party abbreviation
    state selection
      with unlimited state access
        should have link "New South Wales"
        should have link "Tasmania"
        should have link "Victoria"
      with single state access
        should not have link "Tasmania"
        should not have link "Victoria"
        should have link "New South Wales"

PromoterUser
  avatar
    has link to avatar
    edit page shows the default image when promoter has no image
    changes the promoter avatar
    profile page shows the default image when promoter has no image
    when the promoter has an avatar image
      appears on the profile

Campaign Monitor API
  Service Calls
    create_client_and_person
      without a Promoter email
        is invalid
      if the API calls are successful
        the internal API message
          has status :success
          includes the new ClientID
          includes the new email
        the Promoter
          records the Campaign Monitor client id
      if create_client fails
        has status failed
        should not run create_person
        doesn't include the new ClientID
        shows an error message for create_client
        the Promoter
          doesn't record the Campaign Monitor client id
    buy_credits
      calling
        records a Transaction record with the same uuid
        checks OCP Credits
      if the check_credits call fails
        has status :failed
        doesn't call transfer_credits
        doesn't charge on Stripe
      if OCP has sufficient Credits
        transfers Credits to the Client (PENDING: Not yet implemented)
        if the Credits transfer
          if the Stripe Charge succeeds
            has status :success
            doesn't deduct credits back to OCP
            the Transaction record
              has status :success
            the Promoter
              records the credits
            the credit cache
              records the credits
          if the Stripe Charge fails
            has status :failed
            shows the failed Stripe call, id, and result
            deducts the transferred credits back to OCP
            the Transaction record
              has status :failed
          if the charge is 0 for free credits
            has status :success
            records 'free credits' instead of Stripe charge
            doesn't deduct credits back to OCP
            the Transaction record
              has status :success
            the Promoter
              records the credits
        if the Credits fail to transfer
          has status :failed
          doesn't charge the customer on Stripe
      if OCP has insufficient Credits
        has status :failed
        doesn't call transfer_credits
        doesn't charge the customer on Stripe
    find_or_create_person
      without a Promoter email
        is invalid
      without a Promoter campaign_monitor_client_id
        is invalid
      if get_people is successful
        if the person already exists
          has status success
          should not call create_person
        if the person doesn't exist
          if create_person succeeds
            has status success
            should call create_person
            should show the new email in the results
          if create_person fails
            has status failed
            shows an error message for create_person
      if get_people fails
        has status failed
        should not call create_person
        shows an error message for get_people
    create_external_session
      without a Promoter email
        is invalid
      without a Promoter campaign_monitor_client_id
        is invalid
      if get_people is successful
        if the person already exists
          if create_external_session succeeds
            has status success
            should not call create_person
          if create_external_session fails
            has status failed
            shows the result of the failed create_external_session call
            should not call create_person
        if the person doesn't exist
          if create_person succeeds
            if create_external_session succeeds
              has status success
              should call create_person
            if create_external_session fails
              has status failed
              shows the result of the failed create_external_session call
              should call create_person
          if create_person fails
            has status failed
            shows an error message for create_person
            should not call create_external_session
      if get_people fails
        has status failed
        should not call create_person
        should not call create_external_session
        shows an error message for get_people
    list_or_create_custom_fields
      without a list_id
        is invalid
      if list_custom_fields is successful
        if the custom fields already exist
          has status success
          should not call create_custom_field
        if the custom fields do not exist
          if create_custom_field succeeds
            has status success
            should call create_custom_field
          if create_custom_field fails
            has status failed
            shows an error message for create_custom_field
      if list_custom_fields fails
        has status failed
        should not call create_custom_field
        shows an error message for list_custom_fields
    import_subscribers
      without a client_id
        is invalid
      without data
        is invalid
      the wrapped JSON data
        is valid JSON
      with all parameters
        is valid
      if find_or_create_list succeeds
        if 'Save the whales' is listed
          if list_or_create_custom_fields succeeds
            if custom fields already exist
              if import_subscribers succeeds
                has status success
                calls list_lists
                doesn't call create_lists
                doesn't call create_custom_field
                records a Transaction record with the same uuid
              if import_subscribers fails
                has status failed
                calls list_lists
                doesn't call create_lists
                doesn't call create_custom_field
                records a Transaction record with the same uuid
            if custom fields are missing
              calls create_custom_field
              if create_custom_field succeeds
                if import_subscribers succeeds
                  has status success
                if import_subscribers fails
                  has status failed
              if create_custom_field fails
                has status failed
          if list_custom_fields fails
            has status failed
            doesn't call create_custom_field
            doesn't call import_subscribers
        if 'Save the whales' is not listed
          calls create_list
          if create_list succeeds
            if list_or_create_custom_fields succeeds
              if import_subscribers succeeds
                has status success
                records a Transaction record with the same uuid
              if import_subscribers fails
                has status failed
          if create_list fails
            has status failed
            doesn't call list_custom_fields
            doesn't call create_custom_field
            doesn't call import_subscribers
      if list_lists fails
        has status failed
        doesn't call list_custom_fields
        doesn't call import_subscribers
    sync_subscribers
      without a client_id
        is invalid
      without a quantity
        is invalid
      with quantity and client_id
        is valid
      data blocks
        excessive signatures on one message
          has two blocks
          behaves like block data
            a block's .data
              is valid JSON
              is an array
              wrapped in Subscribers JSON
                is valid JSON
          behaves like block data
            a block's .data
              is valid JSON
              is an array
              wrapped in Subscribers JSON
                is valid JSON
        signatures on two messages
          has two blocks
          behaves like block data
            a block's .data
              is valid JSON
              is an array
              wrapped in Subscribers JSON
                is valid JSON
          behaves like block data
            a block's .data
              is valid JSON
              is an array
              wrapped in Subscribers JSON
                is valid JSON
        signatures on one message
          has one block
          behaves like block data
            a block's .data
              is valid JSON
              is an array
              wrapped in Subscribers JSON
                is valid JSON
        alternating signatures
          has 3 blocks
          behaves like block data
            a block's .data
              is valid JSON
              is an array
              wrapped in Subscribers JSON
                is valid JSON
          behaves like block data
            a block's .data
              is valid JSON
              is an array
              wrapped in Subscribers JSON
                is valid JSON
      if list_lists is missing a subject
        if create_list fails
          doesn't sync the blocks
          has status failed
        if create_list succeeds
          syncs the blocks
          has status success
      if the custom fields are uncreated
        creates them
        has status success
      with mixed blocks
        shows the total synced from all blocks
        has status success
        records the quantity synced
        the block calls
          shows status success
  API MQ Message
    goes to the API queue (PENDING: Not yet implemented)
    has a Resource name (e.g. Campaign) (PENDING: Not yet implemented)
    has a promoter_user_id (PENDING: Not yet implemented)
    has a CM ClientId (PENDING: Not yet implemented)
    a Campaign message
      includes promoter_user_id (PENDING: Not yet implemented)
      includes campaign monitor clientid (PENDING: Not yet implemented)
      includes campaign monitor campaignid (PENDING: Not yet implemented)
      includes campaign monitor list_id or segment_id (PENDING: Not yet implemented)
      includes campaign monitor lists_and_segments_serialized (PENDING: Not yet implemented)
      includes number of recipients (PENDING: Not yet implemented)
      includes scheduled delivery datetime (PENDING: Not yet implemented)
      includes status (PENDING: Not yet implemented)
  Campaign Monitor API Agent
    watches the api_queue (PENDING: Not yet implemented)
    reads API MqMessages (PENDING: Not yet implemented)
    processes calls to Campaign Monitor asynchronously (PENDING: Not yet implemented)
    processes 'Check Client' messages (PENDING: Not yet implemented)
    processes 'Create Client' messages (PENDING: Not yet implemented)
    processes 'Check OCP Credits' messages (PENDING: Not yet implemented)
    processes 'Buy Credits' messages (PENDING: Not yet implemented)
    processes 'Login/Start Client Session' messages (PENDING: Not yet implemented)
    processes 'Sync Listings' messages (PENDING: Not yet implemented)
    for any message
      checks the last :in_progress Transaction status (PENDING: Not yet implemented)
    if it gets a Buy Credits message
      checks the Transaction uuid stamp (PENDING: Not yet implemented)
      checks the Transaction status (PENDING: Not yet implemented)
      if the status is :ongoing
        if the uuid stamp doesn't match the message
          ignores the message (PENDING: Not yet implemented)
        if the uuid stamp matches the message
          proceeds (PENDING: Not yet implemented)
      if the status is :failed
        proceeds (PENDING: Not yet implemented)
  Campaign Monitor 1.0
    PromoterUser
      can_buy_email_credits?
        for Stripe status :active
          should equal true
        for Stripe status :trialing
          should equal false
        for an Office
          should equal false
        for an Agency
          should equal false
        for a Proxy
          should equal false
        for a Starter/Solo plan
          should equal false
    Asynchronous transactions
      for any creative/destructive action
        searches for an in_progress record of the same action and promoter (PENDING: Not yet implemented)
        if we're within the wait_threshold for this action
          does not start a new one (PENDING: Not yet implemented)
          returns a link to the transaction (PENDING: Not yet implemented)
      for a non-destructive/creative inquiry into a value
        hits a rails cache (PENDING: Not yet implemented)
        searches for an in_progress record of the same action and promoter (PENDING: Not yet implemented)
        if a transaction is already in_progress
          if we're within the wait_threshold for this action
            does not start a new one (PENDING: Not yet implemented)
            returns a link to the transaction (PENDING: Not yet implemented)
          if we're outside the wait_threshold for this action
            starts a new one (PENDING: Not yet implemented)
            returns a link to the transaction (PENDING: Not yet implemented)
      Callbacks
        for non-destructive/creative inquiries
          updates cached values (PENDING: Not yet implemented)
    Transaction
      gets a simple displayed value (PENDING: Not yet implemented)
      gets a callback, either to a js redirect, or a screen element div to update
      for a count
        is a simple text displayed value (PENDING: Not yet implemented)
      for a session
        is a link (PENDING: Not yet implemented)
      for a redirect callback
        needs to substitute in its uuid (PENDING: Not yet implemented)
      for a screen element div
        needs to substitute in its uuid (PENDING: Not yet implemented)
    Admin Controls
      when synchronous
        on a Promoter's Credits page
          if the Promoter already has a client_id
            shows a Transfer Credits form
            the check_ocp_credits transaction
              should have status success
              the asynchronous tag
                shows OCP's credits
            the show_client transaction
              should have status success
              the asynchronous tag
                shows OCP's credits
            with cached credit counts
              the check_ocp_credits transaction
                should have status success
                the asynchronous tag
                  shows OCP's credits
              the show_client transaction
                should have status success
                the asynchronous tag
                  shows OCP's credits
            transferring credits
              with no amount given
                the error div
                  should have content "amount is required"
                the transaction div
                  should have status 'invalid'
                  the asynchronous tag
                    shows OCP's credits
              with valid parameters
                but failing 'transfer_credits'
                  the transaction div
                    should have status 'failed'
                    should not use the success value
                  the transaction error field
                    should show the error message
              with valid parameters
                updates the cached credit counts
                the saved Transaction
                  is rendered
                  is rendered
                the saved Transaction
                  does not record a charge to Stripe
          if the Promoter has no client_id
            redirects
            when we advance
              the create_client_and_person transaction
                should have status success
                the asynchronous tag
                  shows the ClientId
              if we then visit the Credits page
                the show_client transaction
                  should have status success
                  the asynchronous tag
                    shows the client's credits
      when asynchronous
        on a Promoter's Credits page
          if the Promoter already has a client_id
            the transaction divs
              check_ocp_credits
                behaves like a transaction div
                  the div
                    should have status 'in_progress'
                    should have the uuid for an InternalApiMessage
                    should start the check-status timer (globalRunningTransactions)
                    should have a check-status path
                    if we visit the check-path
                      returns JSON
                      shows the transaction status
              show_client
                behaves like a transaction div
                  the div
                    should have status 'in_progress'
                    should have the uuid for an InternalApiMessage
                    should start the check-status timer (globalRunningTransactions)
                    should have a check-status path
                    if we visit the check-path
                      returns JSON
                      shows the transaction status
            the API queue
              has an ApiAgentMessage for 'check_ocp_credits'
              has an ApiAgentMessage for 'show_client'
          if credit values are cached
            the API queue
              is empty
            either InternalApiMessage
              has status 'success'
          if the Promoter has no client_id
            redirects to new_client
            Creating
              makes an ApiAgentMessage
              the create_client_and_person transaction div
                behaves like a transaction div
                  the div
                    should have status 'in_progress'
                    should have the uuid for an InternalApiMessage
                    should start the check-status timer (globalRunningTransactions)
                    should have a check-status path
                    if we visit the check-path
                      returns JSON
                      shows the transaction status
              if the ApiAgent succeeds
                sets the Promoter's client_id
                visiting the check-path
                  the returned JSON
                    should not raise Exception
                    shows status 'success'
                    shows the client_id
              if the ApiAgent fails
                visiting the check-path
                  the returned JSON
                    should not raise Exception
                    shows status 'failed'
                    shows the failure message
    Promoter Controls
      new Client page
        without a client_id
          does not ask for an email
          shows a Connect button
          the transaction
            is create_client_and_person
          if we click 'Connect'
            if the create_client_and_person call fails
              shows an error message
              doesn't redirect to Campaigns
            if the create_client_and_person call succeeds
              redirects to Campaigns
        with a client_id
          without an email
            asks for a contact email
            shows a Connect button
            the transaction
              is find_or_create_person
            if we pass an invalid email
              should have content "Please enter a valid email address"
              the transaction
                is find_or_create_person
                is not delegated or run
            if we pass a valid email
              updates the promoter
              redirects us to the Campaigns page
      Campaigns page
        with email_blast_access set to false
          redirects to the messages dashboard
        with a client_id
          without an email or contact_email
            redirects to the new Client page
        without a client_id
          redirects to the new Client page
        when synchronous
          if the create_new_session call succeeds
            shows the iframe
          if the create_new_session call fails
            shows an error message
            doesn't direct the iframe
        the Purchase Credits modal/form
          with 250 credits
            shows the customer's credits
          if the customer is an Office
            doesn't show the 'Purchase' button
            refers them to OCP
          if the customer is an Agency
            doesn't show the 'Purchase' button
            refers them to OCP
          with an :active Stripe Subscription
            shows the 'Purchase' button
          with an :trialing Stripe Subscription
            doesn't show the 'Purchase' button
            refers them to OCP
          per-tier discounts
            Enterprise
              gets an Enterprise discount on Credits
            Pro
              gets a Pro discount on Credits
          if there's an ongoing API transaction for this customer
            doesn't show the purchase button (PENDING: Not yet implemented)
          when a Customer buys CM Credits
            when synchronous
              OCP
                if OCP has insufficient Credits
                  displays an error message
                if OCP has enough Credits to transfer
                  if the transfer fails
                    displays an error message
                    doesn't charge the Client
                  if the transfer succeeds
                    if the Charge succeeds
                      updates the credits count
                      the Transaction
                        is successful
                        has quantity 10
                        costs 20
                        the Stripe charge
                          shows status success
                          records the amount and stripe customer_id
                    if the Stripe charge fails
                      shows an error message
                      the credit transfer
                        sends Credits back to OCP
                      the Transaction
                        fails
                        has quantity 50
                        costs 100
                        the Stripe charge
                          shows status failed
                          records the rejected customer_id
            when asynchronous
              if there's an ongoing API transaction for this customer
                doesn't re-order (PENDING: Not yet implemented)
        the Sync modal form
          demoing
            adverts to the 50 sig limit
            syncing
              records our sync with the demo_flg
              syncing again
                doesn't resync listings
              switching to paid
                syncing again
                  has subscribers
                  records our sync without the demo_flg
          syncing
            with mixed blocks
              totals imports and updates
          if a sync is ongoing
            and we revisit the modal
              adverts to the ongoing sync
  sig imports
    a CMSignatureBlock
      has a json array (PENDING: Not yet implemented)
      uses a track :array to collect the string (PENDING: Not yet implemented)
      includes a counter that stops before 1k (PENDING: Not yet implemented)
      has a single message / topic (PENDING: Not yet implemented)
      has the Transaction uuid (PENDING: Not yet implemented)
      the array
        has less than 1k sigs (PENDING: Not yet implemented)
    with multiple sigs for different messages
      adds a custom field with the oneSig
      blocks sigs by message
      splits down blocks to blocksize
      each block
        is valid json
  Campaign Monitor 1.1
    shows a new Email Campaign form (PENDING: Not yet implemented)
    Campaign Monitor API Agent
      processes 'Create/Send Campaign' messages (PENDING: Not yet implemented)
      processes Pull listings messages for text messages (PENDING: Not yet implemented)
    if the customer is an Office
      doesn't show the purchase credits form (PENDING: Not yet implemented)
      recommends they contact their Agency (PENDING: Not yet implemented)
    if the customer is an Agency
      shows the purchase credits form (PENDING: Not yet implemented)
      stores Agency Credits in a pool (PENDING: Not yet implemented)
      allows assigning Credits from pool to Offices (PENDING: Not yet implemented)
      allows removing Credits from Offices to pool (PENDING: Not yet implemented)
    when a Customer purchases Pro tier
      when the Stripe charge processes
        gives them free CM Credits for Pro tier (PENDING: Not yet implemented)
    when a Customer purchases Enterprise tier
      when the Stripe charge processes
        gives them free CM Credits for Enterprise tier (PENDING: Not yet implemented)
    the new Email Campaign form
      takes a Campaign name (PENDING: Not yet implemented)
      takes a Campaign from email (PENDING: Not yet implemented)
      takes a Campaign subject (PENDING: Not yet implemented)
      takes a Campaign body (PENDING: Not yet implemented)
      takes a scheduled delivery datetime (PENDING: Not yet implemented)
      takes a recipients CSV (PENDING: Not yet implemented)
      if the CSV format isn't valid
        shows an error message (PENDING: Not yet implemented)
        doesn't record the Campaign (PENDING: Not yet implemented)
        doesn't deliver the Campaign to CampaignMonitor (PENDING: Not yet implemented)
      if the recipients count exceeds our Credits
        shows an error message (PENDING: Not yet implemented)
        doesn't record the Campaign (PENDING: Not yet implemented)
        doesn't deliver the Campaign to CampaignMonitor (PENDING: Not yet implemented)
      if the CSV is valid and we have sufficient Credits
        records the Campaign (PENDING: Not yet implemented)
        delivers the Campaign to CampaignMonitor (PENDING: Not yet implemented)
        refreshes our Credit count (PENDING: Not yet implemented)
  Email Campaigns Page
    with a finished Email Campaign
      shows the Campaign totals (PENDING: Not yet implemented)
    with a it Email Campaign
      shows the Campaign delivery date (PENDING: Not yet implemented)
  Agent
    if it gets a new Campaign message
      delivers the Campaign to Campaign Monitor (PENDING: Not yet implemented)
      if the Campaign has > 1000 recipients
        breaks the transfer into 1000-record chunks for processing (PENDING: Not yet implemented)
      on 200/201/204 HTTP Success
        updates the Campaign record (PENDING: Not yet implemented)
      on HTTP Failure
        updates the Campaign record (PENDING: Not yet implemented)

Canadian Recipients
  edit recipients
    should have content "Parliament"
    should have content "House of Commons"
    house members
      lists CA house members
      lists party abbreviation
    senate members
      lists CA senate members
      lists party abbreviation
    state selection
      with unlimited state access
        should have_content('Quebec')
        should have_content('Ontario')
      with single state access
        should not have_content('Ontario')
        should have_content('Quebec')

admins
  promoter#edit
    if we have no Subscription
      and an Offer
        shows no Check payments
        allows us to make a Check payment
        Check Payments
          offers a date at the end of the Offer's Subscription period
          if we create a first Check payment
            activates the Subscription
            the Subscription
              is checks_active_to a year from now
            the SaleOffer
              expires
            the Page
              shows a new Check
              shows a Delete link
              clicking 'Delete'
                removes the Check
                touches Subscription and resets checks_active_to
      and no Offers
        Check Payments
          doesn't allow creating a new Check
    if we have a Subscription
      Check Payments
        offers a date at the end of the Subscription period

Check Activation
  a Promoter
    behaves like activation via check payment
      with a Check payment
        within 11 days of expiration
          doesn't show a warning
          doesn't show a check paywall
        within 10 days of expiration
          shows a warning
          shows the payment date (PENDING: Not yet implemented)
          shows the amount due (PENDING: Not yet implemented)
          doesn't show a check paywall
        with a lapsed Check payment
          doesn't show a warning
          shows a paywall
  an Alias / Proxy
    behaves like activation via check payment
      with a Check payment
        within 11 days of expiration
          doesn't show a warning
          doesn't show a check paywall
        within 10 days of expiration
          shows a warning
          shows the payment date (PENDING: Not yet implemented)
          shows the amount due (PENDING: Not yet implemented)
          doesn't show a check paywall
        with a lapsed Check payment
          doesn't show a warning
          shows a paywall

Our Contact Us form
  with Salesforce Contact Us Settings
    has return URL oneclickpolitics.com
  with standard Contact Us settings
    when we fill out the form and click send
      should not be tailored to the modal
      the email sent
        should not be nil
        should have content "First"
        should have content "Last"
        should have content "2154368031"
        should have content "Email: sveta@oneclickpolitics.com"
        should have content "My Organization"
        should have content "I'm a promoter and this is my message"
    when we visit via the modal
      it should be tailored to the modal (PENDING: Not yet implemented)
      when we submit a valid email and message
        should be tailored to the modal
        should show us a success message
        should close the modal, or respond accordingly
      when we submit an invalid email
        should show us an error message
        should ask us for a valid email address
        should not close the modal
    the honeypot field
      should be hidden in css
      when we fill it in
        should appear to have sent
        should not actually send
    when we don't enter our captcha
      and we fill in the form
        should not send an email
        should show us a failure message
        should show us the failed captcha message
      and we first visit the form
        should not show us a failure message
        should not show us the failed captcha message
        should not ask us for a valid email address

ProxyPromoterUser
  the reset password page
    if we enter a Proxy email
      doesn't reset the password
      doesn't send a reset email (PENDING: Not yet implemented)
      shows a message explaining that proxies are not allowed to purchase (PENDING: Not yet implemented)
  promoter/login
    if we enter the Proxy's credentials
      signs in as the Proxy
      does not sign in as the master PromoterUser
      the url
        should include "27169"
        should not include "27172"
      visiting the proxy ID url
        the redirection
          should include "27173"
          should not include "27176"
  the dashboard
    for an unsubscribed PromoterUser
      the Paywall
        should include "/promoter/27177/products"
        should have content "Choose any plan"
        should have link "Choose"
    for an unsubscribed Promoter's Proxy
      the Paywall
        should include "/promoter/27183/products_available"
        should have content "please contact your office's master account holder"
        should not have link "Choose"
    for a subscribed Promoter
      the nag payment link
        should have content "No Subscription"
        should have link "Click here"
    for a subscribed Promoter's Proxy
      the nag payment link
        should have content "No Subscription"
        should not have link "Click here"
      subscriptions routes
        should include "/promoter/27197/master_only"
      cancel trial routes
        should include "/promoter/27199/master_only"
      visiting routes with Proxy ID
        should include "/promoter/27201"
      creating New Message sets the master promoter as the message's owner:
        should eq #<PromoterUser id: 27203, name: "Greenpeace", created_at: "2022-06-07 21:32:08", updated_at: "2022-06...e, video_messaging_flg: false, failed_login_count: 0, adult_keyword: false, max_keywords_allowed: 3>
    for a 'pro' Promoter's Proxy
      doesn't allow purchases / new plan upgrades (PENDING: Not yet implemented)
      Edit Account
        should not have link "Cancel Subscription"
        clicking 'Change Logo'
          should have content "Edit Logo"
          Submitting an Avatar
            updates the PromoterUser, not the Proxy
      with a message and conversions
        should have css "a#edit_message_link_23710", {:visible=>false, :session_options=>#<Capybara::SessionConfig:0x00000007a830c0 @server_host=nil, @alw...ble_aria_label=false, @save_path=#<Pathname:/ocp/tmp/capybara>, @app_host="http://www.example.com">}
        clicking 'Active'
          should have css "a#edit_message_link_23711", {:visible=>false, :session_options=>#<Capybara::SessionConfig:0x00000007a830c0 @server_host=nil, @alw...ble_aria_label=false, @save_path=#<Pathname:/ocp/tmp/capybara>, @app_host="http://www.example.com">}
        when we edit a message
          the message
            should eq "Edited Body"
            should eq #<PromoterUser id: 27217, name: "Greenpeace", created_at: "2022-06-07 21:32:25", updated_at: "2022-06...e, video_messaging_flg: false, failed_login_count: 0, adult_keyword: false, max_keywords_allowed: 3>
        visiting the reporting pages
          shows the new CSVs link
          clicking the link
            should not have content "please contact your office's master account holder"

Proxies Page
  a logged-out Promoter
    must login
  a logged-in Proxy Promoter
    gets redirected
    doesn't see a creation form
  a non-enterprise Promoter
    should not have css "form"
  an enterprise Promoter
    sees a creation form
    adding a new email and valid credentials
      should not equal nil
      should eq 27233
      shows an update form for the new proxy
    adding the email of an existing PromoterUser
      should have content "This email has already been taken"
    adding an invalid password
      should have content "is too short"
    if they own a Proxy
      shows an update form
      changing the password to a valid combination
        should have content "Updated"
      changing the password to an invalid combination
        should not have content "Updated"
        should have content "is too short"
      clicking 'delete'
        should not have css "div#proxy_form27249"
        should equal 0
    if they don't own a Proxy
      doesn't appear
    with maximum proxies
      adding a new proxy
        should have content "co-workers allowed for each office"
        should equal 25

CustomField
  if a promoter has the maximum already
    creating another
      should be invalid
    the existing CustomFields
      should be valid

PromotedMessage
  #update_custom_fields()
    takes a hash of options (PENDING: Not yet implemented)
    doesn't create an openstruct directly (PENDING: Not yet implemented)
    validates lengths before creating openstruct? (PENDING: Not yet implemented)
  validations
    with an overlong select options field
      is invalid
    with invalid JSON in the custom field
      is invalid

SenderProfile
  validations
    with an overlong custom value
      is invalid
    with invalid JSON in the custom value
      is invalid
    if a custom value is required?
      is invalid
    if a custom field is not required?
      should be valid
  #merge_custom_values
    with existing Gender and Town
      should include {"id" => 6, "name" => "gender", "value" => "F"}
      should include {"id" => 7, "name" => "town", "value" => "Thule", "required" => true}
      merging new Town (by ID)
        should include {"id" => 6, "name" => "gender", "value" => "F"}
        should not include {"id" => 7, "name" => "town", "value" => "Thule", "required" => true}
        should include {"id" => 7, "name" => "town", "value" => "Ys", "required" => true}
      merging new Town (by name)
        should include {"id" => 6, "name" => "gender", "value" => "F"}
        should not include {"id" => 443, "name" => "town", "value" => "Thule", "required" => true}
        should include {"name" => "town", "value" => "Ys", "required" => true, "id" => "444"}
      when the message doesn't support custom field 'Party'
        merging new 'Party' (by ID)
          should include {"id" => 6, "name" => "gender", "value" => "F"}
          should include {"id" => 7, "name" => "town", "value" => "Thule", "required" => true}
          should not include {"id" => "100", "name" => "party", "value" => "independent"}
        merging new 'Party' (by name)
          should include {"id" => 6, "name" => "gender", "value" => "F"}
          should include {"id" => 7, "name" => "town", "value" => "Thule", "required" => true}
          should not include {"name" => "party", "value" => "independent"}
      when the promoter doesn't support custom field 'Party'
        merging new 'Party' (by name)
          should include {"id" => 6, "name" => "gender", "value" => "F"}
          should include {"id" => 7, "name" => "town", "value" => "Thule", "required" => true}
          should not include {"name" => "party", "value" => "independent", "id" => nil}
  #create_with_custom_values
    for a message with Town and Gender
      with town and 'Party' (by ID)
        should include {"id" => "6", "name" => "town", "value" => "Thule", "required" => true}
        should not include {"id" => "100", "name" => "party", "value" => "independent"}
      with 'town' and Party' (by Name)
        should include {"name" => "town", "value" => "Thule", "required" => true, "id" => "448"}
        should not include {"id" => "100", "name" => "party", "value" => "independent"}

Widgets
  Fluid widget
    behaves like a widget with custom fields
      with custom Town
        with select values 'Thule','Ys'
          should have select "custom_field_450", {:options=>["Town", "Thule", "Ys"], :session_options=>#<Capybara::ReadOnlySessionConfig(#<Capybara::S...e_aria_label=false, @save_path=#<Pathname:/ocp/tmp/capybara>, @app_host="http://www.example.com">)>}
          if not required
            doesn't include javascript validation (PENDING: Not yet implemented)
            should not eq "required"
            signing without 'Town'
              succeeds
              should eq nil
          if required
            includes javascript validation (PENDING: Not yet implemented)
            should eq "required"
            signing without 'Town'
              requires Validation
              doesn't succeed
              adding 'Town'
                succeeds
        without select values
          should have field "custom_field_458"
          should not have select "custom_field_459"
          if not required?
            doesn't include javascript validation (PENDING: Not yet implemented)
            should not eq "required"
            signing without 'Town'
              succeeds
            signing with 'Town' over max character limit
              requires Validation
              doesn't succeed
              adding 'Town'
                succeeds
                should eq nil
          if required?
            includes javascript validation (PENDING: Not yet implemented)
            should eq "required"
            signing without 'Town'
              requires Validation
              doesn't succeed
              adding 'Town'
                succeeds
            signing with 'Town' over max character limit
              requires Validation
              doesn't succeed
              adding 'Town'
                succeeds
      ordered custom fields
        with ordering [{'Town'},{Gender},{Salutation}]
          should match /custom_field_473.*custom_field_474.*custom_field_475/
        with ordering [{'Gender'},{Salutation},{Town}]
          should match /custom_field_477.*custom_field_478.*custom_field_476/
      with an existing Profile with Gender 'F' and Town 'Thule'
        signing with Salutation 'Ms'
          should eq 1
          should eq "Ms"
          should eq "Thule"
        signing with Town 'Ys'
          should eq 1
          should eq "Ys"
          should eq "F"
  Mobile widget
    behaves like a widget with custom fields
      with custom Town
        with select values 'Thule','Ys'
          should have select "custom_field_497", {:options=>["Town", "Thule", "Ys"], :session_options=>#<Capybara::ReadOnlySessionConfig(#<Capybara::S...e_aria_label=false, @save_path=#<Pathname:/ocp/tmp/capybara>, @app_host="http://www.example.com">)>}
          if not required
            doesn't include javascript validation (PENDING: Not yet implemented)
            should not eq "required"
            signing without 'Town'
              succeeds (FAILED - 17)
              example at ./spec/features/custom_fields_spec.rb:330 (FAILED - 18)
          if required
            includes javascript validation (PENDING: Not yet implemented)
            should eq "required"
            signing without 'Town'
              requires Validation (FAILED - 19)
              doesn't succeed (FAILED - 20)
              adding 'Town'
                succeeds (FAILED - 21)
        without select values
          should have field "custom_field_505"
          should not have select "custom_field_506"
          if not required?
            doesn't include javascript validation (PENDING: Not yet implemented)
            should not eq "required"
            signing without 'Town'
              succeeds (FAILED - 22)
            signing with 'Town' over max character limit
              requires Validation (FAILED - 23)
              doesn't succeed (FAILED - 24)
              adding 'Town'
                succeeds (FAILED - 25)
                example at ./spec/features/custom_fields_spec.rb:442 (FAILED - 26)
          if required?
            includes javascript validation (PENDING: Not yet implemented)
            should eq "required"
            signing without 'Town'
              requires Validation (FAILED - 27)
              doesn't succeed (FAILED - 28)
              adding 'Town'
                succeeds (FAILED - 29)
            signing with 'Town' over max character limit
              requires Validation (FAILED - 30)
              doesn't succeed (FAILED - 31)
              adding 'Town'
                succeeds (FAILED - 32)
      ordered custom fields
        with ordering [{'Town'},{Gender},{Salutation}]
          should match /custom_field_520.*custom_field_521.*custom_field_522/
        with ordering [{'Gender'},{Salutation},{Town}]
          should match /custom_field_524.*custom_field_525.*custom_field_523/
      with an existing Profile with Gender 'F' and Town 'Thule'
        signing with Salutation 'Ms'
          example at ./spec/features/custom_fields_spec.rb:590 (FAILED - 33)
          example at ./spec/features/custom_fields_spec.rb:592 (FAILED - 34)
          example at ./spec/features/custom_fields_spec.rb:594 (FAILED - 35)
        signing with Town 'Ys'
          example at ./spec/features/custom_fields_spec.rb:608 (FAILED - 36)
          example at ./spec/features/custom_fields_spec.rb:610 (FAILED - 37)
          example at ./spec/features/custom_fields_spec.rb:611 (FAILED - 38)

promoter/edit
  on a pro or enterprise plan
    with no custom fields
      should have link "Edit Available Custom Fields"
      should not have select "custom_field"
      clicking 'Edit Available Custom Fields'
        should have content "Add New Custom Field"
        entering 'Custom Field 1' and clicking 'Add'
          should not be empty
          should have css "#custom_field_545"
          adding again
            should eq 1
            should have content "name has already been taken"
          updating 'Custom Field 1' and clicking 'Update'
            should eq 1
            should eq "New Custom Field Name"
          updating to a taken name and clicking 'Update'
            should have content "name has already been taken"
            should not have content "name has already been taken"
        with MAX existing fields
          entering 'Custom Field 1' and clicking 'Add'
            should eq 4
            should have content "4 fields allowed on this service level"
    with custom fields ['Gender','Town']
      should have link "Edit Available Custom Fields"
      should have select "custom_field[id]", {:options=>["Gender", "Town"], :session_options=>#<Capybara::ReadOnlySessionConfig(#<Capybara::Sessio...e_aria_label=false, @save_path=#<Pathname:/ocp/tmp/capybara>, @app_host="http://www.example.com">)>}
    with 'Gender' first and 'Town' second
      selecting 'Town' and clicking 'Add to Widget'
        should eq "Gender"
      adding valid 'options' to Town
        should eq "Thule, Ys"
        updates the preview
      adding overlong 'options' to Town
        doesn't update the preview
      checking 'required?' on 'Town'
        should equal true
      checking 'Remove'
        should eq 1
        should include "578"
        updates the preview

Customer creation
  creates a new PromoterUser
  promoter user product
    creates a new product
    notifies OCP by email
  product page
    redirects to products page
    offers plans
    if we select 'back'
      drops the paywall

CWC Client Testing
  Create message
    should pass through delivery_agent options
  Client posts and errors
    should raise Cwc::BadRequest on failure
    should POST the message to /v2/message as XML, returning true on success
    should POST the message to /v2/validate as XML, returning true if the message is valid
    should POST the message to /v2/validate as XML, returning BadRequest if the message contains invalid phone
    should not POST the message to /v2/validate, returning false if the message contains inactive office
    should not POST the message to /v2/validate, returning false if the message contains invalid address
    should return a sucessful post on /v2/message if the message is valid
  End-to-end tests
    Sending to Custom Recipients with constituents_only on
      in-city profile to local CustomRecipient
        signing with a phone number
          completes an end-to-end send
        signing without a phone number
          doesn't attempt a CWC send
          sends an email instead

Email Body Export to CSV
  validity
    without email_body_export_options
      is invalid
    without destination_email
      is invalid
    without path_name
      is invalid
    with a completed transaction with duplicate path_name
      is valid first run and invalid with a duplicate path_name the second run
    with an in_progress transaction with duplicate path_name
      is not valid
    with invalid characters in the path_name
      is invalid
    with too many characters in the path_name
      is invalid
    with an invalid email
      is invalid
    with valid params with perfect email
      is valid
    with valid params where email has whitespaces that are stripped
      is valid
  inner logic
    without multi_content
      even with whitespaces in the destination_email
        creates a new csv and local transaction with success status for valid call to email_body_export
    multi_content
      multi_content_selector content_one
        returns only content_one
      multi_content_selector content_two
        returns only content_two
      multi_content_selector not present
        returns a row for content_one and content_two
    failures
      creates a new transaction with failed status and sends slack notification when error raised in email_body_export

Our email system, following the LinkedIn conventions
  sets the header to, from, reply-to, and sender correctly

Fastly caching
  the Oneclick/All-in-one widget
    via the Fastly domain/subdomain
      behaves like a page cached by Fastly
        is cached
        uses defined surrogate headers
        avoids other surrogate headers
      if we're logged in with a session_id
        behaves like an uncached page
          is not cached
      version 2.0
        with the ?onesig parameter
          Fastly service / Varnish
            attempts to strip the onesig parameter out and use a header (PENDING: Not yet implemented)
            returns the cached widget without params, but supplies the header (PENDING: Not yet implemented)
  The hosted-campaign page
    via the Fastly domain/subdomain
      and via the promo_url address /promo/:base62_id
        behaves like a page cached by Fastly
          is cached
          uses defined surrogate headers
          avoids other surrogate headers
      and via the promo_id address /edit?promo_id=:id
        behaves like a page cached by Fastly
          is cached
          uses defined surrogate headers
          avoids other surrogate headers
  the impact iframe
    via the Fastly domain/subdomain
      behaves like a page cached by Fastly
        is cached
        uses defined surrogate headers
        avoids other surrogate headers
      if we're logged in with a session_id
        behaves like a page cached by Fastly
          is cached
          uses defined surrogate headers
          avoids other surrogate headers
  the /blank_page_for_cookies widget workaround
    when visited over the fastly domain
      behaves like a page cached by Fastly
        is cached
        uses defined surrogate headers
        avoids other surrogate headers
  the Fluid widget
    via the Fastly domain/subdomain
      shows the fastly header
      the 'Sign with Facebook' link
        uses the full Oneclickpolitics path
      if we're logged in with a session_id
        doesn't show the fastly header
      with parameters
        doesn't set the fastly header
      version 2.0
        with the ?onesig parameter
          Fastly service / Varnish
            attempts to strip the onesig parameter out and use a header (PENDING: Not yet implemented)
            returns the cached widget without params, but supplies the header (PENDING: Not yet implemented)
  altering PromotedMessages
    purges the PromotedMessage's fastly cache
  altering PromoterUsers
    purges the PromoterUser's fastly cache
  Fastly middleman
    uses CORS headers that allow OCP esi and ajax calls
    version 2.0
      uses VCL to turn the onesig parameter into an HTTP header
  Live testing
    if we visit the widget while logged in with an OCP session
      Fastly/Varnish
        doesn't cache or record session values (PENDING: No reason given)
    the oneclick widget
      allows Facebook posts (PENDING: No reason given)
      allows Twitter posts (PENDING: No reason given)
      allows Twilio posts (PENDING: No reason given)
    the fluid widget
      allows 'Facebook sign' (PENDING: No reason given)
  widget
    with a user logged in via a Rails session or has a session_id
      visiting the widget
        via the Fastly domain/subdomain
          does not cache the widget with filled fields
          returns a blank widget
          pings a session controller to see if a session exists and fills the widget
          clears all params
  the ajax/esi visit counter
    records a visit
  the ajax/esi session call
    if a current_user exists
      sets the user
      fills out the widget fields
    if a sessioned profile exists
      sets the sessioned profile
      fills out the widget fields

The Lamar Alexander form
  finds the topic (PENDING: No reason given)

Geocoder
  when we edit our account profile address
    updates geo coordinates
  when we don't edit our account profile address
    doesn't update coordinates
  when we confirm a new account
    gives us new geo coordinates

SenderProfile
  with state and line1
    when we save without validation
      should still geocode lat and lon

The Homepage
  When we're not logged in
    shows us the public menu
  When we're logged in as a Promoter
    shows us the Promoter User menu

/promoter/login
  when we enter invalid credentials
    does not link 'Start your free trial' in the header

/pricing
  does not have facebook connect
  does not have twitter connect
  does not have account signin or create
  does not have link to create message

Help Actions Login
  active promoter with subscription and paid usage_plan logged in
    behaves like successful static page loads
      loads index page
      loads show_user_terms_conditions page
      loads show_terms_conditions_url page
      loads mission page
      loads culture page
      loads recognition page
      loads associations page
      loads nonprofits page
      loads agencies page
      loads startups page
      loads corporations page
      loads united_states page
      loads canada page
      loads australia page
      loads advocacy page
      loads acquisition page
      loads advisory page
      loads bill_tracking page
      loads case_study page
      loads contact_us page
  proxied promoter logged in
    behaves like successful static page loads
      loads index page
      loads show_user_terms_conditions page
      loads show_terms_conditions_url page
      loads mission page
      loads culture page
      loads recognition page
      loads associations page
      loads nonprofits page
      loads agencies page
      loads startups page
      loads corporations page
      loads united_states page
      loads canada page
      loads australia page
      loads advocacy page
      loads acquisition page
      loads advisory page
      loads bill_tracking page
      loads case_study page
      loads contact_us page
  promoter without email_blast_access logged in
    behaves like successful static page loads
      loads index page
      loads show_user_terms_conditions page
      loads show_terms_conditions_url page
      loads mission page
      loads culture page
      loads recognition page
      loads associations page
      loads nonprofits page
      loads agencies page
      loads startups page
      loads corporations page
      loads united_states page
      loads canada page
      loads australia page
      loads advocacy page
      loads acquisition page
      loads advisory page
      loads bill_tracking page
      loads case_study page
      loads contact_us page
  promoter with twilio_id logged in
    behaves like successful static page loads
      loads index page
      loads show_user_terms_conditions page
      loads show_terms_conditions_url page
      loads mission page
      loads culture page
      loads recognition page
      loads associations page
      loads nonprofits page
      loads agencies page
      loads startups page
      loads corporations page
      loads united_states page
      loads canada page
      loads australia page
      loads advocacy page
      loads acquisition page
      loads advisory page
      loads bill_tracking page
      loads case_study page
      loads contact_us page
  agency
    behaves like successful static page loads
      loads index page
      loads show_user_terms_conditions page
      loads show_terms_conditions_url page
      loads mission page
      loads culture page
      loads recognition page
      loads associations page
      loads nonprofits page
      loads agencies page
      loads startups page
      loads corporations page
      loads united_states page
      loads canada page
      loads australia page
      loads advocacy page
      loads acquisition page
      loads advisory page
      loads bill_tracking page
      loads case_study page
      loads contact_us page
  office of agency
    behaves like successful static page loads
      loads index page
      loads show_user_terms_conditions page
      loads show_terms_conditions_url page
      loads mission page
      loads culture page
      loads recognition page
      loads associations page
      loads nonprofits page
      loads agencies page
      loads startups page
      loads corporations page
      loads united_states page
      loads canada page
      loads australia page
      loads advocacy page
      loads acquisition page
      loads advisory page
      loads bill_tracking page
      loads case_study page
      loads contact_us page

Hosted Campaign Page
  layouts
    created with no layout
      with a selected campaign image
        displays default two-column layout
          should have selector "#campaign-image"
          should not have selector ".centered-columns"
      with no campaign image
        displays single column layout
          should not have selector "#campaign-image"
          should have selector ".centered-columns"
      renders title and call to action content
        should have content "Save the whales: Call to action"
        should have content "Save the Whales Title"
    created with background image layout
      visiting the hosted campaign page
        renders background image layout
          should have selector "#page-content"
        renders title and call to action content
          should have content "Save the whales: Call to action"
          should have content "Save the Whales Title"
    created with top image layout
      visiting the hosted campaign page
        renders top image layout
          should have selector "header"
        renders title and call to action content
          should have content "Save the whales: Call to action"
          should have content "Save the Whales Title"
  with video action only
    should render the page correctly
  the show_identity affects the page
    does not render account name if show_identity is false
      should not have css "div.logo"
    renders account name if show_identity is true
      should have css "div.logo"
  the show_counter affects the page
    does not render actions counter if show_counter is false
      should not have css "div.impact-frame"
    renders actions counter if show_counter is true
      should have css "div.impact-frame"
    if show_actions_progress is true
      renders progress circle
    and if show_actions_progress is false
      does not render progress circle

Kindful Login
  Promoter login
    shows a Kindful connect button
  The new customer screen
    shows a Kindful connect button
  connecting
    if authentication fails
      redirects to log_in
    for a new user
      creates a PromoterUser with the org name
      logs in as the PromoterUser
      the Kindful subpage
        offers to sync
        doesn't show a Connect link
    for an existing user
      with the correct Kindful Auth
        doesn't create new records
        logs in as the existing PromoterUser
      without a Kindful Auth
        but logged-in
          visiting the Kindful subpage
            the Kindful subpage
              has a Connect link
            clicking Connect
              doesn't create a new PromoterUser
              authenticates the PromoterUser
              stays logged in
              the Kindful subpage
                offers to sync
                doesn't show a Connect link

Kindful API
  Service Calls
    sync_contacts
      without a transaction_client_api_key
        is invalid
      without a quantity
        is invalid
      with api_key and quantity
        is valid
      data blocks
        excessive signatures on one message
          has two blocks
          behaves like block data
            a block's .data
              is valid JSON
              is an array
              wrapped in Subscribers JSON
                is valid JSON
          behaves like block data
            a block's .data
              is valid JSON
              is an array
              wrapped in Subscribers JSON
                is valid JSON
      with a bad block
        shows 0 synced
        has status failed
      with 2 blocks of 2 and 1 respective records
        shows 3 synced

KindfulTransaction
  if there's a recent non-Kindful transaction
    #latest_sync_for
      doesn't return it
  if there's a recent Kindful transaction
    #latest_sync_for
      returns it
  if there's an ongoing Kindful sync
    #ongoing_sync_for
      is true
  after a Kindful sync 'success'
    #ongoing_sync_for
      is false

Kindful modal
  when asynchronous
    on a Promoter's Kindful modal
      clicking 'Sync Advocates to List'
        the transaction divs
          sync_contacts
            behaves like a transaction div
              the div
                should have status 'in_progress'
                should have the uuid for an InternalApiMessage
                should start the check-status timer (globalRunningTransactions)
                should have a check-status path
                if we visit the check-path
                  returns JSON
                  shows the transaction status
        the API queue
          has an ApiAgentMessage for 'sync_contacts'
        if the ApiAgent succeeds
          visiting the check-path
            the returned JSON
              should not raise Exception
              shows status 'success'
              shows the total sync count
              records the transaction
        if the ApiAgent fails
          visiting the check-path
            the returned JSON
              should not raise Exception
              shows status 'failed'
              shows 0 syncs

Widgets
  without locational redirects
    when we have a donation redirect
      when we sign
        follows the donation redirect
  when our Promoter has conditional_redirects
    when we visit promoter/message#edit
      shows the redirects form
      when we fill out a valid redirect for MA
        saves the redirect
      when we fill out an invalid redirect
        adds a redirect
  when we have redirect conditions
    if our signature is from MA
      redirects to the MA website
    if our signature is from CA
      redirects to the CA website
    if our signature is out of state
      doesn't redirect
    when we also have a donation redirect
      if our signature is in-state
        it redirects to the CA website
        doesn't follow the donation redirect
      if our signature is out-of-state
        follows the donation redirect

Our Manual Account Creation System
  when we have an existing account
    when we complete the account sign-up form
      informs us that the email is already in use
      does not send out an email
  when we have no existing account
    when we complete the account sign-up form
      displays a success message
      sends out a registration/activation email

The Admin Controls
  with one non-NB Promoter
    and one NB Promoter
      if there's an existing Account for the new Promoter
        entering Nation 'oneclickpolitics'
          should have a 'Merge' link
          clicking 'Merge'
            the new Promoter
              shows the 'oneclickpolitics' Authentication
              is associated with the new Account
              is not associated with the existing Promoter's Account
              should have both messages
            the Authentication
              is associated with the new Promoter's Account
      if there's no existing Account for the new Promoter
        entering Nation 'oneclickpolitics'
          should have a 'Merge' link
          clicking 'Merge'
            the new Promoter
              shows the 'oneclickpolitics' Authentication
              is not associated with the existing Promoter's Account
              should have both messages
            the Authentication
              is associated with the new Promoter's Account
      entering the non-existent Nation 'devils_advocates'
        should have a 'Create' link
        clicking 'Create'
          the new Promoter
            shows the 'devils_advocates' Authentication
            is not associated with the existing Promoter's Account
            gets no new messages
          the Authentication
            is associated with the new Promoter's Account

Archive Message short-links
  when not logged in
    shows the Archive Message details
  when logged in
    shows the Archive Message details

Messages without recipients
  when we have no selected recipients
    shows a 'No Recipients' notice
    when we make the message a petition
      does not show a 'No Recipients' notice
      when we fill out the widget
        shouldn't have recipients
    when we fill out the widget
      should have nil recipients
  when we have a SelectedRecipients record with no recipients
    shows a 'No Recipients' notice
    when we add a recipient
      doesn't show a 'No Recipients' notice
    when we add a group
      doesn't show a 'No Recipients' notice

NationBuilder Login
  uses auth code flow rather than implicit grant
  prompts for a Nation
  when we enter a Nation
    removes the nation input
    for a valid nation
      hides the submit button
      produces a login link
      shows success message
    for an invalid nation
      show the submit button
      doesn't reveal login link
      shows error message
  when we click the connect link
    if authentication succeeds
      for a new user
        creates a new PromoterUser with the nation as uid
        records our token
        logs in as the PromoterUser
        notifies OCP by email
        the nationbuilder subpage
          loads
      for an existing user
        doesn't create a new PromoterUser
        records our token
        shows NationBuilder link
        sets :write_access to true (if false)
        should update token if :write_access == false
        should NOT update token if :write_access == true
      for an existing Account that is logged in
        logs in
    if authentication fails
      redirects to log_in
  The contact modal
    when we're missing an email address
      when we're not passed the paywall
        doesn't show the modal
      when we're logged in with NationBuilder'
        when we're past the paywall
          shows the modal
          inside the modal
            when we enter an invalid contact email
              doesn't close the modal
              shows a validation error message
            when we leave the contact email blank
              doesn't close the modal
              shows a validation error message
            when we enter a valid email
              closes the modal
    when we're missing a name
      when we're logged in with NationBuilder'
        when we're past the paywall
          shows the modal
        inside the modal
          when we enter a blank name
            doesn't close the modal
            shows a validation error message
          when we enter a valid name
            closes the modal

Controller Actions
  #show
    when we have synchronize dates
      shows our last synchronize date

Neon Login
  when we don't have a Neon l/p
    should have field :api_key
    should have field :org_id
    when we provide an invalid org id
      should have content "OrgId is invalid."
      should have field :api_key
      should have field :org_id
    when we provide an invalid api key
      should have content "Api key is invalid."
      should have field :api_key
      should have field :org_id
    when we provide a valid org id and api key
      should not have content "Your Org ID is invalid."
      should not have content "Your API Key is invalid."
      should not have content "There was a problem connecting to NeonCRM"
      should not have field :api_key
      should not have field :org_id
  when we already have a Neon account l/p
    should not have field :api_key
    should not have field :org_id
    should have link "Change NeonCRM keys"
    when we click 'Change NeonCRM keys'
      should have content "Please enter your NeonCRM API Org Id and API Key."
      when we submit working keys
        should not have content "Your Org ID is invalid."
        should not have content "Your API Key is invalid."
        should not have content "There was a problem connecting to NeonCRM"
        should not have field :api_key
        should not have field :org_id
      when we submit bad keys
        should have content "Api key is invalid."
        should have field :api_key
        should have field :org_id

Customer Creation
  when a promoter is logged in
    shouldn't show the creation page (PENDING: Not yet implemented)
  when a promoter is not logged in
    shows a NationBuilder link
    when we enter an existing address
      shows a validation message
      doesn't create a new promoter
    when we enter text into the honeypot field
      shows a success message
      doesn't create a new promoter
    when we enter a new email
      when we enter a name, password and password confirmation
        creates a new promoter
        logs us in
        shows pricing
    if email is missing
      doesn't create a new promoter
      shows a validation message
    if organization is missing
      doesn't create a new promoter
      shows a validation message
    if the password is missing
      doesn't create a new promoter
      shows a validation message
    if the password and confirmation don't match
      doesn't create a new promoter
      shows a validation message

New Sales Spec v1
  when the new_sales global is ON
    the front page
      doesn't link to Pricing
    the public Pricing page
      hides all plans
      hides pricing information
      hides all links
      has a 'Schedule Demo button
    the login page
      hides the create account form

New Sales Spec v2
  when the new_sales global is ON
    A PromoterUser
      on 'test' usage plan
        without an Offer outstanding
          Plan Limitations
            limits exports to 50
            doesn't restrict custom recipients
            allows proxies
            allows state access
            custom fields
              should not be empty
          as a proxy
            signs in as the Proxy
            the url
              should match "/promoter/27827/messages"
        with an Offer outstanding
          visiting the dashboard
            drops the Paywall
          as a proxy
            signs in as the Proxy
            drops the proxy's Paywall
            the proxy's Paywall
              should include "/promoter/27837/products_available"
              should have content "please contact your office's master account holder"
              should not have link "Choose"
    the new Paywall
      for a testing Promoter
        with an ongoing Offer
          for 12000 USD with unlimited state access and customizable widgets
            the Pricing panel
              shows the total price
              shows the a la carte options
              has a 'Choose' link
        without an offer
          the Pricing panel
            doesn't have a 'Choose' link
    admins
      promoter#edit
        changing the password
          has an auto-email checkbox
          if the box is checked
            clicking
              sends an email invite
              the invite
                offers the new password
        if an Offer exists
          shows the price
          shows the billing_cycle
          shows an edit button
          shows a Delete button
          clicking 'Edit Offer'
            loads the edit page
          clicking 'Delete Offer'
            removes the Offer
        if an Offer doesn't exist
          shows a create button
          clicking
            loads the new page
      offer#new
        if we don't set a price
          shows a validation message
        if we choose :enterprise and :three_month and 'Save'
          the page
            shows an error message
          the Sale Offer
            doesn't save
        if we choose :enterprise and :yearly and 'Save'
          the page
            doesn't show an error message
          the Sale Offer
            saves
        if we choose :multiple_state_access and :six_month and 'Save'
          the Product
            has :multiple but not :unlimited state access
          the Subscription
            has :six_month billing cycle
          the PromoterUser
            touches the cache
          changing the subscription
            changing to :yearly
              updates the SaleOffer record
              the Subscription
                has :yearly billing cycle
          changing the Product
            changing to :unlimited_state_access
              updates the SaleOffer record
              the Product
                has :unlimited state access
            changing to :state_access
              the Product
                has only single state access
            changing to no state access
              the Product
                has no state access
        if we choose :agency_offices and :yearly and 'Save'
          the page
            doesn't show an error message
          the Sale Offer
            records the office cap and price
          making the first check payment
            updates the Promoter and office cap
    accepting an agency SaleOffer
      admins
        can remove the offer
        can create a new Promoter with email or Nationbuilder access
        can set or change the password
        can set a la carte prospective Product options
        can set prospective Product price
        can make a prospective Product offer
        after creating and setting the prospective Product
          if the promoter has a login email
            auto-sends an email with l/p (PENDING: Not yet implemented)
      when the Promoter logs in
        if there's a prospective multi-office Product on offer
          offers the capped Multi-Office plan
          doesn't offer reseller or conventional plans
          shows their price
          shows their plan cap

Nimble Login
  Promoter login
    shows a Nimble connect button
  The new customer screen
    shows a Nimble connect button
  connecting
    if authentication fails
      redirects to log_in
    for a new user
      creates a PromoterUser with the org name
      logs in as the PromoterUser
      sets the access token
      stores the refresh token
      stores the expiration time
      the Nimble subpage
        offers to sync
        doesn't show a Connect link
    for an existing user
      with the correct Nimble Auth
        doesn't create new records
        logs in as the existing PromoterUser
        sets the access token
        updates the access token
        stores the refresh token and expires_at
      without a Nimble Auth
        but logged-in
          visiting the Nimble subpage
            the Nimble subpage
              has a Connect link
            clicking Connect
              doesn't create a new PromoterUser
              authenticates the PromoterUser
              stores the access token, refresh token, and expires_at
              stays logged in
              sets the access token
              the Nimble subpage
                offers to sync
                doesn't show a Connect link

Nimble API
  Service Calls
    create_field
      without a transaction_client_api_key
        is invalid
      without a custom field name
        is invalid
      without a group_id
        is invalid
      with api_key, group_id, and name
        is valid
    sync_contacts
      without a transaction_client_api_key
        is invalid
      without a quantity
        is invalid
      with api_key and quantity
        is valid
      with a notification_email
        sends an email to that address
        does not send the email if the transaction fails
      without custom fields
        does not make a request to create fields
        sends an email if there's an access token failure
        with more than one record
          only sends an email once on access token failure
      with custom fields
        and no existing Nimble group
          makes a request to create a custom group on Nimble
          persists the resulting group's ID to the database
          passes the resulting group's ID to the create_field method
          sends an email if create_group fails
        and an existing Nimble group
          does not make a request to create a custom group
          makes a request to create the fields on Nimble
          persists the resulting field's ID to the database
          makes 2 requests if the promoter has 2 custom fields
          only makes requests for fields owned by the promoter
          includes a 'create_field' key in the transaction's result
          sends an email if create_field fails
          and existing Nimble fields
            doesn't make a request
      data blocks
        excessive signatures on one message
          has two blocks
          shows no failed emails
          behaves like non-array block data
            a block's .data
              is valid JSON
              is an array
          behaves like non-array block data
            a block's .data
              is valid JSON
              is an array
        with cutoff dates
          passes the parameters to campaign_monitor_export
        with custom fields
          includes the custom fields in the data block
      with a bad block
        shows 0 synced
        has status failed
        shows 1 failed email
      with 2 blocks of 2 and 1 respective records
        shows 3 synced

NimbleTransaction
  if there's a recent non-Nimble transaction
    #latest_sync_for
      doesn't return it
  if there's a recent Nimble transaction
    #latest_sync_for
      returns it
  if there's an ongoing Nimble sync
    #ongoing_sync_for
      is true
  after a Nimble sync 'success'
    #ongoing_sync_for
      is false

Nimble modal
  when asynchronous
    on a Promoter's Nimble modal
      shouldn't say a sync is in progress
      with an expired access token
        requests a new access token
        passes the new access token to the Transaction
        which can't be updated
          does not run the transaction
      with an in progress transaction
        should say a sync is in progress
      with two successful transactions
        should show total synced to date
        should only total successful transactions for that user
      clicking 'Sync Advocates'
        the API queue
          has an ApiAgentMessage for 'sync_contacts'
        if the ApiAgent succeeds
          records the transaction

ohm cleaner
  OCP::UserMessages
    from outside the cutoff
      Redis
        includes Object keys
        running OhmCleaner.clean()
          doesn't include Object keys
    inside the cutoff
      Redis
        includes Object keys
        running OhmCleaner.clean()
          includes Object keys
  OCP::InternalApiMessages, DataBlocks, and CallDataBlocks
    from outside the cutoff
      Redis
        includes Object keys
        running OhmCleaner.clean()
          doesn't include Object keys
    inside the cutoff
      Redis
        includes Object keys
        running OhmCleaner.clean()
          includes Object keys

OHM Service
  connects to redis

oneClick Signature
  with a signature
    includes the sig id
    takes an md5 hash of the sig details
    if we match the id but not the details
      once
        the JSON
          is empty
        and then pass the correct code
          returns JSON
          the JSON
            is not empty
      three times
        and then pass the correct code
          returns JSON
          the JSON
            is empty
    if the id doesn't exist
      returns JSON
      the JSON
        is empty
    if we match
      returns JSON
      the JSON
        returns all signature fields
      a subsequent code with the same id
        the JSON
          is not empty
          returns all signature fields

Patch-calling widget
  with Twilio credits and a Twilio Phone
    with no phone recipients
      doesn't show the patch calling form
    with 3 phone recipients
      asynchronously
        the public check_path
          isn't blank
          doesn't need a promoter_id
          visiting
            returns a JSON message
      synchronously
        shows the patch calling form
        the form
          populates a phone field
          shows checked boxes for each recipient
          tracks the PhoneServiceSend
        with an invalid phone number
          doesn't update the Sender Profile
          populates the phone field
          shows an error message
          doesn't begin the call
        with a valid phone number
          selecting 0 and clicking send
            doesn't update the PhoneServiceSend
            shows an error message
            doesn't begin the call
          selecting 2 and clicking send
            activates 2 recipients to the PhoneServiceSend
            PhoneServiceSend
              tracks the promoted_message_id
            Calling
              behaves like a call div
                the call div
                  should have status 'in_progress'
                  should have the sid for a call
                  should start the check-status timer (globalRunningTransactions)
                  should have a check-status path
                  if we visit the call check-path
                    returns JSON
                    shows the call status
                the transaction div
                  points twilio to the edit_greeting call
              the patch_call call
                stores the call_sid
                with a recorded message
                  plays the recorded greeting
                without a recorded message
                  describes the promoter and message
                the call
                  with working CallSid and Call objects
                    behaves like the call menu
                      offers to connect or skip
                      if we connect
                        dials the first office
                        finishing the call
                          records a PhoneServiceDelivery
                          redirecting
                            offers to connect or skip to the second office
                            if we connect
                              dials the second office
                              finishing the call
                                records a PhoneServiceDelivery
                                redirecting
                                  hangs up
                      if we skip
                        offers to connect or skip to the second office
                        if we skip
                          hangs up
                  with missing CallSid or Call object
                    behaves like the call menu
                      offers to connect or skip
                      if we connect
                        dials the first office
                        finishing the call
                          records a PhoneServiceDelivery
                          redirecting
                            offers to connect or skip to the second office
                            if we connect
                              dials the second office
                              finishing the call
                                records a PhoneServiceDelivery
                                redirecting
                                  hangs up
                      if we skip
                        offers to connect or skip to the second office
                        if we skip
                          hangs up
  with Twilio credits and without a Twilio phone
    doesn't show the patch calling form
    shows the click to call form
  without Twilio credits and without a Twilio phone
    doesn't show the patch calling form
    shows the click to call form

TwilioProduct
  add_credits
    with price=100, credits=50, active_flg=false
      freeze_active_flg=true
        adding 75 credits
          should eq 125
          should equal false
      freeze_active_flg=false
        adding 75 credits
          should eq 125
          should equal true
  remove_credit
    with price=60, credits=100, active_flg=true
      freeze_active_flg=true
        removing 50 credits
          should eq 50
          should equal true
      freeze_active_flg=false
        removing 50 credits
          should eq 50
          should equal false
  update_price
    with price=50, credits=100, active_flg=true
      freeze_active_flg=true
        update_price(200.0)
          should eq 200
          should equal true
      freeze_active_flg=false
        update_price(200.0)
          should eq 200
          should equal false
          sales@oneclickpolitics.com
            receives a notification
  handle_all_price_updates
    with existing TwilioBillingPeriods
      updates the product
      doesn't remove the existing bill outside the period
      removes the bill inside the period
      adds a new bill

TwilioApi
  Service Calls
    any call
      without a supplied transaction_client_id, but with a TwilioProduct record and a twilio_client_id_string
        is invalid
    patch_call
      without a transaction_client_id
        is invalid
      without a twilio_phone
        is invalid
      with a bad outbound number
        is invalid
      without a service send
        is invalid
      with a mismatched promoted_message_id and promoter_user_id
        is invalid
      with a matched promoted_message_id and promoter_user_id
        is valid
      the transaction
        is public
      the internal_message
        is public
    find_account
      without a transaction_client_id
        is invalid
      with transaction_client_id
        is valid
      if Twilio finds the client_id
        has status success
        the result
          has the client_id
      if Twilio doesn't find the client_id
        has status failed
        the result
          shows resource not found
    create_account
      without a name provided
        the result
          uses the promoter's name
      with a name
        is valid
      if Twilio accepts the name
        has status success
        the result
          has the name
          has the sid
        the TwilioProduct
          has the API token
    suspend_account
      without a transaction_client_id
        is invalid
      with transaction_client_id
        is valid
      if Twilio finds the client_id
        the result
          has status success
          is suspended
      if Twilio doesn't find the client_id
        has status failed
        the result
          shows resource not found
    activate_account
      without a transaction_client_id
        is invalid
      with transaction_client_id
        is valid
      if Twilio finds the client_id
        the result
          has status success
          is active
      if Twilio doesn't find the client_id
        has status failed
        the result
          shows resource not found
    get_total_price_since
      without a transaction_client_id
        is invalid
      with transaction_client_id
        is valid
      if Twilio finds the client_id
        if we provide a start_date
          the result
            has status success
            has the total price after the start date
            has the price between the start date and yesterday
            has the price since today
            has the start_date
          the cache
            records the price today
          the TwilioBillingPeriod record
            records the price to yesterday
            records the period_start
            records the period_end as yesterday
          the TwilioProduct record
            records the prices
        if a price is cached for today
          with a start_date of today
            the result
              has status success
              has the cached price
      if Twilio doesn't find the client_id
        has status failed
        the result
          shows resource not found
    delete_greeting
      without a transaction_client_id
        is invalid
      without a recording_sid
        is invalid
      with a transaction_client_id and recording_sid
        is valid
      if Twilio finds the client_id
        if Twilio finds the recording_sid
          the result
            has status success
            shows the removed recording_sid
        if Twilio doesn't find the recording_sid
          the result
            has status failed
            the result
              shows a failure to find_greeting
      if Twilio doesn't find the client_id
        has status failed
        the result
          shows resource not found
    edit_greeting
      without a transaction_client_id
        is invalid
      without a twilio_phone
        is invalid
      with a mismatched promoted_message_id and promoter_user_id
        is invalid
      with a bad outbound number
        is invalid
      with a matched promoted_message_id and promoter_user_id
        is valid
    list_phones
      as a call
        is valid
      the result
        has status success
        lists all calls
        the first call
          lists the phone_sid and phone_number
        the second call
          lists the phone_sid and phone_number
    remove_phone
      as a call
        is valid
      the result
        has status success
        shows the removed phone
      with success
        the promoter
          clears the phone and sid
    send_phone
      as a call
        is valid
      the result
        has status success
        shows the sent phone
      with success
        the promoter
          records the phone and sid

Admin Pages
  for a Promoter without a TwilioProduct
    without a Twilio account
      redirects to the new subaccount page
    the new Subaccount page
      synchronously
        has a 'Create' button
        clicking 'Create'
          creates a TwilioProduct
          links 'View Credits'
      asynchronously
        has a 'Create' button
        clicking 'Create'
          makes an ApiAgentMessage
          create_account
            behaves like a transaction div
              the div
                should have status 'in_progress'
                should have the uuid for an InternalApiMessage
                should start the check-status timer (globalRunningTransactions)
                should have a check-status path
                if we visit the check-path
                  returns JSON
                  shows the transaction status
          if the ApiAgent succeeds
            sets the Promoter's client_id
            visiting the check-path
              the returned JSON
                should not raise Exception
                shows status 'success'
                shows the client_id
  for a Promoter with a TwilioProduct
    with credits
      shows total credits
      with a small number of credits left
        shows total credits
    if we're inactive
      lists us as inactive
    if we're active
      lists us as active
    if we're frozen as active
      lists freeze_active_flg
      and we activate
        keeps us inactive
      and we unfreeze and activate
        makes us Active
    with a Stripe account
      with a Product needing credits
        if we purchase credits
          if the Stripe call succeeds
            records the total credits
            adds the Stripe charge
            activates the Product
            shows the credit history
            allows us to refund the credit
            if we refund
              if the Stripe refund call fails
                doesn't change the total credits
                doesn't change the credit history
                doesn't deactivate the Product
              if the Stripe refund call succeeds
                records the total credits
                removes the credits from the credit history
                deactivates the Product
          if the Stripe call fails
            doesn't charge us on Stripe
            doesn't add credits
            doesn't activate the Product
            shows an error message
        if we grant credits
          records the total credits
          activates the Product
          shows the credit history
          allows us to remove the credit
          if we remove Credits
            records the total credits
            removes the credits from the credit history
            deactivates the Product
    without a phone
      links the phones page with 'No phone'
    with a phone
      links the phones page with the phone number
  Twilio Phones
    shows a dropdown of available phones
    selecting a phone
      updates the TwilioProduct
      shows the remove link
      shows the phone number
      disables the 'Add' button
      and clicking 'Remove'
        removes the phone from the TwilioProduct
        hides the remove link
        enables the 'Add' button
  Twilio Credits report
    with multiple promoters and credits
      for a TwilioProduct in its warning period
        shows total credits
        shows usage
        shows 'Low' warning
        links the individual credits page
      for an invalid TwilioProduct
        shows total credits
        shows usage
        shows status Inactive
        links the individual credits page

Calls controller
  check Status (by Call SID / CallSid) (called from browser/widget)
    checks the Call's Status (PENDING: Not yet implemented)
    checks any notes/data to be read for this part of the ongoing Call (PENDING: Not yet implemented)
  when the Call data changes
    calls and updates javascript (PENDING: Not yet implemented)

Promoter Pages
  without a Twilio Subaccount
    TwilioProduct#allow_promoter
      is false
    visiting credits#index
      offers to create a Twilio Account
      if we create a Twilio Account
        creates a Twilio Product
        reaches credits#index
    visiting the greeting path
      redirects to no_service
      instructs the user to contact support
  with a TwilioProduct but no Twilio phone
    visiting credits#index
      shows no phone number
    visiting the greeting path
      redirects to no_service
      instructs the user to contact support
  with a TwilioProduct and Twilio phone
    visiting credits#index
      refers to the sales team
      Usage reports
        shows the credit history
        after the transaction
          updates credits used
          shows the total credits
          for a product in the warning period
            shows a warning
        for an inactive product
          shows the inactive status
    for a Promoted Message
      without an associated recording
        takes a phone number
        if we supply a number
          the call
            behaves like a call div
              the call div
                should have status 'in_progress'
                should have the sid for a call
                should start the check-status timer (globalRunningTransactions)
                should have a check-status path
                if we visit the call check-path
                  returns JSON
                  shows the call status
              the transaction div
                points twilio to the edit_greeting call
            the test_edit_greeting call
              describes the promoter and message
              redirects to the greeting menu
              redirecting to the greeting menu
                offers to record a greeting
              choosing to record
                takes recorded input
                after recording
                  before the callback runs
                    should have say "Please wait."
                  when the callback runs
                    records the greeting
                    offers the choice to keep or re-record
                    if we keep
                      offers to play or delete our recording
                      the OCP::CallDataBlock Call result
                        is JSON
                        links the greeting
                      if we play it
                        plays
                      if we delete it
                        clears the message
                        redirecting
                          returns to the greeting menu
                    if we re-record
                      clears the message
                      returns to the recording
              when the call ends
                the Call object
                  completes the Call object
      with an associated recording
        links the greeting
        takes a phone number for re-recording

An HTML-based email view
  preserves newlines (FAILED - 39)

promoter user
  create a subscription
    should have css "h5", {:text=>"Choose any plan and try us free for 2 weeks", :session_options=>#<Capybara::ReadOnlySessionC...e_aria_label=false, @save_path=#<Pathname:/ocp/tmp/capybara>, @app_host="http://www.example.com">)>}
    selecting type standard (PENDING: No reason given)
    selecting type pro (PENDING: No reason given)
    selecting type enterprise (PENDING: No reason given)
    selecting type free (PENDING: No reason given)
  no subscription visting promoter pages
    can not edit form fields
    can't send in survey mode
    doesn't allow senders to edit message
    doesn't allow post send redirect
    doesn't redirects user to products page
  Activist subscription
    can send in survey mode
    doesn't allow post send redirect
    allows viewing custom widgets
    widget preview
      has OCP branding on widget
      loads fluid widget
    #select_recipients
      doesn't allow select recipients House
      doesn't allow select recipients Senate
      allows state access
      allow custom recipients preview
      custom_recipients preview
        should have content "Your Custom Targets"
        should have content "Feature not available at for your product tier"
  Cause subscription
    allow senders to edit message
    doesn't allow custom recipients
    doesn't allow post send redirect
    #select_recipients
      allows select recipients House
      allows select recipients Senate
      allow state access
      allows custom recipients
    state access
      with no assigned state
      with assigned state
    behaves like a Signature Exporter
      shows the new CSVs link
  Movement subscription
    allow senders to edit message
    allows post send redirect
    #select_recipients
      allows select recipients House
      allows select recipients Senate
      has the States tab
      allows custom recipients
    allow access to multiple state
      should have css "a", {:text=>"Arkansas", :session_options=>#<Capybara::ReadOnlySessionConfig(#<Capybara::SessionConfig:0x0...e_aria_label=false, @save_path=#<Pathname:/ocp/tmp/capybara>, @app_host="http://www.example.com">)>}
      should have css "a", {:text=>"New York", :session_options=>#<Capybara::ReadOnlySessionConfig(#<Capybara::SessionConfig:0x0...e_aria_label=false, @save_path=#<Pathname:/ocp/tmp/capybara>, @app_host="http://www.example.com">)>}
    the fluid widget
      keeps OCP branding
      when we sign
        keeps OCP branding
    the mobile widget
      keeps OCP branding
      when we sign
        keeps OCP branding (FAILED - 40)
    with remove_branding add-on
      the fluid widget
        removes OCP branding
        when we sign
          removes OCP branding
      the mobile widget
        removes OCP branding
        when we sign
          removes OCP branding (FAILED - 41)
    behaves like a Signature Exporter
      shows the new CSVs link
  Standard subscription
    allow senders to edit message
    allows post send redirect
    doesn't allow senders to receive responses
    keeps OCP branding on widget
    allows viewing custom widgets
    #select_recipients
      allows select recipients House
      allows select recipients Senate
      has the States tab
      allow custom recipients
    state access
      allows user to assign state
      with a state selected
        doesn't allows user to assign state
        links to the user's one state
    behaves like a Signature Exporter
      shows the new CSVs link
  Pro subscription
    allow senders to edit message
    allows post send redirect
    doesn't allow senders to receive responses
    removes OCP branding off widget
    allows custom widgets
    #select_recipients
      allows select recipients House
      allows select recipients Senate
      has the States tab
      allows custom recipients
    state access
      with no assigned state
      should not have css "a", {:text=>"Arkansas", :session_options=>#<Capybara::ReadOnlySessionConfig(#<Capybara::SessionConfig:0x0...e_aria_label=false, @save_path=#<Pathname:/ocp/tmp/capybara>, @app_host="http://www.example.com">)>}
      should not have css "a", {:text=>"New York", :session_options=>#<Capybara::ReadOnlySessionConfig(#<Capybara::SessionConfig:0x0...e_aria_label=false, @save_path=#<Pathname:/ocp/tmp/capybara>, @app_host="http://www.example.com">)>}
      with two states selected
        allows user to assign one more state
        links to the user's first state
        links to the user's second state
      with three states selected
        doesn't allow user to assign one more state
        links to the user's first state
        links to the user's second state
        links to the user's third state
    behaves like a Signature Exporter
      shows the new CSVs link
  Grandfathered in subscription
    allow senders to edit message
    allows post send redirect
    doesn't allow senders to receive responses
    allows custom widgets
    #select_recipients
      allows select recipients House
      allows select recipients Senate
      has the States tab
    allow access to multiple state
      should have css "a", {:text=>"Arkansas", :session_options=>#<Capybara::ReadOnlySessionConfig(#<Capybara::SessionConfig:0x0...e_aria_label=false, @save_path=#<Pathname:/ocp/tmp/capybara>, @app_host="http://www.example.com">)>}
      should have css "a", {:text=>"New York", :session_options=>#<Capybara::ReadOnlySessionConfig(#<Capybara::SessionConfig:0x0...e_aria_label=false, @save_path=#<Pathname:/ocp/tmp/capybara>, @app_host="http://www.example.com">)>}
    behaves like a Signature Exporter
      shows the new CSVs link
  Test account no subscription
    allow senders to edit message
    allows post send redirect
    doesn't allow senders to receive responses
    allows custom widgets
    #select_recipients
      allows select recipients House
      allows select recipients Senate
      has the States tab
    allow access to multiple state
      should have css "a", {:text=>"Arkansas", :session_options=>#<Capybara::ReadOnlySessionConfig(#<Capybara::SessionConfig:0x0...e_aria_label=false, @save_path=#<Pathname:/ocp/tmp/capybara>, @app_host="http://www.example.com">)>}
      should have css "a", {:text=>"New York", :session_options=>#<Capybara::ReadOnlySessionConfig(#<Capybara::SessionConfig:0x0...e_aria_label=false, @save_path=#<Pathname:/ocp/tmp/capybara>, @app_host="http://www.example.com">)>}
    behaves like a Signature Exporter
      shows the new CSVs link
    widget preview
      has OCP branding on widget
      loads fluid widget

account/promoter page
  when logging in as an Account
    visiting /account
      when clicking new message
        visits the new promoter message page

promoter message
  creating a new message
    creating a valid message
      creates a message and goes to the show page
      flashes a success notice
    creating a in valid message
      renders new page
      flashes campaign name error

Promoter profile URLs
  when we're not logged in as promoter
    when the promoter doesn't exist
      redirects to the front page
    when the promoter exists
      visit /profiles/save-the-whales
        is not redirected
        shows the correct promoter name

Promoter-Profile edit page
  when email is invalid
    should have content "Please enter a valid email address"

Public-facing Profile
  should have content "This mission statement will self-destruct."
  should have content "Hwaet! A larum! Call to arms."
  shares the profile link
  should equal true
  should equal true
  send completion bars should be accurate (PENDING: Not yet implemented)
  send numbers should be accurate (PENDING: Not yet implemented)
  a more-supporters subpage (PENDING: Not yet implemented)
  when we don't have contact urls
    should equal false
    should equal false
  unassociated messages
    does not load
    does not show impact topics
    when users upvote
      doesn't list them as supporters
      doesn't link to their profile pages (PENDING: Not yet implemented)
  the account-id route
    for Accounts without a PromoterUser
      creates a new Promoter
      shows their page
    for Accounts with a PromoterUser
      doesn't create a new Promoter
      shows their page

promoter/ api_info
  if we don't have an API key
    generates one
    shows the access token
  if we already have an API key
    does not generate one
    shows the access token

Promoted Messages
  as a Promoter
    shows accurate goal and send progress (PENDING: No reason given)
    keeps monthly tabs for billing

batch sender
  when a Throttle record exists
    with cutoff = 10
      should eq 10
    with cutoff = 0
      should eq 0
  without a Throttle record
    should eq 0
  when the quota cutoff is zero
    when our recipient has a deliverable web_form
      when we send a message
        batches correctly
    when our recipient has an undeliverable web_form but a backup fax
      when we send a message
        batches correctly
      before we batch send
        when we send a message
          snapshotting
            doesn't clear the QuotaMatrix
            does't affect Ohm objects
            the snapshot
              is json
          clearing QuotaMatrix
            and restoring the snapshot
              clears QuotaMatrix
              restores QuotaMatrix on another channel
              does't affect Ohm objects
              running the *restored* batch sender
                when RestoredBatchSender sends batches
                  sends a single batch Fax
                  the final delivery to A
                    mentions both collated fax counts
    when our recipient has an undeliverable web_form but a backup email
      when we send a message
        batches correctly
    when one of two recipients fails
      still archives the conversion
    when delivery fails for both webform and backup fax
      still archives the conversion
    in-state, out-of-city Profile to local CustomRecipient
      when we send a message
        batches correctly
    out of state, in US Profile for state CustomRecipient
      when we send a message
        batches correctly
    in-state profile to one CustomRecipient, out-of-state to another CustomRecipient
      batches correctly
    an OOD US Congress recipient
      doesn't batch
  Collated Faxes
    for two messaging targets
      with multiple faxes
        before we hit the daily Fax limit
          with widget signatures
            with faxes passing the queues
              behaves like a direct fax sender
                sends the faxes directly
                doesn't collate the faxes
                when BatchSender sends collated faxes
                  shouldn't send more faxes
              behaves like a direct fax sender
                sends the faxes directly
                doesn't collate the faxes
                when BatchSender sends collated faxes
                  shouldn't send more faxes
        when we hit the daily Fax limit
          with widget signatures
            with faxes passing the queues
              doesn't deliver the faxes
              collates the faxes
              when BatchSender sends collated faxes
                behaves like a collator of faxes
                  sends one fax per inbound subject
                  the collated faxes
                    show correct subjects, bodies, and signatures
                    doesn't escape apostrophes in text
                behaves like a collator of faxes
                  sends one fax per inbound subject
                  the collated faxes
                    show correct subjects, bodies, and signatures
                    doesn't escape apostrophes in text
              before we send collated faxes
                snapshotting
                  doesn't clear the FaxMatrix
                  does't affect Ohm objects
                  the snapshot
                    is json
                clearing FaxMatrix
                  and restoring the snapshot
                    clears FaxMatrix
                    restores FaxMatrix on another channel
                    does't affect Ohm objects
                    running the *restored* batch sender
                      when RestoredBatchSender sends collated faxes
                        behaves like a collator of faxes
                          sends one fax per inbound subject
                          the collated faxes
                            show correct subjects, bodies, and signatures
                            doesn't escape apostrophes in text
                        behaves like a collator of faxes
                          sends one fax per inbound subject
                          the collated faxes
                            show correct subjects, bodies, and signatures
                            doesn't escape apostrophes in text
  with a SynchronizeCall
    .send_collated_faxes
      if we fail the Sync midway
        doesn't continue sending
    .send_batched_messages
      if we fail the Sync midway
        doesn't continue sending
  Clearing redis
    BatchSender
      clear_all
        clears the QuotaMatrix
        clears the FaxMatrix
        doesn't clear the RestoredQuotaMatrix
        doesn't clear the RestoredFaxMatrix
    RestoredBatchSender
      clear_all
        doesn't clear the QuotaMatrix
        doesn't clear the FaxMatrix
        clears the RestoredQuotaMatrix
        clears the RestoredFaxMatrix

Delivery Agent
  Single recipient
    end to end testing
    Email exception details should be in delivery message
    Fax exception details should be in delivery message
    Failed delivery delivers to next priority address
      email -> fax address
      email -> web address
      email -> none
  Multiple recipients
    end to end testing
    Failed delivery delivers to next priority address
    Update the status when next address is n/a
  Multi content
    end to end testing

End-to-end tests
  when an error is raised
    logging and alerting
      should log the exception and email a developer (currently dev-group)
  The phone-required form
    checks for a selected content_two alternate
    when the sender is not a constituent
      completes an end-to-end send
      passes in the district address
    when the sender is a constituent
      passes in the sender address
  when there is no RecipientAddress for a recipient
    fails gracefully
      does not raise/log an exception and it does archive the internal_message
  when there are no web_form_steps for web form
    when we have a backup email address
      gracefully fails the web_form send and sends an email
  when the recipient's use_web_form_api flag is true
    (temporarily) doesn't call the one-scrape app instead of OCP::WebForm#send_message
  The always-fail form
    import the house of reps and do a test send (PENDING: Not yet implemented)
    we want to enter best-fit values into dropdowns without good matches; in general (PENDING: Not yet implemented)
    always provide a default value for mr/mrs sig fields (PENDING: Not yet implemented)
    make sure we don't lose topic information (PENDING: Not yet implemented)
    we need to scan and interact with radio buttons (PENDING: Not yet implemented)
    when the web_form fails
      when we have a backup email address
        completes an end-to-end send and sets archive_internal_message sent_at and saves archive_message bodycachd
  The Lamar Alexander form
    completes an end-to-end send
  The Radio Button form
    completes an end-to-end send
  The ASCII-only contact form
    completes an end-to-end send
  The FCC form
    when we add a 'confirmation_link' WebFormStep
      if the link is not found
        fails delivery
      if the link is found
        completes delivery
  Sending to Custom Recipients with constituents_only on
    in-city profile to local CustomRecipient
      completes an end-to-end send
    in-state profile to one state CustomRecipient
      completes an end-to-end send
    in-state profile to multiple state CustomRecipients
      completes an end-to-end send
    out-of-state profile to local CustomRecipient
      is blocked
    with a Fax instead of Email
      completes an end-to-end send
  Sending to in-district US Congress recipients
    delivers an email
  End-to-end test with the allow_responses flag
    from constituents
      when we allow_responses
        retains the allow_responses flag
        the email on the form success page
          belongs to the sender
      when we don't allow_responses
        does not retain the allow_responses flag
        the email on the form success page
          is 'contact@oneclickpolitics.com'
    from non-constituents
      when we allow_responses
        does not retain the allow_responses flag
        the email on the form success page
          is 'contact@oneclickpolitics.com'
    when we don't check the box on the widget
      for constituents
        it passes through an intermediary/one-time address to the form (PENDING: Not yet implemented)
      for non-constituents
        it passes through an intermediary/one-time address to the form (PENDING: Not yet implemented)
    with no redirect address
      should eq :sent
      should have content "Share this message and encourage others to take action!"
      should eq "Wisconsin Assemblymember"
      should eq "20148"
      should eq 1
      should not eq nil
      should eq [24288]
      should match /sent at/
    with redirect address
      should eq :sent
      should eq "Wisconsin Assemblymember"
      should eq "20155"
      should eq 1
      should not eq nil
      should eq [24295]
      should match /sent at/
      should match /www.weather.com/
      should not have content "Share this message and encourage others to take action!"
  with the always_send flag
    sending to OOD Custom Recipients
      with Throttle #batch_sender_throttles_always_sends FALSE
        delivers to the always_send recipient
      with Throttle #batch_sender_throttles_always_sends TRUE
        batches the always_send recipient
    sending to OOD standard (non-Custom) recipients
      with Throttle #batch_sender_threshold 0
        with Throttle #batch_sender_throttles_always_sends TRUE
          batches the always_send recipient
        with Throttle #batch_sender_throttles_always_sends FALSE
          delivers to the always_send recipient
  queued_at
    sets the conversion's queued_at column to the current time
  ConventionalServiceSend life cycle
    creates a ConventionalServiceSend when widget is signed
    updates a ConventionalServiceSend to status 'SENT' when UserMessage archived
  End-to-end with Canadian Addresses
    for an L constituency in Toronto, Ontario
      when we sign & send the widget from Toronto, Ontario
        delivers the email directly
  End-to-end with Australian Addresses
    when we send to all of parliament
      from North Sydney, NSW
        delivers to the New South Wales Sen and Rep
      from Melbourne Ports, Victoria
        delivers to the Victoria Sen and Rep
  Email deliveries
    when our message has apostrophes and quotes
      keeps the apostrophes and quotes in the html version
      keeps the apostrophes and quotes in the text version
    when our message sneaks in an open-tag XSS string
      removes the tag in the text version
    when our message has newline characters
      when it completes an end-to-end send
        preserves the newlines in the message body
        verifies the sender in the message body
    with only bad addresses
      when it completes an end-to-end send
        still archives the message
    URLs in messages
      does not pass validations with a URL in the message body
      does not pass validations with a URL in the message subject
    handling disclaimers
      promoter_user.skip_disclaimer = false
        when we visit promoted_message#edit
          when we sign the message
            includes the disclaimer in the email
      promoter_user.skip_disclaimer = true
        when we visit promoted_message#edit
          when we sign the message
--- !ruby/object:OCP::WebMessage
message_type: OCP::WebMessage
created_on: &1 2022-06-07 22:24:44.245828900 Z
protocol_version: '0.1'
message_type: OCP::WebMessage
created_on: *1
protocol_version: '0.1'
recipients:
- 20192
user_id: 16972
subject: Save the whales 947
subject_two:
topic:
body: This message should skip the disclaimer
body_two:
message_uuid: 07130d1f-a3a6-456b-a790-65eaa85d52e9
shared_flg: true
archive_message_id:
promoted_message_id: 24318
conversion_id: 17694
promoter_id: 28468
allow_responses: true
verified_send: true
message_country:
always_send_ids_array: []
local_recipient_ids_array: []
recipient_ids_content_one: []
recipient_ids_content_two: []
multi_content: false
skip_disclaimer: true
            doesn't include the disclaimer in the email
  Send with Verification Emails Disabled
    to a local CustomRecipient
      completes an end-to-end send

The Fax agent
  with 14/15 sent
    send #15
      sends a fax
      send #16
        if we send a standard fax
          collates the fax instead of sending
      send #16
        if we send a batched fax
          doesn't collate
      if we turn collation off
        send #16
          doesn't collate the fax
      if we pass no_limit = true
        send #16
          doesn't collate the fax
  with 15/15 sent
    when APP_CONFIG.fax.limit = 16
      send #16
        sends a fax
        send #17
          collates the fax instead of sending
      if we turn collation off
        send #17
          doesn't collate the fax
      if we pass no_limit = true
        send #17
          doesn't collate the fax
  with 15/15 sent yesterday
    when the date changes
      send #16
        sends a fax
        the counter
          resets to 1

Multi-Content Deliveries
  The messages delivered
    when we make regular (not batched or collated) deliveries
      for WebForms
        signing the widget
          sends content_one and content_two to their respective reps
      for api WebForms
        signing the widget
          sends content_one and content_two to their respective reps
      for Email
        sends a different body and subject to recipients for content_one and content_two
      for Fax
        delivers content_two for content_two recipients
    When one method fails and a second is tried
      correctly delivers the multi_content info for the second delivery
    when we deliver through BatchSender multi_content batch sends
      delivers a batched-send with content_two content in body if recipient is content_two
    when we deliver multi_content Collated Faxes through BatchSender
      has content_two in the body if recipient is in content_two
  with overlapping multi-content Groups
    content_one: All Republicans and content_two: All Senate
      delivers content_one to Republican Senators, content_two to Democratic Senators
  The archival process
    saves multi_content archival info on the Conversion
  a multi-content message to US Congress
    with an OOD signature
      doesn't send

PhoneDeliveryEndToEnd
  Single recipient
    call failed
    call success

TwitterDeliveryEndToEnd
  Single recipient
    twitter success

VideoDeliveryEndToEnd
  Single recipient
    sent through email
    sent through email failed
    sent through webmail after email failed

The promoted/recommended messages list
  when I land on the front page via a short link
    checks the radio button for the linked message
    recommends messages with the same tags (PENDING: No reason given)

Passwords
  when an active user clicks the forgot password link
    sends a reset password email
    the email link
      shows a captcha
      passing the captcha
        links to the set password page
  a PromoterUser
    logged-in before sending the reset password email
      as regular promoter
        visiting 'Forgot Password'
          behaves like PromoterUser currently logged in
            with a valid recaptcha
              redirects to root
              doesn't send a reset password email
      as agency promoter
        visiting 'Forgot Password'
          behaves like PromoterUser currently logged in
            with a valid recaptcha
              redirects to root
              doesn't send a reset password email
    logged-in after sending the reset password email
      as regular promoter
        visiting 'Forgot Password'
          behaves like a PromoterUser who logs in after sending password reset instructions
            if we use the reset link
              shows a captcha
              if we enter the captcha
                redirects to root and displays message
      as agency promoter
        visiting 'Forgot Password'
          behaves like a PromoterUser who logs in after sending password reset instructions
            if we use the reset link
              shows a captcha
              if we enter the captcha
                redirects to root and displays message
    with promoter not logged in
      behaves like a PromoterUser password reset process
        with a valid captcha but invalid email
          has flash error for incorrect information
        with a valid recaptcha
          has message for confirmation email
          sends a reset password email
          if we ignore the email and log in again
            allows the existing password
          if we use the reset link
            shows a captcha
            if we enter the captcha
              links to the set password page
              if we supply a valid password
                and pass the captcha
                  logs us in
                  resets failed_login_count to 0
                  the new password
                    logs us in
                  the old password
                    doesn't log us in
                and fail the captcha
                  stays on the captcha page
                  the new password
                    doesn't log us in
                  if we fix the captcha and re-submit
                    logs us in
                    the new password
                      logs us in
                    the old password
                      doesn't log us in
              if we supply an invalid password
                shows a validation error
            if we fail the captcha
              stays on the captcha page
        with an invalid recaptcha
          shows a recaptcha error message
          doesn't send a reset password email
    with an existing Kindful authentication
      visiting 'Forgot Password?'
        behaves like a PromoterUser password reset process
          with a valid captcha but invalid email
            has flash error for incorrect information
          with a valid recaptcha
            has message for confirmation email
            sends a reset password email
            if we ignore the email and log in again
              allows the existing password
            if we use the reset link
              shows a captcha
              if we enter the captcha
                links to the set password page
                if we supply a valid password
                  and pass the captcha
                    logs us in
                    resets failed_login_count to 0
                    the new password
                      logs us in
                    the old password
                      doesn't log us in
                  and fail the captcha
                    stays on the captcha page
                    the new password
                      doesn't log us in
                    if we fix the captcha and re-submit
                      logs us in
                      the new password
                        logs us in
                      the old password
                        doesn't log us in
                if we supply an invalid password
                  shows a validation error
              if we fail the captcha
                stays on the captcha page
          with an invalid recaptcha
            shows a recaptcha error message
            doesn't send a reset password email

SalesForce Login
  /salesforce
    behaves like a Salesforce connected app
      when we're already logged in
        if authentication succeeds
          with an existing Salesforce Authentication
            doesn't create a new Promoter
            doesn't create a new Authentication
            overwrites the existing token
            overwrites the existing refresh_token
            overwrites the existing instance_url (FAILED - 42)
            doesn't create a new Account
            remains logged in
          the header
            should not have link "LOG OUT"
          the footer
            should not have link "LOG OUT"
      when we're not logged in
        with good oauth credentials
          if we have an existing Authentication
            with an existing Account
              and Promoter
                visit /salesforce
                  should not create an Account
                  should not create a Promoter
                  should not create an Authentication
                  should log us in (FAILED - 43)
                The promoter/salesforce page
                  with an old API 1.0 Authentication
                    shows an API 1 message (FAILED - 44)
                    shows a Synchronize button (FAILED - 45)
                  with a new API 2.0 Authentication
                    shows an API 2.0 message (FAILED - 46)
                    doesn't show a Synchronize button
                  with a successful SalesforceSynchronizeCall
                    promoter_salesforce_path
                      shows the sync (FAILED - 47)
                      doesn't say 'Sync in progress'
                    and another ongoing SalesforceSynchronizeCall
                      promoter_salesforce_path
                        says 'Sync in progress' (FAILED - 48)
                  with a failed SalesforceSynchronizeCall
                    promoter_salesforce_path
                      doesn't show the sync
                      doesn't say 'Sync in progress'
              without a Promoter
                visit /salesforce
                  should not create an Account
                  should create a Promoter (FAILED - 49)
                  should log us in (FAILED - 50)
          if we don't have an existing Authentication
            visit /salesforce
              should create an Account
              should create a Promoter (FAILED - 51)
              should create an Authentication (FAILED - 52)
              saves the token (FAILED - 53)
              saves the refresh_token (FAILED - 54)
              saves the instance_url (FAILED - 55)
              should log us in (FAILED - 56)
  /new_salesforce
    behaves like a Salesforce connected app
      when we're already logged in
        if authentication succeeds
          with an existing Salesforce Authentication
            doesn't create a new Promoter
            doesn't create a new Authentication
            overwrites the existing token
            overwrites the existing refresh_token
            overwrites the existing instance_url (FAILED - 57)
            doesn't create a new Account
            remains logged in
          the header
            should not have link "LOG OUT"
          the footer
            should not have link "LOG OUT"
      when we're not logged in
        with good oauth credentials
          if we have an existing Authentication
            with an existing Account
              and Promoter
                visit /salesforce
                  should not create an Account
                  should not create a Promoter
                  should not create an Authentication
                  should log us in (FAILED - 58)
                The promoter/salesforce page
                  with an old API 1.0 Authentication
                    shows an API 1 message (FAILED - 59)
                    shows a Synchronize button (FAILED - 60)
                  with a new API 2.0 Authentication
                    shows an API 2.0 message (FAILED - 61)
                    doesn't show a Synchronize button
                  with a successful SalesforceSynchronizeCall
                    promoter_salesforce_path
                      shows the sync (FAILED - 62)
                      doesn't say 'Sync in progress'
                    and another ongoing SalesforceSynchronizeCall
                      promoter_salesforce_path
                        says 'Sync in progress' (FAILED - 63)
                  with a failed SalesforceSynchronizeCall
                    promoter_salesforce_path
                      doesn't show the sync
                      doesn't say 'Sync in progress'
              without a Promoter
                visit /salesforce
                  should not create an Account
                  should create a Promoter (FAILED - 64)
                  should log us in (FAILED - 65)
          if we don't have an existing Authentication
            visit /salesforce
              should create an Account
              should create a Promoter (FAILED - 66)
              should create an Authentication (FAILED - 67)
              saves the token (FAILED - 68)
              saves the refresh_token (FAILED - 69)
              saves the instance_url (FAILED - 70)
              should log us in (FAILED - 71)

SalesforceSynchronizeCall
  .cutoff_id_for
    with successful and failed Syncs
      returns the cutoff_id from the last successful Sync

The Salesforce API
  standardize_string
    strips whitespace
    truncates messages at 80 characters

The Salesforce API v1
  #synchronize
    with an existing person signing a new message
      should include "success"
      should include "1 signatures, 0 new Contacts and 1 new Messages"
      should include ["003o0000009c9FoAAI", "0013000000MOzzzDDD"]
    with a new person signing an existing message
      should include "success"
      should include "1 signatures, 1 new Contacts and 0 new Messages"
      should include ["003o000000KZaaqAADsveta@oneclickpolitics.com", "a00o00000075ArsAAE"]
    with an existing person signing an existing message
      should include "success"
      should include "1 signatures, 0 new Contacts and 0 new Messages"
      should include ["003o0000009c9FoAAI", "a00o00000075ArsAAE"]
    with an existing person signing an existing message, and a new person signing a new message
      should include "success"
      should include "2 signatures, 1 new Contacts and 1 new Messages"
      should include ["003o0000009c9FoAAI", "a00o00000075ArsAAE"]
      should include ["003o000000KZaaqAADsveta@oneclickpolitics.com", "0013000000MOzzzDDD"]
    with the same person signing a new message and an old one
      should include "success"
      should include "2 signatures, 1 new Contacts and 1 new Messages"
      doesn't sync duplicate Contacts
      should include ["003o000000KZaaqAADsveta@oneclickpolitics.com", "a00o00000075ArsAAE"]
      should include ["003o000000KZaaqAADsveta@oneclickpolitics.com", "0013000000MOzzzDDD"]
    with paginated Salesforce Contacts
      should include "ldcruz@uog.com"
      should include "next@contact.com"
    when push_assocation returns 'success':false
      with an broken name signing an existing message
        should include "failure"
        should include "0 signatures, 0 new Contacts and 0 new Messages"
    when push_assocation throws an exception
      with an broken name signing an existing message
        should include "failure"
        should include "0 signatures, 0 new Contacts and 0 new Messages"

The Salesforce API v2
  #process_batch_response
    with a Contacts query
      queued
        finds the job and parses the result
      not queued
        parses the result
    with a Contacts upsert
      queued
        finds the job and parses the result
      not queued
        parses the result
  #sync
    with valid and invalid inputs
      returns Salesforce Ids for valid inputs
      returns the unsynced records
    with duplicate Email and Message fields in the same block
      doesn't upsert duplicates, but builds all needed associations
  #bulk_sync_contacts
    with Contacts
      returns a hash mapping Salesforce Ids to Message Names
    with invalid Contacts
      returns a hash mapping Salesforce Ids to Message Names
    with duplicate Contact Emails in the same block
      doesn't upsert duplicates in the same block
    with inputs longer than our block sizes
      behaves like a block API
        with an import_block_size and query_block_size
          groups imports by import_block_size and queries by query_block_size
          collects all results
  #bulk_sync_messages
    with Messages
      returns a hash mapping Salesforce Ids to Message Names
    with invalid Messages
      returns a hash mapping Salesforce Ids to Message Names
      with duplicate Message Names in the same block
        doesn't upsert duplicate Name values in the same block
    with inputs longer than our block sizes
      behaves like a block API
        with an import_block_size and query_block_size
          groups imports by import_block_size and queries by query_block_size
          collects all results
  #bulk_sync_associations
    with Associations
      returns an array of Salesforce Ids
  #make_associations
    with records and Salesforce id hashes
      creates ContactMessageAssociation join records with Salesforce ids
  #bulk_api_call
    passes the first argument as a method name to bulk_api
    passes the second argument as a list of parameters
    on a generic SalesforceException
      logs the error
    on a generic Exception
      logs the error
    on a SalesforceException: Invalid session id (InvalidSessionId)
      with one connection failure
        tries to reconnect once
      with two connection failures
        tries to reconnect once
  Authentication and tokens
    #authenticate_restforce_client
      with an @authentication_callback
        yields the callback the :token / :reborn_token
      without an @authentication_callback
        with a block
          yields the block the :token / :reborn_token
        with an @authentication
          updates @authentication.token
  Data hygeine and filtering methods
    #remove_duplicate_hashes_by_keys
      with association records
        removes duplicates
      with contact records
        removes duplicates
      with message records
        removes duplicates
    #filter_contact_records
      with an Email column
        includes the record
      without an Email column
        excludes the record
    #map_to_contact_record
      with an AdvocateProfile
        behaves like a Salesforce Contact
          has Salesforce Contact columns
      with a SenderProfile
        behaves like a Salesforce Contact
          has Salesforce Contact columns
      with a Hash
        behaves like a Salesforce Contact
          has Salesforce Contact columns
    compact_records
      removes nil columns

SalesforceListener
  process_contact_message
    when a Contact is updated
      behaves like an Advocate updater or creator
        if the AdvocateProfile exists for this PromoterUser
          with an ExternalConnection
            updates the ExternalConnection (FAILED - 72)
            behaves like an Advocate updater
              sets the AdvocateProfile fields to match the message (FAILED - 73)
              behaves like a Streaming API processor
                with a replay_id
                  returns the replay_id (FAILED - 74)
          without an ExternalConnection
            creates the ExternalConnection (FAILED - 75)
            behaves like an Advocate updater
              sets the AdvocateProfile fields to match the message (FAILED - 76)
              behaves like a Streaming API processor
                with a replay_id
                  returns the replay_id (FAILED - 77)
        if the AdvocateProfile doesn't exist
          creates an ExternalConnection (FAILED - 78)
          behaves like an Advocate creator
            creates an AdvocateProfile (FAILED - 79)
    when a Contact is deleted
      if the AdvocateProfile exists for this PromoterUser
        with an ExternalConnection
          behaves like an Advocate deleter
            removes the AdvocateProfile (FAILED - 80)
            behaves like a Streaming API processor
              with a replay_id
                returns the replay_id (FAILED - 81)
    when a Contact is created
      behaves like an Advocate updater or creator
        if the AdvocateProfile exists for this PromoterUser
          with an ExternalConnection
            updates the ExternalConnection (FAILED - 82)
            behaves like an Advocate updater
              sets the AdvocateProfile fields to match the message (FAILED - 83)
              behaves like a Streaming API processor
                with a replay_id
                  returns the replay_id (FAILED - 84)
          without an ExternalConnection
            creates the ExternalConnection (FAILED - 85)
            behaves like an Advocate updater
              sets the AdvocateProfile fields to match the message (FAILED - 86)
              behaves like a Streaming API processor
                with a replay_id
                  returns the replay_id (FAILED - 87)
        if the AdvocateProfile doesn't exist
          creates an ExternalConnection (FAILED - 88)
          behaves like an Advocate creator
            creates an AdvocateProfile (FAILED - 89)
  loop_and_listen
    if our token expires while processing messages
      refreshes it (FAILED - 90)
      stops the EM loop (FAILED - 91)
      restarts the EM loop (FAILED - 92)
      without a ListenerReplayHandler
        restarts the loop with the last replay id (FAILED - 93)
      with a ListenerReplayHandler
        restarts the loop with the ListenerReplayHandler (FAILED - 94)
      if our token expires again
        calls EM.stop again to stop the loop (FAILED - 95)

Our Schedule Demo form
  with standard Schedule Demo settings
    when we fill out the form and click send
      should not be tailored to the modal
      the email sent
        should not be nil
        should have content "First"
        should have content "Last"
        should have content "2154368031"
        should have content "Email: sveta@oneclickpolitics.com"
        should have content "My Organization"
    the honeypot field
      should be hidden in css
      when we fill it in
        should appear to have sent
        should not actually send
    when we don't enter our captcha
      and we fill in the form
        should not send an email
        should show us a failure message
        should show us the failed captcha message
      and we first visit the form
        should not show us a failure message
        should not show us the failed captcha message
        should not ask us for a valid email address

SelectedRecipient
  with a comma-delimited recipients_code
    the Conversion
      has 3 recipients
  A colon-delimited recipients_code
    the Conversion
      has 3 recipients
  2 CustomRecipients with constituency N, owned by the message creator
    sending with 'constituents_only'
      the Conversion
        has 2 recipients
  2 CustomRecipients *not* owned by the message creator
    sending with 'constituents_only'
      the Conversion
        has nil recipients
  2 locals
    sending with 'constituents_only'
      the Conversion
        has 2 recipients
  with selected_recipient_group 'AR' and constituents_only
    signing
      the Conversion
        should equal 2
        should include 20250
        should include 20265
        should not include 20276
        should not include 20294
        should not include 20309
        should not include 20324
        should not include 20339
        should not include 20354
        should not include 20369
        should not include 20384
        should not include 20399
        should not include 20414
    ...with inactive local recipients
      signing
        the Conversion
          has nil recipients
    ...followed by a recipient id
      signing
        the Conversion
          should equal 3
          should include 20446
          should include 20461
          should not include 20472
          should not include 20490
          should not include 20505
          should not include 20520
          should not include 20535
          should not include 20550
          should not include 20565
          should include 20580
          should not include 20595
          should not include 20610
    ...preceded by a recipient id
      signing
        the Conversion
          should equal 3
          should include 20628
          should include 20643
          should not include 20654
          should not include 20672
          should not include 20687
          should not include 20702
          should not include 20717
          should not include 20732
          should not include 20747
          should include 20762
          should not include 20777
          should not include 20792
  with a Governor Recipient
    the Conversion
      does have the in state governor recipient
      does not have the out state governor recipient
  with an inactive Congressman
    with code AA for All of Congress
      the Conversion
        doesn't have the inactive recipient

Signature Export to CSV
  with NoDB signatures
    the promoter pages
      selecting a start_month and end_month
        sends an email
        creates a CSV
        visiting 'CSV Exports'
          shows and links the CSV export
        the CSV
          parses as a CSV
          has a header row
          includes specified records
          excludes unspecified records
      UI Links
        when NoDBTransaction::USE_NODB_SYNCS_IN_UI is flipped to TRUE
          the reporting pages
            shows the new CSVs link in the Reporting pages
          the dashboard
            doesn't show the old CSVs link in the Promoter Sidebar

Starter plan
  if Starter plans are enabled
    an existing customer
      with a demoing Stripe subscription
        visiting the products paywall
          shows the Starter plan link
          selecting the link
            sets up the Starter plan
            cancels the Stripe subscription
            shows the dashboard
            if we click the banner
              the Products page
                should have link "enterprise"
                should not have link "solo"
                doesn't offer a 14-day trial
        with active promotions
          choosing 'solo'
            sets up the Starter plan
            de-activates all promotions except for the newest
      with an active Stripe subscription
        visiting the products paywall
          doesn't show the Starter plan link
      with no Stripe subscription
        visiting the products paywall
          shows the Starter plan link
          selecting the link
            sets up the Starter plan
            doesn't create a Stripe subscription
            shows the dashboard
    a reseller
      doesn't see the Starter plan option
    an office
      doesn't see the Starter plan option
    a proxy
      doesn't see the Starter plan option
    Plan Limitations
      limits exports to 50
      restricts custom recipients
      restricts custom widgets
      restricts state access
      on Active promotions
        with one active message
          clicking 'Resume'
            doesn't Resume
            if we switch to the 'Pro' tier
              clicking 'Resume'
                Resumes
        with no active messages
          clicking 'Resume'
            Resumes
            doesn't show the Solo limit message
  if Starter plans aren't enabled
    an existing customer
      with a demoing Stripe subscription
        visiting the products paywall
          doesn't show the Starter plan link

Sync Signatures CSVs Controller
  /index
    with a recent CSV sync
      links to the CSV
      shows the age
      if the sync is older than 30 minutes
        and newer than their last signature
          doesn't show an enabled re-sync button
          shows 'No new signatures'
        but older than their last signature
          shows an enabled re-sync button
          doesn't show 'No new signatures'
          if a new ongoing CSV sync starts
            links to the CSV
            disables the sync button
            shows an 'Updating CSV' message
    with a partial sync (with set_sync_size)
      shows the cutoff
      doesn't show 'No new signatures'
      if we're running a sync
        shows 'Signatures are still being added to your CSV'
      and another sync
        shows the new cutoff
    re-syncing a new signature
      asynchronously
        beneath LocalTransaction max_sync_size
          sync_signatures_csv
            behaves like a transaction div
              the div
                should have status 'in_progress'
                should have the uuid for an InternalApiMessage
                should start the check-status timer (globalRunningTransactions)
                should have a check-status path
                if we visit the check-path
                  returns JSON
                  shows the transaction status
          the API queue
            has an ApiAgentMessage for 'sync_signatures_csv'
          processing
            if the ApiAgent succeeds
              visiting the check-path
                the returned JSON
                  should not raise Exception
                  shows status 'success'
                  returns the sync count
              the page
                links to the CSV
                shows the age
                shows 'No new signatures'
                clicking the Download link
                  shows the Conversion
        exceeding LocalTransaction max_sync_size
          the API queue
            doesn't get an ApiAgentMessage
      synchronously
        beneath LocalTransaction max_sync_size
          the page
            links to the CSV
            shows the age
            shows 'No new signatures'
            clicking the Download link
              shows the Conversion
        exceeding LocalTransaction max_sync_size
          the page
            shows the validation error

Admin:SynchronizeCalls
  visiting /index
    with varied sync types
      behaves like a SynchronizeCalls list
        shows each included SynchronizeCall's model_type, and its status
        doesn't show SynchronizeCalls that we expect to be omitted
      dropdowns
        the 'Type' dropdown
          selecting 'NationBuilderSynchronizeCall'
            behaves like a SynchronizeCalls list
              shows each included SynchronizeCall's model_type, and its status
              doesn't show SynchronizeCalls that we expect to be omitted
          selecting 'NeonSynchronizeCall'
            behaves like a SynchronizeCalls list
              shows each included SynchronizeCall's model_type, and its status
              doesn't show SynchronizeCalls that we expect to be omitted
        the 'Status' dropdown
          selecting 'In progress'
            behaves like a SynchronizeCalls list
              shows each included SynchronizeCall's model_type, and its status
              doesn't show SynchronizeCalls that we expect to be omitted
          selecting 'success'
            behaves like a SynchronizeCalls list
              shows each included SynchronizeCall's model_type, and its status
              doesn't show SynchronizeCalls that we expect to be omitted
    with a sync that includes a start_id, end_id, or table_name
      shows the field and value
      shows the field and value
      shows the field and value
    with admin-level and promoter-level calls
      an admin-level SynchronizeCall
        is labeled and isn't indented
      a promoter-level SynchronizeCall
        links the promoter
    for ongoing syncs
      shows a 'fail' link
      clicking 'fail'
        fails the sync
    clicking 'details'
      shows the logs
      shows the extra data
      shows the promoter_user_id

VideoDeliveryTransaction
  send_video
    requires a video service send id
    with a non-rubberstamped conversion
      is invalid without an activated sender email
      is valid with an activated sender email & displays 'verified'
    with a rubberstamped conversion
      doesn't require an activated email
      passes the video_service_send_id to the send_video method
      passes the correct arguments to Notifier
      records the delivery
      doesn't send to a bad email
      email body
        renders the email
        uses https links
        with a rubberstamped conversion does not put 'verified' in the email
        the disclaimer
          renders the disclaimer when skip_disclaimer is false
          does not render the disclaimer when skip_disclaimer is true
        the 'Constituent' tag
          with a local sender
            includes the 'Constituent' tag
          with a non-local sender
            doesn't include the 'Constituent' tag
      with 1 recipient having 2 emails
        when the first email delivers
          doesn't try the second email
        when the first email raises an email exception
          tries the second email
        when the first email raises a non-email exception
          sends an agent alert email and doesn't try the second email
      with 1 recipient having 1 email and 1 web_mail_address
        when the email delivers
          doesn't try the WebForm
        when the email raises an exception
          tries the webform
      with 1 recipient having 1 web_mail_address
        creates a service delivery (FAILED - 96)
        doesn't publish back to the receiver
        and use_web_form_api == true
          when the request succeeds
            uses one-scrape
            sets fake_agent_message.body to a string including the https link and disclaimer
            marks the VideoServiceDelivery as having used one-scrape
          when the request times out
            sends a notification email
            still returns a status message
        but no web form steps
          fails gracefully
        which is undeliverable
          doesn't create a service delivery
      with empty video_service_send.recipients_json
        fails gracefully

Video Messaging
  Widget Interaction
    the guide page
      links to the new video page
      displays the video_text
      shows 30 second time limit default
    the new video page
      displays the recorder element
      includes time limit in recorder element
      displays the check box for opt in
      displays the customized video opt in text
      checks the video opt in by default
      when message is set to canada
        does not check video opt in by default
    the show page
      displays the video embed
  Adding video_action_flg to a widget
    with an admin promoter
      behaves like successfully seeing video_action_flg
        shows video_messaging_flg on messages new page
        shows video_messaging_flg on messages edit page
    with a promoter with video_action_flg true
      behaves like successfully seeing video_action_flg
        shows video_messaging_flg on messages new page
        shows video_messaging_flg on messages edit page
    with a promoter with video_action_flg false
      doesn't show video_messaging_flg on messages new page
      doesn't show video_messaging_flg on messages edit page
  VideoServiceSends
    with a promoter with video_messaging_flg false
      the sidebar
        does not display the Advocate Videos link
    with an admin promoter
      the sidebar
        behaves like shows Videos Link in sidebar
          displays the Advocate Videos link
    with a promoter with video_messaging_flg true
      the sidebar
        behaves like shows Videos Link in sidebar
          displays the Advocate Videos link
      the promoter's video queue
        displays the video embeds, statuses, and campaign titles
        displays an opted-in sender's information
        doesn't display an opted-out sender's information
        displays the correct videos when 'ACCEPTED' filter is applied

The One-Touch Test Send
  when we click 'SEND A TEST MESSAGE'
    should have content "Not every matter"
    when we omit phone
      should have content "Status: [:sent"
    when we fill out all fields
      should have content "Status: [:sent"

One Click Widgets
  with NoDB signatures enabled
    with verification off
      signing
        creates a NoDB signature
        the NoDB signature
          has Authenticated=''
        clicking 'Submit'
          sends a verification email
          after verifying by email
            the NoDB Signature
              has Authenticated='yes'
    with two messages
      signing and submitting message one
        creates one signature
        then signing message two
          creates another signature
          NoDB Signature one
            doesn't change
          NoDB Signature two
            shows new signature info

Photos
  a widget thumbnail
    for a recipient with .photo_path
      uses the .photo_path on S3
    for a recipient with .full_photo_url
      uses the full url

A custom recipient
  for its User
    is listable for its user
    can be set to local constituency
    can be set to state constituency
    has the deliverable flag set to true
    has an associated district address
    on custom_recipients page
      renders the custom recipients page
      the Edit Campaign Targets page
        behaves like a paginator with search
          has pagination buttons and a search box
          shows the current page and total
          searching by name for Boston CRs
            shows the correct page total
            behaves like a paginator
              advances and returns
          searching by email for Los Angeles CRs
            shows the correct page total
            behaves like a paginator
              advances and returns
      the Manage Custom Targets page
        behaves like a paginator with search
          has pagination buttons and a search box
          shows the current page and total
          searching by name for Boston CRs
            shows the correct page total
            behaves like a paginator
              advances and returns
          searching by email for Los Angeles CRs
            shows the correct page total
            behaves like a paginator
              advances and returns
      creating a new valid recipient
        saves recipient
      creating a new valid recipient with out the custom_recipient add on
        should have content "Feature not available at for your product tier"
      editing CRs
        selecting 'City' from the dropdown
          shows the dropdown with 'City' selected
          updates the CR to Local
      deleting users
        has recipient on recipient list
        has the promoter_custom_recipients assocation
        from custom_recipient
          removes recipient from recipient list
          doesn't raise 404
          removes recipient from custom recipient list
          removes assocation with promoter_user
      creating a new invalid recipient
        flashes error
      back to message
        should have content "Your Custom Targets"
    for National constituencies
      doesn't offer a selector dropdown
  for an Admin
    will set to National constituency (PENDING: No reason given)
    when we enter a National CustomRecipient
      the Promoter's CustomRecipients
        should eq 1
      the CustomRecipient
        constituency
          should eq "N"
  for another User
    cannot be deleted by other users
    cannot be updated by other users
    new product tiers
      with pro product
        limits custom recipients to 21

CustomRecipient
  #list_by_user
    :per_page => 10
      size
        should eq 10
    :per_page => 10, :page => 2
      should eq #<CustomRecipient id: 21113, name: "Miss 13", model_type: "CustomRecipient", description: nil, lock_v... nil, full_photo_url: nil, scwc_office_code: nil, cicero_official_id: nil, cicero_committee_id: nil>
    :order_by => 'name'
      name
        should eq "Archibald Aersatz"
    :order_by => 'email'
      email
        should eq "adonibel@example.com"
    :search => 'doni'
      size
        should eq 1
      first
        should eq #<CustomRecipient id: 21214, name: "Donnibel Doppleganger", model_type: "CustomRecipient", descriptio... nil, full_photo_url: nil, scwc_office_code: nil, cicero_official_id: nil, cicero_committee_id: nil>

Custom widget
  widget colors
    background color
      shows defualt background color
      shows updated background color
    button color
      shows defualt button color
      shows updated button color
    font color
      shows defualt subject color
      shows defualt font color
      shows updated and subject color
  if per-message is allowed
    the 'All Campaigns / This Campaign' switch
      is present
    if we switch to per-message
      sets the switch to 'This campaign'
      the swatches
        show the message colors
        override the promoter's colors
      the widget preview
        shows the message colors
      the fluid widget
        for this message
          shows the message's custom background
          shows the message's custom font color
          shows the message's custom button color
        for another message from this promoter
          shows the promoter's background
          shows the promoter's font color
          shows the promoter's button color

The scalable Widget
  when the background is set to 'transparent'
    the fluid widget
      should be transparent
    the mobile widget
      should be transparent
  when the font is set to non-Google 'Times New Roman'
    the fluid widget
      should not download 'Times New Roman' from google
      applies 'Times New Roman'
  when the font is set to Google 'Roboto Condensed'
    the fluid widget
      downloads 'Roboto Condensed' from google
      applies 'Roboto Condensed'

Selection Tree
  should have content "Targeting"
  #select_recipients
    when we have an inactive congressman
      send to All of Congress
        should not include "21216"
    States tab
      with unlimited state access
        should have link "Arkansas"
        should have link "South Carolina"
        should have link "West Virginia"
      with multiple state access
        should have content "Add a state"
        with three states
          should not have content "Add a state"
        with two states
          should have link "arkansas"
          should have link "california"
        with two multi-word states
          should have link "new jersey"
          should have link "new mexico"
          escapes New+Mexico with a plus
          escapes New+Jersey with a plus
        with two duplicate states
          should have link "new jersey"
          escapes New+Jersey with a plus
        with states 'newjersey' and NM
          should have link "new jersey"
          should have link "new mexico"
          escapes New+Jersey with a plus
          escapes New+Mexico with a plus
        with single state 'newjersey'
          should have link "new jersey"
          links to &state=newjersey
        with states 'colorado' and 'newjersey'
          should have link "new jersey"
          should have link "colorado"
          escapes New+Jersey with a plus
          links to colorado
          doesn't link accidentally to other states
      with single state access due to agency_state_id being set
        should not have content "Add a state"
        should have link "California"
        should not have link "New Jersey"
        should not have link "New Mexico"
    city councils tab
      for Canadian messages
        doesn't appear
      for Australian messages
        doesn't appear
      for US messages
        appears
      visiting
        lists cities with CityCouncilDistrict records and recipients
        doesn't list cities without CityCouncilDistrict records and recipients
        clicking on a city
          lists Councilmembers for that city
          doesn't list Councilmembers for another city
  Selection error messages
    should show an error message when adding the same recipient
  Selection with flaggable recipients
    for the US
      a Congressional rep
        isn't flaggable
      a state rep
        behaves like a flaggable recipient
          has a flag link
          doesn't have a remove flag link
          when we flag a recipient
            if we haven't reached the per-message limit
              adds its id to the flagged list
              has a remove flag link
            if we've reached the per-message limit
              doesn't add its id to the flagged list
              doesn't have a remove flag link
          a flagged Recipient
            has a remove flag link
            when we remove flag it
              removes its id from the flagged list
            when we remove the recipient
              removes its id from the flagged list
      a Custom Recipient
        behaves like a flaggable recipient
          has a flag link
          doesn't have a remove flag link
          when we flag a recipient
            if we haven't reached the per-message limit
              adds its id to the flagged list
              has a remove flag link
            if we've reached the per-message limit
              doesn't add its id to the flagged list
              doesn't have a remove flag link
          a flagged Recipient
            has a remove flag link
            when we remove flag it
              removes its id from the flagged list
            when we remove the recipient
              removes its id from the flagged list
      a committee
        isn't flaggable
      a preselected group
        isn't flaggable
    for Canada
      a rep
        behaves like a flaggable recipient
          has a flag link
          doesn't have a remove flag link
          when we flag a recipient
            if we haven't reached the per-message limit
              adds its id to the flagged list
              has a remove flag link
            if we've reached the per-message limit
              doesn't add its id to the flagged list
              doesn't have a remove flag link
          a flagged Recipient
            has a remove flag link
            when we remove flag it
              removes its id from the flagged list
            when we remove the recipient
              removes its id from the flagged list
    for Australia
      a rep
        behaves like a flaggable recipient
          has a flag link
          doesn't have a remove flag link
          when we flag a recipient
            if we haven't reached the per-message limit
              adds its id to the flagged list
              has a remove flag link
            if we've reached the per-message limit
              doesn't add its id to the flagged list (FAILED - 97)
              doesn't have a remove flag link
          a flagged Recipient
            has a remove flag link
            when we remove flag it
              removes its id from the flagged list
            when we remove the recipient
              removes its id from the flagged list

Predefined Groups
  multi_content
    with 'All Republicans' and a lone recipient
      displays an error message with the relevant content_name on clicking the lone recipient again
      behaves like selector allowing a commingled group and individuals
        the selector
          shows 'All Republicans'
          shows the lone recipient
        removing the group
          shows the lone recipient
          doesn't show 'All Republicans'
          sending
            delivers to the lone recipient
            doesn't deliver to the group
        removing the lone recipient
          doesn't show the lone recipient
          shows 'All Republicans'
          sending
            doesn't deliver to the lone recipient
            delivers to the group
        adding another group
          shows the lone recipient
          still shows the existing group
          shows the new group
          sending
            delivers to the lone recipient
            still delivers to the old group
            delivers to the new group
        sending
          delivers to the group and to the lone recipient
      the content_two selector
        doesn't display 'All Republicans' in 'Selected Targets'
        displays an error message on clicking 'Send to All Republicans'
        displays an error message with the relevant content_name on clicking the lone recipient again
      adding a group
        assigns the correct content_number
    multi-content Municipalities
      Content One
        behaves like Municipalities selector
          the City selector
            has Content links
            clicking on a city
              the Council page
                has Content links
                lists Councilmembers for that city
                doesn't list Councilmembers for another city
                shows targets already on that content
                adds targets
      Content Two
        behaves like Municipalities selector
          the City selector
            has Content links
            clicking on a city
              the Council page
                has Content links
                lists Councilmembers for that city
                doesn't list Councilmembers for another city
                shows targets already on that content
                adds targets
  with 'All Republicans' and a lone recipient
    behaves like selector allowing a commingled group and individuals
      the selector
        shows 'All Republicans'
        shows the lone recipient
      removing the group
        shows the lone recipient
        doesn't show 'All Republicans'
        sending
          delivers to the lone recipient
          doesn't deliver to the group
      removing the lone recipient
        doesn't show the lone recipient
        shows 'All Republicans'
        sending
          doesn't deliver to the lone recipient
          delivers to the group
      adding another group
        shows the lone recipient
        still shows the existing group
        shows the new group
        sending
          delivers to the lone recipient
          still delivers to the old group
          delivers to the new group
      sending
        delivers to the group and to the lone recipient
  with WI Republicans and a lone recipient
    behaves like selector allowing a commingled group and individuals
      the selector
        shows 'All Republicans'
        shows the lone recipient
      removing the group
        shows the lone recipient
        doesn't show 'All Republicans'
        sending
          delivers to the lone recipient
          doesn't deliver to the group
      removing the lone recipient
        doesn't show the lone recipient
        shows 'All Republicans'
        sending
          doesn't deliver to the lone recipient
          delivers to the group
      adding another group
        shows the lone recipient
        still shows the existing group
        shows the new group
        sending
          delivers to the lone recipient
          still delivers to the old group
          delivers to the new group
      sending
        delivers to the group and to the lone recipient
  with Australian House and a lone recipient
    behaves like selector allowing a commingled group and individuals
      the selector
        shows 'All Republicans'
        shows the lone recipient
      removing the group
        shows the lone recipient
        doesn't show 'All Republicans'
        sending
          delivers to the lone recipient
          doesn't deliver to the group
      removing the lone recipient
        doesn't show the lone recipient
        shows 'All Republicans'
        sending
          doesn't deliver to the lone recipient
          delivers to the group
      adding another group
        shows the lone recipient
        still shows the existing group
        shows the new group
        sending
          delivers to the lone recipient
          still delivers to the old group
          delivers to the new group
      sending
        delivers to the group and to the lone recipient
  with Australian State Council and a lone recipient outside of AU
    behaves like selector allowing a commingled group and individuals
      the selector
        shows 'All Republicans'
        shows the lone recipient
      removing the group
        shows the lone recipient
        doesn't show 'All Republicans'
        sending
          delivers to the lone recipient
          doesn't deliver to the group
      removing the lone recipient
        doesn't show the lone recipient
        shows 'All Republicans'
        sending
          doesn't deliver to the lone recipient
          delivers to the group
      adding another group
        shows the lone recipient
        still shows the existing group
        shows the new group
        sending
          delivers to the lone recipient
          still delivers to the old group
          delivers to the new group
      sending
        delivers to the group and to the lone recipient
  with Canadian Parliament and a lone recipient outside of CA
    behaves like selector allowing a commingled group and individuals
      the selector
        shows 'All Republicans'
        shows the lone recipient
      removing the group
        shows the lone recipient
        doesn't show 'All Republicans'
        sending
          delivers to the lone recipient
          doesn't deliver to the group
      removing the lone recipient
        doesn't show the lone recipient
        shows 'All Republicans'
        sending
          doesn't deliver to the lone recipient
          delivers to the group
      adding another group
        shows the lone recipient
        still shows the existing group
        shows the new group
        sending
          delivers to the lone recipient
          still delivers to the old group
          delivers to the new group
      sending
        delivers to the group and to the lone recipient
  with Canadian Province BC and a lone recipient outside of BC
    behaves like selector allowing a commingled group and individuals
      the selector
        shows 'All Republicans'
        shows the lone recipient
      removing the group
        shows the lone recipient
        doesn't show 'All Republicans'
        sending
          delivers to the lone recipient
          doesn't deliver to the group
      removing the lone recipient
        doesn't show the lone recipient
        shows 'All Republicans'
        sending
          doesn't deliver to the lone recipient
          delivers to the group
      adding another group
        shows the lone recipient
        still shows the existing group
        shows the new group
        sending
          delivers to the lone recipient
          still delivers to the old group
          delivers to the new group
      sending
        delivers to the group and to the lone recipient
  with 'All Republicans' AND WI Republicans
    shows both groups
    can remove just one group
    adding the same group again
      isn't allowed
      displays an error message

Our Sending System
  when there's no existing Account with our email
    when we complete the send form
      sends us an activation email
      creates a new Account with a new SenderProfile
      doesn't send the message right away
  when there is an existing account with an email
    when the Account status is BANNED
      when we complete the send form
        does not send any email
        does not create a new Account or SenderProfile
        doesn't send the message right away
    When the Account status is NEW
      when we have an existing SenderProfile
        when we complete the send form
          sends an Activation email
          creates a new SenderProfile
      when we're lacking a SenderProfile
        when we complete the send form
          does create a new SenderProfile
          doesn't send the message right away
    When the Account status is unsubscribe
      when we have an existing SenderProfile
        when we complete the send form
          doesn't send an Activation email
    When the Account status is CONFIRMED
      when we have an existing SenderProfile
        when we complete the send form
          sends a Permission email
          doesn't offer the act/sharing link within the email
          does not create a new Account
          doesn't send the message right away
      when we're lacking a SenderProfile
        when we complete the send form
          sends a Permission email
          does create a new SenderProfile
          doesn't send the message right away
    When the Account status is ACTIVE
      when we have an existing SenderProfile
        when we complete the send form
          sends a Permission email
          doesn't offer the act/sharing link within the email
          does not create a new Account
          doesn't send the message right away
      when we're lacking a SenderProfile
        when we complete the send form
          sends a Permission email
          does create a new SenderProfile
          doesn't send the message right away

Our activation link
  for an ad-hoc message
    changes a NEW Account into an ACTIVE or CONFIRMED Account
    when clicked
      should have content "Thank You"
      shows sharing links
      forgoes setting up a password
      doesn't show a link back to the promoter
      sends the message
      sends a follow-up email
  for a PromotedMessage
    changes a NEW Account into an ACTIVE or CONFIRMED Account
    when clicked
      should have content "Thank You"
      shows sharing links
      forgoes setting up a password
      shows a link back to the promoter
      offers the descriptive link
      sends the message
      sends a follow-up email

Our permission links
  allows a message to send from a CONFIRMED or ACTIVE Account
  sends a follow up email
  clicking 'Unsubscribe'
    unsubscribes

SenderProfile
  should respond to #country
  affords room for canadian postal codes
  maps to a Canadian province
  geocodes correctly
  when the country is 'Canada'
    for a variety of Canadian postal codes
      is valid
  when the country is not 'Canada'
    for a variety of Canadian postal codes
      is valid
  when it's flagged as canadian
    validates canadian postal codes (PENDING: Not yet implemented)
    it maps postal codes to canadian provinces (PENDING: Not yet implemented)

SenderProfile
  should respond to #country
  affords room for Australian postal codes
  maps to a Australian province
  geocodes correctly
  when the country is 'Australia'
    for a variety of Australian postal codes
      is valid
  when the country is lowercase 'australia'
    for a variety of Australian postal codes
      is valid
  when the country is not 'Australia'
    for a variety of Australian postal codes
      is not valid
  when it's flagged as canadian
    validates canadian postal codes (PENDING: Not yet implemented)
    it maps postal codes to canadian provinces (PENDING: Not yet implemented)

UsStates
  should respond to #country
  should eq 5

UsStates
  should respond to #country
  should eq 6

Recipient
  for Canada
    should respond to #country
    should eq 5
  for Australia
    should respond to #country
    should eq 6
  for lowercase 'australia'
    should respond to #country
    should eq 6

PromotedMessage
  should respond to #country

Canadian PromoterUsers
  as a Promoter
    we can flag a message as Canadian
      should be valid
      country
        should eq "Canada"
      when we create a local Toronto, Ontario CustomRecipient
        city
          should eq "Toronto"
        constituency
          should eq "L"
        state
          should eq "CA-ON"

Australian PromoterUsers
  as a Promoter
    we can flag a message as Australian
      should be valid
      country
        should eq "australia"
      when we create a local NSW, Australian CustomRecipient
        city
          should eq "Sydney"
        constituency
          should eq "L"
        state
          should eq "AU-NSW"

Multi-Content Signatures
  Signing the widget
    the widget page 2
      shows a box of content_one recipients
      shows a separate box of content_two recipients
      shows body and body_two
      editing body_two
        with obscenity
          shows a validation message
        with a valid body_two
          submits and records the new body_two
    clicking 'Submit'
      the Conversion
        includes the multi_content subjects and bodycachd
        assigns expanded and always-send recipients
        assigns content_one recipients
        assigns content_two recipients
  with Groups assigned to content_one and content_two
    the Conversion
      .recipient_ids_expanded_content_one
        includes overlapping content_two recipients
        excludes recipients not on content_one
      .recipient_ids_expanded_content_two
        includes content_two recipients
        excludes overlapping content_one recipients

One Click Widgets
  the widget
    Step details, specific to AU and CA
      Step 2
        with AU recipients
          with cicero_code
            shows AU house of representatives recipients
            shows AU senate recipients
            shows AU state council recipients
            shows AU state assembly recipients
          without cicero_code
            doesn't show AU house of representatives recipients
            doesn't show AU senate recipients
            doesn't show AU state council recipients
            doesn't show AU state assembly recipients
        with CA recipients
          with cicero_code
            shows CA house of representatives recipients
            shows CA senate recipients
            shows CA state assembly recipients
          without cicero_code
            doesn't show CA house of representatives recipients
            doesn't show CA senate recipients
            doesn't show CA state assembly recipients

One Click Widgets
  Step 1
    email validation failures
      email address that has special characters in the email name of the address
        should prompt for valid email
      email address that has special characters in the domain head of the address
        should prompt for valid email
      email address that has special characters in the top-level domain of the address
        should prompt for valid email
      email address using a 1-character top level domain
        should prompt for valid email
      email address using a top level domain greater than 4 characters
        should prompt for valid email
      email address with no dot in the domain
        should prompt for valid email

One Click Widgets
  the widget
    The widget flows
      with the email_action_flg == false
        doesn't recalculate recipients
        Step 3
          shows the phone
      with social_action_flg == false
        doesn't recalculate recipients
        Step 3
          shows the phone
      with phone_action_flg == false
        with phone_required
          Step 1
            validates 'phone'
        without phone_required
          Step 1
            doesn't show a phone field
            doesn't validate phone
          Step 3
            doesn't show call controls
      when promoted_message.skip_second_page? is true
        Finishing Step 1
          doesn't recalculate recipients
          shows Step 3 with the call link
      with video_action_flg == true
        with an existing video
          should show a thank you message instead of the link
        Finishing Step 1
          doesn't recalculate recipients
          shows Step 3 with the video message link
      with video_action_flg == false
        Finishing Step 1
          shows Step 3 without the video message link
      when promoted_message.skip_second_page? is false
        with an existing video
          should show a thank you message instead of the link
    Kiosk mode
      if kiosk-mode is enabled
        if we sign once
          creates a first Conversion
          and reload
            clears the fields
            signing again
              creates a second Conversion
        with a logged-in Account
          clears the fields
    Step details
      Step 1
        with a logged-in current_user
          fills in email
        if we fill the honeypot field
          shows a false success page
          doesn't record or geocode Sender data
        custom fields
          with unrequired custom field 'Town'
            should not eq "required"
            signing without 'Town'
              succeeds
              should eq nil
          with required custom field 'Town'
            should eq "required"
            signing without 'Town'
              requires Validation
              adding 'Town'
                succeeds
        the onesig/oneclick parameter from emailed links
          is present
        the external_id parameter from emailed links
          is present
          signing
            attaches the external_id to our SenderProfile
        allowing opt outs
          should be checked
          if we sign
            opts in
          if message set to canada do not precheck the opt in
            should not be checked
          if we fail validation
            should be checked
          if we uncheck and sign
            doesn't opt in
          if we uncheck and fail validation
            should not be checked
          if we add custom opt in text
            shows custom opt in text
          if we add custom opt in text that is too short
            shows error that text is too short
          if custom opt in text is nil
            should be valid
          if custom opt in text is nil
            should be valid
        not allowing opt outs
          if we sign
            opts in
        with international_signatures turned on
          saves SenderProfile country
          saves a SenderProfile's country as nil when user chooses United States
          returns a zip error if the zip is not formatted for the country
          displays Zip/Postcode for zip field
        with a sessioned SenderProfile
          does not have a country selector
          fills out the email
          upon making address changes
            signing
              advances to Step 2
              doesn't create a new SenderProfile
              re-geocodes
              changes the reps
              opts in
          without making address changes
            signing
              advances to Step 2
              doesn't create a new SenderProfile
              doesn't re-geocode
              doesn't change the reps
        if we visit three times
          records one Visit
      Step 2
        without a loaded SenderProfile
          reverts to Step 1
        with in- and out- of district custom recipients
          with :constituents_only enabled
            the Page
              shows the in-district image link
              doesn't show out-of-district reps
            clicking 'Submit'
              the Conversion
                records in-district reps for email/fax
                records in-district reps for social/phone
          with :constituents_only disabled
            the Page
              shows the in-district image link
              shows out-of-district reps
            clicking 'Submit'
              the Conversion
                records all reps for email/fax
                records in-district reps for social/phone
        with a loaded SenderProfile
          has a 'Submit' button
          editing and tripping the profanity filter
            shows a validation message
            doesn't advance to Step 3
          making a valid edit
            saves the valid edit on the Conversion
          with in- and out- of district recipients
            making a valid edit
              saves the valid edit on the Conversion
            the Conversion
              records all reps for email/fax
              records in-district reps for social/phone
            the Page
              shows the in-district image link
              shows out-of-district reps
              shows reps title
            without verification
              submitting
                rubberstamps
            clicking 'Submit'
              advances to Stage 3
              delivers conventional messages
              if we 'Submit' twice
                advances to Stage 3
                doesn't deliver conventional messages twice
      Step 3
        with custom step 3 subtitle (phone_recipients_text)
          displays custom text
        with recipients and phone action only
          displays phone only default step 3 subtitle text
        with recipients and phone and video actions
          displays phone and video default step 3 subtitle text
        with recipients and video action only
          displays phone and video default step 3 subtitle text
        with petition mode and video action only
          no-recipient video default step 3 subtitle text
        with no recipients and phone only
          displays default step 3 subtitle share text
        with twitter action, no video, no phone
          on a survey campaign
            displays default step 3 share text
          on a campaign with targets
            displays tweet step 3 subtitle share text

One Click Widgets
  the widget
    The widget flows
      without social action
        Step 3
          does not allow Twitter posts
      with only social actions
        Step 3
          allows Twitter posts

Signing and Submitting
  with no recipients
    adds a .comment to the Conversion

One Click Widgets
  Surveys
    with require_address = false
      Signing the survey first
        then signing a non-survey
          updates the SenderProfile
        then clearing the session
          then signing a non-survey
            creates a second SenderProfile
      Signing the non-survey first
        then signing the survey
          updates the SenderProfile
        then clearing the session
          then signing the survey
            creates a second SenderProfile
    with require_address = false
      doesn't show the address fields
      Step 3
        doesn't show call controls
    with zip_only = true
      only shows zip
      Step 3
        doesn't show call controls
      with an existing SenderProfile
        creates a new SenderProfile
    with require_phone = false and phone_action_flg = true
      doesn't show the address or phone fields
      Step 3
        doesn't show call controls
    with require_address = true
      Step 3
        doesn't show call controls
    when we require zips only
      via widget
        records a SenderProfile
        associates the Conversion with its Profile
    when we do not require an address
      missing name
        via widget
          doesn't record a Conversion
          doesn't record a SenderProfile
          prints a validation message
        via send form
          doesn't record a Conversion
          doesn't record a SenderProfile
          prints a validation message
      including a name
        via widget
          records a SenderProfile
          associates the Conversion with its Profile
  NON-Surveys
    missing line1
      doesn't record a Conversion
      doesn't record a SenderProfile
      prints a validation message
    missing city
      doesn't record a Conversion
      doesn't record a SenderProfile
      prints a validation message
    missing zip
      via widget
        doesn't record a Conversion
        doesn't record a SenderProfile
        prints a validation message
      via message form
        doesn't record a Conversion
        doesn't record a SenderProfile
        prints a validation message
    with all fields
      via widget
        records a SenderProfile
        associates the Conversion with its Profile
      via message form
        records a SenderProfile
        associates the Conversion with its Profile

Sending with verification emails off
  with permission/verification disabled
    shows the third page
    doesn't send a verification email
    proceeds to the dispatch queue

Stats and counts
  when we mix :permitted and :rubberstamped Conversions
    PromoterUser
      promoter_user#completed_sends_this_month
        should == 5
      promoter_user#sends_last_7_days
        should == 3
      promoter_user#count_sends
        size
          should == 3
      promoter_user#nation_builder_export
        size
          should eq 3
      promoter_user#neon_export
        size
          should eq 3
    PromotedMessage
      conversions_all_time
        should eq 0
      conversions_all_time(:include_unpermitted => true)
        should eq 1
      #sends_all_time
        should eq 0
      #sends_all_time(:include_unpermitted => true)
        should eq 1
    Conversion
      #sends_all_time
        should eq 4
      #sends_all_time(:include_unpermitted => true)
        should eq 5

The PromotedMessage edit pages
  when email verification is on
    lets us turn email verification off
  when email verification is off
    allow us to turn email verification back on
  with APP_CONFIG.always_disable_verifications = true
    the Message edit page
      doesn't show the verifications selector
    even if a message has verifications on
      signing
        shows the third page
        doesn't send a verification email
        proceeds to the dispatch queue

Our Message Processing security
  Isn't susceptible to YAML exploits

Promoter::MessagesHelper
  correctly returns display_acp_name

Admin::DeliveryDataHelper
  #conversion_status(conversion)
    finished conversions
      for a conversion that is done, no targets
        should return 'DONE, NO TARGETS'
      for a conversion that is done, all failed
        should return 'DONE, ALL FAILED'
      for a conversion that is done, some failed
        should return 'DONE, SOME FAILED'
      for a conversion that is finished
        should return 'FINISHED'
    queued, not finished conversions
      for a conversion that is stale
        should return 'STALE'
      for a conversion that is ongoing
        should return 'ONGOING'
    invalid conversions (never queued)
      for a conversion that is not verified
        should return 'NOT VERIFIED'
      for a conversion that is not submitted
        should return 'NOT SUBMITTED'
      for a conversion that is not staged
        should return 'NOT STAGED'
      for a conversion with no recipients
        should return 'NO RECIPIENTS'
  recipient_name_or_id
    for a recipient without a first name
      should return the id as a string
    for a recipient without a last name
      should return the id as a string
    for a recipient with a first and last name
      should return a string with the first and last name

Admin::PromoterUsersHelper
  agency_status
    for an Agency
      should return Agency
    for an Office
      should return Office
    for a Proxy User
      should return an empty string
    for a standard Promoter
      should return an empty string
  promoter_user_type_is_standard?
    for a standard promoter
      should return true
    for a non-standard promoter
      should return false
  promoter_user_change_to_agency_string
    for an Agency
      should return string for agencies
    for an Office
      should return string for offices
    for a proxy user
      should return string for proxy user promoter
    for a standard Promoter
      should return string for normal promoters
    for a Promoter with an unidentifiable type
      should return string when promoter user type cannot be verified
  proxy_status
    for a proxy user
      should return Proxy User string
    for a non proxy user
      should return nil
  twitter_enabled_for_promoter?
    when enabled globally (global override) is on
      should return true
    when enabled globally (global override) is off
      should return true only for non-blacklisted promoters
    when the app switch does not exist
      returns false
  twitter_enabled?
    while enabled is on
      should return true
    while enabled is off
      should return false
  twitter_enabled_globally?
    when enabled globally (global override) is on
      should return true
    when enabled globally (global override) is off
      should return false

ApplicationHelper
  call_or_body
    with <p> tags in a call to action
      should not include "<p>"
      call_or_body :allow_tags => true
        should include "<p>"
  display_recipient_full_name
    correctly returns with comma in name
    correctly returns with no comma in name
    returns blank string if recipient_name nil
  convert_s3_link_to_cdn
    on environment other than production
      does not change host domain
    on production
      with main host url
        changes the main host to our CDN
      with alt host url
        changes the alt host to our CDN

MessagesHelper
  two_col_cta_class_for_message
    for a promoter with a custom campaign image
#<ImageUploader:0x0000001230c200 @model=#<PromotedMessage id: 25111, message_id: nil, promoted_from: "2022-06-07 21:09:01", promoted_by: nil, created_at: "2022-06-07 23:07:52", updated_at: "2022-06-07 23:07:52", creator_id: nil, goal: nil, front_page_flg: nil, external_message_id: "1930", uuid: nil, bodycachd: "From blue baleena to the mighty Melvilleian white, ...", subject: "Save the whales 1563", topic: "Animals", total_cnt: nil, processed_cnt: nil, shared_flg: true, require_address: true, require_zip_only: false, require_phone: false, call_to_action: "Save the Whales", constituents_only: false, editable_widgets: true, widget_height: nil, widget_width: nil, country: nil, enable_comments_flg: false, hosted_at_url: nil, internal_campaign_name: "Save the Whales 1875", alternate_delivery_header: nil, donation_url: nil, widget_redirect: false, remove_fb_link: nil, disable_email_verifications: false, custom_share_url: nil, allow_opting_out: false, recipients_text: nil, banner: nil, image: nil, model_type: nil, quorum_edit_token: nil, built_in_image: nil, custom_field_ids: nil, custom_fields_json: nil, call_sheet: nil, phone_recipients_text: nil, widget_font_family: nil, widget_background: "#0E0A3C", widget_button: "#FF6300", widget_font: "#FFFFFF", custom_widget_flg: true, tweet_text: nil, socmed_recipients_text: nil, socmed_link: nil, share_tweet_text: nil, share_tweet_via: nil, share_facebook_text: nil, custom_campaign_image: nil, recorded_greeting: nil, oneclick_recipients_text: nil, oneclick_title: nil, facebook_text: nil, recorded_greeting_sid: nil, twitter_activity: 0, call_activity: 0, email_activity: 0, total_activity: 0, email_action_flg: true, social_action_flg: true, phone_action_flg: true, conversion_activity: 0, international_signatures: false, campaign_page_title: nil, campaign_page_template: nil, video_action_flg: false, draft_kings_photo_campaign: false, show_identity: true, show_counter: true, altstyles: false, video_activity: 0, opt_in_text: nil, multi_content: false, disable_email_verifications_last_switched: "2022-06-07 23:07:52", kiosk_mode: false, show_actions_progress: true, video_text: nil, bodycachd_two: nil, subject_two: nil, content_one_name: nil, content_two_name: nil, video_opt_in_text: nil, cwc_campaign_id: "756e370e972cbce2556bd02374bd165d5b49ca0adbb3763cfaa...", disabled: false, whitelisted_widget_host: nil>, @mounted_as=:custom_campaign_image, @storage=#<CarrierWave::Storage::File:0x00000011e97800 @uploader=#<ImageUploader:0x0000001230c200 ...>>>
true
      should return ocp-cta string
    for a promoter with a selected campaign image
      should return ocp-cta string
    for a promoter with no campaign image
      should return ocp-cta-no-image string

PaginationHelper
  next_page_available?
    should return true when page is less than max pages
    should return false when page is not less than max pages
  previous_page_available?
    should return true when page is greater than 1
    should return false when page is 1

Promoter::TextMessageHelper
  text_code
    with non adult keyword promoter
      returns non-adult text number
    with adult keyword promoter
      returns adult text number
    with user that does not use ez texting text url
      returns adult text number
  at_keyword_limit?
    should return true when promoter user has keyword count equal to their limit
    should return true when promoter user has keyword count greater than their limit
    should return false when promoter user has keyword count lesser than their limit
  delivery_time_in_est
    should return properly formatted text message delivery time in EST timezone
    with invalid params
      should return nil when time_in_est is not present

Promoter::MessagesHelper
  returns lower_house_title
  returns upper_senate_title
  returns select_upper_recipients_text
  returns choose_state_text
  twitter_enabled_for_promoter?
    when the app switch exists
      returns true for authorized users
      returns false for unauthorized users
    when the app switch does not exist
      returns false
  state_selector_array_for_campaign
    when the promoted message targets the United States
      should return state hash for US state abbreviations
    when the promoted message targets Canada
      should return state hash for CA state abbreviations
    when the promoted message targets Australia
      should return state hash for AU state abbreviations
    when the promoted message targets an unknown country
      should return state hash for all states
  thanks_for_tweeting_text
    when campaign is a survey
      should return generic thank-you message
    when campaign is not a survey
      should return thank-you for tweeting officials message
  make_a_tweet_button_text
    when campaign is a survey
      should return general tweet text
    when campaign is not a survey
      should return tweet your elected officials text
    when campaign has no selected_recipient
      should not error and return a default message
  url_to_tweet_message
    for promoted message
      with existing tweet text
        with recipients
          should build url with tweet text including recipient twitter handles
        without recipients
          should use tweet text to build url with prebuilt message
      with a nil tweet_text
        should not break

RecipientsHelper
  recipient_has_staffers?
    where recipient has at least one recipient office with staffers
      should return true
    where recipient has no staffers
      should return false

VideoHelper
  #get_time_limit
    for a PromotedMessage owned by Asthma and Allergy Foundation of America
      should return 180
    for a PromotedMessage owned by MPP
      should return 120
    for a PromotedMessage owned by Felkel group
      should return 60
    for a PromotedMessage owned by a normal promoter
      should return 30
  #get_time_limit_text
    for a PromotedMessage owned by MPP
      should return 2 minutes
    for a PromotedMessage owned by Asthma and Allergy Foundation of America
      should return 3 minutes
    for a PromotedMessage owned by Felkel group
      should return 60 seconds
    for a PromotedMessage owned by a normal promoter
      should return 30 seconds

WidgetsHelper
  photo_tag
    creates an img tag for a rep photo (FAILED - 98)

AdvocateProfilesUpdater
  daily_advocate_profiles_update
    calls advocate_profiles_update_for_time with correct time
  advocate_profiles_update_for_time
    benchmarking time
      benchmarks and logs the time
    rescuing errors
      logs errors raised naturally
      logs errors when total time of advocate_profiles_update_for_time is >= 1 hour
    creating advocate_for_promoter with opt_in vs opt_out options and the correct display columns
      creates a new opted in advocate_for_promoter object if sender_profile has opt_in
      creates a new opted in advocate_for_promoter object if sender_profile's account has opt_in
      creates a new opted out advocate_for_promoter object if sender_profile doesnt have opt_in
      updates existing opted-out advocate_for_promoter object if sender_profile has opt_in
      updates existing opted-in advocate_for_promoter object display columns even if sender_profile is opt_out
    updating and creating advocate_profiles
      creates a new advocate_profile with the same attributes as the sender_profile if no advocate_profile exists for sender_profile
      updates sender_profile advocate_profile_id if none is present and updates advocate_profile with new sender info. It doesnt update phone if advocate phone is confirmed and sender profile phone is not confirmed
      finds associated advocate_profile by account email if no sender_profile email
      does not error out if there is no email on a sender_profile's account
      does not create a new advocate_profile for a sender_profile outside the time frame

Updating agg advocate tables
  Top level ETL calls
    successfully calls advocate_activity_tables_update_sql
    logs errors raised in inner methods of advocate_activity_tables_update_sql
    logs errors when total time of advocate_activity_tables_update_sql >= 10 minutes
    successfully runs call_agg_methods for this etl
    without end_time params
      successfully calls advocate_activity_tables_update
    with end_time params
      successfully calls advocate_activity_tables_update(end_time)
  advocate agg sql queries
    when calls run for multiple days
      successfully runs inserts and updates for agg_promoted_message_activity_by_day over multiple days
      successfully runs insert and update for agg_promoter_activity_by_day_table over multiple days
    when run on one day
      successfully runs inserts for dummy email data for one day
    with multi_content column updates
      updates multi_content columns in agg_promoted_message_activity_by_day
      updates multi_content columns in agg_promoter_activity_by_day

Updating agg legislator tables
  successfully calls run_legislator_activity_tables_update
  logs errors raised in inner methods of run_legislator_activity_tables_update
  logs errors when total time of run_legislator_activity_tables_update >= 10 minutes
  successfully runs call_agg_methods for this etl
  without end_time params
    successfully calls legislator_activity_tables_update
  with end_time params
    successfully calls legislator_activity_tables_update(end_time)
  the inner agg methods
    connection to archive_db
      successfully runs insert_dummy_data_legislator_promoted_message_activity_archive_db AND update_agg_legislator_promoted_message_activity_by_day_from_archive_db for multiple days (FAILED - 99)
      successfully updates update_agg_legislator_promoted_message_activity_by_day_from_archive_db for multi_content columns (FAILED - 100)
    connection to ocp_db
      when calls run for multiple days
        promoted_message level ETLs
          successfully runs insert_dummy_data_legislator_promoted_message_activity_ocp_db AND agg_legislator_promoted_message_specific_activity_by_day AND update_non_agg_columns_for_agg_legislator_promoted_message_activity_by_day for multiple days (FAILED - 101)
        promoter level ETLs
          successfully runs insert_dummy_data_agg_legislator_promoter_activity_by_day AND update_agg_legislator_promoter_activity_by_day (FAILED - 102)
          successfully updates with update_agg_legislator_promoter_activity_by_day for multi_content (FAILED - 103)
      when run on one day
        only will insert values for one day (FAILED - 104)

Updating agg profile tables
  Top level ETL methods
    successfully calls daily_agg_advocate_profile_tables_update
    successfully calls update_advocate_profile_tables_through_time
    logs errors raised in inner methods of update_advocate_profile_tables_through_time (FAILED - 105)
    logs errors when total time of update_advocate_profile_tables_through_time >= 1 hour
    successfully runs call_agg_methods for this etl
  Inner SQL
    should correctly insert_non_email_data_agg_promoted_message_by_advocate_activity (FAILED - 106)
    should correctly insert_email_dummy_data_agg_promoted_message_by_advocate_activity (FAILED - 107)
    should correctly update_non_email_data_agg_promoted_message_by_advocate_activity AND update_email_data_agg_promoted_message_by_advocate_activity (FAILED - 108)
    should run update_advocate_for_promoters_activity (FAILED - 109)
    should clean_agg_promoted_message_by_advocate_activity (FAILED - 110)

Australia::CiceroIdMatcher
  initialized_object
    loads stuff correctly
      loads the federal level db (FAILED - 111)
      loads the state level db (FAILED - 112)
      loads the federal level csv (FAILED - 113)
      loads the state level csv (FAILED - 114)
    matching active full match recipients
      applies the cicerco_id to federal senators (FAILED - 115)
      applies the cicerco_id to federal house (FAILED - 116)

Australia::CsvLoader
  Federal level
    def self.house
      loads the file and returns correct row data
    def self.senate
      loads the file and returns correct row data
  Testing each australian state
    state 'VIC' - Victoria
      LOWER - loads the file and returns correct row data
      UPPER - loads the file and returns correct row data
    state 'TAS' - Tasmania
      LOWER - loads the file and returns correct row data
      UPPER - loads the file and returns correct row data
    state 'NT' - Northern Territory
      LOWER - loads the file and returns correct row data
    state 'ACT' - Australian Capital Territory
      LOWER - loads the file and returns correct row data
    state 'NSW' - New South Wales
      LOWER - loads the file and returns correct row data
      UPPER - loads the file and returns correct row data
    state 'SA' - South Australia
      LOWER - loads the file and returns correct row data
      UPPER - loads the file and returns correct row data
    state 'QLD' - Queensland
      LOWER - loads the file and returns correct row data
    state 'WA' - Western Australia
      LOWER - loads the file and returns correct row data
      UPPER - loads the file and returns correct row data

BadAddressUpdater
  get_qualified_addresses
    a good EmailAddress
      example at ./spec/libs/bad_address_updater_spec.rb:22 (FAILED - 117)
    an EmailAddress updated recently
      example at ./spec/libs/bad_address_updater_spec.rb:28 (FAILED - 118)
    an EmailAddress for an inactive Recipient
      example at ./spec/libs/bad_address_updater_spec.rb:34 (FAILED - 119)
    an EmailAddress with .bad_address_type='Permanent...'
      example at ./spec/libs/bad_address_updater_spec.rb:40 (FAILED - 120)
    an EmailAddress with none of the above
      example at ./spec/libs/bad_address_updater_spec.rb:45 (FAILED - 121)
  call
    updates .bad_address_flg=false (FAILED - 122)
    blanks .bad_address_type (FAILED - 123)

Batched Query
  with a 200-row query
    with a batch size of 30
      behaves like batched query
        covers all rows, up to the processing_cap
      with a processing cap of 120
        behaves like batched query
          covers all rows, up to the processing_cap
      with a processing cap of 3
        behaves like batched query
          covers all rows, up to the processing_cap
    with a batch size of 13
      behaves like batched query
        covers all rows, up to the processing_cap
      with a processing cap of 120
        behaves like batched query
          covers all rows, up to the processing_cap
      with a processing cap of 3
        behaves like batched query
          covers all rows, up to the processing_cap
    with a batch size of 300
      behaves like batched query
        covers all rows, up to the processing_cap
      with a processing cap of 120
        behaves like batched query
          covers all rows, up to the processing_cap
      with a processing cap of 3
        behaves like batched query
          covers all rows, up to the processing_cap

cache advocates for country map
  successful calls
    should log time for successful daily_advocates_for_map_cache_update (FAILED - 124)
    should successfully run daily_advocates_for_map_cache_update (FAILED - 125)
  errors
    should log errors when failed call to daily_advocates_for_map_cache_update (FAILED - 126)
    should log errors when daily_advocates_for_map_cache_update total_time is >= 1 hour

ImportAdvocates
  with a custom field
    processes all rows (FAILED - 127)
    running
      creates an 'Initial Import' message (FAILED - 128)
      creates a CustomField (FAILED - 129)
      adds the custom field to the 'Initial Import' message (FAILED - 130)
      doesn't add the custom field to other messages (FAILED - 131)
    when the first row throws an exception
      stops the sync (FAILED - 132)

ImportBioguideIds
  creates a problem if there is no recipient found (FAILED - 133)
  when there are recipients with matching fec_ids
    but not matching offices
      creates a problem (FAILED - 134)
    and matching offices
      but multiple recipient matches
        creates a problem (FAILED - 135)
      (one recipient match)
        doesn't create a problem (FAILED - 136)
        doesn't save the bioguide_ids by default (FAILED - 137)
        with record: true
          saves the bioguide_ids (FAILED - 138)

import city council districts
  successful calls to ImportCityCouncilDistricts
    should create a new 'District' object when a District object doesn't already exist for that City Council Ward (FAILED - 139)
    should update current 'District' object with new geom when a District object already exists for that City Council Ward (FAILED - 140)
  failed calls to RetrieveLegislatorAggregateData
    should respond with an error for when no geom_name passed in (FAILED - 141)
    should respond with an error for when no abbreviation passed in (FAILED - 142)
    should respond with an error for when no state_fips_code passed in (FAILED - 143)
    should respond with an error for when no city_name passed in (FAILED - 144)
    should respond with an error for when no possible_city_names passed in (FAILED - 145)
    should respond with an error for when no district_identifier_column passed in (FAILED - 146)
    should respond with an error for when no state_id passed in (FAILED - 147)

ImportLegislatorProfiles
  with level: 'state'
    gets the state CSV's (FAILED - 148)
  with the default (no level parameter)'
    gets the federal CSV's (FAILED - 149)
  with the default (no record parameter)
    does not update any fields (FAILED - 150)
  with 'record: true'
    updates the recipient's title field (FAILED - 151)
    creates a RecipientBio (FAILED - 152)
    creates 3 RecipientOffices (FAILED - 153)
    fills in the RecipientOffice fields (FAILED - 154)
    creates 14 Staffers (FAILED - 155)
    fills in the Staffer fields (FAILED - 156)
    with an existing RecipientBio
      doesn't create a new RecipientBio (FAILED - 157)
      updates the RecipientBio (FAILED - 158)
      doesn't overwrite an existing value with a blank one (FAILED - 159)
    when the same person appears twice in one row
      creates one Staffer for each (FAILED - 160)
  clear_existing_profiles
    should destroy all recipient bios, staffers, and recipient offices (FAILED - 161)

import nation builder events
  works (FAILED - 162)
  creates a NationBuilderEvent object (FAILED - 163)
  doesn't create a NationBuilderEvent is one already exists (FAILED - 164)

AustraliaDistrictMatcher
  .find_district
    for an existing AU-VIC StateHouseDistrict with a .au_code
      at state-level with state=AU-VIC
        passing the au_code
          matches (FAILED - 165)
        passing the District's exact name
          matches (FAILED - 166)
        passing the District's name, downcased
          matches (FAILED - 167)
        passing the District's name with a double--dash
          matches (FAILED - 168)
        passing a different name
          doesn't match (FAILED - 169)
      at commonwealth-level
        passing the District's exact name
          doesn't match (FAILED - 170)
      at state-level for a different state
        passing the District's exact name
          doesn't match (FAILED - 171)
    if a district isn't returned
      for the Commonwealth Upper
        doesn't add to .problems (FAILED - 172)
      for the Commonwealth Lower
        adds to .problems (FAILED - 173)

AustraliaDistrictImporter
  with a valid NewDistrict
    at state-level
      LOWER
        with a matching District
          updates the geometry column (FAILED - 174)
          behaves like an Australian district importer
            updates the geometry column (FAILED - 175)
            without an au code
              updates the au code (FAILED - 176)
            with an au_code
              with the overwrite flag
                overwrites the old au code (FAILED - 177)
              without the overwrite flag
                doesn't overwrite the au code (FAILED - 178)
          if the existing District lacks a au_code
            updates the code (FAILED - 179)
        without a matching District
          imports the StateHouseDistrict (FAILED - 180)
      UPPER
        with a matching District
          updates the geometry column (FAILED - 181)
          behaves like an Australian district importer
            updates the geometry column (FAILED - 182)
            without an au code
              updates the au code (FAILED - 183)
            with an au_code
              with the overwrite flag
                overwrites the old au code (FAILED - 184)
              without the overwrite flag
                doesn't overwrite the au code (FAILED - 185)
          if the existing District lacks a au_code
            updates the code (FAILED - 186)
        without a matching District
          imports the StateSenateDistrict (FAILED - 187)
      UPPER in NSW (province-wide)
        with an existing, province-wide 'At-large' District
          doesn't create a new 'At Large' District (FAILED - 188)
        with an existing, province-wide 'Legislative Council' District
          doesn't create a new 'Legislative Council' District (FAILED - 189)
    at national-level
      with a matching District
        behaves like an Australian district importer
          updates the geometry column (FAILED - 190)
          without an au code
            updates the au code (FAILED - 191)
          with an au_code
            with the overwrite flag
              overwrites the old au code (FAILED - 192)
            without the overwrite flag
              doesn't overwrite the au code (FAILED - 193)
      without a matching District
        imports the CongressionalDistrict (FAILED - 194)
    with an invalid .district_t column
      doesn't import (FAILED - 195)

AU Recipient Importer
  with two existing AU Reps
    behaves like an AU Recipient record updater and replacer
      behaves like a Recipient record updater and replacer
        with updatable, replaceable, and new Recipients
          matching
            schedules the updatable Recipient for update (FAILED - 196)
            schedules the replaceable Recipient for replacement (FAILED - 197)
          importing
            deactivates the replaceable Recipient (FAILED - 198)
            updates the updatable Recipient (FAILED - 199)
            imports the new Recipient (FAILED - 200)
  with two existing AU Senators
    behaves like an AU Recipient record updater and replacer
      behaves like a Recipient record updater and replacer
        with updatable, replaceable, and new Recipients
          matching
            schedules the updatable Recipient for update (FAILED - 201)
            schedules the replaceable Recipient for replacement (FAILED - 202)
          importing
            deactivates the replaceable Recipient (FAILED - 203)
            updates the updatable Recipient (FAILED - 204)
            imports the new Recipient (FAILED - 205)
  with two existing State-level Council members for AU-NSW
    behaves like an AU Recipient record updater and replacer
      behaves like a Recipient record updater and replacer
        with updatable, replaceable, and new Recipients
          matching
            schedules the updatable Recipient for update (FAILED - 206)
            schedules the replaceable Recipient for replacement (FAILED - 207)
          importing
            deactivates the replaceable Recipient (FAILED - 208)
            updates the updatable Recipient (FAILED - 209)
            imports the new Recipient (FAILED - 210)
  with two existing State-level Reps
    behaves like an AU Recipient record updater and replacer
      behaves like a Recipient record updater and replacer
        with updatable, replaceable, and new Recipients
          matching
            schedules the updatable Recipient for update (FAILED - 211)
            schedules the replaceable Recipient for replacement (FAILED - 212)
          importing
            deactivates the replaceable Recipient (FAILED - 213)
            updates the updatable Recipient (FAILED - 214)
            imports the new Recipient (FAILED - 215)
  with a vacated seat (name VACANT) and an updatable seat
    from different districts
      deactivates the vacated Recipient (FAILED - 216)
      updates the updatable Recipient (FAILED - 217)
  with existing reps swapping seats
    importing
      swaps seats (FAILED - 218)
  testing for problems
    with AU-VIC and AU-NSW data
      importing only_states => ['AU-VIC']
        is successful (FAILED - 219)
    AustraliaRecipientImporter.all_problems
      with party that does not exist
        throws a party_matcher error (FAILED - 220)
      with row for vacant seat
        does not throw a party_matcher error (FAILED - 221)
  with an existing AU Rep with a cicero code
    behaves like an AU Recipient name updater
      behaves like AU Recipient first_name and last_name updater
        with updatable AU Recipients
          behaves like a first_name and last_name updater
            when overwrite lastname is true
              updates the last_name of the updatable Recipient (FAILED - 222)
            when overwrite firstname is false
              does not update the first_name of the updatable Recipient (FAILED - 223)
      behaves like AU Recipient first_name and last_name updater
        with updatable AU Recipients
          behaves like a first_name and last_name updater
            when overwrite lastname is false
              does not update the last_name of the updatable Recipient (FAILED - 224)
            when overwrite firstname is true
              updates the first_name of the updatable Recipient (FAILED - 225)
      behaves like AU Recipient first_name and last_name updater
        with updatable AU Recipients
          behaves like a first_name and last_name updater
            when overwrite lastname is true
              updates the last_name of the updatable Recipient (FAILED - 226)
            when overwrite firstname is true
              updates the first_name of the updatable Recipient (FAILED - 227)
      behaves like AU Recipient first_name and last_name updater
        with updatable AU Recipients
          behaves like a first_name and last_name updater
            when overwrite lastname is false
              does not update the last_name of the updatable Recipient (FAILED - 228)
            when overwrite firstname is false
              does not update the first_name of the updatable Recipient (FAILED - 229)
  with an existing AU Senator with a cicero code
    behaves like AU Recipient first_name and last_name updater
      with updatable AU Recipients
        behaves like a first_name and last_name updater
          when overwrite lastname is true
            updates the last_name of the updatable Recipient (FAILED - 230)
          when overwrite firstname is true
            updates the first_name of the updatable Recipient (FAILED - 231)
  with an existing AU State-level Councilmember with a cicero code
    behaves like AU Recipient first_name and last_name updater
      with updatable AU Recipients
        behaves like a first_name and last_name updater
          when overwrite lastname is true
            updates the last_name of the updatable Recipient (FAILED - 232)
          when overwrite firstname is true
            updates the first_name of the updatable Recipient (FAILED - 233)
  with an existing AU State-level Assemblymember with a cicero code
    behaves like AU Recipient first_name and last_name updater
      with updatable AU Recipients
        behaves like a first_name and last_name updater
          when overwrite lastname is true
            updates the last_name of the updatable Recipient (FAILED - 234)
          when overwrite firstname is true
            updates the first_name of the updatable Recipient (FAILED - 235)
  for Australian Reps
    behaves like an AU Recipient record matcher
      matching
        behaves like a Recipient record matcher
          if a rep already exists
            with the same cicero_code
              matches (FAILED - 236)
            with the same name, state, and district
              and is active
                matches (FAILED - 237)
              with a different name
                doesn't match (FAILED - 238)
              but is inactive
                doesn't match (FAILED - 239)
    behaves like an AU Address and field updater
      importing
        without a cicero code
          updates the cicero code (FAILED - 240)
        with a phone number
          by default
            updates the phone handle (FAILED - 241)
          with ignore_imports_flg = true
            doesn't update the phone number (FAILED - 242)
        without a portrait
          creates the portrait (FAILED - 243)
        with a portrait
          updates the portrait (FAILED - 244)
        without a WebMailAddress
          creates the WebMailAddress (FAILED - 245)
        with a WebMailAddress
          by default
            updates the WebMailAddress (FAILED - 246)
          with :addresses_options => {:except => ['webform']}
            doesn't update the WebMailAddress (FAILED - 247)
          with ignore_imports_flg = true
            doesn't update the WebMailAddress (FAILED - 248)
    behaves like an AU statewise updater for
      importing :except_states => [state]
        doesn't import to the limiting state (FAILED - 249)
      importing :only_states => [state]
        imports to the limiting state (FAILED - 250)
  for Australian Senators
    behaves like an AU Recipient record matcher
      matching
        behaves like a Recipient record matcher
          if a rep already exists
            with the same cicero_code
              matches (FAILED - 251)
            with the same name, state, and district
              and is active
                matches (FAILED - 252)
              with a different name
                doesn't match (FAILED - 253)
              but is inactive
                doesn't match (FAILED - 254)
    behaves like an AU Address and field updater
      importing
        without a cicero code
          updates the cicero code (FAILED - 255)
        with a phone number
          by default
            updates the phone handle (FAILED - 256)
          with ignore_imports_flg = true
            doesn't update the phone number (FAILED - 257)
        without a portrait
          creates the portrait (FAILED - 258)
        with a portrait
          updates the portrait (FAILED - 259)
        without a WebMailAddress
          creates the WebMailAddress (FAILED - 260)
        with a WebMailAddress
          by default
            updates the WebMailAddress (FAILED - 261)
          with :addresses_options => {:except => ['webform']}
            doesn't update the WebMailAddress (FAILED - 262)
          with ignore_imports_flg = true
            doesn't update the WebMailAddress (FAILED - 263)
    behaves like an AU statewise updater for
      importing :except_states => [state]
        doesn't import to the limiting state (FAILED - 264)
      importing :only_states => [state]
        imports to the limiting state (FAILED - 265)
  for State-level Councilmen
    behaves like an AU Recipient record matcher
      matching
        behaves like a Recipient record matcher
          if a rep already exists
            with the same cicero_code
              matches (FAILED - 266)
            with the same name, state, and district
              and is active
                matches (FAILED - 267)
              with a different name
                doesn't match (FAILED - 268)
              but is inactive
                doesn't match (FAILED - 269)
    behaves like an AU Address and field updater
      importing
        without a cicero code
          updates the cicero code (FAILED - 270)
        with a phone number
          by default
            updates the phone handle (FAILED - 271)
          with ignore_imports_flg = true
            doesn't update the phone number (FAILED - 272)
        without a portrait
          creates the portrait (FAILED - 273)
        with a portrait
          updates the portrait (FAILED - 274)
        without a WebMailAddress
          creates the WebMailAddress (FAILED - 275)
        with a WebMailAddress
          by default
            updates the WebMailAddress (FAILED - 276)
          with :addresses_options => {:except => ['webform']}
            doesn't update the WebMailAddress (FAILED - 277)
          with ignore_imports_flg = true
            doesn't update the WebMailAddress (FAILED - 278)
    behaves like an AU statewise updater for
      importing :except_states => [state]
        doesn't import to the limiting state (FAILED - 279)
      importing :only_states => [state]
        imports to the limiting state (FAILED - 280)
  for State-level Assemblywomen
    behaves like an AU Recipient record matcher
      matching
        behaves like a Recipient record matcher
          if a rep already exists
            with the same cicero_code
              matches (FAILED - 281)
            with the same name, state, and district
              and is active
                matches (FAILED - 282)
              with a different name
                doesn't match (FAILED - 283)
              but is inactive
                doesn't match (FAILED - 284)
    behaves like an AU Address and field updater
      importing
        without a cicero code
          updates the cicero code (FAILED - 285)
        with a phone number
          by default
            updates the phone handle (FAILED - 286)
          with ignore_imports_flg = true
            doesn't update the phone number (FAILED - 287)
        without a portrait
          creates the portrait (FAILED - 288)
        with a portrait
          updates the portrait (FAILED - 289)
        without a WebMailAddress
          creates the WebMailAddress (FAILED - 290)
        with a WebMailAddress
          by default
            updates the WebMailAddress (FAILED - 291)
          with :addresses_options => {:except => ['webform']}
            doesn't update the WebMailAddress (FAILED - 292)
          with ignore_imports_flg = true
            doesn't update the WebMailAddress (FAILED - 293)
    behaves like an AU statewise updater for
      importing :except_states => [state]
        doesn't import to the limiting state (FAILED - 294)
      importing :only_states => [state]
        imports to the limiting state (FAILED - 295)

AustraliaPartyImporter
  .import
    with an existing Party
      doesn't import
    without an existing Party
      imports

CanadaDistrictMatcher
  .find_district
    for an existing CA-ON StateHouseDistrict with a .canada_code
      at state-level with state=ON
        passing the canada_code
          matches (FAILED - 296)
        passing the District's exact name
          matches (FAILED - 297)
        passing the District's name, downcased
          matches (FAILED - 298)
        passing the District's name with a single dash
          matches (FAILED - 299)
        passing a different name
          doesn't match (FAILED - 300)
      at commonwealth-level
        passing the District's exact name
          doesn't match (FAILED - 301)
      at state-level for a different state
        passing the District's exact name
          doesn't match (FAILED - 302)
    if a district isn't returned
      for the Commonwealth Upper
        doesn't add to .problems (FAILED - 303)
      for the Commonwealth Lower
        adds to .problems (FAILED - 304)

CanadaDistrictImporter
  with a valid NewDistrict
    at state-level
      with a matching District
        updates the geometry column (FAILED - 305)
        if the existing District lacks a canada_code
          updates the code (FAILED - 306)
      without a matching District
        imports the StateHouseDistrict (FAILED - 307)
    at national-level
      with a matching District
        updates the geometry column (FAILED - 308)
        if the existing District lacks a canada_code
          updates the code (FAILED - 309)
      without a matching District
        imports the CongressionalDistrict (FAILED - 310)
    with an invalid .district_t column
      doesn't import (FAILED - 311)

CA Recipient Importer
  with two existing CA Reps
    behaves like a CA Recipient record updater and replacer
      behaves like a Recipient record updater and replacer
        with updatable, replaceable, and new Recipients
          matching
            schedules the updatable Recipient for update (FAILED - 312)
            schedules the replaceable Recipient for replacement (FAILED - 313)
          importing
            deactivates the replaceable Recipient (FAILED - 314)
            updates the updatable Recipient (FAILED - 315)
            imports the new Recipient (FAILED - 316)
  with two existing CA Senators
    behaves like a CA Recipient record updater and replacer
      behaves like a Recipient record updater and replacer
        with updatable, replaceable, and new Recipients
          matching
            schedules the updatable Recipient for update (FAILED - 317)
            schedules the replaceable Recipient for replacement (FAILED - 318)
          importing
            deactivates the replaceable Recipient (FAILED - 319)
            updates the updatable Recipient (FAILED - 320)
            imports the new Recipient (FAILED - 321)
  with two existing State-level Reps
    behaves like a CA Recipient record updater and replacer
      behaves like a Recipient record updater and replacer
        with updatable, replaceable, and new Recipients
          matching
            schedules the updatable Recipient for update (FAILED - 322)
            schedules the replaceable Recipient for replacement (FAILED - 323)
          importing
            deactivates the replaceable Recipient (FAILED - 324)
            updates the updatable Recipient (FAILED - 325)
            imports the new Recipient (FAILED - 326)
  with a vacated seat (name VACANT) and an updatable seat
    from different districts
      deactivates the vacated Recipient (FAILED - 327)
      updates the updatable Recipient (FAILED - 328)
  with existing reps swapping seats
    importing
      swaps seats (FAILED - 329)
  testing for problems
    with CA-QC and CA-ON data
      importing only_states => ['CA-ON']
        is successful (FAILED - 330)
    CanadaRecipientImporter.all_problems
      with party that does not exist
        throws a party_matcher error (FAILED - 331)
      with row for vacant seat
        does not throw a party_matcher error (FAILED - 332)
    with an existing CA Rep with a cicero code
      overwrite_lastname is true and overwrite_firstname is false
        behaves like Recipient first_name and last_name updater
          with updatable Recipients
            when overwrite lastname is true
              updates the last_name of the updatable Recipient (FAILED - 333)
            when overwrite firstname is false
              does not update the first_name of the updatable Recipient (FAILED - 334)
      overwrite_lastname is true and overwrite_firstname is true
        behaves like Recipient first_name and last_name updater
          with updatable Recipients
            when overwrite lastname is true
              updates the last_name of the updatable Recipient (FAILED - 335)
            when overwrite firstname is true
              updates the first_name of the updatable Recipient (FAILED - 336)
      overwrite_lastname is false and overwrite_firstname is true
        behaves like Recipient first_name and last_name updater
          with updatable Recipients
            when overwrite lastname is false
              does not update the last_name of the updatable Recipient (FAILED - 337)
            when overwrite firstname is true
              updates the first_name of the updatable Recipient (FAILED - 338)
      overwrite_lastname is false and overwrite_firstname is false
        behaves like Recipient first_name and last_name updater
          with updatable Recipients
            when overwrite lastname is false
              does not update the last_name of the updatable Recipient (FAILED - 339)
            when overwrite firstname is false
              does not update the first_name of the updatable Recipient (FAILED - 340)
    with an existing CA Senator with a cicero code
      behaves like Recipient first_name and last_name updater
        with updatable Recipients
          when overwrite lastname is true
            updates the last_name of the updatable Recipient (FAILED - 341)
          when overwrite firstname is true
            updates the first_name of the updatable Recipient (FAILED - 342)
    with an existing CA State-level Assemblymember with a cicero code
      behaves like Recipient first_name and last_name updater
        with updatable Recipients
          when overwrite lastname is true
            updates the last_name of the updatable Recipient (FAILED - 343)
          when overwrite firstname is true
            updates the first_name of the updatable Recipient (FAILED - 344)
  with an existing CA Rep with a cicero code
    behaves like a CA Recipient name updater
      behaves like CA Recipient first_name and last_name updater
        with updatable CA Recipients
          behaves like a first_name and last_name updater
            when overwrite lastname is true
              updates the last_name of the updatable Recipient (FAILED - 345)
            when overwrite firstname is false
              does not update the first_name of the updatable Recipient (FAILED - 346)
      behaves like CA Recipient first_name and last_name updater
        with updatable CA Recipients
          behaves like a first_name and last_name updater
            when overwrite lastname is false
              does not update the last_name of the updatable Recipient (FAILED - 347)
            when overwrite firstname is true
              updates the first_name of the updatable Recipient (FAILED - 348)
      behaves like CA Recipient first_name and last_name updater
        with updatable CA Recipients
          behaves like a first_name and last_name updater
            when overwrite lastname is true
              updates the last_name of the updatable Recipient (FAILED - 349)
            when overwrite firstname is true
              updates the first_name of the updatable Recipient (FAILED - 350)
      behaves like CA Recipient first_name and last_name updater
        with updatable CA Recipients
          behaves like a first_name and last_name updater
            when overwrite lastname is false
              does not update the last_name of the updatable Recipient (FAILED - 351)
            when overwrite firstname is false
              does not update the first_name of the updatable Recipient (FAILED - 352)
  with an existing CA Senator with a cicero code
    behaves like CA Recipient first_name and last_name updater
      with updatable CA Recipients
        behaves like a first_name and last_name updater
          when overwrite lastname is true
            updates the last_name of the updatable Recipient (FAILED - 353)
          when overwrite firstname is true
            updates the first_name of the updatable Recipient (FAILED - 354)
  with an existing CA State-level Assemblymember with a cicero code
    behaves like CA Recipient first_name and last_name updater
      with updatable CA Recipients
        behaves like a first_name and last_name updater
          when overwrite lastname is true
            updates the last_name of the updatable Recipient (FAILED - 355)
          when overwrite firstname is true
            updates the first_name of the updatable Recipient (FAILED - 356)
  for Canadian Reps
    behaves like a CA Recipient record matcher
      matching
        behaves like a Recipient record matcher
          if a rep already exists
            with the same cicero_code
              matches (FAILED - 357)
            with the same name, state, and district
              and is active
                matches (FAILED - 358)
              with a different name
                doesn't match (FAILED - 359)
              but is inactive
                doesn't match (FAILED - 360)
    behaves like a CA Address and field updater
      importing
        without a cicero code
          updates the cicero code (FAILED - 361)
        with a phone number
          by default
            updates the phone handle (FAILED - 362)
          with ignore_imports_flg = true
            doesn't update the phone number (FAILED - 363)
        without a portrait
          creates the portrait (FAILED - 364)
        with a portrait
          updates the portrait (FAILED - 365)
        without a WebMailAddress
          creates the WebMailAddress (FAILED - 366)
        with a WebMailAddress
          by default
            updates the WebMailAddress (FAILED - 367)
          with :addresses_options => {:except => ['webform']}
            doesn't update the WebMailAddress (FAILED - 368)
          with ignore_imports_flg = true
            doesn't update the WebMailAddress (FAILED - 369)
    behaves like a CA statewise updater for
      importing :except_states => [state]
        doesn't import to the limiting state (FAILED - 370)
      importing :only_states => [state]
        imports to the limiting state (FAILED - 371)
  for Canadian Senators
    behaves like a CA Recipient record matcher
      matching
        behaves like a Recipient record matcher
          if a rep already exists
            with the same cicero_code
              matches (FAILED - 372)
            with the same name, state, and district
              and is active
                matches (FAILED - 373)
              with a different name
                doesn't match (FAILED - 374)
              but is inactive
                doesn't match (FAILED - 375)
    behaves like a CA Address and field updater
      importing
        without a cicero code
          updates the cicero code (FAILED - 376)
        with a phone number
          by default
            updates the phone handle (FAILED - 377)
          with ignore_imports_flg = true
            doesn't update the phone number (FAILED - 378)
        without a portrait
          creates the portrait (FAILED - 379)
        with a portrait
          updates the portrait (FAILED - 380)
        without a WebMailAddress
          creates the WebMailAddress (FAILED - 381)
        with a WebMailAddress
          by default
            updates the WebMailAddress (FAILED - 382)
          with :addresses_options => {:except => ['webform']}
            doesn't update the WebMailAddress (FAILED - 383)
          with ignore_imports_flg = true
            doesn't update the WebMailAddress (FAILED - 384)
    behaves like a CA statewise updater for
      importing :except_states => [state]
        doesn't import to the limiting state (FAILED - 385)
      importing :only_states => [state]
        imports to the limiting state (FAILED - 386)
  for State-level Reps
    behaves like a CA Recipient record matcher
      matching
        behaves like a Recipient record matcher
          if a rep already exists
            with the same cicero_code
              matches (FAILED - 387)
            with the same name, state, and district
              and is active
                matches (FAILED - 388)
              with a different name
                doesn't match (FAILED - 389)
              but is inactive
                doesn't match (FAILED - 390)
    behaves like a CA Address and field updater
      importing
        without a cicero code
          updates the cicero code (FAILED - 391)
        with a phone number
          by default
            updates the phone handle (FAILED - 392)
          with ignore_imports_flg = true
            doesn't update the phone number (FAILED - 393)
        without a portrait
          creates the portrait (FAILED - 394)
        with a portrait
          updates the portrait (FAILED - 395)
        without a WebMailAddress
          creates the WebMailAddress (FAILED - 396)
        with a WebMailAddress
          by default
            updates the WebMailAddress (FAILED - 397)
          with :addresses_options => {:except => ['webform']}
            doesn't update the WebMailAddress (FAILED - 398)
          with ignore_imports_flg = true
            doesn't update the WebMailAddress (FAILED - 399)
    behaves like a CA statewise updater for
      importing :except_states => [state]
        doesn't import to the limiting state (FAILED - 400)
      importing :only_states => [state]
        imports to the limiting state (FAILED - 401)

CanadaPartyImporter
  .import
    with an existing Party
      doesn't import
    without an existing Party
      imports

CiceroUSDistrictMatcher
  .find_district
    state house
      Chittenden-4-1 State House District
        behaves like a District finder
          matches
            passing the us_code
              matches (FAILED - 402)
            passing the District's exact name
              matches (FAILED - 403)
            passing in matching names
              matches (FAILED - 404)
            passing the District's name, downcased
              matches (FAILED - 405)
            passing the District's name with extra dashes
              matches (FAILED - 406)
            passing the District's name without extra words
              matches (FAILED - 407)
            passing the District's name without dashes
              matches (FAILED - 408)
          mismatches
            passing the wrong name
              doesn't match (FAILED - 409)
            with the right name
              passing the wrong level
                doesn't match (FAILED - 410)
              passing the wrong state
                doesn't match (FAILED - 411)
              passing the wrong chamber
                doesn't match (FAILED - 412)
      New Hampshire House Merrimack 04
        behaves like a District finder
          matches
            passing the us_code
              matches (FAILED - 413)
            passing the District's exact name
              matches (FAILED - 414)
            passing in matching names
              matches (FAILED - 415)
            passing the District's name, downcased
              matches (FAILED - 416)
            passing the District's name with extra dashes
              matches (FAILED - 417)
            passing the District's name without extra words
              matches (FAILED - 418)
            passing the District's name without dashes
              matches (FAILED - 419)
          mismatches
            passing the wrong name
              doesn't match (FAILED - 420)
            with the right name
              passing the wrong level
                doesn't match (FAILED - 421)
              passing the wrong state
                doesn't match (FAILED - 422)
              passing the wrong chamber
                doesn't match (FAILED - 423)
      New Hampshire House Merrimack 14
        behaves like a District finder
          matches
            passing the us_code
              matches (FAILED - 424)
            passing the District's exact name
              matches (FAILED - 425)
            passing in matching names
              matches (FAILED - 426)
            passing the District's name, downcased
              matches (FAILED - 427)
            passing the District's name with extra dashes
              matches (FAILED - 428)
            passing the District's name without extra words
              matches (FAILED - 429)
            passing the District's name without dashes
              matches (FAILED - 430)
          mismatches
            passing the wrong name
              doesn't match (FAILED - 431)
            with the right name
              passing the wrong level
                doesn't match (FAILED - 432)
              passing the wrong state
                doesn't match (FAILED - 433)
              passing the wrong chamber
                doesn't match (FAILED - 434)
      New Hampshire House Belknap 06
        behaves like a District finder
          matches
            passing the us_code
              matches (FAILED - 435)
            passing the District's exact name
              matches (FAILED - 436)
            passing in matching names
              matches (FAILED - 437)
            passing the District's name, downcased
              matches (FAILED - 438)
            passing the District's name with extra dashes
              matches (FAILED - 439)
            passing the District's name without extra words
              matches (FAILED - 440)
            passing the District's name without dashes
              matches (FAILED - 441)
          mismatches
            passing the wrong name
              doesn't match (FAILED - 442)
            with the right name
              passing the wrong level
                doesn't match (FAILED - 443)
              passing the wrong state
                doesn't match (FAILED - 444)
              passing the wrong chamber
                doesn't match (FAILED - 445)
      Vermont House Orange Washington Addison
        behaves like a District finder
          matches
            passing the us_code
              matches (FAILED - 446)
            passing the District's exact name
              matches (FAILED - 447)
            passing in matching names
              matches (FAILED - 448)
            passing the District's name, downcased
              matches (FAILED - 449)
            passing the District's name with extra dashes
              matches (FAILED - 450)
            passing the District's name without extra words
              matches (FAILED - 451)
            passing the District's name without dashes
              matches (FAILED - 452)
          mismatches
            passing the wrong name
              doesn't match (FAILED - 453)
            with the right name
              passing the wrong level
                doesn't match (FAILED - 454)
              passing the wrong state
                doesn't match (FAILED - 455)
              passing the wrong chamber
                doesn't match (FAILED - 456)
      Wisconsin Assembly District 007
        behaves like a District finder
          matches
            passing the us_code
              matches (FAILED - 457)
            passing the District's exact name
              matches (FAILED - 458)
            passing in matching names
              matches (FAILED - 459)
            passing the District's name, downcased
              matches (FAILED - 460)
            passing the District's name with extra dashes
              matches (FAILED - 461)
            passing the District's name without extra words
              matches (FAILED - 462)
            passing the District's name without dashes
              matches (FAILED - 463)
          mismatches
            passing the wrong name
              doesn't match (FAILED - 464)
            with the right name
              passing the wrong level
                doesn't match (FAILED - 465)
              passing the wrong state
                doesn't match (FAILED - 466)
              passing the wrong chamber
                doesn't match (FAILED - 467)
      Minnesota State House District 04a
        behaves like a District finder
          matches
            passing the us_code
              matches (FAILED - 468)
            passing the District's exact name
              matches (FAILED - 469)
            passing in matching names
              matches (FAILED - 470)
            passing the District's name, downcased
              matches (FAILED - 471)
            passing the District's name with extra dashes
              matches (FAILED - 472)
            passing the District's name without extra words
              matches (FAILED - 473)
            passing the District's name without dashes
              matches (FAILED - 474)
          mismatches
            passing the wrong name
              doesn't match (FAILED - 475)
            with the right name
              passing the wrong level
                doesn't match (FAILED - 476)
              passing the wrong state
                doesn't match (FAILED - 477)
              passing the wrong chamber
                doesn't match (FAILED - 478)
      CT State House District 001
        behaves like a District finder
          matches
            passing the us_code
              matches (FAILED - 479)
            passing the District's exact name
              matches (FAILED - 480)
            passing in matching names
              matches (FAILED - 481)
            passing the District's name, downcased
              matches (FAILED - 482)
            passing the District's name with extra dashes
              matches (FAILED - 483)
            passing the District's name without extra words
              matches (FAILED - 484)
            passing the District's name without dashes
              matches (FAILED - 485)
          mismatches
            passing the wrong name
              doesn't match (FAILED - 486)
            with the right name
              passing the wrong level
                doesn't match (FAILED - 487)
              passing the wrong state
                doesn't match (FAILED - 488)
              passing the wrong chamber
                doesn't match (FAILED - 489)
    state senate
      Vermont Senate Addison
        behaves like a District finder
          matches
            passing the us_code
              matches (FAILED - 490)
            passing the District's exact name
              matches (FAILED - 491)
            passing in matching names
              matches (FAILED - 492)
            passing the District's name, downcased
              matches (FAILED - 493)
            passing the District's name with extra dashes
              matches (FAILED - 494)
            passing the District's name without extra words
              matches (FAILED - 495)
            passing the District's name without dashes
              matches (FAILED - 496)
          mismatches
            passing the wrong name
              doesn't match (FAILED - 497)
            with the right name
              passing the wrong level
                doesn't match (FAILED - 498)
              passing the wrong state
                doesn't match (FAILED - 499)
              passing the wrong chamber
                doesn't match (FAILED - 500)
      Vermont Senate District F
        behaves like a District finder
          matches
            passing the us_code
              matches (FAILED - 501)
            passing the District's exact name
              matches (FAILED - 502)
            passing in matching names
              matches (FAILED - 503)
            passing the District's name, downcased
              matches (FAILED - 504)
            passing the District's name with extra dashes
              matches (FAILED - 505)
            passing the District's name without extra words
              matches (FAILED - 506)
            passing the District's name without dashes
              matches (FAILED - 507)
          mismatches
            passing the wrong name
              doesn't match (FAILED - 508)
            with the right name
              passing the wrong level
                doesn't match (FAILED - 509)
              passing the wrong state
                doesn't match (FAILED - 510)
              passing the wrong chamber
                doesn't match (FAILED - 511)
    US House
      California District 39
        behaves like a District finder
          matches
            passing the us_code
              matches (FAILED - 512)
            passing the District's exact name
              matches (FAILED - 513)
            passing in matching names
              matches (FAILED - 514)
            passing the District's name, downcased
              matches (FAILED - 515)
            passing the District's name with extra dashes
              matches (FAILED - 516)
            passing the District's name without extra words
              matches (FAILED - 517)
            passing the District's name without dashes
              matches (FAILED - 518)
          mismatches
            passing the wrong name
              doesn't match (FAILED - 519)
            with the right name
              passing the wrong level
                doesn't match (FAILED - 520)
              passing the wrong state
                doesn't match (FAILED - 521)
              passing the wrong chamber
                doesn't match (FAILED - 522)
      Vermont At-Large District
        behaves like a District finder
          matches
            passing the us_code
              matches (FAILED - 523)
            passing the District's exact name
              matches (FAILED - 524)
            passing in matching names
              matches (FAILED - 525)
            passing the District's name, downcased
              matches (FAILED - 526)
            passing the District's name with extra dashes
              matches (FAILED - 527)
            passing the District's name without extra words
              matches (FAILED - 528)
            passing the District's name without dashes
              matches (FAILED - 529)
          mismatches
            passing the wrong name
              doesn't match (FAILED - 530)
            with the right name
              passing the wrong level
                doesn't match (FAILED - 531)
              passing the wrong state
                doesn't match (FAILED - 532)
              passing the wrong chamber
                doesn't match (FAILED - 533)
    US City Councils
      Chicago At-Large District
        behaves like a District finder
          matches
            passing the us_code
              matches (FAILED - 534)
            passing the District's exact name
              matches (FAILED - 535)
            passing in matching names
              matches (FAILED - 536)
            passing the District's name, downcased
              matches (FAILED - 537)
            passing the District's name with extra dashes
              matches (FAILED - 538)
            passing the District's name without extra words
              matches (FAILED - 539)
            passing the District's name without dashes
              matches (FAILED - 540)
          mismatches
            passing the wrong name
              doesn't match (FAILED - 541)
            with the right name
              passing the wrong level
                doesn't match (FAILED - 542)
              passing the wrong state
                doesn't match (FAILED - 543)
              passing the wrong chamber
                doesn't match (FAILED - 544)
      Chicago District 12
        behaves like a District finder
          matches
            passing the us_code
              matches (FAILED - 545)
            passing the District's exact name
              matches (FAILED - 546)
            passing in matching names
              matches (FAILED - 547)
            passing the District's name, downcased
              matches (FAILED - 548)
            passing the District's name with extra dashes
              matches (FAILED - 549)
            passing the District's name without extra words
              matches (FAILED - 550)
            passing the District's name without dashes
              matches (FAILED - 551)
          mismatches
            passing the wrong name
              doesn't match (FAILED - 552)
            with the right name
              passing the wrong level
                doesn't match (FAILED - 553)
              passing the wrong state
                doesn't match (FAILED - 554)
              passing the wrong chamber
                doesn't match (FAILED - 555)
      Chicago District III
        behaves like a District finder
          matches
            passing the us_code
              matches (FAILED - 556)
            passing the District's exact name
              matches (FAILED - 557)
            passing in matching names
              matches (FAILED - 558)
            passing the District's name, downcased
              matches (FAILED - 559)
            passing the District's name with extra dashes
              matches (FAILED - 560)
            passing the District's name without extra words
              matches (FAILED - 561)
            passing the District's name without dashes
              matches (FAILED - 562)
          mismatches
            passing the wrong name
              doesn't match (FAILED - 563)
            with the right name
              passing the wrong level
                doesn't match (FAILED - 564)
              passing the wrong state
                doesn't match (FAILED - 565)
              passing the wrong chamber
                doesn't match (FAILED - 566)
      Chicago District F
        behaves like a District finder
          matches
            passing the us_code
              matches (FAILED - 567)
            passing the District's exact name
              matches (FAILED - 568)
            passing in matching names
              matches (FAILED - 569)
            passing the District's name, downcased
              matches (FAILED - 570)
            passing the District's name with extra dashes
              matches (FAILED - 571)
            passing the District's name without extra words
              matches (FAILED - 572)
            passing the District's name without dashes
              matches (FAILED - 573)
          mismatches
            passing the wrong name
              doesn't match (FAILED - 574)
            with the right name
              passing the wrong level
                doesn't match (FAILED - 575)
              passing the wrong state
                doesn't match (FAILED - 576)
              passing the wrong chamber
                doesn't match (FAILED - 577)
      Chicago District Blue Ridge
        behaves like a District finder
          matches
            passing the us_code
              matches (FAILED - 578)
            passing the District's exact name
              matches (FAILED - 579)
            passing in matching names
              matches (FAILED - 580)
            passing the District's name, downcased
              matches (FAILED - 581)
            passing the District's name with extra dashes
              matches (FAILED - 582)
            passing the District's name without extra words
              matches (FAILED - 583)
            passing the District's name without dashes
              matches (FAILED - 584)
          mismatches
            passing the wrong name
              doesn't match (FAILED - 585)
            with the right name
              passing the wrong level
                doesn't match (FAILED - 586)
              passing the wrong state
                doesn't match (FAILED - 587)
              passing the wrong chamber
                doesn't match (FAILED - 588)
      Los Angeles
        city code 'Los Angeles'
          behaves like a District finder
            matches
              passing the us_code
                matches (FAILED - 589)
              passing the District's exact name
                matches (FAILED - 590)
              passing in matching names
                matches (FAILED - 591)
              passing the District's name, downcased
                matches (FAILED - 592)
              passing the District's name with extra dashes
                matches (FAILED - 593)
              passing the District's name without extra words
                matches (FAILED - 594)
              passing the District's name without dashes
                matches (FAILED - 595)
            mismatches
              passing the wrong name
                doesn't match (FAILED - 596)
              with the right name
                passing the wrong level
                  doesn't match (FAILED - 597)
                passing the wrong state
                  doesn't match (FAILED - 598)
                passing the wrong chamber
                  doesn't match (FAILED - 599)
        city code 'L.A.'
          behaves like a District finder
            matches
              passing the us_code
                matches (FAILED - 600)
              passing the District's exact name
                matches (FAILED - 601)
              passing in matching names
                matches (FAILED - 602)
              passing the District's name, downcased
                matches (FAILED - 603)
              passing the District's name with extra dashes
                matches (FAILED - 604)
              passing the District's name without extra words
                matches (FAILED - 605)
              passing the District's name without dashes
                matches (FAILED - 606)
            mismatches
              passing the wrong name
                doesn't match (FAILED - 607)
              with the right name
                passing the wrong level
                  doesn't match (FAILED - 608)
                passing the wrong state
                  doesn't match (FAILED - 609)
                passing the wrong chamber
                  doesn't match (FAILED - 610)
        city code 'LA'
          behaves like a District finder
            matches
              passing the us_code
                matches (FAILED - 611)
              passing the District's exact name
                matches (FAILED - 612)
              passing in matching names
                matches (FAILED - 613)
              passing the District's name, downcased
                matches (FAILED - 614)
              passing the District's name with extra dashes
                matches (FAILED - 615)
              passing the District's name without extra words
                matches (FAILED - 616)
              passing the District's name without dashes
                matches (FAILED - 617)
            mismatches
              passing the wrong name
                doesn't match (FAILED - 618)
              with the right name
                passing the wrong level
                  doesn't match (FAILED - 619)
                passing the wrong state
                  doesn't match (FAILED - 620)
                passing the wrong chamber
                  doesn't match (FAILED - 621)
      San Jose
        city code 'San Jose'
          behaves like a District finder
            matches
              passing the us_code
                matches (FAILED - 622)
              passing the District's exact name
                matches (FAILED - 623)
              passing in matching names
                matches (FAILED - 624)
              passing the District's name, downcased
                matches (FAILED - 625)
              passing the District's name with extra dashes
                matches (FAILED - 626)
              passing the District's name without extra words
                matches (FAILED - 627)
              passing the District's name without dashes
                matches (FAILED - 628)
            mismatches
              passing the wrong name
                doesn't match (FAILED - 629)
              with the right name
                passing the wrong level
                  doesn't match (FAILED - 630)
                passing the wrong state
                  doesn't match (FAILED - 631)
                passing the wrong chamber
                  doesn't match (FAILED - 632)
        city code 'SJ'
          behaves like a District finder
            matches
              passing the us_code
                matches (FAILED - 633)
              passing the District's exact name
                matches (FAILED - 634)
              passing in matching names
                matches (FAILED - 635)
              passing the District's name, downcased
                matches (FAILED - 636)
              passing the District's name with extra dashes
                matches (FAILED - 637)
              passing the District's name without extra words
                matches (FAILED - 638)
              passing the District's name without dashes
                matches (FAILED - 639)
            mismatches
              passing the wrong name
                doesn't match (FAILED - 640)
              with the right name
                passing the wrong level
                  doesn't match (FAILED - 641)
                passing the wrong state
                  doesn't match (FAILED - 642)
                passing the wrong chamber
                  doesn't match (FAILED - 643)
      DC
        city code 'Washington DC'
          behaves like a District finder
            matches
              passing the us_code
                matches (FAILED - 644)
              passing the District's exact name
                matches (FAILED - 645)
              passing in matching names
                matches (FAILED - 646)
              passing the District's name, downcased
                matches (FAILED - 647)
              passing the District's name with extra dashes
                matches (FAILED - 648)
              passing the District's name without extra words
                matches (FAILED - 649)
              passing the District's name without dashes
                matches (FAILED - 650)
            mismatches
              passing the wrong name
                doesn't match (FAILED - 651)
              with the right name
                passing the wrong level
                  doesn't match (FAILED - 652)
                passing the wrong state
                  doesn't match (FAILED - 653)
                passing the wrong chamber
                  doesn't match (FAILED - 654)
        city code 'D.C.'
          behaves like a District finder
            matches
              passing the us_code
                matches (FAILED - 655)
              passing the District's exact name
                matches (FAILED - 656)
              passing in matching names
                matches (FAILED - 657)
              passing the District's name, downcased
                matches (FAILED - 658)
              passing the District's name with extra dashes
                matches (FAILED - 659)
              passing the District's name without extra words
                matches (FAILED - 660)
              passing the District's name without dashes
                matches (FAILED - 661)
            mismatches
              passing the wrong name
                doesn't match (FAILED - 662)
              with the right name
                passing the wrong level
                  doesn't match (FAILED - 663)
                passing the wrong state
                  doesn't match (FAILED - 664)
                passing the wrong chamber
                  doesn't match (FAILED - 665)
      NYC
        city code 'New York City'
          behaves like a District finder
            matches
              passing the us_code
                matches (FAILED - 666)
              passing the District's exact name
                matches (FAILED - 667)
              passing in matching names
                matches (FAILED - 668)
              passing the District's name, downcased
                matches (FAILED - 669)
              passing the District's name with extra dashes
                matches (FAILED - 670)
              passing the District's name without extra words
                matches (FAILED - 671)
              passing the District's name without dashes
                matches (FAILED - 672)
            mismatches
              passing the wrong name
                doesn't match (FAILED - 673)
              with the right name
                passing the wrong level
                  doesn't match (FAILED - 674)
                passing the wrong state
                  doesn't match (FAILED - 675)
                passing the wrong chamber
                  doesn't match (FAILED - 676)
        city code 'NYC'
          behaves like a District finder
            matches
              passing the us_code
                matches (FAILED - 677)
              passing the District's exact name
                matches (FAILED - 678)
              passing in matching names
                matches (FAILED - 679)
              passing the District's name, downcased
                matches (FAILED - 680)
              passing the District's name with extra dashes
                matches (FAILED - 681)
              passing the District's name without extra words
                matches (FAILED - 682)
              passing the District's name without dashes
                matches (FAILED - 683)
            mismatches
              passing the wrong name
                doesn't match (FAILED - 684)
              with the right name
                passing the wrong level
                  doesn't match (FAILED - 685)
                passing the wrong state
                  doesn't match (FAILED - 686)
                passing the wrong chamber
                  doesn't match (FAILED - 687)
    if a district isn't returned
      for the US Senate
        doesn't add to .problems (FAILED - 688)
      for the US House
        adds to .problems (FAILED - 689)

CiceroUSDistrictImporter
  with a valid NewDistrict
    at state-level
      with a matching District
        updates the geometry column (FAILED - 690)
        if the existing District lacks a us_code
          updates the code (FAILED - 691)
        with an existing non-zero fips code
          doesn't overwrite it (FAILED - 692)
      with :overwrite_district_pids => true
        updates the geometry column (FAILED - 693)
        if the existing District lacks a us_code
          updates the code (FAILED - 694)
        with an existing non-zero fips code
          doesn't overwrite it (FAILED - 695)
      without a matching District
        imports the StateHouseDistrict (FAILED - 696)
    at national-level
      with a matching District
        updates the geometry column (FAILED - 697)
        if the existing District lacks a us_code
          updates the code (FAILED - 698)
        if the existing District has a 000 fips_code
          updates the fips_code (FAILED - 699)
      without a matching District
        imports the CongressionalDistrict (FAILED - 700)
    at city council level
      with a matching District
        updates the geometry column (FAILED - 701)
        if the existing District lacks a us_code
          updates the code (FAILED - 702)
      without a matching District
        imports the CongressionalDistrict (FAILED - 703)
    with an invalid .district_t column
      doesn't import (FAILED - 704)
    with :validate_dates => true
      with a past valid_to date
        doesn't import (FAILED - 705)
      with a future valid_to date
        imports (FAILED - 706)
      with a past valid_from date
        imports (FAILED - 707)
      with a future valid_from date
        doesn't import (FAILED - 708)

Cicero US Imports
  USCommitteeMatcher
    setup
      when committee has a cicero_committee_id that is in the CSV
        behaves like a match for committee
          the Committee Matcher
            should have no :not_found problems (FAILED - 709)
      when committee does not have a cicero_committee_id in the CSV
        behaves like a MISMATCH for committee
          the Committee Matcher
            should have :not_found problems (FAILED - 710)
      when committee has a nil cicero_committee_id
        behaves like a MISMATCH for committee
          the Committee Matcher
            should have :not_found problems (FAILED - 711)
    with a Committee
      import_and_update_committees
        when the committee is new
          the committee
            has J constituency and state CT (FAILED - 712)
        when the committee already exists (by cicero_committee_id)
          updates the name of the existing committee (FAILED - 713)
      inactivate_old_committees
        a committee in the .CSV
          is not inactive (FAILED - 714)
        a committee not in the .CSV
          from the US
            inactivates committees (FAILED - 715)
          outside the US
            is not inactive (FAILED - 716)
      when we support sub-committee relationships
        import_committee_relationships
          with all active committees
            relates parent to child and creates a historical_recipient_relation (FAILED - 717)
          with an active and inactive committees
            uses only active committees when comparing cicero codes (FAILED - 718)
        clean_committee_relationships
          destroys RecipientRelations for active committees not in Cicero (FAILED - 719)
          destroys RecipientRelations for inactive committees that are in Cicero (FAILED - 720)
          does not destroy active committees with cicero_committee_ids on import (FAILED - 721)
          does not destroy a RecipientRelation that is outside America (FAILED - 722)
  CiceroUSAssignmentImporter
    with a Recipient with a .cicero_official_id
      with new Committee assignments
        joins the Committee, removes the old associations, and appropriately creates/removes historical_recipient_relations (FAILED - 723)
  Importing
    CiceroUSCouncilsImporter
      with two existing US City Councilmembers
        behaves like a Recipient record updater and replacer
          with updatable, replaceable, and new Recipients
            matching
              schedules the updatable Recipient for update (FAILED - 724)
              schedules the replaceable Recipient for replacement (FAILED - 725)
            importing
              deactivates the replaceable Recipient and removes their committee relationships (FAILED - 726)
              updates the updatable Recipient (FAILED - 727)
              imports the new Recipient (FAILED - 728)
              records the cicero_official_id on the updatable and new Recipients (FAILED - 729)
      when it clears CouncilMembers
        with US Reps, Senators, and State Reps
          importing US City Councils
            doesn't deactivate them (FAILED - 730)
        with CA and AU recipients
          importing US City Councils
            doesn't deactivate them (FAILED - 731)
    US Recipient Importer
      with two existing US Reps
        behaves like a Recipient record updater and replacer
          with updatable, replaceable, and new Recipients
            matching
              schedules the updatable Recipient for update (FAILED - 732)
              schedules the replaceable Recipient for replacement (FAILED - 733)
            importing
              deactivates the replaceable Recipient and removes their committee relationships (FAILED - 734)
              updates the updatable Recipient (FAILED - 735)
              imports the new Recipient (FAILED - 736)
              records the cicero_official_id on the updatable and new Recipients (FAILED - 737)
      with two existing US Senators
        behaves like a Recipient record updater and replacer
          with updatable, replaceable, and new Recipients
            matching
              schedules the updatable Recipient for update (FAILED - 738)
              schedules the replaceable Recipient for replacement (FAILED - 739)
            importing
              deactivates the replaceable Recipient and removes their committee relationships (FAILED - 740)
              updates the updatable Recipient (FAILED - 741)
              imports the new Recipient (FAILED - 742)
              records the cicero_official_id on the updatable and new Recipients (FAILED - 743)
      with two existing State-level Reps
        behaves like a Recipient record updater and replacer
          with updatable, replaceable, and new Recipients
            matching
              schedules the updatable Recipient for update (FAILED - 744)
              schedules the replaceable Recipient for replacement (FAILED - 745)
            importing
              deactivates the replaceable Recipient and removes their committee relationships (FAILED - 746)
              updates the updatable Recipient (FAILED - 747)
              imports the new Recipient (FAILED - 748)
              records the cicero_official_id on the updatable and new Recipients (FAILED - 749)
      with two existing State-level Senators
        behaves like a Recipient record updater and replacer
          with updatable, replaceable, and new Recipients
            matching
              schedules the updatable Recipient for update (FAILED - 750)
              schedules the replaceable Recipient for replacement (FAILED - 751)
            importing
              deactivates the replaceable Recipient and removes their committee relationships (FAILED - 752)
              updates the updatable Recipient (FAILED - 753)
              imports the new Recipient (FAILED - 754)
              records the cicero_official_id on the updatable and new Recipients (FAILED - 755)
      with two existing State Governors
        behaves like a Recipient record updater and replacer
          with updatable, replaceable, and new Recipients
            matching
              schedules the updatable Recipient for update (FAILED - 756)
              schedules the replaceable Recipient for replacement (FAILED - 757)
            importing
              deactivates the replaceable Recipient and removes their committee relationships (FAILED - 758)
              updates the updatable Recipient (FAILED - 759)
              imports the new Recipient (FAILED - 760)
              records the cicero_official_id on the updatable and new Recipients (FAILED - 761)
      with a vacated Governor
        deactivates the vacated Governor (FAILED - 762)
      with a vacated seat (name VACANT) and an updatable seat
        from different districts
          deactivates the vacated Recipient (FAILED - 763)
          updates the updatable Recipient (FAILED - 764)
        from the same district
          deactivates the vacated Recipient (FAILED - 765)
          updates the updatable Recipient (FAILED - 766)
      with a vacated seat (name VACANT) and an empty seat
        .all_problems
          does not report party or import failures (FAILED - 767)
      with existing reps swapping seats
        importing
          swaps seats (FAILED - 768)
      with a State Rep changing to a State Senator
        importing
          changes to a State Senator (FAILED - 769)
      for other chambers and levels
        with a national executive row
          doesn't currently check, process, or import it (FAILED - 770)
        with a non-Governor state executive row
          doesn't currently check, process, or import it (FAILED - 771)
        with a city council row
          doesn't currently check, process, or import it (FAILED - 772)
      for US territories that aren't states
        with a Guam row
          doesn't currently check, process, or import it (FAILED - 773)
      for invalid timestamps
        with an invalid valid_from row
          doesn't currently check, process, or import it (FAILED - 774)
        with an invalid valid_to row
          doesn't currently check, process, or import it (FAILED - 775)
        with a valid row
          processes it (FAILED - 776)
        with a valid_to row from December of the same year
          processes it (FAILED - 777)
        with a valid_from row ending in -2 and date ending in -12
          processes it (FAILED - 778)
        with monthly precision
          with a valid_to row from the same month
            processes it (FAILED - 779)
          with a valid_to row from the month before
            doesn't currently check, process, or import it (FAILED - 780)
          with a valid_from row from the same month
            processes it (FAILED - 781)
          with a valid_from row from the next month
            doesn't currently check, process, or import it (FAILED - 782)
        with yearly precision
          with a valid_to row from the same year
            processes it (FAILED - 783)
          with a valid_to row from the year before
            doesn't currently check, process, or import it (FAILED - 784)
          with a valid_from row from the same year
            processes it (FAILED - 785)
          with a valid_from row from the next year
            doesn't currently check, process, or import it (FAILED - 786)
        time_greater_than_or_eq
          for times ["2022-11", "2022-2"]
            should equal true
          for times ["2022-11-12", "2022-9-12"]
            should equal true
          for times ["2022-1-13", "2022-1-2"]
            should equal true
          for times ["2022-3-30", "2022-3-3"]
            should equal true
          for times ["2022-3", "2022-3"]
            should equal true
          for times ["2022-2", "2022-11"]
            should equal false
          for times ["2022-9-12", "2022-11-12"]
            should equal false
          for times ["2022-1-2", "2022-1-13"]
            should equal false
          for times ["2022-3-3", "2022-3-30"]
            should equal false
        time_less_than_or_eq
          for times ["2022-2", "2022-11"]
            should equal true
          for times ["2022-9-12", "2022-11-12"]
            should equal true
          for times ["2022-1-2", "2022-1-13"]
            should equal true
          for times ["2022-3-3", "2022-3-30"]
            should equal true
          for times ["2022-3", "2022-3"]
            should equal true
          for times ["2022-11", "2022-2"]
            should equal false
          for times ["2022-11-12", "2022-9-12"]
            should equal false
          for times ["2022-1-13", "2022-1-2"]
            should equal false
          for times ["2022-3-30", "2022-3-3"]
            should equal false
      testing for problems
        with full CT and AL state data
          importing only_states => ['CT']
            is successful (FAILED - 787)
            doesn't deactivate the AL reps (FAILED - 788)
        with CA and AU recipients
          importing for the US
            doesn't deactivate them (FAILED - 789)
        with City Council and Custom recipients
          importing
            doesn't deactivate them (FAILED - 790)
        with Recipients of the same level and chamber, with expired cicero_codes
          importing
            deactivates them (FAILED - 791)
        USRecipientImporter.all_problems
          with party that does not exist
            throws a party_matcher error (FAILED - 792)
          with row for vacant seat
            does not throw a party_matcher error (FAILED - 793)
      with an existing US Rep with a cicero code
        behaves like a US Cicero Recipient name updater
          behaves like US Cicero Recipient first_name and last_name updater
            with updatable US Cicero Recipients
              behaves like a first_name and last_name updater
                when overwrite lastname is true
                  updates the last_name of the updatable Recipient (FAILED - 794)
                when overwrite firstname is false
                  does not update the first_name of the updatable Recipient (FAILED - 795)
          behaves like US Cicero Recipient first_name and last_name updater
            with updatable US Cicero Recipients
              behaves like a first_name and last_name updater
                when overwrite lastname is false
                  does not update the last_name of the updatable Recipient (FAILED - 796)
                when overwrite firstname is true
                  updates the first_name of the updatable Recipient (FAILED - 797)
          behaves like US Cicero Recipient first_name and last_name updater
            with updatable US Cicero Recipients
              behaves like a first_name and last_name updater
                when overwrite lastname is true
                  updates the last_name of the updatable Recipient (FAILED - 798)
                when overwrite firstname is true
                  updates the first_name of the updatable Recipient (FAILED - 799)
          behaves like US Cicero Recipient first_name and last_name updater
            with updatable US Cicero Recipients
              behaves like a first_name and last_name updater
                when overwrite lastname is false
                  does not update the last_name of the updatable Recipient (FAILED - 800)
                when overwrite firstname is false
                  does not update the first_name of the updatable Recipient (FAILED - 801)
      for US Reps
        behaves like a Recipient record matcher
          matching
            if a rep already exists
              with the same cicero_code
                matches (FAILED - 802)
              with the same name, state, and district
                matches (FAILED - 803)
              with a different name
                doesn't match (FAILED - 804)
              but is inactive
                doesn't match (FAILED - 805)
        behaves like an Address and field updater
          importing
            when we support Facebook addresses (PENDING: No reason given)
            without a knowhwho code
              updates the cicero code (FAILED - 806)
            with a official_id
              updates the cicero_official_id (FAILED - 807)
            without a twitter handle
              creates the twitter handle (FAILED - 808)
            with a twitter handle
              normally
                updates the twitter handle (FAILED - 809)
              with ignore_imports_flg = true
                doesn't update the twitter handle (FAILED - 810)
            without a Bioguide id
              doesn't import Bioguide id (FAILED - 811)
            with a Bioguide id
              imports the Bioguide id (FAILED - 812)
            with a phone number
              by default
                updates the phone handle (FAILED - 813)
              with ignore_imports_flg = true
                doesn't update the phone number (FAILED - 814)
            without a portrait
              creates the portrait (FAILED - 815)
            with a portrait
              updates the portrait (FAILED - 816)
            without a WebMailAddress
              creates the WebMailAddress (FAILED - 817)
            with a WebMailAddress
              by default
                updates the WebMailAddress (FAILED - 818)
              with :addresses_options => {:except => ['webform']}
                doesn't update the WebMailAddress (FAILED - 819)
              with ignore_imports_flg = true
                doesn't update the WebMailAddress (FAILED - 820)
        behaves like a statewise updater for
          importing :except_states => [state]
            doesn't import to the limiting state (FAILED - 821)
          importing :only_states => [state]
            imports to the limiting state (FAILED - 822)
      for US Senators
        behaves like a Recipient record matcher
          matching
            if a rep already exists
              with the same cicero_code
                matches (FAILED - 823)
              with the same name, state, and district
                matches (FAILED - 824)
              with a different name
                doesn't match (FAILED - 825)
              but is inactive
                doesn't match (FAILED - 826)
        behaves like an Address and field updater
          importing
            when we support Facebook addresses (PENDING: No reason given)
            without a knowhwho code
              updates the cicero code (FAILED - 827)
            with a official_id
              updates the cicero_official_id (FAILED - 828)
            without a twitter handle
              creates the twitter handle (FAILED - 829)
            with a twitter handle
              normally
                updates the twitter handle (FAILED - 830)
              with ignore_imports_flg = true
                doesn't update the twitter handle (FAILED - 831)
            without a Bioguide id
              doesn't import Bioguide id (FAILED - 832)
            with a Bioguide id
              imports the Bioguide id (FAILED - 833)
            with a phone number
              by default
                updates the phone handle (FAILED - 834)
              with ignore_imports_flg = true
                doesn't update the phone number (FAILED - 835)
            without a portrait
              creates the portrait (FAILED - 836)
            with a portrait
              updates the portrait (FAILED - 837)
            without a WebMailAddress
              creates the WebMailAddress (FAILED - 838)
            with a WebMailAddress
              by default
                updates the WebMailAddress (FAILED - 839)
              with :addresses_options => {:except => ['webform']}
                doesn't update the WebMailAddress (FAILED - 840)
              with ignore_imports_flg = true
                doesn't update the WebMailAddress (FAILED - 841)
        behaves like a statewise updater for
          importing :except_states => [state]
            doesn't import to the limiting state (FAILED - 842)
          importing :only_states => [state]
            imports to the limiting state (FAILED - 843)
      for State-level Reps
        behaves like a Recipient record matcher
          matching
            if a rep already exists
              with the same cicero_code
                matches (FAILED - 844)
              with the same name, state, and district
                matches (FAILED - 845)
              with a different name
                doesn't match (FAILED - 846)
              but is inactive
                doesn't match (FAILED - 847)
        behaves like an Address and field updater
          importing
            when we support Facebook addresses (PENDING: No reason given)
            without a knowhwho code
              updates the cicero code (FAILED - 848)
            with a official_id
              updates the cicero_official_id (FAILED - 849)
            without a twitter handle
              creates the twitter handle (FAILED - 850)
            with a twitter handle
              normally
                updates the twitter handle (FAILED - 851)
              with ignore_imports_flg = true
                doesn't update the twitter handle (FAILED - 852)
            without a Bioguide id
              doesn't import Bioguide id (FAILED - 853)
            with a Bioguide id
              imports the Bioguide id (FAILED - 854)
            with a phone number
              by default
                updates the phone handle (FAILED - 855)
              with ignore_imports_flg = true
                doesn't update the phone number (FAILED - 856)
            without a portrait
              creates the portrait (FAILED - 857)
            with a portrait
              updates the portrait (FAILED - 858)
            without a WebMailAddress
              creates the WebMailAddress (FAILED - 859)
            with a WebMailAddress
              by default
                updates the WebMailAddress (FAILED - 860)
              with :addresses_options => {:except => ['webform']}
                doesn't update the WebMailAddress (FAILED - 861)
              with ignore_imports_flg = true
                doesn't update the WebMailAddress (FAILED - 862)
        behaves like a statewise updater for
          importing :except_states => [state]
            doesn't import to the limiting state (FAILED - 863)
          importing :only_states => [state]
            imports to the limiting state (FAILED - 864)
      for State-level Senators
        behaves like a Recipient record matcher
          matching
            if a rep already exists
              with the same cicero_code
                matches (FAILED - 865)
              with the same name, state, and district
                matches (FAILED - 866)
              with a different name
                doesn't match (FAILED - 867)
              but is inactive
                doesn't match (FAILED - 868)
        behaves like an Address and field updater
          importing
            when we support Facebook addresses (PENDING: No reason given)
            without a knowhwho code
              updates the cicero code (FAILED - 869)
            with a official_id
              updates the cicero_official_id (FAILED - 870)
            without a twitter handle
              creates the twitter handle (FAILED - 871)
            with a twitter handle
              normally
                updates the twitter handle (FAILED - 872)
              with ignore_imports_flg = true
                doesn't update the twitter handle (FAILED - 873)
            without a Bioguide id
              doesn't import Bioguide id (FAILED - 874)
            with a Bioguide id
              imports the Bioguide id (FAILED - 875)
            with a phone number
              by default
                updates the phone handle (FAILED - 876)
              with ignore_imports_flg = true
                doesn't update the phone number (FAILED - 877)
            without a portrait
              creates the portrait (FAILED - 878)
            with a portrait
              updates the portrait (FAILED - 879)
            without a WebMailAddress
              creates the WebMailAddress (FAILED - 880)
            with a WebMailAddress
              by default
                updates the WebMailAddress (FAILED - 881)
              with :addresses_options => {:except => ['webform']}
                doesn't update the WebMailAddress (FAILED - 882)
              with ignore_imports_flg = true
                doesn't update the WebMailAddress (FAILED - 883)
        behaves like a statewise updater for
          importing :except_states => [state]
            doesn't import to the limiting state (FAILED - 884)
          importing :only_states => [state]
            imports to the limiting state (FAILED - 885)
      for US Governors
        behaves like a Recipient record matcher
          matching
            if a rep already exists
              with the same cicero_code
                matches (FAILED - 886)
              with the same name, state, and district
                matches (FAILED - 887)
              with a different name
                doesn't match (FAILED - 888)
              but is inactive
                doesn't match (FAILED - 889)
        behaves like an Address and field updater
          importing
            when we support Facebook addresses (PENDING: No reason given)
            without a knowhwho code
              updates the cicero code (FAILED - 890)
            with a official_id
              updates the cicero_official_id (FAILED - 891)
            without a twitter handle
              creates the twitter handle (FAILED - 892)
            with a twitter handle
              normally
                updates the twitter handle (FAILED - 893)
              with ignore_imports_flg = true
                doesn't update the twitter handle (FAILED - 894)
            without a Bioguide id
              doesn't import Bioguide id (FAILED - 895)
            with a Bioguide id
              imports the Bioguide id (FAILED - 896)
            with a phone number
              by default
                updates the phone handle (FAILED - 897)
              with ignore_imports_flg = true
                doesn't update the phone number (FAILED - 898)
            without a portrait
              creates the portrait (FAILED - 899)
            with a portrait
              updates the portrait (FAILED - 900)
            without a WebMailAddress
              creates the WebMailAddress (FAILED - 901)
            with a WebMailAddress
              by default
                updates the WebMailAddress (FAILED - 902)
              with :addresses_options => {:except => ['webform']}
                doesn't update the WebMailAddress (FAILED - 903)
              with ignore_imports_flg = true
                doesn't update the WebMailAddress (FAILED - 904)
        behaves like a statewise updater for
          importing :except_states => [state]
            doesn't import to the limiting state (FAILED - 905)
          importing :only_states => [state]
            imports to the limiting state (FAILED - 906)
      import
        with the :overwrite_firstname => true flag
          without a preferred_name
            records the first_name (FAILED - 907)
          with a preferred_name
            records the preferred_name (FAILED - 908)
      pre_process_phone_and_fax
        for a state representative row
          from a state where we use primary phones
            uses primary_phone_1
            uses primary_phone_1
            uses primary_phone_1
            uses primary_phone_1
            uses primary_phone_1
            uses primary_phone_1
            uses primary_phone_1
            uses primary_phone_1
            uses primary_phone_1
            uses primary_phone_1
            uses primary_phone_1
          from a different state
            uses secondary_phone_1
        for other rows
          uses secondary_phone_1
        with a phone field with an extension
          removes the extension
      deactivate_non_cicero_us_reps
        with cicero reps and knowwho reps
          in US Congress or State Legislatures
            deactivates non-Cicero reps (FAILED - 909)
            doesn't deactivate Cicero reps (FAILED - 910)
          other offices
            doesn't deactivate (FAILED - 911)
          custom recipients
            doesn't deactivate (FAILED - 912)

CiceroUSPartyImporter
  .import
    with an existing Party
      doesn't import
    without an existing Party
      imports

US City Council Imports
  USCityCouncilDistrictMatcher
    .locate_district
      with a CityCouncilDistrict San Jose 09
        behaves like a finder returning matches for
          should have no :district_without_id problems (FAILED - 913)
        behaves like a finder returning MISMATCHES for
          should have no :district_without_id problems (FAILED - 914)
      with a CityCouncilDistrict L.A. District 2
        behaves like a finder returning matches for
          should have no :district_without_id problems (FAILED - 915)
        behaves like a finder returning MISMATCHES for
          should have no :district_without_id problems (FAILED - 916)
      with a Schoolboard District 11
        with a CityCouncilDistrict San Jose District 09
          behaves like a finder returning MISMATCHES for
            should have no :district_without_id problems (FAILED - 917)
  USCityCouncilRecipientImporter
    with two existing City CouncilMembers with districts
      behaves like a City Council Recipient record updater and replacer
        with updatable, replaceable, and new Recipients
          matching
            schedules the updatable Recipient for update (FAILED - 918)
            schedules the replaceable Recipient for replacement (FAILED - 919)
          importing
            deactivates the replaceable Recipient (FAILED - 920)
            updates the updatable Recipient (FAILED - 921)
            imports the new Recipient as a CouncilMember (FAILED - 922)
    with two existing At-large City CouncilMembers
      behaves like a City Council Recipient record updater and replacer
        with updatable, replaceable, and new Recipients
          matching
            schedules the updatable Recipient for update (FAILED - 923)
            schedules the replaceable Recipient for replacement (FAILED - 924)
          importing
            deactivates the replaceable Recipient (FAILED - 925)
            updates the updatable Recipient (FAILED - 926)
            imports the new Recipient as a CouncilMember (FAILED - 927)
    a record that isn't type LEG and Legislative Municipal
      importing
        isn't imported (FAILED - 928)
    with an existing At-large CouncilMember for San Jose
      importing new At-large CouncilMembers from Los Angeles
        importing
          doesn't change the San Jose city CouncilMember (FAILED - 929)
      importing new At-large CouncilMembers from San Jose
        importing
          changes the San Jose city CouncilMember (FAILED - 930)
    supplying an array of 'only_cities'
      importing
        shouldn't import or update other cities (FAILED - 931)
    supplying an array of 'only_states'
      importing
        shouldn't import or update other states (FAILED - 932)
    when there's a problem importing
      with a bad CouncilMember name
        importing
          reports a :row_checker problem (FAILED - 933)
          doesn't create the CouncilMember (FAILED - 934)
      with a nonexistent District number
        importing
          reports a :row_checker problem (FAILED - 935)
          doesn't create the CouncilMember (FAILED - 936)

ImportCiceroUSLegislatorProfiles
  with the default (no record parameter)
    does not update any fields (FAILED - 937)
  with 'record: true'
    updates the recipient's title field (FAILED - 938)
    creates a RecipientBio (FAILED - 939)
    creates 2 RecipientOffices (FAILED - 940)
    fills in the RecipientOffice fields (FAILED - 941)
    creates 2 Staffers (FAILED - 942)
    fills in the Staffer fields (FAILED - 943)
    with an existing RecipientBio
      doesn't create a new RecipientBio (FAILED - 944)
      updates the RecipientBio (FAILED - 945)
      doesn't overwrite an existing value with a blank one (FAILED - 946)
    when we don't have office_location values
      assigns Staffers to the main office (FAILED - 947)
    when we have an office_location
      office_location=CAPITOL
        assigns Staffers to the main office (FAILED - 948)
      office_location=DISTRICT
        assigns Staffers to the main office (FAILED - 949)
    when the same PID appears twice
      creates one Staffer for each (FAILED - 950)
  clear_existing_profiles
    for active Recipients
      should not destroy recipient bios, staffers, and recipient offices (FAILED - 951)
      with :clear_active => true
        should destroy recipient bios, staffers, and recipient offices (FAILED - 952)
        doesn't destroy the recipients (FAILED - 953)
    for inactive Recipients
      should destroy all recipient bios, staffers, and recipient offices (FAILED - 954)
      doesn't destroy the recipients (FAILED - 955)

deactivate_recipients_without_cicero_codes
  with is_ready_to_save = true
    does nothing to a recipient with a cicero code (FAILED - 956)
    deactivates recipient without cicero code (FAILED - 957)
  with is_ready_to_save = false
    does nothing to a recipient with a cicero code (FAILED - 958)
    does nothing to a recipient without cicero code (FAILED - 959)

UK Recipient Importer
  with two existing UK Representatives
    behaves like an UK Recipient record updater and replacer
      with updatable, replaceable, and new Recipients
        matching
          schedules the updatable Recipient for update (FAILED - 960)
          schedules the replaceable Recipient for replacement (FAILED - 961)
        importing
          deactivates the replaceable Recipient (FAILED - 962)
          updates the updatable Recipient (FAILED - 963)
          imports the new Recipient (FAILED - 964)
          imports the recipient with correct state even though district_state is empty (FAILED - 965)
          assigns the recipient to the correct office (FAILED - 966)
  with an existing UK Representatives with a cicero code
    behaves like UK Recipient first_name and last_name updater
      with updatable UK Recipients
        behaves like a first_name and last_name updater
          when overwrite lastname is true
            updates the last_name of the updatable Recipient (FAILED - 967)
          when overwrite firstname is true
            updates the first_name of the updatable Recipient (FAILED - 968)
  with a vacated seat (name VACANT) and an updatable seat
    from different districts
      deactivates the vacated Recipient (FAILED - 969)
      updates the updatable Recipient (FAILED - 970)
  with existing reps swapping seats
    importing
      swaps seats (FAILED - 971)
  testing for problems
    with UK-ENG and UK-SCT data
      importing only_states => ['UK-SCT']
        is successful (FAILED - 972)
    UKRecipientImporter.all_problems
      with party that does not exist
        throws a party_matcher error (FAILED - 973)
      with row for vacant seat
        does not throw a party_matcher error (FAILED - 974)
  an Address and field updater for UK Reps
    importing
      without a cicero code
        updates the cicero code (FAILED - 975)
      with a new official_id
        updates the official_id (FAILED - 976)
      with a phone number
        by default
          updates the phone handle (FAILED - 977)
        with ignore_imports_flg = true
          doesn't update the phone number (FAILED - 978)
      without a portrait
        creates the portrait (FAILED - 979)
      with a portrait
        updates the portrait (FAILED - 980)
      without a WebMailAddress
        creates the WebMailAddress (FAILED - 981)
      with a WebMailAddress
        by default
          updates the WebMailAddress (FAILED - 982)
        with :addresses_options => {:except => ['webform']}
          doesn't update the WebMailAddress (FAILED - 983)
        with ignore_imports_flg = true
          doesn't update the WebMailAddress (FAILED - 984)

UKDistrictImporter
  with a valid NewDistrict
    at national-level
      LOWER
        with a matching District
          updates the geometry column (FAILED - 985)
          behaves like an UK district importer
            updates the geometry column (FAILED - 986)
            without an uk_code
              updates the uk_code (FAILED - 987)
            with an uk_code
              with the overwrite flag
                overwrites the old uk_code (FAILED - 988)
              without the overwrite flag
                doesn't overwrite the uk_code (FAILED - 989)
          if the existing District lacks a uk_code
            updates the code (FAILED - 990)
        without a matching District
          imports the CongressionalDistrict (FAILED - 991)
    with an invalid .district_t column
      doesn't import (FAILED - 992)

UKDistrictMatcher
  .find_district
    for an existing UK-ENG CongressionalDistrict with a .uk_code
      at commonwealth-level with state=UK-ENG
        passing the uk_code
          matches (FAILED - 993)
        passing the District's exact name
          matches (FAILED - 994)
        passing the District's name, downcase
          matches (FAILED - 995)
        passing the District's name with a double--dash
          matches (FAILED - 996)
        passing a different name
          doesn't match (FAILED - 997)
      at comm-level for a different state
        passing the District's exact name
          doesn't match (FAILED - 998)
    if a district isn't returned
      for the Commonwealth Upper
        doesn't add to .problems (FAILED - 999)
      for the Commonwealth Lower
        adds to .problems (FAILED - 1000)

UKPartyImporter
  .import
    with an existing Party
      doesn't import
    without an existing Party
      imports

US Imports
  USCommitteeMatcher
    setup
      when committee has a knowwho_comid that is in the CSV
        behaves like a match for committee
          the Committee Matcher
            should have no :not_found problems (FAILED - 1001)
      when committee does not have a knowwho_comid in the CSV
        behaves like a MISMATCH for committee
          the Committee Matcher
            should have :not_found problems (FAILED - 1002)
      when committee has a nil knowwho_comid
        behaves like a MISMATCH for committee
          the Committee Matcher
            should have :not_found problems (FAILED - 1003)
    with two related Committees
      import_and_update_committees
        when both committees are new
          the child committee
            has J constituency, votesmart != 0, and state CT (FAILED - 1004)
          the parent committee
            has J constituency, votesmart = 0, and state CT (FAILED - 1005)
        when one of the two committees already exists (by knowwho_comid)
          updates the name of the existing committee (FAILED - 1006)
      inactivate_old_committees
        inactivates committees (FAILED - 1007)
      import_committee_relationships
        with all active committees
          relates parent to child and creates a historical_recipient_relation (FAILED - 1008)
        with an active and inactive committees
          uses only active committees when comparing knowwho codes (FAILED - 1009)
      clean_committee_relationships
        destroys RecipientRelations for active committees not in KnowWho (FAILED - 1010)
        destroys RecipientRelations for inactive committees that are in KnowWho (FAILED - 1011)
        does not destroy active committees with knowwho codes in knowwho import (FAILED - 1012)
        does not destroy a RecipientRelation that is outside America (FAILED - 1013)
  USAssignmentImporter
    with new committee and subcommittee assignments
      joins the Subcommittee, removes the old association, and appropriately creates/removes historical_recipient_relations (FAILED - 1014)
    with new CommitteeTerritoryRecipient object assignments (assignments for recipients from territories)
      destroys all old CommitteeTerritoryRecipient objects and makes new ones (FAILED - 1015)
  USDistrictMatcher
    state house
      Vermont House Chittenden 04-01
        behaves like a match for district
          the District Matcher
            should have no :district_without_id problems (FAILED - 1016)
        behaves like a MISMATCH for district
          the District Matcher
            should have :district_without_id problems (FAILED - 1017)
        behaves like a MISMATCH for district
          the District Matcher
            should have :district_without_id problems (FAILED - 1018)
        behaves like a MISMATCH for district
          the District Matcher
            should have :district_without_id problems (FAILED - 1019)
        behaves like a MISMATCH for district
          the District Matcher
            should have :district_without_id problems (FAILED - 1020)
      Vermont House Orange Washington Addison
        behaves like a match for district
          the District Matcher
            should have no :district_without_id problems (FAILED - 1021)
        behaves like a MISMATCH for district
          the District Matcher
            should have :district_without_id problems (FAILED - 1022)
      Vermont House Orange Washington Addison
        behaves like a match for district
          the District Matcher
            should have no :district_without_id problems (FAILED - 1023)
        behaves like a MISMATCH for district
          the District Matcher
            should have :district_without_id problems (FAILED - 1024)
      New Hampshire House Merrimack 04
        behaves like a match for district
          the District Matcher
            should have no :district_without_id problems (FAILED - 1025)
        behaves like a MISMATCH for district
          the District Matcher
            should have :district_without_id problems (FAILED - 1026)
        behaves like a MISMATCH for district
          the District Matcher
            should have :district_without_id problems (FAILED - 1027)
      New Hampshire House Merrimack 14
        behaves like a match for district
          the District Matcher
            should have no :district_without_id problems (FAILED - 1028)
        behaves like a MISMATCH for district
          the District Matcher
            should have :district_without_id problems (FAILED - 1029)
        behaves like a MISMATCH for district
          the District Matcher
            should have :district_without_id problems (FAILED - 1030)
        behaves like a MISMATCH for district
          the District Matcher
            should have :district_without_id problems (FAILED - 1031)
      New Hampshire House Belknap 06
        behaves like a match for district
          the District Matcher
            should have no :district_without_id problems (FAILED - 1032)
        behaves like a MISMATCH for district
          the District Matcher
            should have :district_without_id problems (FAILED - 1033)
        behaves like a MISMATCH for district
          the District Matcher
            should have :district_without_id problems (FAILED - 1034)
        behaves like a MISMATCH for district
          the District Matcher
            should have :district_without_id problems (FAILED - 1035)
      Wisconsin Assembly District 007
        behaves like a match for district
          the District Matcher
            should have no :district_without_id problems (FAILED - 1036)
        behaves like a match for district
          the District Matcher
            should have no :district_without_id problems (FAILED - 1037)
        behaves like a MISMATCH for district
          the District Matcher
            should have :district_without_id problems (FAILED - 1038)
      Wisconsin General Assembly District 007
        behaves like a match for district
          the District Matcher
            should have no :district_without_id problems (FAILED - 1039)
        behaves like a match for district
          the District Matcher
            should have no :district_without_id problems (FAILED - 1040)
        behaves like a MISMATCH for district
          the District Matcher
            should have :district_without_id problems (FAILED - 1041)
      Minnesota State House District 04a
        behaves like a match for district
          the District Matcher
            should have no :district_without_id problems (FAILED - 1042)
        behaves like a match for district
          the District Matcher
            should have no :district_without_id problems (FAILED - 1043)
        behaves like a match for district
          the District Matcher
            should have no :district_without_id problems (FAILED - 1044)
        behaves like a MISMATCH for district
          the District Matcher
            should have :district_without_id problems (FAILED - 1045)
      CT State House District 001
        behaves like a match for district
          the District Matcher
            should have no :district_without_id problems (FAILED - 1046)
    state senate
      Vermont Senate Addison
        behaves like a match for district
          the District Matcher
            should have no :district_without_id problems (FAILED - 1047)
        behaves like a MISMATCH for district
          the District Matcher
            should have :district_without_id problems (FAILED - 1048)
      Vermont Senate District F
        behaves like a match for district
          the District Matcher
            should have no :district_without_id problems (FAILED - 1049)
        behaves like a MISMATCH for district
          the District Matcher
            should have :district_without_id problems (FAILED - 1050)
        behaves like a MISMATCH for district
          the District Matcher
            should have :district_without_id problems (FAILED - 1051)
    US House
      California District 39
        behaves like a match for district
          the District Matcher
            should have no :district_without_id problems (FAILED - 1052)
        behaves like a MISMATCH for district
          the District Matcher
            should have :district_without_id problems (FAILED - 1053)
        behaves like a MISMATCH for district
          the District Matcher
            should have :district_without_id problems (FAILED - 1054)
      Vermont At-Large District
        behaves like a match for district
          the District Matcher
            should have no :district_without_id problems (FAILED - 1055)
        behaves like a MISMATCH for district
          the District Matcher
            should have :district_without_id problems (FAILED - 1056)
    mixed, with the same dist codes
      #dist_code_level_chamber_to_ids
        separates the lower and upper seats (FAILED - 1057)
    a row without a found id
      is included in USDistrictMatcher#districts_without_ids (FAILED - 1058)
      if we import
        adds the district with the knowwho_code (FAILED - 1059)
      if we import :only_states => ['VT']
        adds the district with the knowwho_code (FAILED - 1060)
      if we import :except_states => ['VT']
        doesn't add the district with the knowwho_code (FAILED - 1061)
    a match without a knowwho_code
      is included in USDistrictMatcher#needs_knowwho_code (FAILED - 1062)
      if we update
        adds the knowwho_code (FAILED - 1063)
      if we update :only_states => ['VT']
        adds the knowwho_code (FAILED - 1064)
      if we update :except_states => ['VT']
        adds the knowwho_code (FAILED - 1065)
    .find_district
      if a district isn't returned
        for the US Senate
          doesn't add to .problems (FAILED - 1066)
        for the US House
          adds to .problems (FAILED - 1067)
  US Recipient Importer
    with two existing US Reps
      behaves like a Recipient record updater and replacer
        with updatable, replaceable, and new Recipients
          matching
            schedules the updatable Recipient for update (FAILED - 1068)
            schedules the replaceable Recipient for replacement (FAILED - 1069)
          importing
            deactivates the replaceable Recipient and removes their committee relationships (FAILED - 1070)
            updates the updatable Recipient (FAILED - 1071)
            imports the new Recipient (FAILED - 1072)
            records the fec_id on the updatable and new Recipients (FAILED - 1073)
    with two existing US Senators
      behaves like a Recipient record updater and replacer
        with updatable, replaceable, and new Recipients
          matching
            schedules the updatable Recipient for update (FAILED - 1074)
            schedules the replaceable Recipient for replacement (FAILED - 1075)
          importing
            deactivates the replaceable Recipient and removes their committee relationships (FAILED - 1076)
            updates the updatable Recipient (FAILED - 1077)
            imports the new Recipient (FAILED - 1078)
            records the fec_id on the updatable and new Recipients (FAILED - 1079)
    with two existing State-level Reps
      behaves like a Recipient record updater and replacer
        with updatable, replaceable, and new Recipients
          matching
            schedules the updatable Recipient for update (FAILED - 1080)
            schedules the replaceable Recipient for replacement (FAILED - 1081)
          importing
            deactivates the replaceable Recipient and removes their committee relationships (FAILED - 1082)
            updates the updatable Recipient (FAILED - 1083)
            imports the new Recipient (FAILED - 1084)
            records the fec_id on the updatable and new Recipients (FAILED - 1085)
    with two existing State-level Senators
      behaves like a Recipient record updater and replacer
        with updatable, replaceable, and new Recipients
          matching
            schedules the updatable Recipient for update (FAILED - 1086)
            schedules the replaceable Recipient for replacement (FAILED - 1087)
          importing
            deactivates the replaceable Recipient and removes their committee relationships (FAILED - 1088)
            updates the updatable Recipient (FAILED - 1089)
            imports the new Recipient (FAILED - 1090)
            records the fec_id on the updatable and new Recipients (FAILED - 1091)
    with a vacated seat (name VACANT) and an updatable seat
      from different districts
        deactivates the vacated Recipient (FAILED - 1092)
        updates the updatable Recipient (FAILED - 1093)
      from the same district
        deactivates the vacated Recipient (FAILED - 1094)
        updates the updatable Recipient (FAILED - 1095)
    with a vacated seat (name VACANT) and an empty seat
      .all_problems
        does not report party or import failures (FAILED - 1096)
    with existing reps swapping seats
      importing
        swaps seats (FAILED - 1097)
    testing for problems
      with full CT and AL state data
        importing only_states => ['CT']
          is successful (FAILED - 1098)
      USRecipientImporter.all_problems
        with party that does not exist
          throws a party_matcher error (FAILED - 1099)
        with row for vacant seat
          does not throw a party_matcher error (FAILED - 1100)
    for US Reps
      behaves like a Recipient record matcher
        matching
          if a rep already exists
            with the same knowwho_code
              matches (FAILED - 1101)
            with the same name, state, and district
              matches (FAILED - 1102)
            with a different name
              doesn't match (FAILED - 1103)
            but is inactive
              doesn't match (FAILED - 1104)
          when the same rep changes office
            doesn't match (FAILED - 1105)
            makes a new recipient record (FAILED - 1106)
            makes the old record inactive (FAILED - 1107)
            has the same knowwho uid (FAILED - 1108)
            has a new knowwho pid (FAILED - 1109)
            has a new knowwho_code (FAILED - 1110)
      behaves like an Address and field updater
        importing
          without a knowhwho code
            updates the knowhwho code (FAILED - 1111)
          without a twitter handle
            creates the twitter handle (FAILED - 1112)
          with a twitter handle
            updates the twitter handle (FAILED - 1113)
          without a facebook handle
            creates the facebook handle (FAILED - 1114)
          with a facebook handle
            by default
              updates the facebook handle (FAILED - 1115)
            with ignore_imports_flg = true
              doesn't update the facebook handle (FAILED - 1116)
          with a phone number
            by default
              updates the phone handle (FAILED - 1117)
            with ignore_imports_flg = true
              doesn't update the phone number (FAILED - 1118)
          without a portrait
            creates the portrait (FAILED - 1119)
          with a portrait
            updates the portrait (FAILED - 1120)
          without a WebMailAddress
            creates the WebMailAddress (FAILED - 1121)
          with a WebMailAddress
            by default
              updates the WebMailAddress (FAILED - 1122)
            with :addresses_options => {:except => ['webform']}
              doesn't update the WebMailAddress (FAILED - 1123)
            with ignore_imports_flg = true
              doesn't update the WebMailAddress (FAILED - 1124)
      behaves like a statewise updater for
        importing :except_states => [state]
          doesn't import to the limiting state (FAILED - 1125)
        importing :only_states => [state]
          imports to the limiting state (FAILED - 1126)
    for US Senators
      behaves like a Recipient record matcher
        matching
          if a rep already exists
            with the same knowwho_code
              matches (FAILED - 1127)
            with the same name, state, and district
              matches (FAILED - 1128)
            with a different name
              doesn't match (FAILED - 1129)
            but is inactive
              doesn't match (FAILED - 1130)
          when the same rep changes office
            doesn't match (FAILED - 1131)
            makes a new recipient record (FAILED - 1132)
            makes the old record inactive (FAILED - 1133)
            has the same knowwho uid (FAILED - 1134)
            has a new knowwho pid (FAILED - 1135)
            has a new knowwho_code (FAILED - 1136)
      behaves like an Address and field updater
        importing
          without a knowhwho code
            updates the knowhwho code (FAILED - 1137)
          without a twitter handle
            creates the twitter handle (FAILED - 1138)
          with a twitter handle
            updates the twitter handle (FAILED - 1139)
          without a facebook handle
            creates the facebook handle (FAILED - 1140)
          with a facebook handle
            by default
              updates the facebook handle (FAILED - 1141)
            with ignore_imports_flg = true
              doesn't update the facebook handle (FAILED - 1142)
          with a phone number
            by default
              updates the phone handle (FAILED - 1143)
            with ignore_imports_flg = true
              doesn't update the phone number (FAILED - 1144)
          without a portrait
            creates the portrait (FAILED - 1145)
          with a portrait
            updates the portrait (FAILED - 1146)
          without a WebMailAddress
            creates the WebMailAddress (FAILED - 1147)
          with a WebMailAddress
            by default
              updates the WebMailAddress (FAILED - 1148)
            with :addresses_options => {:except => ['webform']}
              doesn't update the WebMailAddress (FAILED - 1149)
            with ignore_imports_flg = true
              doesn't update the WebMailAddress (FAILED - 1150)
      behaves like a statewise updater for
        importing :except_states => [state]
          doesn't import to the limiting state (FAILED - 1151)
        importing :only_states => [state]
          imports to the limiting state (FAILED - 1152)
    for State-level Reps
      behaves like a Recipient record matcher
        matching
          if a rep already exists
            with the same knowwho_code
              matches (FAILED - 1153)
            with the same name, state, and district
              matches (FAILED - 1154)
            with a different name
              doesn't match (FAILED - 1155)
            but is inactive
              doesn't match (FAILED - 1156)
          when the same rep changes office
            doesn't match (FAILED - 1157)
            makes a new recipient record (FAILED - 1158)
            makes the old record inactive (FAILED - 1159)
            has the same knowwho uid (FAILED - 1160)
            has a new knowwho pid (FAILED - 1161)
            has a new knowwho_code (FAILED - 1162)
      behaves like an Address and field updater
        importing
          without a knowhwho code
            updates the knowhwho code (FAILED - 1163)
          without a twitter handle
            creates the twitter handle (FAILED - 1164)
          with a twitter handle
            updates the twitter handle (FAILED - 1165)
          without a facebook handle
            creates the facebook handle (FAILED - 1166)
          with a facebook handle
            by default
              updates the facebook handle (FAILED - 1167)
            with ignore_imports_flg = true
              doesn't update the facebook handle (FAILED - 1168)
          with a phone number
            by default
              updates the phone handle (FAILED - 1169)
            with ignore_imports_flg = true
              doesn't update the phone number (FAILED - 1170)
          without a portrait
            creates the portrait (FAILED - 1171)
          with a portrait
            updates the portrait (FAILED - 1172)
          without a WebMailAddress
            creates the WebMailAddress (FAILED - 1173)
          with a WebMailAddress
            by default
              updates the WebMailAddress (FAILED - 1174)
            with :addresses_options => {:except => ['webform']}
              doesn't update the WebMailAddress (FAILED - 1175)
            with ignore_imports_flg = true
              doesn't update the WebMailAddress (FAILED - 1176)
      behaves like a statewise updater for
        importing :except_states => [state]
          doesn't import to the limiting state (FAILED - 1177)
        importing :only_states => [state]
          imports to the limiting state (FAILED - 1178)
    for State-level Senators
      behaves like a Recipient record matcher
        matching
          if a rep already exists
            with the same knowwho_code
              matches (FAILED - 1179)
            with the same name, state, and district
              matches (FAILED - 1180)
            with a different name
              doesn't match (FAILED - 1181)
            but is inactive
              doesn't match (FAILED - 1182)
          when the same rep changes office
            doesn't match (FAILED - 1183)
            makes a new recipient record (FAILED - 1184)
            makes the old record inactive (FAILED - 1185)
            has the same knowwho uid (FAILED - 1186)
            has a new knowwho pid (FAILED - 1187)
            has a new knowwho_code (FAILED - 1188)
      behaves like an Address and field updater
        importing
          without a knowhwho code
            updates the knowhwho code (FAILED - 1189)
          without a twitter handle
            creates the twitter handle (FAILED - 1190)
          with a twitter handle
            updates the twitter handle (FAILED - 1191)
          without a facebook handle
            creates the facebook handle (FAILED - 1192)
          with a facebook handle
            by default
              updates the facebook handle (FAILED - 1193)
            with ignore_imports_flg = true
              doesn't update the facebook handle (FAILED - 1194)
          with a phone number
            by default
              updates the phone handle (FAILED - 1195)
            with ignore_imports_flg = true
              doesn't update the phone number (FAILED - 1196)
          without a portrait
            creates the portrait (FAILED - 1197)
          with a portrait
            updates the portrait (FAILED - 1198)
          without a WebMailAddress
            creates the WebMailAddress (FAILED - 1199)
          with a WebMailAddress
            by default
              updates the WebMailAddress (FAILED - 1200)
            with :addresses_options => {:except => ['webform']}
              doesn't update the WebMailAddress (FAILED - 1201)
            with ignore_imports_flg = true
              doesn't update the WebMailAddress (FAILED - 1202)
      behaves like a statewise updater for
        importing :except_states => [state]
          doesn't import to the limiting state (FAILED - 1203)
        importing :only_states => [state]
          imports to the limiting state (FAILED - 1204)

Updating promoter agg columns
  Top level method
    successfully calls update_message_promoter_and_agency_agg_columns
    logs errors raised in inner methods of update_message_promoter_and_agency_agg_columns (FAILED - 1205)
    logs errors when total time of update_message_promoter_and_agency_agg_columns >= 10 minutes
    successfully runs call_agg_methods for this etl
  Inner sql calls
    should successfully update_message_agg_activity_columns (FAILED - 1206)
    should successfully update_message_conversion_activity_columns (FAILED - 1207)
    should successfully update_promoter_agg_activity_columns (FAILED - 1208)
    should successfully update_promoter_total_campaigns_column (FAILED - 1209)
    should successfully update_promoter_total_advocates_column (FAILED - 1210)
    should successfully insert_dummy_data_agg_agency_total_activity (FAILED - 1211)
    should successfully update_offices_activity_sum_for_agg_agency_total_activity (FAILED - 1212)
    should successfully add_individual_agency_activity_to_agg_agency_total_activity (FAILED - 1213)

ModelCleaner
  for NationBuilderSynchronizeCalls
    behaves like a model cleaner
      with a last successful record
        after the cutoff
          destroys before the cutoff (FAILED - 1214)
          doesn't destroy after the cutoff (FAILED - 1215)
        before the cutoff
          destroys before the record (FAILED - 1216)
          doesn't destroy after the record (FAILED - 1217)
        running
          doesn't destroy other Promoters' records (FAILED - 1218)
          doesn't destroy other model_types (FAILED - 1219)
  for CSVSynchronizeCalls
    behaves like a model cleaner
      with a last successful record
        after the cutoff
          destroys before the cutoff (FAILED - 1220)
          doesn't destroy after the cutoff (FAILED - 1221)
        before the cutoff
          destroys before the record (FAILED - 1222)
          doesn't destroy after the record (FAILED - 1223)
        running
          doesn't destroy other Promoters' records (FAILED - 1224)
          doesn't destroy other model_types (FAILED - 1225)
  for NoDBTransactions
    behaves like a model cleaner
      with a last successful record
        after the cutoff
          destroys before the cutoff (FAILED - 1226)
          doesn't destroy after the cutoff (FAILED - 1227)
        before the cutoff
          destroys before the record (FAILED - 1228)
          doesn't destroy after the record (FAILED - 1229)
        running
          doesn't destroy other Promoters' records (FAILED - 1230)
          doesn't destroy other model_types (FAILED - 1231)

NationBuilderClient
  tags.rb
    #create_tag(person_id, contect)
      should return a tag object
      should raise an error if person is not found
      should call NationBuilder API with tag request
  people.rb
    #get_person(person_id)
      should return a person
      should raise an error if person_id does not exist
      should make NationBuilder API call
    #get_people(page = 1)
      should return a hash with people and paging keys
    #create_person(person_data)
      returns a person object
      returns a person with a country_code, AU
      returns a person with a country_code, CA
      returns a person with a country_code, US
      should save address attributes
      should make a NationBuilder API request
      Validations
        Attempting to create a very similar user on NationBuilder
          should raise an error
          should return a person data in the response body
          should raise an error if a person with a duplicate email is created
          should raise an error if a Person with a duplicate phone is created
          should create a new user as long as email and phone are different. All else can remain the same
        Standard Validations Errors
          Long phone number (over 30 chars)
      #people_count
        should return the number of people in the NationBuilder Nation
    update_person(person_id, person_data)
      should return a person new person
      should raise error if email is the same as existing
      should make a call to the NationBuilder API
    destroy_person(person_id)
      should return nothing
      should raise error if not found
      should call the NationBuilder API
    #push_person(person_data)
      returns a created person, if the person does not exist on NB
      returns an updated_person if person does exist on NationBuilder
    search_people(query)
      should return an Enumerator of results
      should return an empty Array if nothing is found
      should return all pages of a search result
      should make a all to the NationBuilder API
    find_by_email(email)
      should find a person by email
      should return nil if no person is found
  contacts.rb
    #create_contact(contact_data)
      should return a Contact
      should make a call to the NationBuilder API
    Settings
      #get_contact_statues
        should return conctact_statuses
      #get_contact_methods
        should return conctact_statuses
  contact_types.rb
    #get_contact_types
      should return all results as an enumerable
    #contact_type_exists?(name)
      should return true if ContactType exists
      should return false if ContactType does not exist
    #get_contact_type_by_name(name)
      should get ContactType by name
    #create_contact_type(name)
      should return ContactType JSON
      should raise an error if an identical name exists
      should make a call to the NationBuilder API
    #destroy_contact_type(name)
      should return and empty string
      should raise an error if not found
      should make a call to the NationBuilderApi
  helpers.rb
    #contact_builder(recipient_id, sender_id, contact_type_name, method, status = nil, note = nil)
      should return a contact
      should not search for a new ContactType, if one has been searched for
      should not search for a new ContactType, if one has been created
  VCR sanity tests
    people.rb
      should fetch a Person
      should create and destroy a Person
    contacts.rb
      should create and destroy a Contact
    contact_types.rb
      should get ContactTypes by name
      should create and destroy a ContactType
    helpers.rb
      contact_builder(recipient_id, sender_id, contact_type_name, method, status, note = nil)
        should create a contact
        with unknown ContactType
          should create an new contact type

NationBuilderSync
  #sync_email_contacts(conversion, advocate_profile_nation_builder_id)
    should call sync_email_contact_from_conversion for every Recipient (FAILED - 1232)
    should not break on a NationBuilderClient::UnprocessableEntityError (FAILED - 1233)
    should not break on a Faraday::ConnectionFailed (FAILED - 1234)
    should make a call to #contact_builder on NationBuilderClient for every Recipient. (FAILED - 1235)
    sync_recipient returns nil
      should log a failure to sync Contact if syncing of Recipient returns nil (FAILED - 1236)
      should NOT attempt to sync the Contact (FAILED - 1237)
  sync_email_conversion
    #sync_advocate_profile returns nil
      should log a failure to sync Contact if syncing of AdvocateProfile returns nil (FAILED - 1238)
      should NOT attempt to sync the Contacts (FAILED - 1239)
      should mark the Conversion as synced (FAILED - 1240)
  #sync_email_contact_from_conversion(conversion, recipient, method)
    should call NationBuilderClient's #contact_builder method (FAILED - 1241)
    Errors
      Record not found Error
        should call sync_tag twice (FAILED - 1242)
        should reset advocate_profile's external_connection (FAILED - 1243)
        should reset recipient's external_connection (FAILED - 1244)
      Validation Failed
        should call sync_tag twice (FAILED - 1245)
        should reset advocate_profile's external_connection (FAILED - 1246)
        should reset recipient's external_connection (FAILED - 1247)
  #sync_email_conversions
    should sync all eligible Conversions (FAILED - 1248)
    should not sync Conversions from before epoch (FAILED - 1249)
    should not sync Conversions from after apocalypse (FAILED - 1250)
    should allow epoch to be set (FAILED - 1251)
    should not sync a Conversion marked as :nation_builder_unsyncable (FAILED - 1252)
    should not sync of Conversion has already been synced (FAILED - 1253)
    should not not attempt to sync Conversion if reached_recipient_ids is nil (FAILED - 1254)
    should not attempt to sync if @sender has no AdvocateProfile (FAILED - 1255)
    should call sync_advocate_profile with @sender (FAILED - 1256)
    should call sync_recipient for each recipient (FAILED - 1257)
    should sync 4 Contacts (FAILED - 1258)
    should NOT sync contacts if AdvocateForPromoter is not present (FAILED - 1259)
    should NOT sync contacts if AdvocateForPromoter :opt_in_id is blank (FAILED - 1260)
  #sync_email_conversion(conversion)
    should update :nation_builder_tag_synced on Conversion (FAILED - 1261)
    should increment report (FAILED - 1262)
    Logging
      should log NationBuilderClient::UnprocessableEntityError (FAILED - 1263)

NationBuilderSyncNotifier
  #notifiy
    should deliver an email with NationBuilderSyncNotificationMailer (FAILED - 1264)
  #error_notification
    should deliver an email with NationBuilderSyncNotificationMailer (FAILED - 1265)

NationBuilderSync
  #new
    should assign @promoter Authenticaton for NationBuilder to @auth (FAILED - 1266)
    should assign @promoter to @promoter (FAILED - 1267)
  #sync_all
    should call sync_email_conversions (FAILED - 1268)
    should call sync_tags (FAILED - 1269)
    should call sync_service_deliveries (FAILED - 1270)
    should create a NationBuilderSynchronizeCall (FAILED - 1271)
    associated NationBuilderSynchronizeCall to success if the sync runs through (FAILED - 1272)
    should assign a summary of the sync to :action of it NationBuilderSynchronizeCall (FAILED - 1273)
    Errors
      Timeout
        should call sync_all again (FAILED - 1274)
      JSON Octets error
        should call sync_all again (FAILED - 1275)
      Service Unavailable - Zero size object Error
        should log the failure (FAILED - 1276)
        should notify the dev team (FAILED - 1277)
        should set the status of the related SynchronizeCall to "Failure" (FAILED - 1278)
      an Internal Server Error
        should log the failure, along with a backtrace (FAILED - 1279)
        should notify the dev team (FAILED - 1280)
        should set the status of the related SynchronizeCall to "Failure" (FAILED - 1281)
      Website temporarily unavailable Error
        should log the failure (FAILED - 1282)
        should notify the dev team (FAILED - 1283)
        should set the status of the related SynchronizeCall to "Failure" (FAILED - 1284)
      Faraday::ConnectionFailed
        should log the failure (FAILED - 1285)
        should notify the dev team (FAILED - 1286)
        should set the status of the related SynchronizeCall to "Failure" (FAILED - 1287)
      Faraday::TimeoutError
        should log the failure (FAILED - 1288)
        should notify the dev team (FAILED - 1289)
        should set the status of the related SynchronizeCall to "Failure" (FAILED - 1290)
      NationBuilderClient::AuthenticationError
        should set :write_access on @authenticaion to false (FAILED - 1291)
        should update the related NationBuilderSyncronizeCall (FAILED - 1292)
        should send notification via NationBuilderSyncNotifier (FAILED - 1293)
        should assign a summary of the sync to :action of it NationBuilderSynchronizeCall (FAILED - 1294)
      Rate Limit Error
        should return nil (FAILED - 1295)
        should log failure (FAILED - 1296)
        should send notification via NationBuilderSyncNotifier (FAILED - 1297)
      OAuth2 Server Error
        should return nil (FAILED - 1298)
        should log failure (FAILED - 1299)
        should send notification via NationBuilderSyncNotifier (FAILED - 1300)
      Unknown (Catastrophic) error
        should call error_notification on a Notifier object (FAILED - 1301)
        should log the error (FAILED - 1302)
        should update the related NationBuilderSyncronizeCall (FAILED - 1303)
        should update the related NationBuilderSyncronizeCall (FAILED - 1304)
        should assign a summary of the sync to :action of it NationBuilderSynchronizeCall (FAILED - 1305)
      NationBuilderSynchronizeCall
        should record a parital sync on :action (FAILED - 1306)
  CLASS METHOD: self.sync_all(exceptions_by_name = [])
    should instantiate a new NationBuilderSync (FAILED - 1307)
    should call sync_all on the instance of NationBuilderSyncs it instantiates (FAILED - 1308)
    should not attempt to sync if the id of @promoter is included
      in an array passes as the single option parameter. (FAILED - 1309)
    With more than one qualified Promoter
      should not sync if Promoter's nation_builder @authentication does not have write_access (FAILED - 1310)
      should create a new instance of NationBuilderSync for each qualified Promoter (FAILED - 1311)
      should call sync_all for every Promoter, even if an Authentication Error is raised (FAILED - 1312)
      With an ongoing NationBuilderSynchronizeCall
        older than 2 days
          should not log failure to sync (FAILED - 1313)
        younger than 2 days
          should log failure to sync because of an ongoing sync (FAILED - 1314)
      NationBuilderSynchronizeCalls
        should create a Call for each Promoter) (FAILED - 1315)
        new Calls should be successful (FAILED - 1316)
        should save relevant :action attribute (FAILED - 1317)
        should count Recipient types that are not Recipients (FAILED - 1318)
      A Catastrophic Error
        should create a new instance of NationBuilderSync for each qualified Promoter (FAILED - 1319)
  .syncable_promoters
    with two PromoterUsers sharing the same Authentication
      and another Promoter with its own Authentication
        returns all 3 PromoterUsers (FAILED - 1320)

NationBuilderSync
  #sync_recipient(recipient)
    should return the Recipient id from NationBuilder (FAILED - 1321)
    should increment report (FAILED - 1322)
    Errors
      UnprocessibleEntityError
        should return nil if a NationBuilderClient::PersonError is raised (FAILED - 1323)
        should continue with the sync and mark it as "success" if it passes (FAILED - 1324)
        should assign a summary of the sync to :action of it NationBuilderSynchronizeCall (FAILED - 1325)
      bad Email Error
        should return nil (FAILED - 1326)
        should mark_unsyncable! if a bad email error is raised (FAILED - 1327)
      county file ID error
        should return nil (FAILED - 1328)
        should mark_unsyncable! (FAILED - 1329)
      profile.website url error
        should return nil (FAILED - 1330)
        should mark_unsyncable! (FAILED - 1331)
      billing_address.phone_number can't be blank
        should return nil (FAILED - 1332)
        should mark_unsyncable! (FAILED - 1333)
      Recruiter name/email error
        should return nil (FAILED - 1334)
        should mark_unsyncable! (FAILED - 1335)
      Missing required values Error
        should return nil (FAILED - 1336)
        should mark_unsyncable! (FAILED - 1337)
        should send notification (FAILED - 1338)
      Username is already taken error
        should return nil (FAILED - 1339)
        should mark_unsyncable! (FAILED - 1340)
      Username is already taken error
        should return nil (FAILED - 1341)
        should mark_unsyncable! (FAILED - 1342)
      Email has already been taken error
        should return nil (FAILED - 1343)
        should mark_unsyncable! (FAILED - 1344)
      Email has already been taken error
        should return nil (FAILED - 1345)
        should mark_unsyncable! (FAILED - 1346)
      Recruiter name/email error
        should return nil (FAILED - 1347)
        should mark_unsyncable! (FAILED - 1348)
      Missing required values Error
        should return nil (FAILED - 1349)
        should mark_unsyncable! (FAILED - 1350)
        should send notification (FAILED - 1351)
      Married not a custom value error
        should return nil (FAILED - 1352)
        should mark_unsyncable! (FAILED - 1353)
      Email has already been taken Error
        should call find_by_email (FAILED - 1354)
        should call update_person (FAILED - 1355)
        should return a NationBuilder id (FAILED - 1356)
        if find_by_email returns nil, return nil (FAILED - 1357)
    with multiple US Recipients
      should attempt to sync multiple email addresses (FAILED - 1358)
    ExternalConnection does not exist
      should call #mark_synced! (FAILED - 1359)
    ExternalConnection exists
      should NOT call #mark_synced! on @recipient if #do_sync? for on ExternalConnection if false (FAILED - 1360)
      should only call #mark_synced! once per sync, per Recipient (FAILED - 1361)
      should return nil if unsyncable (FAILED - 1362)
      Errors
        Person is not found on NationBuilder for an update (Record not found)
          should call :create_person (FAILED - 1363)
          should update relevant ExternalConnection (FAILED - 1364)
    with a US Recipient
      behaves like a Recipient sync
        Recipient is not known by us to exist on NationBuilder
          should create_person on NationBuilder if no ExternalConnection has been established (FAILED - 1365)
          should call mark_synced! (FAILED - 1366)
          should return the NationBuilderId (FAILED - 1367)
          Recipient exists on NationBuilder
            if email matches, update Recipient (FAILED - 1368)
        We have synced to NationBuilder already
          should should update_person on NationBuilder if ExternalConnection has been established (FAILED - 1369)
          should call mark_synced! on @recipient (FAILED - 1370)
          should mark_unsyncable! if a bad email error is raised (FAILED - 1371)
    with an Australian Recipient
      behaves like a Recipient sync
        Recipient is not known by us to exist on NationBuilder
          should create_person on NationBuilder if no ExternalConnection has been established (FAILED - 1372)
          should call mark_synced! (FAILED - 1373)
          should return the NationBuilderId (FAILED - 1374)
          Recipient exists on NationBuilder
            if email matches, update Recipient (FAILED - 1375)
        We have synced to NationBuilder already
          should should update_person on NationBuilder if ExternalConnection has been established (FAILED - 1376)
          should call mark_synced! on @recipient (FAILED - 1377)
          should mark_unsyncable! if a bad email error is raised (FAILED - 1378)
    with a Canadian Recipient
      behaves like a Recipient sync
        Recipient is not known by us to exist on NationBuilder
          should create_person on NationBuilder if no ExternalConnection has been established (FAILED - 1379)
          should call mark_synced! (FAILED - 1380)
          should return the NationBuilderId (FAILED - 1381)
          Recipient exists on NationBuilder
            if email matches, update Recipient (FAILED - 1382)
        We have synced to NationBuilder already
          should should update_person on NationBuilder if ExternalConnection has been established (FAILED - 1383)
          should call mark_synced! on @recipient (FAILED - 1384)
          should mark_unsyncable! if a bad email error is raised (FAILED - 1385)
    Errors
      Recipient email is invalid
        should call mark_unsyncable! on @recipient (FAILED - 1386)
      bad Email Error
        should return nil (FAILED - 1387)
        should mark_unsyncable! if a bad email error is raised (FAILED - 1388)
      county file ID error
        should return nil (FAILED - 1389)
        should mark_unsyncable! (FAILED - 1390)
      profile.website url error
        should return nil (FAILED - 1391)
        should mark_unsyncable! (FAILED - 1392)
    PRIVATE METHOD: #recipient_data(recipient)
      email_opt_in should not be present in returned hash (FAILED - 1393)
      prefix should not be present in returned hash (FAILED - 1394)
      should return only highest-priority phone (FAILED - 1395)
      should return email addresses in order of priority (FAILED - 1396)
      should shorten any zip code that is over 10 digits long (FAILED - 1397)
      Party Abbreviations
        should have a :party key if it is an acceptable, single-digit party abbreviation (FAILED - 1398)
        should NOT have a :party key if the abbreviation is not allowed (FAILED - 1399)
      with an Australian AU- state
        strips the AU- (FAILED - 1400)
      with a Canadian CA- state
        strips the CA- (FAILED - 1401)
  #person_emails_are_valid?
    with valid AU email address
      returns true (FAILED - 1402)
    with valid AU email address containing apostrophe
      returns true (FAILED - 1403)
  #generate_country_code
    with australia
      returns AU (FAILED - 1404)
    with canada
      returns CA (FAILED - 1405)
    with anything other than australia/canada
      returns nil (FAILED - 1406)
  #add_country_code
    with home_address set to null
      home_address returns nil and there is no country_code key (FAILED - 1407)
    with country
      set to Canada
        country_code returns CA (FAILED - 1408)
      set to canada
        country_code returns CA (FAILED - 1409)
      set to Australia
        country_code returns AU (FAILED - 1410)
      set to ''
        country_code returns US (FAILED - 1411)
      set to nil
        country_code returns US (FAILED - 1412)
  #format_state
    with state=CA-MB
      returns MB (FAILED - 1413)
    with state=AU-QLD
      returns QLD (FAILED - 1414)
    with state=CA
      returns CA (FAILED - 1415)
  #sync_advocate_profile(sender)
    should return the AdvocateProfile :id from NationBuilder (FAILED - 1416)
    should return nil if a NationBuilderClient::PersonError is raised (FAILED - 1417)
    should increment report (FAILED - 1418)
    should return nil if a bad email error is raised (FAILED - 1419)
    ExternalConnection does not exist
      should call #mark_synced! (FAILED - 1420)
    ExternalConnection exists
      should NOT call #mark_synced! on @recipient if #do_sync? for on ExternalConnection if false (FAILED - 1421)
      should only call #mark_synced! once per sync, per Recipient (FAILED - 1422)
      should return nil if unsyncable (FAILED - 1423)
      Errors
        Person is not found on NationBuilder for an update (Record not found)
          should call :create_person (FAILED - 1424)
          should update relevant ExternalConnection (FAILED - 1425)
    with a US AdvocateProfile
      behaves like an AdvocateProfile sync
        AdvocateProfile is not known by us to exist on NationBuilder
          should create_person on NationBuidler if no ExternalConnection has been established (FAILED - 1426)
          should call mark_synced! (FAILED - 1427)
          should return the NationBuilderId (FAILED - 1428)
          AdvocateProfile exists on NationBuilder
            if email matches, update AdvocateProfile (FAILED - 1429)
        We have synced to NationBuilder already
          should should update_person on NationBuilder if ExternalConnection has been established (FAILED - 1430)
          should call mark_synced! on @AdvocateProfile (FAILED - 1431)
        AdvocateProfile email is invalid
          should call mark_unsyncable! on @AdvocateProfile (FAILED - 1432)
        AdvocateProfile email raises an error from NationBuilder (passes our RegEx)
          should return nil (FAILED - 1433)
        billing_address.phone_number can't be blank
          should return nil (FAILED - 1434)
          should mark_unsyncable! (FAILED - 1435)
    with an Australian AdvocateProfile
      behaves like an AdvocateProfile sync
        AdvocateProfile is not known by us to exist on NationBuilder
          should create_person on NationBuidler if no ExternalConnection has been established (FAILED - 1436)
          should call mark_synced! (FAILED - 1437)
          should return the NationBuilderId (FAILED - 1438)
          AdvocateProfile exists on NationBuilder
            if email matches, update AdvocateProfile (FAILED - 1439)
        We have synced to NationBuilder already
          should should update_person on NationBuilder if ExternalConnection has been established (FAILED - 1440)
          should call mark_synced! on @AdvocateProfile (FAILED - 1441)
        AdvocateProfile email is invalid
          should call mark_unsyncable! on @AdvocateProfile (FAILED - 1442)
        AdvocateProfile email raises an error from NationBuilder (passes our RegEx)
          should return nil (FAILED - 1443)
        billing_address.phone_number can't be blank
          should return nil (FAILED - 1444)
          should mark_unsyncable! (FAILED - 1445)
    with a Canadian AdvocateProfile
      behaves like an AdvocateProfile sync
        AdvocateProfile is not known by us to exist on NationBuilder
          should create_person on NationBuidler if no ExternalConnection has been established (FAILED - 1446)
          should call mark_synced! (FAILED - 1447)
          should return the NationBuilderId (FAILED - 1448)
          AdvocateProfile exists on NationBuilder
            if email matches, update AdvocateProfile (FAILED - 1449)
        We have synced to NationBuilder already
          should should update_person on NationBuilder if ExternalConnection has been established (FAILED - 1450)
          should call mark_synced! on @AdvocateProfile (FAILED - 1451)
        AdvocateProfile email is invalid
          should call mark_unsyncable! on @AdvocateProfile (FAILED - 1452)
        AdvocateProfile email raises an error from NationBuilder (passes our RegEx)
          should return nil (FAILED - 1453)
        billing_address.phone_number can't be blank
          should return nil (FAILED - 1454)
          should mark_unsyncable! (FAILED - 1455)
    PRIVATE: #advocate_profile_data
      should shorten any zip code that is over 10 digits long (FAILED - 1456)

NationBuilderSync
  Syncing ServiceDeliveries
    #sync_service_delivery(service_delivery)
      should mark the ServiceDelivery as synced (FAILED - 1457)
      should call sync_contact_from_service_delivery with the ServiceDeliver (FAILED - 1458)
      should increment report (FAILED - 1459)
      Recipient fails to sync
        should return nil (FAILED - 1460)
        should log the failure (FAILED - 1461)
        should mark the ServiceDelivery as nation_builder_unsyncable (FAILED - 1462)
      AdvocateProfile (Sender) fails to sync
        should return nil (FAILED - 1463)
        should log the failure (FAILED - 1464)
        should mark the ServiceDelivery as nation_builder_unsyncable (FAILED - 1465)
    #sync_service_deliveries
      should call #sync_service_delivery for each ServiceDelivery (FAILED - 1466)
      should not break on a NationBuilderClient::UnprocessableEntityError (FAILED - 1467)
      should NOT sync contacts if AdvocateForPromoter is not present (FAILED - 1468)
      should NOT sync contacts if AdvocateForPromoter :opt_in_id is blank (FAILED - 1469)
      should NOT sync if marked as :nation_builder_unsyncable (FAILED - 1470)
      should not sync Conversions from before :epoch (FAILED - 1471)
      should not sync Conversions from after :apocalypse (FAILED - 1472)
      should not attempt to sync if an ExternalConnection for provider "nation_buidler" already exists for ServiceDelivery. (FAILED - 1473)
      Logging
        should log NationBuilderClient::UnprocessableEntityError (FAILED - 1474)
    #sync_contact_from_service_delivery(service_delivery)
      should call sync_recipient on @recipient (FAILED - 1475)
      should call sync_advocate_profile on @advocate_profile (FAILED - 1476)
      should call #contact_builder from NationBuilderClient (FAILED - 1477)
      should work with Phone delivery_type too (FAILED - 1478)
      Errors
        Record not found Error
          should call sync_contact_from_service_delivery twice (FAILED - 1479)
          should reset advocate_profile's external_connection (FAILED - 1480)
          should reset recipient's external_connection (FAILED - 1481)
        Validation Failed Error
          should call sync_contact_from_service_delivery twice (FAILED - 1482)
          should reset advocate_profile's external_connection (FAILED - 1483)
          should reset recipient's external_connection (FAILED - 1484)
  Syncing Video Message Service Deliveries
    should sync VideoServiceDeliveries (FAILED - 1485)

NationBuilderSync
  Syncing Tags
    #sync_tag(conversion)
      should call sync_sender on @advocate_profile (FAILED - 1486)
      should call NationBuilderClient's create_tag method (FAILED - 1487)
      should update :nation_builder_tag_synced on Conversion (FAILED - 1488)
      should increment report (FAILED - 1489)
      sync_advocate_profile returns nil (when there is an error)
        should return nil (FAILED - 1490)
        should mark the Conversion as unsyncable with NB (FAILED - 1491)
      Errors
        Record not found Error
          should call sync_tag twice (FAILED - 1492)
          should reset advocate_profile's external_connection (FAILED - 1493)
        Validation Failed Error
          should call sync_tag twice (FAILED - 1494)
          should reset advocate_profile's external_connection (FAILED - 1495)
    #sync_tags
      should sync tags (FAILED - 1496)
      should NOT sync contacts if AdvocateForPromoter is not present (FAILED - 1497)
      should NOT sync contacts if AdvocateForPromoter :opt_in_id is blank (FAILED - 1498)
      should not sync Conversions from before :epoch (FAILED - 1499)
      should NOT sync Conversions from after :apocalypse (FAILED - 1500)
      should not not attempt to sync if nation_builder_tag_synced is true for Conversion (FAILED - 1501)
      should not attempt to sync if Conversion has no AdvocateProfile (FAILED - 1502)
      should not attempt to sync Conversion marked as :nation_builder_unsyncable (FAILED - 1503)
      should not break on a NationBuilderClient::UnprocessableEntityError (FAILED - 1504)
      should not break on a Faraday::ConnectionFailed (FAILED - 1505)

NeonClient::AccountBuilder
  should assign pass params and translate them to period delimited.
  Create Validations
    should raise an error if first_name is not provided
    should raise an error if last_name is not provided
  Phones
    should assign any 1 email to individualAccount.primaryContact.phone1
        w/ the approprate type
  Address
    isPrimaryAddress
      should not set isPrimaryAddress to NO addresss is provided
      should set isPrimaryAddress to true if address_type is provided
    Zip
      should save a 5 digit zip code to zipCode
      should save a zip suffix to zipSuffix
  Updating an Account
    should add contactId to payload
    should add the accountId to the payload
    should add new params to payload
    should add is_primary_address to payload, if passed
    should not add address attributes
    DOB
      should include DOB if provided
      should delete the entire key if no DOB is provided

NeonClient
  #get_custom_fields
    should return an Array of custom fields
    Array items should be a Hashes containg custom field data
  #get_genders
    should return an array of genders and codes
  #get_address_types
    should return an array of address types
  #get_states
    should return an array of states
    Array items should be hashes containing state info
  #get_countries
    should return an Array of countries
    Array items should be hashes containing country info
  #get_sources
    should return an Array of sources
    Array items should be hashes containing source info

NeonClient
  #get_campaigns
    should return any Array of campaign items
    Array items should be hashes of Campaign info
  #get_campaign
    should return a hash of Campaign data
    should raise an error if a bad_id is passed

NeonClient
  #get_custom_fields
    should return an Array of custom fields
    custom fields Array items should be Hashes of custom field data

NeonClient::CustomObjectBuilder
  #build
    should assign pass params and translate them to period delimited.

NeonClient::CustomObjectFieldBuilder
  should translate common params
  should translate type-specific params
  Validations
    data_type
      should raise an error if no data_type is passed
      should raise an error if data_type is not included in list

NeonClient
  #get_custom_object_fields
    should return an Enumerator
    Array items should represent CustomFields
    should raise an error if api_name is not found
  #create_custom_object_field
    should return api_name (this is the only data we get back)
    Bad params will raise an error
  #get_lookup_objects
    should return an array of objects
    Array objects should represent Objects
  #get_master_detail_objects
    should return an array of objects
    Array objects should represent Objects
  End to End
    Creating a Text Field
    Creating a Textarea Field
    Creating a MasterDetail field
    Creating a Lookup field

NeonClient
  End-to-End
  #get_custom_objects
    should return an Enumerator of CustomObjects
    Array items should be hashes containing a CustomObject data
  #get_custom_object
    should search by provided id_key to find custom object
    should raise an error if no object is found
  #find_custom_object
    should search by id to find custom object
    should raise an error if no object is found
  #get_custom_object_by_api_name
    should search by api_name to find custom object
    should raise an error if no object is found
  #get_custom_object_by_label
    should search by name to find custom object
    should raise an error if no object is found
  #create_custom_object
    should return custom new object id
    should raise an error if proper params are not provided
  #update_custom_object
    should return true if successful
    should raise an error if the CustomObject is not found
  #destroy_custom_object
    should return true if successful
    should raise an error on failure

NeonClient::CustomRecordBuilder
  #build
    should add api_name to returned params
    should translate all other params as keys for Neon, with suffixed numbers
        to distinguish keys.
    should not repeate api_key
    should raise an error if no api_name is in params

NeonClient
  End to End (PENDING: fails on update. endpoint may be broken)
  #get_custom_record
    should return a CustomRecord
    should raise an error if CustomRecord params incorrect
  #create_custom_record
    should pass translated params to RestClient
    should return the id of the new record
    should raise an error if proper params are not passed
  #update_custom_record
    should return a record id
    should raise an error if bad params are passed
  #list_custom_records
    should return CustomRecords across multiple pages
    should raise an error if CustomRecord params incorrect

NeonClient::IndividualBuilder
  Updating an Individual
    should carry over existing params to payload

NeonClient
  End to End
  #get_individual
    should return individualAccount data
    should raise an error if the id is bad
  #create_individual
    should return a new id
    should raise an error if last_name is not provided
  #update_individual
    should return existing id
  #get_individual_types
    should return an array of Individual Types
    IndividualTypes Array should contain Hashes

NeonClient
  #connect!
    should set @session_id
    should raise a PromoterWideError if the call fails with a bad api_key
    should raise a PromoterWideError if the call fails with a bad Org Id
    should return @client (self)
  Reconnecting
    should reconnect if a timeout error occurs.
    should raise an error if #connect! is called and this error is returned

NeonSync
  for OCP Campaigns
    #get_or_sync_ocp_campaigns
      with 3 unsynced OCP Campaigns
        syncs those 3 OCP Campaigns (FAILED - 1506)
        calling
          increments the report count (FAILED - 1507)
          behaves like a successful OCP Campaign sync
            matches every PromotedMessage id up with a Neon OCP Campaign id (FAILED - 1508)
            returns true (FAILED - 1509)
      with no unsynced OCP Campaigns
        doesn't sync OCP Campaigns (FAILED - 1510)
        calling
          doesn't increment the report count (FAILED - 1511)
          behaves like a successful OCP Campaign sync
            matches every PromotedMessage id up with a Neon OCP Campaign id (FAILED - 1512)
            returns true (FAILED - 1513)
      if we don't get a synced OCP Campaign id for each PromotedMessage
        returns false (FAILED - 1514)
  for Accounts
    #get_unsynced_advocate_profiles and #get_synced_advocate_profiles
      without a 'neon' ExternalConnection to this PromoterUser
        returns as unsynced (FAILED - 1515)
      with a 'neon' ExternalConnection for this PromoterUser
        returns as synced (FAILED - 1516)
      with an opt-out AdvocateForPromoter for this PromoterUser
        returns as neither (FAILED - 1517)
      with an opt-in AdvocateForPromoter for another PromoterUser
        returns as neither (FAILED - 1518)
    #sync_account
      when the sync succeeds
        behaves like an individualAccount creator
          when the sync succeeds
            passes the correct params to Neon (FAILED - 1519)
            syncing
              creates an ExternalConnection with the external_id (FAILED - 1520)
              increments the report count (FAILED - 1521)
      when the sync fails
        syncing
          creates an ExternalConnection with the error_message (FAILED - 1522)
          doesn't increment the report count (FAILED - 1523)
      if @deduplicate=true
        checks for the individualAccount with that email (FAILED - 1524)
        if it exists
          doesn't call :create_individual (FAILED - 1525)
          syncing
            creates an ExternalConnection with external_id (FAILED - 1526)
            doesn't increment the report count (FAILED - 1527)
        if it doesn't exist
          behaves like an individualAccount creator
            when the sync succeeds
              passes the correct params to Neon (FAILED - 1528)
              syncing
                creates an ExternalConnection with the external_id (FAILED - 1529)
                increments the report count (FAILED - 1530)
  for Participation Records
    get_conventional_service_sends
      behaves like a participation records query
        with .neon_synced = nil
          returns the unsynced record (FAILED - 1531)
        with .neon_synced = TRUE
          does not return the record (FAILED - 1532)
        without a neon ExternalConnection.external_id
          does not return the record (FAILED - 1533)
        without an advocate_for_promoters.opt_in_id
          does not return the record (FAILED - 1534)
        with a starting @epoch
          before the record
            returns the record (FAILED - 1535)
          after the record
            does not return the record (FAILED - 1536)
        with an ending @apocalypse
          before the record
            does not return the record (FAILED - 1537)
          after the record
            returns the record (FAILED - 1538)
    get_service_deliveries
      behaves like a participation records query
        with .neon_synced = nil
          returns the unsynced record (FAILED - 1539)
        with .neon_synced = TRUE
          does not return the record (FAILED - 1540)
        without a neon ExternalConnection.external_id
          does not return the record (FAILED - 1541)
        without an advocate_for_promoters.opt_in_id
          does not return the record (FAILED - 1542)
        with a starting @epoch
          before the record
            returns the record (FAILED - 1543)
          after the record
            does not return the record (FAILED - 1544)
        with an ending @apocalypse
          before the record
            does not return the record (FAILED - 1545)
          after the record
            returns the record (FAILED - 1546)
    sync_service_send
      on success
        makes a Participation Record for each recipient with Action Type = 'Mail' (FAILED - 1547)
        syncing
          marks the ServiceSend (FAILED - 1548)
          increments the report count (FAILED - 1549)
    sync_service_delivery
      with a TwitterServiceDelivery
        on success
          makes one Participation Record with Action Type = Twitter (FAILED - 1550)
          syncing
            marks the ServiceDelivery (FAILED - 1551)
            increments the report count (FAILED - 1552)
        with a failure
          syncing
            marks the ServiceDelivery neon_unsynced and neon_unsyncable (FAILED - 1553)
            doesn't increment the report count (FAILED - 1554)
  run
    End-to-end
      with no synced Accounts
        the custom objects exist (FAILED - 1555)
    a NeonClient::PromoterWideError
      ends the run (FAILED - 1556)
    a NeonClient::AuthenticationError < NeonClient::PromoterWideError
      ends the run (FAILED - 1557)
    a regular NeonClient::Error
      doesn't end the run (FAILED - 1558)
  sync
    with errors
      a NeonClient::AuthenticationError
        ends the run (FAILED - 1559)
        running
          sends us an email (FAILED - 1560)
          the NeonSynchronizeCall
            fails the synchronize call (FAILED - 1561)
      a regular NeonClient::Error
        doesn't end the run (FAILED - 1562)
        running
          doesn't send us an email (FAILED - 1563)
          the NeonSynchronizeCall
            succeeds (FAILED - 1564)
    syncing 1 object of each type
      the NeonSynchronizeCall
        succeeds (FAILED - 1565)
        .action
          shows the total objects synced (FAILED - 1566)
    syncing multiple objects
      syncing
        the NeonSynchronizeCall
          succeeds (FAILED - 1567)
          .action
            shows the total objects synced (FAILED - 1568)
      with .limit = 1
        syncing
          the NeonSynchronizeCall
            succeeds (FAILED - 1569)
            limits synced Accounts to 1 (FAILED - 1570)
            limits synced ServiceSends to 1 (FAILED - 1571)
            .action
              shows the total objects synced (FAILED - 1572)

NeonClient::OrganizationBuilder
  should add organization_name to params
  Updating an Individual
    should carry over existing params to payload

NeonClient
  End to End
  #create_organization
    should return new Organziation json
    should raise an error if last_name is not provided
  #update_organization
    should return existing id
  #get_organization_types
    should return an Array of sources
    Array items should be hashes containing source info

NeonClient
  .find_or_setup_custom_objects
    end to end
      the custom objects do not exist
      the custom objects exist

Running a Nimble Scheduled Sync
  without a Nimble authentication
    does not call 'for' on a NimbleTransaction (FAILED - 1573)
  with one Nimble authentications
    calls delegate on a NimbleTransaction with false (FAILED - 1574)
    calls 'for' on a NimbleTransaction and passes in promoter (FAILED - 1575)
    refreshes the access token (FAILED - 1576)
    passes the new access token to the Transaction (FAILED - 1577)
    sends an email if there's an exception (FAILED - 1578)
  with two Nimble authentications
    calls NimbleTransaction.for() twice (FAILED - 1579)

NoDBBackupWriter
  backup
    with an amount and a :start_id / :end_id
      runs NoDBProcess.backup_conversions_to_nodb(amount, export_options) (FAILED - 1580)
  backup_ids
    with ids
      makes a NoDBBackupSynchronizeCall for each id (FAILED - 1581)
  backup_all
    with 3 'backup_conversions_to_nodb' transactions containing backups, and 1 without any
      makes 4 NoDBBackupSynchronizeCall (FAILED - 1582)
    with options = :export_options => { :cutoff_id => 1, :end_cutoff_id => 10 }
      passes the :cutoff_id and :end_cutoff_id to backup

NoDBPopulator
  populate
    with 2 paid, active promoters and one unpaid promoter
      without options
        runs 'populate_for' for the paid promoters (FAILED - 1583)
      with { :start_id => 1, :end_id => 10 }
        passes them to 'populate_for' for each paid promoter (FAILED - 1584)
  populate_for
    with a successful 'sync_signatures_to_nodb' transaction
      creates a NoDBSignatureSynchronizeCall (FAILED - 1585)
      the NoDBSignatureSynchronizeCall
        has the promoter's id (FAILED - 1586)
        has the status 'success' (FAILED - 1587)
        includes the count (FAILED - 1588)
    with a failed 'sync_signatures_to_nodb' transaction
      creates a NoDBSignatureSynchronizeCall (FAILED - 1589)
      the NoDBSignatureSynchronizeCall
        has the promoter's id (FAILED - 1590)
        has the status 'failure' (FAILED - 1591)
    with { :start_id => 1, :end_id => 10 }
      passes them as :cutoff_id and :end_cutoff_id to PromoterUser#get_combined_query (FAILED - 1592)
      records them on the NoDBSignatureSynchronizeCall (FAILED - 1593)
  populate_until_current_for
    with 2 good 'sync_signatures_to_nodb' transactions and a failure
      makes 3 SynchronizeCalls (FAILED - 1594)
      fails the last SynchronizeCall (FAILED - 1595)
    with 3 'sync_signatures_to_nodb' transactions containing signatures, and 1 without any
      makes 4 SynchronizeCalls (FAILED - 1596)
    with { :start_id => 1, :end_id => 10 }
      passes the :start_id and :end_id to populate_for (FAILED - 1597)
    with NoDBPopulator.new([],{ :start_id => 1, :end_id => 10 })
      passes the :start_id and :end_id to NoDBSignatureSynchronizeCall (FAILED - 1598)
  populate_from_csv
    with NoDBTransaction.sync_size = 2 and ApiDataBlock.maximum_records 10
      with 27 CSV rows
        makes an entry for every CSV row (FAILED - 1599)
        adjusts the Signature_Id values by the offset (FAILED - 1600)

NoDBStorage
  #.batch_query_signatures
    with signatures from a range of months
      processes records inside the range (FAILED - 1601)
    with multiple pages on one month
      returns records from each page (FAILED - 1602)
  #.find_or_create_table_for
    with an existing table in our ExternalConnections
      doesn't make a new ExternalConnection (FAILED - 1603)
      doesn't call NoDBStorage.create_table (FAILED - 1604)
      returns the table_name (FAILED - 1605)
    without an existing table in our ExternalConnections
      calls NoDBStorage.create_table (FAILED - 1606)
      if .create_table throws a Aws::DynamoDB::Errors::ResourceInUseException for an existing table
        makes an ExternalConnection (FAILED - 1607)
        touches the PromoterUser (FAILED - 1608)
        returns the table_name (FAILED - 1609)
      if .create_table throws a different Aws::DynamoDB::Errors::ServiceError exception
        doesn't make an ExternalConnection (FAILED - 1610)
        doesn't touch the PromoterUser (FAILED - 1611)
      if .create_table doesn't throw an exception
        makes an ExternalConnection (FAILED - 1612)
        touches the PromoterUser (FAILED - 1613)
        returns the table_name (FAILED - 1614)

RedeliverCampaignConversions
  successful calls
    with a :status parameter
      :status = done_no_targets
        passes the status to the filter (FAILED - 1615)
        redelivers matching Conversions (FAILED - 1616)
        doesn't redeliver other Conversions (FAILED - 1617)
      :status = done_all_failed
        passes the status to the filter (FAILED - 1618)
        redelivers matching Conversions (FAILED - 1619)
        doesn't redeliver other Conversions (FAILED - 1620)
      :status = done_some_failed
        passes the status to the filter (FAILED - 1621)
        redelivers matching Conversions (FAILED - 1622)
        doesn't redeliver other Conversions (FAILED - 1623)
      :status = finished
        passes the status to the filter (FAILED - 1624)
        redelivers matching Conversions (FAILED - 1625)
        doesn't redeliver other Conversions (FAILED - 1626)
      :status = stale
        passes the status to the filter (FAILED - 1627)
        redelivers matching Conversions (FAILED - 1628)
        doesn't redeliver other Conversions (FAILED - 1629)
      :status = ongoing
        passes the status to the filter (FAILED - 1630)
        redelivers matching Conversions (FAILED - 1631)
        doesn't redeliver other Conversions (FAILED - 1632)
      :status = not_verified
        passes the status to the filter (FAILED - 1633)
        redelivers matching Conversions (FAILED - 1634)
        doesn't redeliver other Conversions (FAILED - 1635)
      :status = not_submitted
        passes the status to the filter (FAILED - 1636)
        redelivers matching Conversions (FAILED - 1637)
        doesn't redeliver other Conversions (FAILED - 1638)
      :status = duplicate
        passes the status to the filter (FAILED - 1639)
        redelivers matching Conversions (FAILED - 1640)
        doesn't redeliver other Conversions (FAILED - 1641)
      :status = not_staged
        passes the status to the filter (FAILED - 1642)
        redelivers matching Conversions (FAILED - 1643)
        doesn't redeliver other Conversions (FAILED - 1644)
      :status = no_recipients
        passes the status to the filter (FAILED - 1645)
        redelivers matching Conversions (FAILED - 1646)
        doesn't redeliver other Conversions (FAILED - 1647)
    calls to generate_and_send_message
      should call generate_and_send_message on a good conversion in its time frame for its message (FAILED - 1648)
      should not call generate_and_send_message on a good conversion outside the time frame (FAILED - 1649)
      should not call generate_and_send_message on a bad conversion with a different message (FAILED - 1650)
    recalculate_recipients
      should pass the correct recipients to UpdateConversionRecipients (FAILED - 1651)
      should pass the correct recipients for multi_content to UpdateConversionRecipients (FAILED - 1652)
      should update the conversion rubberstamped column to true if it is false and promoted_message.disable_email_verifications is true (FAILED - 1653)
      should not update conversion rubberstamped column if recipients is blank (FAILED - 1654)
    Creating and updating RedeliverCampaignConversionsTask
      should successfully create a RedeliverCampaignConversionsTask object and associated conversions to it (FAILED - 1655)
  unsuccessful calls
    should respond with an error when message_id blank (FAILED - 1656)
    should respond with an error when start_time blank (FAILED - 1657)
    should respond with an error when end_time blank (FAILED - 1658)
    should respond with an error when recalculate_recipients true but no selected_recipient on promoted_message (FAILED - 1659)
    should respond with an error when results of selector.update_conversion_with_recipients are not processed (FAILED - 1660)
  Redeliver conversions
    not to include finished conversions (FAILED - 1661)
    to include some failed conversions (FAILED - 1662)
    to include all failed conversions (FAILED - 1663)

RedeliverErrorConversions
  unsuccessful calls
    should respond with an error when no conversions are found (FAILED - 1664)
    should respond with an error when no start_time are found (FAILED - 1665)
    should respond with an error when no end_time are found (FAILED - 1666)
    should respond with an error when end_time is before start_time (FAILED - 1667)
  successful calls
    with a start time
      calls generate_and_send_message on a conversion which was queued after the start_time but before the end_time (FAILED - 1668)
      doesn't call generate_and_send_message on a conversion which was queued before the start time (FAILED - 1669)
      creates a RedeliverErrorConversionsTask object (FAILED - 1670)

RedistrictAdvocatesForDistrictOrState
  Successful Calls
    for a state
      returns the correct standard outputs (FAILED - 1671)
      only calls update_districts for advocates in state (FAILED - 1672)
    for a district
      returns the correct standard outputs (FAILED - 1673)
      only calls update_districts for advocates in district (FAILED - 1674)
  Unsuccessful Calls
    should respond with an error when id blank
    should respond with an error when state_or_district incorrect value
    should respond with an error when no state/district for ID (FAILED - 1675)

ReplacedTargetUpdater
  new
    loads replaced targets (FAILED - 1676)
    maps replaced targets to replacements (FAILED - 1677)
    with older targets
      pairs the latest target from the same district (FAILED - 1678)
    without a district
      pairs targets with the same first or last name (FAILED - 1679)
  call
    for a replaced_target
      gets an affected message (FAILED - 1680)
      doesn't get unaffected messages (FAILED - 1681)
    record = false
      doesn't update affected messages (FAILED - 1682)
    record = true
      updates affected messages (FAILED - 1683)
      doesn't update unaffected messages (FAILED - 1684)

StatesByZip
  #get_state
    United Kingdom
      returns England as a state for England YO10 3XA postcode
      returns England as a state for England B27 6AQ postcode
      returns England as a state for England BA7 7QA postcode
      returns England as a state for England BB10 1AB postcode
      returns England as a state for England BD23 4AH postcode
      returns England as a state for England BH10 4AA postcode
      returns England as a state for England BL6 4YU postcode
      returns England as a state for England BN10 7WE postcode
      returns England as a state for England BR1 1UE postcode
      returns England as a state for England BS10 5AB postcode
      returns England as a state for England CH30 9AE postcode
      returns England as a state for England CW9 7DF postcode
      returns England as a state for England E14 1AP postcode
      returns England as a state for England EC1A 1BB postcode
      returns England as a state for England EN10 6XQ postcode
      returns England as a state for England EX10 0AA postcode
      returns England as a state for England GL9 1FB postcode
      returns England as a state for England GY10 1PB postcode
      returns England as a state for England HR2 0YG postcode
      returns England as a state for England L1 1AH postcode
      returns England as a state for England LA10 5GE postcode
      returns England as a state for England LE1 4GH postcode
      returns England as a state for England LN13 0DS postcode
      returns England as a state for England LS29 0XT postcode
      returns England as a state for England LU1 1YB postcode
      returns England as a state for England M11 0AY postcode
      returns England as a state for England ME10 1AB postcode
      returns England as a state for England MK10 0EE postcode
      returns England as a state for England N10 1ST postcode
      returns England as a state for England NE10 0AA postcode
      returns England as a state for England NG10 1AG postcode
      returns England as a state for England NN10 0WR postcode
      returns England as a state for England NR10 3XF postcode
      returns England as a state for England NW1 0GS postcode
      returns England as a state for England S64 0XB postcode
      returns England as a state for England SE1 0YA postcode
      returns England as a state for England SG10 6AA postcode
      returns England as a state for England SK10 1AA postcode
      returns England as a state for England SL0 0FA postcode
      returns England as a state for England SM1 1AG postcode
      returns England as a state for England SN10 1ZZ postcode
      returns England as a state for England SO14 0AB postcode
      returns England as a state for England SP10 1AJ postcode
      returns England as a state for England SR1 1AG postcode
      returns England as a state for England SS0 0AD postcode
      returns England as a state for England ST10 1AE postcode
      returns England as a state for England SW1E 5RS postcode
      returns England as a state for England W1B 1HR postcode
      returns England as a state for England WA10 1AE postcode
      returns England as a state for England WC1A 1PB postcode
      returns England as a state for England WD17 1XL postcode
      returns England as a state for England WF10 1SA postcode
      returns England as a state for England WN1 1ZL postcode
      returns England as a state for England Wr10 1yN postcode
      returns England as a state for England wa10 0aa postcode
      returns England as a state for England wV10 0Ab postcode
      returns Scotland as a state for Scotland AB10 1AB postcode
      returns Scotland as a state for Scotland DD3 0XA postcode
      returns Scotland as a state for Scotland KY16 0AA postcode
      returns Scotland as a state for Scotland EH10 4YZ postcode
      returns Scotland as a state for Scotland ML10 6AN postcode
      returns Scotland as a state for Scotland G3 7EG postcode
      returns Scotland as a state for Scotland HS3 3AA postcode
      returns Scotland as a state for Scotland IV45 8YD postcode
      returns Northern Ireland as a state for Northern Ireland BT51 3AA postcode
      returns Wales as a state for Wales LD1 5XW postcode
      returns Wales as a state for Wales SA4 0NL postcode
      returns Wales as a state for Wales LL53 5GA postcode
      returns Wales as a state for Wales CF81 8WZ postcode
      returns Wales as a state for Wales NP4 0AA postcode
  #get_area_code
    should return united_kingdom_by_prefix key KW as matched area code
    should return united_kingdom_by_prefix key IV as matched area code
    should return united_kingdom_by_prefix key AB as matched area code
    should return united_kingdom_by_prefix key PH as matched area code
    should return united_kingdom_by_prefix key DD as matched area code
    should return united_kingdom_by_prefix key PA as matched area code
    should return united_kingdom_by_prefix key FK as matched area code
    should return united_kingdom_by_prefix key KY as matched area code
    should return united_kingdom_by_prefix key G as matched area code
    should return united_kingdom_by_prefix key KA as matched area code
    should return united_kingdom_by_prefix key ML as matched area code
    should return united_kingdom_by_prefix key EH as matched area code
    should return united_kingdom_by_prefix key TD as matched area code
    should return united_kingdom_by_prefix key DG as matched area code
    should return united_kingdom_by_prefix key HS as matched area code
    should return united_kingdom_by_prefix key ZE as matched area code
    should return united_kingdom_by_prefix key CF as matched area code
    should return united_kingdom_by_prefix key LD as matched area code
    should return united_kingdom_by_prefix key LL as matched area code
    should return united_kingdom_by_prefix key NP as matched area code
    should return united_kingdom_by_prefix key SA as matched area code
    should return united_kingdom_by_prefix key BT as matched area code
    should return united_kingdom_by_prefix key AL as matched area code
    should return united_kingdom_by_prefix key B as matched area code
    should return united_kingdom_by_prefix key BA as matched area code
    should return united_kingdom_by_prefix key BB as matched area code
    should return united_kingdom_by_prefix key BD as matched area code
    should return united_kingdom_by_prefix key BH as matched area code
    should return united_kingdom_by_prefix key BL as matched area code
    should return united_kingdom_by_prefix key BN as matched area code
    should return united_kingdom_by_prefix key BR as matched area code
    should return united_kingdom_by_prefix key BS as matched area code
    should return united_kingdom_by_prefix key CA as matched area code
    should return united_kingdom_by_prefix key CB as matched area code
    should return united_kingdom_by_prefix key CH as matched area code
    should return united_kingdom_by_prefix key CM as matched area code
    should return united_kingdom_by_prefix key CO as matched area code
    should return united_kingdom_by_prefix key CR as matched area code
    should return united_kingdom_by_prefix key CT as matched area code
    should return united_kingdom_by_prefix key CV as matched area code
    should return united_kingdom_by_prefix key CW as matched area code
    should return united_kingdom_by_prefix key DA as matched area code
    should return united_kingdom_by_prefix key DE as matched area code
    should return united_kingdom_by_prefix key DH as matched area code
    should return united_kingdom_by_prefix key DL as matched area code
    should return united_kingdom_by_prefix key DN as matched area code
    should return united_kingdom_by_prefix key DT as matched area code
    should return united_kingdom_by_prefix key DY as matched area code
    should return united_kingdom_by_prefix key E as matched area code
    should return united_kingdom_by_prefix key EC as matched area code
    should return united_kingdom_by_prefix key EN as matched area code
    should return united_kingdom_by_prefix key EX as matched area code
    should return united_kingdom_by_prefix key FY as matched area code
    should return united_kingdom_by_prefix key GL as matched area code
    should return united_kingdom_by_prefix key GU as matched area code
    should return united_kingdom_by_prefix key GY as matched area code
    should return united_kingdom_by_prefix key HA as matched area code
    should return united_kingdom_by_prefix key HD as matched area code
    should return united_kingdom_by_prefix key HG as matched area code
    should return united_kingdom_by_prefix key HP as matched area code
    should return united_kingdom_by_prefix key HR as matched area code
    should return united_kingdom_by_prefix key HU as matched area code
    should return united_kingdom_by_prefix key HX as matched area code
    should return united_kingdom_by_prefix key IG as matched area code
    should return united_kingdom_by_prefix key IM as matched area code
    should return united_kingdom_by_prefix key IP as matched area code
    should return united_kingdom_by_prefix key JE as matched area code
    should return united_kingdom_by_prefix key KT as matched area code
    should return united_kingdom_by_prefix key L as matched area code
    should return united_kingdom_by_prefix key LA as matched area code
    should return united_kingdom_by_prefix key LE as matched area code
    should return united_kingdom_by_prefix key LN as matched area code
    should return united_kingdom_by_prefix key LS as matched area code
    should return united_kingdom_by_prefix key LU as matched area code
    should return united_kingdom_by_prefix key M as matched area code
    should return united_kingdom_by_prefix key ME as matched area code
    should return united_kingdom_by_prefix key MK as matched area code
    should return united_kingdom_by_prefix key N as matched area code
    should return united_kingdom_by_prefix key NE as matched area code
    should return united_kingdom_by_prefix key NG as matched area code
    should return united_kingdom_by_prefix key NN as matched area code
    should return united_kingdom_by_prefix key NR as matched area code
    should return united_kingdom_by_prefix key NW as matched area code
    should return united_kingdom_by_prefix key OL as matched area code
    should return united_kingdom_by_prefix key OX as matched area code
    should return united_kingdom_by_prefix key PE as matched area code
    should return united_kingdom_by_prefix key PL as matched area code
    should return united_kingdom_by_prefix key PO as matched area code
    should return united_kingdom_by_prefix key PR as matched area code
    should return united_kingdom_by_prefix key QC as matched area code
    should return united_kingdom_by_prefix key RG as matched area code
    should return united_kingdom_by_prefix key RH as matched area code
    should return united_kingdom_by_prefix key RM as matched area code
    should return united_kingdom_by_prefix key S as matched area code
    should return united_kingdom_by_prefix key SE as matched area code
    should return united_kingdom_by_prefix key SG as matched area code
    should return united_kingdom_by_prefix key SK as matched area code
    should return united_kingdom_by_prefix key SL as matched area code
    should return united_kingdom_by_prefix key SM as matched area code
    should return united_kingdom_by_prefix key SN as matched area code
    should return united_kingdom_by_prefix key SO as matched area code
    should return united_kingdom_by_prefix key SP as matched area code
    should return united_kingdom_by_prefix key SR as matched area code
    should return united_kingdom_by_prefix key SS as matched area code
    should return united_kingdom_by_prefix key ST as matched area code
    should return united_kingdom_by_prefix key SW as matched area code
    should return united_kingdom_by_prefix key TA as matched area code
    should return united_kingdom_by_prefix key TF as matched area code
    should return united_kingdom_by_prefix key TN as matched area code
    should return united_kingdom_by_prefix key TQ as matched area code
    should return united_kingdom_by_prefix key TR as matched area code
    should return united_kingdom_by_prefix key TS as matched area code
    should return united_kingdom_by_prefix key TW as matched area code
    should return united_kingdom_by_prefix key UB as matched area code
    should return united_kingdom_by_prefix key W as matched area code
    should return united_kingdom_by_prefix key WA as matched area code
    should return united_kingdom_by_prefix key WC as matched area code
    should return united_kingdom_by_prefix key WD as matched area code
    should return united_kingdom_by_prefix key WF as matched area code
    should return united_kingdom_by_prefix key WN as matched area code
    should return united_kingdom_by_prefix key WR as matched area code
    should return united_kingdom_by_prefix key WS as matched area code
    should return united_kingdom_by_prefix key WV as matched area code
    should return united_kingdom_by_prefix key YO as matched area code
    should return united_kingdom_by_prefix key SY as matched area code

Sync Signatures CSV
  Errors
    marks transaction as failed and sends slack notification if error with service call (FAILED - 1685)
  Full Results
    if a LocalTransaction exists with an end_cutoff_date_time
      with no new Custom Fields
        appends the new record (FAILED - 1686)
      with new Custom Fields
        overwrites existing records and includes custom fields (FAILED - 1687)
    with 30 older signatures
      and 10 recent signatures
        processing a set_sync_size of 29
          with a BatchedQuery block size of 10
            the Transaction
              behaves like a Transaction with set_sync_size
                returns set_sync_size rows (FAILED - 1688)
                uses the timestamp from the last row (FAILED - 1689)
                uses the id from the last row (FAILED - 1690)
              a follow-up Transaction with set_sync_size 5
                behaves like a Transaction with set_sync_size
                  returns set_sync_size rows (FAILED - 1691)
                  uses the timestamp from the last row (FAILED - 1692)
                  uses the id from the last row (FAILED - 1693)
          with a BatchedQuery block size of 300
            the Transaction
              behaves like a Transaction with set_sync_size
                returns set_sync_size rows (FAILED - 1694)
                uses the timestamp from the last row (FAILED - 1695)
                uses the id from the last row (FAILED - 1696)
              a follow-up Transaction with set_sync_size 5
                behaves like a Transaction with set_sync_size
                  returns set_sync_size rows (FAILED - 1697)
                  uses the timestamp from the last row (FAILED - 1698)
                  uses the id from the last row (FAILED - 1699)
        processing a set_sync_size of 31
          with a BatchedQuery block size of 10
            the Transaction
              behaves like a Transaction with set_sync_size
                returns set_sync_size rows (FAILED - 1700)
                uses the timestamp from the last row (FAILED - 1701)
                uses the id from the last row (FAILED - 1702)
          with a BatchedQuery block size of 300
            the Transaction
              behaves like a Transaction with set_sync_size
                returns set_sync_size rows (FAILED - 1703)
                uses the timestamp from the last row (FAILED - 1704)
                uses the id from the last row (FAILED - 1705)
    with 40 randomized opt-in/opt-out signatures
      with a BatchedQuery block size of 10
        processing 15, then 20, then 5
          adds all 40 unique signatures (FAILED - 1706)
          the Transactions
            Transaction 1
              behaves like a Transaction with set_sync_size
                the cutoff date
                  matches this transaction's last row (FAILED - 1707)
                the cutoff id
                  matches this transaction's last row (FAILED - 1708)
                the result count
                  matches the set_sync_size (FAILED - 1709)
            Transaction 2
              behaves like a Transaction with set_sync_size
                the cutoff date
                  matches this transaction's last row (FAILED - 1710)
                the cutoff id
                  matches this transaction's last row (FAILED - 1711)
                the result count
                  matches the set_sync_size (FAILED - 1712)
            Transaction 3
              behaves like a Transaction with set_sync_size
                the cutoff date
                  matches this transaction's last row (FAILED - 1713)
                the cutoff id
                  matches this transaction's last row (FAILED - 1714)
                the result count
                  matches the set_sync_size (FAILED - 1715)
      with a BatchedQuery block size of 100
        processing 15, then 20, then 5
          adds all 40 unique signatures (FAILED - 1716)
          the Transactions
            Transaction 1
              behaves like a Transaction with set_sync_size
                the cutoff date
                  matches this transaction's last row (FAILED - 1717)
                the cutoff id
                  matches this transaction's last row (FAILED - 1718)
                the result count
                  matches the set_sync_size (FAILED - 1719)
            Transaction 2
              behaves like a Transaction with set_sync_size
                the cutoff date
                  matches this transaction's last row (FAILED - 1720)
                the cutoff id
                  matches this transaction's last row (FAILED - 1721)
                the result count
                  matches the set_sync_size (FAILED - 1722)
            Transaction 3
              behaves like a Transaction with set_sync_size
                the cutoff date
                  matches this transaction's last row (FAILED - 1723)
                the cutoff id
                  matches this transaction's last row (FAILED - 1724)
                the result count
                  matches the set_sync_size (FAILED - 1725)
      syncing :set_sync_size=5
        has 5 lines (FAILED - 1726)
        then syncing all
          has 40 lines (FAILED - 1727)
          with 20 more sigs
            syncing :set_sync_size=5
              has 45 lines (FAILED - 1728)
              then syncing all
                has 60 lines (FAILED - 1729)
                the Transactions
                  have the correct counts (FAILED - 1730)
        for back-compatibility
          syncing via timestamp
            with 20 more sigs
              syncing :set_sync_size=5
                has 45 lines (FAILED - 1731)
                the new LocalTransaction
                  adds id stamps (FAILED - 1732)
  Demo Vs. Non-Demo User results
    for demo users
      when we exceed the cutoff
        the signatures .CSV link
          returns a CSV (FAILED - 1733)
          the returned CSV
            limits us to 50 email signatures (FAILED - 1734)
    for non-demo users
      when we exceed the cutoff
        the signatures .CSV link
          returns a CSV (FAILED - 1735)
          the returned CSV
            doesn't limit us to 50 email signatures (FAILED - 1736)
  facebook_handle and twitter_handle display
    the CSV
      includes the social media handles (FAILED - 1737)
  Opt Out vs. Opt In behavior
    an opt-out signature
      example at ./spec/libs/sync_signatures_csv_spec.rb:610 (FAILED - 1738)
      example at ./spec/libs/sync_signatures_csv_spec.rb:611 (FAILED - 1739)
      example at ./spec/libs/sync_signatures_csv_spec.rb:612 (FAILED - 1740)
    an opt-in signature
      example at ./spec/libs/sync_signatures_csv_spec.rb:617 (FAILED - 1741)
      example at ./spec/libs/sync_signatures_csv_spec.rb:618 (FAILED - 1742)
      example at ./spec/libs/sync_signatures_csv_spec.rb:619 (FAILED - 1743)
  with conversion address columns like conversion_line1, conversion_city etc.
    displays ConventionalServiceSend address columns if one exists on a conversion object (FAILED - 1744)

SignatureCSVGenerator
  generates a forward-compatible CSVSynchronizeCall (FAILED - 1745)
  takes arrays of promoter ids (FAILED - 1746)
  takes individual promoter ids (FAILED - 1747)
  doesn't take unpaid promoters (FAILED - 1748)
  #generate_until_current_for( promoter_user_id )
    with 45000 signatures needed
      with 10000 per call
        runs five times (FAILED - 1749)
    with an ongoing global CSVSynchronizeCall
      proceeds (FAILED - 1750)

TurnOffTwitterForPromoterCampaigns
  #call
    with no promoter id provided
      should create a new StandardError
    with correct params
      should successfully turn off the Twitter action for campaigns belonging to the provided promoter (FAILED - 1751)
      where a campaign fails to save
        should log campaigns that failed to save (FAILED - 1752)

Notifier
  agent_error_alert
    is addressed to the dev group email
    includes the environment name in the subject
    renders the error name and backtrace in the body

Account
  should be valid
  should be invalid when empty
  should be valid with names and email
  should be valid with names and facebook id (FAILED - 1753)
  should be valid and activated with names and facebook id (FAILED - 1754)
  validate_zip (PENDING: No reason given)
  should change status from confirmed to active if user valid
  has all the proper columns
    should have db column named email of type string
    should have db column named crypted_password of type string
    should have db column named password_salt of type string
    should have db column named persistence_token of type string
    should have db column named perishable_token of type string of null false
    should have db column named login_count of type integer of default 0 of null false
    should have db column named last_request_at of type datetime
    should have db column named last_login_at of type datetime
    should have db column named current_login_at of type datetime
    should have db column named last_login_ip of type string
    should have db column named current_login_ip of type string
    should have db column named last_request_at of type datetime
    should have db column named last_login_at of type datetime
    should have db column named status of type string of default new of null false
    should have db column named quota_msg_count of type integer of default 0
    should have db column named quota_start_time of type datetime
    should have db column named sent_messages_count of type integer of default 0
    should have db column named facebook_uid of type integer of limit 8
    should have db column named facebook_session_key of type string
    should have db column named default_shared_flg of type boolean of default true of null false
    should have db column named widgets of type string of limit 512
    should have db column named roles_mask of type integer of default 0
  should validate
    presence of email or facebook id (FAILED - 1755)
    uniqueness of email (FAILED - 1756)
  should not validate account
    if only magic columns are changed and status is confirmed (FAILED - 1757)
    if no columns are changed and status is confirmed (FAILED - 1758)
    if some of non-address columns were changed and status is confirmed (FAILED - 1759)
    if some of address columns were changed and status is confirmed (FAILED - 1760)
  should validate account
    if magic columns and other columns are changed and status is confirmed (FAILED - 1761)
  when :is_required_full_validation should
    validate zip (PENDING: No reason given)
    when it validates with full validation
      validate presence of line1
      validate presence of city
      validate presence of state
  activate!
    should change state to confirmed from new (FAILED - 1762)
    should not deliver confirmation emails for the time being
    should change state to confirmed from new (FAILED - 1763)

ActionCenterPagePromotedMessage
  associations
    should belong to action_center_page
    should belong to promoted_message
  validations
    should require action_center_page_id to be set
    should require promoted_message_id to be set

ActionCenterPage
  associations
    should have many action_center_page_promoted_messages
    should have many promoted_messages through action_center_page_promoted_messages
    should belong to us_states
    should belong to action_center
  validations
    should require action_center_id to be set
    should have a type_of FEDERAL of STATE (FAILED - 1764)
    should have a us_states_id if should_be_filled_in? (FAILED - 1765)
  scopes
    should corrected scope ordered_by_state (FAILED - 1766)

ActionCenter
  should have many slider_panels
  should have many action_center_pages
  should have many us_states through action_center_pages
  should belong to promoter_user
  Validations
    should require promoter_user_id to be set
  After Hooks
    should create_action_center_pages in an after_create (FAILED - 1767)

AdvocateForPromoter
  associations
    should belong to promoter_user
    should belong to advocate_profile
    should belong to opt_in
  validations
    should have an advocate_profile_id (FAILED - 1768)
    should have a promoter_user_id (FAILED - 1769)
    should have a unique advocate_profile_id scoped to the promoter_user_id (FAILED - 1770)
  methods
    should return opted_in? correctly (FAILED - 1771)
    should correctly opt_out (FAILED - 1772)

AdvocateProfile
  associations
    should have many sender_profiles
    should have many service_deliveries through sender_profiles
    should have many advocate_for_promoters
    should have many promoter_users through advocate_for_promoters
    should belong to state class_name => UsStates
    should belong to state_senate_district
    should belong to state_house_district
    should belong to congressional_district
    should belong to city_council_district
    should have many external_connections
  validations
    should have a unique email but allow nils (FAILED - 1773)
    should have a valid email (FAILED - 1774)
    should have a unique identifier (FAILED - 1775)
  methods
    update_districts
      without params should save district associations on a profile (FAILED - 1776)
      with_save=false should not save anything (FAILED - 1777)
  after hooks
    should unassign_sender_profiles after destroy (FAILED - 1778)
    assign_districts
      should call update_districts(false) when latitude or longitude change (FAILED - 1779)
      should not call update_districts(false) if latitude and longitude stay the same (FAILED - 1780)

ApiKey
  validations
    with an existing key for a PromoterUser
      a new key for the same PromoterUser
        is invalid (FAILED - 1781)
      a new key for a different PromoterUser
        is valid (FAILED - 1782)
  creating a new ApiKey
    generates a key token string (FAILED - 1783)
    makes a RedisApiKey for the ApiKey (FAILED - 1784)
    the RedisApiKey
      has a matching key (FAILED - 1785)
  updating an ApiKey's key token string
    updates the RedisApiKey (FAILED - 1786)

ApplicationSwitch
  validations
    object
      with valid params
        should be valid (FAILED - 1787)
      with nil name
        should be invalid (FAILED - 1788)
      with duplicate name
        should be invalid (FAILED - 1789)
      with description longer than 500 characters
        should be invalid (FAILED - 1790)
      with non approved name
        should be invalid (FAILED - 1791)
  scope
    enabled_switches
      should return all enabled switches (FAILED - 1792)
    disabled_switches
      should return all disabled switches (FAILED - 1793)
  #destroy
    should set deleted_at without completely destroying object (FAILED - 1794)
  callbacks
    before_save
      should strip whitespace from fields (FAILED - 1795)
  enabled_for_promoter?
    for an enabled app switch
      without whitelisted or blacklisted values
        should return true for all promoters (FAILED - 1796)
      with whitelisted values
        while enabled globally (global_override) is on
          should return true for all promoters (FAILED - 1797)
        while enabled globally (global_override) is off
          should return all whitelisted promoters (FAILED - 1798)
          should return all whitelisted promoters regardless of id format (FAILED - 1799)
      with blacklisted values
        while enabled globally (global_override) is on
          should return true for all promoters (FAILED - 1800)
        while enabled globally (global_override) is off
          should return all promoters excluding blacklisted (FAILED - 1801)
    for a disabled app switch
      should return false (FAILED - 1802)
  enabled?
    for an enabled app switch
      while enabled is on
        should return true (FAILED - 1803)
      while enabled is off
        should return false (FAILED - 1804)
  enabled_globally?
    for an enabled app switch
      while enabled globally (global_override) is on
        should return true (FAILED - 1805)
      while enabled globally (global_override) is off
        should return false (FAILED - 1806)
    for a disabled app switch
      should return false (FAILED - 1807)
  enable_promoter, default blacklist
    for a promoter that starts disabled (is blacklisted)
      should be enabled afterwards (FAILED - 1808)
    for a promoter that starts enabled (not listed, white or black)
      should still be enabled afterwards (FAILED - 1809)
  enable_promoter, using whitelist
    for a promoter that starts disabled (not listed, white or black)
      should be enabled afterwards (FAILED - 1810)
    for a promoter that starts enabled (is whitelisted)
      should still be enabled afterwards (FAILED - 1811)
  enable_promoter, using blacklist
    for a promoter that starts disabled (is blacklisted)
      should be enabled afterwards (FAILED - 1812)
    for a promoter that starts enabled (not listed, white or black)
      should still be enabled afterwards (FAILED - 1813)
  disable_promoter, default blacklist
    for a promoter that starts disabled (is blacklisted)
      should still be disabled afterwards (FAILED - 1814)
    for a promoter that starts enabled (not listed, white or black)
      should still be disabled afterwards (FAILED - 1815)
  disable_promoter, using whitelist
    for a promoter that starts disabled (not listed, white or black)
      should still be disabled afterwards (FAILED - 1816)
    for a promoter that starts enabled (is whitelisted)
      should be disabled afterwards (FAILED - 1817)
  disable_promoter, using blacklist
    for a promoter that starts disabled (is blacklisted)
      should still be disabled afterwards (FAILED - 1818)
    for a promoter that starts enabled (not listed, white or black)
      should be disabled afterwards (FAILED - 1819)

ArchiveMessage
  #body
    returns the bodycachd attribute

BlogArticle
  should require title to be set
  should require description to be set
  should require content to be set
  should require image to be set
  length validation
    should limit title to 255 characters (FAILED - 1820)
    should limit description to 255 characters (FAILED - 1821)
  slug
    should return url friendly sluggified title (FAILED - 1822)
    should handle duplicate titles gracefully (FAILED - 1823)
  strip_fields
    should successfully strip text field values on save (FAILED - 1824)

CityCouncilDistrict
  associations
    should have many advocate_profiles
  CityCouncilDistrict.cities
    with San Jose and Los Angeles districts
      includes San Jose and Los Angeles (FAILED - 1825)
      doesn't include other cities (FAILED - 1826)

Committee
  scopes
    returns Committees for_constituency_and_state (FAILED - 1827)
    returns Committees for_constituency_and_state_without_joint (FAILED - 1828)
    returns Committees all_non_local_for_state (FAILED - 1829)
    returns Committees that are top_level (FAILED - 1830)
    returns Committees that are sub_committees (FAILED - 1831)
  def sub_committes_for_parent_committee
    should return active child committees (FAILED - 1832)
  methods
    should return committees by_state_code_and_filter (FAILED - 1833)

CommitteeTerritoryRecipient
  associations
    should belong to recipient
  validations
    should require recipient_id to be set
    should require state to be set
    should require name to be set

CongressionalDistrict
  associations
    should have many advocate_profiles

ConventionalServiceSend
  methods
    should return recipients (FAILED - 1834)
    should return recipient_ids_local (FAILED - 1835)
    should return recipient_ids_always_send (FAILED - 1836)
    should return recipient_ids_always_send_and_local (FAILED - 1837)
    should return recipient_ids_expanded (FAILED - 1838)
    should return recipient_ids_expanded_content_one (FAILED - 1839)
    should return recipient_ids_expanded_content_two (FAILED - 1840)
    should correctly make_for_conversion (FAILED - 1841)

Conversion
  associations
    should have one promoter through promoted_message
    should have one advocate_profile through sender
    should have many conventional_service_sends
    should have and belong to many redelivery_tasks (FAILED - 1842)
  scopes
    returns conversions delivered_during (FAILED - 1843)
    returns with_reached_recipients (FAILED - 1844)
  methods
    #service_send_details
      no arguments returns nil
      no conversion with service send returns empty array (FAILED - 1845)
      returns video details when conversion has video service send (FAILED - 1846)
      returns phone details when conversion has phone service send (FAILED - 1847)
    #phone_details
      returns empty hash when no service_send (FAILED - 1848)
      return call_duration and service_send_id (FAILED - 1849)
    #video_details
      returns empty hash when no service_send (FAILED - 1850)
      return video_token and service_send_id (FAILED - 1851)
  #undelivered
    includes conversions with finished_and_archived_to set to nil (FAILED - 1852)
    doesn't include conversions with non-nil finished_and_archived_to (FAILED - 1853)
    doesn't include conversions that aren't rubberstamped OR permitted (FAILED - 1854)
  generate_and_send_message
    the always_send_ids_array for send_options
      when conversion does not have recipient_ids_always_send
        sets always_send_ids_array to the selected_recipient always_send_recipients_code_ids (FAILED - 1855)
      when conversion has recipient_ids_always_send
        sets always_send_ids_array to the recipient_ids_always_send column (FAILED - 1856)
    the local_recipient_ids_array for send_options
      when conversion does not have recipient_ids_local
        sets local_recipient_ids_array to Recipient.local_for (FAILED - 1857)
      when conversion has recipient_ids_local
        sets local_recipient_ids_array to the recipient_ids_local column (FAILED - 1858)
  with NoDB Signatures enabled
    .create
      a new opt-in Conversion with a SenderProfile
        behaves like making an opt-in NoDB signature
          records a NoDB Signature (FAILED - 1859)
          the signature
            shows sensitive fields (FAILED - 1860)
      a Conversion without a SenderProfile
        doesn't record a NoDB Signature (FAILED - 1861)
      an opt-out Conversion
        behaves like making an opt-out NoDB signature
          records a NoDB Signature (FAILED - 1862)
          the signature
            hides sensitive fields (FAILED - 1863)
      passing :share => 'on'
        behaves like making an opt-in NoDB signature
          records a NoDB Signature (FAILED - 1864)
          the signature
            shows sensitive fields (FAILED - 1865)
      passing :share => 'off'
        behaves like making an opt-out NoDB signature
          records a NoDB Signature (FAILED - 1866)
          the signature
            hides sensitive fields (FAILED - 1867)
      passing :skip_nodb => true
        doesn't record a NoDB signature (FAILED - 1868)
    .save and .update
      with an existing NoDB signature
        updating the sender_..._for_recipients fields
          updates the signature (FAILED - 1869)
        updating other fields
          doesn't update the NoDB signature (FAILED - 1870)
      without an existing NoDB signature
        updating a sender_..._for_recipients field
          records a NoDB signature (FAILED - 1871)

CouncilMember
  should respond to #name
  should respond to #district_id
  should respond to #state
  should be valid
  when name is not present
    should not be valid
  when district_id is not present
    should be valid
  when state is not present
    should not be valid
  CouncilMember.search
    searching in San Jose
      returns matches in San Jose (FAILED - 1872)
      doesn't return matches in Los Angeles (FAILED - 1873)
      doesn't return inactive members (FAILED - 1874)
  CouncilMember.by_city
    Los Angeles
      doesn't return CouncilMembers in San Jose (FAILED - 1875)
      returns CouncilMembers in Los Angeles (FAILED - 1876)
      doesn't return inactive CouncilMembers (FAILED - 1877)

CsvInBucket
  associations
    should belong to local_transaction

District
  associations
    should belong to state class_name => UsStates
  to_s
    should return district name (FAILED - 1878)
  in USA
    should #contain a point within its boundary (FAILED - 1879)
    should not #contain a point without its boundary (FAILED - 1880)
  in New York City
    in USA
      should #contain a point within its boundary (FAILED - 1881)
      should not #contain a point without its boundary (FAILED - 1882)
  in Australia
    North Sydney
      should contain North Sydney points (FAILED - 1883)
      should not contain Melbourne Ports points (FAILED - 1884)
    Melbourne Ports
      should not contain North Sydney points (FAILED - 1885)
      should not contain Melbourne Ports points (FAILED - 1886)
  in Canada
    Drummond, QC
      should contain Drummond points (FAILED - 1887)
      should not contain Cambridge points (FAILED - 1888)
    Cambridge, ON
      should not contain Drummond points (FAILED - 1889)
      should contain Cambridge points (FAILED - 1890)

EmailAddress
  example at ./spec/models/email_address_spec.rb:8 (FAILED - 1891)
  when email has apostrophe before @
    example at ./spec/models/email_address_spec.rb:12 (FAILED - 1892)
  when email domain is quebec
    example at ./spec/models/email_address_spec.rb:18 (FAILED - 1893)
  when email domain is 4 characters
    example at ./spec/models/email_address_spec.rb:23 (FAILED - 1894)
  when email domain is 3 characters
    example at ./spec/models/email_address_spec.rb:28 (FAILED - 1895)
  when email domain is 2 characters
    example at ./spec/models/email_address_spec.rb:33 (FAILED - 1896)
  when email domain is 1 character
    example at ./spec/models/email_address_spec.rb:38 (FAILED - 1897)
  when email has apostrophe after @
    example at ./spec/models/email_address_spec.rb:43 (FAILED - 1898)
  when email domain is longer than 4 characters
    example at ./spec/models/email_address_spec.rb:48 (FAILED - 1899)

ExternalConnection
  Associations
    example at ./spec/models/external_connection_spec.rb:16 (FAILED - 1900)
    example at ./spec/models/external_connection_spec.rb:17 (FAILED - 1901)
  Validations
    example at ./spec/models/external_connection_spec.rb:21 (FAILED - 1902)
    example at ./spec/models/external_connection_spec.rb:22 (FAILED - 1903)
    example at ./spec/models/external_connection_spec.rb:23 (FAILED - 1904)
    should validate inclusion of :provider in ExternalConnction::PROVIDERS (FAILED - 1905)
    Uniquness scope for :provider. Sanity check for shoulda matcher above
      should not create an identical Record for the same Record and PromoterUser (FAILED - 1906)
      should not validate if Record is different (FAILED - 1907)
      should validate if PromoterUser is different (FAILED - 1908)
  Methods
    #do_sync?
      should return true if Record was updated AFTER last_sync (FAILED - 1909)
      should return true if @record.updated_at is blank (FAILED - 1910)
      should return true if :last_update is true (FAILED - 1911)
      should return false if :unsyncable? is true,
          even if record_is_synced? (Private Method) is false (FAILED - 1912)
      should return false if :last_update is falsey AND :error_messasge is not blank (FAILED - 1913)
      should return false if Record was updated AFTER last_sync (FAILED - 1914)
      should return false if :error_message is not blank (FAILED - 1915)
      should return true if external_id is blank (FAILED - 1916)
      should return false if extenal_id is nil and :error_message is not blank (FAILED - 1917)
    #unsyncable?
      should return true if :error_message is not blank (FAILED - 1918)
      should return false if :error_message is blank (FAILED - 1919)
    #reset!
      should set :error_message to nil (FAILED - 1920)
      should set external_id to nil (FAILED - 1921)
  Class Methods
    Scopes
      #for(provider, promoter_user_id = nil)
        should return an array of ExternalConnections for provider (FAILED - 1922)
        should return ExternalConnections for specific providers (FAILED - 1923)
        should return a single ExternalConnection for PromoterUser, if promoter_user_id is provided (FAILED - 1924)

HistoricalRecipientRelation
  Validations
    only allows one active HistoricalRecipientRelation at a time (FAILED - 1925)

LocalTransaction
  associations
    should have one csv_in_bucket
  dependent destroy
    should destroy associated csv_in_bucket on destroy (FAILED - 1926)
  display_errors
    should display error correctly without their key values
  .run_service( 'sync_signatures_csv' )
    beneath LocalTransaction max_sync_size
      is valid (FAILED - 1927)
    exceeding LocalTransaction max_sync_size
      is NOT valid (FAILED - 1928)
      with param run_outside_rabbit=true
        is valid (FAILED - 1929)
      with param :set_sync_size < max_sync_size
        is valid (FAILED - 1930)
    with non-rubberstamped/non-permitted signatures
      includes them (FAILED - 1931)
      exceeding LocalTransaction max_sync_size
        is not valid (FAILED - 1932)
    .is_hanging?
      .status = 'failed'
        is false (FAILED - 1933)
      .status = 'success'
        is false (FAILED - 1934)
      .status = 'in_progress'
        older than staleness_timeout_in_minutes
          is true (FAILED - 1935)
        younger than staleness_timeout_in_minutes
          is false (FAILED - 1936)
    with an ongoing sync
      for this promoter and action
        is NOT valid (FAILED - 1937)
      for another promoter
        is valid (FAILED - 1938)
      for another action
        is valid (FAILED - 1939)
      older than class.staleness_timeout_in_minutes
        is valid (FAILED - 1940)
      newer than class.staleness_timeout_in_minutes
        is NOT valid (FAILED - 1941)
    .previous
      with an unspecified but successful previous transaction
        auto-fetches the previous transaction (FAILED - 1942)
      for an unspecified but unsuccessful transaction
        doesn't fetch the previous transaction (FAILED - 1943)
      for another promoter
        doesn't fetch the previous transaction (FAILED - 1944)

Mayor
  should respond to #name
  should respond to #state
  should be valid
  when name is not present
    should not be valid
  when state is not present
    should not be valid

Message
  should be invalid when empty
  should be valid with all correct fields
  should validate
    presence of subject
    presence of body
    presence of recipient_ids
    quota
    when multi_content=true
      behaves like a content filter for
        filters obscenity
        filters tags
        filters urls
      behaves like a content filter for
        filters obscenity
        filters tags
        filters urls
  should correctly set recipients
    from array (FAILED - 1945)
    but should raise exception if no array given (FAILED - 1946)

NewDistrict
  in UK
    should have the correct SRID for the cicero shapefiles currently used
    #reset_table?
      clears existing NewDistrict records (FAILED - 1947)
      adds custom UK uk_geom column (FAILED - 1948)
      adds custom UK district_i column (FAILED - 1949)
      adds custom UK city column (FAILED - 1950)
      adds custom UK state column (FAILED - 1951)
      adds custom UK district_t column (FAILED - 1952)
      adds custom UK subtype column (FAILED - 1953)
      adds custom UK valid_from column (FAILED - 1954)
      adds custom UK valid_to column (FAILED - 1955)
      adds custom UK ocd_id column (FAILED - 1956)

NoDBTransaction
  associations
    should have one csv_in_bucket
  .run_service( 'sync_signatures_to_nodb' )
    with an already-synced Conversion
      the sync
        doesn't include it (FAILED - 1957)
    with mixed signatures
      the sync
        includes the unsynced Conversions (FAILED - 1958)
        updates the .signature_in_nodb_at timestamps (FAILED - 1959)
      the NoDB table
        has all 3 items (FAILED - 1960)
        the opt-out item
          hides opt-out info (FAILED - 1961)
        the verified item
          shows Authenticated='yes' (FAILED - 1962)
    with custom fields
      the NoDB table
        the item
          shows the custom fields (FAILED - 1963)
    with export_options['cutoff_id'] and export_options['end_cutoff_id']
      passes the :cutoff_id and :end_cutoff_id to PromoterUser#get_combined_query (FAILED - 1964)
    without export_options
      doesn't pass the :cutoff_id and :end_cutoff_id to PromoterUser#get_combined_query (FAILED - 1965)
  .run_service( 'sync_signature_to_nodb' )
    without a Signature to sync
      is NOT valid (FAILED - 1966)
    with an opt-in Conversion
      with a full Signature to sync
        updates the .signature_in_nodb_at timestamps (FAILED - 1967)
        the NoDB table
          has an item (FAILED - 1968)
        the item
          shows opt-in info (FAILED - 1969)
          shows custom fields (FAILED - 1970)
  .run_service( 'update_signature_on_nodb' )
    without a Signature to sync
      is NOT valid (FAILED - 1971)
    with an existing NoDB table
      for an opt-in NoDB item
        updating with a ConventionalServiceSend
          the item
            overwrites with new address info (FAILED - 1972)
            doesn't overwrite fields left blank (FAILED - 1973)
        updating with a new twitter_handle
          the item
            updates the Twitter handle (FAILED - 1974)
            doesn't change address info (FAILED - 1975)
      for an opt-out NoDB item
        updating with a new ConventionalServiceSend
          the item
            leaves sensitive fields blank (FAILED - 1976)
            writes new non-sensitive info (FAILED - 1977)
  .run_service( 'write_csv_from_nodb' )
    without a destination_email
      is NOT valid (FAILED - 1978)
    with a destination_email
      if all services succeed
        creates a CsvInBucket (FAILED - 1979)
        sends an email (FAILED - 1980)
        the email
          links the CSV (FAILED - 1981)
      with a start_month and an end_month as export_options
        if all services succeed
          passes start_month and end_month to NoDBStorage.batch_query_signatures (FAILED - 1982)
        if start_month = end_month
          is valid (FAILED - 1983)
        if start_month > end_month
          is NOT valid (FAILED - 1984)
  .run_service( 'export_signatures_to_s3_via_node' )
    if S3Storage fails
      fails the Transaction (FAILED - 1985)
    if the node script returns a stderr string
      fails the Transaction (FAILED - 1986)
    if the node script runner throws an exception / fails
      fails the Transaction (FAILED - 1987)
    if all services succeed
      calls NoDBStorage.instance.send_to_s3_via_nodejs (FAILED - 1988)
      with several output files on S3
        the Transaction
          returns an array of the files (FAILED - 1989)
  .run_service( 'export_signatures_to_s3_via_pipeline' )
    without a destination_email
      is NOT valid (FAILED - 1990)
    with a destination_email
      if all services succeed
        calls NoDBPipeline.instance.export_csv (FAILED - 1991)
  .run_service( 'backup_conversions_to_nodb' )
    with an already-backed up Conversion
      the sync
        doesn't include it (FAILED - 1992)
    with mixed signatures
      the sync
        includes the unsynced Conversions (FAILED - 1993)
        updates the .backup_in_nodb_at timestamps (FAILED - 1994)
      the NoDB table
        has all 3 items (FAILED - 1995)
        the verified item
          shows Conversion attributes (FAILED - 1996)
    with export_options['cutoff_id'] and export_options['end_cutoff_id']
      passes the :cutoff_id and :end_cutoff_id to Conversion.without_nodb_backups (FAILED - 1997)
    without export_options
      doesn't pass the :cutoff_id and :end_cutoff_id to Conversion.without_nodb_backups (FAILED - 1998)
  .run_service( 'backup_conversion_to_nodb' )
    without a Conversion to sync
      is NOT valid (FAILED - 1999)
    with an opt-in Conversion
      with a full Conversion to sync
        updates the .signature_in_nodb_at timestamps (FAILED - 2000)
        the NoDB table
          has an item (FAILED - 2001)
        the item
          shows Conversion info (FAILED - 2002)
  .run_service( 'sync_signature_blocks_to_nodb' )
    without block_ids
      is NOT valid (FAILED - 2003)
    with blocks and block_ids
      the NoDB table
        records the items (FAILED - 2004)
        each item
          shows standard signature info (FAILED - 2005)
          shows custom fields (FAILED - 2006)

Office
  associations
    should belong to office_type
    should have many recipients
  methods
    should return correct offices for select_by_chamber_level_and_country (FAILED - 2007)
    should return UK office for select_by_chamber_level_and_country (FAILED - 2008)
    should return US State Senate as default for incorrect params passed to select_by_chamber_level_and_country (FAILED - 2009)
  validations
    should have a unique name (FAILED - 2010)

OptIn
  associations
    should belong to account
    should belong to promoter_user
    should belong to sender_profile
    should have one advocate_for_promoter
  methods
    exists_for_sender_and_promoter?
      returns false if no sender_profile in params (FAILED - 2011)
      returns false if no promoter_user in params (FAILED - 2012)
      should return exists_for_sender_and_promoter? (FAILED - 2013)
      should not return exists_for_sender_and_promoter if an opt_in is for a different sender (FAILED - 2014)

PhoneServiceSend
  #get_recipients_json
    when there's no exception
      returns the result of JSON.parse(self.recipients_json) (FAILED - 2015)
    when an exception is raised
      logs the exception (FAILED - 2016)
      returns a blank array (FAILED - 2017)
      rescues the exception (doesn't bubble up) (FAILED - 2018)

Product
  example at ./spec/models/product_spec.rb:12 (FAILED - 2019)
  example at ./spec/models/product_spec.rb:13 (FAILED - 2020)
  example at ./spec/models/product_spec.rb:14 (FAILED - 2021)
  example at ./spec/models/product_spec.rb:15 (FAILED - 2022)
  example at ./spec/models/product_spec.rb:16 (FAILED - 2023)
  example at ./spec/models/product_spec.rb:17 (FAILED - 2024)
  example at ./spec/models/product_spec.rb:18 (FAILED - 2025)
  example at ./spec/models/product_spec.rb:19 (FAILED - 2026)
  example at ./spec/models/product_spec.rb:20 (FAILED - 2027)
  example at ./spec/models/product_spec.rb:21 (FAILED - 2028)
  example at ./spec/models/product_spec.rb:22 (FAILED - 2029)
  example at ./spec/models/product_spec.rb:24 (FAILED - 2030)
  when description is not present
    example at ./spec/models/product_spec.rb:28 (FAILED - 2031)
  when tier is not present
    example at ./spec/models/product_spec.rb:33 (FAILED - 2032)
  when price is not present
    example at ./spec/models/product_spec.rb:38 (FAILED - 2033)
  #set_price
    activist
      example at ./spec/models/product_spec.rb:58 (FAILED - 2034)
      with add-ons
        adds $40 for sender_data (FAILED - 2035)
        adds $10 for message_edit (FAILED - 2036)
        adds $10 for state_access (FAILED - 2037)
        adds $50 for multiple_state_access (FAILED - 2038)
        adds $50 for donation_redirect (FAILED - 2039)
        adds $50 for custom_recipients (FAILED - 2040)
        adds $50 for remove_branding (FAILED - 2041)
        doesn't add $20 for receiving replies (FAILED - 2042)
        adds $60 for custom_recipients and message_edit (FAILED - 2043)
        adds $50 for custom_widget (FAILED - 2044)
    cause
      example at ./spec/models/product_spec.rb:263 (FAILED - 2045)
      with add-ons
        adds $50 for multiple_state_access (FAILED - 2046)
        adds $50 for donation_redirect (FAILED - 2047)
        adds $50 for custom_recipients (FAILED - 2048)
        adds $100 for custom_recipients and multiple states (FAILED - 2049)
        doesn't add $20 for receiving replies (FAILED - 2050)
        adds $50 for custom_widget (FAILED - 2051)
    movement and pro
      example at ./spec/models/product_spec.rb:394 (FAILED - 2052)
      adds $50 for custom_widget for movement (FAILED - 2053)
    standard
      price yearly
        example at ./spec/models/product_spec.rb:434 (FAILED - 2054)
        multiple_state_access add-on
          adds $1200 (FAILED - 2055)
        custom_recipients add-on with > 3 CRs
          adds $300 (FAILED - 2056)
        custom_widget add-on
          adds $1200 (FAILED - 2057)

PromotedMessage
  returns skip_second_page? (FAILED - 2058)
  associations
    should have many action_center_page_promoted_messages
    should have many action_center_pages through action_center_page_promoted_messages
  validations
    isn't valid when the body triggers the profanity filter (FAILED - 2059)
    isn't valid when the subject triggers the profanity filter (FAILED - 2060)
    isn't valid when the bodycachd triggers the profanity filter (FAILED - 2061)
    isn't valid when the bodycachd triggers the profanity filter (FAILED - 2062)
    isn't valid when there is a URL in bodycachd (FAILED - 2063)
    isn't valid when there is  URL in the subject (FAILED - 2064)
    is invalid without a domain extension in the donation_url (FAILED - 2065)
    is valid with extensions in the donation_url (FAILED - 2066)
    is valid with http/https/none preceding the donation_url (FAILED - 2067)
    is valid with domains preceding the donation_url (FAILED - 2068)
    is valid with params ending the donation_url (FAILED - 2069)
    is valid with subfolders ending the donation_url (FAILED - 2070)
    is invalid without email_action_flg or social_action_flg or phone_action_flg (FAILED - 2071)
    is invalid if email_action_flg off and disable_email_verifications is off (FAILED - 2072)
    is invalid if video_action_flg true but promoter doesnt have video_messaging_flg (FAILED - 2073)
    is valid if video_action_flg true and promoter video_messaging_flg true (FAILED - 2074)
    subject and bodycachd presence/uniqueness
      on its own
        isn't valid when there isn't a subject and email_action_flg == true on update (FAILED - 2075)
        is valid when there isn't a subject and email_action_flg == false on update (FAILED - 2076)
        is valid when there are two promoted_messages with nil subjects or empty string subjects and email_action_flg == false (FAILED - 2077)
        isn't valid when there isn't a bodycachd and email_action_flg == true on update (FAILED - 2078)
        is valid when there isn't a bodycachd and email_action_flg == false on update (FAILED - 2079)
      for the same promoter
        disallows duplicate subjects (FAILED - 2080)
        allows duplicates subjects if they are nil (FAILED - 2081)
      with no promoters
        disallows duplicate subjects (FAILED - 2082)
      between different promoters
        allows duplicate names (FAILED - 2083)
    subject/bodycachd/internal_campaign_name length
      isn't valid when the subject exceeds 255 characters (FAILED - 2084)
      isn't valid when the subject is less than 2 characters (FAILED - 2085)
      isn't valid when the internal_campaign_name exceeds 255 characters (FAILED - 2086)
      isn't valid when the internal_campaign_name is less than 2 characters (FAILED - 2087)
      isn't valid when the bodycachd exceeds 10,000 characters (FAILED - 2088)
      isn't valid when the bodycachd is less than 5 characters (FAILED - 2089)
    when multi_content=true
      behaves like a content filter for
        filters obscenity (FAILED - 2090)
        filters tags (FAILED - 2091)
        filters urls (FAILED - 2092)
      behaves like a content filter for
        filters obscenity (FAILED - 2093)
        filters tags (FAILED - 2094)
        filters urls (FAILED - 2095)
    scalable widgets
      doesn't allow width over 800px (FAILED - 2096)
      doesn't allow width under 300px (FAILED - 2097)
      allows width between 300px-800px (FAILED - 2098)
      allows nil width (FAILED - 2099)
    presence for multi_content
      with multi_content true
        without bodycachd_two
          is invalid (FAILED - 2100)
          the validation error message
            uses the field name 'Email Body Two' (FAILED - 2101)
        without subject_two
          is invalid without subject_two (FAILED - 2102)
          the validation error message
            uses the field name 'Email Subject Two' (FAILED - 2103)
    .survey_only_columns
      if we have a SelectedRecipient
        if SelectedRecipient.recipients_code = 'SURVEY'
          the PromotedMessage
            is valid with require_address=false (FAILED - 2104)
            is valid with require_zip_only=true (FAILED - 2105)
        if the SelectedRecipient isn't 'SURVEY'
          the PromotedMessage
            is invalid with require_address=false (FAILED - 2106)
            is invalid with require_zip_only=true (FAILED - 2107)
  after hooks
    runs set_country before creation (FAILED - 2108)
    runs set_required_fields before creation (FAILED - 2109)
    disable_email_verifications_last_switched
      a message created last week
        doesn't have a recent disable_email_verifications_last_switched (FAILED - 2110)
        if disable_email_verifications changes
          updates disable_email_verifications_last_switched (FAILED - 2111)
    set_default_content_names
      sets content_one_name and content_two_name if multi_content and they dont exist (FAILED - 2112)
      does not set content_one_name or content_two_name if multi_content and those values exist (FAILED - 2113)
      sets subject_two and bodycachd_two if multi_content and they dont exist (FAILED - 2114)
      does not set subject_two or bodycachd_two if multi_content and they do exist (FAILED - 2115)
      does not set content names if multi_content false (FAILED - 2116)
    set_cwc_id
      with a new PromotedMessage sets the cwc_campaign_id to the SHA2 of its id (FAILED - 2117)
      with an incorrect value sets the cwc_campaign_id to the SHA2 of its id (FAILED - 2118)
    disable_opt_in
      allow_opt_out returns true for uk (FAILED - 2119)
      allow_opt_out returns false for non uk (FAILED - 2120)
  methods
    returns title_for_collection (FAILED - 2121)
    duplicate
      returns processed? as true on successful duplication with duplicate selected_recipient and alternate_messages (FAILED - 2122)
      returns processed? as false and error messages on failed duplication (FAILED - 2123)
      duplicates messages without subjects (FAILED - 2124)
      toggles phone_required to true in duplicate when original has US federal targets (FAILED - 2125)
      toggles phone_required remains false in duplicate when original has no US federal targets (FAILED - 2126)
    get_act_url_hash
      with :id => true (default)
        example at ./spec/models/promoted_message_spec.rb:623 (FAILED - 2127)
      with :id => false
        example at ./spec/models/promoted_message_spec.rb:634 (FAILED - 2128)
      with :promoter => true
        example at ./spec/models/promoted_message_spec.rb:645 (FAILED - 2129)
    search_subject
      puts hash (FAILED - 2130)
    alternates_for_content
      returns alternates with content_number of nil, 0, or 1 when 1 is passed (FAILED - 2131)
      returns alternates with an equivalent content_number for any other value (FAILED - 2132)
    retire
      should retire a promoted message (FAILED - 2133)
    disable
      should retire a promoted message and set the disabled column (FAILED - 2134)
  state_sends
    counts sends from indvidual states (FAILED - 2135)
  show_recipient_for_message
    true if the recipient country is USA (FAILED - 2136)
    true if cicero code is present (FAILED - 2137)
    true if it is a custom recipient (FAILED - 2138)
    true if it is a committee (FAILED - 2139)
    false if no cicero code (FAILED - 2140)
  #default_optin_message
    returns the default optin message (FAILED - 2141)
  #action_progress_text
    returns the text to be shown on the impact page (FAILED - 2142)
  #action_progress_completion
    should return the completion number for the progress bar (FAILED - 2143)
  #has_us_federal_targets?
    should return true for US federal recipient (FAILED - 2144)
    should return true for US federal committee (FAILED - 2145)
    should return true for US federal group (FAILED - 2146)
    should return false for US state recipient (FAILED - 2147)
    should return false for US state committee (FAILED - 2148)
    should return false for US state group (FAILED - 2149)
    should return false for custom recipient (FAILED - 2150)
    should return false for non-US targets (FAILED - 2151)

PromoterUser
  associations
    should have many advocate_for_promoters
    should have many advocate_profiles through advocate_for_promoters
    should have many conversions through promoted_messages
    should have many opt_ins
    should belong to agency_state class_name => UsStates
    should belong to agency class_name => PromoterUser
    should have many external_connections
  .campaign_monitor_client_id
    if it changes
      strips out quotes (FAILED - 2152)
  .checks_up_to_date?
    active check returns true (FAILED - 2153)
    inactive check returns false (FAILED - 2154)
  .dashboard_messages
    before cutoff_date message activity is not replaced (FAILED - 2155)
    after cutoff_date message activity is replaced by ES data (FAILED - 2156)
  scopes
    should return correct promoters for_agency (FAILED - 2157)
    should return correct active promoters (FAILED - 2158)
  after hooks
    should update_active_status (FAILED - 2159)
    should set_related_promoters_active_status for sub-accounts and proxied users (FAILED - 2160)
    should update_sub_accounts_active_statuses if agency_flg changed (FAILED - 2161)
  methods
    agency?
      for agency promoter
        should return true (FAILED - 2162)
      for non agency promoter
        should return false (FAILED - 2163)
    office?
      for office promoter
        should return true (FAILED - 2164)
      for non office promoter
        should return false (FAILED - 2165)
    is_proxy_for?
      for a non proxy user
        should return false (FAILED - 2166)
      for a proxy user
        whose proxied id equals the passed id
          should return true (FAILED - 2167)
        whose proxied id is the agency for the office owning the passed id
          should return true (FAILED - 2168)
    is_proxy?
      for proxy user promoter
        should return true (FAILED - 2169)
      for non proxy user promoter
        should return false (FAILED - 2170)
    promoter_user_type
      for agency promoter
        should return Agency (FAILED - 2171)
      for office promoter
        should return Office (FAILED - 2172)
      for proxy user promoter
        should return Proxy (FAILED - 2173)
      for a standard promoter
        should return Standard (FAILED - 2174)
    sends_since
      returns count of rubberstamped and permitted conversions for all time by default (FAILED - 2175)
      returns rubberstamped and permitted conversions with a time param (FAILED - 2176)
    #action_center
      returns own action_center if promoter is not an office (sub_account) (FAILED - 2177)
      returns its agency's action_center if promoter is an office (sub_account) (FAILED - 2178)
    .get_combined_query
      with mixed Account-based and Profile-based Opt-ins on the same message
        exports them all (FAILED - 2179)
      with Account-based and Profile-based Opt-ins on the same Profile
        exports them all (FAILED - 2180)
      with duplicate Account-based and Profile-based OptIns
        doesn't export duplicate signatures (FAILED - 2181)
      with mixed signatures
        on opt-out signatures
          sets opt_in=FALSE (FAILED - 2182)
          sets email='Opted out' (FAILED - 2183)
          hides street address (FAILED - 2184)
          hides phone (FAILED - 2185)
          hides first_name (FAILED - 2186)
          hides last_name (FAILED - 2187)
        on opt-in signatures
          sets opt_in=TRUE (FAILED - 2188)
          includes email (FAILED - 2189)
          shows street address (FAILED - 2190)
          shows phone (FAILED - 2191)
          shows first_name (FAILED - 2192)
          shows last_name (FAILED - 2193)
    Exports (CSV, NB, Neon)
      batched_sender_data cutoff_date_time and end_cutoff_date_time
        includes in batched_sender_data a signature a second after cutoff_date_time but not one on end_cutoff_date_time (FAILED - 2194)
      with mixed Account-based and Profile-based Opt-ins on the same message
        exports them all (FAILED - 2195)
      with Account-based and Profile-based Opt-ins on the same Profile
        exports them all (FAILED - 2196)
      with duplicate Account-based and Profile-based OptIns
        doesn't export duplicates (FAILED - 2197)
      with :no_signature_in_nodb => true
        excludes conversions already in the nodb (FAILED - 2198)
      with a Profile-based OptIn
        an opt-out signature
          on a message from the same Promoter
            exports to Neon and NationBuilder (FAILED - 2199)
          on a message from a different Promoter
            is opt-out (FAILED - 2200)
            doesn't export to the second Promoter's Neon and NationBuilder (FAILED - 2201)
        an opt-out sig from a different Profile
          stays opt-out (FAILED - 2202)
          doesn't sync to NB or Neon (FAILED - 2203)
    #batched_sender_data block sizes
      with block size 2
        shows 5 signatures (FAILED - 2204)
      with block size 4
        shows 5 signatures (FAILED - 2205)
    #nation_builder_export
      pre-cutoff
        returns nothing (FAILED - 2206)
      post-cutoff
        returns fields including the sender_profile ID (FAILED - 2207)
      not opt-in
        excludes (FAILED - 2208)
      quorum_gated = true
        excludes (FAILED - 2209)
      when our message has a internal_campaign_name / Internal message name
        subject
          example at ./spec/models/promoter_user_spec.rb:698 (FAILED - 2210)
    #widget_background
      with valid hex code
        example at ./spec/models/promoter_user_spec.rb:711 (FAILED - 2211)
      with valid rgb code
        example at ./spec/models/promoter_user_spec.rb:722 (FAILED - 2212)
      with invalid hex code
        includes invalid an message (FAILED - 2213)
    #widget_button
      with valid hex code
        example at ./spec/models/promoter_user_spec.rb:748 (FAILED - 2214)
      with valid rgb code
        example at ./spec/models/promoter_user_spec.rb:759 (FAILED - 2215)
      with invalid hex code
        includes invalid an message (FAILED - 2216)
    testing possible urls for base
      is not one of the two possible options (FAILED - 2217)
      works with ez texting (FAILED - 2218)
      works with group texting (FAILED - 2219)

RecipientBio
  is invalid without a recipient
  is valid with a recipient (FAILED - 2220)
  .facebook_url
    behaves like a social url
      when the url field contains the domain
        doesn't add the domain
        matches the col
      when the url field doesn't contain the domain
        adds the domain
        matches the col
      when the url field is empty
        returns nil
  .twitter_url
    behaves like a social url
      when the url field contains the domain
        doesn't add the domain
        matches the col
      when the url field doesn't contain the domain
        adds the domain
        matches the col
      when the url field is empty
        returns nil
  .youtube_url
    behaves like a social url
      when the url field contains the domain
        doesn't add the domain
        matches the col
      when the url field doesn't contain the domain
        adds the domain
        matches the col
      when the url field is empty
        returns nil
  .electdate_trimmed
    with the original Cicero format
      should eq "2007-07-01"
    with a space-delimited format
      should eq "2007 07 01"
    with a slash-delimited format
      should eq "2007/07/01"
    with a written format
      should eq "July 1, 2007"
    with a nil column
      should equal nil

RecipientRelation
  after hooks
    creates a HistoricalRecipientRelation on create and destroys it on destroy (FAILED - 2221)

Recipient
  Associations
    should have many external_connections
  methods
    #local_for
      for CouncilMembers
        with shapefile council Districts for New York City
          a Sender from 'NYC'
            from district 29
              should be local (FAILED - 2222)
            from another district
              should not be local (FAILED - 2223)
          a Sender from 'New York City'
            from district 29
              should be local (FAILED - 2224)
            from another district
              should not be local (FAILED - 2225)
          a Sender from 'Bronx'
            should be local
              should be local (FAILED - 2226)
        For in-district DC sender with city-wide CouncilMembers
          an in-state sender with a matching city string
            should be local (FAILED - 2227)
          an in-state sender without a matching city string
            should not be local (FAILED - 2228)
          an out-of-state sender
            should not be local (FAILED - 2229)
      for Senators
        for a profile within the 61st district
          for State-Senator Dibble
            should return State-Senator Dibble (FAILED - 2230)
        for a profile outside the 61st district
          for State-Senator Dibble
            should not return State-Senator Dibble (FAILED - 2231)
      for office_ca_state_assembly
        for a profile within the ca_state_assemblywoman's district
          should return ca_state_assemblywoman (FAILED - 2232)
        for a profile outside the ca_state_assemblywoman's district
          should not return ca_state_assemblywoman (FAILED - 2233)
      AU State Parliaments
        New South Wales NSW
          Upper House
            an address in NSW
              is local (FAILED - 2234)
          Lower House
            an address in NSW
              for a member in the same district
                is local (FAILED - 2235)
              for a member out of district
                is not local (FAILED - 2236)
        South Australia SA
          Upper House
            an address in SA
              is local (FAILED - 2237)
          Lower House
            for a member in the same district
              is local (FAILED - 2238)
            for a member out of district
              is not local (FAILED - 2239)
        Tasmania Tas
          Upper House
            for a member in district
              is local (FAILED - 2240)
            for a member out of district
              is not local (FAILED - 2241)
          Lower House
            for two members in the same district
              is local (FAILED - 2242)
            for a member out of district
              is not local (FAILED - 2243)
        Australian Capitol Territory ACT
          Unicameral House (Assembly)
            for two members in the same district
              is local (FAILED - 2244)
            for a member out of district
              is not local (FAILED - 2245)
      UK Parliament
        Aberdeen Scotland
          Lower House
            an address in Scotland
              for a member in the same district
                is local (FAILED - 2246)
              for a UK member out of district
                is not local (FAILED - 2247)
      CustomRecipients
        for the same promoter
          when we have a L from the same city
            is local (FAILED - 2248)
          when we have a L from another city
            is not local (FAILED - 2249)
          When a sender profiles city field matches more than one city
            Only attach local recipients based on the sender profiles city and state (FAILED - 2250)
            What happens if the sender profile doesn't have a state -- we skip the method. (FAILED - 2251)
          when we have a S from the same state
            is local (FAILED - 2252)
          when we have a S from another state
            is not local (FAILED - 2253)
          when we have an N
            is local (FAILED - 2254)
        for a different promoter
          when we have a L from the same city
            is not local (FAILED - 2255)
          when we have a L from another city
            is not local (FAILED - 2256)
          when we have a S from the same state
            is not local (FAILED - 2257)
          when we have a S from another state
            is not local (FAILED - 2258)
          when we have an N
            is not local (FAILED - 2259)
      CustomRecipients in UK
        for the same promoter in UK
          when we have a S from the same state
            is local (FAILED - 2260)
          when we have a S from another state
            is not local (FAILED - 2261)
        for a different promoter
          when we have a S from the same state
            is not local (FAILED - 2262)
          when we have a S from another state
            is not local (FAILED - 2263)
      Mayors
        a sender from the same city/state
          should be local (FAILED - 2264)
        a sender from another city/state
          should not be local (FAILED - 2265)
      #get_photo_url
        with a full_photo_url
          should use the full_photo_url (FAILED - 2266)
        with a photo path
          should use photo path to create s3 url (FAILED - 2267)
          and a bioguide id
            should prioritize photo path (FAILED - 2268)
        with bioguide id
          should use bioguide id to create unitedstatesio images url path (FAILED - 2269)
        with no photo
          should use default no-rep-pic (FAILED - 2270)
      #to_s
        should render value of name attribute (FAILED - 2271)
    #full_salutation
      with a custom_salutation field
        example at ./spec/models/recipient_spec.rb:843 (FAILED - 2272)
      with a Senator model_type
        example at ./spec/models/recipient_spec.rb:851 (FAILED - 2273)
      with a Congressman model_type
        example at ./spec/models/recipient_spec.rb:857 (FAILED - 2274)
      with office OFFICE_US_SENATE
        example at ./spec/models/recipient_spec.rb:863 (FAILED - 2275)
      with office OFFICE_US_HOUSE
        example at ./spec/models/recipient_spec.rb:869 (FAILED - 2276)
      with office OFFICE_STATE_SENATE
        example at ./spec/models/recipient_spec.rb:876 (FAILED - 2277)
      with office OFFICE_STATE_HOUSE
        example at ./spec/models/recipient_spec.rb:882 (FAILED - 2278)
      with office OFFICE_STATE_ASSEMBLY
        example at ./spec/models/recipient_spec.rb:890 (FAILED - 2279)
      with office OFFICE_GOVERNOR
        example at ./spec/models/recipient_spec.rb:899 (FAILED - 2280)
      with office OFFICE_LIEUTENANT_GOVERNOR
        example at ./spec/models/recipient_spec.rb:907 (FAILED - 2281)
      with office Senate of Canada
        example at ./spec/models/recipient_spec.rb:916 (FAILED - 2282)
      with office CA House of Commons
        example at ./spec/models/recipient_spec.rb:924 (FAILED - 2283)
      with office Australian Senate
        example at ./spec/models/recipient_spec.rb:932 (FAILED - 2284)
      with office Australian House
        example at ./spec/models/recipient_spec.rb:940 (FAILED - 2285)
    returning search_by_representative
      returns reps correctly for senate (FAILED - 2286)
      returns reps correctly for house (FAILED - 2287)
    returning search_by_uk_representative
      returns uk representative correctly by first_name (FAILED - 2288)
      returns uk representative correctly by last_name (FAILED - 2289)
      returns uk representative correctly by name (FAILED - 2290)
      returns empty array for not found representative (FAILED - 2291)
    find_with_facebooks
      returns one record for each address, with unique facebooks urls (FAILED - 2292)
    find_with_emails_or_web_forms
      returns only the recipient who has an email (FAILED - 2293)
      returns a recipient who only has a webform address (FAILED - 2294)
      returns one result for each unique email or web address a recipient has (FAILED - 2295)
    returning recipients by state
      return_state_reps_by_chamber (FAILED - 2296)
      returns search_by_state_representatives_in_office (FAILED - 2297)
    def self.expand_recipients
      returns a single person if only one person passed in (FAILED - 2298)
      returns expanded recipients for a Committee and it does not return subcommittee objects (FAILED - 2299)
      returns multi_content recipients if recipient_ids_content_one_array or recipient_ids_content_two_array passed in (FAILED - 2300)
    committee_members
      with no params passed in (no include_territories)
        returns committee_members as an array of recipient objects without CommitteeTerritoryRecipient objects (FAILED - 2301)
      with include_territories turned on
        returns committee_members with CommitteeTerritoryRecipient objects (FAILED - 2302)
    custom_recipient?
      for a non custom recipient record
        example at ./spec/models/recipient_spec.rb:1172 (FAILED - 2303)
      for a custom recipient record
        example at ./spec/models/recipient_spec.rb:1178 (FAILED - 2304)
  validations
    is invalid when the knowwho_comid has been taken (FAILED - 2305)
    Australians must have a cicero_code if active
      doesn't validate if active_flg == false || nil (FAILED - 2306)
      validates if active_flg == true (FAILED - 2307)
    must have its state match the country
      validates australia (FAILED - 2308)
      validates canada (FAILED - 2309)
    the country attribute must be capitalized
      works for australia (FAILED - 2310)
      works for canada (FAILED - 2311)
      leaves nil as nil (USA) (FAILED - 2312)
  After hooks
    should run set_inactive_at when a recipient is set inactive (FAILED - 2313)
  scopes
    returns belonging_to_promoted_message (FAILED - 2314)
    returns belonging_to_committee and belonging_to_committee_during_time (FAILED - 2315)
    returns correct recipients for humans_active_during_time_period and humans_for_promoter and active_during_time_period (FAILED - 2316)
    returns by_state_and_office (FAILED - 2317)
    returns search_by_name (FAILED - 2318)
  method for returning recipients by office
    should return correct recipients for search_by_state_representatives_in_office (FAILED - 2319)

RedeliveryTask
  associations
    example at ./spec/models/redelivery_task_spec.rb:6 (FAILED - 2320)

Responsibility
  validations
    object
      should be valid
    value
      which is blank
        should be invalid
      which is longer than 255 characters
        should be invalid

SelectedRecipientGroup
  validations
    should require selected_recipient to be set
    should require group_code to be set
    should require content_number to be set
  content_number validations
    is invalid when == 3 (FAILED - 2321)
    is valid when == 2 (FAILED - 2322)
  group_code custom validations
    returns the relevant content_name (FAILED - 2323)
    doesn't fail validation when the group is on another selected_recipient (FAILED - 2324)
  #uniqueness_of_group_code
    multi-content
      with group=AS state=MA on content_one
        group=AS state=MA on content_one
          is NOT valid (FAILED - 2325)
        group=AS state=MA on content_two
          is NOT valid (FAILED - 2326)
        group=SH state=MA on content_one
          is valid (FAILED - 2327)
        group=AS state=CA on content_two
          is valid (FAILED - 2328)
        group=SH state=MA on content_two
          is valid (FAILED - 2329)
  #content_number_from_string
    returns 1 for 'content_one'
    returns 2 for 'content_two'
    returns 0 when multi_content is false
    returns nil for anything else

SelectedRecipient
  example at ./spec/models/selected_recipient_spec.rb:14 (FAILED - 2330)
  #group_ids_only
    with a selected_recipient_group
      returns the senators (FAILED - 2331)
    with multi_content groups
      returns only content_one group members when options[:content_number] == 1 (FAILED - 2332)
      returns only content_two group members when options[:content_number] == 2 (FAILED - 2333)
  .flag_recipient and .unflag_recipient
    when we flag 3 recipients
      always_send_recipients_code
        doesn't contain blank elements or delimiters (FAILED - 2334)
    when we flag (limit - 1) recipients
      then unflag and flag again
        always_send_recipients_code
          doesn't contain blank elements or delimiters (FAILED - 2335)
  .remove_recipient
    with message_params[:recipient_code]
      without multi_content
        removes recipient from recipients_code (FAILED - 2336)
      with multi_content
        with content_one
          removes recipient from recipients_code and recipients_code_content_one (FAILED - 2337)
        with content_two
          removes recipient from recipients_code and recipients_code_content_two (FAILED - 2338)
    with message_params[:recipient_code]
      when selected_recipient SURVEY
        does a full_clear (FAILED - 2339)
  .multi_content_clear_one_side
    for content_one
      clears recipients_code_content_one and updates recipients_code, and always_send_recipients_code (FAILED - 2340)
      clears content_one groups (FAILED - 2341)
    for content_two
      clears recipients_code_content_two and updates recipients_code, and always_send_recipients_code (FAILED - 2342)
      clears content_two groups (FAILED - 2343)
  .targets_present?
    with a selected_recipient_group
      returns true (FAILED - 2344)
    without multi_content
      with recipients_code present
        returns true (FAILED - 2345)
      with recipients_code blank
        returns false (FAILED - 2346)
      with SURVEY mode
        returns true (FAILED - 2347)
    with multi_content
      for content_one
        with recipients_code_content_one present
          returns true (FAILED - 2348)
        with recipients_code_content_one blank
          returns false (FAILED - 2349)
      for content_two
        with recipients_code_content_two present
          returns true (FAILED - 2350)
        with recipients_code_content_two blank
          returns false (FAILED - 2351)
  .set_to_survey!
    sets recipients_code to SURVEY and resets all recipients columns (FAILED - 2352)
    with Groups
      behaves like a Group clearer
        destroys attached groups (FAILED - 2353)
        with unattached groups
          doesn't destroy unattached groups (FAILED - 2354)
  .full_clear
    runs a full_clear and resets all recipients columns (FAILED - 2355)
    with Groups
      behaves like a Group clearer
        destroys attached groups (FAILED - 2356)
        with unattached groups
          doesn't destroy unattached groups (FAILED - 2357)
  .set_require_address
    for recipients_code=SURVEY
      if our PromotedMessage has require_address=false
        alllows require_address=false (FAILED - 2358)
        if we change from SURVEY mode to use recipients
          resets to require_address=true (FAILED - 2359)
      if our PromotedMessage has require_zip_only=true
        alllows require_zip_only=true (FAILED - 2360)
        if we change from SURVEY mode to use recipients
          resets to require_zip_only=false (FAILED - 2361)
  #verify_multicontent_recipient_code
    when the data is normal
      we should not see any change
        and recipients_code should be a uniq aggregate of content_one and content_two (FAILED - 2362)
    when the data is malformed
      we should detect that it needs changed
        upon save the recipients_codes should normalize (FAILED - 2363)
  .expanded_recipients_code_ids
    multi-content
      with mixed Committees and recipients
        :expanded_recipients
          includes expanded recipient ids (FAILED - 2364)
          excludes committee ids (FAILED - 2365)
        :expanded_recipients_content_one
          includes expanded recipient ids from content_one (FAILED - 2366)
          excludes expanded recipient ids NOT from content_one (FAILED - 2367)
        :expanded_recipients_content_two
          includes expanded recipient ids from content_two (FAILED - 2368)
          excludes expanded recipient ids NOT from content_two (FAILED - 2369)

SenderProfile
  associations
    should belong to account
    should belong to state
    should belong to advocate_profile
    should have many archive_messages
    should have many service_deliveries
    should have many conversions
  validations
    should have a unique identifier (FAILED - 2370)
    lengths
      should limit the length of prefix to 50 characters
      should limit the length of first_name to 25 character
      should limit the length of last_name to 25 character
      should limit the length of line1 to 200 character
      should limit the length of city to 200 character
  after hooks
    downcases email on save (FAILED - 2371)
  class methods
    district_details (FAILED - 2372)
    phone_details (FAILED - 2373)
    draft_kings_csv
      returns the correct attributes (FAILED - 2374)
  methods
    geoaddress
      gives correct geoaddress for an American address (FAILED - 2375)
      gives correct geoaddress for a Canadian address (FAILED - 2376)
      gives correct geoaddress for an Australian address (FAILED - 2377)
      gives correct geoaddress for an British address (FAILED - 2378)
    no_advocate_district_details
      gives district details for America (FAILED - 2379)
      gives district details for Canada (FAILED - 2380)
      gives district details for Australia (FAILED - 2381)
      gives district details for United Kingdom (FAILED - 2382)
    local_recipients_us_congress_only
      returns a local US Federal Senator (FAILED - 2383)
      does not return an out of district US Federal Senator (FAILED - 2384)
      does not return a local State Senator (FAILED - 2385)
    .update_signature
      with NoDB Signatures enabled
        with an opt-in NoDB signature
          updating signature-related fields
            updates the signature-related fields (FAILED - 2386)
            updates the signature (FAILED - 2387)
          updating non-signature fields
            updates the non-signature fields (FAILED - 2388)
            doesn't update the signature (FAILED - 2389)
        with an opt-out NoDB signature
          updating signature-related but sensitive fields
            updates the signature-related fields (FAILED - 2390)
            hides sensitive fields on the signature (FAILED - 2391)
          updating other fields
            updates the non-signature fields (FAILED - 2392)
            doesn't update the signature (FAILED - 2393)

ServiceDelivery
  Associations
    should belong to service_send
    should belong to promoted_message
    should belong to conversion
    should belong to sender_profile
    should belong to recipient
    should belong to recipient_address
  Attributes
    :nation_builder_synced should default to false

Signature
  self.new_from_csv_row
    columns matching Conversions and Signatures
      maps them to Signature fields
    created_at
      with a created_at formatted
        2020-04-10
          should match "2020-04-10"
        4/10/2020
          should match "2020-04-10"
        Apr 10 2020
          should match "2020-04-10"
    extra columns
      become custom_fields
  new_from_batched_sender_data
    if email == 'Opted out'
      blanks sensitive fields (FAILED - 2394)
    with .permitted == t
      sets .permitted to 'yes' (FAILED - 2395)
    with .permitted != t
      sets .permitted to nil (FAILED - 2396)
    with service_send address data
      overwrites the address data (FAILED - 2397)
    with a blank email and a non-blank account_email
      overwrites the email (FAILED - 2398)
    with a state_id
      sets .state to the state name (FAILED - 2399)
    for untransformed columns
      carries over the columns (FAILED - 2400)
  new_from_conversion_and_sender
    opt in
      carries over SenderProfile fields (FAILED - 2401)
    out out
      blanks sensitive fields (FAILED - 2402)

SliderPanel
  associations
    should belong to action_center
  validations
    should require title to be set
    should require link to be set
    should require action_center_id to be set
    should require image to be set
    validates image

Staffer
  validations
    object
      should be valid (FAILED - 2403)
    recipient_office
      should be present

StateHouseDistrict
  associations
    should have many advocate_profiles

StateSenateDistrict
  associations
    should have many advocate_profiles

Subscription
  example at ./spec/models/subscription_spec.rb:14 (FAILED - 2404)
  example at ./spec/models/subscription_spec.rb:15 (FAILED - 2405)
  is associatied with the correct product (FAILED - 2406)
  accepts monthly as a billing cycle (FAILED - 2407)
  accepts six_month as a billing cycle (FAILED - 2408)
  accepts yearly as a billing cycle (FAILED - 2409)
  accepts blank as a billing cycle (FAILED - 2410)
  doesn't accept value outside of inclusion for billing cycle (FAILED - 2411)
  on a Stripe::CardError
    example at ./spec/models/subscription_spec.rb:52 (FAILED - 2412)
  after hooks
    should update_promoter_active_status after save  on promoter, all sub accounts, and all proxied promoters (FAILED - 2413)
    should inactivate_promoter on destruction and all sub accounts (FAILED - 2414)

SynchronizeCall
  .admin
    returns admin calls (FAILED - 2415)
    doesn't return promoter calls (FAILED - 2416)
  BatchSenderSynchronizeCall.all
    returns BatchSenderSynchronizeCalls (FAILED - 2417)
    doesn't return NationBuilderSynchronizeCalls (FAILED - 2418)
    returns BatchSenderSynchronizeCalls (FAILED - 2419)
  .fail
    changes our status to failed (FAILED - 2420)
  .succeed
    changes our status to success (FAILED - 2421)
  .write_to_log
    adds to our log (FAILED - 2422)
  SynchronizeCall.standardize_status_for(string)
    failure strings
      map to SynchronizeCall::FAILED_STATUS
    success strings
      map to SynchronizeCall::SUCCESSFUL_STATUS
    other strings
      map to SynchronizeCall::ONGOING_STATUS
  .get_index_list_since(3.days.ago)
    sorts by class (FAILED - 2423)
    sorts then by admins (FAILED - 2424)
    sorts then by time (FAILED - 2425)
  .process_results
    with failure strings
      makes a failed SynchronizeCall (FAILED - 2426)
    with success strings
      makes a successful SynchronizeCall (FAILED - 2427)
  SynchronizeCall.create
    with failure strings
      makes a failed SynchronizeCall (FAILED - 2428)
    with success strings
      makes a successful SynchronizeCall (FAILED - 2429)
  .if_available
    if we don't fail during the block
      sets sync status to SUCCESSFUL_STATUS (FAILED - 2430)
    if we fail during the block
      sets sync status to FAILED_STATUS (FAILED - 2431)
    behaves like an auto-expiring SynchronizeCall after
      with an ongoing sync
        older than AUTO_EXPIRE_IN_DAYS days
          For all SynchronizeCalls but HourlyAggTablesUpdaterSynchronizeCall
            fails the old sync (FAILED - 2432)
            runs (FAILED - 2433)
          for HourlyAggTablesUpdaterSynchronizeCall
            sends etl_hourly_task_missed email to dev-group if existing sync is ongoing (FAILED - 2434)
            fails the old sync (FAILED - 2435)
            runs (FAILED - 2436)
        younger than AUTO_EXPIRE_IN_DAYS days
          For all SynchronizeCalls but HourlyAggTablesUpdaterSynchronizeCall
            doesn't run (FAILED - 2437)
          for HourlyAggTablesUpdaterSynchronizeCall
            sends etl_hourly_task_missed email to dev-group if existing sync is ongoing (FAILED - 2438)
            doesn't run (FAILED - 2439)
    with :auto_expire_in_days => 2
      behaves like an auto-expiring SynchronizeCall after
        with an ongoing sync
          older than AUTO_EXPIRE_IN_DAYS days
            For all SynchronizeCalls but HourlyAggTablesUpdaterSynchronizeCall
              fails the old sync (FAILED - 2440)
              runs (FAILED - 2441)
            for HourlyAggTablesUpdaterSynchronizeCall
              sends etl_hourly_task_missed email to dev-group if existing sync is ongoing (FAILED - 2442)
              fails the old sync (FAILED - 2443)
              runs (FAILED - 2444)
          younger than AUTO_EXPIRE_IN_DAYS days
            For all SynchronizeCalls but HourlyAggTablesUpdaterSynchronizeCall
              doesn't run (FAILED - 2445)
            for HourlyAggTablesUpdaterSynchronizeCall
              sends etl_hourly_task_missed email to dev-group if existing sync is ongoing (FAILED - 2446)
              doesn't run (FAILED - 2447)
    without an ongoing sync
      when an error is not raised
        creates a new sync (FAILED - 2448)
        runs (FAILED - 2449)
      when an error is raised
        and the sync class is not HourlyAggTablesUpdaterSynchronizeCall
          should mark sync as failed (FAILED - 2450)
        and the sync class is HourlyAggTablesUpdaterSynchronizeCall
          should send etl error email (FAILED - 2451)
    with an ongoing sync from a different class
      creates a new sync (FAILED - 2452)
      runs (FAILED - 2453)
    if_available({:promoter_user_id => 10})
      with an ongoing sync for a different promoter id
        creates a new sync (FAILED - 2454)
        runs (FAILED - 2455)
    .if_available_for 10
      with an ongoing sync for a different promoter id
        creates a new sync (FAILED - 2456)
        runs (FAILED - 2457)
      with an ongoing sync for the same promoter id
        doesn't create a new sync (FAILED - 2458)
        doesn't run (FAILED - 2459)
      with an ongoing sync from another class
        creates a new sync (FAILED - 2460)
        runs (FAILED - 2461)
    .if_available_for_admin
      with an ongoing sync for a promoter id
        creates a new sync (FAILED - 2462)
        runs (FAILED - 2463)
      with an ongoing sync for the admin
        doesn't create a new sync (FAILED - 2464)
        doesn't run (FAILED - 2465)
      with an ongoing sync from another class
        creates a new sync (FAILED - 2466)
        runs (FAILED - 2467)

Tag
  should return an accurate count of popular tags (FAILED - 2468)
  find_active_us_states
    for active messages
      size
        example at ./spec/models/tag_spec.rb:40 (FAILED - 2469)
      first.tag_name
        example at ./spec/models/tag_spec.rb:42 (FAILED - 2470)
      last.tag_name
        example at ./spec/models/tag_spec.rb:43 (FAILED - 2471)
    for unshared messages
      size
        example at ./spec/models/tag_spec.rb:55 (FAILED - 2472)
    for inactive messages
      size
        example at ./spec/models/tag_spec.rb:67 (FAILED - 2473)

Taggable
  should be able to attach and detach tags (FAILED - 2474)
  doesn't destroy or delete tags when it detaches them (FAILED - 2475)
  allows us to tag() and untag() using objects or ids (FAILED - 2476)

TextMessageGroup {:type=>:model}
  update_group_from_ez_texting
    should update the contacts count (FAILED - 2477)
  validations
    should require ez_texting_id to be set
    should require name to be set
  def convert_contacts_to_csv(contacts)
    should create a csv (FAILED - 2478)
  def get_all_contacts
    should return contacts
    should return all the contacts if there are more than 100
    should return all the contacts for WeedMapsCA

TextMessageKeyword
  validations
    should require ez_texting_id to be set
    should require keyword to be set
    should require join_message to be set
  constant
    MAX_JOIN_MESSAGE_SIZE should equal 150
  remove_default_group
    should succeed (FAILED - 2479)
  default_group_name
    should return name of default group (FAILED - 2480)

TextMessage
  Testing the scopeing
    uses match_array to match a scope (FAILED - 2481)
  Saving a text to a promoter user
    create a text message (FAILED - 2482)
  Check validations
    does it have a message (FAILED - 2483)
    should now work (FAILED - 2484)
    does it have a time to send (FAILED - 2485)
    should now work (FAILED - 2486)
    does it have a delivery status (FAILED - 2487)
    should now work (FAILED - 2488)
  .time_in_est
    with a stored EST time
      doesn't convert (FAILED - 2489)
    with another time
      converts (FAILED - 2490)
    with nil time_to_send
      returns nil
  .sent_or_scheduled
    if status == sent
      returns sent
    if status == scheduled
      if .time_in_est < now
        returns 'sent'
      if .time_in_est > now
        returns 'scheduled'

Throttle
  caps batch_sender_threshold at 50
  get_or_create_latest
    with multiple calls and edits
      doesn't use multiple Throttle records (FAILED - 2491)

TwilioProduct
  handle_all_price_updates
    with existing TwilioBillingPeriods
      updates the product (FAILED - 2492)
      doesn't remove the existing bill outside the period (FAILED - 2493)
      removes the bill inside the period (FAILED - 2494)
      adds a new bill (FAILED - 2495)
  without existing TwilioBillingPeriods
    without start_dates
      day one
        calculates the correct values (FAILED - 2496)
      day two
        calculates the correct values (FAILED - 2497)
      day three
        calculates the correct values (FAILED - 2498)
      day four
        calculates the correct values (FAILED - 2499)
      if we skip several days
        calculates the correct values (FAILED - 2500)
    with start_dates
      day one
        calculates the correct values on day 1 (FAILED - 2501)
      day two
        calculates the correct values on day 2 (FAILED - 2502)
      day three
        calculates the correct values (FAILED - 2503)
      day four
        calculates the correct values (FAILED - 2504)
      if we skip several days
        calculates the correct values (FAILED - 2505)
      if we pass in a non-sequential start day
        calculates the correct values (FAILED - 2506)

UsStates
  associations
    should have many districts
    should have many advocate_profiles
  validations
    should have a name (FAILED - 2507)
    should have an abbreviation (FAILED - 2508)
    should have a unique name (FAILED - 2509)
    should have a unique abbreviation (FAILED - 2510)
  scopes
    should return american_states (FAILED - 2511)
    should return no_puerto_rico (FAILED - 2512)
    should return only_full_states (FAILED - 2513)
    should return australian_states (FAILED - 2514)
    should return canadian_states (FAILED - 2515)
    should return united_kingdom_states (FAILED - 2516)
  methods
    should return_states_by_country

VideoServiceSend
  should have a valid factory (FAILED - 2517)
  without a promoted_message_id is invalid (FAILED - 2518)
  without a video_token
    is invalid (FAILED - 2519)
  with a duplicate video_token
    is invalid (FAILED - 2520)
  #record_deliveries_for
    creates a VideoServiceDelivery (FAILED - 2521)
    updates the VideoServiceSend status to 'SENT' (FAILED - 2522)
  #make_for_conversion
    creates a 'NEW' VideoServiceSend (FAILED - 2523)
    leaves recipients blank (FAILED - 2524)
    records the Ziggeo video token (FAILED - 2525)
    records the promoted_message_id (FAILED - 2526)
    recipients_json column
      sets the recipients_json based on the conversion's recipient_ids_always_send_and_local (FAILED - 2527)
      sets only unique recipient IDs in recipients_json (FAILED - 2528)
      when the conversion has no relevant recipients
        records a blank array in recipients_json (FAILED - 2529)
    video_opt_in
      defaults the video_opt_in to false (FAILED - 2530)
      sets video_opt_in to true if params is 'true' (FAILED - 2531)
  #for_promoter
    doesn't retrieve videos from other promoter_users (FAILED - 2532)
    with one of each service send
      with a NEW filter only shows NEW videos (FAILED - 2533)
      with an ACCEPTED filter shows only ACCEPTED and SENT videos (FAILED - 2534)
      with an REJECTED filter only shows REJECTED videos (FAILED - 2535)
      with NEW and REJECTED filters only shows NEW and REJECTED videos (FAILED - 2536)

Visit
  associations
    should belong to archive_message
    should belong to promoted_message
  validations
    should have a unique today column scoped to promoted_message_id (FAILED - 2537)

Generate EmailBodyPdf
  successfully renders an opted in pdf (FAILED - 2538)
  successfully renders an opted out pdf (FAILED - 2539)

account page
  login
    with uppercase email
      logs in (FAILED - 2540)
    with mixedcase email
      logs in (FAILED - 2541)
    with mixedcase email
      flashes error message (FAILED - 2542)
  navbar
    example at ./spec/requests/account_pages_spec.rb:64 (FAILED - 2543)
    with associated promoted account
      example at ./spec/requests/account_pages_spec.rb:75 (FAILED - 2544)
      allows access to the promoter page (FAILED - 2545)
      allows access to the promoter page (FAILED - 2546)
    without associated account
      example at ./spec/requests/account_pages_spec.rb:92 (FAILED - 2547)
  not logged in
    redirects from password page (FAILED - 2548)

admin page
  example at ./spec/requests/admin_pages_spec.rb:13 (FAILED - 2549)
  creating a promoter_user
    has checkbox for making user an agency (FAILED - 2550)
  product page
    lists correct price (FAILED - 2551)
    lists correct add ons (FAILED - 2552)
    #update_product
      updating add ons
        updates add ons (FAILED - 2553)
        updates the price (FAILED - 2554)
      updating tier
        lists correct add ons (FAILED - 2555)
        updates tier (FAILED - 2556)
        updates the price (FAILED - 2557)

messages page
  message edit
    with no topic
      renders view (FAILED - 2558)
    navbar
      example at ./spec/requests/messages_pages_spec.rb:26 (FAILED - 2559)
      example at ./spec/requests/messages_pages_spec.rb:28 (FAILED - 2560)
    message impact
      lists verified and unverified sigs (FAILED - 2561)

promoter page
  profile page
    promoter name
      example at ./spec/requests/promoter_pages_spec.rb:20 (FAILED - 2562)
      saves promoter name (FAILED - 2563)
  navbar
    example at ./spec/requests/promoter_pages_spec.rb:33 (FAILED - 2564)
    with associated account
      example at ./spec/requests/promoter_pages_spec.rb:43 (FAILED - 2565)
  messege edit page
    setting survey mode
      sets Survey mode as recipients (FAILED - 2566)
      doesn't clear recipients (FAILED - 2567)
      navbar
        example at ./spec/requests/promoter_pages_spec.rb:76 (FAILED - 2568)
    with recipients
      prints recipient's name (FAILED - 2569)
      doesn't clear recipients (FAILED - 2570)
    message settings
      defaults to require address (FAILED - 2571)
      email confirmation redirect
        example at ./spec/requests/promoter_pages_spec.rb:124 (FAILED - 2572)
        with a valid url starting with http
          saves url (FAILED - 2573)
          doesn't show error message (FAILED - 2574)
        with an valid url
          rejects url (FAILED - 2575)
          flashes invalid url message (FAILED - 2576)
        with a valid url not starting with http
          rejects url (FAILED - 2577)
          flashes invalid url message (FAILED - 2578)
      outside of survey mode
        shows a disabled address_required box (FAILED - 2579)
        shows a disabled no_address_info box (FAILED - 2580)
        shows a disabled zip_required box (FAILED - 2581)
      survey mode
        shows the address_required box (FAILED - 2582)
        shows the no_address_info box (FAILED - 2583)
        shows the zip_required box (FAILED - 2584)
        selecting no_address_info
          the widget preview
            doesn't require an address (FAILED - 2585)
        selecting zip_required
          the widget preview
            doesn't require an address (FAILED - 2586)
        setting recipients
          requires address once recipients are added (FAILED - 2587)
        remove recipient mode
          adds require address (FAILED - 2588)
          clears recipients (FAILED - 2589)

promoter user session page
  login
    with valid credentials
      logs in (FAILED - 2590)
    with invalid password
      flashes error message (FAILED - 2591)

account page
  when not logged in
    shows the services page on root
  when not logged in
    links to /pricing from footer (FAILED - 2592)
  when logged in as a promoter
    links to /pricing from footer (FAILED - 2593)

routes for Text Message
  text message overview (FAILED - 2594)
  show text landing page (FAILED - 2595)
  text messages
    text messages index (FAILED - 2596)
    text message new (FAILED - 2597)
  text message keyword
    text message keyword new (FAILED - 2598)
    text message keyword edit (FAILED - 2599)
    text message keyword create (FAILED - 2600)
    text message keyword update (FAILED - 2601)
    text message keyword delete (GET) (FAILED - 2602)
    text message keyword delete (DELETE) (FAILED - 2603)
  text message report
    show text message report (FAILED - 2604)
    show detailed text message report (FAILED - 2605)
    Text create (FAILED - 2606)
  group
    download group csv (FAILED - 2607)
    works (FAILED - 2608)
    works (FAILED - 2609)
    works (FAILED - 2610)
    works (FAILED - 2611)
    works (FAILED - 2612)
  contact
    works (FAILED - 2613)
    works (FAILED - 2614)

AddRecipientToPromotedMessage
  successful calls
    with existing SelectedRecipient
      updates existing recipients_code (FAILED - 2615)
      returns an error when adding an existing recipient (FAILED - 2616)
      doesn't return a error when adding a recipient whose id is a substring of an existing recipient (FAILED - 2617)
      adding groups
        when params contains a preselected_group
          creates a selected_recipient_group (FAILED - 2618)
          sets the selected_recipient_group's us_state_id according to the RecipientCodeHandler's state_id (FAILED - 2619)
          when content_type is passed but multi_content is false
            sets the content_number to something other than 1 or 2 (FAILED - 2620)
          which has already been added
            returns the error 'has already been added' (FAILED - 2621)
        when params doesn't contain a group
          doesn't create a selected_recipient_group (FAILED - 2622)
      with multi_content
        for content_one
          behaves like a service updating recipients
            updates existing recipients_code and appropriate multi_content column (FAILED - 2623)
            sets recipients_code and appropriate multi_content column to params when none exist (FAILED - 2624)
            adding an existing recipient
              to the same column
                returns an error (FAILED - 2625)
                doesn't change any recipient columns (FAILED - 2626)
              to the other column
                returns an error (FAILED - 2627)
                doesn't change any recipient columns (FAILED - 2628)
        for content_two
          behaves like a service updating recipients
            updates existing recipients_code and appropriate multi_content column (FAILED - 2629)
            sets recipients_code and appropriate multi_content column to params when none exist (FAILED - 2630)
            adding an existing recipient
              to the same column
                returns an error (FAILED - 2631)
                doesn't change any recipient columns (FAILED - 2632)
              to the other column
                returns an error (FAILED - 2633)
                doesn't change any recipient columns (FAILED - 2634)
        adding groups
          doesn't work without a content_type (FAILED - 2635)
          with a valid content_type
            sets content_type on the group (FAILED - 2636)
            does not affect individuals in recipients_code_content_one (FAILED - 2637)
          with an invalid content_type
            returns an error re: content_number (FAILED - 2638)
    without existing SelectedRecipient
      sets recipients_code to params[:recipient_code] (FAILED - 2639)
      adding groups
        creates a selected_recipient (FAILED - 2640)
        when params contains a group
          creates a selected_recipient_group (FAILED - 2641)
        when params doesn't contain a group
          doesn't create a selected_recipient_group (FAILED - 2642)
      with multi_content
        for content_one
          sets recipients_code and recipients_code_content_one to params[:recipient_code] (FAILED - 2643)
          adding MN State Democrats
            behaves like a SelectedRecipient creator and SelectedRecipientGroup attacher
              makes the SelectedRecipient (FAILED - 2644)
              attaches the appropriate SelectedRecipientGroup (FAILED - 2645)
              doesn't add individual recipient ids (FAILED - 2646)
          adding WI State Republicans
            behaves like a SelectedRecipient creator and SelectedRecipientGroup attacher
              makes the SelectedRecipient (FAILED - 2647)
              attaches the appropriate SelectedRecipientGroup (FAILED - 2648)
              doesn't add individual recipient ids (FAILED - 2649)
        for content_two
          sets recipients_code and recipients_code_content_two to params[:recipient_code] (FAILED - 2650)
          adding MN State Democrats
            behaves like a SelectedRecipient creator and SelectedRecipientGroup attacher
              makes the SelectedRecipient (FAILED - 2651)
              attaches the appropriate SelectedRecipientGroup (FAILED - 2652)
              doesn't add individual recipient ids (FAILED - 2653)
          adding WI State Republicans
            behaves like a SelectedRecipient creator and SelectedRecipientGroup attacher
              makes the SelectedRecipient (FAILED - 2654)
              attaches the appropriate SelectedRecipientGroup (FAILED - 2655)
              doesn't add individual recipient ids (FAILED - 2656)
  errors
    returns an error if promoted_message doesnt save (FAILED - 2657)
    returns an error if selected_recipient is SURVEY (FAILED - 2658)

retrieve conversion recipient names
  successful calls
    processed succesfully (FAILED - 2659)
    either start/end date before cutoff date then fetch from db (FAILED - 2660)
    both start/end date after cutoff date does not fetch from db (FAILED - 2661)
    both start/end date after cutoff date then fetch from ES (FAILED - 2662)
    returns just content_one conversions for multi_content content_one (FAILED - 2663)
    returns just content_two conversions for multi_content content_two (FAILED - 2664)
  failed calls
    no promoter in params (FAILED - 2665)
    start_date greater than end_date (FAILED - 2666)

Admin::DeliveryDataService
  call
    with a Conversion on another message
      doesn't count towards figures[:total] (FAILED - 2667)
    with a Conversion without a 'Submit'
      counts towards figures[:did_not_submit] (FAILED - 2668)
    with a Conversion without a 'Verification'
      counts towards figures[:not_sendable] (FAILED - 2669)
    with a Conversion with a finished delivery
      counts towards figures[:finished_sending] (FAILED - 2670)
    with different finished counts
      counts towards figures[:finished_sending] (FAILED - 2671)
      counts towards figures[:finished_sending_no_targets] (FAILED - 2672)
      counts towards figures[:finished_sending_reached_nobody] (FAILED - 2673)
      counts towards figures[:finished_sending_reached_some] (FAILED - 2674)
      counts towards figures[:finished_sending_reached_all] (FAILED - 2675)
      counts towards figures[:potential_deliveries] (FAILED - 2676)
      counts towards figures[:viable_deliveries] (FAILED - 2677)
      counts towards figures[:successful_deliveries] (FAILED - 2678)
      percent_of_viable
        renders percentages (FAILED - 2679)
    with different unfinished counts
      counts towards figures[:finished_sending] (FAILED - 2680)
    after gathering figures
      adding more conversions
        uses the cached figures (FAILED - 2681)
        passing refresh_figures
          re-calculates the figures (FAILED - 2682)
    with start_date and end_date
      a Conversion before
        doesn't return (FAILED - 2683)
      Conversions during
        return (FAILED - 2684)
      a Conversion after
        doesn't return (FAILED - 2685)
    with a status
      with assorted Conversions
        when status = done_no_targets
          behaves like a status filter
            filters the results (FAILED - 2686)
        when status = done_all_failed
          behaves like a status filter
            filters the results (FAILED - 2687)
        when status = done_some_failed
          behaves like a status filter
            filters the results (FAILED - 2688)
        when status = finished
          behaves like a status filter
            filters the results (FAILED - 2689)
        when status = stale
          behaves like a status filter
            filters the results (FAILED - 2690)
        when status = ongoing
          behaves like a status filter
            filters the results (FAILED - 2691)
        when status = not_verified
          behaves like a status filter
            filters the results (FAILED - 2692)
        when status = not_submitted
          behaves like a status filter
            filters the results (FAILED - 2693)
        when status = duplicate
          behaves like a status filter
            filters the results (FAILED - 2694)
        when status = not_staged
          behaves like a status filter
            filters the results (FAILED - 2695)
        when status = no_recipients
          behaves like a status filter
            filters the results (FAILED - 2696)
    with pages of conversions
      on page 1
        behaves like a paginator
          returns conversions on the current page (FAILED - 2697)
          excludes conversions on other pages (FAILED - 2698)
      on page 2
        behaves like a paginator
          returns conversions on the current page (FAILED - 2699)
          excludes conversions on other pages (FAILED - 2700)
  promoted_messages_list_options
    should return a list of promoted messages for campaign dropdown (FAILED - 2701)

Admin::Integrations::IntegrationsService
  returns kindful and nation_builder Authentications (FAILED - 2702)
  doesn't return facebook Authentications (FAILED - 2703)
  pagination
    splits results into pages (FAILED - 2704)
  filtering
    by provider
      provider = nation_builder
        returns the nation_builder Authentication (FAILED - 2705)
        doesn't return other Authentications (FAILED - 2706)
      provider = facebook
        ignores the filter (FAILED - 2707)
    by promoter id
      returns the nation_builder Authentication (FAILED - 2708)
      doesn't return other Authentications (FAILED - 2709)

Admin::Integrations::IntegrationsUpdateService
  call
    with a new promoter_id
      without a PromoterUser record
        doesn't create a new Account (FAILED - 2710)
        doesn't update the Authentication's account_id (FAILED - 2711)
      with a PromoterUser
        without an Account
          creates a new Account (FAILED - 2712)
          updates the Authentication's account_id (FAILED - 2713)
        with an Account
          doesn't create a new Account (FAILED - 2714)
          updates the Authentication's account_id (FAILED - 2715)
    with parameters
      updates the parameters (FAILED - 2716)

Admin::PromoterUsers::ChangePromoterToAgencyService
  call
    on a standard promoter
      successfully
        should change promoter user to agency and return success hash (FAILED - 2717)
      unsuccessfully
        should not change promoter user to agency and return error hash (FAILED - 2718)
      that does not have a product
        should return error results hash (FAILED - 2719)
    on a non standard promoter user
      should not change promoter user to agency and return failure hash (FAILED - 2720)
    on a nonexistent promoter user
      should return error results hash (FAILED - 2721)

retrieve advocates for country map
  successful calls
    should return advocates for a promoter (FAILED - 2722)
  errors
    should respond with errors for invalid params (FAILED - 2723)

CreateContact
  call
    returns creates a contact (FAILED - 2724)
  valid_phone_number?
    is valid
    is invalid

CwcHash
  .dig!
    with a hash
      retrieves a nested value
  .dig
    with a hash
      retrieves a nested value

CWC::Message
  #generate_delivery_id
    should return a 32 long AlphaNumeric string

CwcHandler
  #cwc_message formating
    Checks if the cwc_message is filled with the topic (FAILED - 2725)
    Checks if the cwc_message is filled if the topic is nill (FAILED - 2726)
  when sender's phone is nil
    cwc_message generates an exception, CwcNoPhoneException (FAILED - 2727)
    send_message returns false and does not send the message to the CWC (FAILED - 2728)
  when sender's email is invalid
    cwc_message does not generate an exception, CwcInvalidEmailException (FAILED - 2729)
    send_message returns false and does not send the message to the CWC (FAILED - 2730)
  when recipient's office code is an inactive office
    cwc_message does not generate an exception, CwcInactiveOfficeException (FAILED - 2731)
    send_message returns false and does not send the message to the CWC (FAILED - 2732)
  when sender's address is invalid
    cwc_message does not generate an exception, CwcInvalidAddressException (FAILED - 2733)
    send_message returns false and does not send the message to the CWC (FAILED - 2734)
  format_phone
    with irregular characters
      behaves like a standardized phone number
        has two dashes (FAILED - 2735)
        has seven numbers (FAILED - 2736)
    with a leading 1
      behaves like a standardized phone number
        has two dashes (FAILED - 2737)
        has seven numbers (FAILED - 2738)
  format_city
    with a city string of size < 2
      lengthens it (FAILED - 2739)
    with a city string of size >= 2
      doesn't lengthen it (FAILED - 2740)

DeliveryHandler
  for invalid signatures
    the Conversion's comment field
      is_duplicate? = true
        example at ./spec/services/delivery_handler_spec.rb:37 (FAILED - 2741)
        example at ./spec/services/delivery_handler_spec.rb:38 (FAILED - 2742)
      is_banned? = true
        example at ./spec/services/delivery_handler_spec.rb:45 (FAILED - 2743)
        example at ./spec/services/delivery_handler_spec.rb:46 (FAILED - 2744)
      is_not_staged? = true
        example at ./spec/services/delivery_handler_spec.rb:55 (FAILED - 2745)
        example at ./spec/services/delivery_handler_spec.rb:56 (FAILED - 2746)
      has_no_recipients? = true
        example at ./spec/services/delivery_handler_spec.rb:64 (FAILED - 2747)
        example at ./spec/services/delivery_handler_spec.rb:65 (FAILED - 2748)

generate advocate aggregate graph csv
  csv headers (FAILED - 2749)
  csv includes all the range of dates (FAILED - 2750)
  has data in agg table
    csv fetches from aggregate table before cutoff date (FAILED - 2751)
    returns a blank CSV if all_messages false and no message_ids (FAILED - 2752)

generate legislator aggregate graph csv
  successful calls
    csv headers:
      by date (FAILED - 2753)
      by target/aggregate (FAILED - 2754)
    data around cutoff date
      includes data before cutoff date from ETL tables: by date (FAILED - 2755)
      does not include data after cutoff date from ETL tables: by date (FAILED - 2756)
      includes data before cutoff date from ETL tables: by recipient (FAILED - 2757)
      does not includes data after cutoff date from ETL tables: by recipient (FAILED - 2758)

GetBlogPageService
  call
    should return first page with 10 most recent blog articles when no arguments are passed (FAILED - 2759)
    should return blog articles (FAILED - 2760)

ImportResponsibilitiesFromStaffersService
  call
    should create responsibilities if they dont exist and associate responsibilities to staffer (FAILED - 2761)

NationBuilderEventRSVP
  get_person_id()
    works
  find_person()
    works
    fails gracefully (FAILED - 2762)
  create_person()
    works
  call()
    works
    fails gracefully (FAILED - 2763)

OneClickWidgetApi::DeliverEmailConversionService
  execute
    with required params
      should successfully deliver conversion (FAILED - 2764)
      should update conversion on successful delivery (FAILED - 2765)
      and promoted message cannot be found
        should return failure status and message (FAILED - 2766)
      and promoted message does not have email action
        should not update or deliver conversion (FAILED - 2767)
      and message is not valid
        should not update or deliver conversion (FAILED - 2768)
    without required params
      sender_profile_id
        behaves like a service call without required parameters
          should return failure status in failure hash (FAILED - 2769)
          should return missing required parameters message in failure hash (FAILED - 2770)
      promoted_message_id
        behaves like a service call without required parameters
          should return failure status in failure hash (FAILED - 2771)
          should return missing required parameters message in failure hash (FAILED - 2772)

OneClickWidgetApi::GenerateOrUpdateSenderProfileService
  execute
    with valid params
      validation service returns success
        when sender data already exists for that promoter and promoted message
          has pre-existing data (FAILED - 2773)
          returns correct data (FAILED - 2774)
          behaves like a successful service call
            ensures the correct count of data (FAILED - 2775)
            returns success status (FAILED - 2776)
        when sender data does not already exist for that promoter and promoted message
          has no pre-existing data (FAILED - 2777)
          returns correct data (FAILED - 2778)
          behaves like a successful service call
            ensures the correct count of data (FAILED - 2779)
            returns success status (FAILED - 2780)
      when providing honeypot field values
        zip_confirmation
          should return honeypot response and message (FAILED - 2781)
          should not create new data (FAILED - 2782)
        email_confirmation
          should return honeypot response and message (FAILED - 2783)
          should not create new data (FAILED - 2784)
      validation service returns failure
        should return failure hash (FAILED - 2785)
    with invalid params
      should return error when sender profile fails to save (FAILED - 2786)
    with missing data
      promoted message
        should return error hash (FAILED - 2787)
      sender data
        should return error hash (FAILED - 2788)

OneClickWidgetApi::GetRecipientDataForWidgetService
  execute
    single content campaign
      with passed parameters
        should successfully collect relevant data from single content recipients (FAILED - 2789)
      with missing parameters
        should return failure status and message with no recipient ids (FAILED - 2790)
    multi content campaign
      with passed parameters
        should successfully collect relevant data from multi content recipients (FAILED - 2791)

OneClickWidgetApi::GetRecipientIdsForSenderProfileService
  execute
    single content
      when required params are present
        returns success hash with matching recipient ids (FAILED - 2792)
        and a selected recipient group code is not valid
          returns success hash with matching recipient ids (FAILED - 2793)
      when required params is missing
        promoted_message_id
          returns failure hash with message and no recipient ids (FAILED - 2794)
        sender_profile_id
          returns failure hash with message and no recipient ids (FAILED - 2795)
        conversion_id
          returns failure hash with message and no recipient ids (FAILED - 2796)
    multi content
      when senator group is part of content_two
        returns success hash with recipient ids (FAILED - 2797)
        has the correct recipient ids (FAILED - 2798)
      and selected recipient group code is not valid
        returns success hash with recipient ids (FAILED - 2799)
        has the correct recipient ids (FAILED - 2800)

OneClickWidgetApi::GetSocialUrlsService
  execute
    with params
      successfully
        should return hash of social urls (FAILED - 2801)
      when promoted message is missing
        should return failure response with missing promoted message message (FAILED - 2802)
    without params
      promoted message id
        should return missing param response (FAILED - 2803)
      recipient ids
        should return missing param response (FAILED - 2804)

OneClickWidgetApi::Social::GetEmailShareUrl
  execute
    when passed a valid promoted_message should return share url (FAILED - 2805)

OneClickWidgetApi::Social::GetFacebookShareUrl
  execute
    when passed a valid promoted_message should return share url (FAILED - 2806)

OneClickWidgetApi::Social::GetLinkedinShareUrl
  execute
    when passed a valid promoted_message should return share url (FAILED - 2807)

OneClickWidgetApi::Social::GetTwitterShareUrl
  execute
    when passed a valid promoted_message should return share url (FAILED - 2808)

OneClickWidgetApi::SubmitEmailConversionService
  execute
    with params
      with successful email conversion submission
        with successful social urls service response
          calls submission services successfully and returns success hash (FAILED - 2809)
        with unsuccessful social urls service response
          raises and rescues error and returns failure hash (FAILED - 2810)
      with unsuccessful email conversion submission
        raises and rescues error and returns failure hash (FAILED - 2811)
      when essential data is missing
        promoted message
          should return missing promoted message response (FAILED - 2812)
        sender profile
          should return missing sender profile response (FAILED - 2813)
    without params
      promoted message id
        should return missing param response (FAILED - 2814)
      promoter id
        should return missing param response (FAILED - 2815)
      sender profile id
        should return missing param response (FAILED - 2816)

OneClickWidgetApi::SubmitSenderDataService
  execute
    without a promoted message
      should return failure status hash (FAILED - 2817)
    with a promoted message
      without sender data
        should return failure status hash (FAILED - 2818)
      with sender data
        with successful sender profile generation
          with successful get recipient ids service call
            with successful get recipient data service call
              should successfully call step one services and return successful response (FAILED - 2819)
            with failing get recipient data service call
              should return failure hash (FAILED - 2820)
          with failing get recipient ids service call
            should return failure hash (FAILED - 2821)
        with honeypot response
          should return success status (FAILED - 2822)
        with failing sender profile generation
          should return failure hash (FAILED - 2823)

OneClickWidgetApi::ValidateSenderProfileService
  execute
    should return successful response when run without errors (FAILED - 2824)
    when record is true
      and account email is present
        and account email passes regex
          should return success hash and not add error to account (FAILED - 2825)
        and account email does not pass regex
          should return failure hash and add error to account (FAILED - 2826)
      and account email is not present
        should return failure hash and add error to account (FAILED - 2827)
    should configure force_phone_validation according to promoted message skip_phone?
      when skip_phone is false
        should be true (FAILED - 2828)
      when skip_phone is true
        should be false (FAILED - 2829)
    should configure ignore_name_validation according to record param
      when record is true
        should be false (FAILED - 2830)
      when record is false
        should be true (FAILED - 2831)
    should configure zip_validation and full_validation
      when require_address is false
        and campaign is a survey
          and promoted message does not require_zip_only
            should set validations to false (FAILED - 2832)
        and campaign is not a survey
          should not set validations to false (FAILED - 2833)
      when require_address is true
        and campaign is a survey
          and promoted message require_zip_only
            should configure validations appropriately (FAILED - 2834)
          and promoted message does not require_zip_only
            validations should be true (FAILED - 2835)
    with missing param
      promoted_message
        should return missing params failure response (FAILED - 2836)
      sender_profile
        should return missing params failure response (FAILED - 2837)
      account
        should return missing params failure response (FAILED - 2838)
      record
        should return missing params failure response (FAILED - 2839)

OneclickWidgetHandler
  get_recipient_ids
    multi_content
      multi_content turned on
        should set the conversion multi_content columns (FAILED - 2840)
        should set recipients and recipient_ids_expanded (FAILED - 2841)
      multi_content turned off
        doesn't set multi_content columns if promoted message multi_content is off (FAILED - 2842)
    unwrapping recipient IDs from selected_recipient and returning correct recipients with a committee and a separate target
      includes active members (FAILED - 2843)
      includes separate targets (FAILED - 2844)
      excludes the committee's id (FAILED - 2845)
      excludes inactive members (FAILED - 2846)
      excludes inactive targets (FAILED - 2847)
    recipient columns on the conversion
      with constituents_only
        conversion.recipients
          doesn't include OOD recipients (FAILED - 2848)
          includes in-district recipients (FAILED - 2849)
        conversion.recipient_ids_always_send_and_local
          doesn't include OOD recipients (FAILED - 2850)
          includes in-district recipients (FAILED - 2851)
        multi-content
          #get_multi_content_recipients
            only looks for in-district recipients (FAILED - 2852)
      without constituents_only
        conversion.recipients
          includes OOD recipients (FAILED - 2853)
          includes in-district recipients (FAILED - 2854)
        conversion.recipient_ids_always_send_and_local
          doesn't include OOD recipients (FAILED - 2855)
          includes in-district recipients (FAILED - 2856)

Promoter::BuildCsvForLegislatorsResultsService
  call
    should return csv for legislator filter (FAILED - 2857)

Promoter::BuildCsvForStafferResultsService
  call
    should return csv for legislator staff (FAILED - 2858)

Promoter::BuildFilenameForLegislatorStaffExportService
  call
    for recipient with a name
      should return filename for legislator staff export file (FAILED - 2859)
    for recipient without a name
      should return filename for legislator staff export file (FAILED - 2860)
    for non existent recipient
      should return nil

Promoter::Importing::CustomRecipientsImporter
  klass
    should be defined (FAILED - 2861)
  allowed_header_matrix
    should be defined (FAILED - 2862)
  import_csv
    should return csv of custom targets and a collection of valid csv headers (FAILED - 2863)
  attr_field_by_header_match(header_str)
    should return the key when passed a matching header (FAILED - 2864)
    should not return a key when passed a mismatching header (FAILED - 2865)

Promoter::LegislatorFilterService
  call
    with no filters
      behaves like a legislator filter
        should return active legislator staff (FAILED - 2866)
    with a title filter
      behaves like a legislator filter
        should return active legislator staff (FAILED - 2867)
    with a responsibility filter
      behaves like a legislator filter
        should return active legislator staff (FAILED - 2868)
    with a country
      where country is United States
        behaves like a legislator filter
          should return active legislator staff (FAILED - 2869)
      where country is Canada
        behaves like a legislator filter
          should return active legislator staff (FAILED - 2870)
      where country is Australia
        behaves like a legislator filter
          should return active legislator staff (FAILED - 2871)
    with country and level
      United States, Federal Upper
        behaves like a legislator filter
          should return active legislator staff (FAILED - 2872)
      United States, Federal Lower
        behaves like a legislator filter
          should return active legislator staff (FAILED - 2873)
      United States, State Upper
        behaves like a legislator filter
          should return active legislator staff (FAILED - 2874)
      United States, State Lower
        behaves like a legislator filter
          should return active legislator staff (FAILED - 2875)
      United States, invalid level
        behaves like a legislator filter
          should return active legislator staff (FAILED - 2876)
      Canada, Federal Upper
        behaves like a legislator filter
          should return active legislator staff (FAILED - 2877)
      Canada, Federal Lower
        behaves like a legislator filter
          should return active legislator staff (FAILED - 2878)
      Canada, State Upper
        behaves like a legislator filter
          should return active legislator staff (FAILED - 2879)
      Canada, State Lower
        behaves like a legislator filter
          should return active legislator staff (FAILED - 2880)
      Canada, invalid level
        behaves like a legislator filter
          should return active legislator staff (FAILED - 2881)
      Australia, Federal Upper
        behaves like a legislator filter
          should return active legislator staff (FAILED - 2882)
      Australia, Federal Lower
        behaves like a legislator filter
          should return active legislator staff (FAILED - 2883)
      Australia, State Upper
        behaves like a legislator filter
          should return active legislator staff (FAILED - 2884)
      Australia, State Lower
        behaves like a legislator filter
          should return active legislator staff (FAILED - 2885)
      Australia, invalid level
        behaves like a legislator filter
          should return active legislator staff (FAILED - 2886)
    with committee
      behaves like a legislator filter
        should return active legislator staff (FAILED - 2887)
    with state
      behaves like a legislator filter
        should return active legislator staff (FAILED - 2888)

Promoter::LegislatorStaffFilterService
  call
    with no filters
      behaves like a staff filter
        should return active legislator staff (FAILED - 2889)
    with a title filter
      behaves like a staff filter
        should return active legislator staff (FAILED - 2890)
    with a responsibility filter
      behaves like a staff filter
        should return active legislator staff (FAILED - 2891)
    with a country
      where country is United States
        behaves like a staff filter
          should return active legislator staff (FAILED - 2892)
      where country is Canada
        behaves like a staff filter
          should return active legislator staff (FAILED - 2893)
      where country is Australia
        behaves like a staff filter
          should return active legislator staff (FAILED - 2894)
    with country and level
      United States, Federal Upper
        behaves like a staff filter
          should return active legislator staff (FAILED - 2895)
      United States, Federal Lower
        behaves like a staff filter
          should return active legislator staff (FAILED - 2896)
      United States, State Upper
        behaves like a staff filter
          should return active legislator staff (FAILED - 2897)
      United States, State Lower
        behaves like a staff filter
          should return active legislator staff (FAILED - 2898)
      United States, invalid level
        behaves like a staff filter
          should return active legislator staff (FAILED - 2899)
      Canada, any
        behaves like a staff filter
          should return active legislator staff (FAILED - 2900)
      Australia, any
        behaves like a staff filter
          should return active legislator staff (FAILED - 2901)
    with committee
      behaves like a staff filter
        should return active legislator staff (FAILED - 2902)
    with state
      behaves like a staff filter
        should return active legislator staff (FAILED - 2903)

Promoter::RecipientList
  state_committees_with_members
    with empty Committees
      does not include them (FAILED - 2904)
    Committees with Recipients
      includes them (FAILED - 2905)

RecipientCodeHandler
  #new_by_group_options
    without delivery: true
      doesn't return the recipients (FAILED - 2906)
      returns a state_id when a state_code is passed (FAILED - 2907)
    with delivery: true
      returns the recipients (FAILED - 2908)
      returns a state_id when a state_code is passed (FAILED - 2909)
      with duplicate WI State House reps, 1 active, 1 inactive
        example at ./spec/services/recipient_code_handler_spec.rb:42 (FAILED - 2910)
        example at ./spec/services/recipient_code_handler_spec.rb:44 (FAILED - 2911)
        example at ./spec/services/recipient_code_handler_spec.rb:46 (FAILED - 2912)
      With UK groups
        returns all UK Parliament members when group is APUK (FAILED - 2913)
        returns members in England only when group is ENG (FAILED - 2914)
        returns members in Scotland only when group is SCT (FAILED - 2915)
        returns members in Labour party only when group is Lab (FAILED - 2916)
        returns members in Scottish National party only when group is SNP (FAILED - 2917)

RecipientSelectionHandler
  #has_video?
    responds with true when there's a video (FAILED - 2918)
    responds with false or nil when there's no video (FAILED - 2919)
  #get_recipient_ids_content_one
    includes ids from the SelectedRecipient's recipients_code_content_one (FAILED - 2920)
    with groups
      includes ids of content_one group members (FAILED - 2921)
      returns each id only once (FAILED - 2922)
  #get_recipient_ids_content_two
    includes ids from the SelectedRecipient's recipients_code_content_two (FAILED - 2923)
    with groups
      includes ids of content_two group members (FAILED - 2924)
      returns each id only once (FAILED - 2925)
      excludes ids in content_one (FAILED - 2926)
  #get_recipient_ids
    with a state_group_code WI 'all house' and co-mingled recipients
      after a knowwho update renders one rep inactive and replaces them
        includes the new rep (FAILED - 2927)
        doesn't include the old rep (FAILED - 2928)
    with mingled active and inactive individual reps
      includes actives (FAILED - 2929)
      excludes inactives (FAILED - 2930)
    with 'All of Congress', constituents_only, and a co-mingled committee
      with a profile
        includes the local Senator (FAILED - 2931)
        includes the committee member (FAILED - 2932)
    with a recipient_codes group All WI State Democrats and a co-mingled rep
      includes the Democrat (FAILED - 2933)
      returns an added individual who is also a group member only once (FAILED - 2934)
      doesn't include the Democrat outside of WI State Leg (FAILED - 2935)
      includes the co-mingled rep (FAILED - 2936)
      doesn't include the Republican (FAILED - 2937)
    with a recipient_codes group All WI State Republicans and a co-mingled rep
      includes the Republican (FAILED - 2938)
      includes the co-mingled rep (FAILED - 2939)
      doesn't include the Democrat (FAILED - 2940)
    with 2 selected_recipient_groups
      includes the WI State Democrat (FAILED - 2941)
      includes the MA State Democrat (FAILED - 2942)
      includes the co-mingled rep (FAILED - 2943)
      doesn't include the Republican (FAILED - 2944)
  #get_local_recipient_ids
    with an OOD committee and a chair flagged as 'always-send'
      with a profile
        doesn't include the committee member (FAILED - 2945)
        includes the committee chair (FAILED - 2946)
      without a profile
        includes the committee chair (FAILED - 2947)
    with a mixture of local ids and always-sends
      with a profile
        arranges the always-sends first (FAILED - 2948)
        omits the oods without always-send (FAILED - 2949)

RefreshAccessToken service
  with good params
    returns the newly updated authentication (FAILED - 2950)
    updates the authentication in the database (FAILED - 2951)
  without a promoter
    should respond with errors
  without an authentication
    should respond with errors (FAILED - 2952)

retrieve activity stream
  successful calls
    retrieves activity stream correctly (FAILED - 2953)
  errors
    should respond with errors for invalid params passed to a call to RetrieveActivityStream (FAILED - 2954)

retrieve advocate aggregation data
  data_array
    should not return data for promoted messages passed in that don't belong to the promoter user (FAILED - 2955)
    should work when no promoted messages passed in and all_messages is false (FAILED - 2956)
    retrieve correct data with valid params and add blank entries when needed (FAILED - 2957)
    retrieve correct data with valid params and add blank entries when needed (FAILED - 2958)
    with multi_content params
      should return content_one content with content_one params (FAILED - 2959)
      should return content_two content with content_two params (FAILED - 2960)
      should return only info for one promoted message even when multiple message_ids (FAILED - 2961)
      should return only info for one promoted message even when all_messages true (FAILED - 2962)
      should not use multi_content when multi_content_selector is blank (FAILED - 2963)
  errors
    should respond with errors for invalid params passed to a call to RetrieveAdvocateAggregateData (FAILED - 2964)

retrieve agency activity hash
  successful calls
    retrieves agency_activity_hash from agg_agency_total_activity (FAILED - 2965)
    returns hash of 0s when no entry for agency in agg_agency_total_activity (FAILED - 2966)
  errors
    should respond with errors for invalid params

retrieve campaign activity for advocate
  successful calls
    retrieves campaign activity (FAILED - 2967)
  errors
    should respond with errors for invalid params passed to a call to RetrieveCampaignActivityForAdvocate

retrieve committees for search
  successful calls
    should return proper committees for Canadian State legislators (FAILED - 2968)
    should return proper committees for American Federal House legislators even when a state is in params (FAILED - 2969)
    should return committees active in the time frame (FAILED - 2970)
  calls that produce errors
    should return errors for searches with invalid params (FAILED - 2971)

retrieve conversion recipient names
  successful calls
    retrieves conversions with advocate_profiles for multiple message_ids (FAILED - 2972)
    returns all_messages conversions with date restrictions (FAILED - 2973)
    returns results for just one promoted_message in a time frame (FAILED - 2974)
    returns no conversions if message_ids blank and all_messages nil (FAILED - 2975)
    returns just content_one conversions for multi_content content_one (FAILED - 2976)
    returns just content_two conversions for multi_content content_two (FAILED - 2977)
  failed calls
    should respond with errors (FAILED - 2978)

retrieve advocate aggregation data
  successful calls to RetrieveLegislatorAggregateData
    promoted_message level data returns
      return_in_aggregate == false
        returns data for multiple promoted messages (FAILED - 2979)
        returns data for committees and messages (FAILED - 2980)
        should return data for federal offices with no state params but with promoted_message params (FAILED - 2981)
        should return data for federal/state offices with a state and messages (FAILED - 2982)
        should return data for state and promoted_messages (FAILED - 2983)
        should return data for single recipient and promoted_message (FAILED - 2984)
        returns all recipients for a promoted_message if promoted_message is only param (FAILED - 2985)
        returns all 0s if there are no recipients for committee (FAILED - 2986)
        returns all 0s if there is a recipient in the params with no entries in the agg db for the time period (FAILED - 2987)
        should return all 0s if there are no promoted_messages and all_messages is false (FAILED - 2988)
        with multi_content == true
          returns content_one info (FAILED - 2989)
          returns content_two info (FAILED - 2990)
      return_in_aggregate == true
        returns a blank array if return_in_aggregate is passed in and all_messages is false and there are no promoted_messages (FAILED - 2991)
        returns data aggregated across days if return_in_aggregate is passed in with multiple promoted messages (FAILED - 2992)
        with multi_content == true
          returns content_one if content_one passed in (FAILED - 2993)
          returns content_two if content_two passed in (FAILED - 2994)
    promoter_user level data returns
      return_in_aggregate == false
        returns data for committees and promoter (FAILED - 2995)
        returns data for federal office with no state params and promoter (FAILED - 2996)
        returns data for federal/state offices with a state and promoter (FAILED - 2997)
        returns data for state and promoter (FAILED - 2998)
        returns data for recipient and promoter (FAILED - 2999)
        returns all recipients for time period if no params (FAILED - 3000)
        with multi_content == true
          returns promoted message level results even when all_messages passed in (FAILED - 3001)
      return_in_aggregate == true
        returns aggregated across days if return_in_aggregate is passed in (FAILED - 3002)
        with multi_content == true
          returns promoted message level results even when all_messages passed in (FAILED - 3003)
  failed calls to RetrieveLegislatorAggregateData
    should respond with errors for invalid params passed to a call to RetrieveLegislatorAggregateData (FAILED - 3004)

retrieve recipients for search
  responds with errors for invalid params (FAILED - 3005)
  a successful call
    successfully returns recipients for all possible valid params passed in (FAILED - 3006)
    doesn't include district names by default (FAILED - 3007)
    does include district names when "include_district" is true (FAILED - 3008)

validate agency dashboard sort by
  successful calls
    returns sorted promoter_users when valid (FAILED - 3009)
  errors
    should respond with errors for invalid sort_by params (FAILED - 3010)
    should respond with errors if agency blank

Return advocates for table
  successful calls to ReturnAdvocatesForTable
    successfully selects advocates based on a search (FAILED - 3011)
    successfully orders advocates (FAILED - 3012)
  error handling
    should respond with error when no promoter passed to call

SendTextMessage
  Epoch conversion testing
    returns a unix timestamp in the expected format if the message is scheduled (FAILED - 3013)
    returns the current time if no time passed in params (FAILED - 3014)
    Fails if the time is in the wrong format (FAILED - 3015)
    the converted time
      with a PST offset
        adjusts by 3 hours (FAILED - 3016)
      with a Hawaii offset
        adjusts by 5 hours (FAILED - 3017)
  .call
    with a text message groups parameter
      passes the text message groups parameter (FAILED - 3018)
  Check errors raised during validation
    Test to make sure the group fails properly with no group (FAILED - 3019)
    Test to make sure the message fails if it contains special characters (FAILED - 3020)
    Test to make sure the subject fails if it contains special characters (FAILED - 3021)
    Test to make sure the message fails if it's longer than 150 characters (FAILED - 3022)
    Test to make sure the subject fails properly if it's over 13 characters (FAILED - 3023)
    Test to make sure the message fails properly when it's blank (FAILED - 3024)
  validate_credits
    Raises an error if the promoter is out of credits (FAILED - 3025)
    The credits should update properly after a text message is sent (FAILED - 3026)
    Making sure credits total properly when there are multiple groups passed in (FAILED - 3027)
  Should successfully add and remove a model
    remove a text message (FAILED - 3028)
    creating a text messagee (FAILED - 3029)

slack notification service
  checking the public wrapper methods
    works for etl_alert
    works for new_relic_alert
    works for nation_builder_alert
    works for local_process_alert
  create_message
    will send a message

recieves data from the amusement park api
  successful calls
    gets some advocates data
    creates a bunch of stuff (FAILED - 3030)
    will not create an account if the advocate has no email
    Rails logger recieves the exception (FAILED - 3031)

SyncNimble service
  with max_sigs set to 2
    creates 2 transactions for 4 records (FAILED - 3032)
    and 5 records
      creates 3 transactions (FAILED - 3033)
      with a destination_email
        only notifies the user once (FAILED - 3034)
  with max_sigs set to 5
    creates 3 transactions for 11 records (FAILED - 3035)
  with an existing in_progress transaction for this promoter
    should respond with errors (FAILED - 3036)
  without a promoter
    should respond with errors (FAILED - 3037)
  without an authentication
    should respond with errors (FAILED - 3038)
  without an transaction_client_api_key
    should respond with errors (FAILED - 3039)
  without a destination_email AND with manual == true
    should respond with errors (FAILED - 3040)
  with an invalid destination_email AND with manual == true
    should respond with errors (FAILED - 3041)
  with a destination_email that has whitespace AND with manual == true
    should not respond with errors (FAILED - 3042)

TextMessageGroupContactsService
  call
    returns contacts (FAILED - 3043)

TextMessageKeywordService
  self.create_keyword_in_ez_texting
    raises an error when join message is blank and returns an unprocessed openstruct object (FAILED - 3044)
    raises an error when join message is too long and returns an unprocessed openstruct object (FAILED - 3045)
  self.setup_keyword(keyword)
    can setup the keyword (FAILED - 3046)
    validate the keyword join message (FAILED - 3047)
    adds a confirm message then removes it (2 API callls) (FAILED - 3048)
    changes the join message and removes the confirm message (FAILED - 3049)
    tests the failure status (FAILED - 3050)
    tests the max length of a message (FAILED - 3051)
  def self.keyword_available_in_ez_texting?(keyword)
    returns false (keyword unavailable)
    returns true (keyword available)
  self.rent_keyword(keyword_in)
    rents the keyword
    with credit card failure
      logs errors

UpdateConversionRecipients
  successful calls
    multi_content turned on
      with CongressMembers
        behaves like a filter for OOD CongressMembers
          removes OOD Congressmembers from .recipients (FAILED - 3052)
          removes OOD Congressmembers from .always_send_ids (FAILED - 3053)
          doesn't remove in-district Congressmembers from .recipients (FAILED - 3054)
          doesn't remove in-district Congressmembers from .always_send_ids (FAILED - 3055)
    multi_content turned off
      with CongressMembers
        behaves like a filter for OOD CongressMembers
          removes OOD Congressmembers from .recipients (FAILED - 3056)
          removes OOD Congressmembers from .always_send_ids (FAILED - 3057)
          doesn't remove in-district Congressmembers from .recipients (FAILED - 3058)
          doesn't remove in-district Congressmembers from .always_send_ids (FAILED - 3059)
    multi_content turned on
      saves recipient_ids_expanded_content_one and recipient_ids_expanded_content_two and multi_content (FAILED - 3060)
      works with multi_content if one content is nil (FAILED - 3061)
    multi_content turned off
      doesn't save any multi_content columns to conversion (FAILED - 3062)
    saving columns where constituency doesnt matter
      correctly saves recipient_ids_local (FAILED - 3063)
      correctly saves recipient_ids_always_send (FAILED - 3064)
      correctly saves recipient_ids_always_send_and_local (FAILED - 3065)
      correctly saves recipient_ids_expanded (FAILED - 3066)
      correctly saves non-recipient columns (FAILED - 3067)
      correctly saves sender_profile columns to a conversion (FAILED - 3068)
    saving columns where constituency matters
      correctly saves recipients
        saves recipients as always_send_and_local IDs with constituents_only turned on (FAILED - 3069)
        saves recipients as all recipients on promoted message with constituents_only turned off (FAILED - 3070)
    service return values
      returns results.recipients correctly
        returns the always_send_and_local IDs with constituents_only turned on (FAILED - 3071)
        returns all recipients fully expanded with constituents_only turned off (FAILED - 3072)
        returns results.processed? as true (FAILED - 3073)
    cap_recipients
      caps recipients saved to conversion.recipients when cap_recipients is on (FAILED - 3074)
      multi_content turned on
        caps recipients and returns half content_one and half content_two (FAILED - 3075)
        fills out more than half content_two if content_one less than half (FAILED - 3076)
        fills out more than half content_two if content_one less than half (FAILED - 3077)
  failed calls
    should respond with an error when no conversion passed in (FAILED - 3078)
    should respond with an error when no recipient_ids_expanded passed in (FAILED - 3079)
    should respond with an error when there is no selected_recipient (FAILED - 3080)
    should respond with an error when no sender_profile passed in and should properly combine errors (FAILED - 3081)

UpdatePromotedMessage
  successful calls
    updating promoted_message columns
      updates with general params (FAILED - 3082)
      updates built_in_image (FAILED - 3083)
      with remove_built_in_image checkbox true
        removes the saved built_in_image selection (FAILED - 3084)
      handling require_address params
        with SURVEY in selected_recipient_params
          with require_address params 'zip_required'
            sets require_address to false and require_zip_only to true (FAILED - 3085)
          with require_address params 'no_address_info'
            sets require_address to false and require_zip_only to false (FAILED - 3086)
          with require_address params 'address_required'
            sets require_address to true and require_zip_only to false (FAILED - 3087)
        with no_survey in selected_recipient_params
          sets require_address to true and require_zip_only to false (FAILED - 3088)
      with multi_content true
        updates with multi_content params (FAILED - 3089)
      with multi_content false
        updates with single-content params (FAILED - 3090)
      with remove_custom_campaign_image param
        removes custom_campaign_image (FAILED - 3091)
    updating selected_recipient
      with no selected_recipient on promoted_message
        creates a selected_recipient (FAILED - 3092)
      with a selected_recipient on promoted_message
        with survey and no_survey params
          with no_survey
            if recipients_code contains 'SURVEY'
              clears recipients_code (FAILED - 3093)
            if recipients_code doesn't contain 'SURVEY'
              keeps recipients_code the same (FAILED - 3094)
          with 'SURVEY' params
            sets recipient columns as SURVEY (FAILED - 3095)
        when multi_content changes to false
          doesn't clear 'subject_two' or 'bodycachd_two' (FAILED - 3096)
        clearing recipients columns when multi_content changes
          when multi_content params differ from promoted_message multi_content
            clears the selected_recipient recipient columns (FAILED - 3097)
          when multi_content params are same as promoted_message multi_content
            does not clear the selected_recipient recipient columns (FAILED - 3098)
      handling alternate_messages
        with multi_content true params
          does note destroy alternate_messages (FAILED - 3099)
        with multi_content false params
          does not destroy alternate_messages (FAILED - 3100)
  calls that return errors
    returns an error (FAILED - 3101)

update sub account controls
  successful calls
    updates email_blast_access successfully and sets notice (FAILED - 3102)
    updates agency_state_id to state ID when ID passed and sets it to nil when that param is blank and sets notice (FAILED - 3103)
    updates agency_state_id to nil when that param is blank and sets notice (FAILED - 3104)
    responds with a notice that nothing has been updated when nothing has been updated (FAILED - 3105)
  errors
    should respond with error when no sub_account passed to a call to UpdateSubAccountControls
    should respond with error when no email_blast_access passed to a call to UpdateSubAccountControls (FAILED - 3106)

VideoHandler
  #add_video
    passes the conversion, Ziggeo video token, and video_opt_in to VideoServiceSend.make_for_conversion (FAILED - 3107)
    with a converion and recipients
      has a conversion with recipients (FAILED - 3108)
      sets in-district recipients on the VideoServiceSend (FAILED - 3109)
      doesn't set out-of-district recipients (FAILED - 3110)
      with an invalid (duplicate) VideoServiceSend
        doesn't save a new VideoServiceSend (FAILED - 3111)
      when the promoted_message's disable_email_verifications == true
        rubberstamps the conversion (FAILED - 3112)

Rake::Task
  index_twitter_deliveries
    enqueue twitter deliveries (FAILED - 3113)

Pending: (Failures listed here are expected and do not affect your suite's status)

  1) Promoter::ProfilesController Old API without SSL #profile.xml the response should not be success
     # No reason given
     Failure/Error: pending { should_not be_success }
       expected `#<ActionController::TestResponse:0x00000013df1340 @body=["<?xml version=\"1.0\" encoding=\"UTF-8\"?><... "promoter_id"=>26092, "controller"=>"promoter/profiles", "action"=>"api_public", "format"=>"xml"}>>.success?` to return false, got true
     # ./spec/controllers/api_spec.rb:1112:in `block (6 levels) in <top (required)>'
     # /usr/local/bundle/gems/webmock-3.14.0/lib/webmock/rspec.rb:37:in `block (2 levels) in <top (required)>'

  2) Promoter::UserSessionsController POST create when we log in as a PromoterUser if there isn't an associated Account creates an account
     # No reason given
     Failure/Error: expect(promoter_user.accounts).to eql([account])

       expected: [#<Double "Account_1039">]
            got: []

       (compared using eql?)

       Diff:
       @@ -1 +1 @@
       -[#<Double "Account_1039">]
       +[]

     # ./spec/controllers/promoter/user_sessions_controller_spec.rb:121:in `block (5 levels) in <top (required)>'
     # /usr/local/bundle/gems/webmock-3.14.0/lib/webmock/rspec.rb:37:in `block (2 levels) in <top (required)>'

  3) Agency any Agency when a new Subscription proceeds creates an Office Subscription record for the Agency
     # Not yet implemented
     # ./spec/features/agencies_spec.rb:858

  4) Agency any Agency when a new Subscription proceeds sets the Office usage_plan = paid
     # Not yet implemented
     # ./spec/features/agencies_spec.rb:860

  5) Agency any Agency when a new Subscription proceeds creates an Office Product record for the Agency
     # Not yet implemented
     # ./spec/features/agencies_spec.rb:862

  6) Agency any Agency when a new Subscription proceeds creates a Product record for the PromoterUser
     # Not yet implemented
     # ./spec/features/agencies_spec.rb:884

  7) Agency any Agency when a new Subscription proceeds creates a Subscription record for the PromoterUser
     # Not yet implemented
     # ./spec/features/agencies_spec.rb:892

  8) Agency any Agency when a new Subscription proceeds the Agency's Office Subscription record is stamped with the Office name/id
     # Not yet implemented
     # ./spec/features/agencies_spec.rb:866

  9) Agency any Agency when a new Subscription proceeds the Agency's Office Subscription record is discounted
     # Not yet implemented
     # ./spec/features/agencies_spec.rb:868

  10) Agency any Agency when a new Subscription proceeds the Agency's Office Subscription record resale discount at 25%?
     # Not yet implemented
     # ./spec/features/agencies_spec.rb:870

  11) Agency any Agency when a new Subscription proceeds the Agency's Office Product record is stamped with the Office name/id
     # Not yet implemented
     # ./spec/features/agencies_spec.rb:876

  12) Agency any Agency when a new Subscription proceeds the Agency's Office Product record is discounted
     # Not yet implemented
     # ./spec/features/agencies_spec.rb:878

  13) Agency any Agency when a new Subscription proceeds the Agency's Office Product record resale discount at 25%?
     # Not yet implemented
     # ./spec/features/agencies_spec.rb:880

  14) Agency any Agency when a new Subscription proceeds the PromoterUser's Product record is free
     # Not yet implemented
     # ./spec/features/agencies_spec.rb:888

  15) Agency any Agency when a new Subscription proceeds the PromoterUser's Subscription record is free
     # Not yet implemented
     # ./spec/features/agencies_spec.rb:896

  16) Agency any Agency when a subscription upgrade proceeds it updates the records
     # Not yet implemented
     # ./spec/features/agencies_spec.rb:904

  17) Agency when a sub-account contract renews if the agency still exists it renews with the agency
     # Not yet implemented
     # ./spec/features/agencies_spec.rb:1329

  18) Agency when a sub-account contract renews if the agency doesn't exist it can renew with OCP
     # Not yet implemented
     # ./spec/features/agencies_spec.rb:1335

  19) Changing Subscriptions and Plans updating plans for an Agency Office while trialing changing the plan remains on day six
     # Not yet implemented
     # ./spec/features/agencies_spec.rb:1381

  20) Changing Subscriptions and Plans updating plans for an Agency Office while trialing changing the plan preserves the demo expiration date
     # Not yet implemented
     # ./spec/features/agencies_spec.rb:1383

  21) Changing Subscriptions and Plans updating plans for an Agency Office during an active subscription when upgrading does not begin in demo mode
     # Not yet implemented
     # ./spec/features/agencies_spec.rb:1404

  22) Changing Subscriptions and Plans updating plans for an Agency Office when a subscription expires on resubscribing does not begin in demo mode
     # Not yet implemented
     # ./spec/features/agencies_spec.rb:1425

  23) Alternate message specs Deliveries Add to the end-to-end message spec?
     # Not yet implemented
     # ./spec/features/alternate_message_spec.rb:365

  24) Campaign Monitor API Service Calls buy_credits if OCP has sufficient Credits transfers Credits to the Client
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:140

  25) Campaign Monitor API API MQ Message goes to the API queue
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:1105

  26) Campaign Monitor API API MQ Message has a Resource name (e.g. Campaign)
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:1107

  27) Campaign Monitor API API MQ Message has a promoter_user_id
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:1109

  28) Campaign Monitor API API MQ Message has a CM ClientId
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:1111

  29) Campaign Monitor API API MQ Message a Campaign message includes promoter_user_id
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:1115

  30) Campaign Monitor API API MQ Message a Campaign message includes campaign monitor clientid
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:1117

  31) Campaign Monitor API API MQ Message a Campaign message includes campaign monitor campaignid
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:1119

  32) Campaign Monitor API API MQ Message a Campaign message includes campaign monitor list_id or segment_id
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:1121

  33) Campaign Monitor API API MQ Message a Campaign message includes campaign monitor lists_and_segments_serialized
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:1123

  34) Campaign Monitor API API MQ Message a Campaign message includes number of recipients
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:1125

  35) Campaign Monitor API API MQ Message a Campaign message includes scheduled delivery datetime
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:1127

  36) Campaign Monitor API API MQ Message a Campaign message includes status
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:1129

  37) Campaign Monitor API Campaign Monitor API Agent watches the api_queue
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:1141

  38) Campaign Monitor API Campaign Monitor API Agent reads API MqMessages
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:1143

  39) Campaign Monitor API Campaign Monitor API Agent processes calls to Campaign Monitor asynchronously
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:1145

  40) Campaign Monitor API Campaign Monitor API Agent processes 'Check Client' messages
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:1147

  41) Campaign Monitor API Campaign Monitor API Agent processes 'Create Client' messages
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:1149

  42) Campaign Monitor API Campaign Monitor API Agent processes 'Check OCP Credits' messages
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:1151

  43) Campaign Monitor API Campaign Monitor API Agent processes 'Buy Credits' messages
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:1153

  44) Campaign Monitor API Campaign Monitor API Agent processes 'Login/Start Client Session' messages
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:1155

  45) Campaign Monitor API Campaign Monitor API Agent processes 'Sync Listings' messages
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:1157

  46) Campaign Monitor API Campaign Monitor API Agent for any message checks the last :in_progress Transaction status
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:1161

  47) Campaign Monitor API Campaign Monitor API Agent if it gets a Buy Credits message checks the Transaction uuid stamp
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:1193

  48) Campaign Monitor API Campaign Monitor API Agent if it gets a Buy Credits message checks the Transaction status
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:1195

  49) Campaign Monitor API Campaign Monitor API Agent if it gets a Buy Credits message if the status is :ongoing if the uuid stamp doesn't match the message ignores the message
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:1201

  50) Campaign Monitor API Campaign Monitor API Agent if it gets a Buy Credits message if the status is :ongoing if the uuid stamp matches the message proceeds
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:1207

  51) Campaign Monitor API Campaign Monitor API Agent if it gets a Buy Credits message if the status is :failed proceeds
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:1215

  52) Campaign Monitor API Campaign Monitor 1.0 Asynchronous transactions for any creative/destructive action searches for an in_progress record of the same action and promoter
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:1302

  53) Campaign Monitor API Campaign Monitor 1.0 Asynchronous transactions for any creative/destructive action if we're within the wait_threshold for this action does not start a new one
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:1306

  54) Campaign Monitor API Campaign Monitor 1.0 Asynchronous transactions for any creative/destructive action if we're within the wait_threshold for this action returns a link to the transaction
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:1308

  55) Campaign Monitor API Campaign Monitor 1.0 Asynchronous transactions for a non-destructive/creative inquiry into a value hits a rails cache
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:1316

  56) Campaign Monitor API Campaign Monitor 1.0 Asynchronous transactions for a non-destructive/creative inquiry into a value searches for an in_progress record of the same action and promoter
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:1318

  57) Campaign Monitor API Campaign Monitor 1.0 Asynchronous transactions for a non-destructive/creative inquiry into a value if a transaction is already in_progress if we're within the wait_threshold for this action does not start a new one
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:1324

  58) Campaign Monitor API Campaign Monitor 1.0 Asynchronous transactions for a non-destructive/creative inquiry into a value if a transaction is already in_progress if we're within the wait_threshold for this action returns a link to the transaction
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:1326

  59) Campaign Monitor API Campaign Monitor 1.0 Asynchronous transactions for a non-destructive/creative inquiry into a value if a transaction is already in_progress if we're outside the wait_threshold for this action starts a new one
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:1332

  60) Campaign Monitor API Campaign Monitor 1.0 Asynchronous transactions for a non-destructive/creative inquiry into a value if a transaction is already in_progress if we're outside the wait_threshold for this action returns a link to the transaction
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:1334

  61) Campaign Monitor API Campaign Monitor 1.0 Asynchronous transactions Callbacks for non-destructive/creative inquiries updates cached values
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:1346

  62) Campaign Monitor API Campaign Monitor 1.0 Transaction gets a simple displayed value
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:1356

  63) Campaign Monitor API Campaign Monitor 1.0 Transaction for a count is a simple text displayed value
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:1359

  64) Campaign Monitor API Campaign Monitor 1.0 Transaction for a session is a link
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:1363

  65) Campaign Monitor API Campaign Monitor 1.0 Transaction for a redirect callback needs to substitute in its uuid
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:1371

  66) Campaign Monitor API Campaign Monitor 1.0 Transaction for a screen element div needs to substitute in its uuid
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:1375

  67) Campaign Monitor API Campaign Monitor 1.0 Promoter Controls Campaigns page the Purchase Credits modal/form if there's an ongoing API transaction for this customer doesn't show the purchase button
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:2109

  68) Campaign Monitor API Campaign Monitor 1.0 Promoter Controls Campaigns page the Purchase Credits modal/form when a Customer buys CM Credits when asynchronous if there's an ongoing API transaction for this customer doesn't re-order
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:2273

  69) Campaign Monitor API sig imports a CMSignatureBlock has a json array
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:2375

  70) Campaign Monitor API sig imports a CMSignatureBlock uses a track :array to collect the string
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:2381

  71) Campaign Monitor API sig imports a CMSignatureBlock includes a counter that stops before 1k
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:2382

  72) Campaign Monitor API sig imports a CMSignatureBlock has a single message / topic
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:2384

  73) Campaign Monitor API sig imports a CMSignatureBlock has the Transaction uuid
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:2385

  74) Campaign Monitor API sig imports a CMSignatureBlock the array has less than 1k sigs
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:2378

  75) Campaign Monitor API Campaign Monitor 1.1 shows a new Email Campaign form
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:2470

  76) Campaign Monitor API Campaign Monitor 1.1 Campaign Monitor API Agent processes 'Create/Send Campaign' messages
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:2424

  77) Campaign Monitor API Campaign Monitor 1.1 Campaign Monitor API Agent processes Pull listings messages for text messages
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:2426

  78) Campaign Monitor API Campaign Monitor 1.1 if the customer is an Office doesn't show the purchase credits form
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:2432

  79) Campaign Monitor API Campaign Monitor 1.1 if the customer is an Office recommends they contact their Agency
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:2434

  80) Campaign Monitor API Campaign Monitor 1.1 if the customer is an Agency shows the purchase credits form
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:2440

  81) Campaign Monitor API Campaign Monitor 1.1 if the customer is an Agency stores Agency Credits in a pool
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:2442

  82) Campaign Monitor API Campaign Monitor 1.1 if the customer is an Agency allows assigning Credits from pool to Offices
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:2444

  83) Campaign Monitor API Campaign Monitor 1.1 if the customer is an Agency allows removing Credits from Offices to pool
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:2446

  84) Campaign Monitor API Campaign Monitor 1.1 when a Customer purchases Pro tier when the Stripe charge processes gives them free CM Credits for Pro tier
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:2454

  85) Campaign Monitor API Campaign Monitor 1.1 when a Customer purchases Enterprise tier when the Stripe charge processes gives them free CM Credits for Enterprise tier
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:2464

  86) Campaign Monitor API Campaign Monitor 1.1 the new Email Campaign form takes a Campaign name
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:2474

  87) Campaign Monitor API Campaign Monitor 1.1 the new Email Campaign form takes a Campaign from email
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:2476

  88) Campaign Monitor API Campaign Monitor 1.1 the new Email Campaign form takes a Campaign subject
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:2478

  89) Campaign Monitor API Campaign Monitor 1.1 the new Email Campaign form takes a Campaign body
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:2480

  90) Campaign Monitor API Campaign Monitor 1.1 the new Email Campaign form takes a scheduled delivery datetime
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:2482

  91) Campaign Monitor API Campaign Monitor 1.1 the new Email Campaign form takes a recipients CSV
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:2484

  92) Campaign Monitor API Campaign Monitor 1.1 the new Email Campaign form if the CSV format isn't valid shows an error message
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:2488

  93) Campaign Monitor API Campaign Monitor 1.1 the new Email Campaign form if the CSV format isn't valid doesn't record the Campaign
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:2490

  94) Campaign Monitor API Campaign Monitor 1.1 the new Email Campaign form if the CSV format isn't valid doesn't deliver the Campaign to CampaignMonitor
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:2492

  95) Campaign Monitor API Campaign Monitor 1.1 the new Email Campaign form if the recipients count exceeds our Credits shows an error message
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:2498

  96) Campaign Monitor API Campaign Monitor 1.1 the new Email Campaign form if the recipients count exceeds our Credits doesn't record the Campaign
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:2500

  97) Campaign Monitor API Campaign Monitor 1.1 the new Email Campaign form if the recipients count exceeds our Credits doesn't deliver the Campaign to CampaignMonitor
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:2502

  98) Campaign Monitor API Campaign Monitor 1.1 the new Email Campaign form if the CSV is valid and we have sufficient Credits records the Campaign
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:2508

  99) Campaign Monitor API Campaign Monitor 1.1 the new Email Campaign form if the CSV is valid and we have sufficient Credits delivers the Campaign to CampaignMonitor
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:2510

  100) Campaign Monitor API Campaign Monitor 1.1 the new Email Campaign form if the CSV is valid and we have sufficient Credits refreshes our Credit count
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:2512

  101) Campaign Monitor API Email Campaigns Page with a finished Email Campaign shows the Campaign totals
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:2524

  102) Campaign Monitor API Email Campaigns Page with a it Email Campaign shows the Campaign delivery date
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:2530

  103) Campaign Monitor API Agent if it gets a new Campaign message delivers the Campaign to Campaign Monitor
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:2546

  104) Campaign Monitor API Agent if it gets a new Campaign message if the Campaign has > 1000 recipients breaks the transfer into 1000-record chunks for processing
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:2542

  105) Campaign Monitor API Agent if it gets a new Campaign message on 200/201/204 HTTP Success updates the Campaign record
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:2550

  106) Campaign Monitor API Agent if it gets a new Campaign message on HTTP Failure updates the Campaign record
     # Not yet implemented
     # ./spec/features/campaign_monitor_spec.rb:2556

  107) Check Activation a Promoter behaves like activation via check payment with a Check payment within 10 days of expiration shows the payment date
     # Not yet implemented
     # ./spec/spec_check_helper.rb:43

  108) Check Activation a Promoter behaves like activation via check payment with a Check payment within 10 days of expiration shows the amount due
     # Not yet implemented
     # ./spec/spec_check_helper.rb:45

  109) Check Activation an Alias / Proxy behaves like activation via check payment with a Check payment within 10 days of expiration shows the payment date
     # Not yet implemented
     # ./spec/spec_check_helper.rb:43

  110) Check Activation an Alias / Proxy behaves like activation via check payment with a Check payment within 10 days of expiration shows the amount due
     # Not yet implemented
     # ./spec/spec_check_helper.rb:45

  111) Our Contact Us form with standard Contact Us settings when we visit via the modal it should be tailored to the modal
     # Not yet implemented
     # ./spec/features/contact_us_spec.rb:65

  112) ProxyPromoterUser the reset password page if we enter a Proxy email doesn't send a reset email
     # Not yet implemented
     # ./spec/features/coworkers_spec.rb:22

  113) ProxyPromoterUser the reset password page if we enter a Proxy email shows a message explaining that proxies are not allowed to purchase
     # Not yet implemented
     # ./spec/features/coworkers_spec.rb:24

  114) ProxyPromoterUser the dashboard for a 'pro' Promoter's Proxy doesn't allow purchases / new plan upgrades
     # Not yet implemented
     # ./spec/features/coworkers_spec.rb:237

  115) PromotedMessage #update_custom_fields() takes a hash of options
     # Not yet implemented
     # ./spec/features/custom_fields_spec.rb:35

  116) PromotedMessage #update_custom_fields() doesn't create an openstruct directly
     # Not yet implemented
     # ./spec/features/custom_fields_spec.rb:36

  117) PromotedMessage #update_custom_fields() validates lengths before creating openstruct?
     # Not yet implemented
     # ./spec/features/custom_fields_spec.rb:37

  118) Widgets Fluid widget behaves like a widget with custom fields with custom Town with select values 'Thule','Ys' if not required doesn't include javascript validation
     # Not yet implemented
     # ./spec/features/custom_fields_spec.rb:316

  119) Widgets Fluid widget behaves like a widget with custom fields with custom Town with select values 'Thule','Ys' if required includes javascript validation
     # Not yet implemented
     # ./spec/features/custom_fields_spec.rb:344

  120) Widgets Fluid widget behaves like a widget with custom fields with custom Town without select values if not required? doesn't include javascript validation
     # Not yet implemented
     # ./spec/features/custom_fields_spec.rb:398

  121) Widgets Fluid widget behaves like a widget with custom fields with custom Town without select values if required? includes javascript validation
     # Not yet implemented
     # ./spec/features/custom_fields_spec.rb:458

  122) Widgets Mobile widget behaves like a widget with custom fields with custom Town with select values 'Thule','Ys' if not required doesn't include javascript validation
     # Not yet implemented
     # ./spec/features/custom_fields_spec.rb:316

  123) Widgets Mobile widget behaves like a widget with custom fields with custom Town with select values 'Thule','Ys' if required includes javascript validation
     # Not yet implemented
     # ./spec/features/custom_fields_spec.rb:344

  124) Widgets Mobile widget behaves like a widget with custom fields with custom Town without select values if not required? doesn't include javascript validation
     # Not yet implemented
     # ./spec/features/custom_fields_spec.rb:398

  125) Widgets Mobile widget behaves like a widget with custom fields with custom Town without select values if required? includes javascript validation
     # Not yet implemented
     # ./spec/features/custom_fields_spec.rb:458

  126) Fastly caching the Oneclick/All-in-one widget via the Fastly domain/subdomain version 2.0 with the ?onesig parameter Fastly service / Varnish attempts to strip the onesig parameter out and use a header
     # Not yet implemented
     # ./spec/features/fastly_spec.rb:76

  127) Fastly caching the Oneclick/All-in-one widget via the Fastly domain/subdomain version 2.0 with the ?onesig parameter Fastly service / Varnish returns the cached widget without params, but supplies the header
     # Not yet implemented
     # ./spec/features/fastly_spec.rb:79

  128) Fastly caching the Fluid widget via the Fastly domain/subdomain version 2.0 with the ?onesig parameter Fastly service / Varnish attempts to strip the onesig parameter out and use a header
     # Not yet implemented
     # ./spec/features/fastly_spec.rb:211

  129) Fastly caching the Fluid widget via the Fastly domain/subdomain version 2.0 with the ?onesig parameter Fastly service / Varnish returns the cached widget without params, but supplies the header
     # Not yet implemented
     # ./spec/features/fastly_spec.rb:214

  130) Fastly caching Live testing if we visit the widget while logged in with an OCP session Fastly/Varnish doesn't cache or record session values
       # No reason given
       Failure/Error: return false

       LocalJumpError:
         unexpected return
       # ./spec/features/fastly_spec.rb:271:in `block (5 levels) in <top (required)>'
       # /usr/local/bundle/gems/webmock-3.14.0/lib/webmock/rspec.rb:37:in `block (2 levels) in <top (required)>'

  131) Fastly caching Live testing the oneclick widget allows Facebook posts
       # No reason given
       Failure/Error: return false

       LocalJumpError:
         unexpected return
       # ./spec/features/fastly_spec.rb:281:in `block (4 levels) in <top (required)>'
       # /usr/local/bundle/gems/webmock-3.14.0/lib/webmock/rspec.rb:37:in `block (2 levels) in <top (required)>'

  132) Fastly caching Live testing the oneclick widget allows Twitter posts
       # No reason given
       Failure/Error: return false

       LocalJumpError:
         unexpected return
       # ./spec/features/fastly_spec.rb:285:in `block (4 levels) in <top (required)>'
       # /usr/local/bundle/gems/webmock-3.14.0/lib/webmock/rspec.rb:37:in `block (2 levels) in <top (required)>'

  133) Fastly caching Live testing the oneclick widget allows Twilio posts
       # No reason given
       Failure/Error: return false

       LocalJumpError:
         unexpected return
       # ./spec/features/fastly_spec.rb:289:in `block (4 levels) in <top (required)>'
       # /usr/local/bundle/gems/webmock-3.14.0/lib/webmock/rspec.rb:37:in `block (2 levels) in <top (required)>'

  134) Fastly caching Live testing the fluid widget allows 'Facebook sign'
       # No reason given
       Failure/Error: return false

       LocalJumpError:
         unexpected return
       # ./spec/features/fastly_spec.rb:297:in `block (4 levels) in <top (required)>'
       # /usr/local/bundle/gems/webmock-3.14.0/lib/webmock/rspec.rb:37:in `block (2 levels) in <top (required)>'

  135) The Lamar Alexander form finds the topic
       # No reason given
       Failure/Error: current_email.click_link "register"

       Capybara::ElementNotFound:
         Unable to find visible link "register"
       # /usr/local/bundle/gems/capybara-2.18.0/lib/capybara/node/finders.rb:314:in `block in synced_resolve'
       # /usr/local/bundle/gems/capybara-2.18.0/lib/capybara/node/base.rb:85:in `synchronize'
       # /usr/local/bundle/gems/capybara-2.18.0/lib/capybara/node/finders.rb:302:in `synced_resolve'
       # /usr/local/bundle/gems/capybara-2.18.0/lib/capybara/node/finders.rb:37:in `find'
       # /usr/local/bundle/gems/capybara-2.18.0/lib/capybara/node/actions.rb:43:in `click_link'
       # ./spec/features/form_fields_spec.rb:24:in `block (2 levels) in <top (required)>'
       # /usr/local/bundle/gems/webmock-3.14.0/lib/webmock/rspec.rb:37:in `block (2 levels) in <top (required)>'

  136) Customer Creation when a promoter is logged in shouldn't show the creation page
     # Not yet implemented
     # ./spec/features/new_customer_spec.rb:5

  137) New Sales Spec v2 when the new_sales global is ON accepting an agency SaleOffer admins after creating and setting the prospective Product if the promoter has a login email auto-sends an email with l/p
     # Not yet implemented
     # ./spec/features/new_sales_spec.rb:600

  138) Calls controller check Status (by Call SID / CallSid) (called from browser/widget) checks the Call's Status
     # Not yet implemented
     # ./spec/features/patch_calling_spec.rb:1968

  139) Calls controller check Status (by Call SID / CallSid) (called from browser/widget) checks any notes/data to be read for this part of the ongoing Call
     # Not yet implemented
     # ./spec/features/patch_calling_spec.rb:1970

  140) Calls controller when the Call data changes calls and updates javascript
     # Not yet implemented
     # ./spec/features/patch_calling_spec.rb:1996

  141) promoter user create a subscription selecting type standard
       # No reason given
       Failure/Error: fill_in "promoter_user_session_email", :with => promoter_user.email

       Capybara::ElementNotFound:
         Unable to find visible field "promoter_user_session_email" that is not disabled
       # /usr/local/bundle/gems/capybara-2.18.0/lib/capybara/node/finders.rb:314:in `block in synced_resolve'
       # /usr/local/bundle/gems/capybara-2.18.0/lib/capybara/node/base.rb:85:in `synchronize'
       # /usr/local/bundle/gems/capybara-2.18.0/lib/capybara/node/finders.rb:302:in `synced_resolve'
       # /usr/local/bundle/gems/capybara-2.18.0/lib/capybara/node/finders.rb:37:in `find'
       # /usr/local/bundle/gems/capybara-2.18.0/lib/capybara/node/actions.rb:92:in `fill_in'
       # /usr/local/bundle/gems/capybara-2.18.0/lib/capybara/session.rb:808:in `block (2 levels) in <class:Session>'
       # /usr/local/bundle/gems/capybara-2.18.0/lib/capybara/dsl.rb:50:in `block (2 levels) in <module:DSL>'
       # ./spec/features/product_subscription_type_spec.rb:13:in `block (3 levels) in <top (required)>'
       # /usr/local/bundle/gems/webmock-3.14.0/lib/webmock/rspec.rb:37:in `block (2 levels) in <top (required)>'

  142) promoter user create a subscription selecting type pro
       # No reason given
       Failure/Error: fill_in "promoter_user_session_email", :with => promoter_user.email

       Capybara::ElementNotFound:
         Unable to find visible field "promoter_user_session_email" that is not disabled
       # /usr/local/bundle/gems/capybara-2.18.0/lib/capybara/node/finders.rb:314:in `block in synced_resolve'
       # /usr/local/bundle/gems/capybara-2.18.0/lib/capybara/node/base.rb:85:in `synchronize'
       # /usr/local/bundle/gems/capybara-2.18.0/lib/capybara/node/finders.rb:302:in `synced_resolve'
       # /usr/local/bundle/gems/capybara-2.18.0/lib/capybara/node/finders.rb:37:in `find'
       # /usr/local/bundle/gems/capybara-2.18.0/lib/capybara/node/actions.rb:92:in `fill_in'
       # /usr/local/bundle/gems/capybara-2.18.0/lib/capybara/session.rb:808:in `block (2 levels) in <class:Session>'
       # /usr/local/bundle/gems/capybara-2.18.0/lib/capybara/dsl.rb:50:in `block (2 levels) in <module:DSL>'
       # ./spec/features/product_subscription_type_spec.rb:13:in `block (3 levels) in <top (required)>'
       # /usr/local/bundle/gems/webmock-3.14.0/lib/webmock/rspec.rb:37:in `block (2 levels) in <top (required)>'

  143) promoter user create a subscription selecting type enterprise
       # No reason given
       Failure/Error: fill_in "promoter_user_session_email", :with => promoter_user.email

       Capybara::ElementNotFound:
         Unable to find visible field "promoter_user_session_email" that is not disabled
       # /usr/local/bundle/gems/capybara-2.18.0/lib/capybara/node/finders.rb:314:in `block in synced_resolve'
       # /usr/local/bundle/gems/capybara-2.18.0/lib/capybara/node/base.rb:85:in `synchronize'
       # /usr/local/bundle/gems/capybara-2.18.0/lib/capybara/node/finders.rb:302:in `synced_resolve'
       # /usr/local/bundle/gems/capybara-2.18.0/lib/capybara/node/finders.rb:37:in `find'
       # /usr/local/bundle/gems/capybara-2.18.0/lib/capybara/node/actions.rb:92:in `fill_in'
       # /usr/local/bundle/gems/capybara-2.18.0/lib/capybara/session.rb:808:in `block (2 levels) in <class:Session>'
       # /usr/local/bundle/gems/capybara-2.18.0/lib/capybara/dsl.rb:50:in `block (2 levels) in <module:DSL>'
       # ./spec/features/product_subscription_type_spec.rb:13:in `block (3 levels) in <top (required)>'
       # /usr/local/bundle/gems/webmock-3.14.0/lib/webmock/rspec.rb:37:in `block (2 levels) in <top (required)>'

  144) promoter user create a subscription selecting type free
       # No reason given
       Failure/Error: fill_in "promoter_user_session_email", :with => promoter_user.email

       Capybara::ElementNotFound:
         Unable to find visible field "promoter_user_session_email" that is not disabled
       # /usr/local/bundle/gems/capybara-2.18.0/lib/capybara/node/finders.rb:314:in `block in synced_resolve'
       # /usr/local/bundle/gems/capybara-2.18.0/lib/capybara/node/base.rb:85:in `synchronize'
       # /usr/local/bundle/gems/capybara-2.18.0/lib/capybara/node/finders.rb:302:in `synced_resolve'
       # /usr/local/bundle/gems/capybara-2.18.0/lib/capybara/node/finders.rb:37:in `find'
       # /usr/local/bundle/gems/capybara-2.18.0/lib/capybara/node/actions.rb:92:in `fill_in'
       # /usr/local/bundle/gems/capybara-2.18.0/lib/capybara/session.rb:808:in `block (2 levels) in <class:Session>'
       # /usr/local/bundle/gems/capybara-2.18.0/lib/capybara/dsl.rb:50:in `block (2 levels) in <module:DSL>'
       # ./spec/features/product_subscription_type_spec.rb:13:in `block (3 levels) in <top (required)>'
       # /usr/local/bundle/gems/webmock-3.14.0/lib/webmock/rspec.rb:37:in `block (2 levels) in <top (required)>'

  145) Public-facing Profile send completion bars should be accurate
     # Not yet implemented
     # ./spec/features/promoter_profile_spec.rb:225

  146) Public-facing Profile send numbers should be accurate
     # Not yet implemented
     # ./spec/features/promoter_profile_spec.rb:226

  147) Public-facing Profile a more-supporters subpage
     # Not yet implemented
     # ./spec/features/promoter_profile_spec.rb:229

  148) Public-facing Profile unassociated messages when users upvote doesn't link to their profile pages
     # Not yet implemented
     # ./spec/features/promoter_profile_spec.rb:181

  149) Promoted Messages as a Promoter shows accurate goal and send progress
       # No reason given
       Failure/Error: find("#progress_bar_#{@active_message.id}")['data-reached'].to_i.should equal 100

       Capybara::ElementNotFound:
         Unable to find visible css "#progress_bar_24167"
       # /usr/local/bundle/gems/capybara-2.18.0/lib/capybara/node/finders.rb:314:in `block in synced_resolve'
       # /usr/local/bundle/gems/capybara-2.18.0/lib/capybara/node/base.rb:85:in `synchronize'
       # /usr/local/bundle/gems/capybara-2.18.0/lib/capybara/node/finders.rb:302:in `synced_resolve'
       # /usr/local/bundle/gems/capybara-2.18.0/lib/capybara/node/finders.rb:37:in `find'
       # /usr/local/bundle/gems/capybara-2.18.0/lib/capybara/session.rb:808:in `block (2 levels) in <class:Session>'
       # /usr/local/bundle/gems/capybara-2.18.0/lib/capybara/dsl.rb:50:in `block (2 levels) in <module:DSL>'
       # ./spec/features/promoters_send_totals_spec.rb:24:in `block (3 levels) in <top (required)>'
       # /usr/local/bundle/gems/webmock-3.14.0/lib/webmock/rspec.rb:37:in `block (2 levels) in <top (required)>'

  150) End-to-end tests The always-fail form import the house of reps and do a test send
     # Not yet implemented
     # ./spec/features/rabbitmq_deliveries/end_to_end_messaging_spec.rb:569

  151) End-to-end tests The always-fail form we want to enter best-fit values into dropdowns without good matches; in general
     # Not yet implemented
     # ./spec/features/rabbitmq_deliveries/end_to_end_messaging_spec.rb:571

  152) End-to-end tests The always-fail form always provide a default value for mr/mrs sig fields
     # Not yet implemented
     # ./spec/features/rabbitmq_deliveries/end_to_end_messaging_spec.rb:579

  153) End-to-end tests The always-fail form make sure we don't lose topic information
     # Not yet implemented
     # ./spec/features/rabbitmq_deliveries/end_to_end_messaging_spec.rb:581

  154) End-to-end tests The always-fail form we need to scan and interact with radio buttons
     # Not yet implemented
     # ./spec/features/rabbitmq_deliveries/end_to_end_messaging_spec.rb:583

  155) End-to-end tests End-to-end test with the allow_responses flag when we don't check the box on the widget for constituents it passes through an intermediary/one-time address to the form
     # Not yet implemented
     # ./spec/features/rabbitmq_deliveries/end_to_end_messaging_spec.rb:1464

  156) End-to-end tests End-to-end test with the allow_responses flag when we don't check the box on the widget for non-constituents it passes through an intermediary/one-time address to the form
     # Not yet implemented
     # ./spec/features/rabbitmq_deliveries/end_to_end_messaging_spec.rb:1467

  157) The promoted/recommended messages list when I land on the front page via a short link recommends messages with the same tags
       # No reason given
       Failure/Error: @promoted_message.message.tag "libertarian"

       NoMethodError:
         undefined method `tag' for nil:NilClass
       # ./spec/features/recommended_messages_spec.rb:18:in `block (3 levels) in <top (required)>'
       # /usr/local/bundle/gems/webmock-3.14.0/lib/webmock/rspec.rb:37:in `block (2 levels) in <top (required)>'

  158) A custom recipient for an Admin will set to National constituency
       # No reason given
       Failure/Error: page.should have_select('custom_recipient_constituency', :selected => "National")
         expected #has_select?("custom_recipient_constituency", {:selected=>"National", :session_options=>#<Capybara::ReadOnlySessionConfig(#<Capybara::SessionConfig...e_aria_label=false, @save_path=#<Pathname:/ocp/tmp/capybara>, @app_host="http://www.example.com">)>}) to return true, got false
       # ./spec/features/widget_setup/custom_recipients_spec.rb:384:in `block (3 levels) in <top (required)>'
       # /usr/local/bundle/gems/webmock-3.14.0/lib/webmock/rspec.rb:37:in `block (2 levels) in <top (required)>'

  159) SenderProfile when it's flagged as canadian validates canadian postal codes
     # Not yet implemented
     # ./spec/features/widget_signing/international_spec.rb:67

  160) SenderProfile when it's flagged as canadian it maps postal codes to canadian provinces
     # Not yet implemented
     # ./spec/features/widget_signing/international_spec.rb:69

  161) SenderProfile when it's flagged as canadian validates canadian postal codes
     # Not yet implemented
     # ./spec/features/widget_signing/international_spec.rb:161

  162) SenderProfile when it's flagged as canadian it maps postal codes to canadian provinces
     # Not yet implemented
     # ./spec/features/widget_signing/international_spec.rb:163

  163) Cicero US Imports Importing US Recipient Importer for US Reps behaves like an Address and field updater importing when we support Facebook addresses
       # No reason given
       Failure/Error: before { FactoryGirl.create(:nancy_pelosi, :district => FactoryGirl.create(:california_first_congressional_district, :us_code => 'existing_district_us_code')) }

       ActiveRecord::StatementInvalid:
         PG::UndefinedTable: ERROR:  relation "districts" does not exist
         LINE 1: INSERT INTO "districts" ("au_code", "canada_code", "city_nam...
                             ^
         : INSERT INTO "districts" ("au_code", "canada_code", "city_names", "created_at", "fips_code", "knowwho_code", "name", "state_fips_code", "state_id", "the_geom", "type", "uk_code", "updated_at", "us_code") VALUES ($1, $2, $3, $4, $5, $6, $7, $8, $9, $10, $11, $12, $13, $14) RETURNING "id"
       Shared Example Group: "an Address and field updater" called from ./spec/libs/importer_modules/cicero_us_import_spec.rb:1490
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/postgresql_adapter.rb:1208:in `prepare'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/postgresql_adapter.rb:1208:in `prepare_statement'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/postgresql_adapter.rb:1168:in `exec_cache'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/postgresql_adapter.rb:661:in `block in exec_query'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/abstract_adapter.rb:280:in `block in log'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/notifications/instrumenter.rb:20:in `instrument'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/abstract_adapter.rb:275:in `log'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/postgresql_adapter.rb:659:in `exec_query'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/abstract/database_statements.rb:63:in `exec_insert'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/abstract/database_statements.rb:90:in `insert'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/abstract/query_cache.rb:14:in `insert'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/relation.rb:66:in `insert'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/persistence.rb:367:in `create'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/timestamp.rb:58:in `create'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/callbacks.rb:268:in `block in create'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/callbacks.rb:403:in `_run__1019859359742492107__create__2403631530340339960__callbacks'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/callbacks.rb:405:in `__run_callback'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/callbacks.rb:385:in `_run_create_callbacks'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/callbacks.rb:81:in `run_callbacks'
       # /usr/local/bundle/gems/bugsnag-6.22.1/lib/bugsnag/integrations/rails/active_record_rescue.rb:25:in `run_callbacks'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/callbacks.rb:268:in `create'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/persistence.rb:348:in `create_or_update'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/callbacks.rb:264:in `block in create_or_update'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/callbacks.rb:425:in `_run__1019859359742492107__save__2403631530340339960__callbacks'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/callbacks.rb:405:in `__run_callback'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/callbacks.rb:385:in `_run_save_callbacks'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/callbacks.rb:81:in `run_callbacks'
       # /usr/local/bundle/gems/bugsnag-6.22.1/lib/bugsnag/integrations/rails/active_record_rescue.rb:25:in `run_callbacks'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/callbacks.rb:264:in `create_or_update'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/persistence.rb:104:in `save!'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/validations.rb:56:in `save!'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/attribute_methods/dirty.rb:33:in `save!'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/transactions.rb:264:in `block in save!'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/transactions.rb:313:in `block in with_transaction_returning_status'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/abstract/database_statements.rb:192:in `transaction'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/transactions.rb:208:in `transaction'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/transactions.rb:311:in `with_transaction_returning_status'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/transactions.rb:264:in `save!'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/configuration.rb:18:in `block in initialize'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/evaluation.rb:15:in `[]'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/evaluation.rb:15:in `create'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/strategy/create.rb:12:in `block in result'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/strategy/create.rb:9:in `tap'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/strategy/create.rb:9:in `result'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/factory.rb:42:in `run'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/factory_runner.rb:23:in `block in run'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/notifications.rb:125:in `instrument'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/factory_runner.rb:22:in `run'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/strategy_syntax_method_registrar.rb:19:in `block in define_singular_strategy_method'
       # ./spec/libs/importer_modules/cicero_us_import_spec.rb:1484:in `block (5 levels) in <top (required)>'
       # /usr/local/bundle/gems/webmock-3.14.0/lib/webmock/rspec.rb:37:in `block (2 levels) in <top (required)>'
       # ------------------
       # --- Caused by: ---
       # PG::UndefinedTable:
       #   ERROR:  relation "districts" does not exist
       #   LINE 1: INSERT INTO "districts" ("au_code", "canada_code", "city_nam...
       #                       ^
       #   /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/postgresql_adapter.rb:1208:in `prepare'

  164) Cicero US Imports Importing US Recipient Importer for US Senators behaves like an Address and field updater importing when we support Facebook addresses
       # No reason given
       Failure/Error: FactoryGirl.create(:recipient_party, :recipient => x, :party => FactoryDefaults::DEMOCRATIC )

       ActiveRecord::StatementInvalid:
         PG::UndefinedColumn: ERROR:  column "bioguide_id" of relation "recipients" does not exist
         LINE 1: ...RT INTO "recipients" ("account_id", "active_flg", "bioguide_...
                                                                      ^
         : INSERT INTO "recipients" ("account_id", "active_flg", "bioguide_id", "can_receive_flg", "cicero_code", "cicero_committee_id", "cicero_official_id", "constituency", "country", "created_at", "custom_position", "custom_salutation", "description", "display_rules", "district_id", "external_id", "fec_id", "first_name", "full_photo_url", "gender", "grouping_name", "inactive_at", "knowwho_code", "knowwho_comid", "last_name", "lock_version", "middle_name", "model_type", "name", "office_id", "order_num", "parent_votesmart_id", "party_id", "photo_path", "prefix", "scwc_office_code", "site_url", "state", "suffix", "title", "updated_at", "use_web_form_api", "votesmart_id") VALUES ($1, $2, $3, $4, $5, $6, $7, $8, $9, $10, $11, $12, $13, $14, $15, $16, $17, $18, $19, $20, $21, $22, $23, $24, $25, $26, $27, $28, $29, $30, $31, $32, $33, $34, $35, $36, $37, $38, $39, $40, $41, $42, $43) RETURNING "id"
       Shared Example Group: "an Address and field updater" called from ./spec/libs/importer_modules/cicero_us_import_spec.rb:1503
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/postgresql_adapter.rb:1208:in `prepare'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/postgresql_adapter.rb:1208:in `prepare_statement'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/postgresql_adapter.rb:1168:in `exec_cache'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/postgresql_adapter.rb:661:in `block in exec_query'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/abstract_adapter.rb:280:in `block in log'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/notifications/instrumenter.rb:20:in `instrument'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/abstract_adapter.rb:275:in `log'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/postgresql_adapter.rb:659:in `exec_query'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/abstract/database_statements.rb:63:in `exec_insert'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/abstract/database_statements.rb:90:in `insert'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/abstract/query_cache.rb:14:in `insert'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/relation.rb:66:in `insert'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/persistence.rb:367:in `create'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/timestamp.rb:58:in `create'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/callbacks.rb:268:in `block in create'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/callbacks.rb:403:in `_run__456384861704403418__create__2403631530340339960__callbacks'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/callbacks.rb:405:in `__run_callback'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/callbacks.rb:385:in `_run_create_callbacks'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/callbacks.rb:81:in `run_callbacks'
       # /usr/local/bundle/gems/bugsnag-6.22.1/lib/bugsnag/integrations/rails/active_record_rescue.rb:25:in `run_callbacks'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/callbacks.rb:268:in `create'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/persistence.rb:348:in `create_or_update'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/callbacks.rb:264:in `block in create_or_update'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/callbacks.rb:480:in `_run__456384861704403418__save__2403631530340339960__callbacks'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/callbacks.rb:405:in `__run_callback'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/callbacks.rb:385:in `_run_save_callbacks'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/callbacks.rb:81:in `run_callbacks'
       # /usr/local/bundle/gems/bugsnag-6.22.1/lib/bugsnag/integrations/rails/active_record_rescue.rb:25:in `run_callbacks'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/callbacks.rb:264:in `create_or_update'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/persistence.rb:84:in `save'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/validations.rb:50:in `save'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/attribute_methods/dirty.rb:22:in `save'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/transactions.rb:259:in `block (2 levels) in save'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/transactions.rb:313:in `block in with_transaction_returning_status'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/abstract/database_statements.rb:192:in `transaction'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/transactions.rb:208:in `transaction'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/transactions.rb:311:in `with_transaction_returning_status'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/transactions.rb:259:in `block in save'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/transactions.rb:270:in `rollback_active_record_state!'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/transactions.rb:258:in `save'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/autosave_association.rb:412:in `save_belongs_to_association'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/autosave_association.rb:209:in `block in add_autosave_association_callbacks'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/autosave_association.rb:161:in `instance_eval'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/autosave_association.rb:161:in `block in define_non_cyclic_method'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/callbacks.rb:418:in `_run__4144678383470711760__save__2403631530340339960__callbacks'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/callbacks.rb:405:in `__run_callback'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/callbacks.rb:385:in `_run_save_callbacks'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/callbacks.rb:81:in `run_callbacks'
       # /usr/local/bundle/gems/bugsnag-6.22.1/lib/bugsnag/integrations/rails/active_record_rescue.rb:25:in `run_callbacks'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/callbacks.rb:264:in `create_or_update'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/persistence.rb:104:in `save!'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/validations.rb:56:in `save!'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/attribute_methods/dirty.rb:33:in `save!'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/transactions.rb:264:in `block in save!'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/transactions.rb:313:in `block in with_transaction_returning_status'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/abstract/database_statements.rb:192:in `transaction'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/transactions.rb:208:in `transaction'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/transactions.rb:311:in `with_transaction_returning_status'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/transactions.rb:264:in `save!'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/configuration.rb:18:in `block in initialize'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/evaluation.rb:15:in `[]'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/evaluation.rb:15:in `create'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/strategy/create.rb:12:in `block in result'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/strategy/create.rb:9:in `tap'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/strategy/create.rb:9:in `result'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/factory.rb:42:in `run'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/factory_runner.rb:23:in `block in run'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/notifications.rb:125:in `instrument'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/factory_runner.rb:22:in `run'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/strategy_syntax_method_registrar.rb:19:in `block in define_singular_strategy_method'
       # ./spec/factories/recipient_factory.rb:100:in `block (3 levels) in <top (required)>'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/callback.rb:13:in `instance_exec'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/callback.rb:13:in `run'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/callbacks_observer.rb:11:in `block in update'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/callbacks_observer.rb:10:in `each'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/callbacks_observer.rb:10:in `update'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/evaluation.rb:20:in `notify'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/strategy/create.rb:10:in `block in result'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/strategy/create.rb:9:in `tap'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/strategy/create.rb:9:in `result'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/factory.rb:42:in `run'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/factory_runner.rb:23:in `block in run'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/notifications.rb:125:in `instrument'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/factory_runner.rb:22:in `run'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/strategy_syntax_method_registrar.rb:19:in `block in define_singular_strategy_method'
       # ./spec/libs/importer_modules/cicero_us_import_spec.rb:1497:in `block (5 levels) in <top (required)>'
       # /usr/local/bundle/gems/webmock-3.14.0/lib/webmock/rspec.rb:37:in `block (2 levels) in <top (required)>'
       # ------------------
       # --- Caused by: ---
       # PG::UndefinedColumn:
       #   ERROR:  column "bioguide_id" of relation "recipients" does not exist
       #   LINE 1: ...RT INTO "recipients" ("account_id", "active_flg", "bioguide_...
       #                                                                ^
       #   /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/postgresql_adapter.rb:1208:in `prepare'

  165) Cicero US Imports Importing US Recipient Importer for State-level Reps behaves like an Address and field updater importing when we support Facebook addresses
       # No reason given
       Failure/Error: before { FactoryGirl.create :state_rep_j_smith, :district => FactoryGirl.create(:ny_assembly_district, :us_code => 'existing_district_us_code') }

       ActiveRecord::StatementInvalid:
         PG::UndefinedTable: ERROR:  relation "districts" does not exist
         LINE 1: INSERT INTO "districts" ("au_code", "canada_code", "city_nam...
                             ^
         : INSERT INTO "districts" ("au_code", "canada_code", "city_names", "created_at", "fips_code", "knowwho_code", "name", "state_fips_code", "state_id", "the_geom", "type", "uk_code", "updated_at", "us_code") VALUES ($1, $2, $3, $4, $5, $6, $7, $8, $9, $10, $11, $12, $13, $14) RETURNING "id"
       Shared Example Group: "an Address and field updater" called from ./spec/libs/importer_modules/cicero_us_import_spec.rb:1517
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/postgresql_adapter.rb:1208:in `prepare'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/postgresql_adapter.rb:1208:in `prepare_statement'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/postgresql_adapter.rb:1168:in `exec_cache'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/postgresql_adapter.rb:661:in `block in exec_query'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/abstract_adapter.rb:280:in `block in log'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/notifications/instrumenter.rb:20:in `instrument'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/abstract_adapter.rb:275:in `log'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/postgresql_adapter.rb:659:in `exec_query'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/abstract/database_statements.rb:63:in `exec_insert'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/abstract/database_statements.rb:90:in `insert'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/abstract/query_cache.rb:14:in `insert'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/relation.rb:66:in `insert'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/persistence.rb:367:in `create'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/timestamp.rb:58:in `create'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/callbacks.rb:268:in `block in create'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/callbacks.rb:403:in `_run__3532194408769876166__create__2403631530340339960__callbacks'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/callbacks.rb:405:in `__run_callback'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/callbacks.rb:385:in `_run_create_callbacks'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/callbacks.rb:81:in `run_callbacks'
       # /usr/local/bundle/gems/bugsnag-6.22.1/lib/bugsnag/integrations/rails/active_record_rescue.rb:25:in `run_callbacks'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/callbacks.rb:268:in `create'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/persistence.rb:348:in `create_or_update'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/callbacks.rb:264:in `block in create_or_update'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/callbacks.rb:425:in `_run__3532194408769876166__save__2403631530340339960__callbacks'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/callbacks.rb:405:in `__run_callback'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/callbacks.rb:385:in `_run_save_callbacks'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/callbacks.rb:81:in `run_callbacks'
       # /usr/local/bundle/gems/bugsnag-6.22.1/lib/bugsnag/integrations/rails/active_record_rescue.rb:25:in `run_callbacks'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/callbacks.rb:264:in `create_or_update'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/persistence.rb:104:in `save!'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/validations.rb:56:in `save!'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/attribute_methods/dirty.rb:33:in `save!'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/transactions.rb:264:in `block in save!'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/transactions.rb:313:in `block in with_transaction_returning_status'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/abstract/database_statements.rb:192:in `transaction'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/transactions.rb:208:in `transaction'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/transactions.rb:311:in `with_transaction_returning_status'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/transactions.rb:264:in `save!'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/configuration.rb:18:in `block in initialize'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/evaluation.rb:15:in `[]'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/evaluation.rb:15:in `create'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/strategy/create.rb:12:in `block in result'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/strategy/create.rb:9:in `tap'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/strategy/create.rb:9:in `result'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/factory.rb:42:in `run'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/factory_runner.rb:23:in `block in run'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/notifications.rb:125:in `instrument'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/factory_runner.rb:22:in `run'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/strategy_syntax_method_registrar.rb:19:in `block in define_singular_strategy_method'
       # ./spec/libs/importer_modules/cicero_us_import_spec.rb:1510:in `block (5 levels) in <top (required)>'
       # /usr/local/bundle/gems/webmock-3.14.0/lib/webmock/rspec.rb:37:in `block (2 levels) in <top (required)>'
       # ------------------
       # --- Caused by: ---
       # PG::UndefinedTable:
       #   ERROR:  relation "districts" does not exist
       #   LINE 1: INSERT INTO "districts" ("au_code", "canada_code", "city_nam...
       #                       ^
       #   /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/postgresql_adapter.rb:1208:in `prepare'

  166) Cicero US Imports Importing US Recipient Importer for State-level Senators behaves like an Address and field updater importing when we support Facebook addresses
       # No reason given
       Failure/Error: before { FactoryGirl.create :state_sen_jason_lewis, :district => FactoryGirl.create(:massachusetts_state_senate_district, :us_code => 'existing_district_us_code') }

       ActiveRecord::StatementInvalid:
         PG::UndefinedTable: ERROR:  relation "districts" does not exist
         LINE 1: INSERT INTO "districts" ("au_code", "canada_code", "city_nam...
                             ^
         : INSERT INTO "districts" ("au_code", "canada_code", "city_names", "created_at", "fips_code", "knowwho_code", "name", "state_fips_code", "state_id", "the_geom", "type", "uk_code", "updated_at", "us_code") VALUES ($1, $2, $3, $4, $5, $6, $7, $8, $9, $10, $11, $12, $13, $14) RETURNING "id"
       Shared Example Group: "an Address and field updater" called from ./spec/libs/importer_modules/cicero_us_import_spec.rb:1531
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/postgresql_adapter.rb:1208:in `prepare'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/postgresql_adapter.rb:1208:in `prepare_statement'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/postgresql_adapter.rb:1168:in `exec_cache'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/postgresql_adapter.rb:661:in `block in exec_query'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/abstract_adapter.rb:280:in `block in log'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/notifications/instrumenter.rb:20:in `instrument'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/abstract_adapter.rb:275:in `log'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/postgresql_adapter.rb:659:in `exec_query'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/abstract/database_statements.rb:63:in `exec_insert'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/abstract/database_statements.rb:90:in `insert'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/abstract/query_cache.rb:14:in `insert'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/relation.rb:66:in `insert'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/persistence.rb:367:in `create'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/timestamp.rb:58:in `create'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/callbacks.rb:268:in `block in create'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/callbacks.rb:403:in `_run__3401221240723627917__create__2403631530340339960__callbacks'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/callbacks.rb:405:in `__run_callback'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/callbacks.rb:385:in `_run_create_callbacks'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/callbacks.rb:81:in `run_callbacks'
       # /usr/local/bundle/gems/bugsnag-6.22.1/lib/bugsnag/integrations/rails/active_record_rescue.rb:25:in `run_callbacks'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/callbacks.rb:268:in `create'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/persistence.rb:348:in `create_or_update'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/callbacks.rb:264:in `block in create_or_update'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/callbacks.rb:425:in `_run__3401221240723627917__save__2403631530340339960__callbacks'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/callbacks.rb:405:in `__run_callback'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/callbacks.rb:385:in `_run_save_callbacks'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/callbacks.rb:81:in `run_callbacks'
       # /usr/local/bundle/gems/bugsnag-6.22.1/lib/bugsnag/integrations/rails/active_record_rescue.rb:25:in `run_callbacks'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/callbacks.rb:264:in `create_or_update'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/persistence.rb:104:in `save!'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/validations.rb:56:in `save!'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/attribute_methods/dirty.rb:33:in `save!'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/transactions.rb:264:in `block in save!'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/transactions.rb:313:in `block in with_transaction_returning_status'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/abstract/database_statements.rb:192:in `transaction'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/transactions.rb:208:in `transaction'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/transactions.rb:311:in `with_transaction_returning_status'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/transactions.rb:264:in `save!'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/configuration.rb:18:in `block in initialize'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/evaluation.rb:15:in `[]'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/evaluation.rb:15:in `create'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/strategy/create.rb:12:in `block in result'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/strategy/create.rb:9:in `tap'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/strategy/create.rb:9:in `result'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/factory.rb:42:in `run'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/factory_runner.rb:23:in `block in run'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/notifications.rb:125:in `instrument'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/factory_runner.rb:22:in `run'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/strategy_syntax_method_registrar.rb:19:in `block in define_singular_strategy_method'
       # ./spec/libs/importer_modules/cicero_us_import_spec.rb:1524:in `block (5 levels) in <top (required)>'
       # /usr/local/bundle/gems/webmock-3.14.0/lib/webmock/rspec.rb:37:in `block (2 levels) in <top (required)>'
       # ------------------
       # --- Caused by: ---
       # PG::UndefinedTable:
       #   ERROR:  relation "districts" does not exist
       #   LINE 1: INSERT INTO "districts" ("au_code", "canada_code", "city_nam...
       #                       ^
       #   /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/postgresql_adapter.rb:1208:in `prepare'

  167) Cicero US Imports Importing US Recipient Importer for US Governors behaves like an Address and field updater importing when we support Facebook addresses
       # No reason given
       Failure/Error: FactoryGirl.create(:recipient_party, :recipient => x, :party => FactoryDefaults::DEMOCRATIC )

       ActiveRecord::StatementInvalid:
         PG::UndefinedColumn: ERROR:  column "bioguide_id" of relation "recipients" does not exist
         LINE 1: ...RT INTO "recipients" ("account_id", "active_flg", "bioguide_...
                                                                      ^
         : INSERT INTO "recipients" ("account_id", "active_flg", "bioguide_id", "can_receive_flg", "cicero_code", "cicero_committee_id", "cicero_official_id", "constituency", "country", "created_at", "custom_position", "custom_salutation", "description", "display_rules", "district_id", "external_id", "fec_id", "first_name", "full_photo_url", "gender", "grouping_name", "inactive_at", "knowwho_code", "knowwho_comid", "last_name", "lock_version", "middle_name", "model_type", "name", "office_id", "order_num", "parent_votesmart_id", "party_id", "photo_path", "prefix", "scwc_office_code", "site_url", "state", "suffix", "title", "updated_at", "use_web_form_api", "votesmart_id") VALUES ($1, $2, $3, $4, $5, $6, $7, $8, $9, $10, $11, $12, $13, $14, $15, $16, $17, $18, $19, $20, $21, $22, $23, $24, $25, $26, $27, $28, $29, $30, $31, $32, $33, $34, $35, $36, $37, $38, $39, $40, $41, $42, $43) RETURNING "id"
       Shared Example Group: "an Address and field updater" called from ./spec/libs/importer_modules/cicero_us_import_spec.rb:1541
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/postgresql_adapter.rb:1208:in `prepare'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/postgresql_adapter.rb:1208:in `prepare_statement'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/postgresql_adapter.rb:1168:in `exec_cache'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/postgresql_adapter.rb:661:in `block in exec_query'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/abstract_adapter.rb:280:in `block in log'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/notifications/instrumenter.rb:20:in `instrument'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/abstract_adapter.rb:275:in `log'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/postgresql_adapter.rb:659:in `exec_query'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/abstract/database_statements.rb:63:in `exec_insert'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/abstract/database_statements.rb:90:in `insert'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/abstract/query_cache.rb:14:in `insert'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/relation.rb:66:in `insert'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/persistence.rb:367:in `create'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/timestamp.rb:58:in `create'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/callbacks.rb:268:in `block in create'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/callbacks.rb:403:in `_run__456384861704403418__create__2403631530340339960__callbacks'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/callbacks.rb:405:in `__run_callback'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/callbacks.rb:385:in `_run_create_callbacks'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/callbacks.rb:81:in `run_callbacks'
       # /usr/local/bundle/gems/bugsnag-6.22.1/lib/bugsnag/integrations/rails/active_record_rescue.rb:25:in `run_callbacks'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/callbacks.rb:268:in `create'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/persistence.rb:348:in `create_or_update'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/callbacks.rb:264:in `block in create_or_update'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/callbacks.rb:480:in `_run__456384861704403418__save__2403631530340339960__callbacks'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/callbacks.rb:405:in `__run_callback'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/callbacks.rb:385:in `_run_save_callbacks'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/callbacks.rb:81:in `run_callbacks'
       # /usr/local/bundle/gems/bugsnag-6.22.1/lib/bugsnag/integrations/rails/active_record_rescue.rb:25:in `run_callbacks'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/callbacks.rb:264:in `create_or_update'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/persistence.rb:84:in `save'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/validations.rb:50:in `save'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/attribute_methods/dirty.rb:22:in `save'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/transactions.rb:259:in `block (2 levels) in save'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/transactions.rb:313:in `block in with_transaction_returning_status'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/abstract/database_statements.rb:192:in `transaction'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/transactions.rb:208:in `transaction'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/transactions.rb:311:in `with_transaction_returning_status'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/transactions.rb:259:in `block in save'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/transactions.rb:270:in `rollback_active_record_state!'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/transactions.rb:258:in `save'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/autosave_association.rb:412:in `save_belongs_to_association'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/autosave_association.rb:209:in `block in add_autosave_association_callbacks'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/autosave_association.rb:161:in `instance_eval'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/autosave_association.rb:161:in `block in define_non_cyclic_method'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/callbacks.rb:418:in `_run__4144678383470711760__save__2403631530340339960__callbacks'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/callbacks.rb:405:in `__run_callback'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/callbacks.rb:385:in `_run_save_callbacks'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/callbacks.rb:81:in `run_callbacks'
       # /usr/local/bundle/gems/bugsnag-6.22.1/lib/bugsnag/integrations/rails/active_record_rescue.rb:25:in `run_callbacks'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/callbacks.rb:264:in `create_or_update'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/persistence.rb:104:in `save!'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/validations.rb:56:in `save!'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/attribute_methods/dirty.rb:33:in `save!'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/transactions.rb:264:in `block in save!'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/transactions.rb:313:in `block in with_transaction_returning_status'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/abstract/database_statements.rb:192:in `transaction'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/transactions.rb:208:in `transaction'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/transactions.rb:311:in `with_transaction_returning_status'
       # /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/transactions.rb:264:in `save!'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/configuration.rb:18:in `block in initialize'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/evaluation.rb:15:in `[]'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/evaluation.rb:15:in `create'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/strategy/create.rb:12:in `block in result'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/strategy/create.rb:9:in `tap'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/strategy/create.rb:9:in `result'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/factory.rb:42:in `run'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/factory_runner.rb:23:in `block in run'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/notifications.rb:125:in `instrument'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/factory_runner.rb:22:in `run'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/strategy_syntax_method_registrar.rb:19:in `block in define_singular_strategy_method'
       # ./spec/factories/recipient_factory.rb:574:in `block (3 levels) in <top (required)>'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/callback.rb:13:in `instance_exec'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/callback.rb:13:in `run'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/callbacks_observer.rb:11:in `block in update'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/callbacks_observer.rb:10:in `each'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/callbacks_observer.rb:10:in `update'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/evaluation.rb:20:in `notify'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/strategy/create.rb:10:in `block in result'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/strategy/create.rb:9:in `tap'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/strategy/create.rb:9:in `result'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/factory.rb:42:in `run'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/factory_runner.rb:23:in `block in run'
       # /usr/local/bundle/gems/activesupport-3.2.22.5/lib/active_support/notifications.rb:125:in `instrument'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/factory_runner.rb:22:in `run'
       # /usr/local/bundle/gems/factory_girl-3.6.2/lib/factory_girl/strategy_syntax_method_registrar.rb:19:in `block in define_singular_strategy_method'
       # ./spec/libs/importer_modules/cicero_us_import_spec.rb:1537:in `block (5 levels) in <top (required)>'
       # /usr/local/bundle/gems/webmock-3.14.0/lib/webmock/rspec.rb:37:in `block (2 levels) in <top (required)>'
       # ------------------
       # --- Caused by: ---
       # PG::UndefinedColumn:
       #   ERROR:  column "bioguide_id" of relation "recipients" does not exist
       #   LINE 1: ...RT INTO "recipients" ("account_id", "active_flg", "bioguide_...
       #                                                                ^
       #   /usr/local/bundle/gems/activerecord-3.2.22.5/lib/active_record/connection_adapters/postgresql_adapter.rb:1208:in `prepare'

  168) NeonClient End to End
       # fails on update. endpoint may be broken
       Failure/Error: expect(@client.get_custom_record('Jeff_c', record_id)['Text_Field_c']).to eq new_val

         expected: "A Second Value"
              got: "A First Value"

         (compared using ==)
       # ./spec/libs/neon_client/custom_records_spec.rb:104:in `block (3 levels) in <top (required)>'
       # /usr/local/bundle/gems/vcr-5.1.0/lib/vcr/util/variable_args_block_caller.rb:9:in `call'
       # /usr/local/bundle/gems/vcr-5.1.0/lib/vcr/util/variable_args_block_caller.rb:9:in `call_block'
       # /usr/local/bundle/gems/vcr-5.1.0/lib/vcr.rb:188:in `use_cassette'
       # ./spec/libs/neon_client/custom_records_spec.rb:90:in `block (2 levels) in <top (required)>'
       # /usr/local/bundle/gems/webmock-3.14.0/lib/webmock/rspec.rb:37:in `block (2 levels) in <top (required)>'

  169) Account validate_zip
       # No reason given
       Failure/Error:
         before :each do
           subject.stub('require_full_validation?').and_return(true)
         end

         `before` is not available from within an example (e.g. an `it` block) or from constructs that run in the scope of an example (e.g. `before`, `let`, etc). It is only available on an example group (e.g. a `describe` or `context` block).
       # ./spec/models/account_spec.rb:157:in `block (2 levels) in <top (required)>'
       # /usr/local/bundle/gems/webmock-3.14.0/lib/webmock/rspec.rb:37:in `block (2 levels) in <top (required)>'

  170) Account when :is_required_full_validation should validate zip
       # No reason given
       Got 1 failure:

       170.1) Failure/Error: subject.should_receive(:validate_zip)

                (#<Account id: nil, email: "test_email170@oneclickpolitics170.com", crypted_password: "400$8$2a$b84cdfbc073727db$e6294c112ffa73d9515b013a1...", password_salt: "bc09bMDtwTHiqe8jlFeo", persistence_token: "15f252e6081c40984db6b303781a37dc3d08650b00aed5ce002...", perishable_token: nil, login_count: 0, last_request_at: nil, last_login_at: "2022-06-07 21:09:01", current_login_at: nil, last_login_ip: nil, current_login_ip: nil, created_at: "2022-06-07 21:09:01", updated_at: nil, status: "new", quota_msg_count: 0, quota_start_time: nil, sent_messages_count: 0, facebook_uid: nil, facebook_session_key: nil, widgets: {}, roles_mask: 0, last_message_sent_at: nil, default_shared_flg: true, ignore_quotas: false, image: nil, needs_quorum_password_approval: nil>).validate_zip(*(any args))
                    expected: 1 time with any arguments
                    received: 0 times with any arguments
              # ./spec/models/account_spec.rb:150:in `block (3 levels) in <top (required)>'
              # /usr/local/bundle/gems/webmock-3.14.0/lib/webmock/rspec.rb:37:in `block (2 levels) in <top (required)>'
Killed
Tue Jun  7 23:12:25 UTC 2022
root@d42a15951b34:/ocp#  
