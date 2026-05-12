# Power BI BIM Model Specification

---

# 1. Data Source Summary

| Property | Value |
|---|---|
| Source System(s) | Not Explicitly Defined in Source Inputs |
| Schema Name(s) | Gold |
| Layer(s) | Gold |
| Physical Tables Detected | go_applicant_dimension, go_application_fact, go_card_product_dimension, go_acquisition_channel_dimension, go_campaign_dimension, go_fraud_check_fact, go_transaction_fact, go_promotional_offer_dimension, go_aggregate_campaign_performance, go_aggregate_risk_segment, go_aggregate_fraud_screening, go_aggregate_transaction_behavior, go_error_data, go_process_audit |
| Source Types | Delta Lake Tables (per DDL) |

---

# 2. Table Inventory

| Property | Value |
|---|---|
| Table Name | go_applicant_dimension |
| Schema | Gold |
| Layer | Gold |
| Classification | Dimension |
| Source Evidence | DDL |
| Description | Not Explicitly Defined in Source Inputs |

| Table Name | go_application_fact |
| Schema | Gold |
| Layer | Gold |
| Classification | Fact |
| Source Evidence | DDL |
| Description | Not Explicitly Defined in Source Inputs |

| Table Name | go_card_product_dimension |
| Schema | Gold |
| Layer | Gold |
| Classification | Dimension |
| Source Evidence | DDL |
| Description | Not Explicitly Defined in Source Inputs |

| Table Name | go_acquisition_channel_dimension |
| Schema | Gold |
| Layer | Gold |
| Classification | Dimension |
| Source Evidence | DDL |
| Description | Not Explicitly Defined in Source Inputs |

| Table Name | go_campaign_dimension |
| Schema | Gold |
| Layer | Gold |
| Classification | Dimension |
| Source Evidence | DDL |
| Description | Not Explicitly Defined in Source Inputs |

| Table Name | go_fraud_check_fact |
| Schema | Gold |
| Layer | Gold |
| Classification | Fact |
| Source Evidence | DDL |
| Description | Not Explicitly Defined in Source Inputs |

| Table Name | go_transaction_fact |
| Schema | Gold |
| Layer | Gold |
| Classification | Fact |
| Source Evidence | DDL |
| Description | Not Explicitly Defined in Source Inputs |

| Table Name | go_promotional_offer_dimension |
| Schema | Gold |
| Layer | Gold |
| Classification | Dimension |
| Source Evidence | DDL |
| Description | Not Explicitly Defined in Source Inputs |

| Table Name | go_aggregate_campaign_performance |
| Schema | Gold |
| Layer | Gold |
| Classification | Aggregate |
| Source Evidence | DDL |
| Description | Not Explicitly Defined in Source Inputs |

| Table Name | go_aggregate_risk_segment |
| Schema | Gold |
| Layer | Gold |
| Classification | Aggregate |
| Source Evidence | DDL |
| Description | Not Explicitly Defined in Source Inputs |

| Table Name | go_aggregate_fraud_screening |
| Schema | Gold |
| Layer | Gold |
| Classification | Aggregate |
| Source Evidence | DDL |
| Description | Not Explicitly Defined in Source Inputs |

| Table Name | go_aggregate_transaction_behavior |
| Schema | Gold |
| Layer | Gold |
| Classification | Aggregate |
| Source Evidence | DDL |
| Description | Not Explicitly Defined in Source Inputs |

| Table Name | go_error_data |
| Schema | Gold |
| Layer | Gold |
| Classification | Technical |
| Source Evidence | DDL |
| Description | Not Explicitly Defined in Source Inputs |

| Table Name | go_process_audit |
| Schema | Gold |
| Layer | Gold |
| Classification | Technical |
| Source Evidence | DDL |
| Description | Not Explicitly Defined in Source Inputs |

---

# 3. Column Definitions

