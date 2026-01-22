# MS Excel project - Data Job Postings(2023)
# Data jobs Salary and Skills Analysis 
## Introduction  
This project analyzes 2023 data job postings using a dataset sourced directly from GitHub. The objective is to explore salary trends and identify the most in-demand skills across various data roles. The analysis is conducted using Microsoft Excel, applying data cleaning, pivot tables, and visualizations to extract meaningful insights and better understand the requirements of the data job market.  
### Questions to Analyze  
To understand the data science job market, I asked the following:  
1. Do more skills get you better pay?
2. What’s the salary for data jobs in different regions?
3. What are the top skills of data professionals?
4. What’s the pay for the top 10 skills?
### MS Excel Skills used   
- Power query
- Power pivot
- DAX (Data Analysis Expressions)
- Pivot Tables
- Pivot Charts
## 1. Do more skills get you better pay?  
### Using Power Query to Extract, Transform and Load the Data  
#### Extract :- 
- I first used Power Query to extract the original data and create two queries:
  * First one with all the data jobs information named data_jobs_all
  * The second listing the skills for each job ID named data_job_skills
#### Transform :-
- Then, I transformed each query by changing column types, removing unnecessary columns, cleaning text to eliminate specific words, and trimming excess whitespace.
  * data_jobs_all
  
    <img width="300" height="385" alt="image" src="https://github.com/user-attachments/assets/a028f6ee-14c2-47cf-886a-5e90cffc2919" />
  * data_job_skills
 
    <img width="302" height="406" alt="image" src="https://github.com/user-attachments/assets/1e9646a6-4537-41ab-a7e7-6236ba0cc276" />
#### Load :-
- Finally, I loaded both transformed queries into the workbook, setting the foundation for the analysis.
  * data_jobs_all

    <img width="1181" height="399" alt="image" src="https://github.com/user-attachments/assets/fc5602db-4f60-4c20-ae6b-2164e2ac8c3a" />
  * data_job_skills
 
    <img width="1183" height="433" alt="image" src="https://github.com/user-attachments/assets/d32cf84d-8d78-479b-83be-b73f3ad49928" />

### Analysis
Afterwards, I put the data into a pivot table and populated distict columns for Job Title, Median Salary And Skills per job values. Along with that, I added a "Job country" Slicer to further enhance the analysis and unlocking an option to view the data in respect to various Countries.  


  <img width="510" height="274" alt="image" src="https://github.com/user-attachments/assets/74a7ae7a-58d8-43d6-9303-c57f343bfd4a" />  
  
### Insights  

- There is a positive correlation between the number of skills requested in job postings and the median salary, particularly in roles like Senior Data Engineer and Data Scientist.  
- Roles that require fewer skills, like Business Analyst, tend to offer lower salaries, suggesting that more specialized skill sets command higher market value.
- This trend emphasizes the value of acquiring multiple relevant skills, particularly for individuals aiming for higher-paying roles.  

  <img width="1145" height="473" alt="image" src="https://github.com/user-attachments/assets/3e22e2fb-b0bb-442e-92e2-3859e5628304" />


## 2. What’s the salary for data jobs in different regions?  
### Skills: PivotTables & DAX  
#### Pivot Table :-  
- I created a PivotTable using the Data Model I created with Power Pivot.  
- I moved the Job Title Column to the rows area and Average yearly Salary into the values area.  
- Then I added new measure to calculate the median salary for India jobs

  =CALCULATE(
    MEDIAN(data_jobs_all[salary_year_avg]),
    data_jobs_all[job_country] = "India")

#### DAX :-  
- To calculate the median year salary I used DAX.  
  Median Salary := MEDIAN(data_jobs_all[salary_year_avg])  

### Analysis  
- Job roles like Senior Data Engineer and Data Scientist command higher median salaries both in the India and internationally, showcasing the global demand for high-level data expertise.  
- The salary disparity between India and Non-India roles is particularly notable in high-tech jobs, which might be influenced by the concentration of tech industries in the India.
- These salary insights are important for planning and salary negotiations, helping professionals and companies align their offers with market standards while considering geographical variations.  

  <img width="1427" height="445" alt="image" src="https://github.com/user-attachments/assets/91c5aeff-8923-4484-95a7-fe0a373756b2" />  

 ## 3. What are the top skills of data professionals?
 ### Skill: Power Pivot
  - Power Pivot
    * I created a data model by integrating the data_jobs_all and data_jobs_skills tables into one model.
    * Since, I had already cleaned the data using Power Query; Power Pivot created a relationship between these two tables.
   
  - Data Model
    * I created a relationship between my two tables using the job_id column.  

    <img width="1788" height="1264" alt="image" src="https://github.com/user-attachments/assets/25a6d974-ed83-40ed-93f7-ab1ea42935bb" />

  - Power Pivot Menu
    * The Power Pivot menu was used to refine my data model and makes it easy to create measures.
   
    <img width="1918" height="742" alt="image" src="https://github.com/user-attachments/assets/09fe3896-4749-4161-90cb-7d6b64d35a36" />

  ### Analysis

  - SQL and Python dominate as top skills in data-related jobs, reflecting their foundational role in data processing and analysis.
  - Emerging technologies like AWS and Azure also show significant presence, underlining the industry's shift towards cloud services and big data technologies.
  - Understanding prevalent skills in the industry not only helps professionals stay competitive but also guides training and educational programs to focus on the most impactful technologies.  
 
    <img width="1388" height="440" alt="image" src="https://github.com/user-attachments/assets/a7b701cf-6de7-4b6c-8bdc-1d5f8bd205ff" />


## 4.What’s the pay of the top 10 skills?
### Skill: Advanced Charts (Pivot Chart)
   - Pivot Charts  

     * I created a combo PivotChart to plot median salary and skill count from my PivotTable.  
             ** Primary Axis: Median Salary (as a Clustered Column)  
             ** Secondary Axis: Skill Likelihood (as a Line with Markers)  
             
To customize the chart, I added a title axis title, removed the lines, and changed the markers to crosses.


###  Analysis  

 -  Higher median salaries are associated with skills like Python, Oracle, and SQL, suggesting their critical role in high-paying tech jobs.  
 -  Skills like PowerPoint and Word have the lowest median salaries, indicating less specialization and demand in high-salary sectors.
 -  This chart highlights the importance of investing time in learning high-value skills like Python and SQL, which are evidently tied to higher paying roles, especially for those looking to maximize their salary in the tech industry.  


   <img width="1314" height="534" alt="image" src="https://github.com/user-attachments/assets/7049d72d-8ea4-4385-8885-4d85952279c0" />  



## Conclusion  

This Excel-based project provides a comprehensive analysis of the data science job market using a dataset curated from real-world job postings. By examining job titles, salary ranges, locations, and required skills, the analysis highlights how market demand and compensation vary across different data roles. Advanced Excel features such as Power Query for data transformation, PivotTables for aggregation, DAX for calculated insights, and dynamic charts for visualization were used to extract meaningful patterns from the data.

One of the key takeaways from this project is the strong correlation between multi-skill proficiency and higher salary levels, particularly in roles requiring Python, SQL, and cloud-based technologies. The findings reinforce the importance of building a well-rounded technical skill set to remain competitive in the evolving data job landscape.

Overall, this project serves both as a demonstration of practical data analysis skills using Excel and as a valuable reference for aspiring data professionals seeking clarity on which skills and roles offer better compensation and growth opportunities.  




    



  


 



  



  

  

  

    
    
    



    







