# PwC Workforce Analytics: Performance, Promotions, and Diversity
![image](https://github.com/user-attachments/assets/98c14d9e-cd09-478b-88ff-214e814470c0)

## **Link to the Project:**
https://app.powerbi.com/groups/me/reports/ec9894b8-b632-45b7-beb9-69c72347cac4/86bc10f390e3aabcab72?experience=power-bi

---

## **Table of Contents:**
1. Project Description
2. Technologies Used
3. Features
4. Project Implementation
5. Logical Diagram
6. Example DAX Code for Data Analysis

---

## **1. Project Description:**

In this project, I analyzed workforce data to examine performance, promotions, and diversity metrics, particularly focusing on gender-related KPIs. This project was completed as part of PwC Switzerland's Power BI Virtual Internship on Forage. The primary objective was to identify the root causes of gender balance issues at the executive management level, enabling data-driven decisions and visualizing insights for effective communication.

- **FY20 Performance by Gender**: A visual representation of how performance ratings differ between male and female employees for fiscal year 2020.
  
- **Turnover Rate by Gender**: This view highlights the turnover rate among male and female employees.
  
- **Promotions by Gender**: Compares the promotion rates of male and female employees in FY20 and FY21.
  
- **Age Distribution**: Visualizes the distribution of employees by age to understand the workforce's demographic breakdown.
  
- **Gender Distribution**: Displays the gender split in the workforce, focusing on the ratio of male to female employees.

---

## **2. Technologies Used:**
- **Power BI**: For creating the dashboards and visualizations.
- **DAX (Data Analysis Expressions)**: Used for data manipulation and calculations within Power BI.
- **Excel/CSV**: Data imported from CSV files for analysis.
- **GitHub**: For version control and project repository hosting.

---

## **3. Features:**
- **Interactive Filters**: Users can filter data by department and gender to view specific insights.
- **Performance vs. Promotions Analysis**: Comparison of employee performance ratings against promotions to evaluate disparities between genders.
- **Age and Tenure Analysis**: Visualization of the workforce's age distribution and average tenure to examine demographic trends.
- **Custom KPIs**: Key Performance Indicators (KPIs) for turnover rate, gender distribution, and average years since last hire.
  
---

## **4. Project Implementation:**

### **Step 1: Data Preparation**
- HR data was imported from CSV files and cleaned to remove duplicates and inconsistencies.
  
### **Step 2: Dashboard Design**
- Various visualizations were created using Power BI, such as bar charts, scatter plots, and pie charts, to represent performance, promotions, and workforce diversity.

### **Step 3: Filters and Interactivity**
- Filters for gender and department were added to allow users to drill down into specific categories.

### **Step 4: Insights and Communication**
- Insights derived from the data were communicated to engagement partners through clear, actionable emails and presentations.


---

## **5. Example DAX Code for Data Analysis**

Here are examples of DAX formulas used to create calculated columns and measures for analysis:

```dax
-- Calculating the average tenure of employees
AverageTenure = AVERAGE(Employee[YearsSinceLastHire])

-- Calculating the promotion rate by gender
PromotionRate = 
    CALCULATE(
        COUNT(Employee[EmployeeID]),
        Employee[PromotionStatus] = 1
    ) / 
    CALCULATE(
        COUNT(Employee[EmployeeID]),
        ALL(Employee[PromotionStatus])
    )

-- Turnover rate by gender
TurnoverRate = 
    CALCULATE(
        COUNT(Employees[EmployeeID]),
        Employee[TurnoverStatus] = "Yes"
    ) / 
    CALCULATE(
        COUNT(Employee[EmployeeID]),
        ALL(Employee[TurnoverStatus])
    )
