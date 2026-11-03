# FTL Stakeholder Vocabulary → Canonical Mapping

Stakeholders at Wheelseye use a lot of internal shorthand and Hinglish phrasing. Map their words to the canonical tables/columns/metrics before doing anything else. The goal here is to remove ambiguity at the start so the rest of the workflow does not waste cycles asking the wrong question of the wrong table.

If the stakeholder uses a term not in this list, ask them to clarify — don't guess.

## Entities

| **Stakeholder says…** | **Canonical** | **Likely table** |
| --- | --- | --- |
| FO, operator, fleet operator, driver, supply, trucker | operator_code | fact_operators_mp_events, fact_operators_onb, fact_vehicle_info, dim_operator_base_district |
| Cx, customer, consigner, shipper, demand-side, payer | consigner_user_code | fact_consigner_demands_lead_source |
| Demand, indent, freight request, load | demand_id | fact_consigner_demands_lead_source |
| Vehicle, truck, tipper, container | vehicle_id | fact_vehicle_info |
| Opsearch, supply depth, FOs within 120km, notification pool | demand_id (summary) / demand_id+operator_code (per-FO) | fact_demand_opsearch_summary, fact_demand_opsearch_operator_summary |
| Bid, token, token paid, token refund/forfeit | demand_id+operator_code | fact_operator_tokens |
| Rating, service quality, delivery delay, GTL delay, damage | demand_id | fact_consigner_service_stats |

## Funnel stages (FO side)

| **Stakeholder says…** | **Canonical column / flag** | **Metric this enables** |
| --- | --- | --- |
| Visitor, landed FO, came to MP, opened marketplace | landed_on_mp = 1 | # Visitors |
| Browsed, opened a load, viewed LDP, checked load detail | is_checked_loads > 0 | # LDP FO |
| Ready FO, onboarded FO, validated vehicle and lane | ready_fo = 1 (events fact) or mp_status = 'MP Ready' AND ready_date IS NOT NULL (onb fact) | # Ready FO |
| Paid token, plc, placed, placement | is_token_paid > 0 (FO-side) or plc_flag = 1 (Cx-side) | # Token Paid FO / % Plc FO |
| Trip, tripped, completed trip | total_trips_loads > 0 (FO-side) or trip_flag = 1 (Cx-side) | # Trip FO / % Trip FO |
| Subscribed, Subs, paying, premium | is_subscribed_at_event = 1 or fo_sub_type = 'Subs' (events); has_sub = 1, sub_date IS NOT NULL (onb) | # Subscribed FOs |
| Bid, submitted bid, bidding | count_of_loads_bid_submit > 0 | % Bid Feature FO |
| Marked VA, vehicle available, available, "I'm free" | is_marked_veh_available = 1 | % Vehicle Available |
| Not available, blocked, busy | is_marked_veh_not_available = 1 | (denominator-side) |
| Used filter, ODVT filter, origin filter, destination filter | is_loading_filter_used = 1 OR is_unloading_filter_used = 1 | % ODVT Filter FO |
| Matching, found a match, qualified in matching | is_checked_loads_matching > 0 | % Matching Feature FO |
| Reverse trip, return leg | reverse_loads_trips = 1 | % Reverse Trip FO |
| Acquired, new FO with first trip, just-acquired | trips_till_date > 0 at the FO's first event_date with that condition | # Acquired FOs |
| Retained, 2nd trip, 3+ trips | trips_till_date > 1 (2nd trip) or > 3 / trip_bucket = '3+' (retained) | # Acquired FOs - 2nd Trip / Retained cohort |
| Churned, lapsed, stopped tripping | Trip FO with last trip > 1 month before today | Churned FOs |

### FO segment (fo_segment)

Stakeholders segment FOs by lifetime trip count using fo_segment (derived from trips_till_date). Per the ODS glossary the values are:

- **"0"** → 0 trips (new / not yet acquired)
- **"1-2"** → 1st or 2nd trip (early retention)
- **"2+"** → more than 2 trips (fully retained) Use as a split / cohort filter on FO-Growth and FO-Exp metrics. (Note: trip_bucket is a separate, similar column with values '0' / '1-2' / '3+'.)

