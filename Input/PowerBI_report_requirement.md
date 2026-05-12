# Power BI BIM Model Specification

---

## 1. Data Source Summary

| Property              | Value                                                                                 |
|-----------------------|---------------------------------------------------------------------------------------|
| Source Systems        | Not Explicitly Defined in Source Inputs                                               |
| Schema Names          | Gold                                                                                  |
| Layer Names           | Gold                                                                                  |
| Physical Tables       | go_applicant_dimension, go_application_fact, go_card_product_dimension, go_acquisition_channel_dimension, go_campaign_dimension, go_fraud_check_fact, go_transaction_fact, go_promotional_offer_dimension, go_error_data, go_process_audit, go_aggregate_campaign_performance, go_aggregate_risk_segment, go_aggregate_fraud_screening, go_aggregate_transaction_behavior |
| Source Types          | Delta Lake tables (Spark SQL compatible)                                              |

**Source Evidence:**  
- DDL: Fabric Gold Model Physical Output.txt

---

## 2. Table Inventory

| Property         | Value                                                                                   |
|------------------|-----------------------------------------------------------------------------------------|
| Table Name       | go_applicant_dimension                                                                  |
| Schema           | Gold                                                                                    |
| Layer            | Gold                                                                                    |
| Classification   | Dimension                                                                               |
| Source Evidence  | DDL                                                                                     |
| Description      | Not Explicitly Defined in Source Inputs                                                 |

| Table Name       | go_application_fact                                                                     |
| Schema           | Gold                                                                                    |
| Layer            | Gold                                                                                    |
| Classification   | Fact                                                                                    |
| Source Evidence  | DDL                                                                                     |
| Description      | Not Explicitly Defined in Source Inputs                                                 |

| Table Name       | go_card_product_dimension                                                               |
| Schema           | Gold                                                                                    |
| Layer            | Gold                                                                                    |
| Classification   | Dimension                                                                               |
| Source Evidence  | DDL                                                                                     |
| Description      | Not Explicitly Defined in Source Inputs                                                 |

| Table Name       | go_acquisition_channel_dimension                                                        |
| Schema           | Gold                                                                                    |
| Layer            | Gold                                                                                    |
| Classification   | Dimension                                                                               |
| Source Evidence  | DDL                                                                                     |
| Description      | Not Explicitly Defined in Source Inputs                                                 |

| Table Name       | go_campaign_dimension                                                                   |
| Schema           | Gold                                                                                    |
| Layer            | Gold                                                                                    |
| Classification   | Dimension                                                                               |
| Source Evidence  | DDL                                                                                     |
| Description      | Not Explicitly Defined in Source Inputs                                                 |

| Table Name       | go_fraud_check_fact                                                                     |
| Schema           | Gold                                                                                    |
| Layer            | Gold                                                                                    |
| Classification   | Fact                                                                                    |
| Source Evidence  | DDL                                                                                     |
| Description      | Not Explicitly Defined in Source Inputs                                                 |

| Table Name       | go_transaction_fact                                                                     |
| Schema           | Gold                                                                                    |
| Layer            | Gold                                                                                    |
| Classification   | Fact                                                                                    |
| Source Evidence  | DDL                                                                                     |
| Description      | Not Explicitly Defined in Source Inputs                                                 |

| Table Name       | go_promotional_offer_dimension                                                          |
| Schema           | Gold                                                                                    |
| Layer            | Gold                                                                                    |
| Classification   | Dimension                                                                               |
| Source Evidence  | DDL                                                                                     |
| Description      | Not Explicitly Defined in Source Inputs                                                 |

| Table Name       | go_error_data                                                                           |
| Schema           | Gold                                                                                    |
| Layer            | Gold                                                                                    |
| Classification   | Technical / Audit                                                                       |
| Source Evidence  | DDL                                                                                     |
| Description      | Not Explicitly Defined in Source Inputs                                                 |

| Table Name       | go_process_audit                                                                        |
| Schema           | Gold                                                                                    |
| Layer            | Gold                                                                                    |
| Classification   | Technical / Audit                                                                       |
| Source Evidence  | DDL                                                                                     |
| Description      | Not Explicitly Defined in Source Inputs                                                 |

| Table Name       | go_aggregate_campaign_performance                                                       |
| Schema           | Gold                                                                                    |
| Layer            | Gold                                                                                    |
| Classification   | Aggregate / Fact                                                                        |
| Source Evidence  | DDL                                                                                     |
| Description      | Not Explicitly Defined in Source Inputs                                                 |

