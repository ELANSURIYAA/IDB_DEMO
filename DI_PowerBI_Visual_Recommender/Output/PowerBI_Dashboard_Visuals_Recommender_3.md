_____________________________________________
## Author: AAVA
## Created on:
## Description: Power BI Dashboard Visuals Recommender for Credit Card Acquisition Analytical Reporting
## Version: 3
## Updated on:
_____________________________________________

# Power BI Dashboard Visuals Recommender (Revalidated)

## 1. Visual Recommendations

### 1. Application & Activation Funnel Report
| Data Element | DAX Query / Measure | Recommended Visual | Data Fields | Measures | Interactivity | Drillthrough | Justification | Optimization Tips |
|--------------|---------------------|-------------------|-------------|----------|---------------|-------------|--------------|-------------------|
| Application Volume Trend | COUNT(application_id) | Line Chart | application_date, application_id | Total Applications | Time slicer, Channel/Product filters | Application-level drillthrough | Shows trends over time | Use date table, filter context |
| Approval Rate | DIVIDE(COUNT(approval_date), COUNT(application_id)) | KPI Visual | status | Approval Rate | Channel/Product/Segment slicers | Application-level drillthrough | KPI for conversion | Use measure, avoid calculated column |
| Activation Rate | DIVIDE(COUNT(activation_id), COUNT(approval_date)) | KPI Visual | activation_id, approval_date | Activation Rate | Channel/Product/Segment slicers | Application-level drillthrough | KPI for onboarding | Use measure |
| Drop-off by Funnel Stage | (COUNT(application_id) - COUNT(activation_id)) / COUNT(application_id) | Funnel Chart | application_id, activation_id | Drop-off Rate | Channel/Product/Segment slicers | Application-level drillthrough | Visualizes bottlenecks | Use funnel visual, optimize DAX |
| Avg. Time to Approval | AVERAGE(DATEDIFF(application_date, approval_date, DAY)) | Card Visual | application_date, approval_date | Avg. Time to Approval | Channel/Product/Segment slicers | Application-level drillthrough | Shows process efficiency | Use DAX date diff |
| Demographic Breakdown | COUNT(application_id) | Clustered Bar/Column Chart | age_group, geography, income_level | Application Count | Slicers for demographics | Drillthrough to segment | Segment analysis | Use star schema |

### 2. Campaign Performance Analytics Report
| Data Element | DAX Query / Measure | Recommended Visual | Data Fields | Measures | Interactivity | Drillthrough | Justification | Optimization Tips |
|--------------|---------------------|-------------------|-------------|----------|---------------|-------------|--------------|-------------------|
| Campaign ROI | (SUM(marketing_cost) - SUM(marketing_cost)) / SUM(marketing_cost) | KPI Visual | campaign_id, marketing_cost | Campaign ROI | Campaign/Channel/Product slicers | Drillthrough to campaign details | Key marketing metric | Use measure, avoid row context |
| Cost per Acquisition | SUM(marketing_cost) / COUNT(activation_id) | Card Visual | campaign_id, marketing_cost, activation_id | Cost per Acquisition | Campaign/Channel/Product slicers | Drillthrough to campaign details | Efficiency metric | Use measure |
| Conversion Rate by Campaign | COUNT(activation_id) / COUNT(application_id) | Clustered Column Chart | campaign_id, application_id, activation_id | Conversion Rate | Campaign/Channel/Product slicers | Drillthrough to campaign details | Compare performance | Use calculated measure |
| Campaign Timeline | COUNT(application_id) | Line and Clustered Column Chart | start_date, end_date, application_id | Application Volume | Time slicer | Drillthrough to campaign details | Visualizes campaign impact | Use combo chart |

### 3. Credit Risk Segmentation Report
| Data Element | DAX Query / Measure | Recommended Visual | Data Fields | Measures | Interactivity | Drillthrough | Justification | Optimization Tips |
|--------------|---------------------|-------------------|-------------|----------|---------------|-------------|--------------|-------------------|
| Approval Rate by Risk Tier | COUNT(approval_date) / COUNT(application_id) | Clustered Bar Chart | risk_tier, application_id, approval_date | Approval Rate | Risk Tier/Product/Channel slicers | Drillthrough to applicant details | Risk-based analysis | Use calculated column for tier |
| Credit Score Distribution | AVERAGE(score) | Histogram/Column Chart | score | Avg. Credit Score | Product/Channel/Segment slicers | Drillthrough to applicant details | Visualizes risk profile | Use binning |
| Decline Rate by Segment | COUNT(rejection_reason) / COUNT(application_id) | Matrix | segment, application_id, rejection_reason | Decline Rate | Segment/Product/Channel slicers | Drillthrough to applicant details | Multi-dim analysis | Use matrix with conditional formatting |

