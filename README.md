

---

# **Azure Pipelines Error Analysis (AZPEA)**  

## **Objective**  
The primary goal of the AZPEA project is to analyze the release logs of build pipelines to provide developers with actionable insights into the most frequent errors encountered during the build-release process. Additionally, the project aims to examine Azure resource usage and share curated data with the developer team to enhance decision-making.  

Refer to the **data flow diagram** for a visual representation of the process.  

---

## **Introduction**  
This project will:  
1. Identify and detail the **10 most common errors** in the release process over the past 30 days.  
2. Analyze and report **Azure Resource Usage** data, including:  
   - Quota and percentage usage.  
   - VM creation dates and statuses.  

---

## **Tools Used**  

### **Technologies**  
- **Azure Data Explorer (ADX):** For querying release logs and errors.  
- **PowerShell ISE:** To execute scripts for resource usage data extraction.  

### **Languages**  
- **PowerShell**  
- **Kusto Query Language (KQL)**  

---

## **Components**  
The project comprises three main components:  

1. **Azure Resource Usage Script**  
   - Extracts data such as quota usage, VM statuses, and creation dates.  
2. **Extract Release Most Common Errors KQL File**  
   - Analyzes release errors in Azure Data Explorer.  
3. **Documentation for Script Execution and Data Extraction**  
   - Provides step-by-step guidance for using the scripts and KQL files.  

---

## **Instructions**  

### **1. Azure Resource Usage Data Extraction**  

#### **Steps**  
1. Open **PowerShell ISE** on your local development machine.  
2. Load the `AzureResourceUsage.ps1` script from the project’s **Azure Resource Usage PS Scripts** folder.  
3. Replace placeholder credentials in the script:  
   - `YourTenantId`  
   - `YourClientId`  
   - `YourClientSecret`  
   - `YourSubscriptionId`  
4. Update the email configuration settings:  
   - **SMTP Server**  
   - **Sender and Recipient Email Addresses**  

#### **Pre-requisites**  
- Ensure the **Az module** is installed:  
  ```powershell
  Install-Module -Name Az
  ```  
- Import the module:  
  ```powershell
  Import-Module Az
  ```  

#### **Execution**  
- Run the script in PowerShell ISE.  

#### **Outputs**  
The script will generate the following CSV files on your desktop:  
1. `example_QuotaUsage_VMs.csv`  
2. `example_Data_VMs.csv`  
3. `example_Status_VMs.csv`  
4. `example_CreationDate_VMs.csv`  
5. `example_Resource_VMs_Ntks.csv`  

Additionally, an email with these files will be sent to:  
`exampleSupportTeam@examplehost.com`.  

---

### **2. Release Error Analysis**  

#### **Steps**  
1. Log in to **Azure Data Explorer (ADX)** at [Azure Data Explorer](https://dataexplorer.azure.com).  
2. Load the `ExtractReleaseMostCommonErrors.kql` script from the **Extract Release Most Common Errors** folder.  
3. Follow the comments above each KQL query block for execution instructions.  
   - To run a query block, either:  
     - Click the **Play** icon.  
     - Or press **Shift + Enter** while selecting the code.  

#### **Exporting Results**  
- To download the query results in Excel format:  
  - Click the **File** icon on the top toolbar and select **Export**.  

---

## **Expected Deliverables**  

### **Error Analysis**  
- A report detailing the **top 10 release errors** over the past month, including error descriptions, frequencies, and impact assessments.  

### **Azure Resource Usage Report**  
- Comprehensive resource usage data in CSV format, covering:  
  - Quota usage percentages.  
  - VM statuses.  
  - Creation dates and networking configurations.  

---

This documentation ensures seamless execution of the AZPEA project, providing clear guidance for analyzing pipeline errors and Azure resource usage. For any issues or queries, please reach out to the support team at `exampleSupportTeam@examplehost.com`.  

--- 