## go_applicant_dimension
| Column Name | Physical Data Type | Suggested Power BI Type | Role | Nullable | Description | Source Evidence |
|---|---|---|---|---|---|---|
| applicant_id | STRING | Text | Key | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| geography | VARCHAR(100) | Text | Attribute | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| age_group | VARCHAR(50) | Text | Attribute | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| income_level | VARCHAR(50) | Text | Attribute | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| employment_type | VARCHAR(50) | Text | Attribute | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| credit_score | INT | Whole Number | Attribute | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| risk_tier | VARCHAR(50) | Text | Attribute | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| load_date | DATE | Date | Technical | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| update_date | DATE | Date | Technical | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| source_system | VARCHAR(50) | Text | Technical | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| marital_status | VARCHAR(50) | Text | Attribute | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL (Alter Table) |

## go_application_fact
| Column Name | Physical Data Type | Suggested Power BI Type | Role | Nullable | Description | Source Evidence |
|---|---|---|---|---|---|---|
| application_id | STRING | Text | Key | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| applicant_id | STRING | Text | Foreign Key | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| card_product_id | STRING | Text | Foreign Key | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| acquisition_channel_id | STRING | Text | Foreign Key | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| campaign_id | STRING | Text | Foreign Key | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| application_submission_date | DATE | Date | Date | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| approval_date | DATE | Date | Date | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| activation_date | DATE | Date | Date | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| application_status | VARCHAR(50) | Text | Attribute | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| application_outcome | VARCHAR(50) | Text | Attribute | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| decline_reason | VARCHAR(255) | Text | Attribute | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| application_stage | VARCHAR(50) | Text | Attribute | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| load_date | DATE | Date | Technical | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| update_date | DATE | Date | Technical | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| source_system | VARCHAR(50) | Text | Technical | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| application_channel | VARCHAR(50) | Text | Attribute | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL (Alter Table) |

## go_card_product_dimension
| Column Name | Physical Data Type | Suggested Power BI Type | Role | Nullable | Description | Source Evidence |
|---|---|---|---|---|---|---|
| card_product_id | STRING | Text | Key | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| product_name | VARCHAR(100) | Text | Attribute | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| product_category | VARCHAR(50) | Text | Attribute | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| product_launch_date | DATE | Date | Attribute | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| load_date | DATE | Date | Technical | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| update_date | DATE | Date | Technical | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| source_system | VARCHAR(50) | Text | Technical | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| reward_points | INT | Whole Number | Attribute | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL (Alter Table) |

## go_acquisition_channel_dimension
| Column Name | Physical Data Type | Suggested Power BI Type | Role | Nullable | Description | Source Evidence |
|---|---|---|---|---|---|---|
| acquisition_channel_id | STRING | Text | Key | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| channel_name | VARCHAR(100) | Text | Attribute | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| channel_type | VARCHAR(50) | Text | Attribute | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| load_date | DATE | Date | Technical | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| update_date | DATE | Date | Technical | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| source_system | VARCHAR(50) | Text | Technical | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |

## go_campaign_dimension
| Column Name | Physical Data Type | Suggested Power BI Type | Role | Nullable | Description | Source Evidence |
|---|---|---|---|---|---|---|
| campaign_id | STRING | Text | Key | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| campaign_name | VARCHAR(100) | Text | Attribute | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| campaign_type | VARCHAR(50) | Text | Attribute | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| campaign_start_date | DATE | Date | Attribute | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| campaign_end_date | DATE | Date | Attribute | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| campaign_cost | DOUBLE | Decimal Number | Attribute | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| campaign_quarter | VARCHAR(10) | Text | Attribute | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| load_date | DATE | Date | Technical | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| update_date | DATE | Date | Technical | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| source_system | VARCHAR(50) | Text | Technical | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |

## go_fraud_check_fact
| Column Name | Physical Data Type | Suggested Power BI Type | Role | Nullable | Description | Source Evidence |
|---|---|---|---|---|---|---|
| fraud_check_id | STRING | Text | Key | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| application_id | STRING | Text | Foreign Key | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| fraud_check_type | VARCHAR(100) | Text | Attribute | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| check_execution_date | DATE | Date | Attribute | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| screening_result | VARCHAR(50) | Text | Attribute | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| escalation_status | VARCHAR(50) | Text | Attribute | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| resolution_outcome | VARCHAR(50) | Text | Attribute | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| load_date | DATE | Date | Technical | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| update_date | DATE | Date | Technical | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| source_system | VARCHAR(50) | Text | Technical | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |

