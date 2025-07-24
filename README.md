# ![CapstoneHR Logo](Assets/HRlogo.png)




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



1appear in the file explorer pane to show that the virtual environment has been created.

1. **Important**: Note that the `.venv` folder is in the `.gitignore` file so that Git won't track it.

1. Return to the terminal by clicking on the TERMINAL tab, or click on the **Terminal** menu and choose **New Terminal** if no terminal is currently open.

1. In the terminal, use the command below to install your dependencies. This may take several minutes.

 ```console
 pip3 install -r requirements.txt
 ```

1. Open the `jupyter_notebooks` directory, and click on the notebook you want to open.

1. Click the **kernel** button and choose **Python Environments**.

Note that the kernel says `Python 3.12.8` as it inherits from the venv, so it will be Python-3.12.8 if that is what is installed on your PC. To confirm this, you can use the command below in a notebook code cell.

```console
! python --version
```

## Deployment Reminders

* Set the `.python-version` Python version to a [Heroku-22](https://devcenter.heroku.com/articles/python-support#supported-runtimes) stack currently supported version that closest matches what you used in this project.
* The project can be deployed to Heroku using the following steps.

1. Log in to Heroku and create an App
2. At the **Deploy** tab, select **GitHub** as the deployment method.
3. Select your repository name and click **Search**. Once it is found, click **Connect**.
4. Select the branch you want to deploy, then click **Deploy Branch**.
5. The deployment process should happen smoothly if all deployment files are fully functional. Click the button **Open App** at the top of the page to access your App.
6. If the slug size is too large, then add large files not required for the app to the `.slugignore` file.