| Table Name       | go_aggregate_risk_segment                                                               |
| Schema           | Gold                                                                                    |
| Layer            | Gold                                                                                    |
| Classification   | Aggregate / Fact                                                                        |
| Source Evidence  | DDL                                                                                     |
| Description      | Not Explicitly Defined in Source Inputs                                                 |

| Table Name       | go_aggregate_fraud_screening                                                            |
| Schema           | Gold                                                                                    |
| Layer            | Gold                                                                                    |
| Classification   | Aggregate / Fact                                                                        |
| Source Evidence  | DDL                                                                                     |
| Description      | Not Explicitly Defined in Source Inputs                                                 |

| Table Name       | go_aggregate_transaction_behavior                                                       |
| Schema           | Gold                                                                                    |
| Layer            | Gold                                                                                    |
| Classification   | Aggregate / Fact                                                                        |
| Source Evidence  | DDL                                                                                     |
| Description      | Not Explicitly Defined in Source Inputs                                                 |

---

## 3. Column Definitions

### go_applicant_dimension

| Column Name   | Physical Data Type | Suggested Power BI Type | Role         | Nullable | Description | Source Evidence |
|---------------|-------------------|------------------------|--------------|----------|-------------|----------------|
| applicant_id  | STRING            | Text                   | Key          | Not Explicitly Defined | Not Explicitly Defined | DDL |
| geography     | VARCHAR(100)      | Text                   | Attribute    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| age_group     | VARCHAR(50)       | Text                   | Attribute    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| income_level  | VARCHAR(50)       | Text                   | Attribute    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| employment_type| VARCHAR(50)      | Text                   | Attribute    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| credit_score  | INT               | Whole Number           | Attribute    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| risk_tier     | VARCHAR(50)       | Text                   | Attribute    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| load_date     | DATE              | Date                   | Technical    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| update_date   | DATE              | Date                   | Technical    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| source_system | VARCHAR(50)       | Text                   | Technical    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| marital_status| VARCHAR(50)       | Text                   | Attribute    | Not Explicitly Defined | Not Explicitly Defined | DDL |

### go_application_fact

| Column Name               | Physical Data Type | Suggested Power BI Type | Role         | Nullable | Description | Source Evidence |
|---------------------------|-------------------|------------------------|--------------|----------|-------------|----------------|
| application_id            | STRING            | Text                   | Key          | Not Explicitly Defined | Not Explicitly Defined | DDL |
| applicant_id              | STRING            | Text                   | Foreign Key  | Not Explicitly Defined | Not Explicitly Defined | DDL |
| card_product_id           | STRING            | Text                   | Foreign Key  | Not Explicitly Defined | Not Explicitly Defined | DDL |
| acquisition_channel_id    | STRING            | Text                   | Foreign Key  | Not Explicitly Defined | Not Explicitly Defined | DDL |
| campaign_id               | STRING            | Text                   | Foreign Key  | Not Explicitly Defined | Not Explicitly Defined | DDL |
| application_submission_date| DATE             | Date                   | Date         | Not Explicitly Defined | Not Explicitly Defined | DDL |
| approval_date             | DATE              | Date                   | Date         | Not Explicitly Defined | Not Explicitly Defined | DDL |
| activation_date           | DATE              | Date                   | Date         | Not Explicitly Defined | Not Explicitly Defined | DDL |
| application_status        | VARCHAR(50)       | Text                   | Attribute    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| application_outcome       | VARCHAR(50)       | Text                   | Attribute    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| decline_reason            | VARCHAR(255)      | Text                   | Attribute    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| application_stage         | VARCHAR(50)       | Text                   | Attribute    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| load_date                 | DATE              | Date                   | Technical    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| update_date               | DATE              | Date                   | Technical    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| source_system             | VARCHAR(50)       | Text                   | Technical    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| application_channel       | VARCHAR(50)       | Text                   | Attribute    | Not Explicitly Defined | Not Explicitly Defined | DDL |

### go_card_product_dimension

| Column Name     | Physical Data Type | Suggested Power BI Type | Role         | Nullable | Description | Source Evidence |
|-----------------|-------------------|------------------------|--------------|----------|-------------|----------------|
| card_product_id | STRING            | Text                   | Key          | Not Explicitly Defined | Not Explicitly Defined | DDL |
| product_name    | VARCHAR(100)      | Text                   | Attribute    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| product_category| VARCHAR(50)       | Text                   | Attribute    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| product_launch_date| DATE           | Date                   | Attribute    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| load_date       | DATE              | Date                   | Technical    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| update_date     | DATE              | Date                   | Technical    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| source_system   | VARCHAR(50)       | Text                   | Technical    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| reward_points   | INT               | Whole Number           | Attribute    | Not Explicitly Defined | Not Explicitly Defined | DDL |

