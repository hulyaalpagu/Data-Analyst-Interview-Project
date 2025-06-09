## Project Overview

This project was completed as part of a technical interview for a Data Analyst role. Many companies evaluate candidates either through live coding (e.g., LeetCode) or by assigning a take-home project with a tight deadline. In this case, I was given **two days** to complete the entire assignment—from data exploration to final presentation.

The task involved working with four raw datasets from a simulated digital learning platform. My responsibilities included cleaning and merging the data using **Python**, uncovering insights, and designing a multi-page **Power BI** dashboard to effectively communicate results.

### Included Files

- 📄 **Before Data Wrangling**: [(Before Data Wrangling) Data Analyst Assessment 2025.xlsx](./Data-Analyst-Interview-Project/%28Before%20Data%20Wrangling%29%20Data%20Analyst%20Assessment%202025.xlsx)
- 📄 **After Data Wrangling**: [(After Data Wrangling) Data Analyst Assessment 2025.csv](./Data-Analyst-Interview-Project/%28After%20Data%20Wrangling%29%20Data%20Analyst%20Assessment%202025.csv)
- 🧹 Python code for cleaning, transforming, and merging the data [Data Analyst Interview Project 2025.pdf](./Data-Analyst-Interview-Project/Data%20Analyst%20Interview%20Project%202025.pdf)
- 📊 Power BI dashboard (3 pages: Overview, Final Grade Analysis, Quiz Score Analysis)  [Data Visualization with Power BI.pbix](./Data-Analyst-Interview-Project/Data%20Visualization%20with%20Power%20BI.pbix)
- 📃 PDF report detailing the entire workflow, findings, and visuals [Data Wrangling with Python.ipynb](./Data-Analyst-Interview-Project/Data%20Wrangling%20with%20Python.ipynb) 


This project showcases my ability to solve complex data problems under time constraints, apply technical tools effectively, and communicate insights clearly to both technical and non-technical stakeholders.


# Data Analyst Interview Project

Candidate: Hulya Alpagu

Email: hulyalpagu@gmail.com

Phone: + 1 (862) 2977302

Project Overview

This assessment is based on four interconnected data tables from a simulated digital learning platform. The objective is to evaluate the effectiveness of the learning product by cleaning and analyzing the data, uncovering actionable insights using Python, and communicating those insights through impactful visualizations created in Power BI. The final outcome should guide data-driven decisions for product improvement.

## Data Summary

Here's a quick overview of the four main data tables:

- **student_table**
    - Contains student performance metrics.
    - 1000 students with columns like student_id, final_grade, total_time_spent, total_resources_completed, mastery_level, badges_earned, dropout_flag

- asset_table
  - Logs student activity with learning assets.
  - 80,503 resource interactions records, including student_id, timestamp, resource_type, resource_id

- **event_table**
    - Records actions taken by students on resources.
    - 80,503 event records, including student_id, resource_id, action_type, time_spent_seconds

- **performance_table**
    - Contains quiz/test performance data.
    - 11,540 quiz/test results, including student_id, resource_type, resource_id, score, difficulty

## Data Cleaning, Preparation, and Export in Python for Power BI Visualization

After reviewing the project objectives and exploring the structure of each table, the next step was to clean and prepare the data for merging. This included checking for missing values, removing duplicates, validating data types, and optimizing the dataset for analysis.

### 1. Missing Values:
No missing values found in any of the four tables.

