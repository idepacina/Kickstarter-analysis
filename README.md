# Kickstarting with Excel

Performing analysis on Kickstarter data to uncover trends.

## Overview of Project

Louise is a playwriter who launched a Crowdfunding analysis to help her make informed  strategy decisions. To make sense of the dataset, the data was sorted and organized, and includes visualizations to show the patterns and trends of past plays.  The analysis will help Louise decide what goal amounts are more accustomed to success and when successful plays are launched. 

### Purpose

The purpose of the project is to help Louise make informed decisions for her campaign strategy. The goal is for her play _Fever_ to be both successful as other plays in the same category and reaches success in a timely manner. 

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date

1. Created a new column labled "Years" to the table in the Kickstarter sheet.
2. Used the YEARS() function to extract the year based on the "Date Created Conversion" column. 
3. Used the Fill Handle to extend the same formula to the rest of the Years column. 
4. A PivotTable was created from the Kickstarter worksheet and the new sheet was labeled "Theater Outcomes by Launch Date."
5. Filtered the PivotTable and used the appropriate fields.
    
    - Filters: Parent Category and Year

    - Columns: Outcomes

    - Rows: Dated Created Conversion

    - Values: Count of Outcomes
6. Excel automatically included Years and Quarters to the Rows field, and those fields were removed to display the Row Labels by months of the year.
7. Filtered "Parent Category" to show the data for "theater."
8. Filtered the column labels to show the data for "successful," "failed," and "canceled."
9. The campaigns were sorted in descending order so "successful" is first. 
10. A line chart was created from the pivot table to show the relationship between the outcomes and the launch month. 

![TheaterOutcomesVs.LaunchDate](https://github.com/idepacina/kickstarter-analysis/blob/main/Resources/Theater_Outcomes_vs_Launch.png)

### Analysis of Outcomes Based on Goals

1. A new sheet was created and labeled "Outcomes Based on Goals." 
2. The following columns and rows were created to hold the data and group the projects based on goal amount.

    - Columns:
        - Goal
        - Number successful
        - Number failed
        - Number canceled
        - Total projects
        - Percentage successful 
        - Percentage failed
        - Percentage canceled
    - Rows: 
        - Less than 1000
        - 1000 to 4999
        - 5000 to 9999
        - 10000 to 14999
        - 15000 to 19999
        - 20000 to 24999
        - 25000 to 29999
        - 30000 to 34999
        - 35000 to 39999
        - 40000 to 44999
        - 45000 to 49999
        - Greater than 50000
3. The COUNTIFS() function was used to populate the "Number Successful," "Number Failed," and "Number Canceled," columns, based on the project "outcome," the "goal" amount in the ranges and the Subcategory "plays."
4. The =SUM(B2:D2) function was used to populate the "Total Projects" column and used the Fill Handle to extend formula to the end of the column.
5. Calculated the percentage of successful, failed, and canceled projects for each row by dividing the respective project by the "Total Projects." Example: =(B2/E2)
6. Created a line chart titled "Outcomes Based on Goal" to show the relationship between the goal-amount ranges and the percentage of successful, failed, and canceled projects.

![OutcomesVs.Goals](https://github.com/idepacina/kickstarter-analysis/blob/main/Resources/Outcomes_vs_Goals.png)

### Challenges and Difficulties Encountered

Challenges and difficulties faced was with the analysis of outcomes based on goals. It was difficult to find an efficient way to utilize the COUNTIFS() function so that the formula could extend to other columns and rows. The solution was to use the F4 button to make the criteria range absolute. 

=COUNTIFS(Kickstarter!$F:$F,"successful",Kickstarter!$D:$D,"<1000",Kickstarter!$R:$R,"plays")

The result allowed for a simple change the function. The first criteria was changed from "successful" to "canceled" and "failed." This way Excel was running the same formula in the table as opposed to having to go to every cell and manually use the =COUNTIFS() function over again. 

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

     Based on the findings and data, we can conclude: 
     - Theater events that are launched in May, June and July are most successful in comparison to events launched in other months.  
     - Theater events that are launched in November and December are least successful compared to events launched in other months. 

- What can you conclude about the Outcomes based on Goals?

    - It would be in Louise's best interest to set a goal less than $1000 because it has the highest successful percentag. 
    - By setting a goal of $1000, it can be predicted that her play will have a 76% chance of being successful.

- What are some limitations of this dataset?
    - The data is sample. Therefore, the results are limited and based on the Kickstarter dataset. 
    - The data can be more specific and include categories such as genre, age groups, and location within the countries. With additional categories, Louise can narrow her search in regards to target audience and cities where theater plays are popular.  

- What are some other possible tables and/or graphs that we could create?
    - Create a pivot table and chart that shows the relationship between successful plays based on country. This particular data will highlight which countries express the most interest plays and which countries might need more attention to grow the interest. 
    - Create a pivot table and chart that shows the relationship between the category theater outcomes based on the deadline date. This particular data will show how many plays were "successful," "failed," and "canceled," based on the deadline date.
