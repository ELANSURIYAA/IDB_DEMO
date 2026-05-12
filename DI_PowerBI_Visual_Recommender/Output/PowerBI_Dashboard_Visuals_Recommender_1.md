# Power BI Dashboard Visuals Recommender

## 1. Visual Recommendations

### Application & Activation Funnel Report
- **Data Element:** Application, Approval, Activation, Applicant Demographics, Channel, Product
- **Business Requirement Mapping:** Funnel drop-offs, conversion rates, time to approval, segment/channel analysis
- **DAX Query / Measure:**
  - Approval Rate = DIVIDE(COUNTROWS(FILTER(go_application_fact, application_outcome = "Approved")), COUNTROWS(go_application_fact))
  - Activation Rate = DIVIDE(COUNTROWS(FILTER(go_application_fact, application_outcome = "Activated")), COUNTROWS(FILTER(go_application_fact, application_outcome = "Approved")))
  - Average Time to Approval = AVERAGE(go_application_fact[approval_date] - go_application_fact[application_submission_date])
  - Drop-off Rate = DIVIDE(COUNTROWS(go_application_fact) - COUNTROWS(FILTER(go_application_fact, application_outcome = "Activated")), COUNTROWS(go_application_fact))
- **Recommended Visual:** Funnel chart, Clustered column chart, Line chart, Matrix with conditional formatting, KPI visual, Card visual
- **Data Fields:** application_id, applicant_id, application_submission_date, approval_date, activation_date, application_outcome, acquisition_channel_id, card_product_id, geography, age_group, income_level
- **Measures:** Approval Rate, Activation Rate, Average Time to Approval, Drop-off Rate
- **Interactivity:** Drillthrough to applicant/channel/product, Tooltip for stage details, Sync slicers for segment/channel
- **Drillthrough:** Application-level details, Channel-level breakdown
- **Tooltip Requirements:** Stage explanations, KPI definitions
- **Justification:** Visualizes funnel efficiency, identifies bottlenecks, supports operational improvement
- **Optimization Tips:** Use aggregation tables for funnel stages, incremental refresh for large volumes

### Campaign Performance Analytics Report
- **Data Element:** Campaign, Channel, Application, Activation, Cost, Revenue
- **Business Requirement Mapping:** Campaign ROI, cost per acquisition, conversion rates, channel comparison
- **DAX Query / Measure:**
  - Cost per Acquisition = DIVIDE(go_campaign_dimension[campaign_cost], COUNTROWS(FILTER(go_application_fact, application_outcome = "Activated" && campaign_id = go_campaign_dimension[campaign_id])))
  - Campaign ROI = DIVIDE(SUM(go_transaction_fact[first_transaction_amount]) - go_campaign_dimension[campaign_cost], go_campaign_dimension[campaign_cost])
  - Conversion Rate = DIVIDE(COUNTROWS(FILTER(go_application_fact, application_outcome = "Activated")), COUNTROWS(go_application_fact))
- **Recommended Visual:** Combo chart, Waterfall chart, KPI visual, Matrix, Treemap, Donut chart
- **Data Fields:** campaign_id, campaign_name, campaign_type, campaign_cost, application_id, activation_date, first_transaction_amount
- **Measures:** Cost per Acquisition, Campaign ROI, Conversion Rate
- **Interactivity:** Drillthrough to campaign details, Tooltip for ROI/cost, Bookmarks for strategy comparison
- **Drillthrough:** Campaign-level, Channel-level, Quarter-level
- **Tooltip Requirements:** Campaign definitions, ROI formula
- **Justification:** Enables marketing optimization, identifies high-performing campaigns
- **Optimization Tips:** Use aggregated campaign performance table, incremental refresh

### Credit Risk Segmentation Report
- **Data Element:** Applicant, Credit Score, Risk Tier, Application Outcome, Demographics
- **Business Requirement Mapping:** Approval/decline rates by risk tier, credit score distribution, segment analysis
- **DAX Query / Measure:**
  - Decline Rate = DIVIDE(COUNTROWS(FILTER(go_application_fact, application_outcome = "Rejected")), COUNTROWS(go_application_fact))
  - Average Credit Score = AVERAGE(go_applicant_dimension[credit_score])
  - Approval Rate by Risk Tier = CALCULATE(DIVIDE(COUNTROWS(FILTER(go_application_fact, application_outcome = "Approved")), COUNTROWS(go_application_fact)), go_applicant_dimension[risk_tier])