## Funnel stages (Cx side / Placement)

| **Stakeholder says…** | **Canonical** | **Metric** |
| --- | --- | --- |
| Demand, request, indent | demand_id with no flag filter | # Demands |
| DR, Demand Record, routed demand, made-it-into-the-pipeline | dr_flag = 1 | # DRs / % Demand to DR |
| Placed, plc | plc_flag = 1 | # Plc / % DR to Plc |
| Trip, fulfilled, completed | trip_flag = 1 | # Trips / % Demand to Trip |
| Auto trip, system-placed, auto plc | auto_plc = 'YES' AND trip_flag = 1 | % Auto Trips |
| Right demand, valid demand, matchable | right_demand = 1 | (filter) |
| Cancel within 30 min, quick regret, cx_plc_cancel | plc_flag=1 AND trip_flag=0 AND datediff('minute', last_plc_time, cx_plc_cancel_time) <= 30 | % Cancellations (<30 mins) |
| GTL, accepted, going to load | WFMS state = 'GOING_TO_LOAD' | % GTL Cancellations, % Plc to Acceptance, % Acceptance to Trip |

## Geography

| **Stakeholder says…** | **Canonical** |
| --- | --- |
| NCR, Delhi NCR | demand_region = 'NCR' (FO side: use the "FO State, cluster, district, region" metric — fo_base_region is Do Not Use) |
| ROI, rest of India | demand_region = 'ROI' |
| Others, OTHERS region | demand_region NOT IN ('NCR','ROI') |
| State (Maharashtra / Gujarat / Karnataka etc) | demand_state or consigner_state; FO side → FO geography metric (via dim_operator_base_district → dim_mp_districts) |
| Cluster | demand_cluster / cluster_id (⛔ sales_cluster is Do Not Use) |
| Origin, source, "from city" | origin_id / demand_city |
| Destination, "to city", drop | destination_id / destination_city |
| Lane | concat of origin → destination — use demand_origin + demand_destination separately (⛔ demand_lane is Do Not Use) |

## Sales hierarchy

| **Stakeholder says…** | **Canonical** |
| --- | --- |
| Sales team, IS / FS | assigned_sales_team (canonical) = INSIDE SALES / FIELD SALES / NOT ASSIGNED |
| Sub-team, onboarding team, retention team | assigned_sales_sub_team = ONBOARDING / RETENTION / NOT ASSIGNED |
| Manager | assigned_manager |
| ASM, SM | ⛔ assigned_manager_designation is Do Not Use — no canonical replacement |
| ZSM | ⛔ assigned_zsm / assigned_zsm_email are Do Not Use — no canonical replacement |
| RH, Regional Head | ⛔ assigned_rh is Do Not Use — no canonical replacement |
| First sales team (original assignment) | ⛔ first_sales_team is Do Not Use — use assigned_sales_team |
| Should-be sales team | ⛔ relevant_sales_team is Do Not Use — use assigned_sales_team |

## Pricing & money

| **Stakeholder says…** | **Canonical** |
| --- | --- |
| Base price, fare to FO | base_price |
| L1 / L2 / L3 fare, base rate | base_rate1 / base_rate2 / base_rate3 |
| Consigner fare, Cx freight, freight quoted | consigner_freight_fare |
| P&L, net P&L | pnl (realised) / pnl_expected (pre-cost) |
| Net Take Rate, Net TR | % Net Take Rate metric |
| Gross Take Rate, Gross TR | % Gross Take Rate metric |
| Plc price range, price bucket | plc_price_range |
| Receivable | receivable_before_settlement (gross) / final_receivable_amount (net) |
| Pending, outstanding | demand_pending_balance (per demand), customer_overall_pending (per customer) |
| Overdue | customer_overdue_pending, days_since_due > 0 |
| Bid amount, opfreight | opfreight (fact_operator_tokens) |
| Token amount / refund | amount_in_paisa / refund_amount_in_paisa (fact_operator_tokens, in paisa) |

