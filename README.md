# -Mental-Health-Survey-Analysis-Microsoft-Fabric-Power-BI
This project is an end-to-end  The project analyzes workplace mental health survey responses to understand patterns related to mental health treatment, workplace environment, employee support, gender, age, remote work, factors by follows a **Medallion Architecture (Bronze → Silver → Gold)** and implements a **Star Schema** for analytical reporting.


# The main objectives of this project are:

- Analyze workplace mental health survey responses
- Clean and transform raw survey data
- Build a Bronze, Silver, and Gold data architecture
- Create dimension and fact tables
- Implement surrogate keys
- Build a Star Schema
- Create a Microsoft Fabric Semantic Model
- Develop DAX measures for analysis
- Create interactive Power BI dashboards
- Identify patterns related to treatment, workplace support, gender, remote work, and mental health consequences

## 📊 Dataset

-The dataset contains **1,259 workplace mental health survey responses**.

# Key areas covered in the dataset include:

- Age
- Gender
- Country
- State
- Family History
- Mental Health Treatment
- Workplace Interference
- Company Size
- Remote Work
- Technology Company
- Benefits
- Care Options
- Wellness Programs
- Seeking Help
- Anonymity
- Leave
- Mental Health Consequences
- Physical Health Consequences
- Workplace Support


# 🏗️ Data Architecture

# The project follows the **Medallion Architecture**:

```text
                 RAW DATA
                    │
                    ▼
             ┌─────────────┐
             │   BRONZE    │
             │ Raw Survey  │
             └──────┬──────┘
                    │
                    ▼
             ┌─────────────┐
             │   SILVER    │
             │ Cleaned Data│
             └──────┬──────┘
                    │
                    ▼
             ┌─────────────┐
             │    GOLD     │
             │ Analytical  │
             │    Layer    │
             └──────┬──────┘
                    │
                    ▼
             ┌─────────────┐
             │ Dimensions  │
             │    +        │
             │    Fact     │
             └──────┬──────┘
                    │
                    ▼
             ┌─────────────┐
             │  Semantic   │
             │    Model    │
             └──────┬──────┘
                    │
                    ▼
             ┌─────────────┐
             │   Power BI  │
             │   Report    │
             └─────────────┘


# 🥉 Bronze Layer

##  The Bronze layer stores the raw survey data.

-Table
dbo.survey_bronze

### The raw data is retained as the starting point for the transformation process.

#  🥈 Silver Layer

### The Silver layer contains cleaned and standardized data.

-Table
-dbo.survey_silver
-Data cleaning performed
-Converted timestamp to DATETIME2
-Validated age values
-Standardized gender values
-Trimmed unnecessary spaces
-Converted blank values to NULL
-Standardized text fields
-Checked duplicate records
-Preserved the original survey information
# 🥇 Gold Layer

###  The Gold layer prepares the cleaned data for analytical modeling.

-Table
- dbo.survey_gold

# A surrogate key was created for each survey response:

-survey_key

- This provides a unique warehouse identifier for each survey record.

#⭐ Star Schema

###The Gold layer was transformed into a Star Schema consisting of one central fact table and multiple dimension tables.

-Fact Table
-fact_survey
-Dimension Tables
-dim_country
-dim_gender
-dim_date
-dim_workplace
-dim_support
-dim_health_context
-Model Structure
                  dim_date
                     │
                     │
dim_country ─── fact_survey ─── dim_gender
                     │
                     │
              dim_workplace
                     │
                     │
                dim_support
                     │
                     │
             dim_health_context



# 99🔑 Surrogate Keys

# Surrogate keys were implemented in the dimension tables.

Examples:

-country_key
-gender_key
-workplace_key
-support_key
-health_context_key
-These keys connect the fact table with the corresponding dimensions.

# What-If Parameter

## A What-If parameter was implemented to allow users to interactively change an analytical target.

-Treatment Rate Target

# The parameter allows the report user to adjust the treatment-rate target and observe the selected value dynamically.

### This demonstrates the use of:

-What-If Parameters
-SELECTEDVALUE
-Dynamic DAX
-Interactive Power BI analysis

# 📈 Power BI Report

-The final report contains 2 interactive pages.

# Page 1 — Mental Health Survey Analysis

## The Executive Overview page provides analysis of:

-Total Survey Responses
- Average Age
- Gender distribution
- Mental Health Consequences
-Treatment
- Country
- State
- Workplace Interference
- Year-over-year analysis
- YTD analysis

-Interactive filters include:

- Country
- Year
- Workplace Interference

# Page 2 — Workplace & Support Survey Analysis

-This page focuses on workplace conditions and employee support.

- Analysis includes:

- Workplace characteristics
- Remote Work
- Company Size
- Mental Health Treatment
- Workplace Support
- Key Influencers
- Decomposition Tree
- Interactive Treatment Rate Target

- Interactive filters include:

Support
Year
State
Survey
# Survey
#🔍 Data Quality Validation

## Data quality checks were performed after creating the fact table.

# Validation Results
- Bronze Records       : 1,259
- Fact Records         : 1,259
- Missing Date Keys    : 0
- Missing Country Keys : 0
- Missing Gender Keys  : 0
- Missing Workplace    : 0
- Missing Support      : 0
- Missing Health Keys  : 0

- This confirmed that all survey responses were successfully retained and matched with the required dimensions.

# 🛠️ Technologies Used
- Technology	Purpose
- Microsoft Fabric	Data platform
- Fabric Warehouse	Data warehouse
- T-SQL	Data transformation and modeling
- Medallion Architecture	Data engineering architecture
- Star Schema	Analytical data model
- Power BI	Data visualization
- DAX	Analytical calculations
- Semantic Model	Business/analytical layer
- GitHub	Portfolio and version control

# 🚀 Project Outcome

This project demonstrates an end-to-end analytics workflow starting from raw survey data and progressing through data cleaning, warehouse modeling, semantic modeling, DAX analysis, and interactive Power BI reporting.

It showcases practical knowledge of both Data Analytics and Data Engineering concepts using Microsoft Fabric.

# 👩‍💻 About Me

I am building my career in Data Analytics, with a focus on:

Microsoft Fabric
Power BI
SQL / T-SQL
Python
Tableau
Data Visualization
Data Warehousing

This project is part of my practical learning journey and portfolio development.








