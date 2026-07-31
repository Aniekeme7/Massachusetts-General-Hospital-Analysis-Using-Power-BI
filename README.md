# Massachusetts-General-Hospital-Analysis-Using-Power-BI
Analysis of healthcare data from Massachusetts General Hospital to derive actionable insights for data-driven healthcare and operational decisions

## Introduction
This is a realistic synthetic dataset showing hospital data that contains records of patient demographic data, hospital encounters and admissions, procedures and insurance coverage.
Through DAX calculations, data modeling and interactive visuals, this analysis answers business questions such as:
- How many patients are readmitted within 30 days of discharge?
- What is the average cost by encounter class?
- Which encounter class receive the least insurance coverage?
- Do older patients experience longer hospital stays than younger patients?
- Are healthcare costs increasing over the years?

This analysis is important because it guides stakeholders to identify encounters and readmissions patterns, gaps in insurance coverage, and cost drivers. The insights uncovered drives a proactive response toreducing preventable readmissions, ensuring optimal resource utilization and ultimately, improving patient 
health outcomes. This project is designed to ensure that limited resources are well managed at controlled costs such that the quality of clinical care is not compromised.

## Project Description
The project covers data cleaning, analysis, visualisation and recommendations to address the highlighted business questions. This analysis of healthcare data examines the relationship between records containing patients, insurance, procedures and encounters data. It features an interactive dashboard with 3 
pages highlighting Patient Overview, Costs Analysis and Admissions Patterns. Insights and recommendations are also provided to guide stakeholders during 
decision-making.

## Project Aim
To analyze hospital data to answer key business questions such as 30-day readmission rates, average cost by encounter class, insurance coverage gaps, length-of-stay patterns across age groups, and cost trends over time. To use uncovered insights as the basis of recommendations that improve patient care and support better resource utilization.

## About the data
The dataset was sourced from Maven Analytics.
The analysis was conducted using a healthcare dataset from Massachusetts General Hospital. The dataset comprises six tables, of which five were used for this analysis: 

Patients Table - It contains 20 columns and 974 rows with the key column being Patient ID

Encounters Table - It contains 15 columns and 27,891 rows with the key column being Encounter ID

Procedures Table - It contains 10 columns and 47,701 rows 

Payers Table - It contains 7 columns and 10 rows with the key column being Payer ID

Dictionary Table - It contains 3 columns and 65 rows

The first four tables provided the patient, clinical, procedural, and insurance data required for the analysis, while the Dictionary table served as a reference for understanding the dataset's fields 
and definitions.

## Tools Used
Power BI

## Importing the Dataset
The CSV files were loaded into Power Query in Power BI for data cleaning. The cleaned data was then loaded into the data model to be used for report and visuals.

## Data Cleaning & Transformation
- Checking for and removing duplicate values
- Changing column names to more appropriate names
- Changing data types of columns 
- Removing irrelevant columns
- Standardizing the Name column

## Data Analysis
After data cleaning, the tables - patients, encounters, procedures and payers table were connected in a relational model using their key columns.

Calculated columns that were added to the dataset to answer the business questions include:

- Length of Stay: This is to determine the duration of an encounter.
- Pay Out of Pocket: This is the billing amount not covered by insurance, paid by the patient.
- 30-day Readmission Flag: This column indicates patients that were readmitted within 30 days.
- Age Group: This column separates the patients into different groups based on their age for demographic analysis.

The values on the KPI cards across the dashboard were derived using DAX calculations. Below are some DAX functions that were used during the analysis and the KPI
measures they were used to calculate:
-  **SUM** (Aggregating raw values across records) - Total Claim Cost, Total Pay out of pocket, Total Payer coverage
- **AVERAGE** (Calculating mean values) - Average Length of Stay
- **COUNTROWS** (Counts number of rows in a table) - Total patients, Total Encounters
- **DIVIDE** (Calculating safe ratios/percentages) - Readmission Rate, Payer Coverage % 
- **CALCULATE** (Applying filtered/conditional logic) - 30-Day Readmission Rate (filtered by date difference), Total Male and Total Female Patients (filtered by gender).

## Data Visualization