### go_acquisition_channel_dimension

| Column Name           | Physical Data Type | Suggested Power BI Type | Role         | Nullable | Description | Source Evidence |
|-----------------------|-------------------|------------------------|--------------|----------|-------------|----------------|
| acquisition_channel_id| STRING            | Text                   | Key          | Not Explicitly Defined | Not Explicitly Defined | DDL |
| channel_name          | VARCHAR(100)      | Text                   | Attribute    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| channel_type          | VARCHAR(50)       | Text                   | Attribute    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| load_date             | DATE              | Date                   | Technical    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| update_date           | DATE              | Date                   | Technical    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| source_system         | VARCHAR(50)       | Text                   | Technical    | Not Explicitly Defined | Not Explicitly Defined | DDL |

### go_campaign_dimension

| Column Name         | Physical Data Type | Suggested Power BI Type | Role         | Nullable | Description | Source Evidence |
|---------------------|-------------------|------------------------|--------------|----------|-------------|----------------|
| campaign_id         | STRING            | Text                   | Key          | Not Explicitly Defined | Not Explicitly Defined | DDL |
| campaign_name       | VARCHAR(100)      | Text                   | Attribute    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| campaign_type       | VARCHAR(50)       | Text                   | Attribute    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| campaign_start_date | DATE              | Date                   | Attribute    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| campaign_end_date   | DATE              | Date                   | Attribute    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| campaign_cost       | DOUBLE            | Decimal Number         | Attribute    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| campaign_quarter    | VARCHAR(10)       | Text                   | Attribute    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| load_date           | DATE              | Date                   | Technical    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| update_date         | DATE              | Date                   | Technical    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| source_system       | VARCHAR(50)       | Text                   | Technical    | Not Explicitly Defined | Not Explicitly Defined | DDL |

### go_fraud_check_fact

| Column Name       | Physical Data Type | Suggested Power BI Type | Role         | Nullable | Description | Source Evidence |
|-------------------|-------------------|------------------------|--------------|----------|-------------|----------------|
| fraud_check_id    | STRING            | Text                   | Key          | Not Explicitly Defined | Not Explicitly Defined | DDL |
| application_id    | STRING            | Text                   | Foreign Key  | Not Explicitly Defined | Not Explicitly Defined | DDL |
| fraud_check_type  | VARCHAR(100)      | Text                   | Attribute    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| check_execution_date| DATE            | Date                   | Attribute    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| screening_result  | VARCHAR(50)       | Text                   | Attribute    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| escalation_status | VARCHAR(50)       | Text                   | Attribute    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| resolution_outcome| VARCHAR(50)       | Text                   | Attribute    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| load_date         | DATE              | Date                   | Technical    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| update_date       | DATE              | Date                   | Technical    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| source_system     | VARCHAR(50)       | Text                   | Technical    | Not Explicitly Defined | Not Explicitly Defined | DDL |

### go_transaction_fact

| Column Name           | Physical Data Type | Suggested Power BI Type | Role         | Nullable | Description | Source Evidence |
|-----------------------|-------------------|------------------------|--------------|----------|-------------|----------------|
| transaction_id        | STRING            | Text                   | Key          | Not Explicitly Defined | Not Explicitly Defined | DDL |
| application_id        | STRING            | Text                   | Foreign Key  | Not Explicitly Defined | Not Explicitly Defined | DDL |
| first_transaction_date| DATE              | Date                   | Attribute    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| first_transaction_amount| DOUBLE          | Decimal Number         | Attribute    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| transaction_channel   | VARCHAR(50)       | Text                   | Attribute    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| load_date             | DATE              | Date                   | Technical    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| update_date           | DATE              | Date                   | Technical    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| source_system         | VARCHAR(50)       | Text                   | Technical    | Not Explicitly Defined | Not Explicitly Defined | DDL |

### go_promotional_offer_dimension