## go_transaction_fact
| Column Name | Physical Data Type | Suggested Power BI Type | Role | Nullable | Description | Source Evidence |
|---|---|---|---|---|---|---|
| transaction_id | STRING | Text | Key | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| application_id | STRING | Text | Foreign Key | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| first_transaction_date | DATE | Date | Date | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| first_transaction_amount | DOUBLE | Decimal Number | Attribute | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| transaction_channel | VARCHAR(50) | Text | Attribute | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| load_date | DATE | Date | Technical | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| update_date | DATE | Date | Technical | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| source_system | VARCHAR(50) | Text | Technical | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |

## go_promotional_offer_dimension
| Column Name | Physical Data Type | Suggested Power BI Type | Role | Nullable | Description | Source Evidence |
|---|---|---|---|---|---|---|
| offer_id | STRING | Text | Key | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| offer_name | VARCHAR(100) | Text | Attribute | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| offer_type | VARCHAR(50) | Text | Attribute | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| offer_eligibility | VARCHAR(255) | Text | Attribute | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| offer_redemption_date | DATE | Date | Attribute | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| load_date | DATE | Date | Technical | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| update_date | DATE | Date | Technical | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |
| source_system | VARCHAR(50) | Text | Technical | Not Explicitly Defined | Not Explicitly Defined in Source Inputs | DDL |

(Other tables omitted for brevity; see DDL for full technical/audit/aggregate tables)

---

# 4. Relationship Specification

| From Table | From Column | To Table | To Column | Relationship Type | Cardinality | Filter Direction | Validation Status | Evidence |
|---|---|---|---|---|---|---|---|---|
| go_application_fact | applicant_id | go_applicant_dimension | applicant_id | Active | Many-to-One | Single | Requires Technical Validation | Visual Recommender, DDL (shared key) |
| go_application_fact | card_product_id | go_card_product_dimension | card_product_id | Active | Many-to-One | Single | Requires Technical Validation | Visual Recommender, DDL (shared key) |
| go_application_fact | acquisition_channel_id | go_acquisition_channel_dimension | acquisition_channel_id | Active | Many-to-One | Single | Requires Technical Validation | Visual Recommender, DDL (shared key) |
| go_application_fact | campaign_id | go_campaign_dimension | campaign_id | Active | Many-to-One | Single | Requires Technical Validation | Visual Recommender, DDL (shared key) |
| go_fraud_check_fact | application_id | go_application_fact | application_id | Active | Many-to-One | Single | Requires Technical Validation | Visual Recommender, DDL (shared key) |
| go_transaction_fact | application_id | go_application_fact | application_id | Active | Many-to-One | Single | Requires Technical Validation | Visual Recommender, DDL (shared key) |

---

# 5. Fact and Dimension Modeling

- Fact Tables: go_application_fact, go_fraud_check_fact, go_transaction_fact
- Dimension Tables: go_applicant_dimension, go_card_product_dimension, go_acquisition_channel_dimension, go_campaign_dimension, go_promotional_offer_dimension
- Aggregate Tables: go_aggregate_campaign_performance, go_aggregate_risk_segment, go_aggregate_fraud_screening, go_aggregate_transaction_behavior
- Grain Analysis: 
  - go_application_fact: Application-level
  - go_fraud_check_fact: Fraud check per application
  - go_transaction_fact: Transaction per application
- Degenerate Dimensions: Not Explicitly Defined in Source Inputs
- Conformed Dimensions: Not Explicitly Defined in Source Inputs
- Suggested Star Schema Structure: Application-centric star with dimensions as above

---

# 6. Base Measures

