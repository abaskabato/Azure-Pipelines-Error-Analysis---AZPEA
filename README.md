**Azure-Pipelines-Error-Analysis-AZPEA**

The primary objective of this project is to analyze the release logs of build pipelines and provide developers with insights into the most common errors encountered during the build-release process. Additionally, we aim to analyze the usage of Azure resources and report the curated data back to the developer team. Please refer to the data flow diagram for a better understanding of the process.

**Introduction**

In this section, we will provide examples of the ten most common errors and specific case errors that have occurred in the release process within the last 30 days. We will also extract Azure Resource Usage data, including details such as quotas, percentage usage, VM creation dates, and VM statuses.

**Tools Used**
To accomplish the goals mentioned above, we will utilize the following tools:
- Azure Data Explorer (ADX)
- PowerShell Integrated Scripting Environment (ISE)

**Programming Languages Used**
We will work with the following programming languages:
- PowerShell
- Kusto Query Language (KQL)

**Content**
The project includes the following components:
- Azure Resource Usage PowerShell Script
- Extract Release Most Common Errors KQL file

**Script Usage to get Azure Resource Usage data**

To extract Azure Resource Usage data, follow these steps:
1. Access PowerShell ISE on your development box.
2. Copy the "AzureResourceUsage.ps1" file from the Azure Resource Usage PS scripts folder and paste it into the PowerShell ISE environment.
Please replace the placeholder values (e.g., YourTenantId, YourClientId, YourClientSecret, YourSubscriptionId) with your actual Azure credentials and adjust the email configuration (e.g., SMTP server, sender, recipient) according to your setup.
3. Remember to install the Az module (Install-Module -Name Az) and import it (Import-Module Az) before executing the script.
After running the script, you can expect to find the following files on your desktop:
1.example_QuotaUsage_VMs.csv
2.example_Data_VMs.csv
3.example_Status_VMs.csv
4.example_CreationDate_VMs.csv
5.example_Resource_VMs_Ntks.csv
An email will be sent to exampleSupportTeam@examplehost.com, attaching the five CSV files.


**Script Usage toRelease Error Analytics**

To analyze release errors, please follow these steps:
1. Access Azure Data Explorer (ADX) through https://dataexplorer.azure.com.
2. Copy the "ExtractReleaseMostCommonErrors.kql" file from the Extract Release Most Common Errors folder and paste it into the Azure Data Explorer Kusto (KQL) running environment.
3. Read the comments above each KQL block and run them accordingly. To execute each block of KQL code, you can either click the play icon or press Shift + Enter while the code is selected.
4. You can download any data outcome into Excel by clicking on the "File" icon at the top of the page.