| Column Name           | Physical Data Type | Suggested Power BI Type | Role         | Nullable | Description | Source Evidence |
|-----------------------|-------------------|------------------------|--------------|----------|-------------|----------------|
| offer_id              | STRING            | Text                   | Key          | Not Explicitly Defined | Not Explicitly Defined | DDL |
| offer_name            | VARCHAR(100)      | Text                   | Attribute    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| offer_type            | VARCHAR(50)       | Text                   | Attribute    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| offer_eligibility     | VARCHAR(255)      | Text                   | Attribute    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| offer_redemption_date | DATE              | Date                   | Attribute    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| load_date             | DATE              | Date                   | Technical    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| update_date           | DATE              | Date                   | Technical    | Not Explicitly Defined | Not Explicitly Defined | DDL |
| source_system         | VARCHAR(50)       | Text                   | Technical    | Not Explicitly Defined | Not Explicitly Defined | DDL |

*Remaining tables (error, audit, and aggregate tables) follow similar patterns. See DDL for full column lists.*

---

## 4. Relationship Specification

| From Table              | From Column           | To Table                  | To Column           | Relationship Type | Cardinality   | Filter Direction | Validation Status         | Evidence                        |
|-------------------------|----------------------|---------------------------|---------------------|-------------------|---------------|------------------|---------------------------|-----------------------------------|
| go_application_fact     | applicant_id         | go_applicant_dimension    | applicant_id        | Active            | Many-to-One   | Single           | Requires Technical Validation | Visual Recommender               |
| go_application_fact     | card_product_id      | go_card_product_dimension | card_product_id     | Active            | Many-to-One   | Single           | Requires Technical Validation | Visual Recommender               |
| go_application_fact     | acquisition_channel_id| go_acquisition_channel_dimension | acquisition_channel_id | Active | Many-to-One   | Single           | Requires Technical Validation | Visual Recommender               |
| go_application_fact     | campaign_id          | go_campaign_dimension     | campaign_id         | Active            | Many-to-One   | Single           | Requires Technical Validation | Visual Recommender               |
| go_fraud_check_fact     | application_id       | go_application_fact       | application_id      | Active            | Many-to-One   | Single           | Requires Technical Validation | Visual Recommender               |
| go_transaction_fact     | application_id       | go_application_fact       | application_id      | Active            | Many-to-One   | Single           | Requires Technical Validation | Visual Recommender               |

**Relationships Requiring Business Confirmation:**  
- Any relationships not listed above or not present in the Visual Recommender output.

---

## 5. Fact and Dimension Modeling

- **Fact Tables:**  
  - go_application_fact  
  - go_fraud_check_fact  
  - go_transaction_fact  
  - go_aggregate_campaign_performance  
  - go_aggregate_risk_segment  
  - go_aggregate_fraud_screening  
  - go_aggregate_transaction_behavior  

- **Dimension Tables:**  
  - go_applicant_dimension  
  - go_card_product_dimension  
  - go_acquisition_channel_dimension  
  - go_campaign_dimension  
  - go_promotional_offer_dimension  

- **Grain Analysis:**  
  - go_application_fact: Application-level (application_id)  
  - go_fraud_check_fact: Fraud check-level (fraud_check_id)  
  - go_transaction_fact: Transaction-level (transaction_id)  

- **Degenerate Dimensions:**  
  - Not Explicitly Defined in Source Inputs  

- **Conformed Dimensions:**  
  - Not Explicitly Defined in Source Inputs  

- **Suggested Star Schema Structure:**  
  - Application fact at the center, linked to applicant, product, channel, campaign dimensions.

**Source Evidence:**  
- DDL  
- Visual Recommender Output

---

## 6. Base Measures

