# ![CapstoneHR Logo](Assets/HRlogo.png)

##  Project Overview – IBM HR Attrition Analysis

This capstone project explores employee attrition using a real-world HR dataset provided by IBM. The goal is to identify key factors that influence employee turnover and develop predictive models that help HR teams make informed, data-driven decisions.

Using Python (Pandas, Seaborn, Matplotlib, Scikit-learn, Plotly) and Power BI, the project combines data analysis, visual storytelling, and machine learning to uncover insights around employee behaviour, job satisfaction, and organisational trends.

---

###  Project Objectives

- Investigate which personal and professional attributes (e.g., age, income, education, tenure) are linked to higher attrition risk
- Explore whether performance ratings correlate with attrition, satisfaction, or promotion likelihood
- Identify early warning signs of voluntary attrition
- Examine how departmental trends influence turnover, especially within high-performing teams
- Build classification models to predict which employees are at risk of leaving

---

###  Dataset

- Source: [IBM HR Analytics Attrition Dataset on Kaggle](https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset)
- Contains demographic, job-related, and performance data for 1,470 employees

---

###  Project Structure

1. **Data Cleaning & Preprocessing**  
   - Removed constant columns
   - Encoded categorical variables (e.g., Attrition → binary)
   - Saved processed dataset for modelling

2. **Exploratory Data Analysis (EDA)**  
   - Bar charts, histograms, and heatmaps to explore trends in attrition by department, role, income, and satisfaction

   ###  Categorical Feature Distributions
   ![Attrition by Department](images/categorical_distribution_dashboard.png)
   ##  Insights
 - The bar charts display the distribution of employees across key categorical features: `Attrition`, `JobRole`, `Department`, `MaritalStatus`, and `EducationField`.  
-  **Attrition:** Majority of employees stayed with the company, with only a small proportion leaving (class imbalance noted earlier).  
-  **JobRole:** Certain roles like *Sales Executive* and *Research Scientist* have higher counts, while others such as *Human Resources* are underrepresented.  
-  **Department:** Most employees work in *Research & Development*, followed by *Sales*; *Human Resources* has the fewest employees.  
-  **MaritalStatus:** A relatively even distribution between *Married* and *Single* employees, with fewer *Divorced*.  
-  **EducationField:** *Life Sciences* and *Medical* dominate, with other fields like *Human Resources* and *Technical Degree* being less common.  
-  These insights will help identify potential patterns and imbalances within categorical variables, which could influence attrition trends and predictive modelling.

   ###  Correlation Heatmap
   ![Correlation Heatmap](images/eda_heatmap.png)
   ## Insights
   **Strong Positive Correlations:**
  - `JobLevel` and `MonthlyIncome` (**+0.95**): Higher job levels are associated with higher monthly income, which is expected in organisational structures.
  - `TotalWorkingYears` and `MonthlyIncome` (**+0.77**): Employees with more experience tend to earn more.
  - `TotalWorkingYears` and `JobLevel` (**+0.78**): Senior employees tend to hold higher job levels.

-  **Moderate Positive Correlations:**
  - `Age` and `TotalWorkingYears` (**+0.68**): Older employees generally have more work experience.
  - `Age` and `MonthlyIncome` (**+0.64**): Older employees tend to have higher salaries.

-  **Weak or No Correlations:**
  - `DailyRate`, `HourlyRate`, and `MonthlyRate` show very low correlations with other salary-related features. This suggests these rates might not provide much predictive value for attrition.

-  **Negligible/Negative Correlations:**
  - `PercentSalaryHike` and `MonthlyIncome` (**+0.03**): Salary hikes are not strongly correlated with income levels—indicating hikes may be percentage-based rather than absolute.
  - `YearsAtCompany` and `YearsSinceLastPromotion` (**+0.35**): Moderate correlation—employees at a company longer are slightly more likely to have been promoted recently.

   ###  Monthly Income Distribution with Normal Curve
   ![Monthly Income Distribution with Normal Curve](images/Histogram_KDE_Curve.png)
## Insights:
- The histogram shows the actual income distribution.
- The red dashed line is the idealised normal distribution with the dataset’s mean and standard deviation.
- Deviations from the normal curve highlight skewness or outliers in salary data.
   ###  Monthly Income vs Age by Attrition Status
   ![Monthly Income vs Age by Attrition Status](images/newplot.png)
##  Insights
-   The scatter plot visualises employees’ **Age** vs **Monthly Income**, with:
  - Bubble size representing **Total Working Years**.
  - Colour indicating **Attrition status** (`Yes` = left, `No` = stayed).
  - Hover data showing employee **JobRole** for deeper exploration.

-   Clear positive trend between **Age** and **Monthly Income**: Older employees tend to earn higher salaries.