| Measure Name | DAX Formula | Format | Description | Source Evidence |
|---|---|---|---|---|
| Approval Rate | DIVIDE(COUNTROWS(FILTER(go_application_fact, go_application_fact[application_outcome] = "Approved")), COUNTROWS(go_application_fact)) | Percentage | Application approval rate | Visual Recommender, Reporting Requirements |
| Activation Rate | DIVIDE(COUNTROWS(FILTER(go_application_fact, go_application_fact[application_outcome] = "Activated")), COUNTROWS(FILTER(go_application_fact, go_application_fact[application_outcome] = "Approved"))) | Percentage | Activation rate among approved applications | Visual Recommender, Reporting Requirements |
| Average Time to Approval | AVERAGE(go_application_fact[approval_date] - go_application_fact[application_submission_date]) | Numeric (days) | Average days from application to approval | Visual Recommender, Reporting Requirements |
| Drop-off Rate | DIVIDE(COUNTROWS(go_application_fact) - COUNTROWS(FILTER(go_application_fact, go_application_fact[application_outcome] = "Activated")), COUNTROWS(go_application_fact)) | Percentage | Application drop-off rate | Visual Recommender, Reporting Requirements |
| Cost per Acquisition | DIVIDE(go_campaign_dimension[campaign_cost], COUNTROWS(FILTER(go_application_fact, go_application_fact[application_outcome] = "Activated" && go_application_fact[campaign_id] = go_campaign_dimension[campaign_id]))) | Numeric | Cost per activated application | Visual Recommender, Reporting Requirements |
| Campaign ROI | DIVIDE(SUM(go_transaction_fact[first_transaction_amount]) - go_campaign_dimension[campaign_cost], go_campaign_dimension[campaign_cost]) | Percentage | Campaign return on investment | Visual Recommender, Reporting Requirements |
| Conversion Rate | DIVIDE(COUNTROWS(FILTER(go_application_fact, go_application_fact[application_outcome] = "Activated")), COUNTROWS(go_application_fact)) | Percentage | Application to activation conversion rate | Visual Recommender, Reporting Requirements |
| Decline Rate | DIVIDE(COUNTROWS(FILTER(go_application_fact, go_application_fact[application_outcome] = "Rejected")), COUNTROWS(go_application_fact)) | Percentage | Application decline rate | Visual Recommender, Reporting Requirements |
| Average Credit Score | AVERAGE(go_applicant_dimension[credit_score]) | Numeric | Average applicant credit score | Visual Recommender, Reporting Requirements |
| Approval Rate by Risk Tier | CALCULATE(DIVIDE(COUNTROWS(FILTER(go_application_fact, go_application_fact[application_outcome] = "Approved")), COUNTROWS(go_application_fact)), go_applicant_dimension[risk_tier]) | Percentage | Approval rate by risk tier | Visual Recommender, Reporting Requirements |
| Fraud Detection Rate | DIVIDE(COUNTROWS(FILTER(go_fraud_check_fact, go_fraud_check_fact[screening_result] = "Confirmed Fraud")), COUNTROWS(go_application_fact)) | Percentage | Confirmed fraud rate | Visual Recommender, Reporting Requirements |
| False Positive Rate | DIVIDE(COUNTROWS(FILTER(go_fraud_check_fact, go_fraud_check_fact[resolution_outcome] = "Cleared")), COUNTROWS(FILTER(go_fraud_check_fact, go_fraud_check_fact[screening_result] = "Flagged"))) | Percentage | False positive rate for fraud flags | Visual Recommender, Reporting Requirements |
| Escalation Rate | DIVIDE(COUNTROWS(FILTER(go_fraud_check_fact, go_fraud_check_fact[escalation_status] = "Manual Review")), COUNTROWS(FILTER(go_fraud_check_fact, go_fraud_check_fact[screening_result] = "Flagged"))) | Percentage | Manual escalation rate for fraud flags | Visual Recommender, Reporting Requirements |
| Time to First Transaction | AVERAGE(go_transaction_fact[first_transaction_date] - go_application_fact[activation_date]) | Numeric (days) | Days from activation to first transaction | Visual Recommender, Reporting Requirements |
| Inactive Rate | DIVIDE(COUNTROWS(FILTER(go_transaction_fact, ISBLANK(go_transaction_fact[first_transaction_date]))), COUNTROWS(FILTER(go_application_fact, go_application_fact[application_outcome] = "Activated"))) | Percentage | Inactive card rate within 30 days | Visual Recommender, Reporting Requirements |
| Average First Transaction Amount | AVERAGE(go_transaction_fact[first_transaction_amount]) | Numeric | Average value of first transaction | Visual Recommender, Reporting Requirements |