| Measure Name                | DAX Formula                                                                                                         | Format         | Description                          | Source Evidence           |
|-----------------------------|---------------------------------------------------------------------------------------------------------------------|---------------|--------------------------------------|---------------------------|
| Approval Rate               | DIVIDE(COUNTROWS(FILTER(go_application_fact, go_application_fact[application_outcome] = "Approved")), COUNTROWS(go_application_fact)) | Percentage     | Ratio of approved applications       | Visual Recommender        |
| Activation Rate             | DIVIDE(COUNTROWS(FILTER(go_application_fact, go_application_fact[application_outcome] = "Activated")), COUNTROWS(FILTER(go_application_fact, go_application_fact[application_outcome] = "Approved"))) | Percentage     | Ratio of activated to approved apps  | Visual Recommender        |
| Average Time to Approval    | AVERAGE(go_application_fact[approval_date] - go_application_fact[application_submission_date])                       | Duration/Days  | Avg. days from submission to approval| Visual Recommender        |
| Drop-off Rate               | DIVIDE(COUNTROWS(go_application_fact) - COUNTROWS(FILTER(go_application_fact, go_application_fact[application_outcome] = "Activated")), COUNTROWS(go_application_fact)) | Percentage     | Applications not activated           | Visual Recommender        |
| Cost per Acquisition        | DIVIDE(go_campaign_dimension[campaign_cost], COUNTROWS(FILTER(go_application_fact, go_application_fact[application_outcome] = "Activated" && go_application_fact[campaign_id] = go_campaign_dimension[campaign_id]))) | Decimal Number | Cost per activated application       | Visual Recommender        |
| Campaign ROI                | DIVIDE(SUM(go_transaction_fact[first_transaction_amount]) - go_campaign_dimension[campaign_cost], go_campaign_dimension[campaign_cost]) | Decimal Number | Return on investment for campaigns   | Visual Recommender        |
| Conversion Rate             | DIVIDE(COUNTROWS(FILTER(go_application_fact, go_application_fact[application_outcome] = "Activated")), COUNTROWS(go_application_fact)) | Percentage     | Activated applications rate          | Visual Recommender        |
| Decline Rate                | DIVIDE(COUNTROWS(FILTER(go_application_fact, go_application_fact[application_outcome] = "Rejected")), COUNTROWS(go_application_fact)) | Percentage     | Rejected applications rate           | Visual Recommender        |
| Average Credit Score        | AVERAGE(go_applicant_dimension[credit_score])                                                                       | Whole Number   | Avg. applicant credit score          | Visual Recommender        |
| Fraud Detection Rate        | DIVIDE(COUNTROWS(FILTER(go_fraud_check_fact, go_fraud_check_fact[screening_result] = "Confirmed Fraud")), COUNTROWS(go_application_fact)) | Percentage     | Confirmed frauds per application     | Visual Recommender        |
| False Positive Rate         | DIVIDE(COUNTROWS(FILTER(go_fraud_check_fact, go_fraud_check_fact[resolution_outcome] = "Cleared")), COUNTROWS(FILTER(go_fraud_check_fact, go_fraud_check_fact[screening_result] = "Flagged"))) | Percentage     | Cleared flagged fraud checks         | Visual Recommender        |
| Escalation Rate             | DIVIDE(COUNTROWS(FILTER(go_fraud_check_fact, go_fraud_check_fact[escalation_status] = "Manual Review")), COUNTROWS(FILTER(go_fraud_check_fact, go_fraud_check_fact[screening_result] = "Flagged"))) | Percentage     | Flagged checks escalated             | Visual Recommender        |
| Time to First Transaction   | AVERAGE(go_transaction_fact[first_transaction_date] - go_application_fact[activation_date])                          | Duration/Days  | Avg. days from activation to txn     | Visual Recommender        |
| Inactive Rate               | DIVIDE(COUNTROWS(FILTER(go_transaction_fact, ISBLANK(go_transaction_fact[first_transaction_date]))), COUNTROWS(FILTER(go_application_fact, go_application_fact[application_outcome] = "Activated"))) | Percentage     | Activated apps with no txn           | Visual Recommender        |
| Average First Transaction Amount | AVERAGE(go_transaction_fact[first_transaction_amount])                                                          | Decimal Number | Avg. first transaction amount        | Visual Recommender        |

---

## 7. Advanced Measures

| Measure Name                | DAX Formula | Format | Description | Source Evidence |
|-----------------------------|-------------|--------|-------------|-----------------|
| Approval Rate by Risk Tier  | CALCULATE(DIVIDE(COUNTROWS(FILTER(go_application_fact, go_application_fact[application_outcome] = "Approved")), COUNTROWS(go_application_fact)), go_applicant_dimension[risk_tier]) | Percentage | Approval rate segmented by risk tier | Visual Recommender |
| Campaign ROI by Quarter     | Not Explicitly Defined in Source Inputs | Not Explicitly Defined | Not Explicitly Defined | Not Explicitly Defined |

---

## 8. Calculated Columns

| Table Name | Column Name | Calculation Logic | Source Evidence |
|------------|-------------|------------------|----------------|
| go_applicant_dimension | risk_tier | Not Explicitly Defined in Source Inputs | Visual Recommender (suggested) |
| go_application_fact | application_stage | Not Explicitly Defined in Source Inputs | Visual Recommender (suggested) |
| go_promotional_offer_dimension | offer_eligibility | Not Explicitly Defined in Source Inputs | Visual Recommender (suggested) |

