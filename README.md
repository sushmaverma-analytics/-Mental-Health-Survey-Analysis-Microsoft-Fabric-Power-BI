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


#🥉 Bronze Layer

## The Bronze layer stores the raw survey data.

-Table
dbo.survey_bronze

### The raw data is retained as the starting point for the transformation process.

# 🥈 Silver Layer

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
#🥇 Gold Layer

### The Gold layer prepares the cleaned data for analytical modeling.

-Table
- dbo.survey_gold

# A surrogate key was created for each survey response:

-survey_key

- This provides a unique warehouse identifier for each survey record.

# ⭐ Star Schema

### The Gold layer was transformed into a Star Schema consisting of one central fact table and multiple dimension tables.

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



#99🔑 Surrogate Keys

Surrogate keys were implemented in the dimension tables.

Examples:

country_key
gender_key
workplace_key
support_key
health_context_key
These keys connect the fact table with the corresponding dimensions.






