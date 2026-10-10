# 🏦 IDFC Bank Loan Analysis Dashboard | Power BI

**Project by Saquib Alam**

## 📌 Project Overview

The **IDFC Bank Loan Analysis Dashboard** is a Business Intelligence project developed using Microsoft Power BI to analyze loan-related data and transform raw CSV data into meaningful, interactive visual reports.

The main objective of this project is to understand loan application performance, approval trends, loan distribution, outstanding balances, repayment status, customer profiles, and potential credit risk patterns.

I imported the loan dataset into Power BI, explored the available columns, prepared the data, created important measures, and designed interactive visualizations to make the analysis easier to understand.

This project demonstrates practical skills in data analytics, data preparation, DAX calculations, interactive dashboard development, and business reporting.

## 📊 Dashboard Preview

### Page 1: Loan Overview Dashboard
<img src="Bank Overview Dashboard.png" width="100%"><br><br>

### Page 2: Loan Performance Analysis
<img src="Loan Performance Dashboard.png" width="100%"><br><br>

### Page 3: Customer & Risk Analysis
<img src="Customer And Risk Dashboard.png" width="100%"><br><br>

### Page 4: Branch & Geographic Analysis
<img src="Branch Analysis Dashboard.png" width="100%"><br><br>


## 🎯 Project Objectives

- Analyze total loan applications and approval performance.
- Calculate important banking and lending KPIs.
- Compare loan amounts across different loan categories.
- Analyze approved, rejected, active, and closed loans using the available status fields.
- Track outstanding loan amounts and repayment-related indicators.
- Explore customer income, credit score, employment type, and debt-to-income ratio.
- Identify patterns in risk categories and default rates.
- Compare loan performance across branches, cities, and states.
- Develop an interactive Power BI dashboard using slicers, filters, and cross-highlighting.
- Present complex loan data in a clear and professional format.

## 🛠️ Tools & Technologies Used

- **Microsoft Power BI Desktop** — dashboard development and data visualization.
- **Power Query** — data transformation and preparation.
- **DAX (Data Analysis Expressions)** — calculated measures and KPIs.
- **CSV / Excel** — source data handling.
- **GitHub** — project documentation and versioned portfolio presentation.

## 📂 Dataset Overview

The project uses CSV-based loan data containing information related to loan applications, customer profiles, loan amounts, approval status, payment status, risk categories, and geographic locations.

The Power BI report references a main table named `Loan_Clean Data`.

### Important Fields

| Field | Description |
|---|---|
| Loan_ID | Unique loan identifier |
| Application_Status | Application decision status |
| Loan_Status | Current loan status |
| Payment_Status | Payment-related status |
| Loan_Type | Category of loan |
| Loan_Amount | Loan amount recorded |
| Outstanding_Amount | Remaining outstanding balance |
| Approved Loan | Approved loan indicator or field, depending on the model |
| Interest_Rate_% | Loan interest rate |
| Credit_Score | Customer credit score |
| Income_Group | Customer income category |
| Employment_Type | Customer employment classification |
| Employer_Type | Employer classification |
| Gender | Customer gender category |
| DTI | Debt-to-income ratio |
| Application month | Application month |
| Application Year | Application year |
| Disbursement_Date | Loan disbursement date |
| State | State associated with the record |
| City | City associated with the record |
| Branch | Branch associated with the record |
| Risk_Category | Customer or loan risk classification |


## 🧹 Data Preparation & Power Query

Data preparation is an important part of the project because accurate analysis depends on reliable and consistently formatted data.

The data preparation workflow includes checking column names, validating data types, reviewing missing or invalid values, checking duplicates using the appropriate business key, and standardizing category values where necessary.

### Key data preparation steps

1. Imported the CSV dataset into Power BI Desktop.
2. Examined the available columns and their data types.
3. Reviewed missing values, blank records, and data quality issues.
4. Checked duplicate loan identifiers and assessed whether records represented genuine duplicates.
5. Verified numeric fields such as loan amount, interest rate, income, and outstanding amount.
6. Reviewed date fields and their formats.
7. Checked category consistency in loan types, statuses, branches, and risk classifications.
8. Prepared the data for analysis and visualization.
9. Validated the results of the data preparation process.

**Note:** The steps above describe the recommended workflow. Document only the specific transformations you actually performed in Power Query as completed cleaning activities.

## 📈 Dashboard Pages & Visualizations

### 1. Loan Overview Dashboard

