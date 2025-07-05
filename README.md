# DSA---Palmora-Group-HR-Analysis

### This is where I started my portfolio building while taking my data analysis Class with the Incubator Hub during Digital Skill up Africa
### Project Topic: Palmora-Group-HR-Analysis
Project Overview :The Palmoria Group, a manufacturing company based in Nigeria, is embroiled in issues bordering on gender inequality in its 3 regions. Unfortunately, the media recently published the news with the headline “Palmoria, the Manufacturing Patriarchy”. This doesn’t look good for the owners of the business, based on their ambition to scale the business to other regions and even overseas. Cases like this can only spiral downwards, revealing other issues like the gender pay gap, amongst other possible issues. The CEO of Palmoria, Mr Ayodeji Chukwuma, is keen to address these issues before they get out of hand. The CHRO, Mr Yunus Shofoluwe, has been assigned the task to identify key areas within the business that could give rise to issues and address them immediately. Mr Shofoluwe decided to recruit an HR Analytics expert to analyse the company’s HR data and come up with recommendations for management’s attention. 
### Data Source 
DSA Data Analysis Capstone Project 
### Tools Used
Ms powerbi for Data Cleaning and Exploratory Data Analysis (EDA) 
- Opened the original dataset on Microsoft power bi [Download here](https://www.microsoft.com/en-us/power-platform/products/power-bi)

### Data Cleaning and Preparation
- Data loading and Inspection
- Handling missing variables
- Data Cleaning and formating
-  Analyse the company data and generate insights that the Palmoria management team would need to address 
- Visualised using appropriate charts 
- Focus will be on gender-related issues within the organization and its 
regions  

### Exploratory Data Analysis
Generally, there are two genders in the organization. However, some employees refused to disclose their gender. We will assign a generic gender status to these employees, some employees are without a salary because they are no longer with the company. We will need to take those employees out and some departments are indicated as “NULL”. These departments would also need to be taken out. 

### Data Analysis
- Import the employee data into Power BI
- Do a proper cleaning E.g
 1. Remove employees without salaries and departments indicated as "NULL".
 2. Assign a generic gender status to employees who refused to disclose their gender (N/A).
- Unpivot Column
- Check column quality, profile and distribution
- Use custom column to create a new column Department/Rating using Department&"/"&Rating
- Import bonus mapping
- Unpivot column
- Use custom column to create a new column Department/Attribute using Department&"/"&Attribute
- Merge employee data and bonus mapping and rename it has New
- Create new column Total pay, Annual bonus and Salary band
- Create visuals on canvas  
1. Create a bar chart:
    - Axis: Region/Department
    - Value: Count of Employees by Gender
2. Use a slicer to filter by region/department.
3. Visualize the overall gender distribution using a pie chart.

Visualization: 
- Bar chart: "Gender Distribution by Region"
- Pie chart: "Overall Gender Distribution"

Measures
- Gender Count = COUNT('Employee'[Gender])
- Gender Percentage = DIVIDE(CALCULATE(COUNT('Employee'[Gender])), CALCULATE(COUNT('Employee'[Gender]), ALL('Employee'[Gender])))
2: Ratings Insights Based on Gender
1. Create a histogram/box plot:
    - Axis: Rating
    - Value: Count of Employees by Gender
2. Use a slicer to filter by gender.
3. Calculate the average rating by gender using a measure.

Visualization:
- Histogram: "Ratings Distribution by Gender"
- Box plot: "Ratings Comparison by Gender"

Measures
- Average Rating by Gender = AVERAGE('Employee'[Rating])
- Rating Count by Gender = COUNT('Employee'[Rating])
3: Salary Structure and Gender Pay Gap Analysis
1. Create a scatter plot:
    - X-axis: Salary
    - Y-axis: Gender
2. Calculate the average salary by gender using a measure.
3. Identify departments and regions with significant pay gaps.

Visualization:
- Scatter plot: "Salary vs. Gender"
- Bar chart: "Average Salary by Department and Region"

Measures 
- Average Salary by Gender = AVERAGE('Employee'[Salary])
- Salary Count by Department and Region = COUNT('Employee'[Salary])
4: Minimum Salary Requirement Analysis
1. Create a histogram:
    - Axis: Salary Band ($10,000 increments)
    - Value: Count of Employees
2. Use a slicer to filter by region.
3. Calculate the number of employees below the minimum salary threshold.

Visualization:
- Histogram: "Salary Distribution by $10,000 Band"
- Bar chart: "Employees Below Minimum Salary Threshold by Region"

Measures
- Employees Below Minimum Salary = COUNTX(FILTER('Employee', 'Employee'[Salary] < 90000), 'Employee'[Salary])
5: Bonus Payment Calculation
1. Create a measure to calculate the bonus amount based on performance ratings.
2. Calculate the total amount to be paid to individual employees (salary + bonus).
3. Create a bar chart to visualize the total amount to be paid out per region.

Visualization:
Bonus Payments
- Bar chart: "Total Bonus Payout by Region"
- Table: "Individual Employee Bonus Payments"

Measures
- Bonus Amount = IF('Employee'[Rating] > 3, 'Employee'[Salary] * 0.1, 0)
- Total Amount to be Paid = 'Employee'[Salary] + 'Bonus Amount'
- Created another sheet for Dashboard


### Result Findings