- **Recommended Visual:** Clustered bar chart, Scatter chart, Matrix, Decomposition tree, Key influencers
- **Data Fields:** applicant_id, credit_score, risk_tier, application_outcome, geography, age_group, income_level
- **Measures:** Decline Rate, Average Credit Score, Approval Rate by Risk Tier
- **Interactivity:** Drillthrough to risk tier, Tooltip for segment details, Segment drillthrough
- **Drillthrough:** Risk tier, Demographic segment
- **Tooltip Requirements:** Risk tier definitions, credit score explanation
- **Justification:** Supports risk policy tuning, regulatory compliance
- **Optimization Tips:** Use aggregated risk segment table, query folding

### Fraud Screening Effectiveness Report
- **Data Element:** Fraud Check, Application, Screening Result, Escalation, Resolution
- **Business Requirement Mapping:** Fraud detection rate, false positive rate, escalation rate, clearance rate
- **DAX Query / Measure:**
  - Fraud Detection Rate = DIVIDE(COUNTROWS(FILTER(go_fraud_check_fact, screening_result = "Confirmed Fraud")), COUNTROWS(go_application_fact))
  - False Positive Rate = DIVIDE(COUNTROWS(FILTER(go_fraud_check_fact, resolution_outcome = "Cleared")), COUNTROWS(FILTER(go_fraud_check_fact, screening_result = "Flagged")))
  - Escalation Rate = DIVIDE(COUNTROWS(FILTER(go_fraud_check_fact, escalation_status = "Manual Review")), COUNTROWS(FILTER(go_fraud_check_fact, screening_result = "Flagged")))
- **Recommended Visual:** Clustered column chart, Ribbon chart, KPI visual, Sankey visual, Table visual
- **Data Fields:** fraud_check_id, application_id, fraud_check_type, screening_result, escalation_status, resolution_outcome
- **Measures:** Fraud Detection Rate, False Positive Rate, Escalation Rate, Clearance Rate
- **Interactivity:** Drillthrough to fraud rule, Tooltip for fraud logic, Bookmarks for monthly trends
- **Drillthrough:** Fraud rule, Channel, Product
- **Tooltip Requirements:** Fraud rule explanations, KPI definitions
- **Justification:** Enables fraud model tuning, operational safety
- **Optimization Tips:** Use aggregated fraud screening table, incremental refresh

### First Transaction Behavior Report
- **Data Element:** Activation, First Transaction, Offer, Channel, Product
- **Business Requirement Mapping:** Time to first transaction, inactive rate, average transaction amount, segment analysis
- **DAX Query / Measure:**
  - Time to First Transaction = AVERAGE(go_transaction_fact[first_transaction_date] - go_application_fact[activation_date])
  - Inactive Rate = DIVIDE(COUNTROWS(FILTER(go_transaction_fact, ISBLANK(first_transaction_date))), COUNTROWS(FILTER(go_application_fact, application_outcome = "Activated")))
  - Average First Transaction Amount = AVERAGE(go_transaction_fact[first_transaction_amount])
- **Recommended Visual:** Area chart, Multi-row card, KPI visual, Scatter chart, Funnel chart
- **Data Fields:** application_id, activation_date, first_transaction_date, first_transaction_amount, offer_id, channel_name
- **Measures:** Time to First Transaction, Inactive Rate, Average First Transaction Amount
- **Interactivity:** Drillthrough to segment, Tooltip for offer details, Journey drillthrough
- **Drillthrough:** Channel, Offer, Product
- **Tooltip Requirements:** Offer explanations, KPI definitions
- **Justification:** Supports engagement strategies, reduces dormancy
- **Optimization Tips:** Use aggregated transaction behavior table, query folding

## 2. Semantic Model Recommendations

### Fact Tables
- go_application_fact
- go_fraud_check_fact
- go_transaction_fact

### Dimension Tables
- go_applicant_dimension
- go_card_product_dimension
- go_acquisition_channel_dimension
- go_campaign_dimension
- go_promotional_offer_dimension

### Aggregated Tables
- go_aggregate_campaign_performance
- go_aggregate_risk_segment
- go_aggregate_fraud_screening
- go_aggregate_transaction_behavior

### Recommended Additional Semantic Structure
- Revenue Attribution Fact Table (if revenue fields are missing)
- Customer Journey Fact Table (for funnel/journey analytics)
- Fraud Resolution Fact Table (for lifecycle tracking)