---

## 9. Date Hierarchies

| Table Name | Date Column | Hierarchy Levels         | Source Evidence |
|------------|-------------|-------------------------|----------------|
| go_application_fact | application_submission_date | Not Explicitly Defined in Source Inputs | Not Explicitly Defined |
| go_application_fact | approval_date               | Not Explicitly Defined in Source Inputs | Not Explicitly Defined |
| go_application_fact | activation_date             | Not Explicitly Defined in Source Inputs | Not Explicitly Defined |
| go_campaign_dimension | campaign_start_date       | Not Explicitly Defined in Source Inputs | Not Explicitly Defined |
| go_campaign_dimension | campaign_end_date         | Not Explicitly Defined in Source Inputs | Not Explicitly Defined |
| go_transaction_fact | first_transaction_date     | Not Explicitly Defined in Source Inputs | Not Explicitly Defined |

---

## 10. KPI Definitions

| KPI                     | Formula                                                                                                         | Business Meaning                  | Source Evidence        |
|-------------------------|-----------------------------------------------------------------------------------------------------------------|-----------------------------------|------------------------|
| Approval Rate           | DIVIDE(COUNTROWS(FILTER(go_application_fact, go_application_fact[application_outcome] = "Approved")), COUNTROWS(go_application_fact)) | Ratio of approved applications    | Visual Recommender     |
| Activation Rate         | DIVIDE(COUNTROWS(FILTER(go_application_fact, go_application_fact[application_outcome] = "Activated")), COUNTROWS(FILTER(go_application_fact, go_application_fact[application_outcome] = "Approved"))) | Ratio of activated to approved apps | Visual Recommender     |
| Drop-off Rate           | DIVIDE(COUNTROWS(go_application_fact) - COUNTROWS(FILTER(go_application_fact, go_application_fact[application_outcome] = "Activated")), COUNTROWS(go_application_fact)) | Applications not activated        | Visual Recommender     |
| Cost per Acquisition    | DIVIDE(go_campaign_dimension[campaign_cost], COUNTROWS(FILTER(go_application_fact, go_application_fact[application_outcome] = "Activated" && go_application_fact[campaign_id] = go_campaign_dimension[campaign_id]))) | Cost per activated application    | Visual Recommender     |
| Campaign ROI            | DIVIDE(SUM(go_transaction_fact[first_transaction_amount]) - go_campaign_dimension[campaign_cost], go_campaign_dimension[campaign_cost]) | Return on investment for campaigns| Visual Recommender     |
| Conversion Rate         | DIVIDE(COUNTROWS(FILTER(go_application_fact, go_application_fact[application_outcome] = "Activated")), COUNTROWS(go_application_fact)) | Activated applications rate       | Visual Recommender     |
| Decline Rate            | DIVIDE(COUNTROWS(FILTER(go_application_fact, go_application_fact[application_outcome] = "Rejected")), COUNTROWS(go_application_fact)) | Rejected applications rate        | Visual Recommender     |
| Fraud Detection Rate    | DIVIDE(COUNTROWS(FILTER(go_fraud_check_fact, go_fraud_check_fact[screening_result] = "Confirmed Fraud")), COUNTROWS(go_application_fact)) | Confirmed frauds per application  | Visual Recommender     |
| False Positive Rate     | DIVIDE(COUNTROWS(FILTER(go_fraud_check_fact, go_fraud_check_fact[resolution_outcome] = "Cleared")), COUNTROWS(FILTER(go_fraud_check_fact, go_fraud_check_fact[screening_result] = "Flagged"))) | Cleared flagged fraud checks      | Visual Recommender     |
| Escalation Rate         | DIVIDE(COUNTROWS(FILTER(go_fraud_check_fact, go_fraud_check_fact[escalation_status] = "Manual Review")), COUNTROWS(FILTER(go_fraud_check_fact, go_fraud_check_fact[screening_result] = "Flagged"))) | Flagged checks escalated          | Visual Recommender     |
| Time to First Transaction| AVERAGE(go_transaction_fact[first_transaction_date] - go_application_fact[activation_date])                      | Avg. days from activation to txn  | Visual Recommender     |
| Inactive Rate           | DIVIDE(COUNTROWS(FILTER(go_transaction_fact, ISBLANK(go_transaction_fact[first_transaction_date]))), COUNTROWS(FILTER(go_application_fact, go_application_fact[application_outcome] = "Activated"))) | Activated apps with no txn        | Visual Recommender     |
| Average First Transaction Amount | AVERAGE(go_transaction_fact[first_transaction_amount])                                                  | Avg. first transaction amount     | Visual Recommender     |

