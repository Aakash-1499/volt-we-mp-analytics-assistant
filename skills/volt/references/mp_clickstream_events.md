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
| Signup | Promotions |  | False |  | v1_offer_signup_screen | view |  | offer_screen | False |  |  | True |  |  |  |
| Signup | Basic Details |  | True |  | v1_basic_details | view |  | sign_up_basic_details | False |  |  | True |  |  |  |
| Signup | Basic Details | Clicks 'Name' field | False |  | v1_enter_name | click |  | sign_up_basic_details | False |  |  | True |  |  |  |
| Signup | Basic Details | Clicks 'Sales Representative' field | False |  | v1_enter_salesrep | click |  | sign_up_basic_details | False |  |  | True |  |  |  |
| Signup | Basic Details | Clicks 'Sales Representative' field | False |  | v1_sales_contact | click |  | sign_up_basic_details | False |  |  | True |  |  |  |
| Signup | Basic Details | Clicks 'Next' button | False |  | v1_next | click |  | sign_up_basic_details | False |  |  | True |  |  |  |
| Signup | Basic Details | Clicks 'Back' arrow | False |  | v1_back | click |  | sign_up_basic_details | False |  |  | True |  |  |  |
| Signup | Business Category |  | True |  | v1_business_category | view |  | sign_up_business_category | False |  |  | True |  |  |  |
| Signup | Business Category | Clicks 'Next' button | False |  | v1_next | click |  | sign_up_business_category | False |  | business_category - id | True |  |  |  |
| Signup | Business Category | Clicks 'Previous' button | False |  | v1_previous | click |  | sign_up_business_category | False |  |  | True |  |  |  |
| Signup | Business Category | Clicks 'Back' arrow | False |  | v1_back | click |  | sign_up_business_category | False |  |  | True |  |  |  |
| Signup | Trip Potential |  | True |  | v1_expected_trip_count | view |  | sign_up_expected_trip_count | False |  |  | True |  |  |  |
| Signup | Trip Potential | Clicks 'Submit' button | False |  | v1_submit | click |  | sign_up_expected_trip_count | False |  | expected_trip_count- id | True |  |  |  |
| Signup | Trip Potential | Clicks 'Previous' button | False |  | v1_previous | click |  | sign_up_expected_trip_count | False |  |  | True |  |  |  |
| Signup | Trip Potential | Clicks 'Back' arrow | False |  | v1_back | click |  | sign_up_expected_trip_count | False |  |  | True |  |  |  |
| Signup | Success |  | True |  | v1_success_bottomsheet | view |  | sign_up_expected_trip_count | False |  |  | True |  |  |  |
| Signup | Insurance Opt in |  | False |  | v1_pricing_type | click | insurance_pricing | insurance | True |  | type:fragile/non-fragile | False |  |  |  |
| Signup | Insurance Opt in |  | False |  | v1_update_pricing | click | Insurance | <dynamic_screen> | True |  |  | False |  |  |  |
| Signup | Insurance Opt in |  | False |  | v1_view_pricing | click | Insurance | <dynamic_screen> | True |  |  | False |  |  |  |
| Signup | Insurance Opt in |  | False |  | v1_confim | click | update_ins_pricing | <dynamic_screen> | True |  |  | False |  |  |  |
| Signup | Insurance Opt in |  | False |  | v1_view_fragile | click | update_ins_pricing | <dynamic_screen> | True |  |  | False |  |  |  |
| Signup | Insurance Opt in |  | False |  | V1_close | click | update_ins_pricing | <dynamic_screen> | True |  |  | False |  |  |  |
| Signup | Insurance Opt in |  | False |  | v1_ok | click | update_ins_pricing | <dynamic_screen> | True |  |  | False |  |  |  |
| Signup | Insurance Opt in |  | False |  | v1_ok | click | fragile_items_list | <dynamic_screen> | True |  |  | False |  |  |  |
| Browsing | Enter Tonnage |  | True | VT Browsing Initiated | v1_tonnage | view |  | tonnage_req_v1 | False |  |  | False |  |  |  |
| Browsing | Enter Tonnage | Clicks tonnage field | False |  | v1_input_wt | click |  | tonnage_req_v1 | False |  |  | False |  |  |  |
| Browsing | Enter Tonnage | Chooses any tonnage option | False |  | v1_choose_wt | click |  | tonnage_req_v1 | False |  |  | False |  |  |  |
| Browsing | Enter Tonnage | Clicks 'I don't know my material weight' button | False |  | v1_dont_know_wt | click |  | tonnage_req_v1 | False |  |  | False |  |  |  |
| Browsing | Enter Tonnage | Clicks 'Submit' button | False |  | v1_submit | click |  | tonnage_req_v1 | False |  | wt | False |  |  |  |
| Browsing | Enter Tonnage | Clicks 'Back' arrow | False |  | v1_back | click | top_nav | tonnage_req_v1 | False |  |  | False |  |  |  |
| Browsing | Enter Tonnage | Clicks 'Edit' button | False |  | v1_edit_add | click | top_nav | tonnage_req_v1 | False |  |  | False |  |  |  |
| Browsing | Enter Tonnage | Clicks 'Add loading' button | False |  | v1_add_loading | click | top_nav | tonnage_req_v1 | False |  |  | False |  |  |  |
| Browsing | Enter Tonnage | Clicks 'Add unloading' button | False |  | v1_add_unloading | click | top_nav | tonnage_req_v1 | False |  |  | False |  |  |  |
| Browsing | VT Browsing |  | True | VT Options Viewed | v1_veh_options | view |  | tonnage_req | False |  |  | False |  |  |  |
| Browsing | VT Browsing | Clicks 'Enter weight' button | False |  | v1_enter_wt | click |  | tonnage_req | False |  |  | False |  |  |  |
| Browsing | VT Browsing | Clicks 'Open/Container/Trailer' options | False |  | v1_body_type | click |  | tonnage_req | False |  | 0 : Open; <br>1 : Container, <br>2 : Trailer | False |  |  |  |
| Browsing | VT Browsing | Clicks any VT card | True |  | v1_veh_opted | click |  | tonnage_req | False |  |  | False |  |  |  |
| Browsing | VT Browsing | Clicks any 'height' choice | True |  | v1_height | click |  | tonnage_req | False |  |  | False |  |  |  |
| Browsing | VT Browsing | Clicks  any special request choice | False |  | v1_spcl_req | click |  | tonnage_req | False |  |  | False |  |  |  |
| Browsing | VT Browsing | Clicks 'Proceed' button | True | Demand Created | v1_cnf_veh | click |  | tonnage_req | False |  | chosen option index | False |  |  |  |
| Browsing | VT Browsing |  | False |  | v1_spcl_req_bottomsheet | view |  | tonnage_req | False |  |  | False |  |  |  |
| Browsing | VT Browsing | Clicks 'Okay, Got it' button | False |  | v1_continue | click | special_req_bottomsheet | tonnage_req | False |  |  | False |  |  |  |
| Browsing | VT Browsing |  | False |  | v1_scroll | view |  | tonnage_req | False |  |  | False |  |  |  |
| Browsing | VT Browsing |  | False |  | v1_veh_unavailable | view |  | tonnage_req | False |  |  | False |  |  |  |
| Browsing | VT Browsing | Clicks 'Change Tonnage' | False |  | v1_change_tonnage | click |  | tonnage_req | False |  |  | False |  |  |  |
| Browsing | VT Browsing |  | False |  | v1_wt_bottomsheet | view | enter_wt_bottomsheet | tonnage_req | False |  |  | False |  |  |  |
| Browsing | VT Browsing | Clicks tonnage in 'Select weight of your goods' | False |  | v1_enter_wt | click | enter_wt_bottomsheet | tonnage_req | False |  |  | False |  |  |  |
| Browsing | VT Browsing | Clicks tonnage option | False |  | v1_choose_wt | click | enter_wt_bottomsheet | tonnage_req | False |  |  | False |  |  |  |
| Browsing | VT Browsing | Clicks 'Submit' | False |  | v1_cnf_wt | click | enter_wt_bottomsheet | tonnage_req | False |  | weight | False |  |  |  |
| Browsing | VT Browsing | Clicks 'Close' button | False |  | v1_close | click | enter_wt_bottomsheet | tonnage_req | False |  |  | False |  |  |  |
| Price Confirmation | Price Range View |  | True |  | v1_demand_price_range | view |  | demand_price_range | True |  |  | False |  |  |  |
| Price Confirmation | Price Range View | Clicks 'Back' button | False |  | v1_back_btn | click | top_nav | demand_price_range | False |  |  | False |  |  |  |
| Price Confirmation | Price Range View | Clicks 'Cancel' button | False |  | v1_cancel | click | top_nav | demand_price_range | False |  |  | False |  |  |  |
| Price Confirmation | Price Range View | Clicks 'Edit' widget | False |  | v1_edit_add | click | top_nav | demand_price_range | False |  |  | False |  |  |  |
| Price Confirmation | Price Range View | Clicks 'Edit' widget | False |  | v1_edit_veh | click | top_nav | demand_price_range | False |  |  | False |  |  |  |
| Price Confirmation | Price Range View | Clicks DR mode option | False |  | v1_mode | click | search_modes | demand_price_range | False |  |  | False |  |  |  |
| Price Confirmation | Price Range View | Clicks 'Next' button | False |  | v1_confirm_btn | click | bottom_nav | demand_price_range | True |  | mode:quick_confirmation/best_price | False |  |  |  |
| Price Confirmation | Loading slot confirmation |  | False |  | v1_loading_slot | view | loading_slot | demand_price_range | True |  |  | False |  |  |  |
| Price Confirmation | Loading slot confirmation | Clicks on loading day from options | False |  | v1_loading_day | click | loading_slot | demand_price_range | True |  | idx:<today/tomorrow | False |  |  |  |
| Price Confirmation | Loading slot confirmation | Clicks on loading time from options | False |  | v1_loading_time | click | loading_slot | demand_price_range | True |  | idx:time_slot | False |  |  |  |
| Price Confirmation | Loading slot confirmation | Clicks on 'Book Now' | False |  | v1_continue_btn | click | bottom_nav | demand_price_range | True |  | dr_slot :<timestamp> | False |  |  |  |
| Price Confirmation |  |  | False |  | v1_dr_stage | view |  | add_loading_unloading | True |  | dr_stage:Loading1/Loading2/Unloading/Insurance | False |  |  |  |
| Price Confirmation | Adding location | Clicks the pointer on map | False |  | v1_map_locate | click | map_view | add_loading_unloading | True |  |  | False |  |  |  |
| Price Confirmation | Adding location | Clicks DR stage:'Loading #1'/'Loading #2','Unloading' | False |  | v1_dr_stage | click | top_nav | add_loading_unloading | True |  | dr_stage:loading1/loading2/unloading/insurance | False |  |  |  |
| Price Confirmation | Adding location | Clicks 'Add via text' or 'Add via location' | False |  | v1_addr_mode | click | top_nav | add_loading_unloading | True |  | entered_via:map/text | False |  |  |  |
| Price Confirmation | Adding location | Clicks 'Enter pincode' textbox | False |  | v1_enter_pincode | click | address_dets | add_loading_unloading | True |  |  | False |  |  |  |
| Price Confirmation | Adding location | Clicks 'Enter full address' textbox | False |  | v1_enter_full_addr | click | address_dets | add_loading_unloading | True |  |  | False |  |  |  |
| Price Confirmation | Adding location | Clicks 'Enter POC number' textbox | False |  | v1_poc_number | click | address_dets | add_loading_unloading | True |  |  | False |  |  |  |
| Price Confirmation | Adding location | Clicks 'Contact' icon | False |  | v1_contact_book | click | address_dets | add_loading_unloading | True |  |  | False |  |  |  |
| Price Confirmation | Adding location | Ticks 'Use my contact'  checkbox | False |  | v1_use_my_contact | click | address_dets | add_loading_unloading | True |  |  | False |  |  |  |
| Price Confirmation | Adding location | Clicks 'POC Name' textbox | False |  | v1_poc_name | click | address_dets | add_loading_unloading | True |  |  | False |  |  |  |
| Price Confirmation | Adding location | Clicks one of the saved address options | False |  | v1_saved_addr | click | address_dets | add_loading_unloading | True |  | addr_choice:Warehouse1/Warehouse2::type:<LOADING/CONSIGNEE> | False |  |  |  |
| Price Confirmation |  | Clicks 'Submit Loading Address' or 'Submit Unloading Address' | False |  | v1_confirm_btn | click | bottom_nav | add_loading_unloading | True |  | entered_via:map/text::action:<Loading/Unloading/Unloading#2/Insurance> | False |  |  |  |
| Fulfilment |  | Clicks DR stage:'Loading #1'/'Loading #2','Unloading' | False |  | v1_dr_stage | view |  | unloading | True |  | unloading/insurance::timer:xx | False |  |  |  |
| Fulfilment |  | Clicks 'Enter pincode' textbox | False |  | v1_enter_pincode | click |  | unloading | True |  |  | False |  |  |  |
| Fulfilment |  | Clicks 'Enter full address' textbox | False |  | v1_enter_full_addr | click |  | unloading | True |  | timer:xx | False |  |  |  |
| Fulfilment |  | Clicks 'Enter POC number' textbox | False |  | v1_poc_number | click |  | unloading | True |  |  | False |  |  |  |
| Fulfilment |  | Clicks 'Contact' icon | False |  | v1_contact_book | click |  | unloading | True |  |  | False |  |  |  |
| Fulfilment |  | Ticks 'Use my contact'  checkbox | False |  | v1_use_my_contact | click |  | unloading | True |  |  | False |  |  |  |
| Fulfilment |  | Clicks 'POC Name' textbox | False |  | v1_poc_name | click |  | unloading | True |  |  | False |  |  |  |
| Fulfilment |  | Clicks one of the saved address options | False |  | v1_saved_addr | click |  | unloading | True |  | addr_choice:warehouse1/warehouse2/other::timer:xx | False |  |  |  |
| Fulfilment |  | Clicks 'Submit Unloading Address #1' | False |  | v1_confirm_btn | click |  | unloading | True |  | action:unloading | False |  |  |  |
| Fulfilment |  |  | False |  | v1_going_to_load | view |  | going_to_load | True |  |  | False |  |  |  |
| Fulfilment |  |  | False |  | v1_cancel_bot | view |  | going_to_load | True |  |  | False |  |  |  |
| Fulfilment |  |  | False |  | v1_continue | click |  | going_to_load | True |  |  | False |  |  |  |
| Fulfilment |  |  | False |  | v1_view_details_btn | click |  | going_to_load | True |  | expensetype:cancellation | False |  |  |  |
| Fulfilment |  |  | False |  | v1_cancel_fee_btmsheet | view |  | going_to_load | True |  |  | False |  |  |  |
| Fulfilment |  |  | False |  | v1_raise_issue | click |  | going_to_load | True |  |  | False |  |  |  |
| Fulfilment |  |  | False |  | v1_cancel_bot | view | cancel_bot | going_to_load | True |  |  | False |  |  |  |
| Fulfilment |  |  | False |  | v1_continue | click | cancel_bot | going_to_load | True |  | searchmode,final_price,time,action<cancel/keep_truck/want_better_price | False |  |  |  |
| Fulfilment |  |  | False |  | v1_truck_on_hold | view | Post_plc_educate | scheduled | True |  |  | False |  |  |  |
| Fulfilment |  |  | False |  | v1_accept | click | conf_cancel_bottomsheet | scheduled | True |  |  | False |  |  |  |
| Fulfilment |  |  | False |  | v1_cancel | click | conf_cancel_bottomsheet | scheduled | True |  |  | False |  |  |  |
| Fulfilment |  |  | False |  | v1_reschedule | click |  | scheduled | True |  |  | False |  |  |  |
| Fulfilment |  |  | False |  | v1_cancel_fee_accept | view |  | scheduled | True |  |  | False |  |  |  |
| Fulfilment |  | Clicks 'I agree and accept the truck' | False |  | v1_confirm_truck | click |  | scheduled | True |  |  | False |  |  |  |
| Fulfilment |  |  | False |  | v1_scheduled_preview | view | confirm_demand | scheduled_preview | True |  | timer:xx  (in secs) | False |  |  |  |
| Fulfilment |  |  | False |  | v1_view_details | click |  | scheduled_preview | True |  |  | False |  |  |  |
| Fulfilment |  |  | False |  | v1_view_pricing | click | insurance | scheduled_preview | True |  |  | False |  |  |  |
| Fulfilment |  |  | False |  | v1_insurance_btmsheet | view |  | scheduled_preview | True |  |  | False |  |  |  |
| Fulfilment |  |  | False |  | v1_add_insurance | click | insurance | scheduled_preview | True |  |  | False |  |  |  |
| Fulfilment |  |  | False |  | v1_edit_btn | click | trip_details | scheduled_preview | True |  |  | False |  |  |  |
| Fulfilment |  |  | False |  | v1_reschedule | click |  | scheduled_preview | True |  |  | False |  |  |  |
| Fulfilment |  |  | False |  | v1_cancel_booking | click |  | scheduled_preview | True |  |  | False |  |  |  |
| Fulfilment |  |  | False |  | v1_confirm_details | click | v1_confirm_details | scheduled_preview | True |  |  | False |  |  |  |
| Fulfilment |  |  | False |  | v1_confirm_truck | click |  | scheduled_preview | True |  |  | False |  |  |  |
| Fulfilment |  |  | False |  | v1_tnc | view |  | scheduled_preview | True |  |  | False |  |  |  |
| Fulfilment |  |  | False |  | v1_confirm_detail_warning | view |  | scheduled_preview | True |  |  | False |  |  |  |
| Fulfilment |  |  | False |  | v1_cancel_bot | view |  | scheduled_preview | True |  |  | False |  |  |  |
| Fulfilment |  |  | False |  | v1_continue | click |  | scheduled_preview | True |  |  | False |  |  |  |
| Fulfilment |  |  | False |  | v1_close | click |  | scheduled_preview | True |  |  | False |  |  |  |
| Fulfilment |  |  | False |  | v1_unlock_discount | click |  | scheduled_preview | True |  |  | False |  |  |  |
| Fulfilment |  |  | False |  | v1_extra_charge_policy | view |  | scheduled_preview | True |  |  | False |  |  |  |
| Fulfilment |  |  | False |  | v1_extra_charge_policy | click |  | scheduled_preview | True |  |  | False |  |  |  |
| Fulfilment |  |  | False |  | v1_remove_pricing | click | insurance | scheduled_preview | True |  |  | False |  |  |  |
| Fulfilment |  |  | False |  | v1_insurance_btmsheet | view |  | scheduled_preview | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  | At Loading | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  | Trip Started | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  | At Unloading | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  | Trip Completed | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |
|  |  |  | False |  |  |  |  |  | False |  |  | False |  |  |  |

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