![image](https://github.com/user-attachments/assets/72270615-fd7b-4e4a-ab70-b5a72be64171)

### 2. Duplicates Found:
After verifying the structure of each table, I checked for duplicate rows to ensure data quality. The results were as follows:

![image](https://github.com/user-attachments/assets/99a5ce99-54c8-4aa3-bfce-c6c852b40257)

All identified duplicates were removed using drop_duplicates() in Python to maintain data accuracy and prevent skewed results in the analysis.

![image](https://github.com/user-attachments/assets/309f67fb-e20b-48d1-9d34-4f91068ff11a)

### 3. Data Types:
All data types were correct. No conversions were needed.

![image](https://github.com/user-attachments/assets/574cf374-e6ff-4acf-ae69-67db944255e9)

### 4. Feature Reduction:
I observed that both the asset_table and performance_table contain a column named resource_type. However, in the performance_table, this column only contains a single value: 'quiz', while the asset_table includes all resource types such as 'reading', 'survey', 'video', 'game', 'quiz', 'forum', and 'assignment'.

![image](https://github.com/user-attachments/assets/564efb72-42fd-4ab4-b916-9add5cf0f777)

Since the resource_type column in the performance_table is redundant and does not provide additional information beyond what is already available in the asset_table, I decided to remove it to avoid duplication and keep the dataset clean.

![image](https://github.com/user-attachments/assets/7d86cd14-650f-420b-b0d5-8e64916c63f7)

### 5. Normalization Values:
I converted the numeric values in the dropout_flag column of the student_table into descriptive labels:

   - **0 → "Active Student"**

   - **1 → "Dropped Out Student"**

This transformation makes the data easier to understand for both technical and non-technical stakeholders and is especially helpful when creating visualizations, reports, or dashboards.

![image](https://github.com/user-attachments/assets/6f69d830-1902-43c8-ad17-2ec71cc6a527)

## Merging the Tables

After completing the data cleaning process, the dataset was ready for integration. The goal was to combine all four tables into a single comprehensive dataset suitable for analysis and Power BI visualization. 
Before merging, here’s a summary of the cleaned table shapes:

![image](https://github.com/user-attachments/assets/e990cbc3-5a12-45e2-b9b0-be27a659c13d)

**Merging Strategy Based on ER Diagram:**

To build a unified dataset, the following key relationships—illustrated in the ER diagram—were used:
 - event_table was merged with asset_table on both student_id and resource_id 
 - The result was merged with performance_table on student_id and resource_id 
 - Finally, the combined dataset was merged with student_table on student_id
This approach preserved the granularity of each interaction while linking it to performance and student-level metrics.

![image](https://github.com/user-attachments/assets/8a8a6f6b-47a2-44c6-aad7-408d8fbce774)

![image](https://github.com/user-attachments/assets/b2ed4154-ef09-4a0a-8d4a-2257aa7c16fb)

The dataset is fully cleaned, merged, and ready for analysis and visualization in Power BI.

## Summary Analysis 
The descriptive statistics above include metrics such as mean, standard deviation, minimum, maximum, and quartiles. These values help explain the distribution and variability of key variables such as time spent, quiz scores, final grades, and badges earned, offering a clearer view of overall student performance and engagement.

![image](https://github.com/user-attachments/assets/cb1c7bae-a488-4cee-ba97-efd9f9bdce95)

## Exporting the Dataset to Power BI

After preparing the final dataset, I exported it to a CSV file using Python to enable visualization in Power BI. This step ensures the data is ready for interactive reporting and dashboard creation.

![image](https://github.com/user-attachments/assets/97080174-570a-4e6c-8cc8-25f7e75993f8)

The exported file can now be imported into Power BI for visual exploration of student performance, engagement, and quiz outcomes

## Data Visualization

I created an interactive Power BI dashboard with three pages: the 'General Overview' page summarizes overall engagement, the 'Final Grade Analysis' page explores student grade patterns, and the 'Quiz Score Analysis' page focuses on quiz performance. Each section highlights a different aspect of student behavior and learning outcomes

### 1. General Overview
 This page provides a high-level summary of platform activity and student engagement. It highlights how learners interact with various resource types and shows engagement patterns, mastery levels, and dropout trends.

![image](https://github.com/user-attachments/assets/9baf35ec-9b94-428b-8e38-56050b9b40f7)

- **Total Time Spent by Resource Type**

![image](https://github.com/user-attachments/assets/f1d550c5-317f-45c4-9979-ed21ea510bd5)

This area chart shows the total time students spent on each resource type. Quizzes had the highest time spent, followed by videos, surveys, and readings. Forum and assignments were the lowest, suggesting students spent the most time on interactive or evaluative content.

- **Student Dropout Distribution**

![image](https://github.com/user-attachments/assets/b6c61f3c-9fb8-4694-805b-13e8a0aa6e7b)

This chart shows the distribution of student dropout status. About 89.8% of students remained active, while 10.2% dropped out. This indicates a relatively high retention rate on the platform.

- **Total Resources Completed by Resource Type**
![image](https://github.com/user-attachments/assets/29fa9362-9ba7-4970-83ea-6ab62fbeba34)

This bar chart shows the total number of completed resources by type. Quizzes had the highest completion count (over 1.7 million), followed by reading, game, and survey resources. Assignments and videos had the lowest totals, suggesting students were most engaged with evaluative and content-heavy materials like quizzes and readings.

- **Student Distribution by Mastery Level**

![image](https://github.com/user-attachments/assets/d774d0bc-0a63-40dc-8aa2-ce7854c05f59)

This chart displays the number of students at each mastery level. Most students are at the beginner level (476), followed by intermediate (312), and advanced (212). This suggests that a majority of learners are still early in their learning progression.

- **Monthly Dropout and Engagement Trend by Resource Type**

![image](https://github.com/user-attachments/assets/b373a385-ee55-4968-82d6-eb139039a6bb)

This area chart shows the monthly count of active vs. dropped-out students across different resource types. The number of active students remains consistently high, while dropouts are consistently low, suggesting stable engagement. A noticeable drop in April may indicate incomplete or missing data for that month.

### 2. Final Grade Analysis
The goal of this page is to evaluate how engagement affects final academic performance and identify patterns among high, mid, and low-grade groups.

![image](https://github.com/user-attachments/assets/f049e4a4-c61e-4e1b-98da-08be68ad1d90)

- **Final Grade and Total Time Spent by Performance Group**

![image](https://github.com/user-attachments/assets/2f80c0de-ab93-4d7a-b52d-53551f604149)  

This scatter plot illustrates the relationship between total time spent and final grades. High-performing students are concentrated at the top, while low-performing students stay in the lower range regardless of time invested. This suggests that time spent helps but does not guarantee high performance, and other factors may also play a role.

- **Student Count by Resource Type and Final Grade Group**

![image](https://github.com/user-attachments/assets/e30ac982-ce31-4295-aebf-92410c1bf441)

This chart compares the number of students by resource type and their final grade performance group. Across all resource types, most students fall into the high-grade category, while low-grade counts remain consistent. This suggests strong academic performance regardless of resource type.

- **Monthly Average Final Grade by Performance Group**

  ![image](https://github.com/user-attachments/assets/6cbf8712-1ba2-4e10-9f2d-1804a0ec7ecc)

This chart shows the monthly average final grades by performance group. Students in the high-grade group consistently scored above 90, while mid-grade students averaged 73 across all months. Low-grade scores increased slightly over time, suggesting potential improvement or better engagement.

- **Student Performance by Mastery Level and Final Grade Group**

![image](https://github.com/user-attachments/assets/dc18f151-4828-4aba-b393-1059887cd790)

This chart shows how final grade performance is distributed across mastery levels. While all groups contain students of varying performance, advanced students have a higher proportion of high grades, while beginners show a more balanced spread across all grade levels.

### 3. Quiz Score Analysis

This page explores student quiz performance by analyzing score distribution across difficulty levels, time spent on quizzes, and monthly trends. It highlights how different performance groups (high, mid, low) respond to varying quiz conditions and helps identify areas where students may need additional support.

![image](https://github.com/user-attachments/assets/225d4706-7cac-4052-9ebc-f5a009405fea)

- **Average Quiz Score by Difficulty and Performance Group**
  
![image](https://github.com/user-attachments/assets/d341219e-33ff-446c-bf5c-8b5bfdaf684d)

This chart shows the average quiz scores across different difficulty levels, grouped by performance. The scores remain consistent across all difficulty levels, with high performers averaging 84, mid performers around 50–52, and low performers around 16–18. This suggests that quiz difficulty had minimal impact on performance distribution.

- **Quiz Score and Time Spent by Performance Group**

![image](https://github.com/user-attachments/assets/7a77cfb0-4338-44ef-925f-d21004c43344)

This scatter plot shows the relationship between time spent on quizzes and the score achieved, grouped by quiz performance level. Students with high scores tend to cluster in the lower to mid time ranges, suggesting efficiency. Low scorers appear across all time ranges, indicating that spending more time doesn't necessarily lead to better scores.

- **Average Quiz Score by Performance Group**

![image](https://github.com/user-attachments/assets/afb98b0e-4445-4f0e-aaa5-6479f0c61769)

This donut chart shows average quiz scores by performance group. Most students are in the high-score group, averaging 84.10. Mid performers average 51.10, and low performers average 16.99. The distribution highlights strong overall performance with a small portion needing support.

- **Monthly Average Quiz Score by Performance Group**

![image](https://github.com/user-attachments/assets/583a842d-84b1-465e-aa9b-cbfe1ecbde10)

This chart shows the monthly average quiz scores for each performance group. High scorers consistently averaged above 83, while mid scorers remained around 50. Low scorers showed a slight decline over time, from 17.65 in January to 14.67 in April, indicating a growing performance gap.

## Conclusion
This project involved end-to-end data preparation, analysis, and visualization using Python and Power BI. By cleaning, merging, and exploring the dataset, I was able to uncover meaningful patterns in student engagement, academic performance, and quiz behavior. The interactive dashboard effectively highlights areas of strength—such as high overall quiz performance and student retention—as well as areas for improvement, such as performance gaps among lower-scoring groups. These insights can support data-driven decisions to enhance the learning platform’s effectiveness and student outcomes.