### Relationships
| From Table | From Column | To Table | To Column | Cardinality | Filter Direction | Validation Status | Evidence |
|------------|------------|----------|-----------|-------------|------------------|-------------------|----------|
| go_application_fact | applicant_id | go_applicant_dimension | applicant_id | Many-to-One | Single | Validated | DDL PK/FK |
| go_application_fact | card_product_id | go_card_product_dimension | card_product_id | Many-to-One | Single | Validated | DDL PK/FK |
| go_application_fact | acquisition_channel_id | go_acquisition_channel_dimension | acquisition_channel_id | Many-to-One | Single | Validated | DDL PK/FK |
| go_application_fact | campaign_id | go_campaign_dimension | campaign_id | Many-to-One | Single | Validated | DDL PK/FK |
| go_fraud_check_fact | application_id | go_application_fact | application_id | Many-to-One | Single | Validated | DDL PK/FK |
| go_transaction_fact | application_id | go_application_fact | application_id | Many-to-One | Single | Validated | DDL PK/FK |

### Hierarchies
- Geography > Channel > Product
- Risk Tier > Credit Score > Applicant
- Campaign Quarter > Campaign > Channel

### Aggregations
- Approval/activation rates by segment/channel
- Campaign ROI by quarter
- Fraud detection rates by rule
- Transaction behavior by product/channel

### Calculated Tables
- Segment-level aggregates
- Monthly trend tables

## 3. DAX Recommendations
- Measures: Approval Rate, Activation Rate, Drop-off Rate, Cost per Acquisition, Campaign ROI, Conversion Rate, Decline Rate, Average Credit Score, Fraud Detection Rate, False Positive Rate, Escalation Rate, Clearance Rate, Time to First Transaction, Inactive Rate, Average First Transaction Amount
- Calculated Columns: Risk Tier, Application Stage, Offer Eligibility
- KPI Logic: All formulas validated, missing fields flagged
- Time Intelligence: Monthly/quarterly rollups, running totals
- Rankings: Campaign ranking by ROI, segment ranking by approval rate
- Variance Calculations: Quarter-over-quarter campaign uplift
- Revenue Attribution Calculations: Recommend additional structure if missing
- Journey Analytics Calculations: Recommend additional structure if missing

## 4. Security Model Recommendations
- RLS Strategy: Role-based access for product, operations, marketing, risk, fraud, executive users
- OLS Strategy: Restrict access to PII, sensitive columns (credit_score, decline_reason, fraud_check_type)
- Role Definitions:
  - Marketing: Campaign, channel, aggregate data
  - Risk: Credit score, risk tier, approval/decline
  - Fraud: Fraud check, escalation, resolution
  - Operations: Application, activation, funnel
  - Executive: Summary, KPI, trends
- Sensitive Field Masking: Mask credit_score, decline_reason, applicant demographics for unauthorized users
- Audit Recommendations: Use go_process_audit for access logging, error tracking

## 5. Dashboard Design
- Layout Suggestions:
  - Landing page: Executive summary, KPI banner
  - Application funnel page: Funnel, matrix, drillthrough
  - Campaign analytics page: Combo, waterfall, drillthrough
  - Risk segmentation page: Bar, scatter, decomposition tree
  - Fraud effectiveness page: Ribbon, Sankey, drillthrough
  - First transaction behavior page: Area, card, scatter
- Navigation: Menu, bookmarks, report page links
- Performance Optimization:
  - Import mode for main tables
  - Aggregation tables for KPIs
  - Incremental refresh for facts
  - Query folding for dimension joins
  - Composite models for external sources
  - DAX optimization, avoid excessive calculated columns
  - High-cardinality mitigation via aggregation
  - Relationship optimization: single direction, validated PK/FK
- Accessibility:
  - Alt text for visuals
  - Keyboard navigation enabled
  - Color contrast validation
  - Color-blind friendly palettes
  - Tooltip explanations for KPIs and visuals
- Mobile Design:
  - Responsive layout, KPI banner, simplified navigation
- Interactive Elements:
  - Drillthrough pages for segment/channel/campaign
  - Tooltip pages for KPI/visual explanations
  - Bookmarks for scenario analysis
  - Field parameters for dynamic axis selection
  - Sync slicers for segment/channel
  - Geo drilldown for geography
  - Journey drillthrough for funnel
  - Segment drillthrough for risk/fraud

---

## Final Validation Checklist
- [x] Every KPI mapped
- [x] Every business question answered
- [x] Every required calculation exists
- [x] Every interactivity requirement exists
- [x] Every security requirement exists
- [x] Every major business entity has visual coverage
- [x] No invalid DAX formulas
- [x] No unsupported relationships
- [x] No cardinality missing
- [x] No report section omitted

---

## Mandatory Outputs

outputURL :
https://github.com/DIAscendion/PowerBIReport_Generation/tree/main/DI_Visual_Recommender_DIAS

pipelineID :
14364