### 4. Fraud Screening Effectiveness Report
| Data Element | DAX Query / Measure | Recommended Visual | Data Fields | Measures | Interactivity | Drillthrough | Justification | Optimization Tips |
|--------------|---------------------|-------------------|-------------|----------|---------------|-------------|--------------|-------------------|
| Fraud Detection Rate | COUNT(check_result = 'Confirmed Fraud') / COUNT(application_id) | KPI Visual | check_result | Fraud Detection Rate | Fraud Rule/Channel/Product slicers | Drillthrough to flagged cases | Key fraud metric | Use measure |
| False Positive Rate | COUNT(screening_result = 'Cleared') / COUNT(check_result = 'Flagged') | Card Visual | screening_result, check_result | False Positive Rate | Fraud Rule/Channel/Product slicers | Drillthrough to flagged cases | Quality of fraud rules | Use measure |
| Escalation Rate | COUNT(screening_result = 'Manual Review') / COUNT(check_result = 'Flagged') | Card Visual | screening_result, check_result | Escalation Rate | Fraud Rule/Channel/Product slicers | Drillthrough to flagged cases | Operational efficiency | Use measure |
| Fraud Trend Over Time | COUNT(check_result = 'Confirmed Fraud') | Line Chart | check_date, check_result | Fraud Cases | Time/Product/Channel slicers | Drillthrough to flagged cases | Trend analysis | Use date table |

### 5. First Transaction Behavior Report
| Data Element | DAX Query / Measure | Recommended Visual | Data Fields | Measures | Interactivity | Drillthrough | Justification | Optimization Tips |
|--------------|---------------------|-------------------|-------------|----------|---------------|-------------|--------------|-------------------|
| Time to First Transaction | AVERAGE(DATEDIFF(activation_date, first_transaction_date, DAY)) | Card Visual | activation_date, first_transaction_date | Avg. Time to First Txn | Product/Channel/Segment slicers | Drillthrough to customer details | Engagement speed | Use DAX date diff |
| Inactive Rate (30 days) | COUNT(first_transaction_date IS NULL OR first_transaction_date > activation_date + 30) / COUNT(activation_id) | KPI Visual | first_transaction_date, activation_id | Inactive Rate | Product/Channel/Segment slicers | Drillthrough to customer details | Early dormancy | Use measure |
| Avg. First Transaction Amount | AVG(first_transaction_amount) | Card Visual | first_transaction_amount | Avg. First Txn Amount | Product/Channel/Segment slicers | Drillthrough to customer details | Early spend | Use measure |
| First Transaction Distribution | COUNT(transaction_id) | Histogram/Column Chart | first_transaction_amount | Transaction Count | Product/Channel/Segment slicers | Drillthrough to customer details | Spend pattern | Use binning |

---

## 2. Semantic Model Recommendations (Revalidated)

### Fact Tables
- bronze_applications (application_id, applicant_id, card_product_id, application_date, status, approval_date, rejection_reason, acquisition_channel, campaign_id, application_outcome)
- bronze_activations (activation_id, application_id, activation_date, first_transaction_amount)
- bronze_transactions (transaction_id, activation_id, first_transaction_date, transaction_amount, promotional_offer)
- bronze_fraud_checks (fraud_check_id, application_id, check_type, check_result, check_date, screening_result)
- bronze_campaigns (campaign_id, campaign_name, channel, start_date, end_date, campaign_type, marketing_cost)

### Dimension Tables
- bronze_applicants (applicant_id, full_name, email, phone_number, dob, geography, age_group, income_level, employment_type)
- bronze_card_products (card_product_id, card_name, category, interest_rate, annual_fee, product_type)
- bronze_credit_scores (credit_score_id, applicant_id, score, score_date)
- bronze_offers (offer_id, card_product_id, offer_detail, valid_from, valid_to)
- bronze_address_history (address_id, applicant_id, address_type, city, state, zip)
- bronze_employment_info (employment_id, applicant_id, employer_name, job_title, income, employment_type)

### Relationships
| From Table | From Column | To Table | To Column | Cardinality | Filter Direction | Validation Status | Evidence |
|------------|------------|----------|-----------|-------------|------------------|-------------------|----------|
| bronze_applications | applicant_id | bronze_applicants | applicant_id | Many-to-One | Single | Validated | FK in schema |
| bronze_applications | card_product_id | bronze_card_products | card_product_id | Many-to-One | Single | Validated | FK in schema |
| bronze_applications | campaign_id | bronze_campaigns | campaign_id | Many-to-One | Single | Validated | FK in schema |
| bronze_activations | application_id | bronze_applications | application_id | Many-to-One | Single | Validated | FK in schema |
| bronze_transactions | activation_id | bronze_activations | activation_id | Many-to-One | Single | Validated | FK in schema |
| bronze_fraud_checks | application_id | bronze_applications | application_id | Many-to-One | Single | Validated | FK in schema |
| bronze_credit_scores | applicant_id | bronze_applicants | applicant_id | Many-to-One | Single | Validated | FK in schema |
| bronze_offers | card_product_id | bronze_card_products | card_product_id | Many-to-One | Single | Validated | FK in schema |
| bronze_employment_info | applicant_id | bronze_applicants | applicant_id | Many-to-One | Single | Validated | FK in schema |

### Hierarchies
- Date: year > month > day (to be built from application_date, activation_date, etc.)
- Geography: geography (if normalized)
- Product: product_type > card_name

