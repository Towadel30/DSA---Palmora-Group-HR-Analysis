# DSA---Palmora-Group-HR-Analysis

### This is where I started my portfolio building while taking my data analysis Class with the Incubator Hub during Digital Skill up Africa
### Project Topic: Palmora-Group-HR-Analysis
Project Overview :The Palmoria Group, a manufacturing company based in Nigeria, is embroiled in issues bordering on gender inequality in its 3 regions. Unfortunately, the media recently published the news with the headline “Palmoria, the Manufacturing Patriarchy”. This doesn’t look good for the owners of the business, based on their ambition to scale the business to other regions and even overseas. Cases like this can only spiral downwards, revealing other issues like the gender pay gap, amongst other possible issues. The CEO of Palmoria, Mr Ayodeji Chukwuma, is keen to address these issues before they get out of hand. The CHRO, Mr Yunus Shofoluwe, has been assigned the task to identify key areas within the business that could give rise to issues and address them immediately. Mr Shofoluwe decided to recruit an HR Analytics expert to analyse the company’s HR data and come up with recommendations for management’s attention. 
### Data Source 
DSA Data Analysis Capstone Project 
### Tools Used
- Ms powerbi for Data Cleaning and Exploratory Data Analysis (EDA) 
- DAX (Data Analysis Expressions)
- Visual filters and slicers for interactivity
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

### File Contents
- PalmoriaData.pbix – Power BI file with interactive dashboards.
- Screenshots of visuals (optional, if you add them):
- Gender Distribution Overview
- Performance Rating Analysis
- Salary Insights
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
- Gender Distribution
Balanced Representation: The overall gender distribution is nearly equal — 49.15% Male, 46.62% Female, and 4.23% N/A (undisclosed).

By Department & Location: Gender is fairly distributed across departments and cities (Abuja, Kaduna, and Lagos), indicating an inclusive workforce.

- Performance Ratings
Majority Rated Average: Most employees received an "Average" rating, with fewer rated "Very Good" or "Very Poor".

No Major Bias by Gender: Male and female employees received similar rating patterns, suggesting no visible gender bias in performance assessments.

- Salary Analysis
Average Salary: The overall average salary across all employees is $73.7K.

By Gender: While total salaries vary, average salaries are fairly balanced between male and female employees.

Top-Paying Departments: Roles in Business Development, Marketing, and Product Management offer the highest average salaries.

Location-Based Pay: Lagos has the highest average salary, followed by Kaduna, then Abuja.

- Gender by Salary Band
This horizontal bar chart shows the number of employees by salary band, broken down by gender.

From the bars, the gender distribution is consistent across salary bands, with similar counts — likely implying minimal gender pay disparity within bands, but it’s unclear if male/female breakdown is visually separated (the chart might just show total count).

- Employees Below Minimum Salary by Location
This chart shows how many employees in each location earn below the minimum salary.

Kaduna has the highest number, followed by Abuja, and Lagos has the fewest.

This might highlight:

Regional inequality in pay structure,

Or cost-of-living adjustments not being factored evenly across regions.

- Location Slicer
At the bottom, there's a slicer to filter visuals by Location (Abuja, Kaduna, Lagos).

This makes it easier to do comparative analysis per location.



![image](https://github.com/user-attachments/assets/2a5462cf-6be4-4e2f-8729-4c116f3d0265)

![image](https://github.com/user-attachments/assets/9a0df48b-4bef-450f-8ac1-099c69411430)

![image](https://github.com/user-attachments/assets/7c7fba63-7887-4311-88f1-987326ee692f)

![image](https://github.com/user-attachments/assets/987ed63a-356d-4cf2-aed6-ce0a3d4dfad8)

