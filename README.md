# DSA_CAPSTONE-PROJECT-I
This is my first data analysis project at DSA(The Incubator Hub) using Power Bi to explore employee metrics across gender. salary ,ratings, and bonus

## Poject Topic: Palmora Employee Analysis
### Project Overview:The Palmora Group seeks to address the issue of gender pay gap to ensure gender equality across the organisation in different regions.
### Data Source:Palmoria Group emp-data.CVS, provided by The Incubator Hub as part of the DSA training program
Tool Used:
* POWERBI;
     - data Cleaning
     - data manipulation
     - creating report
     - visualization
### Exploratory Data Analysis:
#### 1.Gender Distribution Analysis - How are employees distributed across gender,departments,region?
#### 2.Rating Insight Based on Gender - How do performance ratings differ by gender?
#### 3.Salary Structure and Gender Pay Gap - Are there notable pay gaps across gender, departments and regions? 
#### 4.Minimum Salary Requirement Analysis - How many employees earn below the defined salary thresshold and where?
#### 5.Bonus Payment Calculation - How are bonuses awarded based on performance and what is the total compensation distribution?
### Data Analysis:
- import data into powerbi
- transform data by - Remove employees witout salaries and department indicated as "Null"
- Assign a generic gender status as "Undisclosed" to employees who refused to disclose thier genders
  
  ### Gender Distribution Analysis:
  #### DAX Measures Used;
 Gender Count = COUNT('Employee'[Gender])
Gender Percentage = 
DIVIDE(
    COUNT('Employee'[Gender]), 
    CALCULATE(COUNT('Employee'[Gender]), ALL('Employee'[Gender]))
)

![image](https://github.com/user-attachments/assets/4f27accb-6595-48dc-8a9c-d5fed8636391)

![image](https://github.com/user-attachments/assets/fcfb786b-be42-419a-a11c-52a835d05c4d)

 #### Insights
Male and female distribution varies significantly by region.
Generic gender entries suggest areas for improved data collection

### Rating Insights Based on Gender:

#### DAX Measured Used;
 Average Rating by Gender = AVERAGE('Employee'[Rating])
 Rating Count by Gender = COUNT('Employee'[Rating])

 ![image](https://github.com/user-attachments/assets/6fc6edde-2963-4fdf-ad7c-e2f2967c2c75)

#### Insights
Females had a slightly higher average rating.
Most employees are rated between Average and Very Good.

 ### Salary Structure and pay Gap:
  #### DAX Measured Used
  Average Salary by Gender = AVERAGE('Employee'[Salary])
  Salary Count by Department and Region = COUNT('Employee'[Salary])

  ![image](https://github.com/user-attachments/assets/ad944029-dbae-42d9-8cc2-5d2ced544be2)

#### Insights
Slight pay gap observed in technical departments.
Some regions offer higher salaries uniformly across genders.

#### Minimum Salary Requirement:
##### DAX Measure Used;
   Employees Below Minimum Salary = COUNTX(FILTER('Employee', 'Employee'[Salary] < 90000), 'Employee'[Salary])
    
  ![Minimum Salary](https://github.com/user-attachments/assets/ab08592a-45eb-4976-aecb-39863ed91395)
###### Minimum Salary.png
## Insights
Regions;kaduna and Abuja have a large proportion of low-salary employees.
Opportunities exist for equitable wage distribution.
   
 ### Bonus Payment Calculation
#### DAX Measure Used
 Bonus Amount = IF('Employee'[Rating] > 3, 'Employee'[Salary] * 0.1, 0)
 Total Amount to be Paid = 'Employee'[Salary] + 'Bonus Amount'
Minimum Salary.png
 
= IF('Employee'[Rating] > 3, 'Employee'[Salary] * 0.1, 0)
 Total Amount to be Paid = 'Employee'[Salary] + 'Bonus Amount'

