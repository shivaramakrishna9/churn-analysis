# End-to-End Telecom Churn Analysis 📊

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Microsoft SQL Server](https://img.shields.io/badge/SQL_Server-CC2927?style=for-the-badge&logo=microsoft-sql-server&logoColor=white)](https://www.microsoft.com/en-us/sql-server)
[![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=power-bi&logoColor=black)](https://powerbi.microsoft.com/en-us/)
[![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)

An end-to-end business intelligence and machine learning project that analyzes customer churn for a **telecom company**.

This project provides a complete blueprint for building an ETL pipeline, creating an interactive analytics dashboard, and developing a predictive model to identify at-risk customers, turning raw data into actionable business insights.

---

## 🚀 Key Features

*   **⚙️ Robust ETL Pipeline:** A full Extract, Transform, Load process built in SQL Server to ensure data integrity and efficient data handling.
*   **📊 Interactive BI Dashboard:** A comprehensive Power BI dashboard for deep-diving into historical data, visualizing churn rates across demographic, geographic, and service-level dimensions.
*   **🧠 Predictive Churn Modeling:** Utilizes a Random Forest classifier built in Python with Scikit-learn to accurately predict which new customers are likely to churn.
*   **📈 Actionable Insights:** Identifies key drivers of churn and profiles at-risk customers, enabling targeted marketing campaigns for retention.
*   **🔧 End-to-End Workflow:** A seamless, replicable process from initial data loading in a database to final predictive analysis and visualization.

---

## 💡 How It Works

The project follows a multi-stage pipeline to move from raw data to predictive insights:

1.  **ETL in SQL Server:** Raw customer data (`.csv`) is loaded into a staging table in a SQL Server database. Null values are handled, data types are corrected, and the cleaned data is moved to a production table. SQL Views are then created to segment the data for analysis.
2.  **BI Visualization in Power BI:** Power BI connects directly to the SQL Server views. The data model is enriched with calculated columns and DAX measures (`Churn Rate`, `Total Customers`). An interactive dashboard is built to analyze historical churn trends.
3.  **Machine Learning with Python:** The data is exported and loaded into a Jupyter Notebook. `Pandas` is used for preprocessing, and categorical features are encoded. A `Random Forest` model is trained on historical data using `Scikit-learn`.
4.  **Prediction on New Data:** The trained model is used to predict the likelihood of churn for new customers. The list of predicted churners is exported, enabling proactive business action.

---

## 🛠️ Tech Stack

The project integrates a standard stack of data analytics and business intelligence tools.

| Component | Tool | Purpose |
| :--- | :--- | :--- |
| **Database / ETL** | **SQL Server** | Manages the core data loading, cleaning, and transformation workflow. |
| **BI & Visualization**| **Power BI** | Creates the interactive dashboard for historical analysis and reporting. |
| **Machine Learning** | **Python** & **Scikit-learn** | Drives the predictive modeling to identify future churners. |
| **ML Environment** | **Jupyter Notebook** | Provides an interactive environment for developing the ML model. |
| **Data Handling** | **Pandas** | Used within Python for data manipulation and preparation for the ML model. |

---

## ⚙️ Installation & Setup

Follow these steps to replicate the project on your own machine.

### Prerequisites
*   [Microsoft SQL Server](https://www.microsoft.com/en-us/sql-server/sql-server-downloads) & [SSMS](https://learn.microsoft.com/en-us/sql/ssms/download-sql-server-management-studio-ssms)
*   [Power BI Desktop](https://powerbi.microsoft.com/en-us/downloads/)
*   [Anaconda Distribution (for Python/Jupyter)](https://www.anaconda.com/download)

### 1. Download the Dataset
Download the project data from the link below and unzip the file.
*   **Dataset**: [Data-Resources.zip](https://pivotalstats.com/wp-content/uploads/2024/08/Data-Resources.zip)

### 2. Set Up the SQL Database
1.  Open **SQL Server Management Studio (SSMS)** and connect to your database engine.
2.  Create a new database named `db_Churn`.
3.  Right-click the database, go to **Tasks -> Import Flat File...**, and import the project's CSV data into a staging table (`stg_Churn`).
4.  Run the SQL scripts from **STEP 1** of the project guide to clean the data, create the production table (`prod_Churn`), and create the views (`vw_ChurnData`, `vw_JoinData`).

### 3. Set Up the Power BI Dashboard
1.  Open **Power BI Desktop**.
2.  Connect to your SQL Server database and import the `vw_ChurnData` and `vw_JoinData` views.
3.  Follow the transformation steps in **STEP 2** and create the DAX measures from **STEP 3** of the guide to build out the dashboard visuals.

### 4. Run the Prediction Model
1.  Open **Anaconda Prompt** and install the required libraries:
    ```bash
    pip install pandas numpy matplotlib seaborn scikit-learn joblib openpyxl
    ```
2.  Launch **Jupyter Notebook** and create a new notebook.
3.  Follow the Python code in **STEP 5** of the project guide to load the data, train the Random Forest model, and generate predictions.
    *(Remember to update the file paths in the script to match your local machine.)*

---

## 🤝 Contributing

Contributions are what make the open-source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

To contribute:
1.  Fork the Project
2.  Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3.  Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4.  Push to the Branch (`git push origin feature/AmazingFeature`)
5.  Open a Pull Request

---

## 📄 License

This project is distributed under the MIT License. See the `LICENSE` file for more information.
