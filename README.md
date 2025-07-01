# DSA-DATA-ANALYSIS-FINAL PROJECT
This is a project executed at the end of my data analysis course under the auspices of Digital Skill Up Africa.
## PROJECT TITLE: DSA DATA ANALYSIS CAPSTONE PROJECT
## Case Study 3: PALMORA GROUP HUMAN RESOURCE (HR) ANALYSIS

-[Project Overview](#project-overview)

-[Analysis Tool](#analysis-tool)

-[Requirements](#requirements)

-[Step By Step Procedures](#step-by-step-procedures)

-[Analysis Tasks](#analysis-tasks)

-[Conclusion and Recommendation](#conclusion-and-recommendation)


### PROJECT OVERVIEW

This is a project that that is aimed that ascertaining if there is ascertaining if there is any form of gender inequality in the operations of the company with the view to balance the gender distribution if at all there is any. By meticulous analysis of the data, the company will be able to make informed decision that will enable them to confidently challenge any criticism that is confirmed to be baseless.

### ANALYSIS TOOL

I was requested to use Power bi to execute this project and that is what I used.

### REQUIREMENTS

CASE SCENARIO 

●  Analyse the company data and generate insights that the Palmoria management team would need to address. 

● The analysis should be visualised using appropriate charts. 

● The focus should be on gender-related issues within the organization and its regions.

● The insights required are based on your discretion. However, Mr Gamma, as an insider, has offered to give you pointers on areas you need to pay attention to.

### STEP BY STEP PROCEDURES 

- I painstakingly read all that concerns the project and the given parameters as well as the data supplied to me by company. This enable me to understand what steps I am to take towards achieving the goal.
  
- Import the both file which contains the two required tables named Palmoria group emp-data and Bonus Rule  given to me and transformed the two tables using power query.
  
- In the course of transforming my data, I removed unwanted columns (While on power query, right click on the column you intend to remove and click remove). I promoted my column header by making first row header (Click on anywhere in the table, click transform tab, on the table fields click on use first row as header).
  
- I added index Column (click on the table, click on add column and  under general field, click on index column from 1. I reordered it to be my first column in my main data table (Palmoria Group emp-data) by clicking on the header, hold and drag to the desired position. Idouble clicked on the heading to rename it.
  
- I  deleted employees without salary by using filter option (the arrow by the bottom right of the header). Click on arrow of the actual column header you intend to filder and uncheck null cells. Replicate same for Department column.
  
- For the blank cells in the Gender column, I used replaced value option. To do this, leave the find field blank and type unspecified in the replace field.
I removed duplicates using the name column as reference column. (Select the name column, click home tab, in remove row pull down menu, select remove rows).

- On the power query interface, open the bonus rule table, and change the number format for the rating columns to percentage.

- Unpivot the columns  in the bonus table except the Department column (to do this, select the Department column, click unpivot  other columns).

- Rename the Attribute column to Rating.

- Now you have to merge the tables to create a New Salary Table (Open the Palmoria group emp-data set again,on the home tab, under combine field, click merge queries as new using bonus table as second table). Use both department and rating as matching columns for the merging (Department to Department, Attributes to Rating). Left outer join is my type of join. The combined table is named 'New Salary Table'.

- After merging, delete unwanted columns (the Department and Attribute columns in the bouns table that was joined to the main table). This is because I already have them as part of the Palmoria Group emp-data table which I also refer to as my Primary table.

- For employees that were not rated, replace 'null'with '0'and change the data type for bonus rule vale column to percentage.

- For Bonus Amount Column, add custom column and rename the column then type the formula [salary]*[Bonus Rule Value]

- When you close and apply, go to the data type of each of the columns and ensure they are correct. For Name, Gender, Department, Location columns, select text as the data type. For Bonus Rule Value column, select percentage as data type and apply thousand separator under column tools tab which appears once a column is selected.

- Sort the index column in ascending order to get the actual number of employees.

- At this point, the 'New Salary Table' is in order and ready for visualization based on the information required.

- Select the 'New Salary Table'and click on report view.

### ANALYSIS TASKS

Using card visuals, click and drag into the report canva, go to the 'New Salary Table', while the card is selected, check the name column and the number of employee names will be counted and displayed in the visual as shown in the image below.

![Card Visual](https://github.com/user-attachments/assets/f4617d34-663a-4f12-9ecc-3f4b348e8fd1)

After that, you can format the visual by clicking on the 'Format your Visual' option to apply any format of your choice.

Duplicate and use the formated card to ensure format consistency. 

To get number of male employees, create a new measure by right clicking on any column and click new measure. Make the measure name 'Male count' enter the formula below.

Male Count = CALCULATE(CountX(FILTER('New Salary Table','New Salary Table'[Gender]= "MALE"),'New Salary Table'[Gender]))

Select one of the duplicated cards, uncheck existing fields so that you can decide on what to represent. Since we want no. of male employees, check the 'male count' measure created and you will see the number of males as shown in the image above.

Replicate same process for female and unspecified gender as the case may be to get the number of female and unspecified gender employees as shown above.

1. What is the gender distribution in the organization? Distil to regions and departments. 

Click on column chart, drag name column into 'y' axis and choose count while for 'x' axis drag gender and department into it.
From the chart, below, if you hover around the columns in the chart, the number of employees in a particular department will display. Note that the various colors represent different department as shown in the legend. The departments are Research and Development, Accounting, Marketing, Services, Human Resources, Training, Product Management and Business Development department.

![No of employees based on department and gender](https://github.com/user-attachments/assets/e596c101-9837-4819-b37b-407efdcedd6c)

By Location we have the chart below. Duplicate and uncheck the fields for the existing column chart. Drag gender and location into 'x' axis while for 'y' axis drag name column into it and summarize by count.

![Gender Distribution based on location](https://github.com/user-attachments/assets/de0c5998-35c1-47cb-b031-de932eaf6c1c)

2. Show insights on ratings based on gender.
Using a Matrix visual, click and drag the visual in the canva while it is selected, drag gender column into rows area, rating column into column area and name column into values area and summarize by count. You will get the chart below as the result.

![No  of Employees based on gender ratings](https://github.com/user-attachments/assets/c10453d9-7e7e-4f2c-a50e-f0100ba76353)

For no. of employees based on gender and department, duplicate the existing Matrix visuals used above, drag department column into rows area, gender column into column area, name column into values and summarize by count.

3. Analyse the company’s salary structure. Identify if there is a gender pay gap. If there is, identify the department and regions that should be the focus of management.

To do this I think getting the average salary based on gender is necessary and to do this, use pie chart visual. Create separate measures for average salary for male, female and unspecified using the formula below.

```Average Male Salary = CALCULATE(AVERAGE('New Salary Table'[New Salary]),'New Salary Table'[Gender]= "Female")```

Substitute the specific gender for the separate measures to create measures for the other genders having created the first measure. The result is represented in the pie chart below.

![Avg Salary based on gender](https://github.com/user-attachments/assets/025b63f3-5538-4c1f-88a4-c2a8ec50e438)

By the pie chart above, I can confidently say difference between the male and female avearge salary is insignificant for any rational person to say that Palmora is gender biased in her operation or recruitment as the case may be.

Further more you can also get average salary based on location department and region. to do this, duplicate the existing matrix visual to sustain consistency. Uncheck the existing columns in the visual, drag gender and location column into rows area, department column in to column area and average new salary column into values. Using the chart formart tab, you can edit the table title and others to your satisfaction.

![Average salary based on location department and region](https://github.com/user-attachments/assets/e489978b-928b-494d-9a34-4507536a9aa3)

4. A recent regulation was adopted which requires manufacturing companies to pay employees a minimum of $90,000.
  ● Does Palmoria meet this requirement? 
  ● Show the pay distribution of employees grouped by a band of $10,000. For example: 
  ● How many employees fall into a band of $10,000 – $20,000, $20,000 – $30,000, etc.? 
  ● Also visualize this by regions

![Minimum of 90000](https://github.com/user-attachments/assets/f9f526de-e7c6-4ab7-a463-7978fad8f7f4)

By the Pie chart above, Palmora has not met the requirement because 570 employees which represent 65.22% of the total employee still earn below $90,000.

To arrive at the above chart, create a measure for employees earning >=90,000 using the formular below 

New Salary <90000 = COUNTROWS(FILTER('New Salary Table',[New Salary] <90000))

[New Salary >=90000] = COUNTROWS(FILTER('New Salary Table',[New Salary] >=90000))

- For pay distribution grouped by band, create new measures for each ranges by entering the formular below.

  New Salary <30000 = CALCULATE(COUNTROWS(FILTER('New Salary Table',[New Salary] <30000)))

  [New Salary >=30000 <50000] = CALCULATE(COUNTROWS(FILTER('New Salary Table',[New Salary] >=30000 && 'New Salary Table'[New Salary] <50000)))

  New Salary >50000<70000 = COUNTROWS(FILTER('New Salary Table',[New Salary] >=50000 && 'New Salary Table'[New Salary] <70000))

  The Matrix Visual below has the representation of values

  New Salary >70000<90000 = COUNTROWS(FILTER('New Salary Table',[New Salary] >=70000 && 'New Salary Table'[New Salary] <90000))

  New Salary >90000<110000 = COUNTROWS(FILTER('New Salary Table',[New Salary] >=90000 && 'New Salary Table'[New Salary] <110000))

  ``New Salary>110000 = COUNTROWS(FILTER('New Salary Table',[Salary] > 110000))

  ![No  of empoyees based on salary range and region](https://github.com/user-attachments/assets/8467a5b1-7901-49b3-be82-0b812903214f)
  