<img width="1449" height="815" alt="Dashboard Page 1" src="https://github.com/user-attachments/assets/a7ef543d-8950-45f7-91f2-fd9eac48ab22" />
<img width="1452" height="812" alt="Dashboard Page 2" src="https://github.com/user-attachments/assets/010e11cd-c5bd-4f03-95da-d7c1e02770a6" />
<img width="1450" height="814" alt="Dashboard Page 3" src="https://github.com/user-attachments/assets/c03f1748-6027-4eea-a1e6-6362581ab3ed" />


## Key Insights
### Dashboard Page 1 - Patients
- 920 out of 974 patients are insured, indicating high dependence on health insurance
- Patient population is almost evenly distributed between 480 females and 494 males
- 820 patients are alive, showing positive patient outcomes overall.
- The majority of patients are from the White (680), Black (163), and Asian (91) populations
- Patient visits peaked in 2021 (649) and 2014 (630), while 2022 (103) recorded the lowest volume.

### Dashboard Page 2 - Costs
- Only 23 of 1,135 admissions were readmitted within 30 days, indicating a low overall readmission rate.
- Readmission rates were highest in 2011 (8.43%) and generally declined over the years, with slight increases in 2017 and 2019.
- Ambulatory (12.5k) and Outpatient (6.3k) recorded the highest encounter volumes.
- Patients aged 35–49 had the longest average length of stay (29.31 hours), while patients 65+ did not stay longer than younger patients.
- Patients aged 35–49 years recorded the highest readmission rate (2.78%), followed by 65 years and above (2.07%), while patients aged 50–64 years had the lowest readmission rate (1.50%).

### Dashboard Page 3 - Admissions
- The hospital recorded a total claim cost of $101.51M, with $31.10M covered by insurance and $70M paid out-of-pocket, indicating a high financial burden on patients.
- Total claim costs peaked in 2014 ($12.01M) and 2020 ($10.29M), while 2022 ($0.69M) recorded the lowest cost, likely because the dataset does not cover the full year.
- Ambulatory care ($36M) generated the highest total claim cost, followed by Urgent Care ($23M). This is likely due to the high volume of encounters in these services.
- Wellness (53.74%) and Inpatient (41.86%) had the highest insurance coverage, while Urgent Care (13.10%) had the lowest, leaving many urgent care patients without coverage.

## Recommendations
- Strengthen partnerships with major insurance providers and streamline insurance claim processing to reduce reimbursement delays.
- Continue preventive care, routine follow-up, and chronic disease management programs to maintain high survival outcomes.
- Maintain the current discharge protocol and closely monitor high-risk patients to sustain the low readmission rate.
- Review clinical practices during years with increased readmissions and implement targeted interventions where gaps are identified
- Allocate more staff and clinic resources to ambulatory and outpatient services to manage patient demand efficiently.
- Investigate the conditions contributing to longer stays among patients aged 35–49 and introduce standardized care pathways to reduce unnecessary delays.
- Prioritize post-discharge follow-up and patient education for patients aged 35–49 years to reduce avoidable readmissions.
- Review resource utilization and treatment costs in high-volume encounter classes to identify opportunities for cost optimization without affecting care quality.
  
The recommendations primarily focus on strengthening discharge planning, optimizing resource allocation, expanding insurance partnerships, and continuously monitoring patient and financial performance to improve healthcare quality, operational efficiency and financial sustainability.

## Limitations of the Dataset
In the Encounters dataset, it was not explicitly clear which patients were admitted or not. Using the encounter class and/or length of stay was found to be misleading because none of them proved to be a consistent indicator of the admission status. For that reason, only patients identified as inpatients were considered to be admitted patients because that was the only unambiguous and reliable data to support that classification.

## Conclusion
This project involved analyzing Massachusetts General Hospital's patient, admission, and cost data using Power BI to answer practical hospital questions — from readmission rates to insurance coverage gaps. 
The key insights are: 
- there was a low readmission rate as most patients aren't readmitted within 30 days
- Patients between 35-49 years had longer length of stay and returned more often.
- There were insurance coverage gaps for patients in the urgent care encounter class.
- A large share of costs is still paid out of pocket rather than covered by insurance.
  
The recommendations majorly center on improving discharge planning and follow-up care, optimizing resource allocation and utilization and strengthening insurance partnerships.
This project shows how data analytics can help hospital management use data for improving patient care while supporting operational and financial sustainability. 