-   Larger bubbles (more Total Working Years) are concentrated at higher income levels, as expected.

-   Attrition (`Yes`) data points are scattered across age and income ranges but appear slightly more frequent among younger and lower-income employees.

-   This visualisation helps identify potential patterns between employee demographics, tenure, and attrition risk.

3. **Modelling**  
   - Logistic Regression  
   - Decision Tree Classifier  
   - Evaluation using accuracy, classification report, and confusion matrix  
   - Reflections on performance and class imbalance

4. **Dashboard Visualisation (Power BI)**  
   - Page 1: Workforce Overview — attrition by age, tenure, department  
   - Page 2: Statistical Insights — mean & variance, dynamic slicers to drill down by education, department, and satisfaction
---

###  Key Takeaways

- Class imbalance (only ~16% attrition) heavily influences model performance  
- Job level, total working years, and monthly income are strongly correlated  
- Satisfaction levels and short tenure appear to be early warning signs  
- Dashboards and visual storytelling can turn technical metrics into business-relevant insight
---

This project demonstrates a complete data analysis pipeline — from cleaning and visualisation to predictive modelling and stakeholder-ready dashboards.

## Project Plan & Dashboard Communication Strategy

###  Project Plan

This capstone project followed a structured data analysis pipeline, documented in the Jupyter Notebook and supported by the Power BI dashboard:

1. **Data Loading & Inspection**  
   - Reviewed the IBM HR Attrition dataset from Kaggle to understand structure, size, and feature types.

2. **Data Cleaning & Preprocessing**  
   - Removed irrelevant features, handled missing values, and encoded the target variable (`Attrition`) for modelling.

3. **Exploratory Data Analysis (EDA)**  
   - Used Python libraries (Seaborn, Matplotlib, Plotly) to uncover patterns in attrition by department, satisfaction, income, and experience.

4. **Modelling**  
   - Trained Logistic Regression and Decision Tree models to predict attrition.
   - Evaluated using accuracy, confusion matrix, and classification report.

5. **Reflection & Insights**  
   - Addressed class imbalance challenges.
   - Explained rationale behind methods and improvements made (e.g. model tuning, feature selection).

6. **Power BI Dashboard Creation**  
   - Built to communicate key findings interactively to both technical and business audiences.
---

###  Power BI Dashboard Design

The dashboard was structured across two pages to balance **strategic business insights** with **technical depth**:
##  Power BI Dashboard

###  Page 1: Company Workforce Summary

Visualisations include:
- Attrition by education level
- Monthly income vs age with attrition
- Attrition rate by department and tenure
- Number of leavers by satisfaction level

![Company Workforce Summary](images/dashboard_page1.png)

---

###  Page 2: Statistical Insights

Visualisations include:
- Mean and variance of Monthly Income for leavers
- Interactive slicers by Department, Tenure Group, and Education Level
- Insights into pay structure and attrition relationships

![Statistical Insights](images/dashboard_page2.png)


####  Page 1: Workforce Summary
This page targets **non-technical stakeholders (e.g., HR Managers)** by visually summarising workforce dynamics:

- **Attrition by Education Label**  
  Shows educational backgrounds of employees leaving the company.

- **Attrition & Average Monthly Income by Age**  
  Highlights income-age patterns and retention across generations.

- **Attrition Rate by Department**  
  Identifies departments with the highest turnover rates.

- **Attrition & Income by Tenure Group**  
  Reveals how long-serving employees compare to newer hires in terms of pay and attrition.

- **Work-Life Balance vs. Attrition**  
  Compares satisfaction levels to turnover, indicating which groups are at risk.

 *Purpose:* To support data-driven HR policies by clearly communicating trends and risks.

---

####  Page 2: Statistical Insights
This page supports **technical audiences and analysts** seeking deeper understanding through statistical metrics:

- **Mean & Variance of Monthly Income (Attrition = Yes)**  
  Analyses income variability among those who left.

- **Slicers (Department, Tenure Group, Education Level)**  
  Enable focused exploration of how attrition correlates with demographic and career factors.

  *Purpose:* To uncover nuanced drivers of attrition and support advanced segmentation strategies.
---

###  Communication Approach

- **For Technical Audiences:**  
  Jupyter Notebook includes detailed code, statistical outputs, modelling logic, and reflections on limitations.

- **For Non-Technical Stakeholders:**  
  Power BI visualisations simplify key insights (e.g., who is leaving and why) through clear charts, filters, and KPIs.

This dual approach ensures that findings are **accessible, actionable, and relevant** to a wide range of decision-makers.

##  8.2 – Employ Visualisations and Narratives to Enhance User Understanding

This project integrates a range of visualisation tools and narrative techniques to support both technical analysis and stakeholder communication.