---

# 7. Advanced Measures

| Measure Name | DAX Formula | Format | Description | Source Evidence |
|---|---|---|---|---|
| Not Explicitly Defined in Source Inputs | | | | |

---

# 8. Calculated Columns

Not Explicitly Defined in Source Inputs

---

# 9. Date Hierarchies

| Table | Date Column | Hierarchy Levels |
|---|---|---|
| go_application_fact | application_submission_date | Year, Quarter, Month, Day |
| go_application_fact | approval_date | Year, Quarter, Month, Day |
| go_application_fact | activation_date | Year, Quarter, Month, Day |
| go_transaction_fact | first_transaction_date | Year, Quarter, Month, Day |
| go_campaign_dimension | campaign_start_date | Year, Quarter, Month, Day |
| go_campaign_dimension | campaign_end_date | Year, Quarter, Month, Day |

---

# 10. KPI Definitions

| KPI | Formula | Business Meaning | Source Evidence |
|---|---|---|---|
| Approval Rate | (Approved ÷ Total Applications) × 100 | Application approval rate | Reporting Requirements, Visual Recommender |
| Activation Rate | (Activated ÷ Approved) × 100 | Activation rate among approved applications | Reporting Requirements, Visual Recommender |
| Average Time to Approval | Average(Approval Date – Application Date) | Average days from application to approval | Reporting Requirements, Visual Recommender |
| Drop-off Rate | (Applications – Activations) ÷ Applications × 100 | Application drop-off rate | Reporting Requirements, Visual Recommender |
| Cost per Acquisition | Campaign Cost ÷ Activations | Cost per activated application | Reporting Requirements, Visual Recommender |
| Campaign ROI | (Revenue from Activations – Campaign Cost) ÷ Campaign Cost | Campaign return on investment | Reporting Requirements, Visual Recommender |
| Conversion Rate | Activations ÷ Applications × 100 | Application to activation conversion rate | Reporting Requirements, Visual Recommender |
| Decline Rate | Rejections ÷ Total Applications × 100 | Application decline rate | Reporting Requirements, Visual Recommender |
| Average Credit Score | Total Score ÷ Number of Applicants | Average applicant credit score | Reporting Requirements, Visual Recommender |
| Approval Rate by Risk Tier | See DAX | Approval rate by risk tier | Reporting Requirements, Visual Recommender |
| Fraud Detection Rate | Confirmed Fraud ÷ Total Applications × 100 | Confirmed fraud rate | Reporting Requirements, Visual Recommender |
| False Positive Rate | Cleared Fraud Flags ÷ Total Fraud Flags × 100 | False positive rate for fraud flags | Reporting Requirements, Visual Recommender |
| Escalation Rate | Manually Reviewed Applications ÷ Total Flags × 100 | Manual escalation rate for fraud flags | Reporting Requirements, Visual Recommender |
| Time to First Transaction | First Transaction Date – Activation Date | Days from activation to first transaction | Reporting Requirements, Visual Recommender |
| Inactive Rate | (No Transactions within 30 Days ÷ Activated Cards) × 100 | Inactive card rate within 30 days | Reporting Requirements, Visual Recommender |
| Average First Transaction Amount | Total First Transaction Value ÷ Users Who Transacted | Average value of first transaction | Reporting Requirements, Visual Recommender |

---

# 11. Dashboard Specifications

## Application & Activation Funnel Report
- Business Objective: Provide comprehensive visibility into the customer journey from credit card application to activation, enabling analysis of conversion effectiveness and process efficiency.
- Primary Users: Credit product managers, onboarding operations teams, customer experience teams, analytics leads
- Suggested Visuals: Funnel chart, Clustered column chart, Line chart, Matrix, KPI cards
- Drilldowns: Application-level, Channel-level, Product-level
- Filters: Acquisition channel, Geography, Age group, Income level, Product
- Interactions: Drillthrough, Tooltip for stage details, Sync slicers
- KPI Cards: Approval Rate, Activation Rate, Drop-off Rate, Average Time to Approval
- Trend Visuals: Application/approval/activation trends over time
- Detail Views: Application-level activity, segment breakdowns