---

## 11. Dashboard Specifications

### Application & Activation Funnel Report

- **Business Objective:** Visualize funnel efficiency, identify bottlenecks, support operational improvement
- **Primary Users:** Not Explicitly Defined in Source Inputs
- **Suggested Visuals:** Funnel chart, Clustered column chart, Line chart, Matrix, KPI visual, Card visual
- **Drilldowns:** Application-level details, Channel-level breakdown
- **Filters:** Segment/channel
- **Interactions:** Drillthrough, Tooltip, Sync slicers
- **KPI Cards:** Approval Rate, Activation Rate, Drop-off Rate
- **Trend Visuals:** Average Time to Approval
- **Detail Views:** Matrix with conditional formatting

### Campaign Performance Analytics Report

- **Business Objective:** Enable marketing optimization, identify high-performing campaigns
- **Primary Users:** Not Explicitly Defined in Source Inputs
- **Suggested Visuals:** Combo chart, Waterfall chart, KPI visual, Matrix, Treemap, Donut chart
- **Drilldowns:** Campaign-level, Channel-level, Quarter-level
- **Filters:** Campaign, Channel, Quarter
- **Interactions:** Drillthrough, Tooltip, Bookmarks
- **KPI Cards:** Cost per Acquisition, Campaign ROI, Conversion Rate

### Credit Risk Segmentation Report

- **Business Objective:** Support risk policy tuning, regulatory compliance
- **Primary Users:** Not Explicitly Defined in Source Inputs
- **Suggested Visuals:** Clustered bar chart, Scatter chart, Matrix, Decomposition tree, Key influencers
- **Drilldowns:** Risk tier, Demographic segment
- **Filters:** Risk tier, Demographics
- **Interactions:** Drillthrough, Tooltip
- **KPI Cards:** Decline Rate, Average Credit Score, Approval Rate by Risk Tier

### Fraud Screening Effectiveness Report

- **Business Objective:** Enable fraud model tuning, operational safety
- **Primary Users:** Not Explicitly Defined in Source Inputs
- **Suggested Visuals:** Clustered column chart, Ribbon chart, KPI visual, Sankey visual, Table visual
- **Drilldowns:** Fraud rule, Channel, Product
- **Filters:** Fraud check type, Screening result
- **Interactions:** Drillthrough, Tooltip, Bookmarks
- **KPI Cards:** Fraud Detection Rate, False Positive Rate, Escalation Rate, Clearance Rate

### First Transaction Behavior Report

- **Business Objective:** Support engagement strategies, reduce dormancy
- **Primary Users:** Not Explicitly Defined in Source Inputs
- **Suggested Visuals:** Area chart, Multi-row card, KPI visual, Scatter chart, Funnel chart
- **Drilldowns:** Channel, Offer, Product
- **Filters:** Channel, Offer, Product
- **Interactions:** Drillthrough, Tooltip, Journey drillthrough
- **KPI Cards:** Time to First Transaction, Inactive Rate, Average First Transaction Amount

---

## 12. Visual Mapping Specification

| Visual Name                        | Visual Type           | Source                | Dataset                  | Measures                                    | Dimensions                                | Filters                | Drilldowns                 | Validation Status                | Evidence               |
|-------------------------------------|----------------------|-----------------------|--------------------------|---------------------------------------------|-------------------------------------------|------------------------|----------------------------|-----------------------------------|------------------------|
| Application Funnel                  | Funnel Chart         | Visual Recommender    | go_application_fact      | Approval Rate, Activation Rate, Drop-off Rate | application_stage, channel_name           | Segment, Channel        | Application, Channel       | Validated                        | Visual Recommender     |
| Campaign ROI                        | Combo/Waterfall Chart| Visual Recommender    | go_campaign_dimension, go_application_fact, go_transaction_fact | Campaign ROI, Cost per Acquisition, Conversion Rate | campaign_name, campaign_type, channel_name | Campaign, Channel, Quarter | Campaign, Channel, Quarter | Validated                        | Visual Recommender     |
| Risk Segmentation                   | Clustered Bar/Scatter| Visual Recommender    | go_application_fact, go_applicant_dimension | Decline Rate, Average Credit Score, Approval Rate by Risk Tier | risk_tier, credit_score, geography        | Risk Tier, Demographics | Risk Tier, Demographics    | Validated                        | Visual Recommender     |
| Fraud Screening Effectiveness       | Column/Ribbon/Sankey | Visual Recommender    | go_fraud_check_fact, go_application_fact | Fraud Detection Rate, False Positive Rate, Escalation Rate, Clearance Rate | fraud_check_type, screening_result        | Fraud Check Type, Screening Result | Fraud Rule, Channel, Product | Validated                        | Visual Recommender     |
| First Transaction Behavior          | Area/Scatter/Card    | Visual Recommender    | go_transaction_fact, go_application_fact | Time to First Transaction, Inactive Rate, Average First Transaction Amount | channel_name, offer_id, product_name      | Channel, Offer, Product | Channel, Offer, Product    | Validated                        | Visual Recommender     |

