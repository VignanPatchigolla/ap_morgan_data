# 🚀 AP Morgan Data 

## 🌟 Overview
The **AP Morgan Data** focuses on handling, validating, and processing data generated daily by internal applications. This data is initially stored in **Azure Data Lake Storage (ADLS)** and undergoes **schema validation** before being processed and stored in **Delta tables** within Databricks for downstream consumption.

## ✨ Features
- 📅 **Daily Data Processing:** Automatically processes data sent to the ADLS location.
- ✅ **Schema Validation:** Ensures data adheres to predefined schema standards using SQL Database.
- 🛠️ **Delta Lake Integration:** Stores validated data in Delta tables for analytics and downstream usage.
- 🔒 **Secure Operations:** Leverages Azure Key Vault for managing sensitive credentials securely.

## 🛠️ Architecture Workflow

1. **📥 Data Ingestion:**  
   Internal applications send data to ADLS in CSV format daily.

2. **🔍 Schema Validation:**  
   Azure Data Factory (ADF) pipelines validate the schema by querying a SQL Database.  
   Invalid data is sent to the "Rejected" folder for further review.

3. **🗂️ Data Processing in Databricks:**  
   Validated data is processed and stored in Delta tables.

4. **📊 Downstream Usage:**  
   The processed data in Delta tables is available for **Data Analytics (DA)** and **Data Science (DS)** teams.

## 🧰 Technologies Used
- 🗄️ **Azure Data Lake Storage (ADLS):** Centralized storage for raw, rejected, and processed data.
- 🔄 **Azure Data Factory (ADF):** Orchestration tool for data movement and schema validation.
- 🔐 **Azure Key Vault:** Securely manages access credentials for services.
- 🧪 **Azure Databricks:** Processes validated data and writes to Delta tables.
- 📜 **SQL Database:** Validation script for incoming data schema.

## 📂 Repository Structure
```plaintext
AP-Morgan-Data-Project/
|— DataBricks/          # Databricks notebooks for processing
|— pipeline/            # All pipelines used in this project creation
|— Datasets/            # Contains the sample data
|— MorganDataADF/       # Contains all global parameters and ARM templates used in this project
|— linkedService/       # Linked service created in ADF
|— trigger/             # Triggers used for pipeline
|— README.md            # Project overview (this file)


## 🚀 How to Use

1. **🔑 Setup Credentials:**  
   Store necessary credentials (e.g., ADLS, Databricks, SQL) in **Azure Key Vault**.

2. **🔄 Run ADF Pipelines:**  
   Execute ADF pipelines to validate and process incoming data.

3. **🧹 Validate Data:**  
   Ensure that incoming CSV data matches the expected schema.

4. **📊 Process Data:**  
   Use the provided Databricks notebooks to process validated data and store it in Delta tables.

## 🌟 Future Enhancements
- 🤖 Automate schema updates for evolving data structures.
- ⚡ Add real-time data processing capabilities.
- 📈 Improve monitoring and alerting for pipeline failures.

## 📬 Contact
For questions or support, reach out to the repository owner at [vignanpatchigolla5@gmail.com].