## Payments / Credit / NPA

| **Stakeholder says…** | **Canonical** |
| --- | --- |
| Recovery, collected | recovered_within_X_days columns |
| Recovered on time, before due | recovered_within_due_date |
| Recovered within 7 / 15 / 30 / 60 / 90 / 180 days | recovered_within_7_days etc. |
| DSO | demand_dso |
| Days since due, overdue days | days_since_due |
| NPA | demand_gross_npa (≥90d cohort) and demand_net_npa (≥180d cohort) |
| Bad loan, write-off, settlement | npa_settlement_amount, npa_operational_amount |
| Credit cost | demand_credit_cost |
| Discount given to consigner | payment_discount |
| Payment mode fee, our fee revenue | payment_mode_fee |
| Delay fee, late fee, delay charger | delay_amount (% Delay Charges metric — note: dashboard typo says "Chargers") |
| KYC for credit, credit KYC | credit_kyc_flag, credit_kyc_status, kyc_completed_time |
| Cream Cx, top-tier | cream_flag = 1 |
| Restricted, blocked Cx | account_restriction_status = 'RESTRICTED' |
| Billing mode, payment plan, advance, postpaid 15, postpaid 30 | billing_submode (raw code) → maps to human-readable via CASE WHEN. See Payment Plan Usage metric for the full mapping. |
| Bank credit | billing_submode ILIKE '%F%' (= 'Bank' in human-readable) |
| Pay at Loading (PAL), Pay at Unloading (PAU / Paul) | billing_submode ILIKE '%A%' (PAL) / '%C%' (PAU) |
| 60-day credit / 30-day credit / 15-day credit | billing_submode value-set; W4/W8/WT30/WW30 → '30-37 Days Credit', W9/WT60/WW60 → '60-67 Days Credit', etc. |
| To-Pay, consignee pays | topay_flag = 1 |
| GST, FCM, RCM | gst_type, gst_number, gst_amount |
| Wallet | wallet_balance, last_wallet_entry |

## Token / bid status (fact_operator_tokens)