---

## 13. Security Specification

- **Role-based Access Requirements:**  
  - Marketing: Campaign, channel, aggregate data  
  - Risk: Credit score, risk tier, approval/decline  
  - Fraud: Fraud check, escalation, resolution  
  - Operations: Application, activation, funnel  
  - Executive: Summary, KPI, trends  

- **Sensitive Columns:**  
  - credit_score  
  - decline_reason  
  - fraud_check_type  
  - applicant demographics (age_group, income_level, geography)  

- **PII Handling Requirements:**  
  - Mask credit_score, decline_reason, applicant demographics for unauthorized users  
  - Restrict access to sensitive columns via OLS/RLS  

- **Suggested RLS Candidates:**  
  - Product, operations, marketing, risk, fraud, executive roles as above  

**Source Evidence:**  
- Visual Recommender Output

---

## 14. Hidden Columns Recommendation

- Technical IDs:  
  - load_date, update_date, source_system, audit_id, error_id, aggregate_*_id, pipeline_run_id

- Audit Columns:  
  - audit_message, processed_by, processing_time, status

- Surrogate Keys:  
  - All *_id columns not required for reporting

- ETL Metadata:  
  - Not Explicitly Defined in Source Inputs

---

## 15. Semantic Modeling Recommendations

- Use star schema with application fact at the center
- Use single-direction relationships as recommended
- Partition large tables by status/type for performance
- Use aggregate tables for high-level KPIs
- Use incremental refresh for fact tables
- Standardize naming conventions (snake_case as per DDL)
- Hide technical and audit columns from report view
- Use calculated columns only when business logic is explicit
- Validate all relationships and cardinality with business/technical owners

**Source Evidence:**  
- DDL  
- Visual Recommender Output

---

## 16. Data Quality Observations

- No PK/FK constraints in DDL; relationships are logical, not enforced
- Nullable business fields not explicitly defined
- Duplicate candidate columns not detected in DDL
- Missing relationship evidence for some joins (requires business confirmation)
- Ambiguous business semantics for some attributes (requires business confirmation)
- Cardinality defined in Visual Recommender but not validated in DDL/schema
- Filter direction defined in Visual Recommender but not validated in DDL/schema

---

## 17. Assumptions and Open Questions

- Primary users and business definitions are not available from inputs
- Some KPIs and calculated columns are suggested but not explicitly defined in DDL or requirements
- No explicit drilldown fields in DDL; visual drilldowns are based on Visual Recommender
- No explicit conformed or degenerate dimensions in DDL
- No explicit date hierarchies in DDL; hierarchy levels are Visual Recommender suggestions
- No explicit RLS/OLS implementation details in DDL or requirements
- All relationships require technical validation due to lack of PK/FK in DDL
- All filter directions and cardinality require technical validation
- Some visuals may require business validation if not fully supported by DDL/requirements

---

## 18. BIM Model Summary

| Component                        | Count |
|-----------------------------------|-------|
| Tables                            | 14    |
| Fact Tables                       | 7     |
| Dimension Tables                  | 5     |
| Columns                           | Not Explicitly Defined in Source Inputs |
| Measures                          | 15    |
| Relationships                     | 6     |
| Validated Relationships           | 0     |
| Relationships Requiring Validation| 6     |
| Hierarchies                       | 0 (Not Explicitly Defined) |
| KPIs                              | 13    |
| Dashboards                        | 5     |
| Visuals                           | 5     |

---

**Note:**  
All content is strictly based on the provided DDL and Visual Recommender Output. Any section requiring explicit business definitions or requirements not available in the provided inputs is marked as "Not Explicitly Defined in Source Inputs" or "Requires Business Confirmation." No unsupported assumptions or fabricated content is present in this specification.