This page provides a high-level view of loan application and portfolio performance.

**Key elements:**
- Total Applications
- Approved Loans
- Approval Rate
- Total Loan Amount
- Total Outstanding Amount
- Loan application status distribution
- Loan status analysis
- Summary-level lending indicators

**Purpose:** To provide a quick overview of the loan portfolio and help users understand application outcomes and lending performance.

### 2. Loan Performance Analysis

This page focuses on loan categories, application trends, and loan amount comparisons.

**Key elements:**
- Loan Amount by Loan Type
- Approval Rate by Loan Type
- Monthly Application Trends
- Approved Loan Amount Analysis
- Loan Status Distribution
- Loan performance comparisons

**Purpose:** To understand which loan categories contribute to lending activity and how application outcomes vary across categories and time periods.

### 3. Customer & Risk Analysis

This page explores customer-related indicators and potential loan risk patterns.

**Key elements:**
- Average Income
- Average Credit Score
- Average DTI
- Risk Category Distribution
- Default Rate by Risk Category
- Loan Analysis by Employment Type
- Loan Analysis by Income Group
- Credit Score and Interest Rate Comparisons

**Purpose:** To explore how customer characteristics and risk categories relate to observed lending outcomes.

### 4. Branch & Geographic Analysis

This page compares lending performance across branches and geographic locations.

**Key elements:**
- Loan Amount by Branch
- Applications by Branch
- Approval Rate by Branch
- Outstanding Amount by Branch
- Default Rate by Branch
- State-Level Loan Distribution
- Geographic Lending Analysis

**Purpose:** To identify differences in lending activity and portfolio indicators across locations.

*These sections describe the intended analytical areas. Match the final list to the actual visuals present on each report page.*

## 🔑 Key Performance Indicators (KPIs)

The dashboard focuses on important metrics for understanding loan portfolio performance.

| KPI | Business Purpose |
|---|---|
| Total Applications | Measures the number of recorded loan applications |
| Approved Loans | Measures the number of approved loans |
| Approval Rate | Shows the proportion of applications approved |
| Total Loan Amount | Measures the sum of loan amounts |
| Approved Loan Amount | Measures the amount associated with approved loans |
| Average Loan Amount | Shows the average loan amount |
| Total Outstanding Amount | Measures remaining outstanding balances |
| Total Amount Paid | Measures recorded payments, if available |
| Defaulted Loans | Counts loans classified as defaulted |
| Default Rate | Measures the proportion of loans classified as defaulted |
| Overdue Loans | Counts loans classified as overdue |
| Active Loans | Counts loans marked active |
| Closed Loans | Counts loans marked closed |
| Total Customers | Counts customers represented in the data |
| Average Income | Measures average customer income |
| Average Credit Score | Shows the average credit score |
| Average DTI | Shows average debt-to-income ratio |
| Average Interest Rate | Measures the average interest rate |
| Average EMI | Measures the average EMI, if available |

## 🧮 DAX Measures

DAX measures make it possible to calculate KPIs dynamically and update results according to slicers and filters.

The following are example measures. Confirm that the column names, status values, and definitions match your actual Power BI model before using them.

### Total Applications

```DAX
Total Applications =
DISTINCTCOUNT('Loan_Clean Data'[Loan_ID])
```

### Approved Loans

```DAX
Approved Loans =
CALCULATE(
    DISTINCTCOUNT('Loan_Clean Data'[Loan_ID]),
    'Loan_Clean Data'[Application_Status] = "Approved"
)
```

### Approval Rate

```DAX
Approval Rate =
DIVIDE(
    [Approved Loans],
    [Total Applications],
    0
)
```

Format this measure as a percentage in Power BI.

### Total Loan Amount

```DAX
Total Loan Amount =
SUM('Loan_Clean Data'[Loan_Amount])
```

### Total Outstanding Amount

```DAX
Total Outstanding Amount =
SUM('Loan_Clean Data'[Outstanding_Amount])
```

### Average Loan Amount

```DAX
Average Loan Amount =
AVERAGE('Loan_Clean Data'[Loan_Amount])
```

### Average Credit Score

```DAX
Average Credit Score =
AVERAGE('Loan_Clean Data'[Credit_Score])
```

### Average DTI

```DAX
Average DTI =
AVERAGE('Loan_Clean Data'[DTI])
```

