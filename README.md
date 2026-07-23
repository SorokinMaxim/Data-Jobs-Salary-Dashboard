# Excel Salary Dashboard

<img width="1660" height="607" alt="main_page" src="https://github.com/user-attachments/assets/abc3928b-541a-4703-a7d3-876eeb01631c" />

## Introduction

This data jobs salary dashboard was created to see whether job seekers that investigated salaries for their desired jobs ensured they are being adequately compensated as of 2023. 

### Excel Skills Used

The following Excel skills were utilized for analysis:

- **Charts**
- **Formulas and Functions**
- **Data Validation**

### Data Jobs Dataset

The dataset used for this project contains real-world data science job information from 2023. It includes detailed information on:

- **Job titles**
- **Salaries**
- **Locations**
- **Skills**

## Dashboard Build

### Charts

#### Data Science Job Salaries - Bar Chart

<img width="827" height="457" alt="data_jobs_salaries" src="https://github.com/user-attachments/assets/bb635445-c2bf-4eef-85b0-d9027cd8c28e" />

- **Excel Features:** Utilized bar chart feature (with formatted salary values) and optimized layout for clarity.
- **Design Choice:** Horizontal bar chart for visual comparison of median salaries.
- **Data Organization:** Sorted job titles by descending salary for improved readability.
- **Insights Gained:** This enables quick identification of salary trends, noting that Senior roles and Engineers are higher-paying than Analyst roles.

#### Country Median Salaries - Map Chart

<img width="865" height="510" alt="data_jobs_per_country" src="https://github.com/user-attachments/assets/104c30aa-d73a-4583-8e00-764890aa48a2" />

- **Excel Features:** Utilized Excel's map chart feature to plot median salaries globally.
- **Design Choice:** Color-coded map to visually differentiate salary levels across regions.
- **Data Representation:** Plotted median salary for each country with available data.
- **Visual Enhancement:** Improved readability and immediate understanding of geographic salary trends.
- **Insights Gained:** Enables quick grasp of global salary disparities and highlights high/low salary regions.

### Formulas and Functions

#### Median Salary by Job Titles

```
=MEDIAN(
IF(
    (jobs[job_title_short]=A2)*
    (jobs[job_country]=country)*
    (ISNUMBER(SEARCH(type,jobs[job_schedule_type])))*
    (jobs[salary_year_avg]<>0),
    jobs[salary_year_avg]
)
)
```

- **Multi-Criteria Filtering:** Checks job title, country, schedule type, and excludes blank salaries.
- **Array Formula:** Utilizes `MEDIAN()` function with nested `IF()` statement to analyze an array.
- **Tailored Insights:** Provides specific salary information for job titles, regions, and schedule types.
- **Formula Purpose:** This formula populates the table below, returning the median salary based on job title, country, and type specified.

Background Table

<img width="496" height="392" alt="median_salary" src="https://github.com/user-attachments/assets/d81d1ab6-e726-4c98-8434-da8bb33d63a3" />

Dashboard Implementation

<img width="567" height="537" alt="jobs_chart" src="https://github.com/user-attachments/assets/fb8710f4-f20d-494a-a108-7551adcd2dc4" />

#### Count of Job Schedule Type

```
=FILTER(J2#,(NOT(ISNUMBER(SEARCH("and",J2#))+ISNUMBER(SEARCH(",",J2#))))*(J2#<>0))
```

- **Unique List Generation:** This Excel formula below employs the `FILTER()` function to exclude entries containing "and" or commas, and omit zero values.
- **Formula Purpose:** This formula populates the table below, which gives us a list of unique job schedule types.

Background Table

<img width="562" height="227" alt="job_schedule" src="https://github.com/user-attachments/assets/230cd9d7-f61e-4ee7-907b-b6535873c4b2" />

Dashboard Implementation:

<img width="515" height="537" alt="job_type_chart" src="https://github.com/user-attachments/assets/74f1f395-c5be-421c-b254-4dd412a871b7" />

### Data Validation

#### Filtered List

- 🔒 **Enhanced Data Validation:** Implementing the filtered list as a data validation rule under the `Job Title`, `Country`, and `Type` option in the Data tab ensures:
    - User input is restricted to predefined parts of dashboard like job title, country, type dropdown menus 
    - Incorrect or inconsistent entries are prevented

## Conclusion

I created this dashboard to showcase insights into salary trends across multiple data-related job titles. This dashboard allows users to see how data jobs market was back in 2023 and using the functionalities explore how location and job type influenced salaries. 