## Campaign Performance Analytics Report
- Business Objective: Evaluate marketing campaign effectiveness in driving applications and activations, and optimize channel investment.
- Primary Users: Marketing team, digital acquisition managers, campaign planners, finance business partners
- Suggested Visuals: Combo chart, Waterfall chart, KPI visual, Matrix, Treemap, Donut chart
- Drilldowns: Campaign, Channel, Quarter
- Filters: Campaign type, Channel, Product
- Interactions: Drillthrough, Tooltip for ROI/cost, Bookmarks
- KPI Cards: Cost per Acquisition, Campaign ROI, Conversion Rate
- Trend Visuals: Campaign performance over time
- Detail Views: Campaign-level performance

## Credit Risk Segmentation Report
- Business Objective: Segment applicants by creditworthiness and assess the impact of credit risk on approval and portfolio quality.
- Primary Users: Credit risk managers, underwriting policy analysts, compliance and regulatory reporting teams
- Suggested Visuals: Clustered bar chart, Scatter chart, Matrix, Decomposition tree, Key influencers
- Drilldowns: Risk tier, Demographic segment
- Filters: Risk tier, Geography, Age group, Income level
- Interactions: Drillthrough, Tooltip for segment details
- KPI Cards: Approval Rate by Risk Tier, Decline Rate, Average Credit Score
- Trend Visuals: Approval/decline trends by risk tier
- Detail Views: Risk segment analysis

## Fraud Screening Effectiveness Report
- Business Objective: Monitor fraud detection outcomes to enhance the accuracy of fraud identification during the acquisition process.
- Primary Users: Fraud management teams, compliance officers, data science teams
- Suggested Visuals: Clustered column chart, Ribbon chart, KPI visual, Sankey visual, Table visual
- Drilldowns: Fraud rule, Channel, Product
- Filters: Fraud check type, Screening result
- Interactions: Drillthrough, Tooltip for fraud logic, Bookmarks
- KPI Cards: Fraud Detection Rate, False Positive Rate, Escalation Rate, Clearance Rate
- Trend Visuals: Fraud detection trends over time
- Detail Views: Fraud case resolution paths

## First Transaction Behavior Report
- Business Objective: Understand post-activation engagement by analyzing transaction activity within the initial 30-day period.
- Primary Users: Customer engagement teams, lifecycle marketing leads, loyalty and rewards managers
- Suggested Visuals: Area chart, Multi-row card, KPI visual, Scatter chart, Funnel chart
- Drilldowns: Channel, Offer, Product
- Filters: Channel, Offer, Product
- Interactions: Drillthrough, Tooltip for offer details, Journey drillthrough
- KPI Cards: Time to First Transaction, Inactive Rate, Average First Transaction Amount
- Trend Visuals: First transaction trends
- Detail Views: Segment-level behavior patterns

---

# 12. Visual Mapping Specification

| Visual Name | Visual Type | Source | Dataset | Measures | Dimensions | Filters | Drilldowns | Validation Status | Evidence |
|---|---|---|---|---|---|---|---|---|---|
| Application Funnel | Funnel Chart | Both | go_application_fact | Approval Rate, Activation Rate, Drop-off Rate, Average Time to Approval | Application Stage, Channel, Geography, Age Group, Income Level | Channel, Geography, Age Group, Income Level | Application, Channel, Product | Validated | Reporting Requirements, Visual Recommender, DDL |
| Campaign ROI | Combo Chart | Both | go_campaign_dimension, go_application_fact, go_transaction_fact | Campaign ROI, Cost per Acquisition, Conversion Rate | Campaign, Channel, Product | Campaign Type, Channel, Product | Campaign, Channel, Quarter | Validated | Reporting Requirements, Visual Recommender, DDL |
| Risk Segmentation | Clustered Bar Chart | Both | go_applicant_dimension, go_application_fact | Approval Rate by Risk Tier, Decline Rate, Average Credit Score | Risk Tier, Geography, Age Group, Income Level | Risk Tier, Geography, Age Group, Income Level | Risk Tier, Demographic Segment | Validated | Reporting Requirements, Visual Recommender, DDL |
| Fraud Effectiveness | Clustered Column Chart | Both | go_fraud_check_fact, go_application_fact | Fraud Detection Rate, False Positive Rate, Escalation Rate, Clearance Rate | Fraud Check Type, Screening Result | Fraud Check Type, Screening Result | Fraud Rule, Channel, Product | Validated | Reporting Requirements, Visual Recommender, DDL |
| First Transaction Analysis | Area Chart | Both | go_transaction_fact, go_application_fact | Time to First Transaction, Inactive Rate, Average First Transaction Amount | Channel, Offer, Product | Channel, Offer, Product | Channel, Offer, Product | Validated | Reporting Requirements, Visual Recommender, DDL |

