Of course! Here is the README file modified to reflect the use of **MySQL** and an **ODBC connection**.

# End-to-End Telecom Churn Analysis 📊

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)](https://www.mysql.com/)
[![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=power-bi&logoColor=black)](https://powerbi.microsoft.com/en-us/)
[![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)

An end-to-end business intelligence and machine learning project that analyzes customer churn for a **telecom company**.

This project provides a complete blueprint for building an ETL pipeline in **MySQL**, creating an interactive analytics dashboard with Power BI, and developing a predictive model to identify at-risk customers, turning raw data into actionable business insights.

---

## 🚀 Key Features

*   **⚙️ Robust ETL Pipeline:** A full Extract, Transform, Load process built in **MySQL** to ensure data integrity and efficient data handling.
*   **📊 Interactive BI Dashboard:** A comprehensive Power BI dashboard for deep-diving into historical data, visualizing churn rates across demographic, geographic, and service-level dimensions.
*   **🧠 Predictive Churn Modeling:** Utilizes a Random Forest classifier built in Python with Scikit-learn to accurately predict which new customers are likely to churn.
*   **📈 Actionable Insights:** Identifies key drivers of churn and profiles at-risk customers, enabling targeted marketing campaigns for retention.
*   **🔌 Flexible Connectivity:** Uses an **ODBC connection** to link the Power BI dashboard to the MySQL database, demonstrating a common enterprise integration pattern.

---

## 💡 How It Works

The project follows a multi-stage pipeline to move from raw data to predictive insights:

1.  **ETL in MySQL:** Raw customer data (`.csv`) is loaded into a staging table in a MySQL database. Null values are handled (using `IFNULL` or `COALESCE`), data types are corrected, and the cleaned data is moved to a production table. SQL Views are then created to segment the data for analysis.
2.  **BI Visualization in Power BI:** Power BI connects to the MySQL database via an **ODBC driver**. The data model is enriched with calculated columns and DAX measures (`Churn Rate`, `Total Customers`). An interactive dashboard is built to analyze historical churn trends.
3.  **Machine Learning with Python:** The data is exported and loaded into a Jupyter Notebook. `Pandas` is used for preprocessing, and categorical features are encoded. A `Random Forest` model is trained on historical data using `Scikit-learn`.
4.  **Prediction on New Data:** The trained model is used to predict the likelihood of churn for new customers. The list of predicted churners is exported, enabling proactive business action.

---

## 🛠️ Tech Stack

The project integrates a standard stack of data analytics and business intelligence tools.

| Component | Tool | Purpose |
| :--- | :--- | :--- |
| **Database / ETL** | **MySQL** | Manages the core data loading, cleaning, and transformation workflow. |
| **BI & Visualization**| **Power BI** | Creates the interactive dashboard for historical analysis and reporting. |
| **Connectivity** | **ODBC Driver** | Provides a standardized connection between Power BI and MySQL. |
| **Machine Learning** | **Python** & **Scikit-learn** | Drives the predictive modeling to identify future churners. |
| **ML Environment** | **Jupyter Notebook** | Provides an interactive environment for developing the ML model. |

---

## ⚙️ Installation & Setup

Follow these steps to replicate the project on your own machine.

### Prerequisites
*   [MySQL Server](https://dev.mysql.com/downloads/mysql/) & a client like [MySQL Workbench](https://dev.mysql.com/downloads/workbench/)
*   [MySQL ODBC Driver](https://dev.mysql.com/downloads/connector/odbc/) (ensure the bitness—32-bit or 64-bit—matches your Power BI installation)
*   [Power BI Desktop](https://powerbi.microsoft.com/en-us/downloads/)
*   [Anaconda Distribution (for Python/Jupyter)](https://www.anaconda.com/download)

### 1. Download the Dataset
Download the project data from the link below and unzip the file.
*   **Dataset**: [Data-Resources.zip](https://pivotalstats.com/wp-content/uploads/2024/08/Data-Resources.zip)

### 2. Set Up the MySQL Database
1.  Open **MySQL Workbench** and connect to your database instance.
2.  Create a new schema (database) named `db_churn`.
3.  In the new schema, right-click **Tables** and select **Table Data Import Wizard**. Import the project's CSV file into a new staging table (`stg_churn`).
4.  Run the SQL scripts provided in the original project guide. **You will need to adapt the syntax for MySQL** (e.g., change `ISNULL` to `IFNULL` or `COALESCE`). The goal is to create the production table (`prod_churn`) and the views (`vw_churn_data`, `vw_join_data`).

### 3. Set Up the Power BI Dashboard
1.  Install and configure the MySQL ODBC driver on your system by setting up a new DSN (Data Source Name).
2.  Open **Power BI Desktop**. Click **Get Data**, search for **ODBC**, and select it.
3.  Choose the DSN you configured for your MySQL database from the dropdown menu.
4.  Connect to and import the `vw_churn_data` and `vw_join_data` views.
5.  Follow the transformation steps in **STEP 2** and create the DAX measures from **STEP 3** of the original guide to build out the dashboard visuals.

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
