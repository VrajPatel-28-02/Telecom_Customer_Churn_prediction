Telecom Data Analysis — Google-Oriented Portfolio Case Study

Project Overview

This project provides a comprehensive analysis of 243,553 telecom customers to identify the strongest drivers and concentration points of churn. Rather than presenting generic exploratory data analysis, this work demonstrates how to transform raw customer data into actionable business insights through a rigorous analytical pipeline. The project explicitly addresses data quality challenges and validates findings with SQL-based analysis, resulting in a decision-ready dashboard that helps prioritize retention actions by segment, geography, and usage behavior.
Core Research Question

How can we identify and prioritize high-risk customer segments to maximize retention impact, while accounting for data quality limitations and operational constraints?
Dataset Characteristics

- Size: 243,553 customer records with 15 fields
- Key Fields:
  - customer_id, telecom_partner, gender, age, state, city, pincode, date_of_registration
  - num_dependents, estimated_salary, calls_made, sms_sent, data_used, churn
- Churn Distribution: 48,827 churned customers (20.05% overall churn rate)
- Telecom Partners: 4 providers (Airtel, Reliance Jio, Vodafone, BSNL)
- Geography: 28 states with varying customer distributions
- Temporal Scope: Registration dates spanning January 2020 to May 2023
Critical Data Quality Consideration

The dataset contains suspicious negative values in usage metrics:
- 6,713 negative values in calls_made
- 7,375 negative values in sms_sent
- 6,050 negative values in data_used
This project addresses these issues through a documented data quality treatment process rather than silently replacing values.
Analytical Methodology

The project follows a business-focused analytical workflow:
1. Business Problem Definition

Churn directly reduces customer lifetime value and makes acquisition spend less efficient. The analysis focuses on identifying actionable insights to prioritize retention efforts.
2. Data Quality Assessment

- Verified schema and data structure
- Documented data quality limitations (negative usage values)
- Created clean and raw datasets with clear documentation
- Implemented data quality flags to track treatment impact
3. Core Analysis Approach

- Descriptive Analysis: Established customer baseline (churn rate, partner distribution, geography coverage)
- Diagnostic Analysis: Identified where churn over-indexes by segment (geography, partner, age)
- Statistical Validation: Applied confidence intervals and significance testing where appropriate
- Segment Prioritization: Developed a risk matrix showing customer segment size versus churn rate
4. Visualization Strategy

- Prioritized clarity and business relevance over quantity
- Focused on 8-10 purposeful visualizations
- Used SQL to create analytical foundation for dashboard
- Implemented Looker Studio for stakeholder-ready presentation
Project Architecture


RAW DATA
│
├───> Data Audit & Quality
│     │
│     ├── Data Dictionary
│     ├── Missingness Report
│     └── Usage Value Treatment
│
└───> Analytical Processing
      │
      ├── SQL Profiling
      │     ├── Customer Baseline
      │     ├── Partner Churn Analysis
      │     └── Geography Analysis
      │
      ├── Feature Engineering
      │     ├── Age Bands
      │     ├── Usage Bands
      │     └── Registration Cohorts
      │
      ├── Diagnostic Analysis
      │     ├── Segment Comparison
      │     └── Risk Matrix
      │
      └── Dashboard Layer
            │
            ├── Executive Overview (KPIs)
            ├── Customer Segmentation
            └── Data Quality Methodology


Technical Stack

Core Tools

- Cloud Warehouse: BigQuery (demonstrates cloud-scale analytical SQL)
- SQL Engine: Standard SQL (primary analytical language)
- Data Profiling & Analysis: Python with Pandas
- Visualization: Plotly (interactive analytical plots)
- Dashboard Presentation: Looker Studio (Google-centric reporting)
- Data Modeling: SQLite (local development modeling)
Workflow Structure

- Data Quality Assessment - Documented data issues and treatment
- SQL Profiling - Built core customer segmentation tables
- Feature Engineering - Created meaningful business segments
- Diagnostic Analysis - Compared churn patterns across segments
- Statistical Validation - Applied confidence intervals where relevant
- Decision Dashboard - Prioritized actionable segments
Key Findings

Churn Baseline

- Overall portfolio churn rate: 20.05%
- Partner-specific churn rates:
  - Airtel: 20.37% (60,905 customers)
  - Reliance Jio: 20.02% (61,123 customers)
  - Vodafone: 19.95% (60,802 customers)
  - BSNL: 19.86% (60,723 customers)
Geographic Analysis

- Top states with highest churn rates:
  - Jharkhand: 21.12% (1,849 of 8,755 customers)
  - Karnataka: 20.71% (1,832 of 8,845 customers)
  - Mizoram: 20.65% (1,794 of 8,689 customers)
Age Segment Analysis

- Age bands showing similar churn rates (19.65% to 20.36%)
- No single age segment demonstrates substantially higher churn
Data Quality Impact

- Treatment of negative usage values changed the distribution of key metrics
- Documented impact on churn analysis (with sensitivity analysis)
Business Recommendations

Prioritized Action Plan

The project identifies high-value segments where retention efforts could maximize impact:
- High-Risk Geographic Zones - States showing above-average churn rates combined with sufficient customer volumes
- High-Risk Partners - Identifying partners where churn rates exceed portfolio averages
- Usage-Based Segments - Customers with low usage patterns that over-index on churn
Recommended Implementation

- Target retention resources to segments with highest churn rate and customer volume
- Use usage pattern insights to design tailored retention offers
- Implement tracking to measure retention program effectiveness
Methodological Strengths

- Transparent Data Treatment - Documented cleaning rules and impact analysis
- SQL-Driven Analytics - Core analysis built on reproducible SQL queries
- Business-Centric Visualization - Dashboards designed for decision-making
- Segment Prioritization - Focus on actionable segments rather than merely reporting averages
- Statistical Validation - Confidence intervals used where appropriate
Conclusion

This project demonstrates how to transform complex customer data into actionable business insights using a rigorous analytical approach. The focus is not on generating charts but on solving business problems with data-driven recommendations that can improve retention strategy effectiveness. The framework can be applied to similar business intelligence challenges in various industries.
