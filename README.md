# DSA-DATA-ANALYSIS-FINAL PROJECT
This is a project executed at the end of my data analysis course under the auspices of Digital Skill Up Africa.
## PROJECT TITLE: DSA DATA ANALYSIS CAPSTONE PROJECT
## Case Study 3: PALMORA GROUP HUMAN RESOURCE (HR) ANALYSIS

-[Project Overview](#project-overview)

-[Analysis Tool](#analysis-tool)

-[Step By Step Procedures](#step-by-step-procedures)

-[Outcome of Analysis](#outcome-of-analysis)

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

## ANALYSIS TASKS

Using card visuals, click and drag into the report canva, go to the 'New Salary Table', while the card is selected, check the name column and the number of employee names will be counted and displayed in the visual as shown in the image below.

![Card Visual](https://github.com/user-attachments/assets/f4617d34-663a-4f12-9ecc-3f4b348e8fd1)

After that, you can format the visual by clicking on the 'Format your Visual' option to apply any format of your choice.

Duplicate and use the formated card to ensure format consistency. 

To get number of male employees, create a new measure by right clicking on any column and click new measure. Make the measure name 'Male count' enter the formula below.

Male Count = CALCULATE(CountX(FILTER('New Salary Table','New Salary Table'[Gender]= "MALE"),'New Salary Table'[Gender]))

Select one of the duplicated cards, uncheck existing fields so that you can decide on what to represent. Since we want no. of male employees, check the 'male count' measure created and you will see the number of males as shown in the image above.

Replicate same process for female and unspecified gender as the case may be to get the number of female and unspecified gender employees as shown above.

To get average salary based on gender, use pie chart visual. Create separate measures for average salary for male, female and unspecified using the formula below.

Average Male Salary = CALCULATE(AVERAGE('New Salary Table'[New Salary]),'New Salary Table'[Gender]= "Female")

Substitute the specific gender for the separate measures to create for the other genders. The result is represented in the pie chart below.

![Avg Salary based on gender](https://github.com/user-attachments/assets/025b63f3-5538-4c1f-88a4-c2a8ec50e438)

1. What is the gender distribution in the organization? Distil to regions and departments.

Click on column chart, drag name column into 'y' axis and chose count while for 'x' axis drag gender and location into it.  

![No  of employee based on gender, department and region](https://github.com/user-attachments/assets/6dbea2c6-cc73-4ab8-9ef6-5d16ab75b014)

By Location we have the chart below.

![Uploading Gender Distribution based on location.JPG…]()

