# mp_clickstream_events

## Glossary

**Overview:** This sheet lists the clickstream event details for Markeplace related journeys on the consigner and operator apps/website

**How to read 'Consigner App' tab:** The below table lists all the fields, their meanings and the equivalent mapping names (can be used to join with similar fields in the 'mp_analytics_core.fact_cx_events_l3m' table)
The fields 'Flow/ Feature Name', 'Describe Screen', 'Describe Action','Critical Step' are defined in this sheet to describe and classify the events and not present in any database table. The stakeholder's query should be mapped to these fields to find the right Flow/Feature name, Stages, Actions that the stakeholder is talking about.
The rest of the fields are present in the 'mp_analytics_core.fact_cx_events_l3m'  table

| Field | Description | Mapping Name |
| --- | --- | --- |
| Flow/ Feature Name | Defines the flow name or the feature name by which it is commonly addressed eg. Signup flow, Demand flow, VIP Pass feature |  |
| Describe Stage | Defines the stage within the flow where the event gets triggerred |  |
| Describe Action | Defines the user/system actions within a stage that causes the event to trigger |  |
| Critical Step | Defines whether the 'Describe Action' is a critical step or not |  |
| Event name | Defines the name of the event. | eventname |
| Event action | Defines the action type:  Click or View | event_action |
| Event Category | Defines the event category | event_category |
| Screen name | Defines the screen name. This is not same as 'Describe Screen' field. | screen_name |
| Demand ID | Defines whether demand_id is populated on the given event or not | demand_id |
| Entity id | Defines the entity | entity_id |
| Miscellaneous | Defines the extra field which can contain additional metadata related to the event | miscellaneous |
| user_code | Defines whether user_code is populated on the given event or not | user_code |

## Consigner

| Flow/ Feature Name | Describe Screen | Describe Action | Critical Step | Critical Step Details | Event Name | Event Action | Event Category | Screen Name | Demand ID | Entity id | Miscellaneous | user_code | android_version | ios_version | web_version |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Permissions | Location Permission |  | True |  | v1_location_permission | view |  | location_permission | False |  |  | True |  |  |  |
| Permissions | Location Permission | Clicks 'Location Permission' | False |  | v1_location_permission | click | bottom_nav | location_permission | False |  | allowed | True |  |  |  |
| Permissions | Notification Permission |  | True |  | v1_notification_permission | view |  | notification_permission | False |  |  | True |  |  |  |
| Permissions | Notification Permission | Clicks 'Notification Permission' | False |  | v1_notification_permission | click | bottom_nav | notification_permission | False |  | allowed | True |  |  |  |
| Login | Login - Mobile Number |  | True |  | v1_app_login | view |  | app_login | False |  |  | False |  |  |  |
| Login | Login - Mobile Number |  | False |  | v1_app_restriction | view |  | app_login | False |  | emsg | False |  |  |  |
| Login | Login - Mobile Number | Clicks 'Privacy Policy' | False |  | v1_privacy_policy | click | bottom_nav | app_login | False |  |  | False |  |  |  |
| Login | Login - Mobile Number | Clicks 'Terms & Conditions' | False |  | v1_terms_condition | click | bottom_nav | app_login | False |  |  | False |  |  |  |
| Login | Login - Mobile Number | Views 'Truecaller Login Bottomsheet' | False |  | v1_use_truecaller | view | truecaller_login_bottom_sheet | app_login | False |  |  | False |  |  |  |
| Login | Login - Mobile Number | Clicks 'Continue with Truecaller' on 'Truecaller Login Bottomsheet' | False |  | v1_use_truecaller | click | truecaller_login_bottom_sheet | app_login | False |  | phone_no | True |  |  |  |
| Login | Login - Mobile Number | Clicks 'Mobile Number' field on 'Contact Input' | False |  | v1_phone_no_input | click | contact_input | app_login | False |  |  | False |  |  |  |
| Login | Login - Mobile Number | Clicks 'New Company Account' on 'Contact Input' | True | Login - new account started | v1_new_company_acct | click | contact_input | app_login | False |  | phone_no | False |  |  |  |
| Login | Login - Mobile Number | Clicks 'Login to Existing Account' on 'Contact Input' | True | Login - existing account | v1_login_existing_acct | click | contact_input | app_login | False |  | phone_no | False |  |  |  |
| Login | Login - Mobile Number | Views 'Multiple Logins Bottomsheet' | False |  | v1_multiple_logins_bottomsheet | view | multiple_logins_bottomsheet | app_login | False |  |  | True |  |  |  |
| Login | Login - Mobile Number | Clicks 'Close' (X) on 'Multiple Logins Bottomsheet' | False |  | v1_close_btn | click | multiple_logins_bottomsheet | app_login | False |  |  | True |  |  |  |
| Login | Login - Mobile Number | Clicks 'Got it' on 'Multiple Logins Bottomsheet' | False |  | v1_got_it | click | multiple_logins_bottomsheet | app_login | False |  |  | True |  |  |  |
| Login | Login - Mobile Number | Clicks 'Get Help' on 'Multiple Logins Bottomsheet' | False |  | v1_get_help | click | multiple_logins_bottomsheet | app_login | False |  |  | True |  |  |  |
| Login | Login - OTP |  | True |  | v1_otp_screen | view |  | otp_screen | False |  |  | False |  |  |  |
| Login | Login - OTP | Clicks 'Back' arrow | False |  | v1_back_btn | click | top_nav | otp_screen | False |  |  | True |  |  |  |
| Login | Login - OTP | Clicks 'Login with Password' | False |  | v1_login_with_password | click | bottom_nav | otp_screen | False |  |  | False |  |  |  |
| Login | Login - OTP | OTP verified successfully on 'Otp Input' | True | Login successful (OTP verified) | v1_otp_sucess | click | otp_input | otp_screen | False |  | type | False |  |  |  |
| Login | Login - OTP | Clicks 'Resend OTP' on 'Otp Input' | False |  | v1_resend_btn | click | otp_input | otp_screen | False |  |  | False |  |  |  |
| Login | Login - Password |  | True |  | v1_login_via_password | view |  | login_via_password | False |  |  | False |  |  |  |
| Login | Login - Password | Clicks 'Login' button | True | Login via password | v1_login_btn | click | bottom_nav | login_via_password | False |  | phone_no | False |  |  |  |
| Login | Login - Password | Clicks 'Terms & Conditions' | False |  | v1_terms_condition | click | bottom_nav | login_via_password | False |  |  | False |  |  |  |
| Login | Login - Password | Clicks 'Privacy Policy' | False |  | v1_privacy_policy | click | bottom_nav | login_via_password | False |  |  | False |  |  |  |
| Login | Login - Password | Clicks 'Back' arrow | False |  | v1_back_btn | click | top_nav | login_via_password | False |  |  | True |  |  |  |
| Login | Login - Password | Clicks 'Mobile Number' field | False |  | v1_phone_no_input | click | top_nav | login_via_password | False |  |  | True |  |  |  |
| Login | Login - Password | Clicks 'Password' field on 'Password Input' | False |  | v1_password_input | click | password_input | login_via_password | False |  | phone_no | False |  |  |  |
| Login | Login - Password | Clicks 'Show Password' icon on 'Password Input' | False |  | v1_view_password | click | password_input | login_via_password | False |  | type | False |  |  |  |
| Signup | Promotions |  | False |  | v1_offer_signup_screen | view |  | offer_screen | False |  |  | True |  |  |  |
| Signup | Basic Details |  | True |  | v1_basic_details | view |  | sign_up_basic_details | False |  |  | True |  |  |  |
| Signup | Basic Details |  | False |  | v1_next_sign_up_basic_details | view |  | sign_up_basic_details | False |  |  | True |  |  |  |
| Signup | Basic Details | Clicks 'Name' field | False |  | v1_enter_name | click |  | sign_up_basic_details | False |  |  | True |  |  |  |
| Signup | Basic Details | Clicks 'Next' button | False |  | v1_next | click |  | sign_up_basic_details | False |  | business_category | True |  |  |  |
| Signup | Basic Details | Clicks 'Sales Representative' field | False |  | v1_enter_salesrep | click |  | sign_up_basic_details | False |  |  | True |  |  |  |
| Signup | Basic Details | Clicks 'Back' arrow | False |  | v1_back | click |  | sign_up_basic_details | False |  |  | True |  |  |  |
| Signup | Basic Details | Clicks 'Sales Representative' field | False |  | v1_sales_contact | click |  | sign_up_basic_details | False |  |  | True |  |  |  |
| Signup | Business Category |  | True |  | v1_business_category | view |  | sign_up_business_category | False |  |  | True |  |  |  |
| Signup | Business Category |  | False |  | v1_next_sign_up_business_category | view |  | sign_up_business_category | False |  |  | True |  |  |  |
| Signup | Business Category |  | False |  | v1_previous_sign_up_business_category | view |  | sign_up_business_category | False |  |  | True |  |  |  |
| Signup | Business Category | Clicks 'Next' button | False |  | v1_next | click |  | sign_up_business_category | False |  | business_category | True |  |  |  |
| Signup | Business Category | Clicks 'Back' arrow | False |  | v1_back | click |  | sign_up_business_category | False |  |  | True |  |  |  |
| Signup | Business Category | Clicks 'Previous' button | False |  | v1_previous | click |  | sign_up_business_category | False |  |  | True |  |  |  |
| Signup | Trip Potential |  | True |  | v1_expected_trip_count | view |  | sign_up_expected_trip_count | False |  |  | True |  |  |  |
| Signup | Trip Potential |  | True | Signup completed | v1_success_bottomsheet | view |  | sign_up_expected_trip_count | False |  | slug | True |  |  |  |
| Signup | Trip Potential |  | False |  | v1_submit_sign_up_expected_trip_count | view |  | sign_up_expected_trip_count | False |  |  | True |  |  |  |
| Signup | Trip Potential |  | False |  | v1_previous_sign_up_expected_trip_count | view |  | sign_up_expected_trip_count | False |  |  | True |  |  |  |
| Signup | Trip Potential | Clicks 'Submit' button | False |  | v1_submit | click |  | sign_up_expected_trip_count | False |  |  | True |  |  |  |
| Signup | Trip Potential | Clicks 'Back' arrow | False |  | v1_back | click |  | sign_up_expected_trip_count | False |  |  | True |  |  |  |
| Signup | Trip Potential | Clicks 'Previous' button | False |  | v1_previous | click |  | sign_up_expected_trip_count | False |  |  | True |  |  |  |
| Signup | Company Registration Check |  | True |  | v1_co_reg_detail | view |  | co_reg_detail | False |  |  | True |  |  |  |
| Signup | Company Registration Check | Clicks 'New Company' on 'Acct Creat' | False |  | v1_new_comp | click | acct_creat | co_reg_detail | False |  |  | True |  |  |  |
| Signup | Company Registration Check | Clicks 'Already Registered' on 'Acct Creat' | False |  | v1_already_reg | click | acct_creat | co_reg_detail | False |  |  | True |  |  |  |
| Signup | GST Details |  | True |  | v1_gst_details | view |  | gst_details | False |  |  | True |  |  |  |
| Signup | GST Details |  | False |  | v1_verify_acct_bot | view |  | gst_details | False |  |  | True |  |  |  |
| Signup | GST Details | Clicks 'Back' arrow | False |  | v1_back_btn | click | top_nav | gst_details | False |  |  | True |  |  |  |
| Signup | GST Details | Clicks 'GST Number' field on 'Gst Input' | False |  | v1_enter_gst | click | gst_input | gst_details | False |  | status | True |  |  |  |
| Signup | GST Details | Clicks 'Continue' button on 'Gst Input' | False |  | v1_continue | click | gst_input | gst_details | False |  | gst_no | True |  |  |  |
| Signup | GST Details | Clicks 'Confirm' on 'Verify Acct Bottomsheet' | False |  | v1_confirm | click | verify_acct_bottomsheet | gst_details | False |  |  | True |  |  |  |
| Home | Home (FTL/PTL Tabs) |  | True |  | v1_ftl_screen | view |  | home_screen | False |  |  | True |  |  |  |
| Home | Home (FTL/PTL Tabs) |  | False |  | v1_new_ptl_page_view | view |  | home_screen | False |  |  | True |  |  |  |
| Home | Home Page |  | True |  | v1_home_page | view |  | home_page | False |  | ntfc_status | True |  |  |  |
| Home | Home Page |  | False |  | v1_scroll | view |  | home_page | False |  | scroll_direction | True |  |  |  |
| Home | Home Page |  | False |  | v1_app_exit_info | view |  | home_page | False |  | axi, s | True |  |  |  |
| Home | Home Page | Clicks 'Explore Map' | False |  | v1_explore_map | click |  | home_page | False |  |  | True |  |  |  |
| Home | Home Page | Clicks 'Close' (X) | False |  | v1_close | click |  | home_page | False |  |  | True |  |  |  |
| Home | Home Page | Clicks 'Check Lane Prices' | False |  | v1_check_lane_prices | click |  | home_page | False |  | idx | True |  |  |  |
| Home | Home Page |  | False |  | v1_snackbar | view | bottom_nav | home_page | False |  | text | True |  |  |  |
| Home | Home Page | Clicks 'My Trips' tab | False |  | v1_my_trips | click | bottom_nav | home_page | False |  |  | True |  |  |  |
| Home | Home Page | Clicks 'Home' tab | False |  | v1_home | click | bottom_nav | home_page | False |  |  | True |  |  |  |
| Home | Home Page | Clicks 'Payment' tab | False |  | v1_payment | click | bottom_nav | home_page | False |  |  | True |  |  |  |
| Home | Home Page | Clicks 'Help' tab | False |  | v1_help | click | bottom_nav | home_page | False |  |  | True |  |  |  |
| Home | Home Page | Clicks floating 'Call Us' button | False |  | call_us | click | bottom_nav | home_page | False |  |  | True |  |  |  |
| Home | Home Page | Clicks status snackbar | False |  | v1_snackbar | click | bottom_nav | home_page | True |  | text | True |  |  |  |
| Home | Home Page | Views 'Ab Testing' | False |  | v1_start_ab_testing_flow | view | ab_testing | home_page | False |  | frs | True |  |  |  |
| Home | Home Page - KYC / GST |  | False |  | v1_get_bonus | view |  | home_page | False |  | value | True |  |  |  |
| Home | Home Page - VIP Pass / Coupon |  | False |  | v1_explore_plans | view |  | home_page | False |  |  | True |  |  |  |
| Home | Home Page - Vehicle Confirmation |  | False |  | v1_truck_on_hold | view |  | home_page | True |  |  | True |  |  |  |
| Home | Home Page - Payments / Dues |  | False |  | v1_payment_banner_view | view |  | home_page | False |  |  | True |  |  |  |
| Home | Home Page - KYC / GST |  | False |  | v1_upload_method | view |  | home_page | False |  |  | True |  |  |  |
| Home | Home Page - VIP Pass / Coupon |  | False |  | v1_view_active_pass_details | view |  | home_page | False |  | type | True |  |  |  |
| Home | Home Page - VIP Pass / Coupon |  | False |  | v1_renew_pass | view |  | home_page | False |  |  | True |  |  |  |
| Home | Home Page - KYC / GST | Clicks 'Complete Profile' | False |  | v1_complete_profile | click |  | home_page | False |  |  | True |  |  |  |
| Home | Home Page - VIP Pass / Coupon | Clicks 'Explore Plans' | False |  | v1_explore_plans | click |  | home_page | False |  |  | True |  |  |  |
| Home | Home Page - KYC / GST | Clicks 'Upload Image' | False |  | v1_upload_image | click |  | home_page | False |  |  | True |  |  |  |
| Home | Home Page - KYC / GST | Clicks 'Back' arrow | False |  | v1_back | click |  | home_page | False |  |  | True |  |  |  |
| Home | Home Page - KYC / GST | Clicks 'View Avail Balance' | False |  | v1_view_avail_balance | click |  | home_page | False |  |  | True |  |  |  |
| Home | Home Page - KYC / GST | Clicks 'Verify' | False |  | v1_verify | click |  | home_page | False |  |  | True |  |  |  |
| Home | Home Page - KYC / GST | Clicks 'Reupload' | False |  | v1_reupload | click |  | home_page | False |  |  | True |  |  |  |
| Home | Home Page - KYC / GST | Clicks 'Contact Us' | False |  | v1_contact_us | click |  | home_page | False |  |  | True |  |  |  |
| Home | Home Page - VIP Pass / Coupon | Clicks 'View Active Pass Details' | False |  | v1_view_active_pass_details | click |  | home_page | False |  |  | True |  |  |  |
| Home | Home Page - VIP Pass / Coupon | Clicks 'Renew Pass' | False |  | v1_renew_pass | click |  | home_page | False |  |  | True |  |  |  |
| Home | Home Page - Vehicle Confirmation | Clicks 'Confirm Truck' | False |  | v1_confirm_truck | click |  | home_page | False |  |  | True |  |  |  |
| Home | Home Page - Payments / Dues | Views 'Payment Plan Banner' | False |  | v1_payment_plan_banner | view | payment_plan_banner | home_page | False |  |  | True |  |  |  |
| Home | Home Page - Payments / Dues | Clicks 'Close' (X) on 'Payment Plan Banner' | False |  | v1_close_btn | click | payment_plan_banner | home_page | False |  |  | True |  |  |  |
| Home | Home Page | Clicks 'Loading Address' field on 'Add Input' | True | Booking initiated from Home | v1_loading_add | click | add_input | home_page | False |  |  | True |  |  |  |
| Home | Home Page | Clicks 'Book Truck' button on 'Add Input' | True | Booking initiated from Home | v1_book_truck | click | add_input | home_page | False |  |  | True |  |  |  |
| Home | Home Page | Clicks 'Unloading Address' field on 'Add Input' | False |  | v1_unloading_add | click | add_input | home_page | False |  |  | True |  |  |  |
| Home | Home Page - Repeat Booking | Views 'Misc Widget' | False |  | v1_repeat_widget | view | misc_widget | home_page | False |  |  | True |  |  |  |
| Home | Home Page | Views 'Misc Widget' | False |  | v1_just_check_price | view | misc_widget | home_page | False |  |  | True |  |  |  |
| Home | Home Page | Clicks 'Just Check Price' on 'Misc Widget' | False |  | v1_just_check_price | click | misc_widget | home_page | False |  |  | True |  |  |  |
| Home | Home Page - Vehicle Confirmation | Clicks 'Detail' on 'Confirm Deny Bottomsheet' | False |  | v1__detail | click | confirm_deny_btmsheet | home_page | True |  |  | True |  |  |  |
| Home | Home Page - Vehicle Confirmation | Clicks 'Accept' on 'Confirm Deny Bottomsheet' | False |  | v1_accept | click | confirm_deny_btmsheet | home_page | True |  |  | True |  |  |  |
| Home | Home Page - Vehicle Confirmation | Clicks 'Complete Detail' on 'Confirm Deny Bottomsheet' | False |  | v1_complete_detail | click | confirm_deny_btmsheet | home_page | True |  |  | True |  |  |  |
| Home | Home Page - Vehicle Confirmation | Clicks 'View Detail' on 'Confirm Deny Bottomsheet' | False |  | v1_view_detail | click | confirm_deny_btmsheet | home_page | True |  |  | True |  |  |  |
| Home | Home Page - KYC / GST | Clicks 'Upload Method' on 'Kyc Bottomsheet' | False |  | v1_upload_method | click | kyc_bottomsheet | home_page | False |  | mode | True |  |  |  |
| Home | Home Page - KYC / GST | Views 'Verifying Gst Bottomsheet' | False |  | v1_verifying_gst_bottomsheet | view | verifying_gst_bottomsheet | home_page | False |  | value | True |  |  |  |
| Home | Home Page - KYC / GST | Views 'Verifying Gst Bottomsheet' | False |  | v1_offer_activated | view | verifying_gst_bottomsheet | home_page | False |  |  | True |  |  |  |
| Home | Home Page - Payments / Dues | Views 'Delay Fee Info' | False |  | v1_fee_info | view | delay_fee_info | home_page | False |  |  | True |  |  |  |
| Home | Home Page - Payments / Dues | Clicks 'Clear Due' on 'Delay Fee Info' | False |  | v1_clear_due | click | delay_fee_info | home_page | False |  |  | True |  |  |  |
| Home | Home Page - Payments / Dues | Clicks 'Fee Icon' on 'Delay Fee Info' | False |  | v1_fee_icon | click | delay_fee_info | home_page | False |  |  | True |  |  |  |
| Home | Home Page - Repeat Booking | Clicks 'View All' on 'Repeat Demand Cards' | False |  | v1_view_all | click | repeat_demand_cards | home_page | False |  | demand_count | True |  |  |  |
| Home | Home Page - Repeat Booking | Clicks 'Re Book' on 'Repeat Demand Cards' | False |  | v1_re_book | click | repeat_demand_cards | home_page | False |  | demand_count | True |  |  |  |
| Home | Home Page | Views 'Unloading Destinations' | False |  | v1_unloading_locations | view | unloading_destinations | home_page | False |  |  | True |  |  |  |
| Home | Home Page | Clicks 'Unloading Locations' on 'Unloading Destinations' | False |  | v1_unloading_locations | click | unloading_destinations | home_page | False |  | idx | True |  |  |  |
| Home | Home Page - KYC / GST | Clicks 'Continue' button on 'Bonus Unlocked Bottomsheet' | False |  | v1_continue | click | bonus_unlocked_bottomsheet | home_page | False |  |  | True |  |  |  |
| Home | Home Page - KYC / GST | Clicks 'Link Acct' on 'Gst Info' | False |  | v1_link_acct | click | gst_info | home_page | False |  |  | True |  |  |  |
| Home | Home Page - Payments / Dues | Views 'Tds Banner' | False |  | v1_tds_banner | view | tds_banner | home_page | False |  |  | True |  |  |  |
| Home | Home Page - Payments / Dues | Clicks 'Understand' on 'Tds Banner' | False |  | v1_understand | click | tds_banner | home_page | False |  |  | True |  |  |  |
| Home | Home Page - Payments / Dues | Clicks 'Auto Settle Post Review' on 'Auto Settle Bottomsheet' | False |  | v1_auto_settle_post_review | click | auto_settle_btmsheet | home_page | False |  |  | True |  |  |  |
| Home | Explore Map |  | False |  | explore_map_view | view |  | explore_map | False |  |  | True |  |  |  |
| Home | Explore Map | Clicks 'Back' arrow | False |  | back | click |  | explore_map | False |  |  | True |  |  |  |
| Address Selection | Home Page | Clicks 'Loading Address' field on 'Add Input' | True | Booking initiated from Home | v1_loading_add | click | add_input | home_page | False |  |  | True |  |  |  |
| Address Selection | Home Page | Clicks 'Book Truck' button on 'Add Input' | True | Booking initiated from Home | v1_book_truck | click | add_input | home_page | False |  |  | True |  |  |  |
| Address Selection | Home Page | Clicks 'Unloading Address' field on 'Add Input' | False |  | v1_unloading_add | click | add_input | home_page | False |  |  | True |  |  |  |
| Address Selection | App Shortcut | Clicks 'App Shortcut' on 'D Create' | False |  | v1_app_shortcut | click | d_create | app_shortcut | False |  | user_code | True |  |  |  |
| Address Selection | Loading Address Search |  | True |  | v1_add_selection | view |  | loading_add_selection | False |  |  | True |  |  |  |
| Address Selection | Loading Address Search | Selects an address from search results | True | Loading address selected | v1_select_add | click |  | loading_add_selection | False |  | up_src | True |  |  |  |
| Address Selection | Loading Address Search | Clicks 'Use Current Location' | False |  | v1_curr_location | click |  | loading_add_selection | False |  |  | True |  |  |  |
| Address Selection | Loading Address Search | Clicks 'Back' arrow | False |  | v1_back | click |  | loading_add_selection | False |  |  | True |  |  |  |
| Address Selection | Loading Address Search | Loading address search API called | False |  | v1_from_api | api | add_input | loading_add_selection | False |  | search_str | True |  |  |  |
| Address Selection | Just Check Price - Address Search |  | False |  | v1_jcp_add_selection | view |  | jcp_add_selection | False |  |  | True |  |  |  |
| Address Selection | Just Check Price - Address Search | Loading address search API called | False |  | v1_from_api | api | add_input | jcp_add_selection | False |  | search_str | True |  |  |  |
| Address Selection | Saved Address Selection |  | False |  | v1_add_selection | view |  | add_selection | False |  |  | True |  |  |  |
| Address Selection | Saved Address Selection | Clicks 'Current Add' on 'Saved Add' | False |  | v1_current_add | click | saved_add | add_selection | False |  |  | True |  |  |  |
| Address Selection | Loading Location Map (Save Address) | Clicks 'Pincode Check' on 'Add Input' | False |  | v1_pincode_check | click | add_input | save_loading_add | False |  | valid | True |  |  |  |
| Address Selection | Loading Location Map (Save Address) | Clicks 'Confirm Via Point' on 'Add Input' | False |  | v1_confirm_via_point | click | add_input | save_loading_add | False |  |  | True |  |  |  |
| Address Selection | Loading Location Map (Save Address) | Clicks 'Change Loc' on 'Add Input' | False |  | v1_change_loc | click | add_input | save_loading_add | False |  |  | True |  |  |  |
| Address Selection | Loading Location Map (Save Address) | Clicks 'Current Location' on 'Add Input' | False |  | v1_current_location | click | add_input | save_loading_add | False |  |  | True |  |  |  |
| Address Selection | Loading Location Map (Save Address) | Clicks 'Loading Location Confirmation' on 'Map View' | False |  | v1_loading_location_confirmation | click | map_view | save_loading_add | False |  |  | True |  |  |  |
| Address Selection | Loading Location Map (Save Address) | Drags map pin on 'Map View' | False |  | v1_pin_drag | click | map_view | save_loading_add | False |  |  | True |  |  |  |
| Address Selection | Loading Location Map (Save Address) | Drops map pin on 'Map View' | False |  | v1_pin_drop | click | map_view | save_loading_add | False |  |  | True |  |  |  |
| Address Selection | Loading Location Map (Save Address) | Clicks 'Back' arrow on 'Map View' | False |  | v1_back_btn | click | map_view | save_loading_add | False |  |  | True |  |  |  |
| Address Selection | Unloading Address Search |  | True |  | v1_add_selection | view |  | unloading_add_selection | False |  |  | True |  |  |  |
| Address Selection | Unloading Address Search | Selects an address from search results | True | Unloading address selected | v1_select_add | click |  | unloading_add_selection | False |  | up_src | True |  |  |  |
| Address Selection | Unloading Address Search | Clicks 'Back' arrow | False |  | v1_back | click |  | unloading_add_selection | False |  |  | True |  |  |  |
| Address Selection | Unloading Address Search | Unloading address search API called | False |  | v1_to_api | api | add_input | unloading_add_selection | False |  | search_str | True |  |  |  |
| Address Selection | Unloading Address Search | Views 'Add Error Bottomsheet' | False |  | v1_add_valid_check | view | add_error_bottom_sheet | unloading_add_selection | False |  | o | True |  |  |  |
| Address Selection | Unloading Address Search | Clicks 'Add Valid Check' on 'Add Error Bottomsheet' | False |  | v1_add_valid_check | click | add_error_bottom_sheet | unloading_add_selection | False |  | o | True |  |  |  |
| Address Selection | Multi-Drop Unloading Search |  | True |  | v1_vt_unloading | view |  | vt_unloading | False |  |  | True |  |  |  |
| Address Selection | Multi-Drop Unloading Search | Clicks 'Unloading Location' | False |  | v1_unloading_location | click |  | vt_unloading | False |  | idx | True |  |  |  |
| Address Selection | Multi-Drop Unloading Search | Clicks 'Check Prices' | False |  | v1_check_prices | click |  | vt_unloading | False |  | count | True |  |  |  |
| Address Selection | Via Points (Multi Stop) |  | True |  | v1_via_point | view |  | via_point | False |  |  | True |  |  |  |
| Address Selection | Via Points (Multi Stop) | Clicks 'Continue' button | False |  | v1_continue_btn | click |  | via_point | False |  |  | True |  |  |  |
| Address Selection | Via Points (Multi Stop) | Clicks 'Edit Via Point' | False |  | v1_edit_via_point | click |  | via_point | False |  | src | True |  |  |  |
| Address Selection | Via Points (Multi Stop) | Clicks 'Back' arrow | False |  | v1_back | click |  | via_point | False |  |  | True |  |  |  |
| Address Selection | Via Points (Multi Stop) | Clicks 'Add Unloading Point' | False |  | v1_add_unloading | click |  | via_point | False |  |  | True |  |  |  |
| Address Selection | Via Points (Multi Stop) | Clicks 'Add Loading Point' | False |  | v1_add_loading | click |  | via_point | False |  |  | True |  |  |  |
| Address Selection | Via Points (Multi Stop) | Clicks 'Close' (X) | False |  | v1_close | click |  | via_point | False |  |  | True |  |  |  |
| Address Selection | Via Points (Multi Stop) | Views 'Add Error Bottomsheet' | False |  | v1_add_valid_check | view | add_error_bottom_sheet | via_point | False |  | o | True |  |  |  |
| Address Selection | Via Points (Multi Stop) | Clicks 'Add Valid Check' on 'Add Error Bottomsheet' | False |  | v1_add_valid_check | click | add_error_bottom_sheet | via_point | False |  | o | True |  |  |  |
| Address Selection | Via Points Map | Clicks 'Address Bar' on 'Map View' | False |  | v1_address_bar | click | map_view | via_points | False |  | src | True |  |  |  |
| Browsing | Truck Requirement | Views 'Vehicle Input' | False |  | v1_duplicate_demand_restriction | view | vehicle_input | truck_requirement | True |  |  | True |  |  |  |
| Browsing | Truck Requirement | Views 'Vehicle Input' | False |  | v1_waiting_cnf_btmsheet | view | vehicle_input | truck_requirement | True |  |  | True |  |  |  |
| Browsing | Truck Requirement | Clicks 'View Similar Booking' on 'Vehicle Input' | False |  | v1_view_similar_booking | click | vehicle_input | truck_requirement | False |  |  | True |  |  |  |
| Browsing | Enter Tonnage |  | True | VT Browsing Initiated | v1_tonnage | view |  | tonnage_req_v1 | False |  | source | True |  |  |  |
| Browsing | Enter Tonnage | Chooses any tonnage option | False |  | v1_choose_wt | click |  | tonnage_req_v1 | False |  |  | True |  |  |  |
| Browsing | Enter Tonnage | Clicks tonnage field | False |  | v1_input_wt | click |  | tonnage_req_v1 | False |  |  | True |  |  |  |
| Browsing | Enter Tonnage | Clicks 'Submit' button | True | Tonnage submitted | v1_submit | click |  | tonnage_req_v1 | False |  |  | True |  |  |  |
| Browsing | Enter Tonnage | Clicks 'I don't know my material weight' button | False |  | v1_dont_know_wt | click |  | tonnage_req_v1 | False |  |  | True |  |  |  |
| Browsing | Enter Tonnage | Clicks 'Back' arrow | False |  | v1_back | click | top_nav | tonnage_req_v1 | False |  |  | True |  |  |  |
| Browsing | Enter Tonnage | Clicks 'Edit' address | False |  | v1_edit_add | click | top_nav | tonnage_req_v1 | False |  |  | True |  |  |  |
| Browsing | Enter Tonnage | Clicks 'Add Loading Point' | False |  | v1_add_loading | click | top_nav | tonnage_req_v1 | False |  |  | True |  |  |  |
| Browsing | Enter Tonnage | Clicks 'Add Unloading Point' | False |  | v1_add_unloading | click | top_nav | tonnage_req_v1 | False |  |  | True |  |  |  |
| Browsing | Vehicle Selection |  | True |  | v1_veh_options | view |  | tonnage_req | False |  | source | True |  |  |  |
| Browsing | Vehicle Selection |  | False |  | v1_scroll | view |  | tonnage_req | False |  | scroll_direction | True |  |  |  |
| Browsing | Vehicle Selection |  | False |  | v1_demand_create_info | view |  | tonnage_req | False |  |  | True |  |  |  |
| Browsing | Vehicle Selection |  | False |  | v1_veh_unavailable | view |  | tonnage_req | False |  |  | True |  |  |  |
| Browsing | Vehicle Selection |  | False |  | v1_price_range_info | view |  | tonnage_req | False |  |  | True |  |  |  |
| Browsing | Vehicle Selection |  | False |  | v1_rate_limit_issue | view |  | tonnage_req | False |  |  | True |  |  |  |
| Browsing | Vehicle Selection |  | False |  | v1_unloading_location | view |  | tonnage_req | False |  |  | True |  |  |  |
| Browsing | Vehicle Selection |  | False |  | v1_wkly_limit | view |  | tonnage_req | False |  |  | True |  |  |  |
| Browsing | Vehicle Selection | Selects a vehicle option | False |  | v1_veh_opted | click |  | tonnage_req | False |  | idx | True |  |  |  |
| Browsing | Vehicle Selection | Selects truck body type | False |  | v1_body_type | click |  | tonnage_req | False |  | bt | True |  |  |  |
| Browsing | Vehicle Selection | Clicks 'Confirm Vehicle' button | True | Vehicle confirmed | v1_cnf_veh | click |  | tonnage_req | False |  | idx | True |  |  |  |
| Browsing | Vehicle Selection | Selects truck height | False |  | v1_height | click |  | tonnage_req | False |  | ht | True |  |  |  |
| Browsing | Vehicle Selection | Clicks 'Enter Weight' field | False |  | v1_enter_wt | click |  | tonnage_req | False |  |  | True |  |  |  |
| Browsing | Vehicle Selection | Clicks 'Special Requirement' | False |  | v1_spcl_req | click |  | tonnage_req | False |  | click | True |  |  |  |
| Browsing | Vehicle Selection | Clicks 'Change Tonnage' | False |  | v1_change_tonnage | click |  | tonnage_req | False |  |  | True |  |  |  |
| Browsing | Vehicle Selection | Selects truck width | False |  | v1_width | click |  | tonnage_req | False |  | wi | True |  |  |  |
| Browsing | Vehicle Selection | Clicks 'Price Range Info' | False |  | v1_price_range_info | click |  | tonnage_req | False |  |  | True |  |  |  |
| Browsing | Vehicle Selection | Clicks 'Unloading Location Edit' | False |  | v1_unloading_location_edit | click |  | tonnage_req | False |  |  | True |  |  |  |
| Browsing | Vehicle Selection | Clicks 'Unloading Location' | False |  | v1_unloading_location | click |  | tonnage_req | False |  | idx | True |  |  |  |
| Browsing | Vehicle Selection | Clicks 'Learn Why' | False |  | v1_learn_why | click |  | tonnage_req | False |  |  | True |  |  |  |
| Browsing | Vehicle Selection | Clicks 'Add Stop' | False |  | v1_add_stop | click |  | tonnage_req | False |  |  | True |  |  |  |
| Browsing | Vehicle Selection | Clicks 'Edit' address | False |  | v1_edit_add | click | top_nav | tonnage_req | False |  |  | True |  |  |  |
| Browsing | Vehicle Selection | Clicks 'Add Loading Point' | False |  | v1_add_loading | click | top_nav | tonnage_req | False |  |  | True |  |  |  |
| Browsing | Vehicle Selection | Clicks 'Add Unloading Point' | False |  | v1_add_unloading | click | top_nav | tonnage_req | False |  |  | True |  |  |  |
| Browsing | Vehicle Selection | Views 'Enter Wt Bottomsheet' | False |  | v1_wt_bottomsheet | view | enter_wt_bottomsheet | tonnage_req | False |  |  | True |  |  |  |
| Browsing | Vehicle Selection | Clicks 'Confirm Weight' button on 'Enter Wt Bottomsheet' | False |  | v1_cnf_wt | click | enter_wt_bottomsheet | tonnage_req | False |  | wt | True |  |  |  |
| Browsing | Vehicle Selection | Chooses any tonnage option on 'Enter Wt Bottomsheet' | False |  | v1_choose_wt | click | enter_wt_bottomsheet | tonnage_req | False |  |  | True |  |  |  |
| Browsing | Vehicle Selection | Clicks 'Enter Weight' field on 'Enter Wt Bottomsheet' | False |  | v1_enter_wt | click | enter_wt_bottomsheet | tonnage_req | False |  |  | True |  |  |  |
| Browsing | Vehicle Selection | Clicks 'Close' (X) on 'Enter Wt Bottomsheet' | False |  | v1_close | click | enter_wt_bottomsheet | tonnage_req | False |  |  | True |  |  |  |
| Browsing | Vehicle Selection | Views 'Add Error Bottomsheet' | False |  | v1_add_valid_check | view | add_error_bottom_sheet | tonnage_req | False |  | o | True |  |  |  |
| Browsing | Vehicle Selection | Clicks 'Add Valid Check' on 'Add Error Bottomsheet' | False |  | v1_add_valid_check | click | add_error_bottom_sheet | tonnage_req | False |  | o | True |  |  |  |
| Browsing | Vehicle Selection | Views 'Price Range Info Bottomsheet' | False |  | v1_price_range_info_btmsheet | view | price_range_info_btmsheet | tonnage_req | False |  |  | True |  |  |  |
| Browsing | Vehicle Selection | Clicks 'Iunderstand' on 'Price Range Info Bottomsheet' | False |  | v1_iunderstand | click | price_range_info_btmsheet | tonnage_req | False |  |  | True |  |  |  |
| Demand Creation | Demand Creation |  | False |  | v1_restriction_bottomsheet | view |  | demand_creation | True |  |  | True |  |  |  |
| Demand Creation | Demand Creation | Clicks 'Continue' button | False |  | v1_continue | click |  | demand_creation | True |  | duetype | True |  |  |  |
| Demand Creation | Demand Creation | Clicks 'Fee Icon' | False |  | v1_fee_icon | click |  | demand_creation | True |  |  | True |  |  |  |
| Demand Creation | Demand Creation | Clicks 'Clear Due' | False |  | v1_clear_due | click |  | demand_creation | True |  |  | True |  |  |  |
| Demand Creation | Demand Creation | Clicks 'Need Help' | False |  | v1_need_help | click |  | demand_creation | True |  |  | True |  |  |  |
| Demand Creation | Price Range & Loading Slot |  | True |  | v1_demand_price_range | view |  | demand_price_range | True |  |  | True |  |  |  |
| Demand Creation | Price Range & Loading Slot | Clicks 'Continue Demand Price Range' | False |  | v1_continue_btn_demand_price_range | click |  | demand_price_range | False |  |  | True |  |  |  |
| Demand Creation | Price Range & Loading Slot | Clicks 'Time' | False |  | v1_time | click |  | demand_price_range | True |  | idx | True |  |  |  |
| Demand Creation | Price Range & Loading Slot | Clicks 'Day' | False |  | v1_day | click |  | demand_price_range | True |  | idx | True |  |  |  |
| Demand Creation | Price Range & Loading Slot | Clicks 'Paymode' | False |  | v1_paymode | click |  | demand_price_range | True |  | payment_mode | True |  |  |  |
| Demand Creation | Price Range & Loading Slot | Clicks 'Edit Photo' | False |  | v1_edit_photo | click |  | demand_price_range | True |  |  | True |  |  |  |
| Demand Creation | Price Range & Loading Slot | Clicks 'Confirm' button | True | Demand created | v1_confirm_btn | click | bottom_nav | demand_price_range | True |  | entered_via | True |  |  |  |
| Demand Creation | Price Range & Loading Slot | Clicks 'Continue' button | True | Demand price range confirmed | v1_continue_btn | click | bottom_nav | demand_price_range | True |  | dr_slot | True |  |  |  |
| Demand Creation | Price Range & Loading Slot | Clicks 'Back' arrow | False |  | v1_back_btn | click | top_nav | demand_price_range | True |  | timer | True |  |  |  |
| Demand Creation | Price Range & Loading Slot | Clicks 'Cancel' | False |  | v1_cancel | click | top_nav | demand_price_range | True |  |  | True |  |  |  |
| Demand Creation | Price Range & Loading Slot | Clicks 'Edit Vehicle' | False |  | v1_edit_veh | click | top_nav | demand_price_range | True |  |  | True |  |  |  |
| Demand Creation | Price Range & Loading Slot | Clicks 'Edit' address | False |  | v1_edit_add | click | top_nav | demand_price_range | False |  |  | True |  |  |  |
| Demand Creation | Price Range & Loading Slot | Selects search mode on 'Search Modes' | False |  | v1_mode | click | search_modes | demand_price_range | True |  |  | True |  |  |  |
| Demand Creation | Price Range & Loading Slot | Views 'Loading Slot' | False |  | v1_loading_slot | view | loading_slot | demand_price_range | True |  | schdr | True |  |  |  |
| Demand Creation | Price Range & Loading Slot | Selects loading time on 'Loading Slot' | False |  | v1_loading_time | click | loading_slot | demand_price_range | True |  | idx | True |  |  |  |
| Demand Creation | Price Range & Loading Slot | Selects loading day on 'Loading Slot' | False |  | v1_loading_day | click | loading_slot | demand_price_range | True |  | idx | True |  |  |  |
| Demand Creation | Price Range & Loading Slot | Views 'Last Booking Warning' | False |  | v1_last_booking_btmsheet | view | last_booking_warning | demand_price_range | False |  |  | True |  |  |  |
| Demand Creation | Price Range & Loading Slot | Clicks 'Got it' on 'Last Booking Warning' | False |  | v1_got_it | click | last_booking_warning | demand_price_range | False |  |  | True |  |  |  |
| Demand Creation | Price Range & Loading Slot | Clicks 'Close' (X) on 'Last Booking Warning' | False |  | v1_close | click | last_booking_warning | demand_price_range | False |  |  | True |  |  |  |
| Demand Creation | Price Range & Loading Slot | Clicks 'Learn Why' on 'Last Booking Warning' | False |  | v1_learn_why | click | last_booking_warning | demand_price_range | False |  |  | True |  |  |  |
| Demand Creation | Weekly Booking Limit |  | False |  | v1_wkly_plc_limit | view |  | wkly_plc_limit | False |  |  | True |  |  |  |
| Demand Creation | Weekly Booking Limit | Clicks 'Got it' | False |  | v1_got_it | click |  | wkly_plc_limit | False |  |  | True |  |  |  |
| Demand Creation | Weekly Booking Limit | Clicks 'Back' arrow | False |  | v1_back | click |  | wkly_plc_limit | False |  |  | True |  |  |  |
| Demand Creation | Booking Preview | Views 'Bottomsheet' | True |  | v1_bottom_sheet_view | view | bottom_sheet | booking_preview | True |  | amt_due | True |  |  |  |
| Demand Creation | Booking Preview | Clicks 'Close' (X) on 'Bottomsheet' | False |  | v1_close_btn | click | bottom_sheet | booking_preview | True |  |  | True |  |  |  |
| Demand Creation | Booking Preview | Clicks 'Pay' button on 'Bottomsheet' | False |  | v1_pay_btn | click | bottom_sheet | booking_preview | True |  | amt_due | True |  |  |  |
| Loading/Unloading Details | Loading Details (DR Steps) |  | True |  | v1_dr_stage | view |  | add_loading_unloading | True |  | dr_stage | True |  |  |  |
| Loading/Unloading Details | Loading Details (DR Steps) |  | False |  | v1_material_photo_bottomsheet | view |  | add_loading_unloading | True |  |  | True |  |  |  |
| Loading/Unloading Details | Loading Details (DR Steps) | Clicks 'Submit' button | False |  | v1_submit | click |  | add_loading_unloading | False |  | expected_trip_count | True |  |  |  |
| Loading/Unloading Details | Loading Details (DR Steps) | Clicks 'Confirm' button | True | Loading details confirmed | v1_confirm_btn | click | bottom_nav | add_loading_unloading | True |  | entered_via | True |  |  |  |
| Loading/Unloading Details | Loading Details (DR Steps) | Selects address entry mode | False |  | v1_addr_mode | click | top_nav | add_loading_unloading | True |  | entered_via | True |  |  |  |
| Loading/Unloading Details | Loading Details (DR Steps) | Clicks 'Back' arrow | False |  | v1_back_btn | click | top_nav | add_loading_unloading | True |  | timer | True |  |  |  |
| Loading/Unloading Details | Loading Details (DR Steps) | Clicks DR step tab | False |  | v1_dr_stage | click | top_nav | add_loading_unloading | True |  | dr_stage | True |  |  |  |
| Loading/Unloading Details | Loading Details (DR Steps) | Drags map pin on 'Map View' | False |  | v1_pin_drag | click | map_view | add_loading_unloading | True |  | lat | True |  |  |  |
| Loading/Unloading Details | Loading Details (DR Steps) | Drops map pin on 'Map View' | False |  | v1_pin_drop | click | map_view | add_loading_unloading | True |  | lat | True |  |  |  |
| Loading/Unloading Details | Loading Details (DR Steps) | Clicks 'Locate on Map' on 'Map View' | False |  | v1_map_locate | click | map_view | add_loading_unloading | True |  |  | True |  |  |  |
| Loading/Unloading Details | Loading Details (DR Steps) | Clicks 'Current Location' on 'Map View' | False |  | v1_current_location | click | map_view | add_loading_unloading | True |  |  | True |  |  |  |
| Loading/Unloading Details | Loading Details (DR Steps) | Selects a saved address on 'Address Dets' | False |  | v1_saved_addr | click | address_dets | add_loading_unloading | True |  | addr_choice | True |  |  |  |
| Loading/Unloading Details | Loading Details (DR Steps) | Clicks 'Use My Contact' on 'Address Dets' | False |  | v1_use_my_contact | click | address_dets | add_loading_unloading | True |  | type | True |  |  |  |
| Loading/Unloading Details | Loading Details (DR Steps) | Clicks 'POC Number' field on 'Address Dets' | False |  | v1_poc_number | click | address_dets | add_loading_unloading | True |  | type | True |  |  |  |
| Loading/Unloading Details | Loading Details (DR Steps) | Clicks 'Full Address' field on 'Address Dets' | False |  | v1_enter_full_addr | click | address_dets | add_loading_unloading | True |  | type | True |  |  |  |
| Loading/Unloading Details | Loading Details (DR Steps) | Clicks 'POC Name' field on 'Address Dets' | False |  | v1_poc_name | click | address_dets | add_loading_unloading | True |  | type | True |  |  |  |
| Loading/Unloading Details | Loading Details (DR Steps) | Clicks 'Contact Book' icon on 'Address Dets' | False |  | v1_contact_book | click | address_dets | add_loading_unloading | True |  | type | True |  |  |  |
| Loading/Unloading Details | Loading Details (DR Steps) | Clicks 'Pincode' field on 'Address Dets' | False |  | v1_enter_pincode | click | address_dets | add_loading_unloading | True |  | type | True |  |  |  |
| Loading/Unloading Details | Loading Details (DR Steps) | Clicks 'Change Loc' on 'Add Input' | False |  | v1_change_loc | click | add_input | add_loading_unloading | True |  |  | True |  |  |  |
| Loading/Unloading Details | Loading Details (DR Steps) | Clicks 'Close' (X) on 'Material Photo Bottomsheet' | False |  | v1_close | click | material_photo_bottomsheet | add_loading_unloading | True |  |  | True |  |  |  |
| Loading/Unloading Details | Loading Details (DR Steps) | Clicks 'Select From Gallery' on 'Material Photo Bottomsheet' | False |  | v1_select_from_gallery | click | material_photo_bottomsheet | add_loading_unloading | True |  |  | True |  |  |  |
| Loading/Unloading Details | Loading Details (DR Steps) | Clicks 'Take Picture' on 'Material Photo Bottomsheet' | False |  | v1_take_picture | click | material_photo_bottomsheet | add_loading_unloading | True |  |  | True |  |  |  |
| Loading/Unloading Details | Loading Details (DR Steps) | Views 'Photo Unclear Bottomsheet' | False |  | v1_photo_unclear_bottomsheet | view | photo_unclear_bottomsheet | add_loading_unloading | True |  |  | True |  |  |  |
| Loading/Unloading Details | Loading Details (DR Steps) | Clicks 'Upload Again' on 'Photo Unclear Bottomsheet' | False |  | v1_upload_again | click | photo_unclear_bottomsheet | add_loading_unloading | True |  |  | True |  |  |  |
| Loading/Unloading Details | Loading Details (DR Steps) | Clicks 'Close' (X) on 'Photo Unclear Bottomsheet' | False |  | v1_close | click | photo_unclear_bottomsheet | add_loading_unloading | True |  |  | True |  |  |  |
| Loading/Unloading Details | Unloading Details (DR Steps) |  | True |  | v1_dr_stage | view |  | unloading | True |  | dr_stage | True |  |  |  |
| Loading/Unloading Details | Unloading Details (DR Steps) | Clicks 'Confirm' button | True | Unloading details confirmed | v1_confirm_btn | click | bottom_nav | unloading | True |  | entered_via | True |  |  |  |
| Loading/Unloading Details | Unloading Details (DR Steps) | Clicks 'Back' arrow | False |  | v1_back_btn | click | top_nav | unloading | True |  | timer | True |  |  |  |
| Loading/Unloading Details | Unloading Details (DR Steps) | Clicks DR step tab | False |  | v1_dr_stage | click | top_nav | unloading | True |  | dr_stage | True |  |  |  |
| Loading/Unloading Details | Unloading Details (DR Steps) | Clicks 'Full Address' field on 'Address Dets' | False |  | v1_enter_full_addr | click | address_dets | unloading | True |  | type | True |  |  |  |
| Loading/Unloading Details | Unloading Details (DR Steps) | Selects a saved address on 'Address Dets' | False |  | v1_saved_addr | click | address_dets | unloading | True |  | addr_choice | True |  |  |  |
| Loading/Unloading Details | Unloading Details (DR Steps) | Clicks 'Use My Contact' on 'Address Dets' | False |  | v1_use_my_contact | click | address_dets | unloading | True |  | type | True |  |  |  |
| Loading/Unloading Details | Unloading Details (DR Steps) | Clicks 'POC Number' field on 'Address Dets' | False |  | v1_poc_number | click | address_dets | unloading | True |  | type | True |  |  |  |
| Loading/Unloading Details | Unloading Details (DR Steps) | Clicks 'POC Name' field on 'Address Dets' | False |  | v1_poc_name | click | address_dets | unloading | True |  | type | True |  |  |  |
| Loading/Unloading Details | Unloading Details (DR Steps) | Clicks 'Contact Book' icon on 'Address Dets' | False |  | v1_contact_book | click | address_dets | unloading | True |  | type | True |  |  |  |
| Loading/Unloading Details | Unloading Details (DR Steps) | Clicks 'Pincode' field on 'Address Dets' | False |  | v1_enter_pincode | click | address_dets | unloading | True |  | type | True |  |  |  |
| Insurance | Insurance Opt in | Clicks 'No' | False |  | v1_no | click | bottom_nav | insurance | True |  |  | True |  |  |  |
| Insurance | Insurance Opt in | Clicks 'Add Insurance' | False |  | v1_add_ins | click | bottom_nav | insurance | True |  |  | True |  |  |  |
| Insurance | Insurance Opt in | Toggles insurance checkbox | False |  | v1_ins_check | click | bottom_nav | insurance | True |  |  | True |  |  |  |
| Insurance | Insurance Opt in | Views 'Insurance' | True |  | v1_insurance | view | insurance | insurance | True |  |  | True |  |  |  |
| Insurance | Insurance Opt in | Clicks 'Submit' button on 'Reason Bottomsheet' | False |  | v1_submit | click | reason_btm_sheet | insurance | True |  | reason | True |  |  |  |
| Insurance | Insurance Opt in | Clicks 'Close' (X) on 'Reason Bottomsheet' | False |  | v1_close | click | reason_btm_sheet | insurance | True |  |  | True |  |  |  |
| Insurance | Insurance Opt in | Selects insurance pricing type on 'Insurance Pricing' | False |  | v1_pricing_type | click | insurance_pricing | insurance | True |  | type | True |  |  |  |
| Insurance | Searching Vehicle (Trip Details) - Insurance | Views 'Insurance Bottomsheet' | False |  | v1_insurance_btm_sheet | view | insurance_btm_sheet | searching_vehicle | True |  |  | True |  |  |  |
| Insurance | Searching Vehicle (Trip Details) - Insurance | Clicks 'Close' (X) on 'Insurance Bottomsheet' | False |  | v1_close | click | insurance_btm_sheet | searching_vehicle | True |  |  | True |  |  |  |
| Insurance | Searching Vehicle (Trip Details) - Insurance | Clicks 'Okay' on 'Insurance Bottomsheet' | False |  | v1_okay | click | insurance_btm_sheet | searching_vehicle | True |  |  | True |  |  |  |
| Insurance | Searching Vehicle (Trip Details) - Insurance | Clicks 'Add Insurance' on 'Insurance Bottomsheet' | False |  | v1_add_ins | click | insurance_btm_sheet | searching_vehicle | True |  |  | True |  |  |  |
| Insurance | Searching Vehicle (Trip Details) - Insurance | Clicks 'No' on 'Insurance Bottomsheet' | False |  | v1_no | click | insurance_btm_sheet | searching_vehicle | True |  |  | True |  |  |  |
| Insurance | Searching Vehicle (Trip Details) - Insurance | Toggles insurance checkbox on 'Insurance Bottomsheet' | False |  | v1_ins_check | click | insurance_btm_sheet | searching_vehicle | True |  |  | True |  |  |  |
| Insurance | Searching Vehicle (Trip Details) - Insurance | Clicks 'View Pricing' on 'Insurance' | False |  | v1_view_pricing | click | insurance | searching_vehicle | True |  |  | True |  |  |  |
| Insurance | Searching Vehicle (Trip Details) - Insurance | Toggles insurance checkbox on 'Insurance' | False |  | v1_ins_check | click | insurance | searching_vehicle | True |  |  | True |  |  |  |
| Insurance | Searching Vehicle (Trip Details) - Insurance | Clicks 'Add Insurance' on 'Insurance' | False |  | v1_add_insurance | click | insurance | searching_vehicle | True |  |  | True |  |  |  |
| Insurance | Searching Vehicle (Trip Details) - Insurance | Clicks 'Remove Insurance' on 'Insurance' | False |  | v1_remove_pricing | click | insurance | searching_vehicle | False |  |  | True |  |  |  |
| Insurance | Vehicle Found - Confirm Details - Insurance | Views 'Insurance Doc' | False |  | v1_insurance_doc | view | insurance_doc | scheduled_preview | True |  |  | True |  |  |  |
| Insurance | Vehicle Found - Confirm Details - Insurance | Clicks 'Remove Insurance' on 'Insurance' | False |  | v1_remove_pricing | click | insurance | scheduled_preview | False |  |  | True |  |  |  |
| Insurance | Vehicle Found - Confirm Details - Insurance | Clicks 'Update Pricing' on 'Insurance' | False |  | v1_update_pricing | click | insurance | scheduled_preview | True |  |  | True |  |  |  |
| Insurance | Vehicle Found - Confirm Details - Insurance | Clicks 'Add Insurance' on 'Insurance' | False |  | v1_add_insurance | click | insurance | scheduled_preview | True |  |  | True |  |  |  |
| Insurance | Vehicle Found - Confirm Details - Insurance | Clicks 'View Pricing' on 'Insurance' | False |  | v1_view_pricing | click | insurance | scheduled_preview | True |  |  | True |  |  |  |
| Insurance | Vehicle Found - Confirm Details - Insurance | Clicks 'Confirm' button on 'Update Ins Pricing' | False |  | v1_confim | click | update_ins_pricing | scheduled_preview | True |  |  | True |  |  |  |
| Insurance | Vehicle Found - Confirm Details - Insurance | Clicks 'OK' on 'Update Ins Pricing' | False |  | v1_ok | click | update_ins_pricing | scheduled_preview | True |  |  | True |  |  |  |
| Insurance | Vehicle Found - Confirm Details - Insurance | Clicks 'Close' (X) on 'Update Ins Pricing' | False |  | v1_close | click | update_ins_pricing | scheduled_preview | True |  |  | True |  |  |  |
| Insurance | Vehicle Found - Confirm Details - Insurance | Clicks 'View Fragile Items' on 'Update Ins Pricing' | False |  | v1_view_fragile | click | update_ins_pricing | scheduled_preview | True |  |  | True |  |  |  |
| Insurance | Vehicle Found - Confirm Details - Insurance | Views 'Insurance Bottomsheet' | False |  | v1_insurance_btm_sheet | view | insurance_btm_sheet | scheduled_preview | True |  |  | True |  |  |  |
| Insurance | Vehicle Found - Confirm Details - Insurance | Clicks 'Add Insurance' on 'Insurance Bottomsheet' | False |  | v1_add_ins | click | insurance_btm_sheet | scheduled_preview | True |  |  | True |  |  |  |
| Insurance | Vehicle Found - Confirm Details - Insurance | Clicks 'Close' (X) on 'Insurance Bottomsheet' | False |  | v1_close | click | insurance_btm_sheet | scheduled_preview | True |  |  | True |  |  |  |
| Insurance | Vehicle Found - Confirm Details - Insurance | Clicks 'No' on 'Insurance Bottomsheet' | False |  | v1_no | click | insurance_btm_sheet | scheduled_preview | True |  |  | True |  |  |  |
| Insurance | Vehicle Found - Confirm Details - Insurance | Clicks 'OK' on 'Fragile Items List' | False |  | v1_ok | click | fragile_items_list | scheduled_preview | True |  |  | True |  |  |  |
| Insurance | Trip Scheduled - Insurance | Views 'Insurance Doc' | False |  | v1_insurance_doc | view | insurance_doc | scheduled | True |  |  | True |  |  |  |
| Insurance | Trip Scheduled - Insurance | Clicks 'Confirm' button on 'Update Ins Pricing' | False |  | v1_confim | click | update_ins_pricing | scheduled | True |  |  | True |  |  |  |
| Insurance | Trip Scheduled - Insurance | Clicks 'OK' on 'Update Ins Pricing' | False |  | v1_ok | click | update_ins_pricing | scheduled | True |  |  | True |  |  |  |
| Insurance | Trip Scheduled - Insurance | Clicks 'Close' (X) on 'Update Ins Pricing' | False |  | v1_close | click | update_ins_pricing | scheduled | True |  |  | True |  |  |  |
| Insurance | Trip Scheduled - Insurance | Clicks 'View Fragile Items' on 'Update Ins Pricing' | False |  | v1_view_fragile | click | update_ins_pricing | scheduled | True |  |  | True |  |  |  |
| Insurance | Trip Scheduled - Insurance | Toggles insurance checkbox on 'Insurance' | False |  | v1_ins_check | click | insurance | scheduled | True |  |  | True |  |  |  |
| Insurance | Trip Scheduled - Insurance | Clicks 'Remove Insurance' on 'Insurance' | False |  | v1_remove_pricing | click | insurance | scheduled | False |  |  | True |  |  |  |
| Insurance | Trip Scheduled - Insurance | Clicks 'Update Pricing' on 'Insurance' | False |  | v1_update_pricing | click | insurance | scheduled | True |  |  | True |  |  |  |
| Insurance | Trip Scheduled - Insurance | Clicks 'View Pricing' on 'Insurance' | False |  | v1_view_pricing | click | insurance | scheduled | True |  |  | True |  |  |  |
| Insurance | Trip Scheduled - Insurance | Clicks 'Add Insurance' on 'Insurance' | False |  | v1_add_insurance | click | insurance | scheduled | True |  |  | True |  |  |  |
| Insurance | Trip Scheduled - Insurance | Views 'Insurance Bottomsheet' | False |  | v1_insurance_btm_sheet | view | insurance_btm_sheet | scheduled | True |  |  | True |  |  |  |
| Insurance | Trip Scheduled - Insurance | Clicks 'Close' (X) on 'Insurance Bottomsheet' | False |  | v1_close | click | insurance_btm_sheet | scheduled | True |  |  | True |  |  |  |
| Insurance | Trip Scheduled - Insurance | Clicks 'Add Insurance' on 'Insurance Bottomsheet' | False |  | v1_add_ins | click | insurance_btm_sheet | scheduled | True |  |  | True |  |  |  |
| Insurance | Trip Scheduled - Insurance | Clicks 'No' on 'Insurance Bottomsheet' | False |  | v1_no | click | insurance_btm_sheet | scheduled | True |  |  | True |  |  |  |
| Insurance | Trip Scheduled - Insurance | Toggles insurance checkbox on 'Insurance Bottomsheet' | False |  | v1_ins_check | click | insurance_btm_sheet | scheduled | True |  |  | True |  |  |  |
| Insurance | Trip Scheduled - Insurance | Clicks 'OK' on 'Fragile Items List' | False |  | v1_ok | click | fragile_items_list | scheduled | True |  |  | True |  |  |  |
| Insurance | Going To Load - Insurance | Views 'Insurance Doc' | False |  | v1_insurance_doc | view | insurance_doc | going_to_load | True |  |  | True |  |  |  |
| Insurance | Going To Load - Insurance | Clicks 'Confirm' button on 'Update Ins Pricing' | False |  | v1_confim | click | update_ins_pricing | going_to_load | True |  |  | True |  |  |  |
| Insurance | Going To Load - Insurance | Clicks 'OK' on 'Update Ins Pricing' | False |  | v1_ok | click | update_ins_pricing | going_to_load | True |  |  | True |  |  |  |
| Insurance | Going To Load - Insurance | Clicks 'Close' (X) on 'Update Ins Pricing' | False |  | v1_close | click | update_ins_pricing | going_to_load | True |  |  | True |  |  |  |
| Insurance | Going To Load - Insurance | Clicks 'View Fragile Items' on 'Update Ins Pricing' | False |  | v1_view_fragile | click | update_ins_pricing | going_to_load | True |  |  | True |  |  |  |
| Insurance | Going To Load - Insurance | Toggles insurance checkbox on 'Insurance' | False |  | v1_ins_check | click | insurance | going_to_load | True |  |  | True |  |  |  |
| Insurance | Going To Load - Insurance | Clicks 'Remove Insurance' on 'Insurance' | False |  | v1_remove_pricing | click | insurance | going_to_load | False |  |  | True |  |  |  |
| Insurance | Going To Load - Insurance | Clicks 'Update Pricing' on 'Insurance' | False |  | v1_update_pricing | click | insurance | going_to_load | True |  |  | True |  |  |  |
| Insurance | Going To Load - Insurance | Clicks 'Add Insurance' on 'Insurance' | False |  | v1_add_insurance | click | insurance | going_to_load | True |  |  | True |  |  |  |
| Insurance | Going To Load - Insurance | Clicks 'View Pricing' on 'Insurance' | False |  | v1_view_pricing | click | insurance | going_to_load | True |  |  | True |  |  |  |
| Insurance | Going To Load - Insurance | Views 'Insurance Bottomsheet' | False |  | v1_insurance_btm_sheet | view | insurance_btm_sheet | going_to_load | True |  |  | True |  |  |  |
| Insurance | Going To Load - Insurance | Clicks 'Close' (X) on 'Insurance Bottomsheet' | False |  | v1_close | click | insurance_btm_sheet | going_to_load | True |  |  | True |  |  |  |
| Insurance | Going To Load - Insurance | Clicks 'Add Insurance' on 'Insurance Bottomsheet' | False |  | v1_add_ins | click | insurance_btm_sheet | going_to_load | True |  |  | True |  |  |  |
| Insurance | Going To Load - Insurance | Toggles insurance checkbox on 'Insurance Bottomsheet' | False |  | v1_ins_check | click | insurance_btm_sheet | going_to_load | True |  |  | True |  |  |  |
| Insurance | Going To Load - Insurance | Clicks 'No' on 'Insurance Bottomsheet' | False |  | v1_no | click | insurance_btm_sheet | going_to_load | True |  |  | True |  |  |  |
| Insurance | Going To Load - Insurance | Clicks 'OK' on 'Fragile Items List' | False |  | v1_ok | click | fragile_items_list | going_to_load | True |  |  | True |  |  |  |
| Insurance | At Loading - Insurance | Views 'Insurance Doc' | False |  | v1_insurance_doc | view | insurance_doc | at_loading | True |  |  | True |  |  |  |
| Insurance | At Loading - Insurance | Clicks 'Confirm' button on 'Update Ins Pricing' | False |  | v1_confim | click | update_ins_pricing | at_loading | True |  |  | True |  |  |  |
| Insurance | At Loading - Insurance | Clicks 'OK' on 'Update Ins Pricing' | False |  | v1_ok | click | update_ins_pricing | at_loading | True |  |  | True |  |  |  |
| Insurance | At Loading - Insurance | Clicks 'Close' (X) on 'Update Ins Pricing' | False |  | v1_close | click | update_ins_pricing | at_loading | True |  |  | True |  |  |  |
| Insurance | At Loading - Insurance | Clicks 'View Fragile Items' on 'Update Ins Pricing' | False |  | v1_view_fragile | click | update_ins_pricing | at_loading | True |  |  | True |  |  |  |
| Insurance | At Loading - Insurance | Toggles insurance checkbox on 'Insurance' | False |  | v1_ins_check | click | insurance | at_loading | True |  |  | True |  |  |  |
| Insurance | At Loading - Insurance | Clicks 'Update Pricing' on 'Insurance' | False |  | v1_update_pricing | click | insurance | at_loading | True |  |  | True |  |  |  |
| Insurance | At Loading - Insurance | Clicks 'Remove Insurance' on 'Insurance' | False |  | v1_remove_pricing | click | insurance | at_loading | False |  |  | True |  |  |  |
| Insurance | At Loading - Insurance | Clicks 'Add Insurance' on 'Insurance' | False |  | v1_add_insurance | click | insurance | at_loading | True |  |  | True |  |  |  |
| Insurance | At Loading - Insurance | Clicks 'View Pricing' on 'Insurance' | False |  | v1_view_pricing | click | insurance | at_loading | True |  |  | True |  |  |  |
| Insurance | At Loading - Insurance | Views 'Insurance Bottomsheet' | False |  | v1_insurance_btm_sheet | view | insurance_btm_sheet | at_loading | True |  |  | True |  |  |  |
| Insurance | At Loading - Insurance | Clicks 'Add Insurance' on 'Insurance Bottomsheet' | False |  | v1_add_ins | click | insurance_btm_sheet | at_loading | True |  |  | True |  |  |  |
| Insurance | At Loading - Insurance | Clicks 'Close' (X) on 'Insurance Bottomsheet' | False |  | v1_close | click | insurance_btm_sheet | at_loading | True |  |  | True |  |  |  |
| Insurance | At Loading - Insurance | Toggles insurance checkbox on 'Insurance Bottomsheet' | False |  | v1_ins_check | click | insurance_btm_sheet | at_loading | True |  |  | True |  |  |  |
| Insurance | At Loading - Insurance | Clicks 'No' on 'Insurance Bottomsheet' | False |  | v1_no | click | insurance_btm_sheet | at_loading | True |  |  | True |  |  |  |
| Insurance | At Loading - Insurance | Clicks 'OK' on 'Fragile Items List' | False |  | v1_ok | click | fragile_items_list | at_loading | True |  |  | True |  |  |  |
| Insurance | In Transit - Insurance | Views 'Insurance Doc' | False |  | v1_insurance_doc | view | insurance_doc | in_transit | True |  |  | True |  |  |  |
| Insurance | In Transit - Insurance | Clicks 'Download' on 'Insurance Doc' | False |  | v1_download | click | insurance_doc | in_transit | True |  |  | True |  |  |  |
| Insurance | At Unloading - Insurance | Views 'Insurance Doc' | False |  | v1_insurance_doc | view | insurance_doc | at_unloading | True |  |  | True |  |  |  |
| Insurance | At Unloading - Insurance | Clicks 'Download' on 'Insurance Doc' | False |  | v1_download | click | insurance_doc | at_unloading | True |  |  | True |  |  |  |
| Insurance | Trip End - Insurance | Views 'Insurance Doc' | False |  | v1_insurance_doc | view | insurance_doc | trip_end | True |  |  | True |  |  |  |
| Insurance | Trip End - Insurance | Clicks 'Download' on 'Insurance Doc' | False |  | v1_download | click | insurance_doc | trip_end | True |  |  | True |  |  |  |
| Payment Selection | Payment Mode Selection | Views 'Payment Selection' | True |  | v1_payment_page | view | payment_selection | payment_plc | True |  | payment_mode | True |  |  |  |
| Payment Selection | Payment Mode Selection | Clicks 'Submit' on payment mode on 'Payment Selection' | True | Payment mode submitted | v1_pmode_submit | click | payment_selection | payment_plc | True |  | payment_mode | True |  |  |  |
| Payment Selection | Payment Mode Selection | Clicks 'Edit Plan' on 'Payment Selection' | False |  | v1_plan_edit | click | payment_selection | payment_plc | True |  | payment_mode | True |  |  |  |
| Payment Selection | Payment Mode Selection | Clicks 'Submit Billing' on 'Payment Selection' | False |  | v1_bill_submit | click | payment_selection | payment_plc | True |  | billing | True |  |  |  |
| Payment Selection | Payment Mode Selection | Clicks 'Edit Billing' on 'Payment Selection' | False |  | v1_bill_edit | click | payment_selection | payment_plc | True |  | payment_mode | True |  |  |  |
| Payment Selection | Payment Mode Selection | Clicks 'Consignee Edit' on 'Payment Selection' | False |  | v1_consignee_edit | click | payment_selection | payment_plc | True |  | payment_mode | True |  |  |  |
| Payment Selection | Payment Mode Edit | Views 'Payment Selection' | True |  | v1_payment_page | view | payment_selection | payment_edit | True |  | payment_mode | True |  |  |  |
| Payment Selection | Payment Mode Edit | Clicks 'Submit' on payment mode on 'Payment Selection' | True | Payment mode submitted | v1_pmode_submit | click | payment_selection | payment_edit | True |  | payment_mode | True |  |  |  |
| Payment Selection | Payment Mode Edit | Clicks 'Bkyc Submit' on 'Payment Selection' | False |  | v1_bkyc_submit | click | payment_selection | payment_edit | True |  | payment_mode | True |  |  |  |
| Payment Selection | Payment Mode Edit | Clicks 'Edit Plan' on 'Payment Selection' | False |  | v1_plan_edit | click | payment_selection | payment_edit | True |  | payment_mode | True |  |  |  |
| Payment Selection | Payment Mode Edit | Clicks 'Edit Billing' on 'Payment Selection' | False |  | v1_bill_edit | click | payment_selection | payment_edit | True |  | payment_mode | True |  |  |  |
| Payment Selection | Payment Mode Edit | Clicks 'Submit Billing' on 'Payment Selection' | False |  | v1_bill_submit | click | payment_selection | payment_edit | True |  | billing | True |  |  |  |
| Payment Selection | Payment Mode Edit | Clicks 'Consignee Edit' on 'Payment Selection' | False |  | v1_consignee_edit | click | payment_selection | payment_edit | True |  | payment_mode | True |  |  |  |
| Payment Selection | Payment Mode Edit | Clicks 'Ckyc Submit' on 'Payment Selection' | False |  | v1_ckyc_submit | click | payment_selection | payment_edit | True |  | payment_mode | True |  |  |  |
| Payment Selection | Payment Mode Edit | Clicks 'Choose Plan Submit' on 'Payment Selection' | False |  | v1_choose_plan_submit | click | payment_selection | payment_edit | True |  | payment_mode | True |  |  |  |
| Vehicle Search | Searching Price - Cancellation | Views 'Cancel Bottomsheet' | False |  | v1_cancel_bottom_sheet | view | cancel_bottom_sheet | searching_price | True |  |  | True |  |  |  |
| Vehicle Search | Searching Price - Cancellation | Selects a reason on 'Cancel Bottomsheet' | False |  | v1_reason_selected | click | cancel_bottom_sheet | searching_price | True |  |  | True |  |  |  |
| Vehicle Search | Searching Price - Cancellation | Clicks 'Submit' button on 'Cancel Bottomsheet' | False |  | v1_submit_btn | click | cancel_bottom_sheet | searching_price | True |  | reason | True |  |  |  |
| Vehicle Search | Searching Price - Cancellation | Clicks 'Modify' button on 'Cancel Bottomsheet' | False |  | v1_modify_btn | click | cancel_bottom_sheet | searching_price | True |  | reason | True |  |  |  |
| Vehicle Search | Searching Price - Invoices, Expenses & Dues | Views 'Pending Due Agreement Sheet' | False |  | v1_payment_note_sheet | view | pending_due_agreement_sheet | searching_price | True |  |  | True |  |  |  |
| Vehicle Search | Searching Price - Invoices, Expenses & Dues | Clicks 'Agree' on 'Pending Due Agreement Sheet' | False |  | v1_agree | click | pending_due_agreement_sheet | searching_price | True |  |  | True |  |  |  |
| Vehicle Search | Searching Price - Invoices, Expenses & Dues | Clicks 'View Detail' on 'Pending Due Agreement Sheet' | False |  | v1_view_detail | click | pending_due_agreement_sheet | searching_price | True |  |  | True |  |  |  |
| Vehicle Search | Searching Price - Invoices, Expenses & Dues | Clicks 'View All' on 'Pending Due Agreement Sheet' | False |  | v1_view_all | click | pending_due_agreement_sheet | searching_price | True |  |  | True |  |  |  |
| Vehicle Search | Vehicle Searching |  | True |  | v1_veh_searching | view |  | veh_searching | True |  | time | True |  |  |  |
| Vehicle Search | Vehicle Searching |  | False |  | v1_price_not_found | view |  | veh_searching | True |  |  | True |  |  |  |
| Vehicle Search | Vehicle Searching | Clicks 'View Details' | False |  | v1_view_details | click |  | veh_searching | True |  |  | True |  |  |  |
| Vehicle Search | Vehicle Searching | Clicks 'Back' arrow | False |  | v1_back | click | top_nav | veh_searching | False |  |  | True |  |  |  |
| Vehicle Search | Vehicle Searching |  | False |  | v1_cancel_policy | view | bottom_nav | veh_searching | True |  |  | True |  |  |  |
| Vehicle Search | Vehicle Searching | Views 'Post Plc Educate' | False |  | v1_plc_edu | view | post_plc_educate | veh_searching | False |  |  | True |  |  |  |
| Vehicle Search | Vehicle Searching | Clicks 'Edu Pop Click' on 'Post Plc Educate' | False |  | v1_edu_pop_click | click | post_plc_educate | veh_searching | False |  |  | True |  |  |  |
| Vehicle Search | Vehicle Searching | Clicks 'Iunderstand' on 'Post Plc Educate' | False |  | v1_iunderstand | click | post_plc_educate | veh_searching | False |  |  | True |  |  |  |
| Vehicle Search | Vehicle Searching - Cancellation | Views 'Cancel Bot' | False |  | v1_cancel_bot | view | cancel_bot | veh_searching | True |  | time | True |  |  |  |
| Vehicle Search | Vehicle Searching - Cancellation | Clicks 'Continue' button on 'Cancel Bot' | False |  | v1_continue | click | cancel_bot | veh_searching | True |  | action | True |  |  |  |
| Vehicle Search | Vehicle Searching - Cancellation | Clicks 'Close' (X) on 'Cancel Bot' | False |  | v1_close | click | cancel_bot | veh_searching | True |  | time | True |  |  |  |
| Vehicle Search | Vehicle Searching | Clicks 'Try Again' on 'Price Not Found' | False |  | v1_try_again | click | price_not_found | veh_searching | True |  | search_mode | True |  |  |  |
| Vehicle Search | Vehicle Searching | Views 'Loc Stops' | False |  | v1_loc_stops | view | loc_stops | veh_searching | True |  |  | True |  |  |  |
| Vehicle Search | Searching Vehicle (Trip Details) - Cancellation | Views 'Cancellation Bottomsheet' | False |  | v1_cancellation_bottom_sheet | view | cancellation_bottom_sheet | searching_vehicle | True |  |  | True |  |  |  |
| Vehicle Search | Searching Vehicle (Trip Details) | Views 'Searching Veh' | True |  | v1_macro_event_search | view | searching_veh | searching_vehicle | False |  |  | True |  |  |  |
| Vehicle Search | Searching Vehicle (Trip Details) - Cancellation | Clicks 'Cancel Booking' on 'Cancellation Bottomsheet' | False |  | v1_cancel_booking | click | cancellation_bottomsheet | searching_vehicle | True |  | reason | True |  |  |  |
| Vehicle Search | Searching Vehicle (Trip Details) - Cancellation | Clicks 'Cancel Booking Close' on 'Cancellation Bottomsheet' | False |  | v1_cancel_booking_close | click | cancellation_bottomsheet | searching_vehicle | True |  |  | True |  |  |  |
| Vehicle Search | Searching Vehicle (Trip Details) - Cancellation | Views 'Final Cancel Bottomsheet' | False |  | v1_final_cancel_bottom_sheet | view | final_cancel_bottom_sheet | searching_vehicle | True |  | rsn | True |  |  |  |
| Vehicle Search | Searching Vehicle (Trip Details) - Cancellation | Confirms cancellation (Yes) on 'Final Cancel Bottomsheet' | False |  | v1_cancel_yes | click | final_cancel_bottom_sheet | searching_vehicle | True |  | rsn | True |  |  |  |
| Vehicle Search | Searching Vehicle (Trip Details) - Cancellation | Does not cancel (No) on 'Final Cancel Bottomsheet' | False |  | v1_cancel_no | click | final_cancel_bottom_sheet | searching_vehicle | True |  | rsn | True |  |  |  |
| Vehicle Search | Searching Vehicle (Trip Details) - Insurance | Views 'Insurance Bottomsheet' | False |  | v1_insurance_btm_sheet | view | insurance_btm_sheet | searching_vehicle | True |  |  | True |  |  |  |
| Vehicle Search | Searching Vehicle (Trip Details) - Insurance | Clicks 'Close' (X) on 'Insurance Bottomsheet' | False |  | v1_close | click | insurance_btm_sheet | searching_vehicle | True |  |  | True |  |  |  |
| Vehicle Search | Searching Vehicle (Trip Details) - Insurance | Clicks 'Okay' on 'Insurance Bottomsheet' | False |  | v1_okay | click | insurance_btm_sheet | searching_vehicle | True |  |  | True |  |  |  |
| Vehicle Search | Searching Vehicle (Trip Details) - Insurance | Clicks 'Add Insurance' on 'Insurance Bottomsheet' | False |  | v1_add_ins | click | insurance_btm_sheet | searching_vehicle | True |  |  | True |  |  |  |
| Vehicle Search | Searching Vehicle (Trip Details) - Insurance | Clicks 'No' on 'Insurance Bottomsheet' | False |  | v1_no | click | insurance_btm_sheet | searching_vehicle | True |  |  | True |  |  |  |
| Vehicle Search | Searching Vehicle (Trip Details) - Insurance | Toggles insurance checkbox on 'Insurance Bottomsheet' | False |  | v1_ins_check | click | insurance_btm_sheet | searching_vehicle | True |  |  | True |  |  |  |
| Vehicle Search | Searching Vehicle (Trip Details) - Insurance | Clicks 'View Pricing' on 'Insurance' | False |  | v1_view_pricing | click | insurance | searching_vehicle | True |  |  | True |  |  |  |
| Vehicle Search | Searching Vehicle (Trip Details) - Insurance | Toggles insurance checkbox on 'Insurance' | False |  | v1_ins_check | click | insurance | searching_vehicle | True |  |  | True |  |  |  |
| Vehicle Search | Searching Vehicle (Trip Details) - Insurance | Clicks 'Add Insurance' on 'Insurance' | False |  | v1_add_insurance | click | insurance | searching_vehicle | True |  |  | True |  |  |  |
| Vehicle Search | Searching Vehicle (Trip Details) - Insurance | Clicks 'Remove Insurance' on 'Insurance' | False |  | v1_remove_pricing | click | insurance | searching_vehicle | False |  |  | True |  |  |  |
| Vehicle Search | Price Confirmation - Cancellation | Views 'Final Cancel Bottomsheet' | False |  | v1_final_cancel_bottom_sheet | view | final_cancel_bottom_sheet | price_confirmation | True |  | rsn | True |  |  |  |
| Vehicle Search | Price Confirmation - Cancellation | Confirms cancellation (Yes) on 'Final Cancel Bottomsheet' | False |  | v1_cancel_yes | click | final_cancel_bottom_sheet | price_confirmation | True |  | rsn | True |  |  |  |
| Vehicle Search | Price Confirmation - Cancellation | Does not cancel (No) on 'Final Cancel Bottomsheet' | False |  | v1_cancel_no | click | final_cancel_bottom_sheet | price_confirmation | True |  | rsn | True |  |  |  |
| Vehicle Search | Price Confirmation - Cancellation | Views 'Cancel Bottomsheet' | False |  | v1_cancel_bottom_sheet | view | cancel_bottom_sheet | price_confirmation | True |  |  | True |  |  |  |
| Vehicle Search | Price Confirmation - Cancellation | Selects a reason on 'Cancel Bottomsheet' | False |  | v1_reason_selected | click | cancel_bottom_sheet | price_confirmation | True |  |  | True |  |  |  |
| Vehicle Search | Price Confirmation - Cancellation | Clicks 'Submit' button on 'Cancel Bottomsheet' | False |  | v1_submit_btn | click | cancel_bottom_sheet | price_confirmation | True |  | reason | True |  |  |  |
| Vehicle Search | Price Confirmation - Cancellation | Clicks 'Modify' button on 'Cancel Bottomsheet' | False |  | v1_modify_btn | click | cancel_bottom_sheet | price_confirmation | True |  | reason | True |  |  |  |
| Trip Scheduled | Home Page - Vehicle Confirmation |  | False |  | v1_truck_on_hold | view |  | home_page | True |  |  | True |  |  |  |
| Trip Scheduled | Home Page - Vehicle Confirmation | Clicks 'Confirm Truck' | False |  | v1_confirm_truck | click |  | home_page | False |  |  | True |  |  |  |
| Trip Scheduled | Home Page - Vehicle Confirmation | Clicks 'Detail' on 'Confirm Deny Bottomsheet' | False |  | v1__detail | click | confirm_deny_btmsheet | home_page | True |  |  | True |  |  |  |
| Trip Scheduled | Home Page - Vehicle Confirmation | Clicks 'Accept' on 'Confirm Deny Bottomsheet' | False |  | v1_accept | click | confirm_deny_btmsheet | home_page | True |  |  | True |  |  |  |
| Trip Scheduled | Home Page - Vehicle Confirmation | Clicks 'Complete Detail' on 'Confirm Deny Bottomsheet' | False |  | v1_complete_detail | click | confirm_deny_btmsheet | home_page | True |  |  | True |  |  |  |
| Trip Scheduled | Home Page - Vehicle Confirmation | Clicks 'View Detail' on 'Confirm Deny Bottomsheet' | False |  | v1_view_detail | click | confirm_deny_btmsheet | home_page | True |  |  | True |  |  |  |
| Trip Scheduled | Vehicle Found - Confirm Details |  | True |  | v1_scheduled_preview | view |  | scheduled_preview | True |  | timer | True |  |  |  |
| Trip Scheduled | Vehicle Found - Confirm Details |  | False |  | v1_tnc | view |  | scheduled_preview | True |  | timer | True |  |  |  |
| Trip Scheduled | Vehicle Found - Confirm Details |  | False |  | v1_cancel_fee_accept | view |  | scheduled_preview | True |  | timer | True |  |  |  |
| Trip Scheduled | Vehicle Found - Confirm Details |  | False |  | v1_veh_info | view |  | scheduled_preview | True |  |  | True |  |  |  |
| Trip Scheduled | Vehicle Found - Confirm Details |  | False |  | v1_confirm_detail_warning | view |  | scheduled_preview | True |  | timer | True |  |  |  |
| Trip Scheduled | Vehicle Found - Confirm Details |  | False |  | v1_penalty_warning | view |  | scheduled_preview | True |  |  | True |  |  |  |
| Trip Scheduled | Vehicle Found - Confirm Details | Clicks 'Close' (X) | False |  | v1_close | click |  | scheduled_preview | True |  | idx | True |  |  |  |
| Trip Scheduled | Vehicle Found - Confirm Details | Clicks 'Confirm Truck' | True | Truck confirmed (TR) | v1_confirm_truck | click |  | scheduled_preview | True |  | timer | True |  |  |  |
| Trip Scheduled | Vehicle Found - Confirm Details | Clicks 'Confirm Details Scheduled Preview' | False |  | v1_confirm_details_scheduled_preview | click |  | scheduled_preview | False |  | timer | True |  |  |  |
| Trip Scheduled | Vehicle Found - Confirm Details - VIP Pass / Coupon |  | False |  | v1_explore_plans | view |  | scheduled_preview | False |  | action_type | True |  |  |  |
| Trip Scheduled | Vehicle Found - Confirm Details - VIP Pass / Coupon |  | False |  | v1_coupon | view |  | scheduled_preview | True |  |  | True |  |  |  |
| Trip Scheduled | Vehicle Found - Confirm Details - VIP Pass / Coupon |  | False |  | v1_promo_applied | view |  | scheduled_preview | False |  | disc_type | True |  |  |  |
| Trip Scheduled | Vehicle Found - Confirm Details - VIP Pass / Coupon |  | False |  | v1_renew_pass | view |  | scheduled_preview | False |  | action_type | True |  |  |  |
| Trip Scheduled | Vehicle Found - Confirm Details - Edit Booking | Clicks 'Reschedule' | False |  | v1_reschedule | click |  | scheduled_preview | True |  | timer | True |  |  |  |
| Trip Scheduled | Vehicle Found - Confirm Details - Cancellation | Clicks 'Cancel Booking' | False |  | v1_cancel_booking | click |  | scheduled_preview | True |  | timer | True |  |  |  |
| Trip Scheduled | Vehicle Found - Confirm Details - VIP Pass / Coupon | Clicks 'Add Pass' | False |  | v1_add_pass | click |  | scheduled_preview | True |  |  | True |  |  |  |
| Trip Scheduled | Vehicle Found - Confirm Details - VIP Pass / Coupon | Clicks 'Explore Plans' | False |  | v1_explore_plans | click |  | scheduled_preview | False |  |  | True |  |  |  |
| Trip Scheduled | Vehicle Found - Confirm Details - VIP Pass / Coupon | Clicks 'Save With Pass' | False |  | v1_save_with_pass | click |  | scheduled_preview | True |  |  | True |  |  |  |
| Trip Scheduled | Vehicle Found - Confirm Details - VIP Pass / Coupon | Clicks 'Coupon Action' | False |  | v1_coupon_action | click |  | scheduled_preview | True |  | enum_type | True |  |  |  |
| Trip Scheduled | Vehicle Found - Confirm Details - VIP Pass / Coupon | Clicks 'Pass Added' | False |  | v1_pass_added | click |  | scheduled_preview | True |  |  | True |  |  |  |
| Trip Scheduled | Vehicle Found - Confirm Details - VIP Pass / Coupon | Clicks 'Renew Pass' | False |  | v1_renew_pass | click |  | scheduled_preview | False |  |  | True |  |  |  |
| Trip Scheduled | Vehicle Found - Confirm Details - Insurance | Views 'Insurance Doc' | False |  | v1_insurance_doc | view | insurance_doc | scheduled_preview | True |  |  | True |  |  |  |
| Trip Scheduled | Vehicle Found - Confirm Details - Edit Booking | Views 'Trip Details' | False |  | v1_edit_btn | view | trip_details | scheduled_preview | True |  |  | True |  |  |  |
| Trip Scheduled | Vehicle Found - Confirm Details - Edit Booking | Clicks 'Edit' button on 'Trip Details' | False |  | v1_edit_btn | click | trip_details | scheduled_preview | True |  |  | True |  |  |  |
| Trip Scheduled | Vehicle Found - Confirm Details | Clicks 'Confirm Details' on 'Confirm Demand' | True | Booking details confirmed | v1_confirm_details | click | confirm_demand | scheduled_preview | True |  | timer | True |  |  |  |
| Trip Scheduled | Vehicle Found - Confirm Details | Clicks 'View Details' on 'Confirm Demand' | False |  | v1_view_details | click | confirm_demand | scheduled_preview | True |  | timer | True |  |  |  |
| Trip Scheduled | Vehicle Found - Confirm Details - VIP Pass / Coupon | Views 'Unlock Pass Bottomsheet' | False |  | v1_unlock_pass | view | unlock_pass_btmsheet | scheduled_preview | True |  | type | True |  |  |  |
| Trip Scheduled | Vehicle Found - Confirm Details - VIP Pass / Coupon | Clicks 'Conf Pass' on 'Unlock Pass Bottomsheet' | False |  | v1_conf_pass | click | unlock_pass_btmsheet | scheduled_preview | True |  |  | True |  |  |  |
| Trip Scheduled | Vehicle Found - Confirm Details - VIP Pass / Coupon | Clicks 'Explore Plans' on 'Unlock Pass Bottomsheet' | False |  | v1_explore_plans | click | unlock_pass_btmsheet | scheduled_preview | True |  |  | True |  |  |  |
| Trip Scheduled | Vehicle Found - Confirm Details - Cancellation | Views 'Cancel Bot' | False |  | v1_cancel_bot | view | cancel_bot | scheduled_preview | True |  | time | True |  |  |  |
| Trip Scheduled | Vehicle Found - Confirm Details - Cancellation | Clicks 'Continue' button on 'Cancel Bot' | False |  | v1_continue | click | cancel_bot | scheduled_preview | True |  | action | True |  |  |  |
| Trip Scheduled | Vehicle Found - Confirm Details - Cancellation | Clicks 'Close' (X) on 'Cancel Bot' | False |  | v1_close | click | cancel_bot | scheduled_preview | True |  | time | True |  |  |  |
| Trip Scheduled | Vehicle Found - Confirm Details | Views 'Veh Info' | False |  | v1_offer | view | veh_info | scheduled_preview | True |  | discount | True |  |  |  |
| Trip Scheduled | Vehicle Found - Confirm Details | Views 'Veh Info' | False |  | v1_badge | view | veh_info | scheduled_preview | True |  |  | True |  |  |  |
| Trip Scheduled | Vehicle Found - Confirm Details - Insurance | Clicks 'Remove Insurance' on 'Insurance' | False |  | v1_remove_pricing | click | insurance | scheduled_preview | False |  |  | True |  |  |  |
| Trip Scheduled | Vehicle Found - Confirm Details - Insurance | Clicks 'Update Pricing' on 'Insurance' | False |  | v1_update_pricing | click | insurance | scheduled_preview | True |  |  | True |  |  |  |
| Trip Scheduled | Vehicle Found - Confirm Details - Insurance | Clicks 'Add Insurance' on 'Insurance' | False |  | v1_add_insurance | click | insurance | scheduled_preview | True |  |  | True |  |  |  |
| Trip Scheduled | Vehicle Found - Confirm Details - Insurance | Clicks 'View Pricing' on 'Insurance' | False |  | v1_view_pricing | click | insurance | scheduled_preview | True |  |  | True |  |  |  |
| Trip Scheduled | Vehicle Found - Confirm Details - Insurance | Clicks 'Confirm' button on 'Update Ins Pricing' | False |  | v1_confim | click | update_ins_pricing | scheduled_preview | True |  |  | True |  |  |  |
| Trip Scheduled | Vehicle Found - Confirm Details - Insurance | Clicks 'OK' on 'Update Ins Pricing' | False |  | v1_ok | click | update_ins_pricing | scheduled_preview | True |  |  | True |  |  |  |
| Trip Scheduled | Vehicle Found - Confirm Details - Insurance | Clicks 'Close' (X) on 'Update Ins Pricing' | False |  | v1_close | click | update_ins_pricing | scheduled_preview | True |  |  | True |  |  |  |
| Trip Scheduled | Vehicle Found - Confirm Details - Insurance | Clicks 'View Fragile Items' on 'Update Ins Pricing' | False |  | v1_view_fragile | click | update_ins_pricing | scheduled_preview | True |  |  | True |  |  |  |
| Trip Scheduled | Vehicle Found - Confirm Details - Insurance | Views 'Insurance Bottomsheet' | False |  | v1_insurance_btm_sheet | view | insurance_btm_sheet | scheduled_preview | True |  |  | True |  |  |  |
| Trip Scheduled | Vehicle Found - Confirm Details - Insurance | Clicks 'Add Insurance' on 'Insurance Bottomsheet' | False |  | v1_add_ins | click | insurance_btm_sheet | scheduled_preview | True |  |  | True |  |  |  |
| Trip Scheduled | Vehicle Found - Confirm Details - Insurance | Clicks 'Close' (X) on 'Insurance Bottomsheet' | False |  | v1_close | click | insurance_btm_sheet | scheduled_preview | True |  |  | True |  |  |  |
| Trip Scheduled | Vehicle Found - Confirm Details - Insurance | Clicks 'No' on 'Insurance Bottomsheet' | False |  | v1_no | click | insurance_btm_sheet | scheduled_preview | True |  |  | True |  |  |  |
| Trip Scheduled | Vehicle Found - Confirm Details - Insurance | Clicks 'OK' on 'Fragile Items List' | False |  | v1_ok | click | fragile_items_list | scheduled_preview | True |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled |  | True |  | v1_veh_info | view |  | scheduled | True |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled |  | False |  | v1_tnc | view |  | scheduled | True |  | timer | True |  |  |  |
| Trip Scheduled | Trip Scheduled |  | False |  | v1_cancel_fee_accept | view |  | scheduled | True |  | timer | True |  |  |  |
| Trip Scheduled | Trip Scheduled |  | False |  | v1_call_driver_btm_sheet | view |  | scheduled | True |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled |  | False |  | v1_penalty_warning | view |  | scheduled | True |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled | Clicks 'Close' (X) | False |  | v1_close | click |  | scheduled | True |  | idx | True |  |  |  |
| Trip Scheduled | Trip Scheduled | Clicks 'Confirm Truck' | True | Truck confirmed (TR) | v1_confirm_truck | click |  | scheduled | True |  | timer | True |  |  |  |
| Trip Scheduled | Trip Scheduled | Clicks 'Call Driver' | False |  | v1_call_driver | click |  | scheduled | True |  | otp | True |  |  |  |
| Trip Scheduled | Trip Scheduled | Clicks 'Confirm Truck Scheduled' | False |  | v1_confirm_truck_scheduled | click |  | scheduled | False |  | timer | True |  |  |  |
| Trip Scheduled | Trip Scheduled | Clicks 'Call Driver Close' | False |  | v1_call_driver_close | click |  | scheduled | True |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled | Clicks 'Back' arrow | False |  | v1_back_btn | click | top_nav | scheduled | True |  | timer | True |  |  |  |
| Trip Scheduled | Trip Scheduled | Switches trip details tab | False |  | v1_screen_fliter | click | top_nav | scheduled | True |  | segment | True |  |  |  |
| Trip Scheduled | Trip Scheduled | Clicks 'Complete Kyc' | False |  | v1_complete_kyc | click | bottom_nav | scheduled | True |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled - VIP Pass / Coupon |  | False |  | v1_explore_plans | view |  | scheduled | False |  | action_type | True |  |  |  |
| Trip Scheduled | Trip Scheduled - VIP Pass / Coupon |  | False |  | v1_coupon | view |  | scheduled | True |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled - VIP Pass / Coupon |  | False |  | v1_promo_applied | view |  | scheduled | False |  | disc_type | True |  |  |  |
| Trip Scheduled | Trip Scheduled - VIP Pass / Coupon |  | False |  | v1_renew_pass | view |  | scheduled | False |  | action_type | True |  |  |  |
| Trip Scheduled | Trip Scheduled - Cancellation |  | False |  | v1_cancel_fee_btmsheet | view |  | scheduled | True |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled - VIP Pass / Coupon | Clicks 'Explore Plans' | False |  | v1_explore_plans | click |  | scheduled | False |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled - VIP Pass / Coupon | Clicks 'Add Pass' | False |  | v1_add_pass | click |  | scheduled | True |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled - VIP Pass / Coupon | Clicks 'Save With Pass' | False |  | v1_save_with_pass | click |  | scheduled | True |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled - VIP Pass / Coupon | Clicks 'Coupon Action' | False |  | v1_coupon_action | click |  | scheduled | True |  | enum_type | True |  |  |  |
| Trip Scheduled | Trip Scheduled - VIP Pass / Coupon | Clicks 'Pass Added' | False |  | v1_pass_added | click |  | scheduled | True |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled - VIP Pass / Coupon | Clicks 'Renew Pass' | False |  | v1_renew_pass | click |  | scheduled | False |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled | Views 'Veh Info' | False |  | v1_offer | view | veh_info | scheduled | True |  | discount | True |  |  |  |
| Trip Scheduled | Trip Scheduled | Views 'Veh Info' | False |  | v1_badge | view | veh_info | scheduled | True |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled | Views 'Trip Details' | False |  | v1_halt_info | view | trip_details | scheduled | True |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled - Edit Booking | Views 'Trip Details' | False |  | v1_edit_btn | view | trip_details | scheduled | True |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled | Views 'Trip Details' | False |  | v1_veh_status | view | trip_details | scheduled | True |  | start | True |  |  |  |
| Trip Scheduled | Trip Scheduled | Views 'Trip Details' | False |  | v1_macro_event_post_dr | view | trip_details | scheduled | False |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled - Invoices, Expenses & Dues | Clicks 'View Details' on 'Trip Details' | False |  | v1_view_details_btn | click | trip_details | scheduled | True |  | expense_type | True |  |  |  |
| Trip Scheduled | Trip Scheduled - Edit Booking | Clicks 'Edit Booking' button on 'Trip Details' | False |  | v1_edit_booking_btn | click | trip_details | scheduled | True |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled - Edit Booking | Clicks 'Edit' button on 'Trip Details' | False |  | v1_edit_btn | click | trip_details | scheduled | True |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled - Insurance | Views 'Insurance Doc' | False |  | v1_insurance_doc | view | insurance_doc | scheduled | True |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled | Views 'Post Plc Educate' | False |  | v1_truck_on_hold | view | post_plc_educate | scheduled | True |  | timer | True |  |  |  |
| Trip Scheduled | Trip Scheduled | Clicks 'Accept' on 'Confirm Demand' | True | Truck accepted | v1_accept | click | confirm_demand | scheduled | True |  | timer | True |  |  |  |
| Trip Scheduled | Trip Scheduled | Clicks 'View Details' on 'Confirm Demand' | False |  | v1_view_details | click | confirm_demand | scheduled | True |  | timer | True |  |  |  |
| Trip Scheduled | Trip Scheduled - Cancellation | Clicks 'Cancel' on 'Conf Cancel Bottomsheet' | False |  | v1_cancel | click | conf_cancel_bottomsheet | scheduled | True |  | timer | True |  |  |  |
| Trip Scheduled | Trip Scheduled - Cancellation | Views 'Cancel Bot' | False |  | v1_cancel_bot | view | cancel_bot | scheduled | True |  | time | True |  |  |  |
| Trip Scheduled | Trip Scheduled - Cancellation | Clicks 'Continue' button on 'Cancel Bot' | False |  | v1_continue | click | cancel_bot | scheduled | True |  | action | True |  |  |  |
| Trip Scheduled | Trip Scheduled - Cancellation | Clicks 'Close' (X) on 'Cancel Bot' | False |  | v1_close | click | cancel_bot | scheduled | True |  | time | True |  |  |  |
| Trip Scheduled | Trip Scheduled - Cancellation | Clicks 'Cancel' on 'Tracking' | False |  | v1_cancel | click | tracking | scheduled | True |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled - Cancellation | Views 'Cancellation Bottomsheet' | False |  | v1_cancellation_bottom_sheet | view | cancellation_bottom_sheet | scheduled | True |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled - Cancellation | Clicks 'Cancel Booking' on 'Cancellation Bottomsheet' | False |  | v1_cancel_booking | click | cancellation_bottomsheet | scheduled | True |  | reason | True |  |  |  |
| Trip Scheduled | Trip Scheduled - Cancellation | Clicks 'Cancel Booking Close' on 'Cancellation Bottomsheet' | False |  | v1_cancel_booking_close | click | cancellation_bottomsheet | scheduled | True |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled - Cancellation | Clicks 'Change Booking' button on 'Cancellation Bottomsheet' | False |  | v1_change_booking_btn | click | cancellation_bottomsheet | scheduled | True |  | reason | True |  |  |  |
| Trip Scheduled | Trip Scheduled - Cancellation | Views 'Final Cancel Bottomsheet' | False |  | v1_final_cancel_bottom_sheet | view | final_cancel_bottom_sheet | scheduled | True |  | rsn | True |  |  |  |
| Trip Scheduled | Trip Scheduled - Cancellation | Confirms cancellation (Yes) on 'Final Cancel Bottomsheet' | False |  | v1_cancel_yes | click | final_cancel_bottom_sheet | scheduled | True |  | rsn | True |  |  |  |
| Trip Scheduled | Trip Scheduled - Cancellation | Does not cancel (No) on 'Final Cancel Bottomsheet' | False |  | v1_cancel_no | click | final_cancel_bottom_sheet | scheduled | True |  | rsn | True |  |  |  |
| Trip Scheduled | Trip Scheduled - VIP Pass / Coupon | Views 'Unlock Pass Bottomsheet' | False |  | v1_unlock_pass | view | unlock_pass_btmsheet | scheduled | True |  | type | True |  |  |  |
| Trip Scheduled | Trip Scheduled - VIP Pass / Coupon | Clicks 'Conf Pass' on 'Unlock Pass Bottomsheet' | False |  | v1_conf_pass | click | unlock_pass_btmsheet | scheduled | True |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled - VIP Pass / Coupon | Clicks 'Explore Plans' on 'Unlock Pass Bottomsheet' | False |  | v1_explore_plans | click | unlock_pass_btmsheet | scheduled | True |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled - Insurance | Clicks 'Confirm' button on 'Update Ins Pricing' | False |  | v1_confim | click | update_ins_pricing | scheduled | True |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled - Insurance | Clicks 'OK' on 'Update Ins Pricing' | False |  | v1_ok | click | update_ins_pricing | scheduled | True |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled - Insurance | Clicks 'Close' (X) on 'Update Ins Pricing' | False |  | v1_close | click | update_ins_pricing | scheduled | True |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled - Insurance | Clicks 'View Fragile Items' on 'Update Ins Pricing' | False |  | v1_view_fragile | click | update_ins_pricing | scheduled | True |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled - Insurance | Toggles insurance checkbox on 'Insurance' | False |  | v1_ins_check | click | insurance | scheduled | True |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled - Insurance | Clicks 'Remove Insurance' on 'Insurance' | False |  | v1_remove_pricing | click | insurance | scheduled | False |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled - Insurance | Clicks 'Update Pricing' on 'Insurance' | False |  | v1_update_pricing | click | insurance | scheduled | True |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled - Insurance | Clicks 'View Pricing' on 'Insurance' | False |  | v1_view_pricing | click | insurance | scheduled | True |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled - Insurance | Clicks 'Add Insurance' on 'Insurance' | False |  | v1_add_insurance | click | insurance | scheduled | True |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled - Invoices, Expenses & Dues | Views 'Detention Charge Bottomsheet' | False |  | v1_detention_charge_bottomsheet | view | detention_charge_bottomsheet | scheduled | True |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled - Invoices, Expenses & Dues | Clicks 'Close' (X) on 'Detention Charge Bottomsheet' | False |  | v1_close | click | detention_charge_bottomsheet | scheduled | True |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled - Invoices, Expenses & Dues | Clicks 'Got it' on 'Detention Charge Bottomsheet' | False |  | v1_got_it | click | detention_charge_bottomsheet | scheduled | True |  | expense_type | True |  |  |  |
| Trip Scheduled | Trip Scheduled - Invoices, Expenses & Dues | Clicks 'Read Policy' on 'Detention Charge Bottomsheet' | False |  | v1_read_policy | click | detention_charge_bottomsheet | scheduled | True |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled - Invoices, Expenses & Dues | Clicks 'Submit' button on 'Extra Charge Policy Popup' | False |  | v1_submit_btn | click | extra_charge_policy_popup | scheduled | True |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled - Invoices, Expenses & Dues | Views 'Past Trip Balance' | False |  | v1_past_payment | view | past_trip_balance | scheduled | True |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled - Invoices, Expenses & Dues | Clicks 'Past View Detail' on 'Past Trip Balance' | False |  | v1_past_view_detail | click | past_trip_balance | scheduled | True |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled - Help / Ticket | Clicks 'Raise Issue' | False |  | v1_raise_issue | click | bottom_nav | scheduled | True |  | expense_type | True |  |  |  |
| Trip Scheduled | Trip Scheduled - Insurance | Views 'Insurance Bottomsheet' | False |  | v1_insurance_btm_sheet | view | insurance_btm_sheet | scheduled | True |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled - Insurance | Clicks 'Close' (X) on 'Insurance Bottomsheet' | False |  | v1_close | click | insurance_btm_sheet | scheduled | True |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled - Insurance | Clicks 'Add Insurance' on 'Insurance Bottomsheet' | False |  | v1_add_ins | click | insurance_btm_sheet | scheduled | True |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled - Insurance | Clicks 'No' on 'Insurance Bottomsheet' | False |  | v1_no | click | insurance_btm_sheet | scheduled | True |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled - Insurance | Toggles insurance checkbox on 'Insurance Bottomsheet' | False |  | v1_ins_check | click | insurance_btm_sheet | scheduled | True |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled | Views 'Demand Stage' | False |  | v1_dmg_guidlines | view | demand_stage | scheduled | True |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled | Clicks 'Dmg Guidlines' on 'Demand Stage' | False |  | v1_dmg_guidlines | click | demand_stage | scheduled | True |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled | Clicks 'Call Driver' on 'Driver Details' | False |  | v1_call_driver | click | driver_details | scheduled | True |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled | Expands section on 'Driver Details' | False |  | v1_expand | click | driver_details | scheduled | True |  | action | True |  |  |  |
| Trip Scheduled | Trip Scheduled | Expands section on 'Transit Information' | False |  | v1_expand | click | transit_information | scheduled | True |  | action | True |  |  |  |
| Trip Scheduled | Trip Scheduled - Help / Ticket | Clicks 'Create Ticket' on 'Help Support' | False |  | v1_create_ticket | click | help_support | scheduled | True |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled - Help / Ticket | Clicks 'Need Help' on 'Help Widget' | False |  | v1_need_help | click | help_widget | scheduled | True |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled - Insurance | Clicks 'OK' on 'Fragile Items List' | False |  | v1_ok | click | fragile_items_list | scheduled | True |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled - Bilti / E-way / OTP | Views 'Otp View' | False |  | v1_otp | view | otp_view | scheduled | True |  |  | True |  |  |  |
| Trip Scheduled | Trip Scheduled - Bilti / E-way / OTP | Clicks 'Complete Kyc Payment' on 'Otp View' | False |  | v1_complete_kyc_payment | click | otp_view | scheduled | True |  | action | True |  |  |  |
| Trip Scheduled | Trip Scheduled | Expands section on 'Trip Information' | False |  | v1_expand | click | trip_information | scheduled | True |  | action | True |  |  |  |
| Trip Scheduled | Slot Update Overlay |  | False |  | v1_overlay | view |  | confirm_deny_overlay | True |  | m_s_p | True |  |  |  |
| Trip Scheduled | Going To Load - Vehicle Confirmation |  | False |  | v1_penalty_warning | view |  | going_to_load | True |  |  | True |  |  |  |
| Trip Scheduled | At Unloading - Vehicle Confirmation |  | False |  | v1_confirm_detail_warning | view |  | at_unloading | True |  | timer | True |  |  |  |
| Trip Scheduled | Push Notification - Vehicle Confirmation | Clicks 'Close' (X) on 'Confirm Demand' | False |  | v1_close | click | confirm_demand | notification | True |  | mis_time | True |  |  |  |
| Trip Scheduled | Push Notification - Vehicle Confirmation | Clicks 'Accept' on 'Confirm Demand' | False |  | v1_accept | click | confirm_demand | notification | True |  | timer | True |  |  |  |
| Trip Edit | Vehicle Found - Confirm Details - Edit Booking | Clicks 'Reschedule' | False |  | v1_reschedule | click |  | scheduled_preview | True |  | timer | True |  |  |  |
| Trip Edit | Vehicle Found - Confirm Details - Edit Booking | Views 'Trip Details' | False |  | v1_edit_btn | view | trip_details | scheduled_preview | True |  |  | True |  |  |  |
| Trip Edit | Vehicle Found - Confirm Details - Edit Booking | Clicks 'Edit' button on 'Trip Details' | False |  | v1_edit_btn | click | trip_details | scheduled_preview | True |  |  | True |  |  |  |
| Trip Edit | Trip Scheduled - Edit Booking | Views 'Trip Details' | False |  | v1_edit_btn | view | trip_details | scheduled | True |  |  | True |  |  |  |
| Trip Edit | Trip Scheduled - Edit Booking | Clicks 'Edit Booking' button on 'Trip Details' | False |  | v1_edit_booking_btn | click | trip_details | scheduled | True |  |  | True |  |  |  |
| Trip Edit | Trip Scheduled - Edit Booking | Clicks 'Edit' button on 'Trip Details' | False |  | v1_edit_btn | click | trip_details | scheduled | True |  |  | True |  |  |  |
| Trip Edit | Edit Date & Time |  | True |  | v1_date_time_confirmation | view |  | date_time_confirmation | True |  |  | True |  |  |  |
| Trip Edit | Edit Date & Time | Clicks 'Continue' button | False |  | v1_continue_btn | click | bottom_nav | date_time_confirmation | True |  | dr_slot | True |  |  |  |
| Trip Edit | Edit Date & Time | Clicks 'Back' arrow | False |  | v1_back_btn | click | top_nav | date_time_confirmation | True |  | timer | True |  |  |  |
| Trip Edit | Edit Booking Preview |  | True |  | v1_demand_detail_update_preview | view |  | demand_detail_update_preview | True |  |  | True |  |  |  |
| Trip Edit | Edit Booking Preview | Clicks 'Back' arrow | False |  | v1_back_btn | click | top_nav | demand_detail_update_preview | True |  | timer | True |  |  |  |
| Trip Edit | Edit Booking Preview | Clicks 'Edit Veh Type' on 'Update Details' | False |  | v1_edit_veh_type | click | update_details | demand_detail_update_preview | True |  |  | True |  |  |  |
| Trip Edit | Edit Booking Preview | Clicks 'Add Via Points' on 'Update Details' | False |  | v1_add_via_points | click | update_details | demand_detail_update_preview | True |  |  | True |  |  |  |
| Trip Edit | Edit Booking Preview | Clicks 'Edit Date Time' on 'Update Details' | False |  | v1_edit_date_time | click | update_details | demand_detail_update_preview | True |  |  | True |  |  |  |
| Trip Edit | Going To Load - Edit Booking | Views 'Trip Details' | False |  | v1_edit_btn | view | trip_details | going_to_load | True |  |  | True |  |  |  |
| Trip Edit | Going To Load - Edit Booking | Clicks 'Edit Booking' button on 'Trip Details' | False |  | v1_edit_booking_btn | click | trip_details | going_to_load | True |  |  | True |  |  |  |
| Trip Edit | Going To Load - Edit Booking | Clicks 'Edit' button on 'Trip Details' | False |  | v1_edit_btn | click | trip_details | going_to_load | True |  |  | True |  |  |  |
| Trip Edit | At Loading - Edit Booking | Views 'Trip Details' | False |  | v1_edit_btn | view | trip_details | at_loading | True |  |  | True |  |  |  |
| Trip Edit | At Loading - Edit Booking | Clicks 'Edit Booking' button on 'Trip Details' | False |  | v1_edit_booking_btn | click | trip_details | at_loading | True |  |  | True |  |  |  |
| Trip Edit | At Loading - Edit Booking | Clicks 'Edit' button on 'Trip Details' | False |  | v1_edit_btn | click | trip_details | at_loading | True |  |  | True |  |  |  |
| Trip Edit | In Transit - Edit Booking | Views 'Trip Details' | False |  | v1_edit_btn | view | trip_details | in_transit | True |  |  | True |  |  |  |
| Trip Edit | In Transit - Edit Booking | Clicks 'Edit' button on 'Trip Details' | False |  | v1_edit_btn | click | trip_details | in_transit | True |  |  | True |  |  |  |
| Trip Edit | At Unloading - Edit Booking | Views 'Trip Details' | False |  | v1_edit_btn | view | trip_details | at_unloading | True |  |  | True |  |  |  |
| Trip Edit | At Unloading - Edit Booking | Clicks 'Edit' button on 'Trip Details' | False |  | v1_edit_btn | click | trip_details | at_unloading | True |  |  | True |  |  |  |
| Trip Edit | Trip End - Edit Booking | Views 'Trip Details' | False |  | v1_edit_btn | view | trip_details | trip_end | True |  |  | True |  |  |  |
| Trip Edit | Trip End - Edit Booking | Clicks 'Edit' button on 'Trip Details' | False |  | v1_edit_btn | click | trip_details | trip_end | True |  |  | True |  |  |  |
| Cancellation | Searching Price - Cancellation | Views 'Cancel Bottomsheet' | False |  | v1_cancel_bottom_sheet | view | cancel_bottom_sheet | searching_price | True |  |  | True |  |  |  |
| Cancellation | Searching Price - Cancellation | Selects a reason on 'Cancel Bottomsheet' | False |  | v1_reason_selected | click | cancel_bottom_sheet | searching_price | True |  |  | True |  |  |  |
| Cancellation | Searching Price - Cancellation | Clicks 'Submit' button on 'Cancel Bottomsheet' | False |  | v1_submit_btn | click | cancel_bottom_sheet | searching_price | True |  | reason | True |  |  |  |
| Cancellation | Searching Price - Cancellation | Clicks 'Modify' button on 'Cancel Bottomsheet' | False |  | v1_modify_btn | click | cancel_bottom_sheet | searching_price | True |  | reason | True |  |  |  |
| Cancellation | Vehicle Searching - Cancellation | Views 'Cancel Bot' | False |  | v1_cancel_bot | view | cancel_bot | veh_searching | True |  | time | True |  |  |  |
| Cancellation | Vehicle Searching - Cancellation | Clicks 'Continue' button on 'Cancel Bot' | False |  | v1_continue | click | cancel_bot | veh_searching | True |  | action | True |  |  |  |
| Cancellation | Vehicle Searching - Cancellation | Clicks 'Close' (X) on 'Cancel Bot' | False |  | v1_close | click | cancel_bot | veh_searching | True |  | time | True |  |  |  |
| Cancellation | Searching Vehicle (Trip Details) - Cancellation | Views 'Cancellation Bottomsheet' | False |  | v1_cancellation_bottom_sheet | view | cancellation_bottom_sheet | searching_vehicle | True |  |  | True |  |  |  |
| Cancellation | Searching Vehicle (Trip Details) - Cancellation | Clicks 'Cancel Booking' on 'Cancellation Bottomsheet' | False |  | v1_cancel_booking | click | cancellation_bottomsheet | searching_vehicle | True |  | reason | True |  |  |  |
| Cancellation | Searching Vehicle (Trip Details) - Cancellation | Clicks 'Cancel Booking Close' on 'Cancellation Bottomsheet' | False |  | v1_cancel_booking_close | click | cancellation_bottomsheet | searching_vehicle | True |  |  | True |  |  |  |
| Cancellation | Searching Vehicle (Trip Details) - Cancellation | Views 'Final Cancel Bottomsheet' | False |  | v1_final_cancel_bottom_sheet | view | final_cancel_bottom_sheet | searching_vehicle | True |  | rsn | True |  |  |  |
| Cancellation | Searching Vehicle (Trip Details) - Cancellation | Confirms cancellation (Yes) on 'Final Cancel Bottomsheet' | False |  | v1_cancel_yes | click | final_cancel_bottom_sheet | searching_vehicle | True |  | rsn | True |  |  |  |
| Cancellation | Searching Vehicle (Trip Details) - Cancellation | Does not cancel (No) on 'Final Cancel Bottomsheet' | False |  | v1_cancel_no | click | final_cancel_bottom_sheet | searching_vehicle | True |  | rsn | True |  |  |  |
| Cancellation | Price Confirmation - Cancellation | Views 'Final Cancel Bottomsheet' | False |  | v1_final_cancel_bottom_sheet | view | final_cancel_bottom_sheet | price_confirmation | True |  | rsn | True |  |  |  |
| Cancellation | Price Confirmation - Cancellation | Confirms cancellation (Yes) on 'Final Cancel Bottomsheet' | False |  | v1_cancel_yes | click | final_cancel_bottom_sheet | price_confirmation | True |  | rsn | True |  |  |  |
| Cancellation | Price Confirmation - Cancellation | Does not cancel (No) on 'Final Cancel Bottomsheet' | False |  | v1_cancel_no | click | final_cancel_bottom_sheet | price_confirmation | True |  | rsn | True |  |  |  |
| Cancellation | Price Confirmation - Cancellation | Views 'Cancel Bottomsheet' | False |  | v1_cancel_bottom_sheet | view | cancel_bottom_sheet | price_confirmation | True |  |  | True |  |  |  |
| Cancellation | Price Confirmation - Cancellation | Selects a reason on 'Cancel Bottomsheet' | False |  | v1_reason_selected | click | cancel_bottom_sheet | price_confirmation | True |  |  | True |  |  |  |
| Cancellation | Price Confirmation - Cancellation | Clicks 'Submit' button on 'Cancel Bottomsheet' | False |  | v1_submit_btn | click | cancel_bottom_sheet | price_confirmation | True |  | reason | True |  |  |  |
| Cancellation | Price Confirmation - Cancellation | Clicks 'Modify' button on 'Cancel Bottomsheet' | False |  | v1_modify_btn | click | cancel_bottom_sheet | price_confirmation | True |  | reason | True |  |  |  |
| Cancellation | Vehicle Found - Confirm Details - Cancellation | Clicks 'Cancel Booking' | False |  | v1_cancel_booking | click |  | scheduled_preview | True |  | timer | True |  |  |  |
| Cancellation | Vehicle Found - Confirm Details - Cancellation | Views 'Cancel Bot' | False |  | v1_cancel_bot | view | cancel_bot | scheduled_preview | True |  | time | True |  |  |  |
| Cancellation | Vehicle Found - Confirm Details - Cancellation | Clicks 'Continue' button on 'Cancel Bot' | False |  | v1_continue | click | cancel_bot | scheduled_preview | True |  | action | True |  |  |  |
| Cancellation | Vehicle Found - Confirm Details - Cancellation | Clicks 'Close' (X) on 'Cancel Bot' | False |  | v1_close | click | cancel_bot | scheduled_preview | True |  | time | True |  |  |  |
| Cancellation | Trip Scheduled - Cancellation |  | False |  | v1_cancel_fee_btmsheet | view |  | scheduled | True |  |  | True |  |  |  |
| Cancellation | Trip Scheduled - Cancellation | Clicks 'Cancel' on 'Conf Cancel Bottomsheet' | False |  | v1_cancel | click | conf_cancel_bottomsheet | scheduled | True |  | timer | True |  |  |  |
| Cancellation | Trip Scheduled - Cancellation | Views 'Cancel Bot' | False |  | v1_cancel_bot | view | cancel_bot | scheduled | True |  | time | True |  |  |  |
| Cancellation | Trip Scheduled - Cancellation | Clicks 'Continue' button on 'Cancel Bot' | False |  | v1_continue | click | cancel_bot | scheduled | True |  | action | True |  |  |  |
| Cancellation | Trip Scheduled - Cancellation | Clicks 'Close' (X) on 'Cancel Bot' | False |  | v1_close | click | cancel_bot | scheduled | True |  | time | True |  |  |  |
| Cancellation | Trip Scheduled - Cancellation | Clicks 'Cancel' on 'Tracking' | False |  | v1_cancel | click | tracking | scheduled | True |  |  | True |  |  |  |
| Cancellation | Trip Scheduled - Cancellation | Views 'Cancellation Bottomsheet' | False |  | v1_cancellation_bottom_sheet | view | cancellation_bottom_sheet | scheduled | True |  |  | True |  |  |  |
| Cancellation | Trip Scheduled - Cancellation | Clicks 'Cancel Booking' on 'Cancellation Bottomsheet' | False |  | v1_cancel_booking | click | cancellation_bottomsheet | scheduled | True |  | reason | True |  |  |  |
| Cancellation | Trip Scheduled - Cancellation | Clicks 'Cancel Booking Close' on 'Cancellation Bottomsheet' | False |  | v1_cancel_booking_close | click | cancellation_bottomsheet | scheduled | True |  |  | True |  |  |  |
| Cancellation | Trip Scheduled - Cancellation | Clicks 'Change Booking' button on 'Cancellation Bottomsheet' | False |  | v1_change_booking_btn | click | cancellation_bottomsheet | scheduled | True |  | reason | True |  |  |  |
| Cancellation | Trip Scheduled - Cancellation | Views 'Final Cancel Bottomsheet' | False |  | v1_final_cancel_bottom_sheet | view | final_cancel_bottom_sheet | scheduled | True |  | rsn | True |  |  |  |
| Cancellation | Trip Scheduled - Cancellation | Confirms cancellation (Yes) on 'Final Cancel Bottomsheet' | False |  | v1_cancel_yes | click | final_cancel_bottom_sheet | scheduled | True |  | rsn | True |  |  |  |
| Cancellation | Trip Scheduled - Cancellation | Does not cancel (No) on 'Final Cancel Bottomsheet' | False |  | v1_cancel_no | click | final_cancel_bottom_sheet | scheduled | True |  | rsn | True |  |  |  |
| Cancellation | Going To Load - Cancellation |  | False |  | v1_cancel_fee_btmsheet | view |  | going_to_load | True |  |  | True |  |  |  |
| Cancellation | Going To Load - Cancellation | Views 'Cancel Bot' | False |  | v1_cancel_bot | view | cancel_bot | going_to_load | True |  | time | True |  |  |  |
| Cancellation | Going To Load - Cancellation | Clicks 'Continue' button on 'Cancel Bot' | False |  | v1_continue | click | cancel_bot | going_to_load | True |  | action | True |  |  |  |
| Cancellation | Going To Load - Cancellation | Clicks 'Close' (X) on 'Cancel Bot' | False |  | v1_close | click | cancel_bot | going_to_load | True |  | time | True |  |  |  |
| Cancellation | Going To Load - Cancellation | Clicks 'Cancel' on 'Tracking' | False |  | v1_cancel | click | tracking | going_to_load | True |  |  | True |  |  |  |
| Cancellation | Going To Load - Cancellation | Views 'Cancellation Bottomsheet' | False |  | v1_cancellation_bottom_sheet | view | cancellation_bottom_sheet | going_to_load | True |  |  | True |  |  |  |
| Cancellation | Going To Load - Cancellation | Clicks 'Cancel Booking' on 'Cancellation Bottomsheet' | False |  | v1_cancel_booking | click | cancellation_bottomsheet | going_to_load | True |  | reason | True |  |  |  |
| Cancellation | Going To Load - Cancellation | Clicks 'Change Booking' button on 'Cancellation Bottomsheet' | False |  | v1_change_booking_btn | click | cancellation_bottomsheet | going_to_load | True |  | reason | True |  |  |  |
| Cancellation | Going To Load - Cancellation | Clicks 'Cancel Booking Close' on 'Cancellation Bottomsheet' | False |  | v1_cancel_booking_close | click | cancellation_bottomsheet | going_to_load | True |  |  | True |  |  |  |
| Cancellation | Going To Load - Cancellation | Views 'Final Cancel Bottomsheet' | False |  | v1_final_cancel_bottom_sheet | view | final_cancel_bottom_sheet | going_to_load | True |  | rsn | True |  |  |  |
| Cancellation | Going To Load - Cancellation | Confirms cancellation (Yes) on 'Final Cancel Bottomsheet' | False |  | v1_cancel_yes | click | final_cancel_bottom_sheet | going_to_load | True |  | rsn | True |  |  |  |
| Cancellation | Going To Load - Cancellation | Does not cancel (No) on 'Final Cancel Bottomsheet' | False |  | v1_cancel_no | click | final_cancel_bottom_sheet | going_to_load | True |  | rsn | True |  |  |  |
| Cancellation | Going To Load - Cancellation | Clicks 'Raise Issue' on 'Cancel Fee Bottomsheet' | False |  | v1_raise_issue | click | cancel_fee_btmsheet | going_to_load | True |  | demand_id | True |  |  |  |
| Cancellation | Going To Load - Cancellation | Views 'Cancel Bottomsheet' | False |  | v1_cancel_bottom_sheet | view | cancel_bottom_sheet | going_to_load | True |  |  | True |  |  |  |
| Cancellation | Going To Load - Cancellation | Selects a reason on 'Cancel Bottomsheet' | False |  | v1_reason_selected | click | cancel_bottom_sheet | going_to_load | True |  |  | True |  |  |  |
| Cancellation | Going To Load - Cancellation | Clicks 'Submit' button on 'Cancel Bottomsheet' | False |  | v1_submit_btn | click | cancel_bottom_sheet | going_to_load | True |  | reason | True |  |  |  |
| Cancellation | At Loading - Cancellation |  | False |  | v1_cancel_fee_btmsheet | view |  | at_loading | True |  |  | True |  |  |  |
| Cancellation | At Loading - Cancellation | Clicks 'Cancel' on 'Tracking' | False |  | v1_cancel | click | tracking | at_loading | True |  |  | True |  |  |  |
| Cancellation | At Loading - Cancellation | Clicks 'Cancel Booking' button on 'Cancellation Bottomsheet' | False |  | v1_cancel_booking_btn | click | cancellation_bottomsheet | at_loading | True |  |  | True |  |  |  |
| Cancellation | At Loading - Cancellation | Clicks 'Cancel Booking' on 'Cancellation Bottomsheet' | False |  | v1_cancel_booking | click | cancellation_bottomsheet | at_loading | True |  | reason | True |  |  |  |
| Cancellation | At Loading - Cancellation | Clicks 'Close' (X) on 'Cancellation Bottomsheet' | False |  | v1_close_btn | click | cancellation_bottomsheet | at_loading | True |  |  | True |  |  |  |
| Cancellation | At Loading - Cancellation | Clicks 'Change Booking' button on 'Cancellation Bottomsheet' | False |  | v1_change_booking_btn | click | cancellation_bottomsheet | at_loading | True |  | reason | True |  |  |  |
| Cancellation | At Loading - Cancellation | Clicks 'Cancel Booking Close' on 'Cancellation Bottomsheet' | False |  | v1_cancel_booking_close | click | cancellation_bottomsheet | at_loading | True |  |  | True |  |  |  |
| Cancellation | At Loading - Cancellation | Views 'Cancellation Bottomsheet' | False |  | v1_cancellation_bottom_sheet | view | cancellation_bottom_sheet | at_loading | True |  |  | True |  |  |  |
| Cancellation | At Loading - Cancellation | Views 'Final Cancel Bottomsheet' | False |  | v1_final_cancel_bottom_sheet | view | final_cancel_bottom_sheet | at_loading | True |  | rsn | True |  |  |  |
| Cancellation | At Loading - Cancellation | Confirms cancellation (Yes) on 'Final Cancel Bottomsheet' | False |  | v1_cancel_yes | click | final_cancel_bottom_sheet | at_loading | True |  | rsn | True |  |  |  |
| Cancellation | At Loading - Cancellation | Does not cancel (No) on 'Final Cancel Bottomsheet' | False |  | v1_cancel_no | click | final_cancel_bottom_sheet | at_loading | True |  | rsn | True |  |  |  |
| Cancellation | In Transit - Cancellation |  | False |  | v1_cancel_fee_btmsheet | view |  | in_transit | True |  |  | True |  |  |  |
| Cancellation | At Unloading - Cancellation |  | False |  | v1_cancel_fee_btmsheet | view |  | at_unloading | True |  |  | True |  |  |  |
| Cancellation | Trip End - Cancellation |  | False |  | v1_cancel_fee_btmsheet | view |  | trip_end | True |  |  | True |  |  |  |
| Cancellation | Cancelled Trip - Cancellation | Views 'Cancel Bottomsheet' | False |  | v1_cancel_bottom_sheet | view | cancel_bottom_sheet | cancelled | True |  |  | True |  |  |  |
| Cancellation | Cancelled Trip - Cancellation | Selects a reason on 'Cancel Bottomsheet' | False |  | v1_reason_selected | click | cancel_bottom_sheet | cancelled | True |  |  | True |  |  |  |
| Cancellation | Cancelled Trip - Cancellation | Clicks 'Submit' button on 'Cancel Bottomsheet' | False |  | v1_submit_btn | click | cancel_bottom_sheet | cancelled | True |  | reason | True |  |  |  |
| Cancellation | Cancelled Trip - Cancellation | Clicks 'Modify' button on 'Cancel Bottomsheet' | False |  | v1_modify_btn | click | cancel_bottom_sheet | cancelled | True |  | reason | True |  |  |  |
| Trip Tracking | Trip Details - Invoices, Expenses & Dues |  | False |  | v1_expense_confirm | view | bottom_nav | demand_detail | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load |  | True |  | v1_going_to_load | view |  | going_to_load | True |  | status | True |  |  |  |
| Trip Tracking | Going To Load |  | False |  | v1_call_driver_btm_sheet | view |  | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load | Clicks 'Call Driver' | False |  | v1_call_driver | click |  | going_to_load | True |  | otp | True |  |  |  |
| Trip Tracking | Going To Load | Clicks 'Call Driver Close' | False |  | v1_call_driver_close | click |  | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load | Clicks 'Going To Load' | False |  | v1_going_to_load | click |  | going_to_load | True |  | status | True |  |  |  |
| Trip Tracking | Going To Load | Switches trip details tab | False |  | v1_screen_fliter | click | top_nav | going_to_load | True |  | segment | True |  |  |  |
| Trip Tracking | Going To Load | Clicks 'Back' arrow | False |  | v1_back_btn | click | top_nav | going_to_load | True |  | timer | True |  |  |  |
| Trip Tracking | Going To Load | Clicks 'Complete Kyc' | False |  | v1_complete_kyc | click | bottom_nav | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - VIP Pass / Coupon |  | False |  | v1_explore_plans | view |  | going_to_load | False |  | action_type | True |  |  |  |
| Trip Tracking | Going To Load - VIP Pass / Coupon |  | False |  | v1_coupon | view |  | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Vehicle Confirmation |  | False |  | v1_penalty_warning | view |  | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Cancellation |  | False |  | v1_cancel_fee_btmsheet | view |  | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - VIP Pass / Coupon |  | False |  | v1_promo_applied | view |  | going_to_load | False |  | disc_type | True |  |  |  |
| Trip Tracking | Going To Load - VIP Pass / Coupon |  | False |  | v1_renew_pass | view |  | going_to_load | False |  | action_type | True |  |  |  |
| Trip Tracking | Going To Load - VIP Pass / Coupon | Clicks 'Coupon Action' | False |  | v1_coupon_action | click |  | going_to_load | True |  | enum_type | True |  |  |  |
| Trip Tracking | Going To Load - VIP Pass / Coupon | Clicks 'Explore Plans' | False |  | v1_explore_plans | click |  | going_to_load | False |  |  | True |  |  |  |
| Trip Tracking | Going To Load - VIP Pass / Coupon | Clicks 'Save With Pass' | False |  | v1_save_with_pass | click |  | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - VIP Pass / Coupon | Clicks 'Add Pass' | False |  | v1_add_pass | click |  | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - VIP Pass / Coupon | Clicks 'Pass Added' | False |  | v1_pass_added | click |  | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Invoices, Expenses & Dues | Clicks 'Unlock Discount' | False |  | v1_unlock_discount | click |  | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - VIP Pass / Coupon | Clicks 'Renew Pass' | False |  | v1_renew_pass | click |  | going_to_load | False |  |  | True |  |  |  |
| Trip Tracking | Going To Load | Views 'Demand Stage' | False |  | v1_dmg_guidlines | view | demand_stage | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load | Clicks 'Dmg Guidlines' on 'Demand Stage' | False |  | v1_dmg_guidlines | click | demand_stage | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Insurance | Views 'Insurance Doc' | False |  | v1_insurance_doc | view | insurance_doc | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Bilti / E-way / OTP | Views 'Otp View' | False |  | v1_otp | view | otp_view | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Bilti / E-way / OTP | Clicks 'Complete Kyc Payment' on 'Otp View' | False |  | v1_complete_kyc_payment | click | otp_view | going_to_load | True |  | action | True |  |  |  |
| Trip Tracking | Going To Load - Edit Booking | Views 'Trip Details' | False |  | v1_edit_btn | view | trip_details | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load | Views 'Trip Details' | False |  | v1_halt_info | view | trip_details | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load | Views 'Trip Details' | False |  | v1_veh_status | view | trip_details | going_to_load | True |  | start | True |  |  |  |
| Trip Tracking | Going To Load | Views 'Trip Details' | False |  | v1_macro_event_post_dr | view | trip_details | going_to_load | False |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Bilti / E-way / OTP | Views 'Trip Details' | False |  | v1_bilti_download_due_payment | view | trip_details | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Edit Booking | Clicks 'Edit Booking' button on 'Trip Details' | False |  | v1_edit_booking_btn | click | trip_details | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Invoices, Expenses & Dues | Clicks 'View Details' on 'Trip Details' | False |  | v1_view_details_btn | click | trip_details | going_to_load | True |  | expense_type | True |  |  |  |
| Trip Tracking | Going To Load - Edit Booking | Clicks 'Edit' button on 'Trip Details' | False |  | v1_edit_btn | click | trip_details | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Bilti / E-way / OTP | Clicks 'Share' on 'Trip Details' | False |  | v1_share | click | trip_details | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Bilti / E-way / OTP | Clicks 'Add LR' on 'Trip Details' | False |  | v1_add_lr | click | trip_details | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Bilti / E-way / OTP | Clicks 'Bilti Download Due Payment' on 'Trip Details' | False |  | v1_bilti_download_due_payment | click | trip_details | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load | Clicks 'Call Driver' on 'Driver Details' | False |  | v1_call_driver | click | driver_details | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load | Expands section on 'Driver Details' | False |  | v1_expand | click | driver_details | going_to_load | True |  | action | True |  |  |  |
| Trip Tracking | Going To Load - Cancellation | Views 'Cancel Bot' | False |  | v1_cancel_bot | view | cancel_bot | going_to_load | True |  | time | True |  |  |  |
| Trip Tracking | Going To Load - Cancellation | Clicks 'Continue' button on 'Cancel Bot' | False |  | v1_continue | click | cancel_bot | going_to_load | True |  | action | True |  |  |  |
| Trip Tracking | Going To Load - Cancellation | Clicks 'Close' (X) on 'Cancel Bot' | False |  | v1_close | click | cancel_bot | going_to_load | True |  | time | True |  |  |  |
| Trip Tracking | Going To Load | Expands section on 'Transit Information' | False |  | v1_expand | click | transit_information | going_to_load | True |  | action | True |  |  |  |
| Trip Tracking | Going To Load - Cancellation | Clicks 'Cancel' on 'Tracking' | False |  | v1_cancel | click | tracking | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Cancellation | Views 'Cancellation Bottomsheet' | False |  | v1_cancellation_bottom_sheet | view | cancellation_bottom_sheet | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Cancellation | Clicks 'Cancel Booking' on 'Cancellation Bottomsheet' | False |  | v1_cancel_booking | click | cancellation_bottomsheet | going_to_load | True |  | reason | True |  |  |  |
| Trip Tracking | Going To Load - Cancellation | Clicks 'Change Booking' button on 'Cancellation Bottomsheet' | False |  | v1_change_booking_btn | click | cancellation_bottomsheet | going_to_load | True |  | reason | True |  |  |  |
| Trip Tracking | Going To Load - Cancellation | Clicks 'Cancel Booking Close' on 'Cancellation Bottomsheet' | False |  | v1_cancel_booking_close | click | cancellation_bottomsheet | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Cancellation | Views 'Final Cancel Bottomsheet' | False |  | v1_final_cancel_bottom_sheet | view | final_cancel_bottom_sheet | going_to_load | True |  | rsn | True |  |  |  |
| Trip Tracking | Going To Load - Cancellation | Confirms cancellation (Yes) on 'Final Cancel Bottomsheet' | False |  | v1_cancel_yes | click | final_cancel_bottom_sheet | going_to_load | True |  | rsn | True |  |  |  |
| Trip Tracking | Going To Load - Cancellation | Does not cancel (No) on 'Final Cancel Bottomsheet' | False |  | v1_cancel_no | click | final_cancel_bottom_sheet | going_to_load | True |  | rsn | True |  |  |  |
| Trip Tracking | Going To Load - Help / Ticket | Clicks 'Raise Issue' | False |  | v1_raise_issue | click | bottom_nav | going_to_load | True |  | expense_type | True |  |  |  |
| Trip Tracking | Going To Load - Help / Ticket | Clicks 'Create Ticket' on 'Help Support' | False |  | v1_create_ticket | click | help_support | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Help / Ticket | Clicks 'Need Help' on 'Help Widget' | False |  | v1_need_help | click | help_widget | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Invoices, Expenses & Dues | Views 'No Cash Bottomsheet' | False |  | v1_nocashbanner | view | no_cash_bottomsheet | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Invoices, Expenses & Dues | Clicks 'Agree' on 'No Cash Bottomsheet' | False |  | v1_agree | click | no_cash_bottomsheet | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Invoices, Expenses & Dues | Clicks 'Submit' button on 'No Cash Bottomsheet' | False |  | v1_submit | click | no_cash_bottomsheet | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load | Clicks 'Recenter' map on 'Map View' | False |  | v1_recenter | click | map_view | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Bilti / E-way / OTP | Clicks 'Pay & Generate OTP' on 'Map View' | False |  | v1_pay_gen_otp | click | map_view | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Bilti / E-way / OTP | Clicks 'Generate OTP' on 'Map View' | False |  | v1_gen_otp | click | map_view | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load | Clicks 'Share Location' on 'Map View' | False |  | v1_share_loc | click | map_view | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Bilti / E-way / OTP | Clicks 'Share OTP' on 'Map View' | False |  | v1_share_otp | click | map_view | going_to_load | True |  | otp | True |  |  |  |
| Trip Tracking | Going To Load - Invoices, Expenses & Dues | Clicks 'Pay Now' on 'Freight Invoice' | False |  | v1_pay_now | click | freight_invoice | going_to_load | False |  | amt | True |  |  |  |
| Trip Tracking | Going To Load - VIP Pass / Coupon | Views 'Unlock Pass Bottomsheet' | False |  | v1_unlock_pass | view | unlock_pass_btmsheet | going_to_load | True |  | type | True |  |  |  |
| Trip Tracking | Going To Load - VIP Pass / Coupon | Clicks 'Conf Pass' on 'Unlock Pass Bottomsheet' | False |  | v1_conf_pass | click | unlock_pass_btmsheet | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - VIP Pass / Coupon | Clicks 'Explore Plans' on 'Unlock Pass Bottomsheet' | False |  | v1_explore_plans | click | unlock_pass_btmsheet | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Invoices, Expenses & Dues | Views 'Detention Charge Bottomsheet' | False |  | v1_detention_charge_bottomsheet | view | detention_charge_bottomsheet | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Invoices, Expenses & Dues | Clicks 'Close' (X) on 'Detention Charge Bottomsheet' | False |  | v1_close | click | detention_charge_bottomsheet | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Invoices, Expenses & Dues | Clicks 'Got it' on 'Detention Charge Bottomsheet' | False |  | v1_got_it | click | detention_charge_bottomsheet | going_to_load | True |  | expense_type | True |  |  |  |
| Trip Tracking | Going To Load - Invoices, Expenses & Dues | Clicks 'Read Policy' on 'Detention Charge Bottomsheet' | False |  | v1_read_policy | click | detention_charge_bottomsheet | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Cancellation | Clicks 'Raise Issue' on 'Cancel Fee Bottomsheet' | False |  | v1_raise_issue | click | cancel_fee_btmsheet | going_to_load | True |  | demand_id | True |  |  |  |
| Trip Tracking | Going To Load - Bilti / E-way / OTP | Clicks 'Add Eway Bill' on 'Bilti Train Bottomsheet' | False |  | v1_add_eway_bill | click | bilti_train_btmsheet | going_to_load | True |  | text | True |  |  |  |
| Trip Tracking | Going To Load - Bilti / E-way / OTP | Clicks 'Download Bilti' on 'Lr Details' | False |  | v1_bilti_download | click | lr_details | going_to_load | True |  | lrnumber | True |  |  |  |
| Trip Tracking | Going To Load - Bilti / E-way / OTP | Clicks 'Generate OTP' on 'Eway Confirm Bottomsheet' | False |  | v1_gen_otp | click | eway_confirm_btmsheet | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Bilti / E-way / OTP | Clicks 'Yes' on 'No Eway Bottomsheet' | False |  | v1_yes | click | no_eway_btmsheet | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Bilti / E-way / OTP | Clicks 'Close' (X) on 'No Eway Bottomsheet' | False |  | v1_close | click | no_eway_btmsheet | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Bilti / E-way / OTP | Clicks 'No' on 'No Eway Bottomsheet' | False |  | v1_no | click | no_eway_btmsheet | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Bilti / E-way / OTP | Clicks 'Close' (X) on 'Otp Bottomsheet' | False |  | v1_close | click | otp_btmsheet | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Bilti / E-way / OTP | Clicks 'Download' on 'Otp Bottomsheet' | False |  | v1_download | click | otp_btmsheet | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Bilti / E-way / OTP | Clicks 'Share OTP' on 'Otp Bottomsheet' | False |  | v1_share_otp | click | otp_btmsheet | going_to_load | True |  | otp | True |  |  |  |
| Trip Tracking | Going To Load - Bilti / E-way / OTP | Clicks 'Add E-way Bill' on 'Otp Bottomsheet' | False |  | v1_add_eway | click | otp_btmsheet | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Bilti / E-way / OTP | Clicks 'Close' (X) on 'Eway Add Bottomsheet' | False |  | v1_close | click | eway_add_btmsheet | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Bilti / E-way / OTP | Clicks 'Submit' button on 'Eway Add Bottomsheet' | False |  | v1_submit | click | eway_add_btmsheet | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Bilti / E-way / OTP | Clicks 'Add E-way Bill' on 'Eway Add Bottomsheet' | False |  | v1_add_eway | click | eway_add_btmsheet | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load | Views 'Dmg Guide Bottomsheet' | False |  | v1_guideline | view | dmg_guide_bottom_sheet | going_to_load | True |  | type | True |  |  |  |
| Trip Tracking | Going To Load | Clicks 'Got it' on 'Dmg Guide Bottomsheet' | False |  | v1_got_it | click | dmg_guide_bottom_sheet | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Insurance | Clicks 'Confirm' button on 'Update Ins Pricing' | False |  | v1_confim | click | update_ins_pricing | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Insurance | Clicks 'OK' on 'Update Ins Pricing' | False |  | v1_ok | click | update_ins_pricing | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Insurance | Clicks 'Close' (X) on 'Update Ins Pricing' | False |  | v1_close | click | update_ins_pricing | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Insurance | Clicks 'View Fragile Items' on 'Update Ins Pricing' | False |  | v1_view_fragile | click | update_ins_pricing | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load | Expands section on 'Trip Information' | False |  | v1_expand | click | trip_information | going_to_load | True |  | action | True |  |  |  |
| Trip Tracking | Going To Load - Help / Ticket | Opens an existing ticket on 'Tickets' | False |  | v1_open_ticket | click | tickets | going_to_load | True |  | status | True |  |  |  |
| Trip Tracking | Going To Load - Insurance | Toggles insurance checkbox on 'Insurance' | False |  | v1_ins_check | click | insurance | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Insurance | Clicks 'Remove Insurance' on 'Insurance' | False |  | v1_remove_pricing | click | insurance | going_to_load | False |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Insurance | Clicks 'Update Pricing' on 'Insurance' | False |  | v1_update_pricing | click | insurance | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Insurance | Clicks 'Add Insurance' on 'Insurance' | False |  | v1_add_insurance | click | insurance | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Insurance | Clicks 'View Pricing' on 'Insurance' | False |  | v1_view_pricing | click | insurance | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Invoices, Expenses & Dues | Views 'Past Trip Balance' | False |  | v1_past_payment | view | past_trip_balance | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Invoices, Expenses & Dues | Clicks 'Past View Detail' on 'Past Trip Balance' | False |  | v1_past_view_detail | click | past_trip_balance | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load | Views 'Monsoon Alert Bottomsheet' | False |  | v1_monsoon_alert_btm_sheet | view | monsoon_alert_btm_sheet | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load | Clicks 'Download' on 'Monsoon Alert Bottomsheet' | False |  | v1_download | click | monsoon_alert_btm_sheet | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load | Clicks 'Close' (X) on 'Monsoon Alert Bottomsheet' | False |  | v1_close | click | monsoon_alert_btm_sheet | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Insurance | Views 'Insurance Bottomsheet' | False |  | v1_insurance_btm_sheet | view | insurance_btm_sheet | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Insurance | Clicks 'Close' (X) on 'Insurance Bottomsheet' | False |  | v1_close | click | insurance_btm_sheet | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Insurance | Clicks 'Add Insurance' on 'Insurance Bottomsheet' | False |  | v1_add_ins | click | insurance_btm_sheet | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Insurance | Toggles insurance checkbox on 'Insurance Bottomsheet' | False |  | v1_ins_check | click | insurance_btm_sheet | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Insurance | Clicks 'No' on 'Insurance Bottomsheet' | False |  | v1_no | click | insurance_btm_sheet | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Invoices, Expenses & Dues | Clicks 'Submit' button on 'Extra Charge Policy Popup' | False |  | v1_submit_btn | click | extra_charge_policy_popup | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Insurance | Clicks 'OK' on 'Fragile Items List' | False |  | v1_ok | click | fragile_items_list | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Cancellation | Views 'Cancel Bottomsheet' | False |  | v1_cancel_bottom_sheet | view | cancel_bottom_sheet | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Cancellation | Selects a reason on 'Cancel Bottomsheet' | False |  | v1_reason_selected | click | cancel_bottom_sheet | going_to_load | True |  |  | True |  |  |  |
| Trip Tracking | Going To Load - Cancellation | Clicks 'Submit' button on 'Cancel Bottomsheet' | False |  | v1_submit_btn | click | cancel_bottom_sheet | going_to_load | True |  | reason | True |  |  |  |
| Trip Tracking | At Loading |  | False |  | v1_call_driver_btm_sheet | view |  | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading | Clicks 'At Loading' | False |  | v1_at_loading | click |  | at_loading | True |  | eta | True |  |  |  |
| Trip Tracking | At Loading | Clicks 'Call Driver' | False |  | v1_call_driver | click |  | at_loading | True |  | otp | True |  |  |  |
| Trip Tracking | At Loading | Clicks 'Call Driver Close' | False |  | v1_call_driver_close | click |  | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading | Switches trip details tab | False |  | v1_screen_fliter | click | top_nav | at_loading | True |  | segment | True |  |  |  |
| Trip Tracking | At Loading | Clicks 'Back' arrow | False |  | v1_back_btn | click | top_nav | at_loading | True |  | timer | True |  |  |  |
| Trip Tracking | At Loading | Clicks 'Complete Kyc' | False |  | v1_complete_kyc | click | bottom_nav | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - VIP Pass / Coupon |  | False |  | v1_explore_plans | view |  | at_loading | False |  | action_type | True |  |  |  |
| Trip Tracking | At Loading - VIP Pass / Coupon |  | False |  | v1_coupon | view |  | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Cancellation |  | False |  | v1_cancel_fee_btmsheet | view |  | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - VIP Pass / Coupon |  | False |  | v1_renew_pass | view |  | at_loading | False |  | action_type | True |  |  |  |
| Trip Tracking | At Loading - VIP Pass / Coupon |  | False |  | v1_promo_applied | view |  | at_loading | False |  | disc_type | True |  |  |  |
| Trip Tracking | At Loading - VIP Pass / Coupon | Clicks 'Coupon Action' | False |  | v1_coupon_action | click |  | at_loading | True |  | enum_type | True |  |  |  |
| Trip Tracking | At Loading - VIP Pass / Coupon | Clicks 'Save With Pass' | False |  | v1_save_with_pass | click |  | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - VIP Pass / Coupon | Clicks 'Explore Plans' | False |  | v1_explore_plans | click |  | at_loading | False |  |  | True |  |  |  |
| Trip Tracking | At Loading - VIP Pass / Coupon | Clicks 'Add Pass' | False |  | v1_add_pass | click |  | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - VIP Pass / Coupon | Clicks 'Pass Added' | False |  | v1_pass_added | click |  | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Invoices, Expenses & Dues | Clicks 'Unlock Discount' | False |  | v1_unlock_discount | click |  | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - VIP Pass / Coupon | Clicks 'Renew Pass' | False |  | v1_renew_pass | click |  | at_loading | False |  |  | True |  |  |  |
| Trip Tracking | At Loading - Bilti / E-way / OTP | Views 'Otp View' | False |  | v1_otp | view | otp_view | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Bilti / E-way / OTP | Clicks 'Complete Kyc Payment' on 'Otp View' | False |  | v1_complete_kyc_payment | click | otp_view | at_loading | True |  | action | True |  |  |  |
| Trip Tracking | At Loading | Views 'Demand Stage' | False |  | v1_dmg_guidlines | view | demand_stage | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading | Clicks 'Dmg Guidlines' on 'Demand Stage' | False |  | v1_dmg_guidlines | click | demand_stage | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Insurance | Views 'Insurance Doc' | False |  | v1_insurance_doc | view | insurance_doc | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading | Views 'Trip Details' | False |  | v1_halt_info | view | trip_details | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading | Views 'Trip Details' | False |  | v1_veh_status | view | trip_details | at_loading | True |  | start | True |  |  |  |
| Trip Tracking | At Loading - Edit Booking | Views 'Trip Details' | False |  | v1_edit_btn | view | trip_details | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading | Views 'Trip Details' | False |  | v1_avoid_delay | view | trip_details | at_loading | True |  | type | True |  |  |  |
| Trip Tracking | At Loading - Bilti / E-way / OTP | Views 'Trip Details' | False |  | v1_bilti_download_due_payment | view | trip_details | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Bilti / E-way / OTP | Clicks 'Share' on 'Trip Details' | False |  | v1_share | click | trip_details | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Invoices, Expenses & Dues | Clicks 'View Details' on 'Trip Details' | False |  | v1_view_details_btn | click | trip_details | at_loading | True |  | expense_type | True |  |  |  |
| Trip Tracking | At Loading - Edit Booking | Clicks 'Edit Booking' button on 'Trip Details' | False |  | v1_edit_booking_btn | click | trip_details | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Edit Booking | Clicks 'Edit' button on 'Trip Details' | False |  | v1_edit_btn | click | trip_details | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Bilti / E-way / OTP | Clicks 'Add LR' on 'Trip Details' | False |  | v1_add_lr | click | trip_details | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Bilti / E-way / OTP | Clicks 'Bilti Download Due Payment' on 'Trip Details' | False |  | v1_bilti_download_due_payment | click | trip_details | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading | Clicks hyperlink on 'Trip Details' | False |  | v1_hyperlink | click | trip_details | at_loading | True |  | type | True |  |  |  |
| Trip Tracking | At Loading | Clicks 'Close' (X) on 'Avoid Detention Bottomsheet' | False |  | v1_close | click | avoid_detention_btm_sheet | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading | Clicks 'View Policy' on 'Avoid Detention Bottomsheet' | False |  | v1_view_policy | click | avoid_detention_btm_sheet | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Bilti / E-way / OTP | Clicks 'Generate OTP' on 'Map View' | False |  | v1_gen_otp | click | map_view | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Bilti / E-way / OTP | Clicks 'Pay & Generate OTP' on 'Map View' | False |  | v1_pay_gen_otp | click | map_view | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading | Clicks 'Recenter' map on 'Map View' | False |  | v1_recenter | click | map_view | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Bilti / E-way / OTP | Clicks 'Share OTP' on 'Map View' | False |  | v1_share_otp | click | map_view | at_loading | True |  | otp | True |  |  |  |
| Trip Tracking | At Loading | Clicks 'Share Location' on 'Map View' | False |  | v1_share_loc | click | map_view | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Bilti / E-way / OTP | Clicks 'Download Bilti' on 'Lr Details' | False |  | v1_bilti_download | click | lr_details | at_loading | True |  | lrnumber | True |  |  |  |
| Trip Tracking | At Loading - Bilti / E-way / OTP | Clicks 'Generate OTP' on 'Eway Confirm Bottomsheet' | False |  | v1_gen_otp | click | eway_confirm_btmsheet | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading | Views 'Monsoon Alert Bottomsheet' | False |  | v1_monsoon_alert_btm_sheet | view | monsoon_alert_btm_sheet | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading | Clicks 'Download' on 'Monsoon Alert Bottomsheet' | False |  | v1_download | click | monsoon_alert_btm_sheet | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading | Clicks 'Close' (X) on 'Monsoon Alert Bottomsheet' | False |  | v1_close | click | monsoon_alert_btm_sheet | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading | Clicks 'Need Help' on 'Monsoon Alert Bottomsheet' | False |  | v1_need_help | click | monsoon_alert_btm_sheet | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Bilti / E-way / OTP | Clicks 'Yes' on 'No Eway Bottomsheet' | False |  | v1_yes | click | no_eway_btmsheet | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Bilti / E-way / OTP | Clicks 'No' on 'No Eway Bottomsheet' | False |  | v1_no | click | no_eway_btmsheet | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Bilti / E-way / OTP | Clicks 'Close' (X) on 'No Eway Bottomsheet' | False |  | v1_close | click | no_eway_btmsheet | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Bilti / E-way / OTP | Clicks 'Download' on 'Otp Bottomsheet' | False |  | v1_download | click | otp_btmsheet | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Bilti / E-way / OTP | Clicks 'Close' (X) on 'Otp Bottomsheet' | False |  | v1_close | click | otp_btmsheet | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Bilti / E-way / OTP | Clicks 'Share OTP' on 'Otp Bottomsheet' | False |  | v1_share_otp | click | otp_btmsheet | at_loading | True |  | otp | True |  |  |  |
| Trip Tracking | At Loading - Bilti / E-way / OTP | Clicks 'Add E-way Bill' on 'Otp Bottomsheet' | False |  | v1_add_eway | click | otp_btmsheet | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading | Expands section on 'Driver Details' | False |  | v1_expand | click | driver_details | at_loading | True |  | action | True |  |  |  |
| Trip Tracking | At Loading | Clicks 'Call Driver' on 'Driver Details' | False |  | v1_call_driver | click | driver_details | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Bilti / E-way / OTP | Clicks 'Add Eway Bill' on 'Bilti Train Bottomsheet' | False |  | v1_add_eway_bill | click | bilti_train_btmsheet | at_loading | True |  | text | True |  |  |  |
| Trip Tracking | At Loading - Help / Ticket | Clicks 'Create Ticket' on 'Help Support' | False |  | v1_create_ticket | click | help_support | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Help / Ticket | Clicks 'Need Help' on 'Help Widget' | False |  | v1_need_help | click | help_widget | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Bilti / E-way / OTP | Clicks 'Submit' button on 'Eway Add Bottomsheet' | False |  | v1_submit | click | eway_add_btmsheet | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Bilti / E-way / OTP | Clicks 'Close' (X) on 'Eway Add Bottomsheet' | False |  | v1_close | click | eway_add_btmsheet | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Bilti / E-way / OTP | Clicks 'Add E-way Bill' on 'Eway Add Bottomsheet' | False |  | v1_add_eway | click | eway_add_btmsheet | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Invoices, Expenses & Dues | Clicks 'Pay Now' on 'Freight Invoice' | False |  | v1_pay_now | click | freight_invoice | at_loading | False |  | amt | True |  |  |  |
| Trip Tracking | At Loading - Cancellation | Clicks 'Cancel' on 'Tracking' | False |  | v1_cancel | click | tracking | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Cancellation | Clicks 'Cancel Booking' button on 'Cancellation Bottomsheet' | False |  | v1_cancel_booking_btn | click | cancellation_bottomsheet | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Cancellation | Clicks 'Cancel Booking' on 'Cancellation Bottomsheet' | False |  | v1_cancel_booking | click | cancellation_bottomsheet | at_loading | True |  | reason | True |  |  |  |
| Trip Tracking | At Loading - Cancellation | Clicks 'Close' (X) on 'Cancellation Bottomsheet' | False |  | v1_close_btn | click | cancellation_bottomsheet | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Cancellation | Clicks 'Change Booking' button on 'Cancellation Bottomsheet' | False |  | v1_change_booking_btn | click | cancellation_bottomsheet | at_loading | True |  | reason | True |  |  |  |
| Trip Tracking | At Loading - Cancellation | Clicks 'Cancel Booking Close' on 'Cancellation Bottomsheet' | False |  | v1_cancel_booking_close | click | cancellation_bottomsheet | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Cancellation | Views 'Cancellation Bottomsheet' | False |  | v1_cancellation_bottom_sheet | view | cancellation_bottom_sheet | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Cancellation | Views 'Final Cancel Bottomsheet' | False |  | v1_final_cancel_bottom_sheet | view | final_cancel_bottom_sheet | at_loading | True |  | rsn | True |  |  |  |
| Trip Tracking | At Loading - Cancellation | Confirms cancellation (Yes) on 'Final Cancel Bottomsheet' | False |  | v1_cancel_yes | click | final_cancel_bottom_sheet | at_loading | True |  | rsn | True |  |  |  |
| Trip Tracking | At Loading - Cancellation | Does not cancel (No) on 'Final Cancel Bottomsheet' | False |  | v1_cancel_no | click | final_cancel_bottom_sheet | at_loading | True |  | rsn | True |  |  |  |
| Trip Tracking | At Loading - Help / Ticket | Clicks 'Raise Issue' | False |  | v1_raise_issue | click | bottom_nav | at_loading | True |  | expense_type | True |  |  |  |
| Trip Tracking | At Loading - Invoices, Expenses & Dues | Views 'Detention Charge Bottomsheet' | False |  | v1_detention_charge_bottomsheet | view | detention_charge_bottomsheet | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Invoices, Expenses & Dues | Clicks 'Close' (X) on 'Detention Charge Bottomsheet' | False |  | v1_close | click | detention_charge_bottomsheet | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Invoices, Expenses & Dues | Clicks 'Got it' on 'Detention Charge Bottomsheet' | False |  | v1_got_it | click | detention_charge_bottomsheet | at_loading | True |  | expense_type | True |  |  |  |
| Trip Tracking | At Loading - Invoices, Expenses & Dues | Clicks 'Read Policy' on 'Detention Charge Bottomsheet' | False |  | v1_read_policy | click | detention_charge_bottomsheet | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading | Expands section on 'Trip Information' | False |  | v1_expand | click | trip_information | at_loading | True |  | action | True |  |  |  |
| Trip Tracking | At Loading - Invoices, Expenses & Dues | Views 'No Cash Bottomsheet' | False |  | v1_nocashbanner | view | no_cash_bottomsheet | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Invoices, Expenses & Dues | Clicks 'Agree' on 'No Cash Bottomsheet' | False |  | v1_agree | click | no_cash_bottomsheet | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Invoices, Expenses & Dues | Clicks 'Submit' button on 'No Cash Bottomsheet' | False |  | v1_submit | click | no_cash_bottomsheet | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - VIP Pass / Coupon | Views 'Unlock Pass Bottomsheet' | False |  | v1_unlock_pass | view | unlock_pass_btmsheet | at_loading | True |  | type | True |  |  |  |
| Trip Tracking | At Loading - VIP Pass / Coupon | Clicks 'Conf Pass' on 'Unlock Pass Bottomsheet' | False |  | v1_conf_pass | click | unlock_pass_btmsheet | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - VIP Pass / Coupon | Clicks 'Explore Plans' on 'Unlock Pass Bottomsheet' | False |  | v1_explore_plans | click | unlock_pass_btmsheet | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Help / Ticket | Opens an existing ticket on 'Tickets' | False |  | v1_open_ticket | click | tickets | at_loading | True |  | status | True |  |  |  |
| Trip Tracking | At Loading - Insurance | Clicks 'Confirm' button on 'Update Ins Pricing' | False |  | v1_confim | click | update_ins_pricing | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Insurance | Clicks 'OK' on 'Update Ins Pricing' | False |  | v1_ok | click | update_ins_pricing | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Insurance | Clicks 'Close' (X) on 'Update Ins Pricing' | False |  | v1_close | click | update_ins_pricing | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Insurance | Clicks 'View Fragile Items' on 'Update Ins Pricing' | False |  | v1_view_fragile | click | update_ins_pricing | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading | Views 'Dmg Guide Bottomsheet' | False |  | v1_guideline | view | dmg_guide_bottom_sheet | at_loading | True |  | type | True |  |  |  |
| Trip Tracking | At Loading | Clicks 'Got it' on 'Dmg Guide Bottomsheet' | False |  | v1_got_it | click | dmg_guide_bottom_sheet | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Insurance | Toggles insurance checkbox on 'Insurance' | False |  | v1_ins_check | click | insurance | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Insurance | Clicks 'Update Pricing' on 'Insurance' | False |  | v1_update_pricing | click | insurance | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Insurance | Clicks 'Remove Insurance' on 'Insurance' | False |  | v1_remove_pricing | click | insurance | at_loading | False |  |  | True |  |  |  |
| Trip Tracking | At Loading - Insurance | Clicks 'Add Insurance' on 'Insurance' | False |  | v1_add_insurance | click | insurance | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Insurance | Clicks 'View Pricing' on 'Insurance' | False |  | v1_view_pricing | click | insurance | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Invoices, Expenses & Dues | Views 'Past Trip Balance' | False |  | v1_past_payment | view | past_trip_balance | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Invoices, Expenses & Dues | Clicks 'Past View Detail' on 'Past Trip Balance' | False |  | v1_past_view_detail | click | past_trip_balance | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Insurance | Views 'Insurance Bottomsheet' | False |  | v1_insurance_btm_sheet | view | insurance_btm_sheet | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Insurance | Clicks 'Add Insurance' on 'Insurance Bottomsheet' | False |  | v1_add_ins | click | insurance_btm_sheet | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Insurance | Clicks 'Close' (X) on 'Insurance Bottomsheet' | False |  | v1_close | click | insurance_btm_sheet | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Insurance | Toggles insurance checkbox on 'Insurance Bottomsheet' | False |  | v1_ins_check | click | insurance_btm_sheet | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Insurance | Clicks 'No' on 'Insurance Bottomsheet' | False |  | v1_no | click | insurance_btm_sheet | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Invoices, Expenses & Dues | Clicks 'Submit' button on 'Extra Charge Policy Popup' | False |  | v1_submit_btn | click | extra_charge_policy_popup | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Invoices, Expenses & Dues | Views 'Due Payment Amount Widget' | False |  | v1_due_payment_amount_widget | view | due_payment_amount_widget | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | At Loading - Insurance | Clicks 'OK' on 'Fragile Items List' | False |  | v1_ok | click | fragile_items_list | at_loading | True |  |  | True |  |  |  |
| Trip Tracking | Bilti Training - Bilti / E-way / OTP | Views 'Bilti Overlay' | False |  | v1_bilti_overlay | view | bilti_overlay | bilti_training | True |  |  | True |  |  |  |
| Trip Tracking | Bilti Training - Bilti / E-way / OTP | Clicks 'Next' button | False |  | v1_next | click | bottom_nav | bilti_training | True |  | current_page | True |  |  |  |
| Trip Tracking | Bilti Training - Bilti / E-way / OTP | Clicks 'Previous' button | False |  | v1_previous | click | bottom_nav | bilti_training | True |  | current_page | True |  |  |  |
| Trip Tracking | Bilti Training - Bilti / E-way / OTP | Clicks 'Close' (X) | False |  | v1_close | click | top_nav | bilti_training | True |  | current_page | True |  |  |  |
| Trip Tracking | In Transit |  | False |  | v1_call_driver_btm_sheet | view |  | in_transit | True |  |  | True |  |  |  |
| Trip Tracking | In Transit | Clicks 'In Transit' | False |  | v1_in_transit | click |  | in_transit | True |  | status | True |  |  |  |
| Trip Tracking | In Transit | Clicks 'Call Driver' | False |  | v1_call_driver | click |  | in_transit | True |  | otp | True |  |  |  |
| Trip Tracking | In Transit | Clicks 'Call Driver Close' | False |  | v1_call_driver_close | click |  | in_transit | True |  |  | True |  |  |  |
| Trip Tracking | In Transit | Switches trip details tab | False |  | v1_screen_fliter | click | top_nav | in_transit | True |  | segment | True |  |  |  |
| Trip Tracking | In Transit | Clicks 'Back' arrow | False |  | v1_back_btn | click | top_nav | in_transit | True |  | timer | True |  |  |  |
| Trip Tracking | In Transit - Cancellation |  | False |  | v1_cancel_fee_btmsheet | view |  | in_transit | True |  |  | True |  |  |  |
| Trip Tracking | In Transit - VIP Pass / Coupon |  | False |  | v1_promo_applied | view |  | in_transit | False |  | disc_type | True |  |  |  |
| Trip Tracking | In Transit - VIP Pass / Coupon | Clicks 'Save With Pass' | False |  | v1_save_with_pass | click |  | in_transit | True |  |  | True |  |  |  |
| Trip Tracking | In Transit - Invoices, Expenses & Dues | Clicks 'Unlock Discount' | False |  | v1_unlock_discount | click |  | in_transit | True |  |  | True |  |  |  |
| Trip Tracking | In Transit | Views 'Trip Details' | False |  | v1_halt_info | view | trip_details | in_transit | True |  |  | True |  |  |  |
| Trip Tracking | In Transit | Views 'Trip Details' | False |  | v1_veh_status | view | trip_details | in_transit | True |  | start | True |  |  |  |
| Trip Tracking | In Transit | Views 'Trip Details' | False |  | v1_macro_event_post_dr | view | trip_details | in_transit | False |  |  | True |  |  |  |
| Trip Tracking | In Transit - Edit Booking | Views 'Trip Details' | False |  | v1_edit_btn | view | trip_details | in_transit | True |  |  | True |  |  |  |
| Trip Tracking | In Transit - Invoices, Expenses & Dues | Clicks 'View Details' on 'Trip Details' | False |  | v1_view_details_btn | click | trip_details | in_transit | True |  | expense_type | True |  |  |  |
| Trip Tracking | In Transit - Edit Booking | Clicks 'Edit' button on 'Trip Details' | False |  | v1_edit_btn | click | trip_details | in_transit | True |  |  | True |  |  |  |
| Trip Tracking | In Transit - Bilti / E-way / OTP | Clicks 'Share' on 'Trip Details' | False |  | v1_share | click | trip_details | in_transit | True |  |  | True |  |  |  |
| Trip Tracking | In Transit - Feedback & Rating | Views 'Pickup Feedback Bottomsheet' | False |  | v1_pickup_feedback | view | pickup_feedback_btmsheet | in_transit | True |  |  | True |  |  |  |
| Trip Tracking | In Transit - Feedback & Rating | Clicks 'Close' (X) on 'Pickup Feedback Bottomsheet' | False |  | v1_close | click | pickup_feedback_btmsheet | in_transit | True |  |  | True |  |  |  |
| Trip Tracking | In Transit - Feedback & Rating | Clicks 'Submit' button on 'Pickup Feedback Bottomsheet' | False |  | v1_submit | click | pickup_feedback_btmsheet | in_transit | True |  |  | True |  |  |  |
| Trip Tracking | In Transit - Feedback & Rating | Clicks 'Okay' on 'Pickup Feedback Bottomsheet' | False |  | v1_okay | click | pickup_feedback_btmsheet | in_transit | True |  |  | True |  |  |  |
| Trip Tracking | In Transit - Feedback & Rating | Clicks 'No' on 'Pickup Feedback Bottomsheet' | False |  | v1_no | click | pickup_feedback_btmsheet | in_transit | True |  |  | True |  |  |  |
| Trip Tracking | In Transit - Feedback & Rating | Clicks 'Remark' on 'Pickup Feedback Bottomsheet' | False |  | v1_remark | click | pickup_feedback_btmsheet | in_transit | True |  | remark | True |  |  |  |
| Trip Tracking | In Transit | Expands section on 'Transit Information' | False |  | v1_expand | click | transit_information | in_transit | True |  | action | True |  |  |  |
| Trip Tracking | In Transit - Insurance | Views 'Insurance Doc' | False |  | v1_insurance_doc | view | insurance_doc | in_transit | True |  |  | True |  |  |  |
| Trip Tracking | In Transit - Insurance | Clicks 'Download' on 'Insurance Doc' | False |  | v1_download | click | insurance_doc | in_transit | True |  |  | True |  |  |  |
| Trip Tracking | In Transit - Invoices, Expenses & Dues | Views 'No Cash Bottomsheet' | False |  | v1_nocashbanner | view | no_cash_bottomsheet | in_transit | True |  |  | True |  |  |  |
| Trip Tracking | In Transit - Invoices, Expenses & Dues | Clicks 'OK' on 'No Cash Bottomsheet' | False |  | v1_ok | click | no_cash_bottomsheet | in_transit | True |  |  | True |  |  |  |
| Trip Tracking | In Transit - Invoices, Expenses & Dues | Clicks 'Agree' on 'No Cash Bottomsheet' | False |  | v1_agree | click | no_cash_bottomsheet | in_transit | True |  |  | True |  |  |  |
| Trip Tracking | In Transit - Invoices, Expenses & Dues | Clicks 'Submit' button on 'No Cash Bottomsheet' | False |  | v1_submit | click | no_cash_bottomsheet | in_transit | True |  |  | True |  |  |  |
| Trip Tracking | In Transit - Invoices, Expenses & Dues | Clicks 'Guideline' on 'No Cash Bottomsheet' | False |  | v1_guideline | click | no_cash_bottomsheet | in_transit | True |  |  | True |  |  |  |
| Trip Tracking | In Transit | Clicks 'Recenter' map on 'Map View' | False |  | v1_recenter | click | map_view | in_transit | True |  |  | True |  |  |  |
| Trip Tracking | In Transit | Clicks 'Share Location' on 'Map View' | False |  | v1_share_loc | click | map_view | in_transit | True |  |  | True |  |  |  |
| Trip Tracking | In Transit - Bilti / E-way / OTP | Clicks 'Pay & Generate OTP' on 'Map View' | False |  | v1_pay_gen_otp | click | map_view | in_transit | True |  |  | True |  |  |  |
| Trip Tracking | In Transit - Bilti / E-way / OTP | Clicks 'Share OTP' on 'Map View' | False |  | v1_share_otp | click | map_view | in_transit | True |  | otp | True |  |  |  |
| Trip Tracking | In Transit - Bilti / E-way / OTP | Clicks 'Download Bilti' on 'Lr Details' | False |  | v1_bilti_download | click | lr_details | in_transit | True |  | lrnumber | True |  |  |  |
| Trip Tracking | In Transit | Expands section on 'Driver Details' | False |  | v1_expand | click | driver_details | in_transit | True |  | action | True |  |  |  |
| Trip Tracking | In Transit | Clicks 'Call Driver' on 'Driver Details' | False |  | v1_call_driver | click | driver_details | in_transit | True |  |  | True |  |  |  |
| Trip Tracking | In Transit - Help / Ticket | Clicks 'Create Ticket' on 'Help Support' | False |  | v1_create_ticket | click | help_support | in_transit | True |  |  | True |  |  |  |
| Trip Tracking | In Transit - Help / Ticket | Clicks 'Need Help' on 'Help Widget' | False |  | v1_need_help | click | help_widget | in_transit | True |  |  | True |  |  |  |
| Trip Tracking | In Transit | Views 'Monsoon Alert Bottomsheet' | False |  | v1_monsoon_alert_btm_sheet | view | monsoon_alert_btm_sheet | in_transit | True |  |  | True |  |  |  |
| Trip Tracking | In Transit | Clicks 'Download' on 'Monsoon Alert Bottomsheet' | False |  | v1_download | click | monsoon_alert_btm_sheet | in_transit | True |  |  | True |  |  |  |
| Trip Tracking | In Transit | Clicks 'Close' (X) on 'Monsoon Alert Bottomsheet' | False |  | v1_close | click | monsoon_alert_btm_sheet | in_transit | True |  |  | True |  |  |  |
| Trip Tracking | In Transit | Clicks 'Trip Modal' on 'Trip Information' | False |  | v1_trip_modal | click | trip_information | in_transit | True |  |  | True |  |  |  |
| Trip Tracking | In Transit | Expands section on 'Trip Information' | False |  | v1_expand | click | trip_information | in_transit | True |  | action | True |  |  |  |
| Trip Tracking | In Transit | Views 'Modal Bottomsheet' | False |  | v1_modal_btm_sheet | view | modal_btm_sheet | in_transit | True |  |  | True |  |  |  |
| Trip Tracking | In Transit | Clicks 'Understand' on 'Modal Bottomsheet' | False |  | v1_understand | click | modal_btm_sheet | in_transit | True |  |  | True |  |  |  |
| Trip Tracking | In Transit - Help / Ticket | Opens an existing ticket on 'Tickets' | False |  | v1_open_ticket | click | tickets | in_transit | True |  | status | True |  |  |  |
| Trip Tracking | In Transit - Invoices, Expenses & Dues | Views 'Detention Charge Bottomsheet' | False |  | v1_detention_charge_bottomsheet | view | detention_charge_bottomsheet | in_transit | True |  |  | True |  |  |  |
| Trip Tracking | In Transit - Invoices, Expenses & Dues | Clicks 'Close' (X) on 'Detention Charge Bottomsheet' | False |  | v1_close | click | detention_charge_bottomsheet | in_transit | True |  |  | True |  |  |  |
| Trip Tracking | In Transit - Invoices, Expenses & Dues | Clicks 'Read Policy' on 'Detention Charge Bottomsheet' | False |  | v1_read_policy | click | detention_charge_bottomsheet | in_transit | True |  |  | True |  |  |  |
| Trip Tracking | In Transit - Invoices, Expenses & Dues | Clicks 'Got it' on 'Detention Charge Bottomsheet' | False |  | v1_got_it | click | detention_charge_bottomsheet | in_transit | True |  | expense_type | True |  |  |  |
| Trip Tracking | In Transit - Bilti / E-way / OTP | Views 'Otp View' | False |  | v1_otp | view | otp_view | in_transit | True |  |  | True |  |  |  |
| Trip Tracking | In Transit - Bilti / E-way / OTP | Clicks 'Complete Kyc Payment' on 'Otp View' | False |  | v1_complete_kyc_payment | click | otp_view | in_transit | True |  | action | True |  |  |  |
| Trip Tracking | In Transit - Invoices, Expenses & Dues | Views 'Due Payment Amount Widget' | False |  | v1_due_payment_amount_widget | view | due_payment_amount_widget | in_transit | True |  |  | True |  |  |  |
| Trip Tracking | In Transit - Invoices, Expenses & Dues | Views 'Pending Expense Bottomsheet' | False |  | v1_pending_expense | view | pending_expense_bottomsheet | in_transit | True |  |  | True |  |  |  |
| Trip Tracking | In Transit - Invoices, Expenses & Dues | Clicks 'Close' (X) on 'Pending Expense Bottomsheet' | False |  | v1_close | click | pending_expense_bottomsheet | in_transit | True |  |  | True |  |  |  |
| Trip Tracking | In Transit - Invoices, Expenses & Dues | Clicks 'Price Breakup' on 'Pending Expense Bottomsheet' | False |  | v1_price_breakup | click | pending_expense_bottomsheet | in_transit | True |  |  | True |  |  |  |
| Trip Tracking | In Transit - Invoices, Expenses & Dues | Clicks 'Pay' on 'Pending Expense Bottomsheet' | False |  | v1_pay | click | pending_expense_bottomsheet | in_transit | True |  |  | True |  |  |  |
| Trip Tracking | In Transit - Invoices, Expenses & Dues | Clicks 'Pay Now' on 'Freight Invoice' | False |  | v1_pay_now | click | freight_invoice | in_transit | False |  | amt | True |  |  |  |
| Trip Tracking | In Transit - Help / Ticket | Clicks 'Raise Issue' | False |  | v1_raise_issue | click | bottom_nav | in_transit | True |  | expense_type | True |  |  |  |
| Trip Tracking | In Transit - Feedback & Rating | Clicks 'Rate Now' on 'Pickup Feedback' | False |  | v1_rate_now | click | pickup_feedback | in_transit | True |  |  | True |  |  |  |
| Trip Tracking | In Transit - VIP Pass / Coupon | Views 'Unlock Pass Bottomsheet' | False |  | v1_unlock_pass | view | unlock_pass_btmsheet | in_transit | True |  | type | True |  |  |  |
| Trip Tracking | In Transit - VIP Pass / Coupon | Clicks 'Explore Plans' on 'Unlock Pass Bottomsheet' | False |  | v1_explore_plans | click | unlock_pass_btmsheet | in_transit | True |  |  | True |  |  |  |
| Trip Tracking | In Transit - VIP Pass / Coupon | Clicks 'Conf Pass' on 'Unlock Pass Bottomsheet' | False |  | v1_conf_pass | click | unlock_pass_btmsheet | in_transit | True |  |  | True |  |  |  |
| Trip Tracking | In Transit - Invoices, Expenses & Dues | Clicks 'Submit' button on 'Extra Charge Policy Popup' | False |  | v1_submit_btn | click | extra_charge_policy_popup | in_transit | True |  |  | True |  |  |  |
| Trip Tracking | In Transit - Bilti / E-way / OTP | Clicks 'Add Eway Bill' on 'Bilti Train Bottomsheet' | False |  | v1_add_eway_bill | click | bilti_train_btmsheet | in_transit | True |  | text | True |  |  |  |
| Trip Tracking | In Transit - Bilti / E-way / OTP | Clicks 'Download' on 'Otp Bottomsheet' | False |  | v1_download | click | otp_btmsheet | in_transit | True |  |  | True |  |  |  |
| Trip Tracking | In Transit - Bilti / E-way / OTP | Clicks 'Close' (X) on 'Otp Bottomsheet' | False |  | v1_close | click | otp_btmsheet | in_transit | True |  |  | True |  |  |  |
| Trip Tracking | In Transit - Bilti / E-way / OTP | Clicks 'Share OTP' on 'Otp Bottomsheet' | False |  | v1_share_otp | click | otp_btmsheet | in_transit | True |  | otp | True |  |  |  |
| Trip Tracking | In Transit - Bilti / E-way / OTP | Clicks 'Close' (X) on 'Eway Add Bottomsheet' | False |  | v1_close | click | eway_add_btmsheet | in_transit | True |  |  | True |  |  |  |
| Trip Tracking | In Transit - Bilti / E-way / OTP | Clicks 'Submit' button on 'Eway Add Bottomsheet' | False |  | v1_submit | click | eway_add_btmsheet | in_transit | True |  |  | True |  |  |  |
| Trip Tracking | At Unloading |  | False |  | v1_call_driver_btm_sheet | view |  | at_unloading | True |  |  | True |  |  |  |
| Trip Tracking | At Unloading | Clicks 'At Unloading' | False |  | v1_at_unloading | click |  | at_unloading | True |  | eta | True |  |  |  |
| Trip Tracking | At Unloading | Clicks 'Call Driver' | False |  | v1_call_driver | click |  | at_unloading | True |  | otp | True |  |  |  |
| Trip Tracking | At Unloading | Clicks 'Call Driver Close' | False |  | v1_call_driver_close | click |  | at_unloading | True |  |  | True |  |  |  |
| Trip Tracking | At Unloading | Switches trip details tab | False |  | v1_screen_fliter | click | top_nav | at_unloading | True |  | segment | True |  |  |  |
| Trip Tracking | At Unloading | Clicks 'Back' arrow | False |  | v1_back_btn | click | top_nav | at_unloading | True |  | timer | True |  |  |  |
| Trip Tracking | At Unloading - Vehicle Confirmation |  | False |  | v1_confirm_detail_warning | view |  | at_unloading | True |  | timer | True |  |  |  |
| Trip Tracking | At Unloading - Cancellation |  | False |  | v1_cancel_fee_btmsheet | view |  | at_unloading | True |  |  | True |  |  |  |
| Trip Tracking | At Unloading - VIP Pass / Coupon |  | False |  | v1_promo_applied | view |  | at_unloading | False |  | disc_type | True |  |  |  |
| Trip Tracking | At Unloading - VIP Pass / Coupon | Clicks 'Save With Pass' | False |  | v1_save_with_pass | click |  | at_unloading | True |  |  | True |  |  |  |
| Trip Tracking | At Unloading | Views 'Trip Details' | False |  | v1_halt_info | view | trip_details | at_unloading | True |  |  | True |  |  |  |
| Trip Tracking | At Unloading | Views 'Trip Details' | False |  | v1_veh_status | view | trip_details | at_unloading | True |  | start | True |  |  |  |
| Trip Tracking | At Unloading | Views 'Trip Details' | False |  | v1_avoid_delay | view | trip_details | at_unloading | True |  | type | True |  |  |  |
| Trip Tracking | At Unloading - Edit Booking | Views 'Trip Details' | False |  | v1_edit_btn | view | trip_details | at_unloading | True |  |  | True |  |  |  |
| Trip Tracking | At Unloading - Invoices, Expenses & Dues | Clicks 'View Details' on 'Trip Details' | False |  | v1_view_details_btn | click | trip_details | at_unloading | True |  | expense_type | True |  |  |  |
| Trip Tracking | At Unloading | Clicks hyperlink on 'Trip Details' | False |  | v1_hyperlink | click | trip_details | at_unloading | True |  | type | True |  |  |  |
| Trip Tracking | At Unloading - Edit Booking | Clicks 'Edit' button on 'Trip Details' | False |  | v1_edit_btn | click | trip_details | at_unloading | True |  |  | True |  |  |  |
| Trip Tracking | At Unloading | Clicks 'Close' (X) on 'Avoid Detention Bottomsheet' | False |  | v1_close | click | avoid_detention_btm_sheet | at_unloading | True |  |  | True |  |  |  |
| Trip Tracking | At Unloading | Clicks 'View Policy' on 'Avoid Detention Bottomsheet' | False |  | v1_view_policy | click | avoid_detention_btm_sheet | at_unloading | True |  |  | True |  |  |  |
| Trip Tracking | At Unloading - Insurance | Views 'Insurance Doc' | False |  | v1_insurance_doc | view | insurance_doc | at_unloading | True |  |  | True |  |  |  |
| Trip Tracking | At Unloading - Insurance | Clicks 'Download' on 'Insurance Doc' | False |  | v1_download | click | insurance_doc | at_unloading | True |  |  | True |  |  |  |
| Trip Tracking | At Unloading | Expands section on 'Driver Details' | False |  | v1_expand | click | driver_details | at_unloading | True |  | action | True |  |  |  |
| Trip Tracking | At Unloading | Clicks 'Call Driver' on 'Driver Details' | False |  | v1_call_driver | click | driver_details | at_unloading | True |  |  | True |  |  |  |
| Trip Tracking | At Unloading - Bilti / E-way / OTP | Clicks 'Download Bilti' on 'Lr Details' | False |  | v1_bilti_download | click | lr_details | at_unloading | True |  | lrnumber | True |  |  |  |
| Trip Tracking | At Unloading - Help / Ticket | Clicks 'Create Ticket' on 'Help Support' | False |  | v1_create_ticket | click | help_support | at_unloading | True |  |  | True |  |  |  |
| Trip Tracking | At Unloading - Help / Ticket | Clicks 'Need Help' on 'Help Widget' | False |  | v1_need_help | click | help_widget | at_unloading | True |  |  | True |  |  |  |
| Trip Tracking | At Unloading | Clicks 'Recenter' map on 'Map View' | False |  | v1_recenter | click | map_view | at_unloading | True |  |  | True |  |  |  |
| Trip Tracking | At Unloading | Clicks 'Share Location' on 'Map View' | False |  | v1_share_loc | click | map_view | at_unloading | True |  |  | True |  |  |  |
| Trip Tracking | At Unloading - Bilti / E-way / OTP | Clicks 'Pay & Generate OTP' on 'Map View' | False |  | v1_pay_gen_otp | click | map_view | at_unloading | True |  |  | True |  |  |  |
| Trip Tracking | At Unloading | Views 'Monsoon Alert Bottomsheet' | False |  | v1_monsoon_alert_btm_sheet | view | monsoon_alert_btm_sheet | at_unloading | True |  |  | True |  |  |  |
| Trip Tracking | At Unloading | Clicks 'Download' on 'Monsoon Alert Bottomsheet' | False |  | v1_download | click | monsoon_alert_btm_sheet | at_unloading | True |  |  | True |  |  |  |
| Trip Tracking | At Unloading | Clicks 'Close' (X) on 'Monsoon Alert Bottomsheet' | False |  | v1_close | click | monsoon_alert_btm_sheet | at_unloading | True |  |  | True |  |  |  |
| Trip Tracking | At Unloading | Expands section on 'Trip Information' | False |  | v1_expand | click | trip_information | at_unloading | True |  | action | True |  |  |  |
| Trip Tracking | At Unloading - Help / Ticket | Opens an existing ticket on 'Tickets' | False |  | v1_open_ticket | click | tickets | at_unloading | True |  | status | True |  |  |  |
| Trip Tracking | At Unloading - Invoices, Expenses & Dues | Views 'No Cash Bottomsheet' | False |  | v1_nocashbanner | view | no_cash_bottomsheet | at_unloading | True |  |  | True |  |  |  |
| Trip Tracking | At Unloading - Invoices, Expenses & Dues | Clicks 'OK' on 'No Cash Bottomsheet' | False |  | v1_ok | click | no_cash_bottomsheet | at_unloading | True |  |  | True |  |  |  |
| Trip Tracking | At Unloading - Invoices, Expenses & Dues | Clicks 'Agree' on 'No Cash Bottomsheet' | False |  | v1_agree | click | no_cash_bottomsheet | at_unloading | True |  |  | True |  |  |  |
| Trip Tracking | At Unloading - Invoices, Expenses & Dues | Clicks 'Submit' button on 'No Cash Bottomsheet' | False |  | v1_submit | click | no_cash_bottomsheet | at_unloading | True |  |  | True |  |  |  |
| Trip Tracking | At Unloading - Invoices, Expenses & Dues | Clicks 'Guideline' on 'No Cash Bottomsheet' | False |  | v1_guideline | click | no_cash_bottomsheet | at_unloading | True |  |  | True |  |  |  |
| Trip Tracking | At Unloading - Invoices, Expenses & Dues | Views 'Detention Charge Bottomsheet' | False |  | v1_detention_charge_bottomsheet | view | detention_charge_bottomsheet | at_unloading | True |  |  | True |  |  |  |
| Trip Tracking | At Unloading - Invoices, Expenses & Dues | Clicks 'Close' (X) on 'Detention Charge Bottomsheet' | False |  | v1_close | click | detention_charge_bottomsheet | at_unloading | True |  |  | True |  |  |  |
| Trip Tracking | At Unloading - Invoices, Expenses & Dues | Clicks 'Got it' on 'Detention Charge Bottomsheet' | False |  | v1_got_it | click | detention_charge_bottomsheet | at_unloading | True |  | expense_type | True |  |  |  |
| Trip Tracking | At Unloading - Invoices, Expenses & Dues | Clicks 'Read Policy' on 'Detention Charge Bottomsheet' | False |  | v1_read_policy | click | detention_charge_bottomsheet | at_unloading | True |  |  | True |  |  |  |
| Trip Tracking | At Unloading - Invoices, Expenses & Dues | Views 'Due Payment Amount Widget' | False |  | v1_due_payment_amount_widget | view | due_payment_amount_widget | at_unloading | True |  |  | True |  |  |  |
| Trip Tracking | At Unloading - Invoices, Expenses & Dues | Views 'Pending Expense Bottomsheet' | False |  | v1_pending_expense | view | pending_expense_bottomsheet | at_unloading | True |  |  | True |  |  |  |
| Trip Tracking | At Unloading - Invoices, Expenses & Dues | Clicks 'Close' (X) on 'Pending Expense Bottomsheet' | False |  | v1_close | click | pending_expense_bottomsheet | at_unloading | True |  |  | True |  |  |  |
| Trip Tracking | At Unloading - Invoices, Expenses & Dues | Clicks 'Price Breakup' on 'Pending Expense Bottomsheet' | False |  | v1_price_breakup | click | pending_expense_bottomsheet | at_unloading | True |  |  | True |  |  |  |
| Trip Tracking | At Unloading - Bilti / E-way / OTP | Views 'Otp View' | False |  | v1_otp | view | otp_view | at_unloading | True |  |  | True |  |  |  |
| Trip Tracking | At Unloading - Bilti / E-way / OTP | Clicks 'Complete Kyc Payment' on 'Otp View' | False |  | v1_complete_kyc_payment | click | otp_view | at_unloading | True |  | action | True |  |  |  |
| Trip Tracking | At Unloading - Help / Ticket | Clicks 'Raise Issue' | False |  | v1_raise_issue | click | bottom_nav | at_unloading | True |  | expense_type | True |  |  |  |
| Trip Tracking | At Unloading - Invoices, Expenses & Dues | Clicks 'Pay Now' on 'Freight Invoice' | False |  | v1_pay_now | click | freight_invoice | at_unloading | False |  | amt | True |  |  |  |
| Trip Tracking | At Unloading - VIP Pass / Coupon | Views 'Unlock Pass Bottomsheet' | False |  | v1_unlock_pass | view | unlock_pass_btmsheet | at_unloading | True |  | type | True |  |  |  |
| Trip Tracking | At Unloading - VIP Pass / Coupon | Clicks 'Conf Pass' on 'Unlock Pass Bottomsheet' | False |  | v1_conf_pass | click | unlock_pass_btmsheet | at_unloading | True |  |  | True |  |  |  |
| Trip Tracking | At Unloading - VIP Pass / Coupon | Clicks 'Explore Plans' on 'Unlock Pass Bottomsheet' | False |  | v1_explore_plans | click | unlock_pass_btmsheet | at_unloading | True |  |  | True |  |  |  |
| Trip Tracking | At Unloading - Invoices, Expenses & Dues | Clicks 'Submit' button on 'Extra Charge Policy Popup' | False |  | v1_submit_btn | click | extra_charge_policy_popup | at_unloading | True |  |  | True |  |  |  |
| Trip Tracking | At Unloading - Bilti / E-way / OTP | Clicks 'Add Eway Bill' on 'Bilti Train Bottomsheet' | False |  | v1_add_eway_bill | click | bilti_train_btmsheet | at_unloading | True |  | text | True |  |  |  |
| Trip Tracking | Trip End - Cancellation |  | False |  | v1_cancel_fee_btmsheet | view |  | trip_end | True |  |  | True |  |  |  |
| Trip Tracking | Trip End - VIP Pass / Coupon |  | False |  | v1_promo_applied | view |  | trip_end | False |  | disc_type | True |  |  |  |
| Trip Tracking | Trip End - Invoices, Expenses & Dues | Clicks 'Trip End' | False |  | v1_trip_end | click |  | trip_end | True |  |  | True |  |  |  |
| Trip Tracking | Trip End - VIP Pass / Coupon | Clicks 'Save With Pass' | False |  | v1_save_with_pass | click |  | trip_end | True |  |  | True |  |  |  |
| Trip Tracking | Trip End - Invoices, Expenses & Dues | Clicks 'Unlock Discount' | False |  | v1_unlock_discount | click |  | trip_end | True |  |  | True |  |  |  |
| Trip Tracking | Trip End - Invoices, Expenses & Dues | Views 'Trip Details' | False |  | v1_halt_info | view | trip_details | trip_end | True |  |  | True |  |  |  |
| Trip Tracking | Trip End - Invoices, Expenses & Dues | Views 'Trip Details' | False |  | v1_veh_status | view | trip_details | trip_end | True |  | start | True |  |  |  |
| Trip Tracking | Trip End - Edit Booking | Views 'Trip Details' | False |  | v1_edit_btn | view | trip_details | trip_end | True |  |  | True |  |  |  |
| Trip Tracking | Trip End - Invoices, Expenses & Dues | Clicks 'View Details' on 'Trip Details' | False |  | v1_view_details_btn | click | trip_details | trip_end | True |  | expense_type | True |  |  |  |
| Trip Tracking | Trip End - Edit Booking | Clicks 'Edit' button on 'Trip Details' | False |  | v1_edit_btn | click | trip_details | trip_end | True |  |  | True |  |  |  |
| Trip Tracking | Trip End - Bilti / E-way / OTP | Clicks 'Share' on 'Trip Details' | False |  | v1_share | click | trip_details | trip_end | True |  |  | True |  |  |  |
| Trip Tracking | Trip End - Invoices, Expenses & Dues | Switches trip details tab | False |  | v1_screen_fliter | click | top_nav | trip_end | True |  | segment | True |  |  |  |
| Trip Tracking | Trip End - Invoices, Expenses & Dues | Clicks 'Back' arrow | False |  | v1_back_btn | click | top_nav | trip_end | True |  | timer | True |  |  |  |
| Trip Tracking | Trip End - Feedback & Rating | Views 'Rating Bottomsheet' | False |  | v1_rating | view | rating_bottom_sheet | trip_end | True |  | rate | True |  |  |  |
| Trip Tracking | Trip End - Feedback & Rating | Clicks 'Submit' button on 'Rating Bottomsheet' | False |  | v1_submit_btn | click | rating_bottom_sheet | trip_end | True |  | rate | True |  |  |  |
| Trip Tracking | Trip End - Feedback & Rating | Selects star rating on 'Rating Bottomsheet' | False |  | v1_rating | click | rating_bottom_sheet | trip_end | True |  | rate | True |  |  |  |
| Trip Tracking | Trip End - Feedback & Rating | Selects a reason on 'Rating Bottomsheet' | False |  | v1_reason_selected | click | rating_bottom_sheet | trip_end | True |  | rate | True |  |  |  |
| Trip Tracking | Trip End - Feedback & Rating | Deselects a reason on 'Rating Bottomsheet' | False |  | v1_reason_deslected | click | rating_bottom_sheet | trip_end | True |  | rate | True |  |  |  |
| Trip Tracking | Trip End - Insurance | Views 'Insurance Doc' | False |  | v1_insurance_doc | view | insurance_doc | trip_end | True |  |  | True |  |  |  |
| Trip Tracking | Trip End - Insurance | Clicks 'Download' on 'Insurance Doc' | False |  | v1_download | click | insurance_doc | trip_end | True |  |  | True |  |  |  |
| Trip Tracking | Trip End - Bilti / E-way / OTP | Clicks 'Download POD' on 'Lr Details' | False |  | v1_pod_download | click | lr_details | trip_end | True |  |  | True |  |  |  |
| Trip Tracking | Trip End - Bilti / E-way / OTP | Clicks 'View LR' on 'Lr Details' | False |  | v1_view_lr | click | lr_details | trip_end | True |  |  | True |  |  |  |
| Trip Tracking | Trip End - Bilti / E-way / OTP | Clicks 'Download Bilti' on 'Lr Details' | False |  | v1_bilti_download | click | lr_details | trip_end | True |  | lrnumber | True |  |  |  |
| Trip Tracking | Trip End - Help / Ticket | Clicks 'Create Ticket' on 'Help Support' | False |  | v1_create_ticket | click | help_support | trip_end | True |  |  | True |  |  |  |
| Trip Tracking | Trip End - Help / Ticket | Clicks 'Need Help' on 'Help Widget' | False |  | v1_need_help | click | help_widget | trip_end | True |  |  | True |  |  |  |
| Trip Tracking | Trip End - Invoices, Expenses & Dues | Views 'Detention Charge Bottomsheet' | False |  | v1_detention_charge_bottomsheet | view | detention_charge_bottomsheet | trip_end | True |  |  | True |  |  |  |
| Trip Tracking | Trip End - Invoices, Expenses & Dues | Clicks 'Close' (X) on 'Detention Charge Bottomsheet' | False |  | v1_close | click | detention_charge_bottomsheet | trip_end | True |  |  | True |  |  |  |
| Trip Tracking | Trip End - Invoices, Expenses & Dues | Clicks 'Got it' on 'Detention Charge Bottomsheet' | False |  | v1_got_it | click | detention_charge_bottomsheet | trip_end | True |  | expense_type | True |  |  |  |
| Trip Tracking | Trip End - Invoices, Expenses & Dues | Clicks 'Read Policy' on 'Detention Charge Bottomsheet' | False |  | v1_read_policy | click | detention_charge_bottomsheet | trip_end | True |  |  | True |  |  |  |
| Trip Tracking | Trip End - Help / Ticket | Clicks 'Raise Issue' | False |  | v1_raise_issue | click | bottom_nav | trip_end | True |  | expense_type | True |  |  |  |
| Trip Tracking | Trip End - Help / Ticket | Opens an existing ticket on 'Tickets' | False |  | v1_open_ticket | click | tickets | trip_end | True |  | status | True |  |  |  |
| Trip Tracking | Trip End - Invoices, Expenses & Dues | Clicks 'Pay Now' on 'Freight Invoice' | False |  | v1_pay_now | click | freight_invoice | trip_end | False |  | amt | True |  |  |  |
| Trip Tracking | Trip End - Invoices, Expenses & Dues | Views 'Pending Due Screen' | False |  | v1_pending_due | view | pending_due_screen | trip_end | True |  |  | True |  |  |  |
| Trip Tracking | Trip End - Invoices, Expenses & Dues | Clicks 'Price Breakup' on 'Pending Due Screen' | False |  | v1_price_breakup | click | pending_due_screen | trip_end | True |  |  | True |  |  |  |
| Trip Tracking | Trip End - Invoices, Expenses & Dues | Clicks 'Pay' on 'Pending Due Screen' | False |  | v1_pay | click | pending_due_screen | trip_end | True |  |  | True |  |  |  |
| Trip Tracking | Trip End - Invoices, Expenses & Dues | Views 'Due Payment Amount Widget' | False |  | v1_due_payment_amount_widget | view | due_payment_amount_widget | trip_end | True |  |  | True |  |  |  |
| Trip Tracking | Trip End - Invoices, Expenses & Dues | Views 'Shipment Safety' | False |  | v1_shipment_safety | view | shipment_safety | trip_end | True |  |  | True |  |  |  |
| Trip Tracking | Trip End - Invoices, Expenses & Dues | Clicks 'Yes' on 'Shipment Safety' | False |  | v1_yes | click | shipment_safety | trip_end | True |  |  | True |  |  |  |
| Trip Tracking | Trip End - Invoices, Expenses & Dues | Clicks 'Report Issue' on 'Shipment Safety' | False |  | v1_report_issue | click | shipment_safety | trip_end | True |  |  | True |  |  |  |
| Trip Tracking | Trip End - Bilti / E-way / OTP | Views 'Otp View' | False |  | v1_otp | view | otp_view | trip_end | True |  |  | True |  |  |  |
| Trip Tracking | Trip End - Bilti / E-way / OTP | Clicks 'Complete Kyc Payment' on 'Otp View' | False |  | v1_complete_kyc_payment | click | otp_view | trip_end | True |  | action | True |  |  |  |
| Trip Tracking | Trip End - Invoices, Expenses & Dues | Views 'No Cash Bottomsheet' | False |  | v1_nocashbanner | view | no_cash_bottomsheet | trip_end | True |  |  | True |  |  |  |
| Trip Tracking | Trip End - Invoices, Expenses & Dues | Clicks 'Agree' on 'No Cash Bottomsheet' | False |  | v1_agree | click | no_cash_bottomsheet | trip_end | True |  |  | True |  |  |  |
| Trip Tracking | Trip End - Invoices, Expenses & Dues | Clicks 'Submit' button on 'No Cash Bottomsheet' | False |  | v1_submit | click | no_cash_bottomsheet | trip_end | True |  |  | True |  |  |  |
| Trip Tracking | Trip End - Invoices, Expenses & Dues | Views 'Invoice Locked Bottomsheet' | False |  | v1_invoice_sheet | view | invoice_locked_bottomsheet | trip_end | True |  |  | True |  |  |  |
| Trip Tracking | Trip End - Invoices, Expenses & Dues | Clicks 'Close' (X) on 'Invoice Locked Bottomsheet' | False |  | v1_close | click | invoice_locked_bottomsheet | trip_end | True |  |  | True |  |  |  |
| Trip Tracking | Trip End - Invoices, Expenses & Dues | Clicks 'Price Breakup' on 'Invoice Locked Bottomsheet' | False |  | v1_price_breakup | click | invoice_locked_bottomsheet | trip_end | True |  |  | True |  |  |  |
| Trip Tracking | Trip End - Invoices, Expenses & Dues | Clicks 'Pay' on 'Invoice Locked Bottomsheet' | False |  | v1_pay | click | invoice_locked_bottomsheet | trip_end | True |  |  | True |  |  |  |
| Trip Tracking | Trip End - Invoices, Expenses & Dues | Views 'Pod Locked Bottomsheet' | False |  | v1_pod_sheet | view | pod_locked_bottomsheet | trip_end | True |  |  | True |  |  |  |
| Trip Tracking | Trip End - Invoices, Expenses & Dues | Clicks 'Close' (X) on 'Pod Locked Bottomsheet' | False |  | v1_close | click | pod_locked_bottomsheet | trip_end | True |  |  | True |  |  |  |
| Trip Tracking | Trip End - Invoices, Expenses & Dues | Clicks 'Price Breakup' on 'Pod Locked Bottomsheet' | False |  | v1_price_breakup | click | pod_locked_bottomsheet | trip_end | True |  |  | True |  |  |  |
| Trip Tracking | Trip End - Invoices, Expenses & Dues | Clicks 'Pay' on 'Pod Locked Bottomsheet' | False |  | v1_pay | click | pod_locked_bottomsheet | trip_end | True |  |  | True |  |  |  |
| Trip Tracking | Trip End - Invoices, Expenses & Dues | Clicks 'Submit' button on 'Extra Charge Policy Popup' | False |  | v1_submit_btn | click | extra_charge_policy_popup | trip_end | True |  |  | True |  |  |  |
| Trip Tracking | Trip End - VIP Pass / Coupon | Views 'Unlock Pass Bottomsheet' | False |  | v1_unlock_pass | view | unlock_pass_btmsheet | trip_end | True |  | type | True |  |  |  |
| Trip Tracking | Trip End - VIP Pass / Coupon | Clicks 'Conf Pass' on 'Unlock Pass Bottomsheet' | False |  | v1_conf_pass | click | unlock_pass_btmsheet | trip_end | True |  |  | True |  |  |  |
| Trip Tracking | Trip End - Bilti / E-way / OTP | Clicks 'Pay & Generate OTP' on 'Map View' | False |  | v1_pay_gen_otp | click | map_view | trip_end | True |  |  | True |  |  |  |
| Trip Tracking | Extra Charge Policy - Invoices, Expenses & Dues |  | True |  | v1_extra_charge_policy | view |  | extra_charge_policy | True |  |  | True |  |  |  |
| Trip Tracking | Damage/Shortage Policy | Clicks 'Back' arrow | False |  | v1_back_btn | click | top_nav | damage/shortage policy | True |  | timer | True |  |  |  |
| Trip Tracking | Damage/Shortage Policy | Clicks 'Got it' | False |  | v1_got_it | click | bottom_nav | damage/shortage policy | False |  |  | True |  |  |  |
| Bilti / E-way Bill | Trip Scheduled - Bilti / E-way / OTP | Views 'Otp View' | False |  | v1_otp | view | otp_view | scheduled | True |  |  | True |  |  |  |
| Bilti / E-way Bill | Trip Scheduled - Bilti / E-way / OTP | Clicks 'Complete Kyc Payment' on 'Otp View' | False |  | v1_complete_kyc_payment | click | otp_view | scheduled | True |  | action | True |  |  |  |
| Bilti / E-way Bill | Going To Load - Bilti / E-way / OTP | Views 'Otp View' | False |  | v1_otp | view | otp_view | going_to_load | True |  |  | True |  |  |  |
| Bilti / E-way Bill | Going To Load - Bilti / E-way / OTP | Clicks 'Complete Kyc Payment' on 'Otp View' | False |  | v1_complete_kyc_payment | click | otp_view | going_to_load | True |  | action | True |  |  |  |
| Bilti / E-way Bill | Going To Load - Bilti / E-way / OTP | Views 'Trip Details' | False |  | v1_bilti_download_due_payment | view | trip_details | going_to_load | True |  |  | True |  |  |  |
| Bilti / E-way Bill | Going To Load - Bilti / E-way / OTP | Clicks 'Share' on 'Trip Details' | False |  | v1_share | click | trip_details | going_to_load | True |  |  | True |  |  |  |
| Bilti / E-way Bill | Going To Load - Bilti / E-way / OTP | Clicks 'Add LR' on 'Trip Details' | False |  | v1_add_lr | click | trip_details | going_to_load | True |  |  | True |  |  |  |
| Bilti / E-way Bill | Going To Load - Bilti / E-way / OTP | Clicks 'Bilti Download Due Payment' on 'Trip Details' | False |  | v1_bilti_download_due_payment | click | trip_details | going_to_load | True |  |  | True |  |  |  |
| Bilti / E-way Bill | Going To Load - Bilti / E-way / OTP | Clicks 'Pay & Generate OTP' on 'Map View' | False |  | v1_pay_gen_otp | click | map_view | going_to_load | True |  |  | True |  |  |  |
| Bilti / E-way Bill | Going To Load - Bilti / E-way / OTP | Clicks 'Generate OTP' on 'Map View' | False |  | v1_gen_otp | click | map_view | going_to_load | True |  |  | True |  |  |  |
| Bilti / E-way Bill | Going To Load - Bilti / E-way / OTP | Clicks 'Share OTP' on 'Map View' | False |  | v1_share_otp | click | map_view | going_to_load | True |  | otp | True |  |  |  |
| Bilti / E-way Bill | Going To Load - Bilti / E-way / OTP | Clicks 'Add Eway Bill' on 'Bilti Train Bottomsheet' | False |  | v1_add_eway_bill | click | bilti_train_btmsheet | going_to_load | True |  | text | True |  |  |  |
| Bilti / E-way Bill | Going To Load - Bilti / E-way / OTP | Clicks 'Download Bilti' on 'Lr Details' | False |  | v1_bilti_download | click | lr_details | going_to_load | True |  | lrnumber | True |  |  |  |
| Bilti / E-way Bill | Going To Load - Bilti / E-way / OTP | Clicks 'Generate OTP' on 'Eway Confirm Bottomsheet' | False |  | v1_gen_otp | click | eway_confirm_btmsheet | going_to_load | True |  |  | True |  |  |  |
| Bilti / E-way Bill | Going To Load - Bilti / E-way / OTP | Clicks 'Yes' on 'No Eway Bottomsheet' | False |  | v1_yes | click | no_eway_btmsheet | going_to_load | True |  |  | True |  |  |  |
| Bilti / E-way Bill | Going To Load - Bilti / E-way / OTP | Clicks 'Close' (X) on 'No Eway Bottomsheet' | False |  | v1_close | click | no_eway_btmsheet | going_to_load | True |  |  | True |  |  |  |
| Bilti / E-way Bill | Going To Load - Bilti / E-way / OTP | Clicks 'No' on 'No Eway Bottomsheet' | False |  | v1_no | click | no_eway_btmsheet | going_to_load | True |  |  | True |  |  |  |
| Bilti / E-way Bill | Going To Load - Bilti / E-way / OTP | Clicks 'Close' (X) on 'Otp Bottomsheet' | False |  | v1_close | click | otp_btmsheet | going_to_load | True |  |  | True |  |  |  |
| Bilti / E-way Bill | Going To Load - Bilti / E-way / OTP | Clicks 'Download' on 'Otp Bottomsheet' | False |  | v1_download | click | otp_btmsheet | going_to_load | True |  |  | True |  |  |  |
| Bilti / E-way Bill | Going To Load - Bilti / E-way / OTP | Clicks 'Share OTP' on 'Otp Bottomsheet' | False |  | v1_share_otp | click | otp_btmsheet | going_to_load | True |  | otp | True |  |  |  |
| Bilti / E-way Bill | Going To Load - Bilti / E-way / OTP | Clicks 'Add E-way Bill' on 'Otp Bottomsheet' | False |  | v1_add_eway | click | otp_btmsheet | going_to_load | True |  |  | True |  |  |  |
| Bilti / E-way Bill | Going To Load - Bilti / E-way / OTP | Clicks 'Close' (X) on 'Eway Add Bottomsheet' | False |  | v1_close | click | eway_add_btmsheet | going_to_load | True |  |  | True |  |  |  |
| Bilti / E-way Bill | Going To Load - Bilti / E-way / OTP | Clicks 'Submit' button on 'Eway Add Bottomsheet' | False |  | v1_submit | click | eway_add_btmsheet | going_to_load | True |  |  | True |  |  |  |
| Bilti / E-way Bill | Going To Load - Bilti / E-way / OTP | Clicks 'Add E-way Bill' on 'Eway Add Bottomsheet' | False |  | v1_add_eway | click | eway_add_btmsheet | going_to_load | True |  |  | True |  |  |  |
| Bilti / E-way Bill | At Loading - Bilti / E-way / OTP | Views 'Otp View' | False |  | v1_otp | view | otp_view | at_loading | True |  |  | True |  |  |  |
| Bilti / E-way Bill | At Loading - Bilti / E-way / OTP | Clicks 'Complete Kyc Payment' on 'Otp View' | False |  | v1_complete_kyc_payment | click | otp_view | at_loading | True |  | action | True |  |  |  |
| Bilti / E-way Bill | At Loading - Bilti / E-way / OTP | Views 'Trip Details' | False |  | v1_bilti_download_due_payment | view | trip_details | at_loading | True |  |  | True |  |  |  |
| Bilti / E-way Bill | At Loading - Bilti / E-way / OTP | Clicks 'Share' on 'Trip Details' | False |  | v1_share | click | trip_details | at_loading | True |  |  | True |  |  |  |
| Bilti / E-way Bill | At Loading - Bilti / E-way / OTP | Clicks 'Add LR' on 'Trip Details' | False |  | v1_add_lr | click | trip_details | at_loading | True |  |  | True |  |  |  |
| Bilti / E-way Bill | At Loading - Bilti / E-way / OTP | Clicks 'Bilti Download Due Payment' on 'Trip Details' | False |  | v1_bilti_download_due_payment | click | trip_details | at_loading | True |  |  | True |  |  |  |
| Bilti / E-way Bill | At Loading - Bilti / E-way / OTP | Clicks 'Generate OTP' on 'Map View' | False |  | v1_gen_otp | click | map_view | at_loading | True |  |  | True |  |  |  |
| Bilti / E-way Bill | At Loading - Bilti / E-way / OTP | Clicks 'Pay & Generate OTP' on 'Map View' | False |  | v1_pay_gen_otp | click | map_view | at_loading | True |  |  | True |  |  |  |
| Bilti / E-way Bill | At Loading - Bilti / E-way / OTP | Clicks 'Share OTP' on 'Map View' | False |  | v1_share_otp | click | map_view | at_loading | True |  | otp | True |  |  |  |
| Bilti / E-way Bill | At Loading - Bilti / E-way / OTP | Clicks 'Download Bilti' on 'Lr Details' | False |  | v1_bilti_download | click | lr_details | at_loading | True |  | lrnumber | True |  |  |  |
| Bilti / E-way Bill | At Loading - Bilti / E-way / OTP | Clicks 'Generate OTP' on 'Eway Confirm Bottomsheet' | False |  | v1_gen_otp | click | eway_confirm_btmsheet | at_loading | True |  |  | True |  |  |  |
| Bilti / E-way Bill | At Loading - Bilti / E-way / OTP | Clicks 'Yes' on 'No Eway Bottomsheet' | False |  | v1_yes | click | no_eway_btmsheet | at_loading | True |  |  | True |  |  |  |
| Bilti / E-way Bill | At Loading - Bilti / E-way / OTP | Clicks 'No' on 'No Eway Bottomsheet' | False |  | v1_no | click | no_eway_btmsheet | at_loading | True |  |  | True |  |  |  |
| Bilti / E-way Bill | At Loading - Bilti / E-way / OTP | Clicks 'Close' (X) on 'No Eway Bottomsheet' | False |  | v1_close | click | no_eway_btmsheet | at_loading | True |  |  | True |  |  |  |
| Bilti / E-way Bill | At Loading - Bilti / E-way / OTP | Clicks 'Download' on 'Otp Bottomsheet' | False |  | v1_download | click | otp_btmsheet | at_loading | True |  |  | True |  |  |  |
| Bilti / E-way Bill | At Loading - Bilti / E-way / OTP | Clicks 'Close' (X) on 'Otp Bottomsheet' | False |  | v1_close | click | otp_btmsheet | at_loading | True |  |  | True |  |  |  |
| Bilti / E-way Bill | At Loading - Bilti / E-way / OTP | Clicks 'Share OTP' on 'Otp Bottomsheet' | False |  | v1_share_otp | click | otp_btmsheet | at_loading | True |  | otp | True |  |  |  |
| Bilti / E-way Bill | At Loading - Bilti / E-way / OTP | Clicks 'Add E-way Bill' on 'Otp Bottomsheet' | False |  | v1_add_eway | click | otp_btmsheet | at_loading | True |  |  | True |  |  |  |
| Bilti / E-way Bill | At Loading - Bilti / E-way / OTP | Clicks 'Add Eway Bill' on 'Bilti Train Bottomsheet' | False |  | v1_add_eway_bill | click | bilti_train_btmsheet | at_loading | True |  | text | True |  |  |  |
| Bilti / E-way Bill | At Loading - Bilti / E-way / OTP | Clicks 'Submit' button on 'Eway Add Bottomsheet' | False |  | v1_submit | click | eway_add_btmsheet | at_loading | True |  |  | True |  |  |  |
| Bilti / E-way Bill | At Loading - Bilti / E-way / OTP | Clicks 'Close' (X) on 'Eway Add Bottomsheet' | False |  | v1_close | click | eway_add_btmsheet | at_loading | True |  |  | True |  |  |  |
| Bilti / E-way Bill | At Loading - Bilti / E-way / OTP | Clicks 'Add E-way Bill' on 'Eway Add Bottomsheet' | False |  | v1_add_eway | click | eway_add_btmsheet | at_loading | True |  |  | True |  |  |  |
| Bilti / E-way Bill | Bilti Training - Bilti / E-way / OTP | Views 'Bilti Overlay' | False |  | v1_bilti_overlay | view | bilti_overlay | bilti_training | True |  |  | True |  |  |  |
| Bilti / E-way Bill | Bilti Training - Bilti / E-way / OTP | Clicks 'Next' button | False |  | v1_next | click | bottom_nav | bilti_training | True |  | current_page | True |  |  |  |
| Bilti / E-way Bill | Bilti Training - Bilti / E-way / OTP | Clicks 'Previous' button | False |  | v1_previous | click | bottom_nav | bilti_training | True |  | current_page | True |  |  |  |
| Bilti / E-way Bill | Bilti Training - Bilti / E-way / OTP | Clicks 'Close' (X) | False |  | v1_close | click | top_nav | bilti_training | True |  | current_page | True |  |  |  |
| Bilti / E-way Bill | In Transit - Bilti / E-way / OTP | Clicks 'Share' on 'Trip Details' | False |  | v1_share | click | trip_details | in_transit | True |  |  | True |  |  |  |
| Bilti / E-way Bill | In Transit - Bilti / E-way / OTP | Clicks 'Pay & Generate OTP' on 'Map View' | False |  | v1_pay_gen_otp | click | map_view | in_transit | True |  |  | True |  |  |  |
| Bilti / E-way Bill | In Transit - Bilti / E-way / OTP | Clicks 'Share OTP' on 'Map View' | False |  | v1_share_otp | click | map_view | in_transit | True |  | otp | True |  |  |  |
| Bilti / E-way Bill | In Transit - Bilti / E-way / OTP | Clicks 'Download Bilti' on 'Lr Details' | False |  | v1_bilti_download | click | lr_details | in_transit | True |  | lrnumber | True |  |  |  |
| Bilti / E-way Bill | In Transit - Bilti / E-way / OTP | Views 'Otp View' | False |  | v1_otp | view | otp_view | in_transit | True |  |  | True |  |  |  |
| Bilti / E-way Bill | In Transit - Bilti / E-way / OTP | Clicks 'Complete Kyc Payment' on 'Otp View' | False |  | v1_complete_kyc_payment | click | otp_view | in_transit | True |  | action | True |  |  |  |
| Bilti / E-way Bill | In Transit - Bilti / E-way / OTP | Clicks 'Add Eway Bill' on 'Bilti Train Bottomsheet' | False |  | v1_add_eway_bill | click | bilti_train_btmsheet | in_transit | True |  | text | True |  |  |  |
| Bilti / E-way Bill | In Transit - Bilti / E-way / OTP | Clicks 'Download' on 'Otp Bottomsheet' | False |  | v1_download | click | otp_btmsheet | in_transit | True |  |  | True |  |  |  |
| Bilti / E-way Bill | In Transit - Bilti / E-way / OTP | Clicks 'Close' (X) on 'Otp Bottomsheet' | False |  | v1_close | click | otp_btmsheet | in_transit | True |  |  | True |  |  |  |
| Bilti / E-way Bill | In Transit - Bilti / E-way / OTP | Clicks 'Share OTP' on 'Otp Bottomsheet' | False |  | v1_share_otp | click | otp_btmsheet | in_transit | True |  | otp | True |  |  |  |
| Bilti / E-way Bill | In Transit - Bilti / E-way / OTP | Clicks 'Close' (X) on 'Eway Add Bottomsheet' | False |  | v1_close | click | eway_add_btmsheet | in_transit | True |  |  | True |  |  |  |
| Bilti / E-way Bill | In Transit - Bilti / E-way / OTP | Clicks 'Submit' button on 'Eway Add Bottomsheet' | False |  | v1_submit | click | eway_add_btmsheet | in_transit | True |  |  | True |  |  |  |
| Bilti / E-way Bill | At Unloading - Bilti / E-way / OTP | Clicks 'Download Bilti' on 'Lr Details' | False |  | v1_bilti_download | click | lr_details | at_unloading | True |  | lrnumber | True |  |  |  |
| Bilti / E-way Bill | At Unloading - Bilti / E-way / OTP | Clicks 'Pay & Generate OTP' on 'Map View' | False |  | v1_pay_gen_otp | click | map_view | at_unloading | True |  |  | True |  |  |  |
| Bilti / E-way Bill | At Unloading - Bilti / E-way / OTP | Views 'Otp View' | False |  | v1_otp | view | otp_view | at_unloading | True |  |  | True |  |  |  |
| Bilti / E-way Bill | At Unloading - Bilti / E-way / OTP | Clicks 'Complete Kyc Payment' on 'Otp View' | False |  | v1_complete_kyc_payment | click | otp_view | at_unloading | True |  | action | True |  |  |  |
| Bilti / E-way Bill | At Unloading - Bilti / E-way / OTP | Clicks 'Add Eway Bill' on 'Bilti Train Bottomsheet' | False |  | v1_add_eway_bill | click | bilti_train_btmsheet | at_unloading | True |  | text | True |  |  |  |
| Bilti / E-way Bill | Trip End - Bilti / E-way / OTP | Clicks 'Share' on 'Trip Details' | False |  | v1_share | click | trip_details | trip_end | True |  |  | True |  |  |  |
| Bilti / E-way Bill | Trip End - Bilti / E-way / OTP | Clicks 'Download POD' on 'Lr Details' | False |  | v1_pod_download | click | lr_details | trip_end | True |  |  | True |  |  |  |
| Bilti / E-way Bill | Trip End - Bilti / E-way / OTP | Clicks 'View LR' on 'Lr Details' | False |  | v1_view_lr | click | lr_details | trip_end | True |  |  | True |  |  |  |
| Bilti / E-way Bill | Trip End - Bilti / E-way / OTP | Clicks 'Download Bilti' on 'Lr Details' | False |  | v1_bilti_download | click | lr_details | trip_end | True |  | lrnumber | True |  |  |  |
| Bilti / E-way Bill | Trip End - Bilti / E-way / OTP | Views 'Otp View' | False |  | v1_otp | view | otp_view | trip_end | True |  |  | True |  |  |  |
| Bilti / E-way Bill | Trip End - Bilti / E-way / OTP | Clicks 'Complete Kyc Payment' on 'Otp View' | False |  | v1_complete_kyc_payment | click | otp_view | trip_end | True |  | action | True |  |  |  |
| Bilti / E-way Bill | Trip End - Bilti / E-way / OTP | Clicks 'Pay & Generate OTP' on 'Map View' | False |  | v1_pay_gen_otp | click | map_view | trip_end | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Searching Price - Invoices, Expenses & Dues | Views 'Pending Due Agreement Sheet' | False |  | v1_payment_note_sheet | view | pending_due_agreement_sheet | searching_price | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Searching Price - Invoices, Expenses & Dues | Clicks 'Agree' on 'Pending Due Agreement Sheet' | False |  | v1_agree | click | pending_due_agreement_sheet | searching_price | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Searching Price - Invoices, Expenses & Dues | Clicks 'View Detail' on 'Pending Due Agreement Sheet' | False |  | v1_view_detail | click | pending_due_agreement_sheet | searching_price | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Searching Price - Invoices, Expenses & Dues | Clicks 'View All' on 'Pending Due Agreement Sheet' | False |  | v1_view_all | click | pending_due_agreement_sheet | searching_price | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Trip Scheduled - Invoices, Expenses & Dues | Clicks 'View Details' on 'Trip Details' | False |  | v1_view_details_btn | click | trip_details | scheduled | True |  | expense_type | True |  |  |  |
| Invoices, Expenses & Dues | Trip Scheduled - Invoices, Expenses & Dues | Views 'Detention Charge Bottomsheet' | False |  | v1_detention_charge_bottomsheet | view | detention_charge_bottomsheet | scheduled | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Trip Scheduled - Invoices, Expenses & Dues | Clicks 'Close' (X) on 'Detention Charge Bottomsheet' | False |  | v1_close | click | detention_charge_bottomsheet | scheduled | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Trip Scheduled - Invoices, Expenses & Dues | Clicks 'Got it' on 'Detention Charge Bottomsheet' | False |  | v1_got_it | click | detention_charge_bottomsheet | scheduled | True |  | expense_type | True |  |  |  |
| Invoices, Expenses & Dues | Trip Scheduled - Invoices, Expenses & Dues | Clicks 'Read Policy' on 'Detention Charge Bottomsheet' | False |  | v1_read_policy | click | detention_charge_bottomsheet | scheduled | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Trip Scheduled - Invoices, Expenses & Dues | Clicks 'Submit' button on 'Extra Charge Policy Popup' | False |  | v1_submit_btn | click | extra_charge_policy_popup | scheduled | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Trip Scheduled - Invoices, Expenses & Dues | Views 'Past Trip Balance' | False |  | v1_past_payment | view | past_trip_balance | scheduled | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Trip Scheduled - Invoices, Expenses & Dues | Clicks 'Past View Detail' on 'Past Trip Balance' | False |  | v1_past_view_detail | click | past_trip_balance | scheduled | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Trip Details - Invoices, Expenses & Dues |  | False |  | v1_expense_confirm | view | bottom_nav | demand_detail | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Going To Load - Invoices, Expenses & Dues | Clicks 'Unlock Discount' | False |  | v1_unlock_discount | click |  | going_to_load | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Going To Load - Invoices, Expenses & Dues | Clicks 'View Details' on 'Trip Details' | False |  | v1_view_details_btn | click | trip_details | going_to_load | True |  | expense_type | True |  |  |  |
| Invoices, Expenses & Dues | Going To Load - Invoices, Expenses & Dues | Views 'No Cash Bottomsheet' | False |  | v1_nocashbanner | view | no_cash_bottomsheet | going_to_load | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Going To Load - Invoices, Expenses & Dues | Clicks 'Agree' on 'No Cash Bottomsheet' | False |  | v1_agree | click | no_cash_bottomsheet | going_to_load | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Going To Load - Invoices, Expenses & Dues | Clicks 'Submit' button on 'No Cash Bottomsheet' | False |  | v1_submit | click | no_cash_bottomsheet | going_to_load | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Going To Load - Invoices, Expenses & Dues | Clicks 'Pay Now' on 'Freight Invoice' | False |  | v1_pay_now | click | freight_invoice | going_to_load | False |  | amt | True |  |  |  |
| Invoices, Expenses & Dues | Going To Load - Invoices, Expenses & Dues | Views 'Detention Charge Bottomsheet' | False |  | v1_detention_charge_bottomsheet | view | detention_charge_bottomsheet | going_to_load | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Going To Load - Invoices, Expenses & Dues | Clicks 'Close' (X) on 'Detention Charge Bottomsheet' | False |  | v1_close | click | detention_charge_bottomsheet | going_to_load | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Going To Load - Invoices, Expenses & Dues | Clicks 'Got it' on 'Detention Charge Bottomsheet' | False |  | v1_got_it | click | detention_charge_bottomsheet | going_to_load | True |  | expense_type | True |  |  |  |
| Invoices, Expenses & Dues | Going To Load - Invoices, Expenses & Dues | Clicks 'Read Policy' on 'Detention Charge Bottomsheet' | False |  | v1_read_policy | click | detention_charge_bottomsheet | going_to_load | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Going To Load - Invoices, Expenses & Dues | Views 'Past Trip Balance' | False |  | v1_past_payment | view | past_trip_balance | going_to_load | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Going To Load - Invoices, Expenses & Dues | Clicks 'Past View Detail' on 'Past Trip Balance' | False |  | v1_past_view_detail | click | past_trip_balance | going_to_load | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Going To Load - Invoices, Expenses & Dues | Clicks 'Submit' button on 'Extra Charge Policy Popup' | False |  | v1_submit_btn | click | extra_charge_policy_popup | going_to_load | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | At Loading - Invoices, Expenses & Dues | Clicks 'Unlock Discount' | False |  | v1_unlock_discount | click |  | at_loading | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | At Loading - Invoices, Expenses & Dues | Clicks 'View Details' on 'Trip Details' | False |  | v1_view_details_btn | click | trip_details | at_loading | True |  | expense_type | True |  |  |  |
| Invoices, Expenses & Dues | At Loading - Invoices, Expenses & Dues | Clicks 'Pay Now' on 'Freight Invoice' | False |  | v1_pay_now | click | freight_invoice | at_loading | False |  | amt | True |  |  |  |
| Invoices, Expenses & Dues | At Loading - Invoices, Expenses & Dues | Views 'Detention Charge Bottomsheet' | False |  | v1_detention_charge_bottomsheet | view | detention_charge_bottomsheet | at_loading | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | At Loading - Invoices, Expenses & Dues | Clicks 'Close' (X) on 'Detention Charge Bottomsheet' | False |  | v1_close | click | detention_charge_bottomsheet | at_loading | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | At Loading - Invoices, Expenses & Dues | Clicks 'Got it' on 'Detention Charge Bottomsheet' | False |  | v1_got_it | click | detention_charge_bottomsheet | at_loading | True |  | expense_type | True |  |  |  |
| Invoices, Expenses & Dues | At Loading - Invoices, Expenses & Dues | Clicks 'Read Policy' on 'Detention Charge Bottomsheet' | False |  | v1_read_policy | click | detention_charge_bottomsheet | at_loading | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | At Loading - Invoices, Expenses & Dues | Views 'No Cash Bottomsheet' | False |  | v1_nocashbanner | view | no_cash_bottomsheet | at_loading | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | At Loading - Invoices, Expenses & Dues | Clicks 'Agree' on 'No Cash Bottomsheet' | False |  | v1_agree | click | no_cash_bottomsheet | at_loading | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | At Loading - Invoices, Expenses & Dues | Clicks 'Submit' button on 'No Cash Bottomsheet' | False |  | v1_submit | click | no_cash_bottomsheet | at_loading | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | At Loading - Invoices, Expenses & Dues | Views 'Past Trip Balance' | False |  | v1_past_payment | view | past_trip_balance | at_loading | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | At Loading - Invoices, Expenses & Dues | Clicks 'Past View Detail' on 'Past Trip Balance' | False |  | v1_past_view_detail | click | past_trip_balance | at_loading | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | At Loading - Invoices, Expenses & Dues | Clicks 'Submit' button on 'Extra Charge Policy Popup' | False |  | v1_submit_btn | click | extra_charge_policy_popup | at_loading | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | At Loading - Invoices, Expenses & Dues | Views 'Due Payment Amount Widget' | False |  | v1_due_payment_amount_widget | view | due_payment_amount_widget | at_loading | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | In Transit - Invoices, Expenses & Dues | Clicks 'Unlock Discount' | False |  | v1_unlock_discount | click |  | in_transit | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | In Transit - Invoices, Expenses & Dues | Clicks 'View Details' on 'Trip Details' | False |  | v1_view_details_btn | click | trip_details | in_transit | True |  | expense_type | True |  |  |  |
| Invoices, Expenses & Dues | In Transit - Invoices, Expenses & Dues | Views 'No Cash Bottomsheet' | False |  | v1_nocashbanner | view | no_cash_bottomsheet | in_transit | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | In Transit - Invoices, Expenses & Dues | Clicks 'OK' on 'No Cash Bottomsheet' | False |  | v1_ok | click | no_cash_bottomsheet | in_transit | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | In Transit - Invoices, Expenses & Dues | Clicks 'Agree' on 'No Cash Bottomsheet' | False |  | v1_agree | click | no_cash_bottomsheet | in_transit | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | In Transit - Invoices, Expenses & Dues | Clicks 'Submit' button on 'No Cash Bottomsheet' | False |  | v1_submit | click | no_cash_bottomsheet | in_transit | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | In Transit - Invoices, Expenses & Dues | Clicks 'Guideline' on 'No Cash Bottomsheet' | False |  | v1_guideline | click | no_cash_bottomsheet | in_transit | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | In Transit - Invoices, Expenses & Dues | Views 'Detention Charge Bottomsheet' | False |  | v1_detention_charge_bottomsheet | view | detention_charge_bottomsheet | in_transit | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | In Transit - Invoices, Expenses & Dues | Clicks 'Close' (X) on 'Detention Charge Bottomsheet' | False |  | v1_close | click | detention_charge_bottomsheet | in_transit | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | In Transit - Invoices, Expenses & Dues | Clicks 'Read Policy' on 'Detention Charge Bottomsheet' | False |  | v1_read_policy | click | detention_charge_bottomsheet | in_transit | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | In Transit - Invoices, Expenses & Dues | Clicks 'Got it' on 'Detention Charge Bottomsheet' | False |  | v1_got_it | click | detention_charge_bottomsheet | in_transit | True |  | expense_type | True |  |  |  |
| Invoices, Expenses & Dues | In Transit - Invoices, Expenses & Dues | Views 'Due Payment Amount Widget' | False |  | v1_due_payment_amount_widget | view | due_payment_amount_widget | in_transit | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | In Transit - Invoices, Expenses & Dues | Views 'Pending Expense Bottomsheet' | False |  | v1_pending_expense | view | pending_expense_bottomsheet | in_transit | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | In Transit - Invoices, Expenses & Dues | Clicks 'Close' (X) on 'Pending Expense Bottomsheet' | False |  | v1_close | click | pending_expense_bottomsheet | in_transit | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | In Transit - Invoices, Expenses & Dues | Clicks 'Price Breakup' on 'Pending Expense Bottomsheet' | False |  | v1_price_breakup | click | pending_expense_bottomsheet | in_transit | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | In Transit - Invoices, Expenses & Dues | Clicks 'Pay' on 'Pending Expense Bottomsheet' | False |  | v1_pay | click | pending_expense_bottomsheet | in_transit | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | In Transit - Invoices, Expenses & Dues | Clicks 'Pay Now' on 'Freight Invoice' | False |  | v1_pay_now | click | freight_invoice | in_transit | False |  | amt | True |  |  |  |
| Invoices, Expenses & Dues | In Transit - Invoices, Expenses & Dues | Clicks 'Submit' button on 'Extra Charge Policy Popup' | False |  | v1_submit_btn | click | extra_charge_policy_popup | in_transit | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | At Unloading - Invoices, Expenses & Dues | Clicks 'View Details' on 'Trip Details' | False |  | v1_view_details_btn | click | trip_details | at_unloading | True |  | expense_type | True |  |  |  |
| Invoices, Expenses & Dues | At Unloading - Invoices, Expenses & Dues | Views 'No Cash Bottomsheet' | False |  | v1_nocashbanner | view | no_cash_bottomsheet | at_unloading | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | At Unloading - Invoices, Expenses & Dues | Clicks 'OK' on 'No Cash Bottomsheet' | False |  | v1_ok | click | no_cash_bottomsheet | at_unloading | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | At Unloading - Invoices, Expenses & Dues | Clicks 'Agree' on 'No Cash Bottomsheet' | False |  | v1_agree | click | no_cash_bottomsheet | at_unloading | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | At Unloading - Invoices, Expenses & Dues | Clicks 'Submit' button on 'No Cash Bottomsheet' | False |  | v1_submit | click | no_cash_bottomsheet | at_unloading | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | At Unloading - Invoices, Expenses & Dues | Clicks 'Guideline' on 'No Cash Bottomsheet' | False |  | v1_guideline | click | no_cash_bottomsheet | at_unloading | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | At Unloading - Invoices, Expenses & Dues | Views 'Detention Charge Bottomsheet' | False |  | v1_detention_charge_bottomsheet | view | detention_charge_bottomsheet | at_unloading | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | At Unloading - Invoices, Expenses & Dues | Clicks 'Close' (X) on 'Detention Charge Bottomsheet' | False |  | v1_close | click | detention_charge_bottomsheet | at_unloading | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | At Unloading - Invoices, Expenses & Dues | Clicks 'Got it' on 'Detention Charge Bottomsheet' | False |  | v1_got_it | click | detention_charge_bottomsheet | at_unloading | True |  | expense_type | True |  |  |  |
| Invoices, Expenses & Dues | At Unloading - Invoices, Expenses & Dues | Clicks 'Read Policy' on 'Detention Charge Bottomsheet' | False |  | v1_read_policy | click | detention_charge_bottomsheet | at_unloading | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | At Unloading - Invoices, Expenses & Dues | Views 'Due Payment Amount Widget' | False |  | v1_due_payment_amount_widget | view | due_payment_amount_widget | at_unloading | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | At Unloading - Invoices, Expenses & Dues | Views 'Pending Expense Bottomsheet' | False |  | v1_pending_expense | view | pending_expense_bottomsheet | at_unloading | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | At Unloading - Invoices, Expenses & Dues | Clicks 'Close' (X) on 'Pending Expense Bottomsheet' | False |  | v1_close | click | pending_expense_bottomsheet | at_unloading | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | At Unloading - Invoices, Expenses & Dues | Clicks 'Price Breakup' on 'Pending Expense Bottomsheet' | False |  | v1_price_breakup | click | pending_expense_bottomsheet | at_unloading | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | At Unloading - Invoices, Expenses & Dues | Clicks 'Pay Now' on 'Freight Invoice' | False |  | v1_pay_now | click | freight_invoice | at_unloading | False |  | amt | True |  |  |  |
| Invoices, Expenses & Dues | At Unloading - Invoices, Expenses & Dues | Clicks 'Submit' button on 'Extra Charge Policy Popup' | False |  | v1_submit_btn | click | extra_charge_policy_popup | at_unloading | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Trip End - Invoices, Expenses & Dues | Clicks 'Trip End' | False |  | v1_trip_end | click |  | trip_end | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Trip End - Invoices, Expenses & Dues | Clicks 'Unlock Discount' | False |  | v1_unlock_discount | click |  | trip_end | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Trip End - Invoices, Expenses & Dues | Views 'Trip Details' | False |  | v1_halt_info | view | trip_details | trip_end | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Trip End - Invoices, Expenses & Dues | Views 'Trip Details' | False |  | v1_veh_status | view | trip_details | trip_end | True |  | start | True |  |  |  |
| Invoices, Expenses & Dues | Trip End - Invoices, Expenses & Dues | Clicks 'View Details' on 'Trip Details' | False |  | v1_view_details_btn | click | trip_details | trip_end | True |  | expense_type | True |  |  |  |
| Invoices, Expenses & Dues | Trip End - Invoices, Expenses & Dues | Switches trip details tab | False |  | v1_screen_fliter | click | top_nav | trip_end | True |  | segment | True |  |  |  |
| Invoices, Expenses & Dues | Trip End - Invoices, Expenses & Dues | Clicks 'Back' arrow | False |  | v1_back_btn | click | top_nav | trip_end | True |  | timer | True |  |  |  |
| Invoices, Expenses & Dues | Trip End - Invoices, Expenses & Dues | Views 'Detention Charge Bottomsheet' | False |  | v1_detention_charge_bottomsheet | view | detention_charge_bottomsheet | trip_end | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Trip End - Invoices, Expenses & Dues | Clicks 'Close' (X) on 'Detention Charge Bottomsheet' | False |  | v1_close | click | detention_charge_bottomsheet | trip_end | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Trip End - Invoices, Expenses & Dues | Clicks 'Got it' on 'Detention Charge Bottomsheet' | False |  | v1_got_it | click | detention_charge_bottomsheet | trip_end | True |  | expense_type | True |  |  |  |
| Invoices, Expenses & Dues | Trip End - Invoices, Expenses & Dues | Clicks 'Read Policy' on 'Detention Charge Bottomsheet' | False |  | v1_read_policy | click | detention_charge_bottomsheet | trip_end | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Trip End - Invoices, Expenses & Dues | Clicks 'Pay Now' on 'Freight Invoice' | False |  | v1_pay_now | click | freight_invoice | trip_end | False |  | amt | True |  |  |  |
| Invoices, Expenses & Dues | Trip End - Invoices, Expenses & Dues | Views 'Pending Due Screen' | False |  | v1_pending_due | view | pending_due_screen | trip_end | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Trip End - Invoices, Expenses & Dues | Clicks 'Price Breakup' on 'Pending Due Screen' | False |  | v1_price_breakup | click | pending_due_screen | trip_end | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Trip End - Invoices, Expenses & Dues | Clicks 'Pay' on 'Pending Due Screen' | False |  | v1_pay | click | pending_due_screen | trip_end | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Trip End - Invoices, Expenses & Dues | Views 'Due Payment Amount Widget' | False |  | v1_due_payment_amount_widget | view | due_payment_amount_widget | trip_end | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Trip End - Invoices, Expenses & Dues | Views 'Shipment Safety' | False |  | v1_shipment_safety | view | shipment_safety | trip_end | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Trip End - Invoices, Expenses & Dues | Clicks 'Yes' on 'Shipment Safety' | False |  | v1_yes | click | shipment_safety | trip_end | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Trip End - Invoices, Expenses & Dues | Clicks 'Report Issue' on 'Shipment Safety' | False |  | v1_report_issue | click | shipment_safety | trip_end | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Trip End - Invoices, Expenses & Dues | Views 'No Cash Bottomsheet' | False |  | v1_nocashbanner | view | no_cash_bottomsheet | trip_end | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Trip End - Invoices, Expenses & Dues | Clicks 'Agree' on 'No Cash Bottomsheet' | False |  | v1_agree | click | no_cash_bottomsheet | trip_end | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Trip End - Invoices, Expenses & Dues | Clicks 'Submit' button on 'No Cash Bottomsheet' | False |  | v1_submit | click | no_cash_bottomsheet | trip_end | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Trip End - Invoices, Expenses & Dues | Views 'Invoice Locked Bottomsheet' | False |  | v1_invoice_sheet | view | invoice_locked_bottomsheet | trip_end | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Trip End - Invoices, Expenses & Dues | Clicks 'Close' (X) on 'Invoice Locked Bottomsheet' | False |  | v1_close | click | invoice_locked_bottomsheet | trip_end | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Trip End - Invoices, Expenses & Dues | Clicks 'Price Breakup' on 'Invoice Locked Bottomsheet' | False |  | v1_price_breakup | click | invoice_locked_bottomsheet | trip_end | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Trip End - Invoices, Expenses & Dues | Clicks 'Pay' on 'Invoice Locked Bottomsheet' | False |  | v1_pay | click | invoice_locked_bottomsheet | trip_end | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Trip End - Invoices, Expenses & Dues | Views 'Pod Locked Bottomsheet' | False |  | v1_pod_sheet | view | pod_locked_bottomsheet | trip_end | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Trip End - Invoices, Expenses & Dues | Clicks 'Close' (X) on 'Pod Locked Bottomsheet' | False |  | v1_close | click | pod_locked_bottomsheet | trip_end | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Trip End - Invoices, Expenses & Dues | Clicks 'Price Breakup' on 'Pod Locked Bottomsheet' | False |  | v1_price_breakup | click | pod_locked_bottomsheet | trip_end | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Trip End - Invoices, Expenses & Dues | Clicks 'Pay' on 'Pod Locked Bottomsheet' | False |  | v1_pay | click | pod_locked_bottomsheet | trip_end | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Trip End - Invoices, Expenses & Dues | Clicks 'Submit' button on 'Extra Charge Policy Popup' | False |  | v1_submit_btn | click | extra_charge_policy_popup | trip_end | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Extra Charge Policy - Invoices, Expenses & Dues |  | True |  | v1_extra_charge_policy | view |  | extra_charge_policy | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Cancelled Trip - Invoices, Expenses & Dues | Views 'No Cash Bottomsheet' | False |  | v1_nocashbanner | view | no_cash_bottomsheet | cancelled | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Cancelled Trip - Invoices, Expenses & Dues | Clicks 'Agree' on 'No Cash Bottomsheet' | False |  | v1_agree | click | no_cash_bottomsheet | cancelled | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Cancelled Trip - Invoices, Expenses & Dues | Clicks 'Submit' button on 'No Cash Bottomsheet' | False |  | v1_submit | click | no_cash_bottomsheet | cancelled | True |  |  | True |  |  |  |
| Invoices, Expenses & Dues | Cancelled Trip - Invoices, Expenses & Dues | Clicks 'Pay Now' on 'Freight Invoice' | False |  | v1_pay_now | click | freight_invoice | cancelled | False |  | amt | True |  |  |  |
| Rating & Feedback | In Transit - Feedback & Rating | Views 'Pickup Feedback Bottomsheet' | False |  | v1_pickup_feedback | view | pickup_feedback_btmsheet | in_transit | True |  |  | True |  |  |  |
| Rating & Feedback | In Transit - Feedback & Rating | Clicks 'Close' (X) on 'Pickup Feedback Bottomsheet' | False |  | v1_close | click | pickup_feedback_btmsheet | in_transit | True |  |  | True |  |  |  |
| Rating & Feedback | In Transit - Feedback & Rating | Clicks 'Submit' button on 'Pickup Feedback Bottomsheet' | False |  | v1_submit | click | pickup_feedback_btmsheet | in_transit | True |  |  | True |  |  |  |
| Rating & Feedback | In Transit - Feedback & Rating | Clicks 'Okay' on 'Pickup Feedback Bottomsheet' | False |  | v1_okay | click | pickup_feedback_btmsheet | in_transit | True |  |  | True |  |  |  |
| Rating & Feedback | In Transit - Feedback & Rating | Clicks 'No' on 'Pickup Feedback Bottomsheet' | False |  | v1_no | click | pickup_feedback_btmsheet | in_transit | True |  |  | True |  |  |  |
| Rating & Feedback | In Transit - Feedback & Rating | Clicks 'Remark' on 'Pickup Feedback Bottomsheet' | False |  | v1_remark | click | pickup_feedback_btmsheet | in_transit | True |  | remark | True |  |  |  |
| Rating & Feedback | In Transit - Feedback & Rating | Clicks 'Rate Now' on 'Pickup Feedback' | False |  | v1_rate_now | click | pickup_feedback | in_transit | True |  |  | True |  |  |  |
| Rating & Feedback | Trip End - Feedback & Rating | Views 'Rating Bottomsheet' | False |  | v1_rating | view | rating_bottom_sheet | trip_end | True |  | rate | True |  |  |  |
| Rating & Feedback | Trip End - Feedback & Rating | Clicks 'Submit' button on 'Rating Bottomsheet' | False |  | v1_submit_btn | click | rating_bottom_sheet | trip_end | True |  | rate | True |  |  |  |
| Rating & Feedback | Trip End - Feedback & Rating | Selects star rating on 'Rating Bottomsheet' | False |  | v1_rating | click | rating_bottom_sheet | trip_end | True |  | rate | True |  |  |  |
| Rating & Feedback | Trip End - Feedback & Rating | Selects a reason on 'Rating Bottomsheet' | False |  | v1_reason_selected | click | rating_bottom_sheet | trip_end | True |  | rate | True |  |  |  |
| Rating & Feedback | Trip End - Feedback & Rating | Deselects a reason on 'Rating Bottomsheet' | False |  | v1_reason_deslected | click | rating_bottom_sheet | trip_end | True |  | rate | True |  |  |  |
| Rating & Feedback | Trip Rating | Views 'Rating Bottomsheet' | True |  | v1_rating_btm_sheet | view | rating_bottom_sheet | rating_bottom_sheet | True |  | source | True |  |  |  |
| Rating & Feedback | Trip Rating | Clicks 'Submit' button on 'Rating Bottomsheet' | False |  | v1_submit | click | rating_bottom_sheet | rating_bottom_sheet | True |  | source | True |  |  |  |
| Rating & Feedback | Trip Rating | Clicks 'Submit Trip Feedback' on 'Rating Bottomsheet' | True | Trip feedback submitted | v1_submit_trip_feedback | click | rating_bottom_sheet | rating_bottom_sheet | True |  | source | True |  |  |  |
| Rating & Feedback | Trip Rating | Clicks 'Skip' on 'Rating Bottomsheet' | False |  | v1_skip_rating | click | rating_bottom_sheet | rating_bottom_sheet | True |  | source | True |  |  |  |
| Rating & Feedback | Playstore Rating | Views 'Rating Popup' | False |  | v1_rating_popup | view | rating_popup | playstore_rating | False |  |  | True |  |  |  |
| Cancelled Trip | Cancelled Trip | Switches trip details tab | False |  | v1_screen_fliter | click | top_nav | cancelled | True |  | segment | True |  |  |  |
| Cancelled Trip | Cancelled Trip | Clicks 'Back' arrow | False |  | v1_back_btn | click | top_nav | cancelled | True |  | timer | True |  |  |  |
| Cancelled Trip | Cancelled Trip | Clicks 'Complete Kyc' | False |  | v1_complete_kyc | click | bottom_nav | cancelled | True |  |  | True |  |  |  |
| Cancelled Trip | Cancelled Trip | Views 'Trip Details' | False |  | v1_halt_info | view | trip_details | cancelled | True |  |  | True |  |  |  |
| Cancelled Trip | Cancelled Trip | Views 'Trip Details' | False |  | v1_veh_status | view | trip_details | cancelled | True |  | start | True |  |  |  |
| Cancelled Trip | Cancelled Trip - Help / Ticket | Clicks 'Create Ticket' on 'Help Support' | False |  | v1_create_ticket | click | help_support | cancelled | True |  |  | True |  |  |  |
| Cancelled Trip | Cancelled Trip - Help / Ticket | Clicks 'Need Help' on 'Help Widget' | False |  | v1_need_help | click | help_widget | cancelled | True |  |  | True |  |  |  |
| Cancelled Trip | Cancelled Trip - Invoices, Expenses & Dues | Views 'No Cash Bottomsheet' | False |  | v1_nocashbanner | view | no_cash_bottomsheet | cancelled | True |  |  | True |  |  |  |
| Cancelled Trip | Cancelled Trip - Invoices, Expenses & Dues | Clicks 'Agree' on 'No Cash Bottomsheet' | False |  | v1_agree | click | no_cash_bottomsheet | cancelled | True |  |  | True |  |  |  |
| Cancelled Trip | Cancelled Trip - Invoices, Expenses & Dues | Clicks 'Submit' button on 'No Cash Bottomsheet' | False |  | v1_submit | click | no_cash_bottomsheet | cancelled | True |  |  | True |  |  |  |
| Cancelled Trip | Cancelled Trip - Cancellation | Views 'Cancel Bottomsheet' | False |  | v1_cancel_bottom_sheet | view | cancel_bottom_sheet | cancelled | True |  |  | True |  |  |  |
| Cancelled Trip | Cancelled Trip - Cancellation | Selects a reason on 'Cancel Bottomsheet' | False |  | v1_reason_selected | click | cancel_bottom_sheet | cancelled | True |  |  | True |  |  |  |
| Cancelled Trip | Cancelled Trip - Cancellation | Clicks 'Submit' button on 'Cancel Bottomsheet' | False |  | v1_submit_btn | click | cancel_bottom_sheet | cancelled | True |  | reason | True |  |  |  |
| Cancelled Trip | Cancelled Trip - Cancellation | Clicks 'Modify' button on 'Cancel Bottomsheet' | False |  | v1_modify_btn | click | cancel_bottom_sheet | cancelled | True |  | reason | True |  |  |  |
| Cancelled Trip | Cancelled Trip - Help / Ticket | Opens an existing ticket on 'Tickets' | False |  | v1_open_ticket | click | tickets | cancelled | True |  | status | True |  |  |  |
| Cancelled Trip | Cancelled Trip | Clicks 'Share Location' on 'Map View' | False |  | v1_share_loc | click | map_view | cancelled | True |  |  | True |  |  |  |
| Cancelled Trip | Cancelled Trip | Clicks 'Recenter' map on 'Map View' | False |  | v1_recenter | click | map_view | cancelled | True |  |  | True |  |  |  |
| Cancelled Trip | Cancelled Trip - Invoices, Expenses & Dues | Clicks 'Pay Now' on 'Freight Invoice' | False |  | v1_pay_now | click | freight_invoice | cancelled | False |  | amt | True |  |  |  |
| My Trips | Home Page | Clicks 'My Trips' tab | False |  | v1_my_trips | click | bottom_nav | home_page | False |  |  | True |  |  |  |
| My Trips | App Shortcut | Clicks 'App Shortcut' on 'My Trips' | False |  | v1_app_shortcut | click | my_trips | app_shortcut | False |  | user_code | True |  |  |  |
| My Trips | Home Page - Repeat Booking | Views 'Misc Widget' | False |  | v1_repeat_widget | view | misc_widget | home_page | False |  |  | True |  |  |  |
| My Trips | Home Page - Repeat Booking | Clicks 'View All' on 'Repeat Demand Cards' | False |  | v1_view_all | click | repeat_demand_cards | home_page | False |  | demand_count | True |  |  |  |
| My Trips | Home Page - Repeat Booking | Clicks 'Re Book' on 'Repeat Demand Cards' | False |  | v1_re_book | click | repeat_demand_cards | home_page | False |  | demand_count | True |  |  |  |
| My Trips | My Trips | Clicks 'Demand Detail' on 'Demand Cards' | False |  | v1_demand_detail | click | demand_cards | my_trips | True |  | text | True |  |  |  |
| My Trips | Repeat Booking |  | True |  | v1_repeat_demand | view |  | repeat_demand | False |  |  | True |  |  |  |
| My Trips | Repeat Booking | Clicks 'Select Demand' on 'Demand Cards' | False |  | v1_select_demand | click | demand_cards | repeat_demand | False |  | demand_idx | True |  |  |  |
| Payments | Home Page | Clicks 'Payment' tab | False |  | v1_payment | click | bottom_nav | home_page | False |  |  | True |  |  |  |
| Payments | App Shortcut | Clicks 'App Shortcut' on 'Payment Home' | False |  | v1_app_shortcut | click | payment_home | app_shortcut | False |  | user_code | True |  |  |  |
| Payments | Home Page - Payments / Dues |  | False |  | v1_payment_banner_view | view |  | home_page | False |  |  | True |  |  |  |
| Payments | Home Page - Payments / Dues | Views 'Payment Plan Banner' | False |  | v1_payment_plan_banner | view | payment_plan_banner | home_page | False |  |  | True |  |  |  |
| Payments | Home Page - Payments / Dues | Clicks 'Close' (X) on 'Payment Plan Banner' | False |  | v1_close_btn | click | payment_plan_banner | home_page | False |  |  | True |  |  |  |
| Payments | Home Page - Payments / Dues | Views 'Delay Fee Info' | False |  | v1_fee_info | view | delay_fee_info | home_page | False |  |  | True |  |  |  |
| Payments | Home Page - Payments / Dues | Clicks 'Clear Due' on 'Delay Fee Info' | False |  | v1_clear_due | click | delay_fee_info | home_page | False |  |  | True |  |  |  |
| Payments | Home Page - Payments / Dues | Clicks 'Fee Icon' on 'Delay Fee Info' | False |  | v1_fee_icon | click | delay_fee_info | home_page | False |  |  | True |  |  |  |
| Payments | Home Page - Payments / Dues | Views 'Tds Banner' | False |  | v1_tds_banner | view | tds_banner | home_page | False |  |  | True |  |  |  |
| Payments | Home Page - Payments / Dues | Clicks 'Understand' on 'Tds Banner' | False |  | v1_understand | click | tds_banner | home_page | False |  |  | True |  |  |  |
| Payments | Home Page - Payments / Dues | Clicks 'Auto Settle Post Review' on 'Auto Settle Bottomsheet' | False |  | v1_auto_settle_post_review | click | auto_settle_btmsheet | home_page | False |  |  | True |  |  |  |
| Payments | Payments Home |  | False |  | v1_screen_view | view |  | payment_page | False |  |  | True |  |  |  |
| Payments | Payments Home |  | False |  | v1_fraud_banner | view |  | payment_page | False |  |  | True |  |  |  |
| Payments | Payments Home |  | True |  | v1_payment_page | view |  | payment_page | False |  | due_amt | True |  |  |  |
| Payments | Payments Home |  | False |  | v1_avail_credit_widget | view |  | payment_page | False |  |  | True |  |  |  |
| Payments | Payments Home |  | False |  | v1_confirm_detail_warning | view |  | payment_page | False |  |  | True |  |  |  |
| Payments | Payments Home |  | False |  | v1_plan_view | view |  | payment_page | False |  | status | True |  |  |  |
| Payments | Payments Home | Clicks 'Payment Spoke' | False |  | v1_payment_spoke | click |  | payment_page | False |  |  | True |  |  |  |
| Payments | Payments Home | Views 'Payment Details' | False |  | v1_credit_limit | view | payment_details | payment_page | False |  | credit_amt | True |  |  |  |
| Payments | Payments Home | Views 'Payment Details' | False |  | v1_settle_tds | view | payment_details | payment_page | False |  | amt | True |  |  |  |
| Payments | Payments Home | Clicks 'Pay Now' button on 'Payment Details' | True | Payment initiated | v1_pay_now_btn | click | payment_details | payment_page | False |  | due_amt | True |  |  |  |
| Payments | Payments Home | Clicks 'Bank Detail' on 'Payment Details' | False |  | v1_bank_detail | click | payment_details | payment_page | False |  |  | True |  |  |  |
| Payments | Payments Home | Clicks 'View' button on 'Payment Details' | False |  | v1_view_btn | click | payment_details | payment_page | False |  |  | True |  |  |  |
| Payments | Payments Home | Clicks 'Unbilled Amt' button on 'Payment Details' | False |  | v1_unbilled_amt_btn | click | payment_details | payment_page | False |  | unbilled_amt | True |  |  |  |
| Payments | Payments Home | Clicks 'Plan Change' on 'Payment Details' | False |  | v1_plan_change | click | payment_details | payment_page | False |  |  | True |  |  |  |
| Payments | Payments Home | Clicks 'Close' (X) on 'No Cash Bottomsheet' | False |  | v1_close | click | no_cash_bottomsheet | payment_page | False |  |  | True |  |  |  |
| Payments | Payments Home | Views 'Pmnt Plan Widget' | False |  | v1_pmnt_plan_widget | view | pmnt_plan_widget | payment_page | False |  | pmnt_plan | True |  |  |  |
| Payments | Payments Home | Clicks 'Increase Info' on 'Pmnt Plan Widget' | False |  | v1_increase_info | click | pmnt_plan_widget | payment_page | False |  |  | True |  |  |  |
| Payments | Payments Home | Clicks 'Gst Verify' on 'Payment Plan Listing' | False |  | v1_gst_verify | click | payment_plan_listing | payment_page | False |  |  | True |  |  |  |
| Payments | Payments Home | Views 'Tds Banner' | False |  | v1_tds_banner | view | tds_banner | payment_page | False |  |  | True |  |  |  |
| Payments | Payments Home | Clicks 'Understand' on 'Tds Banner' | False |  | v1_understand | click | tds_banner | payment_page | False |  |  | True |  |  |  |
| Payments | Payments Home | Clicks 'Learnwhy' on 'Tds Details' | False |  | v1_learnwhy | click | tds_details | payment_page | False |  |  | True |  |  |  |
| Payments | Due Trips |  | True |  | v1_due_trips_listing | view |  | due_trips_listing | False |  |  | True |  |  |  |
| Payments | Due Trips |  | False |  | v1_pmnt_link_bottom_sheet | view |  | due_trips_listing | False |  |  | True |  |  |  |
| Payments | Due Trips | Clicks 'Pay Now' button | True | Payment initiated | v1_pay_now_btn | click | bottom_nav | due_trips_listing | False |  | trip_count | True |  |  |  |
| Payments | Due Trips | Clicks 'Tds Click' | False |  | v1_tds_click | click | bottom_nav | due_trips_listing | False |  | tds | False |  |  |  |
| Payments | Due Trips | Clicks 'Breakup View' on 'Trip Details' | False |  | v1_breakup_view | click | trip_details | due_trips_listing | False |  |  | True |  |  |  |
| Payments | Due Trips | Clicks 'Share Pmnt Link' on 'Trip Details' | False |  | v1_share_pmnt_link | click | trip_details | due_trips_listing | False |  | amt | True |  |  |  |
| Payments | Due Trips | Clicks 'Bank Detail' on 'Payment Details' | False |  | v1_bank_detail | click | payment_details | due_trips_listing | False |  |  | True |  |  |  |
| Payments | Due Trips | Clicks 'Share Now' button on 'Pmnt Link Bottomsheet' | False |  | v1_share_now_btn | click | pmnt_link_bottom_sheet | due_trips_listing | False |  | mode | True |  |  |  |
| Payments | Due Trips | Clicks 'Share Method' on 'Pmnt Link Bottomsheet' | False |  | v1_share_method | click | pmnt_link_bottom_sheet | due_trips_listing | False |  | mode | True |  |  |  |
| Payments | Due Trips | Clicks 'Enter Mail' on 'Pmnt Link Bottomsheet' | False |  | v1_enter_mail | click | pmnt_link_bottom_sheet | due_trips_listing | False |  |  | True |  |  |  |
| Payments | Payment Plans | Clicks 'Pmnt Mode Select' on 'Payment Plan Listing' | False |  | v1_pmnt_mode_select | click | payment_plan_listing | payment_plans | False |  | mode | True |  |  |  |
| Payments | Plan Details | Views 'Payment Plan Listing Details' | False |  | v1_plan_details | view | payment_plan_listing_details | plan_details | False |  | mode | True |  |  |  |
| Payments | Plan Details | Views 'Payment Plan Listing Details' | False |  | v1_instant_act_banner | view | payment_plan_listing_details | plan_details | False |  |  | True |  |  |  |
| Payments | Plan Details | Clicks 'Back' arrow on 'Payment Plan Listing Details' | False |  | v1_back_btn | click | payment_plan_listing_details | plan_details | False |  | mode | True |  |  |  |
| Payments | Plan Details | Clicks 'Cibil' button on 'Payment Plan Listing Details' | False |  | v1_cibil_btn | click | payment_plan_listing_details | plan_details | False |  | mode | True |  |  |  |
| Payments | Plan Details | Clicks 'Faq Select' on 'Payment Plan Listing Details' | False |  | v1_faq_select | click | payment_plan_listing_details | plan_details | False |  | mode | True |  |  |  |
| Payments | Plan Details | Views 'Activation Mode Bottomsheet' | False |  | v1_activation_mode_bottomsheet | view | activation_mode_bottomsheet | plan_details | False |  |  | True |  |  |  |
| Payments | Plan Details | Clicks 'Mode Select' on 'Activation Mode Bottomsheet' | False |  | v1_mode_select | click | activation_mode_bottomsheet | plan_details | False |  | amt | True |  |  |  |
| Payments | Plan Details | Clicks 'Continue' button on 'Activation Mode Bottomsheet' | False |  | v1_continue_btn | click | activation_mode_bottomsheet | plan_details | False |  | mode | True |  |  |  |
| Payments | Plan Details | Clicks 'Cibil' button on 'Activation Mode Bottomsheet' | False |  | v1_cibil_btn | click | activation_mode_bottomsheet | plan_details | False |  | mode | True |  |  |  |
| Payments | Plan Comparison | Clicks 'Grace Days' on 'Grace Detail' | False |  | v1_grace_days | click | grace_detail | payment_comparison | False |  | grace | True |  |  |  |
| Payments | Plan Comparison | Clicks 'Cycle Billing' on 'Cycle Detail' | False |  | v1_cycle_billing | click | cycle_detail | payment_comparison | False |  | cycle | True |  |  |  |
| Payments | Security Cheque Upload |  | False |  | v1_upload_option | view |  | security_cheque_upload | False |  |  | True |  |  |  |
| Payments | Security Cheque Upload | Clicks 'Back' arrow | False |  | v1_back_btn | click | top_nav | security_cheque_upload | False |  |  | True |  |  |  |
| Payments | Security Cheque Upload | Clicks 'Upload Cheque' button on 'Cheque Details' | False |  | v1_upload_cheque_btn | click | cheque_details | security_cheque_upload | False |  |  | True |  |  |  |
| Payments | Security Cheque Upload | Clicks 'Gallery' button on 'Upload Option' | False |  | v1_gallery_btn | click | upload_option | security_cheque_upload | False |  |  | True |  |  |  |
| Payments | Cheque Preview |  | False |  | v1_cheque_view | view |  | cheque_view | False |  |  | True |  |  |  |
| Payments | PAN Upload | Clicks 'Upload' on 'Upload Doc' | False |  | v1_upload | click | upload_doc | pan_upload | False |  |  | True |  |  |  |
| Payments | PAN Upload | Clicks 'Next' button on 'Upload Doc' | False |  | v1_next | click | upload_doc | pan_upload | False |  |  | True |  |  |  |
| Payments | PAN Upload | Clicks 'Again' on 'Failed Upload Doc' | False |  | v1_again | click | failed_upload_doc | pan_upload | False |  |  | True |  |  |  |
| Payments | GST Upload | Clicks 'Upload' on 'Upload Doc' | False |  | v1_upload | click | upload_doc | gst_upload | False |  |  | True |  |  |  |
| Payments | GST Upload | Clicks 'Next' button on 'Upload Doc' | False |  | v1_next | click | upload_doc | gst_upload | False |  |  | True |  |  |  |
| Payments | GST Upload | Clicks 'Again' on 'Failed Upload Doc' | False |  | v1_again | click | failed_upload_doc | gst_upload | False |  |  | True |  |  |  |
| Payments | Cheque Upload | Clicks 'Upload' on 'Upload Doc' | False |  | v1_upload | click | upload_doc | cheque_upload | False |  |  | True |  |  |  |
| Payments | Cancelled Cheque Upload | Clicks 'Next' button on 'Upload Doc' | False |  | v1_next | click | upload_doc | cancelled_cheque | False |  |  | True |  |  |  |
| Payments | Cancelled Cheque Upload | Clicks 'Again' on 'Failed Upload Doc' | False |  | v1_again | click | failed_upload_doc | cancelled_cheque | False |  |  | True |  |  |  |
| Payments | Plan Activation - OTP | Clicks 'Verify' on 'Enter Otp' | False |  | v1_verify | click | enter_otp | enter_otp | False |  |  | True |  |  |  |
| Payments | Plan Activation Initiated |  | False |  | v1_plan_details | view |  | activation_initiated_page | False |  | mode | True |  |  |  |
| Payments | Plan Activation Initiated |  | False |  | v1_activation_initiated_page | view |  | activation_initiated_page | False |  |  | True |  |  |  |
| Payments | Plan Activation Initiated | Clicks 'Payment Spoke' | False |  | v1_payment_spoke | click |  | activation_initiated_page | False |  |  | True |  |  |  |
| Payments | Plan Activation Initiated | Clicks 'Confirm' button on 'Payment Plan Listing Details' | False |  | v1_confirm_btn | click | payment_plan_listing_details | activation_initiated_page | False |  | mode | True |  |  |  |
| Payments | Payment History | Clicks 'Get Statement' | False |  | v1_get_statement | click | top_nav | payment_history | False |  |  | True |  |  |  |
| Payments | Statement | Clicks 'Share Doc' | False |  | v1_share_doc | click | bottom_nav | get_statement | False |  | doc_type | True |  |  |  |
| Payments | Payment SPOC | Clicks 'Back' arrow on 'Payment Spoken Page' | False |  | v1_back | click | payment_spoken_page | payment_spoken | False |  |  | True |  |  |  |
| Payments | Payment SPOC | Clicks 'Submit' button on 'Payment Spoken Page' | False |  | v1_submit | click | payment_spoken_page | payment_spoken | False |  |  | True |  |  |  |
| Payments | Payment SPOC | Clicks 'Add' on 'Payment Spoken Page' | False |  | v1_add | click | payment_spoken_page | payment_spoken | False |  |  | True |  |  |  |
| Payments | Payment SPOC | Clicks 'Delete' on 'Payment Spoken Page' | False |  | v1_delete | click | payment_spoken_page | payment_spoken | False |  |  | True |  |  |  |
| Payments | Payment SPOC | Clicks 'Skip' on 'Payment Spoken Page' | False |  | v1_skip | click | payment_spoken_page | payment_spoken | False |  |  | True |  |  |  |
| VIP Pass | Home Page - VIP Pass / Coupon |  | False |  | v1_explore_plans | view |  | home_page | False |  |  | True |  |  |  |
| VIP Pass | Home Page - VIP Pass / Coupon |  | False |  | v1_view_active_pass_details | view |  | home_page | False |  | type | True |  |  |  |
| VIP Pass | Home Page - VIP Pass / Coupon |  | False |  | v1_renew_pass | view |  | home_page | False |  |  | True |  |  |  |
| VIP Pass | Home Page - VIP Pass / Coupon | Clicks 'Explore Plans' | False |  | v1_explore_plans | click |  | home_page | False |  |  | True |  |  |  |
| VIP Pass | Home Page - VIP Pass / Coupon | Clicks 'View Active Pass Details' | False |  | v1_view_active_pass_details | click |  | home_page | False |  |  | True |  |  |  |
| VIP Pass | Home Page - VIP Pass / Coupon | Clicks 'Renew Pass' | False |  | v1_renew_pass | click |  | home_page | False |  |  | True |  |  |  |
| VIP Pass | Vehicle Found - Confirm Details - VIP Pass / Coupon |  | False |  | v1_explore_plans | view |  | scheduled_preview | False |  | action_type | True |  |  |  |
| VIP Pass | Vehicle Found - Confirm Details - VIP Pass / Coupon |  | False |  | v1_coupon | view |  | scheduled_preview | True |  |  | True |  |  |  |
| VIP Pass | Vehicle Found - Confirm Details - VIP Pass / Coupon |  | False |  | v1_promo_applied | view |  | scheduled_preview | False |  | disc_type | True |  |  |  |
| VIP Pass | Vehicle Found - Confirm Details - VIP Pass / Coupon |  | False |  | v1_renew_pass | view |  | scheduled_preview | False |  | action_type | True |  |  |  |
| VIP Pass | Vehicle Found - Confirm Details - VIP Pass / Coupon | Clicks 'Add Pass' | False |  | v1_add_pass | click |  | scheduled_preview | True |  |  | True |  |  |  |
| VIP Pass | Vehicle Found - Confirm Details - VIP Pass / Coupon | Clicks 'Explore Plans' | False |  | v1_explore_plans | click |  | scheduled_preview | False |  |  | True |  |  |  |
| VIP Pass | Vehicle Found - Confirm Details - VIP Pass / Coupon | Clicks 'Save With Pass' | False |  | v1_save_with_pass | click |  | scheduled_preview | True |  |  | True |  |  |  |
| VIP Pass | Vehicle Found - Confirm Details - VIP Pass / Coupon | Clicks 'Coupon Action' | False |  | v1_coupon_action | click |  | scheduled_preview | True |  | enum_type | True |  |  |  |
| VIP Pass | Vehicle Found - Confirm Details - VIP Pass / Coupon | Clicks 'Pass Added' | False |  | v1_pass_added | click |  | scheduled_preview | True |  |  | True |  |  |  |
| VIP Pass | Vehicle Found - Confirm Details - VIP Pass / Coupon | Clicks 'Renew Pass' | False |  | v1_renew_pass | click |  | scheduled_preview | False |  |  | True |  |  |  |
| VIP Pass | Vehicle Found - Confirm Details - VIP Pass / Coupon | Views 'Unlock Pass Bottomsheet' | False |  | v1_unlock_pass | view | unlock_pass_btmsheet | scheduled_preview | True |  | type | True |  |  |  |
| VIP Pass | Vehicle Found - Confirm Details - VIP Pass / Coupon | Clicks 'Conf Pass' on 'Unlock Pass Bottomsheet' | False |  | v1_conf_pass | click | unlock_pass_btmsheet | scheduled_preview | True |  |  | True |  |  |  |
| VIP Pass | Vehicle Found - Confirm Details - VIP Pass / Coupon | Clicks 'Explore Plans' on 'Unlock Pass Bottomsheet' | False |  | v1_explore_plans | click | unlock_pass_btmsheet | scheduled_preview | True |  |  | True |  |  |  |
| VIP Pass | Trip Scheduled - VIP Pass / Coupon |  | False |  | v1_explore_plans | view |  | scheduled | False |  | action_type | True |  |  |  |
| VIP Pass | Trip Scheduled - VIP Pass / Coupon |  | False |  | v1_coupon | view |  | scheduled | True |  |  | True |  |  |  |
| VIP Pass | Trip Scheduled - VIP Pass / Coupon |  | False |  | v1_promo_applied | view |  | scheduled | False |  | disc_type | True |  |  |  |
| VIP Pass | Trip Scheduled - VIP Pass / Coupon |  | False |  | v1_renew_pass | view |  | scheduled | False |  | action_type | True |  |  |  |
| VIP Pass | Trip Scheduled - VIP Pass / Coupon | Clicks 'Explore Plans' | False |  | v1_explore_plans | click |  | scheduled | False |  |  | True |  |  |  |
| VIP Pass | Trip Scheduled - VIP Pass / Coupon | Clicks 'Add Pass' | False |  | v1_add_pass | click |  | scheduled | True |  |  | True |  |  |  |
| VIP Pass | Trip Scheduled - VIP Pass / Coupon | Clicks 'Save With Pass' | False |  | v1_save_with_pass | click |  | scheduled | True |  |  | True |  |  |  |
| VIP Pass | Trip Scheduled - VIP Pass / Coupon | Clicks 'Coupon Action' | False |  | v1_coupon_action | click |  | scheduled | True |  | enum_type | True |  |  |  |
| VIP Pass | Trip Scheduled - VIP Pass / Coupon | Clicks 'Pass Added' | False |  | v1_pass_added | click |  | scheduled | True |  |  | True |  |  |  |
| VIP Pass | Trip Scheduled - VIP Pass / Coupon | Clicks 'Renew Pass' | False |  | v1_renew_pass | click |  | scheduled | False |  |  | True |  |  |  |
| VIP Pass | Trip Scheduled - VIP Pass / Coupon | Views 'Unlock Pass Bottomsheet' | False |  | v1_unlock_pass | view | unlock_pass_btmsheet | scheduled | True |  | type | True |  |  |  |
| VIP Pass | Trip Scheduled - VIP Pass / Coupon | Clicks 'Conf Pass' on 'Unlock Pass Bottomsheet' | False |  | v1_conf_pass | click | unlock_pass_btmsheet | scheduled | True |  |  | True |  |  |  |
| VIP Pass | Trip Scheduled - VIP Pass / Coupon | Clicks 'Explore Plans' on 'Unlock Pass Bottomsheet' | False |  | v1_explore_plans | click | unlock_pass_btmsheet | scheduled | True |  |  | True |  |  |  |
| VIP Pass | Going To Load - VIP Pass / Coupon |  | False |  | v1_explore_plans | view |  | going_to_load | False |  | action_type | True |  |  |  |
| VIP Pass | Going To Load - VIP Pass / Coupon |  | False |  | v1_coupon | view |  | going_to_load | True |  |  | True |  |  |  |
| VIP Pass | Going To Load - VIP Pass / Coupon |  | False |  | v1_promo_applied | view |  | going_to_load | False |  | disc_type | True |  |  |  |
| VIP Pass | Going To Load - VIP Pass / Coupon |  | False |  | v1_renew_pass | view |  | going_to_load | False |  | action_type | True |  |  |  |
| VIP Pass | Going To Load - VIP Pass / Coupon | Clicks 'Coupon Action' | False |  | v1_coupon_action | click |  | going_to_load | True |  | enum_type | True |  |  |  |
| VIP Pass | Going To Load - VIP Pass / Coupon | Clicks 'Explore Plans' | False |  | v1_explore_plans | click |  | going_to_load | False |  |  | True |  |  |  |
| VIP Pass | Going To Load - VIP Pass / Coupon | Clicks 'Save With Pass' | False |  | v1_save_with_pass | click |  | going_to_load | True |  |  | True |  |  |  |
| VIP Pass | Going To Load - VIP Pass / Coupon | Clicks 'Add Pass' | False |  | v1_add_pass | click |  | going_to_load | True |  |  | True |  |  |  |
| VIP Pass | Going To Load - VIP Pass / Coupon | Clicks 'Pass Added' | False |  | v1_pass_added | click |  | going_to_load | True |  |  | True |  |  |  |
| VIP Pass | Going To Load - VIP Pass / Coupon | Clicks 'Renew Pass' | False |  | v1_renew_pass | click |  | going_to_load | False |  |  | True |  |  |  |
| VIP Pass | Going To Load - VIP Pass / Coupon | Views 'Unlock Pass Bottomsheet' | False |  | v1_unlock_pass | view | unlock_pass_btmsheet | going_to_load | True |  | type | True |  |  |  |
| VIP Pass | Going To Load - VIP Pass / Coupon | Clicks 'Conf Pass' on 'Unlock Pass Bottomsheet' | False |  | v1_conf_pass | click | unlock_pass_btmsheet | going_to_load | True |  |  | True |  |  |  |
| VIP Pass | Going To Load - VIP Pass / Coupon | Clicks 'Explore Plans' on 'Unlock Pass Bottomsheet' | False |  | v1_explore_plans | click | unlock_pass_btmsheet | going_to_load | True |  |  | True |  |  |  |
| VIP Pass | At Loading - VIP Pass / Coupon |  | False |  | v1_explore_plans | view |  | at_loading | False |  | action_type | True |  |  |  |
| VIP Pass | At Loading - VIP Pass / Coupon |  | False |  | v1_coupon | view |  | at_loading | True |  |  | True |  |  |  |
| VIP Pass | At Loading - VIP Pass / Coupon |  | False |  | v1_renew_pass | view |  | at_loading | False |  | action_type | True |  |  |  |
| VIP Pass | At Loading - VIP Pass / Coupon |  | False |  | v1_promo_applied | view |  | at_loading | False |  | disc_type | True |  |  |  |
| VIP Pass | At Loading - VIP Pass / Coupon | Clicks 'Coupon Action' | False |  | v1_coupon_action | click |  | at_loading | True |  | enum_type | True |  |  |  |
| VIP Pass | At Loading - VIP Pass / Coupon | Clicks 'Save With Pass' | False |  | v1_save_with_pass | click |  | at_loading | True |  |  | True |  |  |  |
| VIP Pass | At Loading - VIP Pass / Coupon | Clicks 'Explore Plans' | False |  | v1_explore_plans | click |  | at_loading | False |  |  | True |  |  |  |
| VIP Pass | At Loading - VIP Pass / Coupon | Clicks 'Add Pass' | False |  | v1_add_pass | click |  | at_loading | True |  |  | True |  |  |  |
| VIP Pass | At Loading - VIP Pass / Coupon | Clicks 'Pass Added' | False |  | v1_pass_added | click |  | at_loading | True |  |  | True |  |  |  |
| VIP Pass | At Loading - VIP Pass / Coupon | Clicks 'Renew Pass' | False |  | v1_renew_pass | click |  | at_loading | False |  |  | True |  |  |  |
| VIP Pass | At Loading - VIP Pass / Coupon | Views 'Unlock Pass Bottomsheet' | False |  | v1_unlock_pass | view | unlock_pass_btmsheet | at_loading | True |  | type | True |  |  |  |
| VIP Pass | At Loading - VIP Pass / Coupon | Clicks 'Conf Pass' on 'Unlock Pass Bottomsheet' | False |  | v1_conf_pass | click | unlock_pass_btmsheet | at_loading | True |  |  | True |  |  |  |
| VIP Pass | At Loading - VIP Pass / Coupon | Clicks 'Explore Plans' on 'Unlock Pass Bottomsheet' | False |  | v1_explore_plans | click | unlock_pass_btmsheet | at_loading | True |  |  | True |  |  |  |
| VIP Pass | In Transit - VIP Pass / Coupon |  | False |  | v1_promo_applied | view |  | in_transit | False |  | disc_type | True |  |  |  |
| VIP Pass | In Transit - VIP Pass / Coupon | Clicks 'Save With Pass' | False |  | v1_save_with_pass | click |  | in_transit | True |  |  | True |  |  |  |
| VIP Pass | In Transit - VIP Pass / Coupon | Views 'Unlock Pass Bottomsheet' | False |  | v1_unlock_pass | view | unlock_pass_btmsheet | in_transit | True |  | type | True |  |  |  |
| VIP Pass | In Transit - VIP Pass / Coupon | Clicks 'Explore Plans' on 'Unlock Pass Bottomsheet' | False |  | v1_explore_plans | click | unlock_pass_btmsheet | in_transit | True |  |  | True |  |  |  |
| VIP Pass | In Transit - VIP Pass / Coupon | Clicks 'Conf Pass' on 'Unlock Pass Bottomsheet' | False |  | v1_conf_pass | click | unlock_pass_btmsheet | in_transit | True |  |  | True |  |  |  |
| VIP Pass | At Unloading - VIP Pass / Coupon |  | False |  | v1_promo_applied | view |  | at_unloading | False |  | disc_type | True |  |  |  |
| VIP Pass | At Unloading - VIP Pass / Coupon | Clicks 'Save With Pass' | False |  | v1_save_with_pass | click |  | at_unloading | True |  |  | True |  |  |  |
| VIP Pass | At Unloading - VIP Pass / Coupon | Views 'Unlock Pass Bottomsheet' | False |  | v1_unlock_pass | view | unlock_pass_btmsheet | at_unloading | True |  | type | True |  |  |  |
| VIP Pass | At Unloading - VIP Pass / Coupon | Clicks 'Conf Pass' on 'Unlock Pass Bottomsheet' | False |  | v1_conf_pass | click | unlock_pass_btmsheet | at_unloading | True |  |  | True |  |  |  |
| VIP Pass | At Unloading - VIP Pass / Coupon | Clicks 'Explore Plans' on 'Unlock Pass Bottomsheet' | False |  | v1_explore_plans | click | unlock_pass_btmsheet | at_unloading | True |  |  | True |  |  |  |
| VIP Pass | Trip End - VIP Pass / Coupon |  | False |  | v1_promo_applied | view |  | trip_end | False |  | disc_type | True |  |  |  |
| VIP Pass | Trip End - VIP Pass / Coupon | Clicks 'Save With Pass' | False |  | v1_save_with_pass | click |  | trip_end | True |  |  | True |  |  |  |
| VIP Pass | Trip End - VIP Pass / Coupon | Views 'Unlock Pass Bottomsheet' | False |  | v1_unlock_pass | view | unlock_pass_btmsheet | trip_end | True |  | type | True |  |  |  |
| VIP Pass | Trip End - VIP Pass / Coupon | Clicks 'Conf Pass' on 'Unlock Pass Bottomsheet' | False |  | v1_conf_pass | click | unlock_pass_btmsheet | trip_end | True |  |  | True |  |  |  |
| VIP Pass | VIP Pass Landing |  | True |  | v1_pass_landing | view |  | vip_pass_landing | False |  |  | True |  |  |  |
| VIP Pass | VIP Pass Landing | Clicks 'Back' arrow | False |  | v1_back | click |  | vip_pass_landing | False |  |  | True |  |  |  |
| VIP Pass | VIP Pass Landing | Clicks 'Proceed' button | True | VIP Pass purchase initiated | v1_proceed | click |  | vip_pass_landing | False |  | pass_id | True |  |  |  |
| VIP Pass | VIP Pass Landing | Clicks 'Want Tds Deducted' | False |  | v1_want_tds_deducted | click |  | vip_pass_landing | False |  |  | True |  |  |  |
| VIP Pass | VIP Pass Landing | Clicks 'Enter Tan' | False |  | v1_enter_tan | click |  | vip_pass_landing | False |  |  | True |  |  |  |
| VIP Pass | VIP Pass Landing | Clicks 'Call Custom Plan' | False |  | v1_call_custom_plan | click |  | vip_pass_landing | False |  |  | True |  |  |  |
| VIP Pass | VIP Pass Landing | Clicks 'Imp Info' | False |  | v1_imp_info | click |  | vip_pass_landing | False |  |  | True |  |  |  |
| VIP Pass | VIP Pass Landing | Clicks 'Learn Why' | False |  | v1_learn_why | click |  | vip_pass_landing | False |  |  | True |  |  |  |
| VIP Pass | VIP Pass Landing | Views 'Pass Payment Bottomsheet' | False |  | v1_review_pass_btmsheet | view | pass_payment_btmsheet | vip_pass_landing | False |  |  | True |  |  |  |
| VIP Pass | VIP Pass Landing | Clicks 'Proceed Payment' on 'Pass Payment Bottomsheet' | False |  | v1_proceed_payment | click | pass_payment_btmsheet | vip_pass_landing | False |  |  | True |  |  |  |
| VIP Pass | VIP Pass Landing | Clicks 'Close' (X) on 'Pass Payment Bottomsheet' | False |  | v1_close | click | pass_payment_btmsheet | vip_pass_landing | False |  |  | True |  |  |  |
| VIP Pass | VIP Pass Landing | Views 'Tds Bottomsheet' | False |  | v1_learn_why | view | tds_btmsheet | vip_pass_landing | False |  |  | True |  |  |  |
| VIP Pass | VIP Pass Landing | Clicks 'Close' (X) on 'Tds Bottomsheet' | False |  | v1_close | click | tds_btmsheet | vip_pass_landing | False |  |  | True |  |  |  |
| VIP Pass | VIP Pass Landing | Clicks 'Understand' on 'Tds Bottomsheet' | False |  | v1_understand | click | tds_btmsheet | vip_pass_landing | False |  |  | True |  |  |  |
| VIP Pass | VIP Pass Landing | Views 'Add To Active Trip Bottomsheet' | False |  | v1_add_to_active_trip | view | add_to_active_trip_btmsheet | vip_pass_landing | False |  |  | True |  |  |  |
| VIP Pass | VIP Pass Landing | Clicks 'Add To Active Trip' on 'Add To Active Trip Bottomsheet' | False |  | v1_add_to_active_trip | click | add_to_active_trip_btmsheet | vip_pass_landing | True |  | trip_idx | True |  |  |  |
| VIP Pass | VIP Pass Landing | Clicks 'Close' (X) on 'Add To Active Trip Bottomsheet' | False |  | v1_close | click | add_to_active_trip_btmsheet | vip_pass_landing | False |  |  | True |  |  |  |
| VIP Pass | VIP Pass Landing | Clicks 'Activate Separate' on 'Add To Active Trip Bottomsheet' | False |  | v1_activate_separate | click | add_to_active_trip_btmsheet | vip_pass_landing | False |  |  | True |  |  |  |
| VIP Pass | VIP Pass Details |  | False |  | v1_pass_detail | view |  | vip_pass_detail | False |  |  | True |  |  |  |
| VIP Pass | VIP Pass Details | Clicks 'Back' arrow | False |  | v1_back | click |  | vip_pass_detail | False |  |  | True |  |  |  |
| VIP Pass | VIP Pass Details | Clicks 'Download Invoice' | False |  | v1_download_invoice | click |  | vip_pass_detail | False |  |  | True |  |  |  |
| VIP Pass | Apply Promo |  | False |  | v1_promo_list | view |  | promo_page | False |  |  | True |  |  |  |
| VIP Pass | Apply Promo | Clicks 'Back' arrow | False |  | v1_back | click |  | promo_page | False |  |  | True |  |  |  |
| VIP Pass | Apply Promo | Clicks 'Select Promo' | False |  | v1_select_promo | click |  | promo_page | False |  | status | True |  |  |  |
| VIP Pass | Apply Promo | Clicks 'Enter Promo Code' | False |  | v1_enter_promo_code | click |  | promo_page | False |  |  | True |  |  |  |
| VIP Pass | Pass Activated |  | True |  | v1_pass_active | view |  | pass_activation_success | False |  | type | True |  |  |  |
| VIP Pass | Pass Activated | Clicks 'Pass Active' | False |  | v1_pass_active | click |  | pass_activation_success | False |  | trips_count | True |  |  |  |
| VIP Pass | Pass Activated | Clicks 'Applied On Trip' | False |  | v1_applied_on_trip | click |  | pass_activation_success | True |  | trip_idx | True |  |  |  |
| My Account | My Account |  | True |  | v1_my_accnt | view |  | my_account | False |  | kyc_status | True |  |  |  |
| My Account | My Account | Clicks 'Back' arrow | False |  | v1_back_btn | click | top_nav | my_account | False |  |  | True |  |  |  |
| My Account | My Account | Views 'Contact Us Bottomsheet' | False |  | v1_contact_us_bottomsheet | view | contact_us_bottomsheet | my_account | False |  |  | True |  |  |  |
| My Account | My Account | Clicks 'Call' button on 'Contact Us Bottomsheet' | False |  | v1_call_btn | click | contact_us_bottomsheet | my_account | False |  | poc | True |  |  |  |
| My Account | My Account | Clicks 'Got it' on 'Contact Us Bottomsheet' | False |  | v1_got_it_btn | click | contact_us_bottomsheet | my_account | False |  |  | True |  |  |  |
| My Account | My Account | Clicks 'KYC' on 'Account Details' | False |  | v1_kyc_btn | click | account_details | my_account | False |  |  | True |  |  |  |
| My Account | My Account | Clicks 'Account Settings' on 'Account Details' | False |  | v1_accnt_settings | click | account_details | my_account | False |  |  | True |  |  |  |
| My Account | My Account | Clicks 'Add Team' on 'Account Details' | False |  | v1_add_team | click | account_details | my_account | False |  |  | True |  |  |  |
| My Account | My Account | Clicks 'Busn Dtls' button on 'Account Details' | False |  | v1_busn_dtls_btn | click | account_details | my_account | False |  |  | True |  |  |  |
| My Account | My Account | Clicks 'Address Book' on 'Account Details' | False |  | v1_address_book | click | account_details | my_account | False |  |  | True |  |  |  |
| My Account | My Account | Clicks 'Wallet' on 'Account Details' | False |  | v1_wallet | click | account_details | my_account | False |  |  | True |  |  |  |
| My Account | My Account | Clicks 'Policies' on 'Account Details' | False |  | v1_policies | click | account_details | my_account | False |  |  | True |  |  |  |
| My Account | My Account | Clicks 'Help Support' on 'Account Details' | False |  | v1_help_support | click | account_details | my_account | False |  |  | True |  |  |  |
| My Account | Account (GST Verification) |  | False |  | v1_pass_type | view |  | account_screen | False |  | type | True |  |  |  |
| My Account | Account (GST Verification) |  | False |  | v1_upload_method | view |  | account_screen | False |  |  | True |  |  |  |
| My Account | Account (GST Verification) | Clicks 'Upload Image' | False |  | v1_upload_image | click |  | account_screen | False |  |  | True |  |  |  |
| My Account | Account (GST Verification) | Clicks 'Verify' | False |  | v1_verify | click |  | account_screen | False |  |  | True |  |  |  |
| My Account | Account (GST Verification) | Clicks 'Reupload' | False |  | v1_reupload | click |  | account_screen | False |  |  | True |  |  |  |
| My Account | Account (GST Verification) | Clicks 'Close' (X) | False |  | v1_close | click |  | account_screen | False |  |  | True |  |  |  |
| My Account | Account (GST Verification) | Clicks 'Contact Us' | False |  | v1_contact_us | click |  | account_screen | False |  |  | True |  |  |  |
| My Account | Account (GST Verification) | Clicks 'Pass Type' | False |  | v1_pass_type | click |  | account_screen | False |  |  | True |  |  |  |
| My Account | Account (GST Verification) | Clicks 'Upload Method' on 'Kyc Bottomsheet' | False |  | v1_upload_method | click | kyc_bottomsheet | account_screen | False |  | mode | True |  |  |  |
| My Account | Account (GST Verification) | Views 'Verifying Gst Bottomsheet' | False |  | v1_verifying_gst_bottomsheet | view | verifying_gst_bottomsheet | account_screen | False |  | value | True |  |  |  |
| My Account | Account (GST Verification) | Views 'Verifying Gst Bottomsheet' | False |  | v1_offer_activated | view | verifying_gst_bottomsheet | account_screen | False |  |  | True |  |  |  |
| My Account | Account (GST Verification) | Clicks 'Continue' button on 'Bonus Unlocked Bottomsheet' | False |  | v1_continue | click | bonus_unlocked_bottomsheet | account_screen | False |  |  | True |  |  |  |
| My Account | Account (GST Verification) | Clicks 'Link Acct' on 'Gst Info' | False |  | v1_link_acct | click | gst_info | account_screen | False |  |  | True |  |  |  |
| My Account | Business Details |  | False |  | v1_business_details | view |  | business_details | False |  |  | True |  |  |  |
| My Account | Business Details | Clicks 'Back' arrow | False |  | v1_back_btn | click | top_nav | business_details | False |  |  | True |  |  |  |
| My Account | KYC Details |  | False |  | v1_kyc_gst | view |  | kyc_details | False |  | gst | True |  |  |  |
| My Account | KYC Details |  | False |  | v1_kyc_income_tax | view |  | kyc_details | False |  | kyc_status | True |  |  |  |
| My Account | KYC Details |  | False |  | v1_link_acc_bot | view |  | kyc_details | False |  |  | True |  |  |  |
| My Account | KYC Details |  | False |  | v1_verify_acct_bot | view |  | kyc_details | False |  |  | True |  |  |  |
| My Account | KYC Details |  | False |  | v1_billing_gst_slab_bottomsheet | view |  | kyc_details | False |  |  | True |  |  |  |
| My Account | KYC Details |  | False |  | v1_mismatch_mob_bot | view |  | kyc_details | False |  |  | True |  |  |  |
| My Account | KYC Details | Clicks 'Back' arrow | False |  | v1_back_btn | click | top_nav | kyc_details | False |  |  | True |  |  |  |
| My Account | KYC Details | Clicks 'Submit' button | False |  | v1_submit_btn | click | bottom_nav | kyc_details | False |  | tan_no | True |  |  |  |
| My Account | KYC Details | Clicks 'Income Tax' button on 'Gst Info' | False |  | v1_income_tax_btn | click | gst_info | kyc_details | False |  |  | True |  |  |  |
| My Account | KYC Details | Clicks 'Gst' button on 'Gst Info' | False |  | v1_gst_btn | click | gst_info | kyc_details | False |  |  | True |  |  |  |
| My Account | KYC Details | Clicks 'Change' button on 'Gst Info' | False |  | v1_change_btn | click | gst_info | kyc_details | False |  |  | True |  |  |  |
| My Account | KYC Details | Clicks 'Deduct Tds' button on 'Tds Info' | False |  | v1_deduct_tds_btn | click | tds_info | kyc_details | False |  | tds_opt | True |  |  |  |
| My Account | KYC Details | Clicks 'Confirm Mob' on 'Link Acct Bottomsheet' | False |  | v1_confirm_mob | click | link_acct_bottomsheet | kyc_details | False |  | phone | True |  |  |  |
| My Account | KYC Details | Clicks 'Confirm' on 'Verify Acct Bottomsheet' | False |  | v1_confirm | click | verify_acct_bottomsheet | kyc_details | False |  |  | True |  |  |  |
| My Account | KYC Details | Views 'Tan Success Bottomsheet' | False |  | v1_tan_success_bottom_sheet | view | tan_success_bottom_sheet | kyc_details | False |  |  | True |  |  |  |
| My Account | KYC Details | Clicks 'Got it' on 'Tan Success Bottomsheet' | False |  | v1_got_it_btn | click | tan_success_bottom_sheet | kyc_details | False |  |  | True |  |  |  |
| My Account | KYC Details | Clicks 'Close' (X) on 'Billing Gst Slab Bottomsheet' | False |  | v1_close_btn | click | billing_gst_slab_bottomsheet | kyc_details | False |  |  | True |  |  |  |
| My Account | KYC Details | Clicks 'Confirm' button on 'Billing Gst Slab Bottomsheet' | False |  | v1_confirm_btn | click | billing_gst_slab_bottomsheet | kyc_details | False |  | gst | True |  |  |  |
| My Account | KYC Documents |  | False |  | v1_kyc_doc | view |  | kyc_doc | False |  |  | True |  |  |  |
| My Account | KYC Documents |  | False |  | v1_upload_method | view |  | kyc_doc | False |  |  | True |  |  |  |
| My Account | KYC Documents | Clicks 'Upload Image' | False |  | v1_upload_image | click |  | kyc_doc | False |  |  | True |  |  |  |
| My Account | KYC Documents | Clicks 'Verify' | False |  | v1_verify | click |  | kyc_doc | False |  |  | True |  |  |  |
| My Account | KYC Documents | Clicks 'Back' arrow | False |  | v1_back | click |  | kyc_doc | False |  |  | True |  |  |  |
| My Account | KYC Documents | Clicks 'Reupload' | False |  | v1_reupload | click |  | kyc_doc | False |  |  | True |  |  |  |
| My Account | KYC Documents | Clicks 'Contact Us' | False |  | v1_contact_us | click |  | kyc_doc | False |  |  | True |  |  |  |
| My Account | KYC Documents | Clicks 'Close' (X) | False |  | v1_close | click |  | kyc_doc | False |  |  | True |  |  |  |
| My Account | KYC Documents | Clicks 'Upload Method' on 'Kyc Bottomsheet' | False |  | v1_upload_method | click | kyc_bottomsheet | kyc_doc | False |  | mode | True |  |  |  |
| My Account | KYC Documents | Views 'Verifying Gst Bottomsheet' | False |  | v1_verifying_gst_bottomsheet | view | verifying_gst_bottomsheet | kyc_doc | False |  | value | True |  |  |  |
| My Account | KYC Documents | Views 'Verifying Gst Bottomsheet' | False |  | v1_offer_activated | view | verifying_gst_bottomsheet | kyc_doc | False |  |  | True |  |  |  |
| My Account | KYC Documents | Clicks 'Continue' button on 'Bonus Unlocked Bottomsheet' | False |  | v1_continue | click | bonus_unlocked_bottomsheet | kyc_doc | False |  |  | True |  |  |  |
| My Account | KYC Documents | Clicks 'Link Acct' on 'Gst Info' | False |  | v1_link_acct | click | gst_info | kyc_doc | False |  |  | True |  |  |  |
| My Account | GST Entered | Clicks 'Confirm' on 'Kyc Bottomsheet' | False |  | v1_confirm | click | kyc_bottomsheet | gst_entred | False |  |  | True |  |  |  |
| My Account | GST Verification Method | Clicks 'Via Otp' on 'Verification Method' | False |  | v1_via_otp | click | verification_method | gst_verification | False |  |  | True |  |  |  |
| My Account | GST Verification Method | Clicks 'Via Certificate' on 'Verification Method' | False |  | v1_via_certificate | click | verification_method | gst_verification | False |  |  | True |  |  |  |
| My Account | GST Verification Method | Clicks 'Via Bank' on 'Verification Method' | False |  | v1_via_bank | click | verification_method | gst_verification | False |  |  | True |  |  |  |
| My Account | GST Verification Method | Clicks 'Edit' on 'Verification Method' | False |  | v1_edit | click | verification_method | gst_verification | False |  |  | True |  |  |  |
| My Account | Address Book | Clicks 'Filter' | False |  | filter | click | top_nav | add_book | False |  |  | True |  |  |  |
| My Account | Address Book | Clicks 'Back' arrow | False |  | back_btn | click | top_nav | add_book | False |  |  | True |  |  |  |
| My Account | Address Book | Clicks 'Add New Add' | False |  | add_new_add | click | bottom_nav | add_book | False |  |  | True |  |  |  |
| My Account | Address Book | Clicks 'Delete Add' on 'Add Cards' | False |  | delete_add | click | add_cards | add_book | False |  |  | True |  |  |  |
| My Account | Address Book | Clicks 'Edit Add' on 'Add Cards' | False |  | edit_add | click | add_cards | add_book | False |  |  | True |  |  |  |
| My Account | Address Book | Clicks 'Delete Yes' on 'Add Delete Popup' | False |  | delete_yes | click | add_delete_popup | add_book | False |  |  | True |  |  |  |
| My Account | Address Book | Clicks 'Delete No' on 'Add Delete Popup' | False |  | delete_no | click | add_delete_popup | add_book | False |  |  | True |  |  |  |
| My Account | Manage Profiles |  | False |  | v1_manage_profiles | view |  | manage_profiles | False |  |  | True |  |  |  |
| My Account | Manage Profiles | Clicks 'Back' arrow | False |  | v1_back_btn | click | top_nav | manage_profiles | False |  |  | True |  |  |  |
| My Account | Manage Profiles | Clicks 'Owner' button on 'Owner Det' | False |  | v1_owner_btn | click | owner_det | manage_profiles | False |  | id | True |  |  |  |
| My Account | Manage Profiles | Clicks 'New User' on 'Bottom Add User' | False |  | v1_new_user | click | bottom_add_user | manage_profiles | False |  |  | True |  |  |  |
| My Account | Add User |  | False |  | v1_add_user | view |  | add_user | False |  | id | True |  |  |  |
| My Account | Add User |  | False |  | v1_info_bot | view |  | add_user | False |  | action | True |  |  |  |
| My Account | Add User | Clicks 'Back' arrow | False |  | v1_back_btn | click | top_nav | add_user | False |  |  | True |  |  |  |
| My Account | Add User | Clicks 'Save Changes' on 'User Dets' | False |  | v1_save_changes | click | user_dets | add_user | False |  |  | True |  |  |  |
| My Account | Add User | Clicks 'Add User' on 'User Dets' | False |  | v1_add_user | click | user_dets | add_user | False |  |  | True |  |  |  |
| My Account | Add User | Clicks 'Contact Book' icon on 'User Dets' | False |  | v1_contact_book | click | user_dets | add_user | False |  |  | True |  |  |  |
| My Account | Add User | Clicks 'Delete User' on 'User Dets' | False |  | v1_delete_user | click | user_dets | add_user | False |  |  | True |  |  |  |
| My Account | Account Settings | Clicks 'Log Out' on 'Account Details' | False |  | v1_log_out | click | account_details | account_setting | False |  |  | True |  |  |  |
| My Account | Account Settings | Clicks 'Log Out' on 'Logout Bottomsheet' | False |  | v1_log_out | click | logout_bottom_sheet | account_setting | False |  | cta | True |  |  |  |
| My Account | Policies |  | False |  | v1_policies | view |  | policies | False |  |  | True |  |  |  |
| My Account | Policies | Clicks 'Back' arrow | False |  | v1_back_btn | click | top_nav | policies | False |  |  | True |  |  |  |
| My Account | Policies | Opens a policy on 'Policies List' | False |  | v1_policy_entry | click | policies_list | policies | False |  | policy_name | True |  |  |  |
| My Account | Rewards |  | False |  | v1_reward_history | view |  | reward_balance | False |  |  | True |  |  |  |
| My Account | Rewards |  | False |  | v1_how_to_avail | view |  | reward_balance | False |  |  | True |  |  |  |
| My Account | Rewards | Clicks 'Back' arrow | False |  | v1_back_btn | click |  | reward_balance | False |  |  | True |  |  |  |
| My Account | Home Page - KYC / GST |  | False |  | v1_get_bonus | view |  | home_page | False |  | value | True |  |  |  |
| My Account | Home Page - KYC / GST |  | False |  | v1_upload_method | view |  | home_page | False |  |  | True |  |  |  |
| My Account | Home Page - KYC / GST | Clicks 'Complete Profile' | False |  | v1_complete_profile | click |  | home_page | False |  |  | True |  |  |  |
| My Account | Home Page - KYC / GST | Clicks 'Upload Image' | False |  | v1_upload_image | click |  | home_page | False |  |  | True |  |  |  |
| My Account | Home Page - KYC / GST | Clicks 'Back' arrow | False |  | v1_back | click |  | home_page | False |  |  | True |  |  |  |
| My Account | Home Page - KYC / GST | Clicks 'View Avail Balance' | False |  | v1_view_avail_balance | click |  | home_page | False |  |  | True |  |  |  |
| My Account | Home Page - KYC / GST | Clicks 'Verify' | False |  | v1_verify | click |  | home_page | False |  |  | True |  |  |  |
| My Account | Home Page - KYC / GST | Clicks 'Reupload' | False |  | v1_reupload | click |  | home_page | False |  |  | True |  |  |  |
| My Account | Home Page - KYC / GST | Clicks 'Contact Us' | False |  | v1_contact_us | click |  | home_page | False |  |  | True |  |  |  |
| My Account | Home Page - KYC / GST | Clicks 'Upload Method' on 'Kyc Bottomsheet' | False |  | v1_upload_method | click | kyc_bottomsheet | home_page | False |  | mode | True |  |  |  |
| My Account | Home Page - KYC / GST | Views 'Verifying Gst Bottomsheet' | False |  | v1_verifying_gst_bottomsheet | view | verifying_gst_bottomsheet | home_page | False |  | value | True |  |  |  |
| My Account | Home Page - KYC / GST | Views 'Verifying Gst Bottomsheet' | False |  | v1_offer_activated | view | verifying_gst_bottomsheet | home_page | False |  |  | True |  |  |  |
| My Account | Home Page - KYC / GST | Clicks 'Continue' button on 'Bonus Unlocked Bottomsheet' | False |  | v1_continue | click | bonus_unlocked_bottomsheet | home_page | False |  |  | True |  |  |  |
| My Account | Home Page - KYC / GST | Clicks 'Link Acct' on 'Gst Info' | False |  | v1_link_acct | click | gst_info | home_page | False |  |  | True |  |  |  |
| Help & Support | Home Page | Clicks 'Help' tab | False |  | v1_help | click | bottom_nav | home_page | False |  |  | True |  |  |  |
| Help & Support | Home Page | Clicks floating 'Call Us' button | False |  | call_us | click | bottom_nav | home_page | False |  |  | True |  |  |  |
| Help & Support | My Account | Clicks 'Help Support' on 'Account Details' | False |  | v1_help_support | click | account_details | my_account | False |  |  | True |  |  |  |
| Help & Support | App Shortcut | Clicks 'App Shortcut' on 'Open Help Trip List Screen' | False |  | v1_app_shortcut | click | open_help_trip_list_screen | app_shortcut | False |  | user_code | True |  |  |  |
| Help & Support | Trip Scheduled - Help / Ticket | Clicks 'Raise Issue' | False |  | v1_raise_issue | click | bottom_nav | scheduled | True |  | expense_type | True |  |  |  |
| Help & Support | Trip Scheduled - Help / Ticket | Clicks 'Create Ticket' on 'Help Support' | False |  | v1_create_ticket | click | help_support | scheduled | True |  |  | True |  |  |  |
| Help & Support | Trip Scheduled - Help / Ticket | Clicks 'Need Help' on 'Help Widget' | False |  | v1_need_help | click | help_widget | scheduled | True |  |  | True |  |  |  |
| Help & Support | Going To Load - Help / Ticket | Clicks 'Raise Issue' | False |  | v1_raise_issue | click | bottom_nav | going_to_load | True |  | expense_type | True |  |  |  |
| Help & Support | Going To Load - Help / Ticket | Clicks 'Create Ticket' on 'Help Support' | False |  | v1_create_ticket | click | help_support | going_to_load | True |  |  | True |  |  |  |
| Help & Support | Going To Load - Help / Ticket | Clicks 'Need Help' on 'Help Widget' | False |  | v1_need_help | click | help_widget | going_to_load | True |  |  | True |  |  |  |
| Help & Support | Going To Load - Help / Ticket | Opens an existing ticket on 'Tickets' | False |  | v1_open_ticket | click | tickets | going_to_load | True |  | status | True |  |  |  |
| Help & Support | At Loading - Help / Ticket | Clicks 'Create Ticket' on 'Help Support' | False |  | v1_create_ticket | click | help_support | at_loading | True |  |  | True |  |  |  |
| Help & Support | At Loading - Help / Ticket | Clicks 'Need Help' on 'Help Widget' | False |  | v1_need_help | click | help_widget | at_loading | True |  |  | True |  |  |  |
| Help & Support | At Loading - Help / Ticket | Clicks 'Raise Issue' | False |  | v1_raise_issue | click | bottom_nav | at_loading | True |  | expense_type | True |  |  |  |
| Help & Support | At Loading - Help / Ticket | Opens an existing ticket on 'Tickets' | False |  | v1_open_ticket | click | tickets | at_loading | True |  | status | True |  |  |  |
| Help & Support | In Transit - Help / Ticket | Clicks 'Create Ticket' on 'Help Support' | False |  | v1_create_ticket | click | help_support | in_transit | True |  |  | True |  |  |  |
| Help & Support | In Transit - Help / Ticket | Clicks 'Need Help' on 'Help Widget' | False |  | v1_need_help | click | help_widget | in_transit | True |  |  | True |  |  |  |
| Help & Support | In Transit - Help / Ticket | Opens an existing ticket on 'Tickets' | False |  | v1_open_ticket | click | tickets | in_transit | True |  | status | True |  |  |  |
| Help & Support | In Transit - Help / Ticket | Clicks 'Raise Issue' | False |  | v1_raise_issue | click | bottom_nav | in_transit | True |  | expense_type | True |  |  |  |
| Help & Support | At Unloading - Help / Ticket | Clicks 'Create Ticket' on 'Help Support' | False |  | v1_create_ticket | click | help_support | at_unloading | True |  |  | True |  |  |  |
| Help & Support | At Unloading - Help / Ticket | Clicks 'Need Help' on 'Help Widget' | False |  | v1_need_help | click | help_widget | at_unloading | True |  |  | True |  |  |  |
| Help & Support | At Unloading - Help / Ticket | Opens an existing ticket on 'Tickets' | False |  | v1_open_ticket | click | tickets | at_unloading | True |  | status | True |  |  |  |
| Help & Support | At Unloading - Help / Ticket | Clicks 'Raise Issue' | False |  | v1_raise_issue | click | bottom_nav | at_unloading | True |  | expense_type | True |  |  |  |
| Help & Support | Trip End - Help / Ticket | Clicks 'Create Ticket' on 'Help Support' | False |  | v1_create_ticket | click | help_support | trip_end | True |  |  | True |  |  |  |
| Help & Support | Trip End - Help / Ticket | Clicks 'Need Help' on 'Help Widget' | False |  | v1_need_help | click | help_widget | trip_end | True |  |  | True |  |  |  |
| Help & Support | Trip End - Help / Ticket | Clicks 'Raise Issue' | False |  | v1_raise_issue | click | bottom_nav | trip_end | True |  | expense_type | True |  |  |  |
| Help & Support | Trip End - Help / Ticket | Opens an existing ticket on 'Tickets' | False |  | v1_open_ticket | click | tickets | trip_end | True |  | status | True |  |  |  |
| Help & Support | Cancelled Trip - Help / Ticket | Clicks 'Create Ticket' on 'Help Support' | False |  | v1_create_ticket | click | help_support | cancelled | True |  |  | True |  |  |  |
| Help & Support | Cancelled Trip - Help / Ticket | Clicks 'Need Help' on 'Help Widget' | False |  | v1_need_help | click | help_widget | cancelled | True |  |  | True |  |  |  |
| Help & Support | Cancelled Trip - Help / Ticket | Opens an existing ticket on 'Tickets' | False |  | v1_open_ticket | click | tickets | cancelled | True |  | status | True |  |  |  |
| Help & Support | Help Home |  | True |  | v1_help | view |  | help | False |  |  | True |  |  |  |
| Help & Support | Help Home | Selects an issue on 'Issue List' | False |  | v1_issue_select | click | issue_list | help | False | ticket_id |  | True |  |  |  |
| Help & Support | Help Home | Clicks 'Call Us' on 'Issue List' | False |  | v1_call_us | click | issue_list | help | False | ticket_id |  | True |  |  |  |
| Help & Support | Help Home | Clicks hyperlink on 'Issue List' | False |  | v1_hyperlink | click | issue_list | help | False | ticket_id |  | True |  |  |  |
| Help & Support | Help Home | Clicks 'Chat With Us' on 'Issue List' | False |  | v1_chat_with_us | click | issue_list | help | False | ticket_id |  | True |  |  |  |
| Help & Support | Help Home | Opens a ticket card on 'Issue Cards' | False |  | v1_open_tkt | click | issue_cards | help | False | ticket_id |  | True |  |  |  |
| Help & Support | Help Home | Clicks 'View All' on 'Issue Cards' | False |  | v1_view_all | click | issue_cards | help | False |  |  | True |  |  |  |
| Help & Support | Help Home | Clicks 'View All' on 'Trip Cards' | False |  | v1_view_all | click | trip_cards | help | False |  |  | True |  |  |  |
| Help & Support | My Tickets | Clicks 'Back' arrow | False |  | v1_back_btn | click | top_nav | view_issues | False |  |  | True |  |  |  |
| Help & Support | My Tickets | Clicks 'Select Issue' on 'Tickets List' | False |  | v1_select_issue | click | tickets_list | view_issues | False | ticket_id | idx | True |  |  |  |
| Help & Support | My Tickets | Clicks 'Need Help' on 'Tickets List' | False |  | v1_need_help | click | tickets_list | view_issues | False |  |  | True |  |  |  |
| Help & Support | Help - Select Trip | Clicks 'Back' arrow | False |  | v1_back_btn | click | top_nav | need_help_trips | False |  |  | True |  |  |  |
| Help & Support | Help - Select Trip | Clicks 'Need Help' on 'Trip List' | False |  | v1_need_help | click | trip_list | need_help_trips | True |  | idx | True |  |  |  |
| Help & Support | Help - Trip Issues | Selects an issue on 'Issue List' | False |  | v1_issue_select | click | issue_list | need_help_trip_detail | True | ticket_id |  | True |  |  |  |
| Help & Support | Help - Trip Issues | Clicks 'Chat With Us' on 'Issue List' | False |  | v1_chat_with_us | click | issue_list | need_help_trip_detail | True | ticket_id |  | True |  |  |  |
| Help & Support | Help - Trip Issues | Clicks 'Call Us' on 'Issue List' | False |  | v1_call_us | click | issue_list | need_help_trip_detail | True | ticket_id |  | True |  |  |  |
| Help & Support | Help - Trip Issues | Clicks hyperlink on 'Issue List' | False |  | v1_hyperlink | click | issue_list | need_help_trip_detail | True | ticket_id |  | True |  |  |  |
| Help & Support | Damage Claim - Select Items | Clicks 'Submit' button | False |  | v1_submit | click | bottom_nav | dmg_select_items | False |  | count_of_images | True |  |  |  |
| Help & Support | Damage Claim - Select Items | Clicks 'Search Cross' | False |  | v1_search_cross | click | top_nav | dmg_select_items | False |  |  | True |  |  |  |
| Help & Support | Damage Claim - Select Items | Clicks 'Qty Done' on 'Qty Bottomsheet' | False |  | v1_qty_done | click | qty_bottom_sheet | dmg_select_items | False |  |  | True |  |  |  |
| Help & Support | Damage Claim - Upload Photos | Clicks 'Submit' button | False |  | v1_submit | click | bottom_nav | dmg_upload_pics | False |  | count_of_images | True |  |  |  |
| Help & Support | Damage Claim - Upload Photos | Clicks 'Upload' button on 'Upload Image' | False |  | v1_upload_btn | click | upload_image | dmg_upload_pics | False |  |  | True |  |  |  |
| Help & Support | Chatbot | Clicks 'Option' button on 'Chat Window' | False |  | option_btn | click | chat_window | chatbot | False |  | button_name | True |  |  |  |
| Help & Support | Chatbot | Views 'Chat Interaction' | False |  | v1_chat_feedback | view | chat_interaction | chatbot | False |  | text | True |  |  |  |
| Help & Support | Chatbot | Clicks 'Chat Feedback' on 'Chat Interaction' | False |  | v1_chat_feedback | click | chat_interaction | chatbot | False |  | feedback | True |  |  |  |
| Help & Support | Chat With Us (Ticket) |  | True |  | v1_screen_view | view |  | chat_with_us | False |  |  | True |  |  |  |
| Help & Support | Chat With Us (Ticket) | Selects a sub-issue on 'Chat Interaction' | False |  | v1_sub_issue_select | click | chat_interaction | chat_with_us | False | session_id | medium | True |  |  |  |
| Help & Support | Chat With Us (Ticket) | Clicks 'Back' arrow on 'Chat Interaction' | False |  | v1_back_btn | click | chat_interaction | chat_with_us | False | session_id | medium | True |  |  |  |
| Help & Support | Chat With Us (Ticket) | Clicks 'Raise Issue' on 'Chat Interaction' | False |  | v1_raise_issue | click | chat_interaction | chat_with_us | False | session_id | medium | True |  |  |  |
| Help & Support | Chat With Us (Ticket) | Clicks 'Enter Remark' on 'Chat Interaction' | False |  | v1_enter_remark | click | chat_interaction | chat_with_us | False | session_id | medium | True |  |  |  |
| Help & Support | Chat With Us (Ticket) | Clicks 'No' on 'Chat Interaction' | False |  | v1_no | click | chat_interaction | chat_with_us | False | session_id |  | True |  |  |  |
| Help & Support | Chat With Us (Ticket) | Clicks 'Not Satisfy' on 'Chat Interaction' | False |  | v1_not_satisfy | click | chat_interaction | chat_with_us | False |  | amt | True |  |  |  |
| Help & Support | Chat With Us (Ticket) | Clicks 'Yes' on 'Chat Interaction' | False |  | v1_yes | click | chat_interaction | chat_with_us | False | session_id |  | True |  |  |  |
| Help & Support | Chat With Us (Ticket) | Clicks 'Call Us' on 'Chat Interaction' | False |  | v1_call_us | click | chat_interaction | chat_with_us | False |  | medium | True |  |  |  |
| Help & Support | Chat With Us (Ticket) | Clicks 'Track Complaint' on 'Chat Interaction' | False |  | v1_track_complaint | click | chat_interaction | chat_with_us | False | session_id | medium | True |  |  |  |
| Help & Support | Chat With Us (Ticket) | Clicks 'Reopen Tkt' on 'Chat Interaction' | False |  | v1_reopen_tkt | click | chat_interaction | chat_with_us | False | session_id |  | True |  |  |  |
| Help & Support | Chat With Us (Ticket) | Clicks 'Reason' on 'Chat Interaction' | False |  | v1_reason | click | chat_interaction | chat_with_us | False | session_id | reason | True |  |  |  |
| Help & Support | Chat With Us (Ticket) | Clicks hyperlink on 'Chat Interaction' | False |  | v1_hyperlink | click | chat_interaction | chat_with_us | False | session_id | medium | True |  |  |  |
| Help & Support | Chat With Us (Ticket) | Clicks 'Submit Loss Amt' on 'Chat Interaction' | False |  | v1_submit_loss_amt | click | chat_interaction | chat_with_us | False |  |  | True |  |  |  |
| Help & Support | Chat With Us (Ticket) | Clicks 'Cnfirm Amt' on 'Chat Interaction' | False |  | v1_cnfirm_amt | click | chat_interaction | chat_with_us | False |  |  | True |  |  |  |
| Help & Support | Chat With Us (Ticket) | Clicks 'Exit' on 'Exit Bottomsheet' | False |  | v1_exit | click | exit_bottom_sheet | chat_with_us | False | session_id | text | True |  |  |  |
| Help & Support | Chat With Us (Ticket) | Clicks 'Continue Chat' on 'Exit Bottomsheet' | False |  | v1_continue_chat | click | exit_bottom_sheet | chat_with_us | False | session_id | text | True |  |  |  |
| Notifications & Widgets | Push Notification | Views 'Sent' | False |  | bt_nt_sent | view | sent | notification | False |  | notification_id | True |  |  |  |
| Notifications & Widgets | Push Notification | Views 'View' | False |  | bt_nt_received | view | view | notification | False |  | notification_id | True |  |  |  |
| Notifications & Widgets | Push Notification - Vehicle Confirmation | Clicks 'Close' (X) on 'Confirm Demand' | False |  | v1_close | click | confirm_demand | notification | True |  | mis_time | True |  |  |  |
| Notifications & Widgets | Push Notification - Vehicle Confirmation | Clicks 'Accept' on 'Confirm Demand' | False |  | v1_accept | click | confirm_demand | notification | True |  | timer | True |  |  |  |
| Notifications & Widgets | Home Screen Widget | Clicks 'Widget Added' on 'Widget Lifecycle' | False |  | v1_widget_added | click | widget_lifecycle | home_widget | False |  | user_code | True |  |  |  |
| Notifications & Widgets | Home Screen Widget | Clicks 'Widget Removed' on 'Widget Lifecycle' | False |  | v1_widget_removed | click | widget_lifecycle | home_widget | False |  | user_code | True |  |  |  |
| Notifications & Widgets | Home Screen Widget | Clicks 'Rebook Widget' on 'Widget Card' | False |  | v1_rebook_widget | click | widget_card | home_widget | False |  | user_code | True |  |  |  |
| Notifications & Widgets | Home Screen Widget | Clicks 'Rebook Widget' on 'Widget Cta' | False |  | v1_rebook_widget | click | widget_cta | home_widget | False |  | user_code | True |  |  |  |
| Notifications & Widgets | App Shortcut | Clicks 'App Shortcut' on 'My Trips' | False |  | v1_app_shortcut | click | my_trips | app_shortcut | False |  | user_code | True |  |  |  |
| Notifications & Widgets | App Shortcut | Clicks 'App Shortcut' on 'D Create' | False |  | v1_app_shortcut | click | d_create | app_shortcut | False |  | user_code | True |  |  |  |
| Notifications & Widgets | App Shortcut | Clicks 'App Shortcut' on 'Open Help Trip List Screen' | False |  | v1_app_shortcut | click | open_help_trip_list_screen | app_shortcut | False |  | user_code | True |  |  |  |
| Notifications & Widgets | App Shortcut | Clicks 'App Shortcut' on 'Payment Home' | False |  | v1_app_shortcut | click | payment_home | app_shortcut | False |  | user_code | True |  |  |  |

## Operator

| Journey | Feature Description | Page Description | Event Description | Important Details | Event name | Event action | Event Category | Screen name | Miscellaneous | Entity id |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| - | - | - | - | - | add exact value | add exact value | add exact value | add exact value | add only key values and their defination if needed | add only key values and their defination if needed |
| Demand Confirmation Flow | After DR, notification for rate confirmation are being sent to eligible FO. And  demand card in shown on Confirm Load page.<br>This flow covers journey from Notification/Demand Card to Token payment | Overlay notification | Notification delivered | To identify exact event,  notification id to be matched with fact_notification_history_s3 with filter notification_type="Booking Automation" | NotificationStatus | view |  |  | nid |  |
|  |  |  | Action taken on the notification | Following action are defined as,<br>CONFIRM_BOOKING - Click on Confirm<br>NEED_PROGRAM - Click anywhere on notification<br>DISMISS - Click on back button | NotificationAction | click |  |  | nid<br>action |  |
|  |  | Demand Card | Demand card viewed |  | v1_load_card | view | load_card | web_confirm_load | amount : Rate shown to FO<br>demand_index : Rank of card starting from 0 | demand_id |
|  |  |  | Clicked on Demand Card |  | v1_load_confirm | click | load_card | web_confirm_load | entity : demand_id<br>freight : Rate shown to FO<br>demand_index : Rank of card starting from 0 |  |
|  |  | Token Page | Toke Page viewed |  | v1_load_confirmation | view |  | web_load_confirmation | conf_freight : Rate shown to FO | demandId |
|  |  |  | Token Paid clicked |  | v1_submit_btn | click | bottom_nav | web_load_confirmation | conf_freight : Rate shown to FO | demandId |
|  |  |  |  | This is scroll button | v1_submit_btn | click | we_wallet_bottom_sheet | web_load_confirmation | conf_freight : Rate shown to FO | demandId |
| Bidding Flow | FO asked to quote their rate for demands.<br>This flow covers journey from Notification/Demand Card to Token payment | Overlay notification | Notification delivered | To identify exact event,  notification id to be matched with fact_notification_history_s3 with filter notification_type="Bidding" | NotificationStatus | view |  |  | nid |  |
|  |  |  | Action taken on the notification | Following action are defined as,<br>CONFIRM_BOOKING - Click on Confirm<br>NEED_PROGRAM - Click anywhere on notification<br>DISMISS - Click on back button | NotificationAction | click |  |  | nid<br>action |  |
|  |  | Demand Card | Demand card viewed |  | v1_load_card | view | load_card | web_confirm_load | amount : Always null value<br>demand_index : Rank of card starting from 0 | demand_id |
|  |  |  | Clicked on Demand Card |  | v1_rate_and_confirm | click | load_cards | web_confirm_load | entity : demand_id<br>demand_index : Rank of card starting from 0 |  |
|  |  | Bidding | Bidding Page viewed |  | v1_rate_and_confirm | view | rate_and_confirm | web_rate_and_confirm | conf_freight : Always null value | demandId |
|  |  |  | Rate edited |  | v1_plus | click | bottom_nav | web_rate_and_confirm |  | demand_id |
|  |  |  |  |  | v1_minus | click | bottom_nav | web_rate_and_confirm |  | demand_id |
|  |  |  | Token Paid clicked |  | v1_submit | click | bottom_nav | web_rate_and_confirm | conf_freight : Rate selected by FO<br>get_prob : % probability value shown to FO | demand_id |
|  |  |  |  | This is scroll button | v1_submit_btn | click | we_wallet_bottom_sheet | web_load_confirmation | token_amt : Rate selected by FO | demandId |
| Load Browsing Flow | FO lands on Marketplace Home (Live loads) and browses available loads.<br>Covers vehicle availability popup, vehicle / vehicle-type chips, Loading-Unloading-Vehicle filters, My loads tab, add vehicle (+) and opening a load card into Load details. | Home – Live loads | Home page viewed | Fires on every Home open (also after bottom-nav HOME and after a bid) | non_sub_loads | view |  | web_non_sub_loads |  |  |
|  |  |  | Home template viewed |  | template_name | view | top_nav | web_non_sub_loads | u_s : user segment (blank for test user) | u_c, u_m (null for test user) |
|  |  |  | Broker promo tooltip viewed | Fires 2× per Home open | broker_promo_tooltip | view | broker_promo_tooltip | web_home_page |  |  |
|  |  |  | Token card viewed | screen_name comes as web_trip_details on Home (wrong) | token_active | view | token_card | web_trip_details |  |  |
|  |  |  | Bottom nav clicked | event_name = tab clicked (HOME, AVAILABLE_VEHICLES, TRIPS, HELP_SUPPORT, OPERATOR_PROFILE); screen_name = screen being left | HOME / AVAILABLE_VEHICLES / TRIPS / HELP_SUPPORT / OPERATOR_PROFILE | click | bottom_nav | web_home / web_my_trips / web_veh_available / web_help / web_my_account |  |  |
|  |  | Vehicle availability popup ("कौनसी गाड़ी खाली है?") | Popup viewed | Opens on Home load; also fires after every filter submit | vt_list | view |  | web_active_loads |  |  |
|  |  |  | Vehicle marked available / not available | Toggle on a vehicle row | toggle | click |  | web_active_loads | on_off : on / off<br>vehicle_id : internal vehicle id<br>load_count : loads available for that vehicle |  |
|  |  |  | "गाड़ी खाली नहीं है" clicked | No event fires (gap). Search box also fires nothing |  |  |  |  |  |  |
|  |  | Home – chips & filters | Vehicle chip clicked | Chips at top: सभी लोड / each vehicle number | veh_select | click | load_filters | web_active_loads | vehicle_number : vehicle selected (सभी लोड = all) |  |
|  |  |  | Vehicle-type chip clicked | e.g. ओपन 42-45 ft. Same event for select and unselect | filter_select | click | filters | web_active_loads | id : vehicle-type id |  |
|  |  |  | Loading dropdown clicked | Opens Filter sheet on Loading tab | loading_location_filter | click | filters | web_active_loads |  |  |
|  |  |  | अन्य गाड़ी clicked | Opens Filter sheet on Vehicle type tab | select_other_veh | click | filters | web_active_loads |  |  |
|  |  | Filter sheet ("फ़िल्टर लगाएं") | Tab switched | Tabs: लोडिंग / अनलोडिंग / गाड़ी टाइप. Picking a state, city, vehicle type or length fires nothing (gap) | tab_switch | click | unified_filter | web_all_loads | tab : LOADING / UNLOADING / VEHICLE |  |
|  |  |  | All filters cleared | सभी फ़िल्टर हटाएं | clear_all | click | unified_filter | web_all_loads |  |  |
|  |  |  | Filters applied | जमा करें | submit | click | unified_filter | web_all_loads | loading : no. of loading cities selected<br>unloading : no. of unloading cities selected<br>vehicle : no. of vehicle types selected<br>loadCount : loads matching the filter |  |
|  |  |  | No-result "अन्य लोड देखें" clicked | Shown when filter returns 0 loads | no_loads_found | click | loads_list | web_active_loads |  |  |
|  |  | Home – My loads | My loads / Live loads tab clicked |  | loads_view | click | loads_view_select | web_active_loads | section : my_loads / new_loads |  |
|  |  |  | My loads empty state viewed | Fires 2× per open | no_loads | view |  | web_active_loads |  |  |
|  |  |  | More-loads banner viewed | screen_name in uppercase | more_loads_for_veh | view | misc_banner | web_HOME_PAGE |  |  |
|  |  | Add vehicle sheet (+) | Add vehicle (+) clicked | + next to vehicle chips | broker_add_chip | click | broker_add_vehicle_fab | web_home_page |  |  |
|  |  |  | Add vehicle sheet viewed |  | broker_search_sheet | view | broker_search_btm_sheet | web_home_page |  |  |
|  |  |  | Vehicle number error shown | e.g. "इस गाड़ी पर GPS नहीं लगा है" | broker_search_error | view | broker_search_btm_sheet | web_home_page | vn : vehicle number entered<br>em : error message shown |  |
|  |  |  | नंबर जमा करें clicked | One click fires both events; lookup event has wrong screen_name | broker_search_submit | click | broker_search_btm_sheet | web_home_page | vn : vehicle number entered |  |
|  |  |  |  |  | broker_search_lookup_fire | click | broker_search_btm_sheet | web_vehicle_confirmation | vn : vehicle number entered |  |
|  |  | Demand Card → Load details | Clicked on Demand Card | One click fires both events | confirm | click | load_card | web_confirm_load | scroll_action : list scrolled before click (true/false)<br>vh_id : vehicle chip selected (ALL)<br>loadTag : card tag (e.g. RECOMMENDED)<br>v_dist : distance shown (true/false)<br>tab : all_loads |  |
|  |  |  |  |  | rate_and_confirm | click | load_cards | web_confirm_load | entity : demand_id<br>scroll_action, vh_id, loadTag, v_dist, tab : same as above | demand_id (inside miscellaneous) |
|  |  |  | Load details page viewed |  | new_load_details | view | top_nav | web_new_load_details | ldp_type : bidding / confirm<br>is_subscribed : token active (true/false)<br>br : broker flag<br>dr : demand rate type<br>source : where opened from (all_loads) | demand_id |
| Valid Bid Flow | FO opens a bidding load, sets a rate, picks a vehicle and driver and submits the bid.<br>This flow covers journey from Demand Card to Bid success (token already active). | Demand Card | Clicked on Demand Card | One click fires both events | confirm | click | load_card | web_confirm_load | scroll_action, vh_id, loadTag, v_dist, tab |  |
|  |  |  |  |  | rate_and_confirm | click | load_cards | web_confirm_load | entity : demand_id | demand_id (inside miscellaneous) |
|  |  | Bidding (Load details) | Bidding page viewed |  | new_load_details | view | top_nav | web_new_load_details | ldp_type : bidding<br>is_subscribed : token active<br>br, dr, source | demand_id |
|  |  |  |  |  | rate_and_confirm | view | rate_and_confirm | web_rate_and_confirm | conf_freight : always null on view | demand_id |
|  |  |  | Token strip viewed |  | token_active | view | token_card | web_confirm_load |  |  |
|  |  |  | Rate edited | − / + buttons | minus | click | bottom_nav | web_new_load_details | ldp_type : bidding<br>conf_freight : rate after change | demand_id |
|  |  |  |  |  | plus | click | bottom_nav | web_new_load_details | ldp_type : bidding<br>conf_freight : rate after change | demand_id |
|  |  |  | Bid submitted (swipe) | Swipe slider "भाड़ा जमा करें" – logged as click | confirm_load | click | bottom_nav | web_new_load_details | ldp_type : bidding<br>conf_freight : rate selected by FO | demand_id |
|  |  | Vehicle selection sheet | Vehicle sheet viewed |  | vehicle_confirmation | view | vehicle_details | web_vehicle_confirmation | time_left : bid timer end (epoch ms)<br>br : broker flag | demand_id |
|  |  |  |  |  | token_active | view | token_card | web_confirm_load |  |  |
|  |  |  | Broker coachmark viewed | "यहाँ पर क्लिक करके मार्केट की कोई भी गाड़ी लगाएं" | broker_coachmark | view | broker_coachmark | web_vehicle_confirmation | br : broker flag |  |
|  |  |  | Coachmark ठीक है clicked |  | broker_coachmark_cta | click | broker_coachmark | web_vehicle_confirmation | br : broker flag |  |
|  |  |  | Vehicle selected | One click fires both events (fired 3× per tap on 18 Oct) | select_veh | click | veh_selection | web_confirm_load | vehicle_num : vehicle selected |  |
|  |  |  |  |  | veh_num_select | click | vehicle_details | web_vehicle_confirmation | br : broker flag<br>on : owner name (null)<br>vn : vehicle number |  |
|  |  |  | Vehicle changed (बदले) |  | vehicle_change | click | vehicle_details | web_vehicle_confirmation |  |  |
|  |  |  | जमा करें clicked | One click fires both events; opens driver details | driver_info_btn | click | bottom_nav | web_vehicle_confirmation |  |  |
|  |  |  |  |  | submit | click | bottom_nav | web_confirm_load |  |  |
|  |  | Driver details | Driver details page viewed | No view event fires (gap). Name field appears after a 10-digit number |  |  |  |  |  |  |
|  |  |  | Driver details submitted | API POST /token/{demandId}/vehicle-details. If vehicle is busy API returns 400 with no message and no event | submit_btn | click | bottom_nav | web_vehicle_confirmation | sel_type : manual / suggested vehicle<br>br : broker flag<br>on : owner name<br>vn : vehicle number<br>pbv : pre-booked vehicle (true/false) | demand_id |
|  |  | Bid success | Load confirmation viewed | Fires 5–6×; conf_freight comes as 0 | load_confirmation | view |  | web_load_confirmation | conf_freight : rate (sent as 0)<br>address_count : no. of addresses (2) | demand_id |
|  |  |  | More-loads card viewed |  | view_load | view | load_card | web_more_loads_for_veh |  |  |
|  |  |  | Bid success sheet viewed | Auto-closes in ~2 s and returns to Home. On 18 Oct this fired as bid_success_bottom_sheet / web_vehicle_confirmation (demand_id) instead | bidding_success | view | token_pay_bottom_sheet | web_load_bidding |  |  |
| Available Vehicles Flow | FO marks which vehicles are free so the app can show matching loads.<br>This flow covers the खाली गाड़ी tab: vehicle list, availability toggle, see loads for a vehicle, and add vehicle. | Available vehicles list | Tab opened | From bottom nav खाली गाड़ी; screen_name = screen being left | AVAILABLE_VEHICLES | click | bottom_nav | web_home |  |  |
|  |  |  | Vehicle list viewed | Same event name as the Home popup | vt_list | view |  | web_veh_available |  |  |
|  |  |  | Vehicle marked available / not available | Toggle on a vehicle row. Search box fires nothing (gap) | toggle | click |  | web_veh_available | on_off : on / off<br>vehicle_id : internal vehicle id<br>load_count : loads available for that vehicle |  |
|  |  |  | "X लोड देखें" clicked | Shown after toggle ON; opens Home with that vehicle's loads | see_loads | click |  | web_veh_available | vehicle_id : internal vehicle id<br>load_count : loads available |  |
|  |  | Add vehicle sheet | + गाड़ी ऐड करें clicked | Home uses broker_add_chip for the same sheet | broker_add_fab | click | broker_add_vehicle_fab | web_available_vehicle |  |  |
|  |  |  | Add vehicle sheet viewed | screen_name has a hyphen here | broker_search_sheet | view | broker_search_btm_sheet | web_available-vehicles |  |  |
|  |  |  | Vehicle number error shown | e.g. "इस गाड़ी पर GPS नहीं लगा है" | broker_search_error | view | broker_search_btm_sheet | web_available-vehicles | vn : vehicle number entered<br>em : error message shown |  |
|  |  |  | नंबर जमा करें clicked | One click fires both events; lookup event has wrong screen_name | broker_search_submit | click | broker_search_btm_sheet | web_available-vehicles | vn : vehicle number entered |  |
|  |  |  |  |  | broker_search_lookup_fire | click | broker_search_btm_sheet | web_vehicle_confirmation | vn : vehicle number entered | demand_id (null here) |
| Trips – Change Driver Flow | FO opens the ट्रिप tab and changes the driver on an active trip.<br>This flow covers Trips list → ड्राइवर बदलें → driver form → confirmation. | Trips list | Tab opened | From bottom nav ट्रिप. Trips list itself fires no view event, and tabs चालू / समाप्त / कैंसिल fire nothing (gap) | TRIPS | click | bottom_nav | web_home |  |  |
|  |  |  | ड्राइवर बदलें clicked | On an active trip card | driver_replacement | click | trip_cards | web_my_trips |  | trip_id |
|  |  | Driver details | Driver form viewed | Name field appears after a 10-digit number | driver_details | view | driver_details | web_driver_details_update |  | trip_id |
|  |  |  | जमा करें clicked |  | submit_btn | click | driver_details | web_driver_details_update |  | trip_id |
|  |  |  | Confirmation viewed | "ड्राइवर बदल दिया गया है"; ठीक है opens Trip details | driver_details_confirmation | view | driver_details_confirmation | web_driver_details_update |  | trip_id |
| Help & Support Flow | FO gets help for a trip or a general issue and raises a ticket.<br>This flow covers the सहायता tab: ticket list, existing ticket chat, trip FAQ and creating a new ticket. | Help home | Tab opened | From bottom nav सहायता | HELP_SUPPORT | click | bottom_nav | web_my_trips |  |  |
|  |  |  | Help page viewed |  | help | view |  | web_help | cat_viewed : sections shown (trip_cards_ticket_cards) |  |
|  |  |  | General issue clicked | साधारण समस्याएँ list (e.g. गाड़ी KYC की समस्या) | issue_select | click | trip_list | web_help |  | questionId : issue text |
|  |  | Tickets | सब देखे clicked | Ticket listing page fires no view event (gap) | view_all | click | issue_cards | web_help |  |  |
|  |  |  | Ticket opened |  | open_tkt | click | issue_cards | web_help |  | ticket_id |
|  |  |  | Ticket chat viewed |  | chat_with_us | view | issue_list | web_chat_with_us | trip_id : null for an existing ticket |  |
|  |  | Trip help (FAQ → chat) | Trip सहायता पाएँ clicked | From आपकी ट्रिप card | need_help | click | trip_cards | web_help |  | trip_id |
|  |  |  | Trip FAQ viewed |  | need_help_trip_detail | view |  | web_need_help_trip_detail |  |  |
|  |  |  | Issue clicked | e.g. वाहन लोड करने में देरी – answer expands | issue_select | click | issue_list | web_need_help_trip_detail |  | questionId : issue text |
|  |  |  | सहायता पाएँ clicked (still need help) |  | chat_with_us | click | issue_list | web_need_help_trip_detail | questionId : issue text |  |
|  |  |  | Chat viewed |  | chat_with_us | view | issue_list | web_chat_with_us | trip_id : trip id |  |
|  |  |  | Ticket raised (जमा करे) | Ticket T0089004 created on stage | raise_issue | click | chat_interaction | web_chat_with_us | question_id : issue text<br>trip_id : trip id<br>option : text typed by FO |  |
| Profile Flow | FO checks their profile: service score, policies, language and token history.<br>This flow covers the KYC करें tab (MSME is in Coming soon). | Profile | Tab opened | From bottom nav KYC करें | OPERATOR_PROFILE | click | bottom_nav | web_help |  |  |
|  |  |  | Profile viewed | आपकी KYC / गाड़ी KYC steps fire nothing (gap) | my_profile | view |  | web_operator_profile |  |  |
|  |  |  | Score card viewed |  | v1_view_score | view | op_rating_details | web_operator_profile | score : service score (0–100) |  |
|  |  |  | Token card viewed |  | token_active | view | token_card | web_operator_profile |  |  |
|  |  | Score detail | अपने स्कोर को समझे clicked | Score detail fires no view event | v1_understand_score | click | op_rating_details | web_operator_profile | score : service score |  |
|  |  |  | Guideline carousel scrolled | Auto scroll | v1_horiz_scroll | scroll | rating_guidelines | web_rating_details | slide_number : current / total<br>action_type : auto / manual |  |
|  |  | Policies | लोड पॉलिसी clicked | Policy listing fires no view event | load_policy | click | policy_detail | web_operator_profile |  |  |
|  |  |  | Policy clicked | e.g. टोकन रिफंड पॉलिसी | policy_preview | click | policy_detail | web_load_policy | policy : policy name |  |
|  |  |  | Policy page viewed | Event name changes per policy | token_non_refund_policy | view | token_non_refund_policy | web_token_non_refund_policy | op_code : operator code |  |
|  |  |  | मैं पॉलिसी स्वीकार करता हूँ clicked | event_name comes blank (issue) | (blank) | click | policy_acceptance | web_policy_page | op_code : operator code<br>prev_path : OPERATOR_POLICY |  |
|  |  | Language | भाषा बदले clicked | screen_name comes as web_confirm_load on Profile (wrong). आगे बढ़ें fires nothing | edit_lang | click | top_nav | web_confirm_load | cur_lang : current language |  |
|  |  | Token history | टोकन एक्टिव card clicked | Same event name as the view | token_active | click | token_card | web_operator_profile |  |  |
|  |  |  | Token history viewed | टोकन वापस ले (refund) is in Coming soon | token_txn_history | view |  | web_token_txn_history |  |  |
| Confirm Load Flow | Instant confirm of a confirm-type load → vehicle + driver → token payment |  | Coming soon | No confirm-type load on stage during the crawl | Coming soon |  |  |  |  |  |
| Trip Journey Flow | Trip details → reached loading → start trip (bilty OTP) → in transit → unloading → POD → payment |  | Coming soon | Needs stage bilty OTP | Coming soon |  |  |  |  |  |
| Trips – Change Vehicle Flow | गाड़ी नं बदले → reason → vehicle number → saved |  | Coming soon | Vehicle field did not open from the browser; covered by the script run | Coming soon |  |  |  |  |  |
| Token Purchase / Refund Flow | Buy token → payment → token active; टोकन वापस ले → refund |  | Coming soon | Needs payment test mode; refund moves money | Coming soon |  |  |  |  |  |
| Broker / Market Vehicle Flow | Bid with a market (non-own) vehicle |  | Coming soon | Stage vehicles have no GPS | Coming soon |  |  |  |  |  |
| MSME Flow | MSME number, type, certificate photo → saved |  | Coming soon | Needs a real photo upload; page fires no events today | Coming soon |  |  |  |  |  |
| Signup Flow | New number → OTP → profile → KYC |  | Coming soon | Native app screens (needs stage APK) | Coming soon |  |  |  |  |  |
| Login Flow | Number → OTP → Home |  | Coming soon | Native app screens (needs stage APK) | Coming soon |  |  |  |  |  |
| Notification Flow | NotificationStatus / NotificationAction |  | Coming soon | Native push events (needs stage APK or BigQuery) | Coming soon |  |  |  |  |  |
