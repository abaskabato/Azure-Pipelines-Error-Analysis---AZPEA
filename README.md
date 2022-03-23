This project is temporarily posted as sample work. 

# Azure-Pipelines-Error-Analysis---AZPEA

Goal: The first goal is analyzing build pipeline release logs and sending the analytics result to a team of developers with the most common errors during build release. The second goal is analyzing used Azure resource and reporting the curated data back to the developer team.  Please review the data flow diagram. 

#Introduction  
  *  Providing example of 10 most common errors & Specific case errors in the release that have occured in the last 30 days. 
  *  Extracting example of Azure Resource Usage Data and  detailing Quota's, Percentage Usage, VMs creation Date and VMs Status. 
  
#USED TOOLS 
  *  ADX - Azure data explorer  
  *  Powershell ISE 

#USED PL
  *  Powershell
  *  Kusto Query Language - KQL 

#CONTENT 
1. Azure Pipeline Slack App 
2. Azure Resource Usage PS Script
3. Extract Release Most Common Errors KQL file  

                                              Script Usage

# Azure Resource Usage.
1. Access The "Powershell ISE" through your Development Box 
2. Copy  "AzureResourceUsage.ps1" from Azure Resource Usage PS scripts  folder and Paste it into the environment of Powershell ISE. 
3. After Running your Script, Expect to have 1.example_QuotaUsage_VMs.csv , 2. example_Data_VMs.csv , 3.example_Status_VMs.csv 4.example_CreationDate_VMs.csv 4.example_Resource_VMs_Ntks.csv on your desktop.
5. Email is sent to exampleSuportTeam@examplehost.com attaching the five Csv files.   

# Release Error analytics.
1. Access the ADX (Azure Data Explorer) through https://dataexplorer.azure.com 
2. Copy "ExtractReleaseMostCommonErrors.kql"  from Extract Release Most Common Errors folder and  paste it into Azure Data Explorer Kusto(KQL) running environment
3. Read the comments above each KQL blocks and run them accordingly. To run each block of KQL code, You can either press the play icon or click shift + Enter while being on the code
4. Any Data Outcome can be downloaded into excel by clicking up on the top "File" Icon. 