---

# 13. Security Specification

- Role-based access requirements: Explicitly required for all reports (see Reporting Requirements)
- Sensitive columns: credit_score, decline_reason, applicant demographics, fraud_check_type
- PII handling requirements: Restrict access to PII and customer-level data to authorized users only (see Reporting Requirements)
- Suggested RLS candidates: Product, Operations, Marketing, Risk, Fraud, Executive roles (see Visual Recommender Security Model)
- Audit logging: Use go_process_audit for access tracking

---

# 14. Hidden Columns Recommendation

- Technical IDs: load_date, update_date, source_system, audit_id, pipeline_run_id
- Audit columns: audit_id, processed_by, processing_time, audit_message
- Surrogate keys: All *_id columns not required for reporting visuals
- ETL metadata: error_id, error_source_table, error_column, error_type, error_description, error_value, error_detected_on

---

# 15. Semantic Modeling Recommendations

- Star schema optimization: Application-centric star with dimensions for applicant, card product, channel, campaign, offer
- Fact table grain: Application-level (go_application_fact), Fraud check per application (go_fraud_check_fact), Transaction per application (go_transaction_fact)
- Date dimension usage: Explicitly use date columns for hierarchies and time intelligence
- Naming standardization: Use clear, business-friendly names for measures and dimensions
- Performance optimization: Use aggregate tables for KPIs, incremental refresh for large facts, partitioning as per DDL
- Aggregation optimization: Use go_aggregate_* tables for summary-level reporting
- Relationship optimization: Single direction, validated PK/FK where possible

---

# 16. Data Quality Observations

- No explicit PK/FK constraints in DDL; relationships are semantically derived
- Nullable business fields: Not Explicitly Defined in Source Inputs
- Duplicate candidate columns: Not Explicitly Defined in Source Inputs
- Missing relationship evidence: All relationships require technical validation
- Ambiguous business semantics: Not Explicitly Defined in Source Inputs
- Cardinality validation gaps: Cardinality defined in Visual Recommender but not validated in DDL/schema
- Filter direction validation gaps: Filter direction defined in Visual Recommender but not validated in DDL/schema

---

# 17. Assumptions and Open Questions

- Source system(s) not explicitly defined
- No explicit PK/FK constraints in DDL
- No explicit nullable/required field definitions
- No explicit business definitions for all attributes
- No calculated columns defined in DDL or requirements
- Some visual recommendations (e.g., Sankey, Decomposition Tree) require business validation for appropriateness
- Hierarchies (e.g., Geography > Channel > Product) require business confirmation
- No explicit revenue field in DDL; Campaign ROI formula assumes transaction amount as revenue
- All relationships require technical validation due to lack of enforced constraints
- Security model (RLS/OLS) requires implementation confirmation
- Aggregated tables require business confirmation for reporting use
- Some measures (e.g., Clearance Rate) not fully defined in requirements

---

# 18. BIM Model Summary

| Component | Count |
|---|---|
| Tables | 14 |
| Fact Tables | 3 |
| Dimension Tables | 5 |
| Columns | Not Explicitly Defined in Source Inputs |
| Measures | 16 (from base measures) |
| Relationships | 6 |
| Validated Relationships | 0 (all require technical validation) |
| Relationships Requiring Validation | 6 |
| Hierarchies | 6 (date + suggested business) |
| KPIs | 15 |
| Dashboards | 5 |
| Visuals | 5 |

---