| **Stakeholder says…** | **Canonical** |
| --- | --- |
| Bid submitted, entered price | row with opfreight non-empty (status = 'INITIATED' before token) |
| Token paid | status = 'SUCCESS' |
| Token refunded (didn't convert) | status = 'REFUNDED' |
| Forfeited (won bid but backed out) | status = 'FORFEITED' |
| Bid expired (no token) | status = 'EXPIRED' |
| Matching flow (took shown price) vs Bidding flow (own price) | flow = 'MATCHING' / flow = 'BIDDING' |

## Service quality (fact_consigner_service_stats)

| **Stakeholder says…** | **Canonical** |
| --- | --- |
| Rating, stars | rating (1–5) |
| Rating reasons | reasons |
| Pickup delay, gate-to-loading delay | gtl_delay |
| Delivery / transit delay, in_tat / delay / critical | sys_trnst_dly |
| Vehicle offline / untracked time | total_offline_time |
| Damage | type (damage type) |

## Cohorts & segments

| **Stakeholder says…** | **Canonical** |
| --- | --- |
| Onboarding cohort, new Cx, 0-trip Cx | cx_segment = 'New' OR trip_rank <= 4 (depending on which dashboard); also see cx_segment Signup/Repeat/Unactivated/Dormant classification |
| Retention cohort, repeat Cx | cx_segment = '4+' OR trip_rank > 4 (Payment POD uses trip_rank > 4) |
| Dormant Cx, lapsed, 90-day inactive | cx_segment = 'Dormant' (monthly classification — last trip > 90 days before given month) |
| FS, FS Cx | Sales team = 'FIELD SALES' |
| IS, IS Cx | Sales team = 'INSIDE SALES' |

## Time terminology

| **Stakeholder says…** | **Canonical** |
| --- | --- |
| DoD, day-on-day | timeframe_type / Interval = 'Day' |
| WoW, week-on-week | 'Week' |
| MoM, month-on-month | 'Month' |
| Cumulative, lifetime | View_Type = 'Cumulative' (or use _till_date / life_time_ columns) |
| Period, in-period | View_Type = 'Normal' |
| Hourly, today's pacing, intra-day | Hourly tab on Placement Overview (mp_demand_details source, not the canonical fact) |

## Common shorthand / typos / Hinglish

| **You'll see…** | **Read as** |
| --- | --- |
| "plc" | placement |
| "Cx" | consigner / customer |
| "FO" | fleet operator (supply side) |
| "OB" | Onboarding |
| "RT" | Retention |
| "Plc Cx" / "placed Cx" | consigner whose demand was placed |
| "Trip Cx" / "Tripping Cx" | consigner whose demand became a trip |
| "DR drop" / "DR cancel" | DR cancelled before placement |
| "kyc nahi hua" / "no kyc" | credit_kyc_status != 'Approved' |
| "limit khatam" / "credit limit exhausted" | account_restriction_status = 'RESTRICTED' AND account_restriction_substatus = 'OVERDUE_LIMIT' |
| "VA mark", "marked VA" | Vehicle Available marked |
| "GTL", "GTL ho gaya" | Going-to-Load state in WFMS (= driver accepted) |
| "Token paid", "token kar diya" | is_token_paid > 0 |
| "Acquired" | first trip done |
| "Drop off", "leakage" | conversion gap between funnel stages |
| "Chargers" | dashboard typo for Charges — read as "delay charges" |
| "Paul" | Pay At Unloading (PAU). Sometimes a typo, sometimes deliberate shorthand. |
| "L2 fare" / "L2 price" | base_rate2 |

## Region rollouts (cohort start dates to remember)

| **Region** | **Start date** | **Notes** |
| --- | --- | --- |
| NCR | 2025-12-01 | North Star base |
| ROI | 2025-12-01 | covers most of India |
| ROI:2 | 2025-12-09 | Mumbai / Pune / Bengaluru / Gujarat etc. expansion |
| ROI:3 | 2025-12-18 | Jaipur / Hyderabad expansion |
| OTHERS | (default) | everything else |

If a stakeholder asks about a region for a period before its rollout date, that's zero by construction — not a real zero. Always call this out.

# PTL Stakeholder Vocabulary → Canonical Mapping

Companion to mp_vocabulary (FTL). Map stakeholder words about PTL (part truck load / part load) to canonical tables, columns and metrics before doing anything else. If the stakeholder uses a PTL term not in this list, ask them to clarify — don't guess. Do not transfer FTL meanings (DR, ODVT, plc_flag, opsearch) to PTL.

## Entities

| **Stakeholder says…** | **Canonical** | **Likely table** |
| --- | --- | --- |
| Cx, customer, consigner, shipper (PTL) | consigner_user_code | fact_ptl_requirements, fact_ptl_bookings |
| Price check, rate check, quote, API call, re-quote | browsing_id (one rate-API call; includes automatic re-quotes, so rows ≠ searches) | fact_ptl_browsing, fact_ptl_requirements |
| Price search, PTL requirement, real search, shipment need | requirement_flag = 1 (consigner × lane, price checks grouped with < 30 min gap, ≥1 change from prefill or continue event) | fact_ptl_requirements |
| PTL demand, booking request | demand_id (real only: demand_id not like 'B/%' and demand_id <> '') | fact_ptl_requirements, fact_ptl_bookings |
| Would-be demand, backfilled demand | demand_id = 'B/<browsing_id>' (demand the old flow never created) | fact_ptl_requirements |
| Manual demand, ODIN demand, ops-created demand | browsing_id = 'D/<demand_id>', channel = 'ODIN' | fact_ptl_requirements |
| PTL demand / trip / SLA detail | demand_id (bigint) | fact_ptl_bookings |
| Payment | demand_id | mp_analytics_core.as_trip_payments |

## Funnel stages (PTL)

| **Stakeholder says…** | **Canonical column / flag** | **Metric this enables** |
| --- | --- | --- |
| Price checks (raw), API calls | count(distinct browsing_id) excluding D/ rows | # Price checks |
| Price search, requirements, # Price Search | sum(requirement_flag) (⛔ never count(*); rows ≈ 3x requirements) | # Price Search / # Price Search Cx |
| Demand, demand created | demand_flag = 1 (includes would-be); for conversion add use_for_demand_funnel = 1 | # Demands / % Price Search to Demand |
| Booked, booking, placed, plc | placement_flag = 1 (booked) | # Bookings (alias # Placements) / % Price Search to Booking |
| Payment | demand_pending_balance=final_receivable_amount + overall_received_amount (since overall_received_amount is stored as negative value) | # payment_received |
| Picked up, pickup done, PTL acquired | pickup_flag = 1 (pickup_done_time not null) | # Pickups / PTL acquisition |
| Trip, tripped | trip_flag = 1 (pickup / in-transit / trip-end, not cancelled or expired) | # Trips |
| Delivered, trip ended | delivered_flag = 1 (trip_end_time not null) | # Delivered |

Funnel flags (placement, pickup, trip, delivered) have no recency window: exclude the last 7–14 days or read the latest period as immature. Exclude channel = 'BULK_UPLOAD' from conversion rates.

## Channels

| **Stakeholder says…** | **Canonical** |
| --- | --- |
| App, Book Truck app, Part Load tab, consigner web, app web | channel = 'APP' (Android, iOS and consigner web) |
| Consigner web | fact_ptl_bookings.app_platform = 'CONSIGNER_WEB'; events event_platform in ('web','mweb') |
| PTL portal | channel = 'WEB PORTAL'; events event_platform = '' with consigner in payload "uc":"WE…". ⛔ Not the same as consigner web |
| ODIN, manual, ops entry | channel = 'ODIN' |
| Bulk upload | channel = 'BULK_UPLOAD' (from 15 Oct 2026; volume only, not conversion) |

## Experiments & cohorts

| **Stakeholder says…** | **Canonical** |
| --- | --- |
| PTL live, SHOW, test arm, PTL-enabled | fact_experiment_user_allocation.variant_id = 17 and deleted = false |
| Control, DISABLE, FTL-only arm | variant_id = 18 and deleted = false |
| Payment flow test | variant_id 36 = PTL_DEFAULT_PAYMENT_FLOW / 37 = PTL_DIVIDE_PAYMENT_FLOW(pay at booking is live) |
| Browsing flow test | variant_id 44 = PTL_BROWSING_FLOW_DEFAULT / 45 = PTL_BROWSING_FLOW_V2 |
| flow_type_config_id | ⛔ Does not exist on the table — use variant_id |
| deleted = true | PTL is NOT shown to that consigner — not live |

## Geography

| **Stakeholder says…** | **Canonical** |
| --- | --- |
| Region, NCR / R1 / R2 / R3 | fact_consigner_demands_lead_source.consigner_region = NCR / R1 (TOP 5 CLUSTERS) / R2 (NEXT 24 CLUSTERS) / R3 (ROI); fallback mp_analytics_core.dim_consigners consigner_region |
| Lane, route | loading_pincode + unloading_pincode (fact_ptl_bookings) |
| City (PTL or FTL) | Map from pincode via mp_analytics_sandbox.as_vibheeshan_city_pincodes (deleted = false). ⛔ Never string-match FTL district names to PTL city names |

## Consigner history & acquisition

| **Stakeholder says…** | **Canonical** |
| --- | --- |
| PTL acquisition, PTL acquired, first PTL trip | Acquisition_date_ptl Mp_analytics_core.dim_consigners<br>Fallback : (fact_ptl_bookings / pickup_flag) |
| acquisition_date_ptl | Acquisition_date_ptl Mp_analytics_core.dim_consigners |
| FTL acquired, first FTL trip, already an FTL customer | dim_consigners.acquisition_date_ftl (FTL only, history from 2019) |
| first_trip_date | ⛔ Not "first FTL trip" — covers any load type (PTL-only consigners get their PTL date) |
| FTL trips / demands | fact_demands where load_type = 'FTL' (from Oct 2025) or fact_consigner_demands_lead_source trip_flag = 1 (from Jan 2024). |
| Lifetime / last trip by load type | lifetime_trips_ftl / lifetime_trips_ptl, last_trip_date_ftl / last_trip_date_ptl, has_tripped_ftl / has_tripped_ptl (dim_consigners) |
| Recency, active, last seen | max(login_date) from fact_consigner_demands_lead_source. ⛔ fact_cx_events_l3m (rolling 3-month window) |
| Business category, manufacturer / trader | cx_business_category (the PTL targeting signal; app_potential predicts FTL, not PTL) |

## App events (fact_cx_events_l24m)

| **Stakeholder says…** | **Canonical** |
| --- | --- |
| Landed on PTL, opened Part Load | v1_ptl_home_page — count distinct users / user-days (double-fires) |
| Saw rates, rate screen, transporter list | v1_ptl_estimate_rate (screen ptl_select_transporter) |
| Tapped a transporter card | v1_ptl_select_transporter (payload tpt:<name>) |
| Continue from transporter list, app would-be demand | v1_ptl_submit with miscellaneous containing tpt. ⛔ screen_name alone (overstates ~8x) |
| Rate request | v1_ptl_submit with ::st: in payload |
| Create pickup request (web portal) | v1_create_prq (web portal would-be demand) |
| Book tapped | v1_ptl_book (payload carries demandid) |
| Tutorial banner seen | v1_ptl_tutorial_view (from 15 Sep 2026) |
| pcId | = fact_ptl_browsing.browsing_id; parse regexp_substr(miscellaneous,'pcid[^0-9]*([0-9]+)',1,1,'ie') |
| "all PTL events" | ⛔ Never event_name ilike '%ptl%' — catches the PTL tab firing on the FTL home page |

## Time terminology

| **Stakeholder says…** | **Canonical** |
| --- | --- |
| Event time | UTC epoch microseconds (fact_cx_events_*) |
| Price-check / demand / trip time | price_check_time, demand_time, trip_end_time are IST (+5.5 h vs events) |
| Data freshness, data upto | max(data_upto) on fact_ptl_requirements; max(demand_time) on fact_ptl_bookings |
| By day 30, within N days | Always state the observation window; use matured cohorts only |

## Common shorthand / Hinglish

| **You'll see…** | **Read as** |
| --- | --- |
| "PTL", "part load" | part truck load |
| "FTL", "full truck" | full truck load (core MP business) |
| "TPT" | transporter (PTL supply; not an FO) |
| "D2D" / "W2W" / "D2W" / "W2D" | service type: door/warehouse at pickup to door/warehouse at drop (payload st) |
| "PRQ" | pickup request (web portal v1_create_prq) |
| "ODIN" | ops tool for manual demands |
| "B/…" / "D/…" ids | would-be demand / manual-demand row in fact_ptl_requirements |
| "price search" vs "price check" | requirement (deduped) vs raw rate-API row |

## PTL timeline (dates to remember)

If a stakeholder asks about a period before the relevant date, a zero is by construction — not a real zero. Always call this out.

| **Event** | **Date** | **Notes** |
| --- | --- | --- |
| fact_demands (FTL) start | 2025-10-01 | earlier FTL history in lead_source (Jan 2024) / dim_consigners |
| fact_ptl_requirements start | 2026-01-01 | first price check in the table |
| NCR retention test exposure | 2026-05-01 | SHOW vs DISABLE on the NCR FTL-retention base |
| New booking flow | ~2026-05-22 | booking-flow events exist only from here |
| Consigner web PTL events | 2026-06 | event_platform web / mweb |
| Booking widget on PTL home | 2026-08-01 | lane input moved to ptl_home_page |
| Tutorial banner | 2026-09-15 | v1_ptl_tutorial_view |
| Bulk upload channel | 2026-10-15 | channel = 'BULK_UPLOAD' |
| Web portal new-flow cutover | 2026-10-16 15:48 IST | portal demand created at Create Pickup Request |