### Aggregations
- Pre-aggregate application, activation, and transaction counts by date/product/channel for performance

### Calculated Tables (if needed)
- Risk Tier Table (for banding credit scores)
- Disconnected Target Table (for KPI targets)

---

## 3. DAX Recommendations

### Measures
- Total Applications = COUNT(bronze_applications[application_id])
- Approved Applications = CALCULATE([Total Applications], bronze_applications[status] = "Approved")
- Activation Rate = DIVIDE(COUNT(bronze_activations[activation_id]), [Approved Applications])
- Approval Rate = DIVIDE([Approved Applications], [Total Applications])
- Drop-off Rate = DIVIDE([Total Applications] - COUNT(bronze_activations[activation_id]), [Total Applications])
- Avg. Time to Approval = AVERAGE(DATEDIFF(bronze_applications[application_date], bronze_applications[approval_date], DAY))
- Cost per Acquisition = DIVIDE(SUM(bronze_campaigns[marketing_cost]), COUNT(bronze_activations[activation_id]))
- Campaign ROI = DIVIDE(SUM(bronze_campaigns[marketing_cost]) - SUM(bronze_campaigns[marketing_cost]), SUM(bronze_campaigns[marketing_cost]))
- Conversion Rate = DIVIDE(COUNT(bronze_activations[activation_id]), [Total Applications])
- Decline Rate = DIVIDE(COUNT(bronze_applications[rejection_reason]), [Total Applications])
- Avg. Credit Score = AVERAGE(bronze_credit_scores[score])
- Fraud Detection Rate = DIVIDE(COUNT(bronze_fraud_checks[check_result] = 'Confirmed Fraud'), [Total Applications])
- False Positive Rate = DIVIDE(COUNT(bronze_fraud_checks[screening_result] = 'Cleared'), COUNT(bronze_fraud_checks[check_result] = 'Flagged'))
- Escalation Rate = DIVIDE(COUNT(bronze_fraud_checks[screening_result] = 'Manual Review'), COUNT(bronze_fraud_checks[check_result] = 'Flagged'))
- Time to First Transaction = AVERAGE(DATEDIFF(bronze_activations[activation_date], bronze_transactions[first_transaction_date], DAY))
- Inactive Rate = DIVIDE(COUNT(bronze_transactions[first_transaction_date] IS NULL OR bronze_transactions[first_transaction_date] > bronze_activations[activation_date] + 30), COUNT(bronze_activations[activation_id]))
- Avg. First Transaction Amount = AVG(bronze_activations[first_transaction_amount])

### Calculated Columns
- Risk Tier = SWITCH(TRUE(), bronze_credit_scores[score] < 580, "High", bronze_credit_scores[score] < 700, "Moderate", bronze_credit_scores[score] >= 700, "Low")
- First Transaction Flag = IF(bronze_transactions[first_transaction_date] <= bronze_activations[activation_date] + 30, 1, 0)

### Time Intelligence
- Use built-in DAX time intelligence for YTD, QTD, MTD trends

### KPI Logic
- Use disconnected tables for targets
- Use DAX for dynamic KPI status (e.g., color coding)

### Ranking/Running Totals
- RANKX for campaign/product/channel ranking
- RUNNINGTOTAL for cumulative applications/activations

### Percent Variance
- VARIANCE = ([Current Period] - [Previous Period]) / [Previous Period]

---

## 4. Overall Dashboard Design

### Layout Suggestions
- Landing page with high-level KPIs and navigation
- Separate tabs/pages for each report (Funnel, Campaign, Risk, Fraud, Transaction)
- Consistent slicers (date, product, channel, segment) on all pages
- Use bookmarks for guided navigation and scenario analysis

### Navigation Flow
- Top-level navigation bar or left-side menu
- Drillthrough from summary visuals to detailed tables
- Tooltip pages for additional context

### Bookmark Usage
- Scenario toggles (e.g., show/hide segments)
- Guided analysis paths

### Performance Optimization
- Use Import mode unless DirectQuery is required
- Pre-aggregate large tables
- Use incremental refresh for Fact tables
- Avoid excessive calculated columns
- Optimize DAX (avoid row context in measures)
- Use query folding where possible

### Color Scheme
- Use organization branding
- Color-blind friendly palettes
- Consistent color coding for statuses (e.g., green=approved, red=declined)

### Typography
- Use clear, readable fonts
- Hierarchical font sizes for headings, KPIs, and details

### Accessibility
- Alt text for visuals
- Sufficient color contrast
- Keyboard navigation
- Use tooltips for explanations

### Mobile Layout
- Responsive design for key KPIs and visuals
- Prioritize cards, KPIs, and summary charts
- Minimize scrolling and horizontal navigation

### Interactive Elements
- Slicers for date, product, channel, segment
- Drillthrough and tooltip pages
- Sync slicers across pages
- Field parameters for dynamic axis selection

---

## Additional Recommendations
- Implement row-level security for PII and sensitive data
- Use audit logs for access to sensitive reports
- Regularly review and optimize data model as requirements evolve
- Document all DAX measures and model relationships

---

# End of Power BI Dashboard Visuals Recommender