###  In the Jupyter Notebook:
Visual tools such as **Matplotlib**, **Seaborn**, and **Plotly** were used to:

- Explore feature distributions (e.g., Attrition by Department, Education Field)
- Reveal correlations between numeric features using a **heatmap**
- Create **interactive dashboards** with Plotly to drill into department-level attrition and satisfaction trends

Each visualisation is accompanied by **clear markdown commentary** explaining:
- What the chart shows
- Why the chart is relevant
- Key insights and limitations

###  In the Power BI Dashboard:
Two dashboard pages were created to support **different audience needs**:

1. **Company Workforce Summary**
   - Shows high-level trends in attrition by education, department, age, tenure, and satisfaction

2. **Statistical Insights**
   - Communicates technical metrics like **mean** and **variance** using slicers and dynamic filtering

Design choices (e.g., bar charts, line graphs, tooltip details) were made to enhance **clarity and interpretability** for both technical and non-technical users.
---
These elements collectively ensure that the analysis is not only robust but also **accessible and actionable**, meeting the 8.2 requirement.

## Reflection on Learning Process

This capstone project has been a significant learning journey, pushing me to apply and deepen my skills in data analytics. Initially, I faced several challenges ranging from dataset handling and cleaning, to creating meaningful visualisations and communicating findings effectively through both code and narrative. These challenges ultimately became learning opportunities that strengthened my technical foundation and problem-solving mindset.

### Key Learning Moments

- **File structuring and output saving**  
  I initially struggled with correct file path management in VSCode, which led to output errors. Through trial and error, and by researching `os.makedirs()` and proper directory handling, I successfully implemented a clear project structure.

- **Plotly and data visualisation**  
  Although familiar with static visualisation, adapting to Plotly's interactive features required additional learning. I overcame this by reading documentation, watching tutorials, and experimenting with different chart types.

- **Git and version control**  
  I improved my understanding of Git commands and commit practices, particularly when syncing changes from VSCode to GitHub.

---

## Strategies for Overcoming Challenges

To address challenges, I used a variety of strategies:

- **Incremental testing**  
  I tested code blocks in isolation to identify where things were breaking.

- **Using community resources**  
  Platforms like Stack Overflow and GitHub issues were instrumental in resolving bugs and understanding best practices.

- **Peer feedback**  
  I received informal feedback on presentation and code readability from peers, which led me to better comment my code and restructure my analysis for clarity.

---

## Bug Fixes and Adaptations

Examples of how I adapted my code during the project:

- **FileNotFoundError when loading data**  
  I realised I needed to create directories dynamically and ensure file paths were correct. Solved with:  
  ```python
  os.makedirs('data/inputs/raw', exist_ok=True)

## Data cleaning inconsistencies
Learned to use:
df.isnull().sum() 
df.duplicated().sum()
to identify and address missing or duplicate data effectively.

## Visualisation bugs
When visualisations failed to render due to data type issues, I used df.dtypes and resolved them through appropriate type casting.

### Development Roadmap
| **Skill / Tool**         | **Why It’s Next**                                                   | **Planned Approach**                                 |
| ------------------------ | ------------------------------------------------------------------- | ---------------------------------------------------- |
| **Deployment Tools**     | To deploy notebooks as web apps or dashboards                       | Learn basics of Streamlit and Flask                  |
| **Machine Learning**     | To move from descriptive to predictive analytics                    | Explore supervised learning using Scikit-learn       |

##  Technology Framework

| **Tool / Technology**               | **Purpose**                                                  |
|------------------------------------|--------------------------------------------------------------|
| **Pandas, NumPy, Matplotlib, Seaborn** | Core Python libraries used for data analysis, processing, and basic visualisation. |
| **Plotly**                         | Used for creating interactive and faceted data visualisations in Python. |
| **Power BI**                       | Used to create an interactive dashboard for visualising and presenting key insights to stakeholders. |
| **GitHub (Kanban & Repository)**   | Used for project management, version control, and documenting progress. |

## Deployment & Accessibility

- **Power BI Dashboard**:  
  [HR Analytics Dashboard – Power BI (Web Link)](https://app.powerbi.com/groups/me/reports/Dashboard/CapstoneHRPBVisual.pbix)  
  *An interactive dashboard visualising key HR insights such as attrition trends, job satisfaction, and department-wise performance.*

- **Jupyter Notebook**:  
   [CapstoneHR Analysis Notebook](notebooks/jupyter_notebooks/data_investigation.ipynb)  
  *Complete analysis including data cleaning, EDA, visualisations, and reflections using Python.*

- **GitHub Repository**:  
  [CapstoneHR GitHub Repo](https://github.com/Shema774/CapstoneHR)  
  *Clone and install required dependencies:*  
  ```bash
  pip install -r requirements.txt