**Important:** These are sample formulas, not a verified export of every measure in your PBIX file. Use the actual formulas from your Power BI model in the final documentation. Ensure that application counts, loan counts, approval rates, and default rates use the correct denominator and business definition.

## 🔍 Business Questions Answered

The dashboard supports investigation of questions such as:

1. How many loan applications are recorded?
2. What proportion of applications have been approved?
3. Which loan types contribute the most to total loan value?
4. How does approval performance differ by loan type?
5. How do loan applications and approved amounts change over time?
6. How much outstanding loan balance is recorded?
7. Which risk categories have higher observed default rates?
8. How do credit scores and DTI vary across customer groups?
9. Which branches contribute the largest loan amounts?
10. How does loan performance vary across states and cities?

## 💡 Key Insights & Findings

The dashboard allows users to investigate:

- Loan categories contributing the highest total loan amounts.
- Differences between application volume and approval performance.
- Monthly changes in loan applications and approved amounts.
- Outstanding balances across loan categories and branches.
- Default and overdue patterns across risk categories.
- Differences in customer income, credit score, and DTI.
- Geographic variations in lending activity.

**Important:** Add quantified findings from your actual report before publishing. For example, include the loan category with the highest loan amount, the overall approval rate, or the branch with the largest outstanding balance only after verifying the corresponding values in Power BI.

## 🎛️ Interactivity & Filters

The dashboard uses Power BI's interactive capabilities to make analysis more flexible.

- Slicers filter the report by available dates, loan type, branch, and customer attributes.
- Chart selections can cross-filter or highlight related visuals.
- Tables support detailed comparisons.
- Geographic visuals provide a location-based view of lending activity.
- KPI cards update according to the selected filter context.

These interactions help users explore the data from multiple perspectives without creating a separate report for every question.

## 📁 Repository Structure

```text
IDFC-Bank-Loan-Analysis/
│
├── README.md
├── Banking Power BI.pbix
├── data/
│   └── loan_data_sample.csv
│
└── images/
    ├── dashboard_overview.png
    ├── dashboard_performance.png
    ├── dashboard_risk.png
    └── dashboard_branch_location.png
```

The folder and image names above are suggested. Replace them with your actual filenames. Include the CSV only if you have permission to distribute it and it contains no confidential customer information.

## ▶️ How to Use the Project

1. Download or clone the GitHub repository.
2. Install Microsoft Power BI Desktop.
3. Open `Banking Power BI.pbix`.
4. If a data source prompt appears, connect the report to the correct CSV file.
5. Refresh the dataset and resolve any missing-source or data-type errors.
6. Navigate through the report pages.
7. Use slicers and chart selections to explore loan performance and customer risk indicators.

## ⚠️ Limitations & Responsible Use

- This is a portfolio analytics project, not an official banking system.
- Confirm the dataset's source and usage permissions before identifying it as bank-specific data.
- Clearly label synthetic, sample, or anonymized data.
- Data quality issues may affect calculated metrics and conclusions.
- Correlation between customer attributes and loan outcomes does not prove causation.
- Approval and default rates depend on consistent definitions and appropriate denominators.
- The dashboard should not be used alone to make credit eligibility or lending decisions.
- Do not publish private customer details, credentials, or confidential banking data.

## 🏁 Conclusion

The **IDFC Bank Loan Analysis Dashboard** demonstrates how loan-related CSV data can be analyzed and presented through Microsoft Power BI.

The project brings together loan application analysis, approval performance, portfolio indicators, customer characteristics, risk exploration, and branch-level comparisons in an interactive reporting environment.

Through Power Query, DAX measures, KPI cards, charts, tables, maps, and slicers, this project demonstrates practical skills in data preparation, business intelligence, data visualization, and analytical reporting.

It also provides a foundation for further improvements, including validated business insights, additional time-based analysis, a documented data model, and more detailed risk monitoring.

## 👨‍💻 About Me

**Saquib Alam**  
Aspiring Data Analyst | Power BI | Excel | SQL | Data Visualization | Business Intelligence

I am interested in transforming raw data into meaningful insights through data analysis, dashboard development, and business reporting. This project reflects my practical experience with Power BI, data preparation, KPI development, and interactive visualizations.

### 📬 Connect With Me

- **Email:** khansaquib765@gmail.com
- **LinkedIn:** www.linkedin.com/in/saquib-khan-b321ab308
- **GitHub:** khansaquib765-crypto


⭐ If you find this project useful, consider starring the repository.

**Thank you for visiting my project!**
