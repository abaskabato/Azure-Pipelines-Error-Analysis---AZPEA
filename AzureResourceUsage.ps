Set-StrictMode -Version Latest

# Connect to Azure using service principal authentication
$tenantId = "YourTenantId"
$clientId = "YourClientId"
$clientSecret = "YourClientSecret"
$subscriptionId = "YourSubscriptionId"

$securePassword = ConvertTo-SecureString $clientSecret -AsPlainText -Force
$credential = New-Object System.Management.Automation.PSCredential($clientId, $securePassword)

Connect-AzAccount -ServicePrincipal -Credential $credential -TenantId $tenantId -SubscriptionId $subscriptionId

$location = "westus2"

# Retrieve VM usage quota
$exampleVmQuota = Get-AzVMUsage -Location $location | Select-Object Name, CurrentValue, Limit, @{Name = "Category"; Expression = {"VM"}}

# Export VM quota usage to CSV
$exampleVmQuota | Export-Csv -Path "C:\users\$env:username\desktop\example_QuotaUsage_VMs.csv" -NoTypeInformation -Force

# Retrieve VM count and IP addresses
$exampleVMsCount = Get-AzVM | Select-Object Name, @{Name = "IP Address"; Expression = {$_.GuestIPAddresses[0]}}

# Export VM count and IP addresses to CSV
$exampleVMsCount | Export-Csv -Path "C:\users\$env:username\desktop\example_VMs_Count.csv" -NoTypeInformation -Force

# Retrieve VM information and SKU data
$ServerData = Get-AzVM -Status | Where-Object { $_.Name -like "*avmced*" } | ForEach-Object {
    $VMSize = $_.HardwareProfile.VmSize
    $SKUData = Get-AzVMSize -Location $location | Where-Object { $_.Name -eq $VMSize }

    [PSCustomObject]@{
        ServerName        = $_.Name
        ResourceGroupName = $_.ResourceGroupName
        CoreCount         = $SKUData.NumberOfCores
        MemoryInMB        = $SKUData.MemoryInMB
    }
}

# Export VM data to CSV
$ServerData | Export-Csv -Path "C:\users\$env:username\desktop\example_Data_VMs.csv" -NoTypeInformation -Force

# Retrieve VM status
$GetexampleVMstatus = Get-AzVM -Status | Select-Object ResourceGroupName, Name, Location, @{Name = "VMStatus"; Expression = {$_.PowerState}}

# Export VM status to CSV
$GetexampleVMstatus | Export-Csv -Path "C:\users\$env:username\desktop\example_Status_VMs.csv" -NoTypeInformation -Force

# Retrieve VM creation date
$exampleVMCreationDate = Get-AzDisk | Select-Object Name, ResourceGroupName, TimeCreated

# Export VM creation date to CSV
$exampleVMCreationDate | Export-Csv -Path "C:\users\$env:username\desktop\example_CreationDate_VMs.csv" -NoTypeInformation -Force

# Retrieve resource usage for VMs and networks
$exampleVms = Get-AzVMUsage -Location $location | Select-Object @{Name = "Name"; Expression = {$_.Name.LocalizedValue}}, CurrentValue, Limit, @{Name = "Used Percentage"; Expression = {($_.CurrentValue / $_.Limit) * 100}}, @{Name = "Remaining"; Expression = {$_.Limit - $_.CurrentValue}}, @{Name = "Location"; Expression = {"westus"}}
$examplenetworks = Get-AzNetworkUsage -Location $location | Select-Object @{Name = "Name"; Expression = {$_.ResourceType}}, CurrentValue, Limit, @{Name = "Used Percentage"; Expression = {($_.CurrentValue / $_.Limit) * 100}}, @{Name = "Remaining"; Expression = {$_.Limit - $_.CurrentValue}}, @{Name = "Location"; Expression = {"westus"}}
$exampleVmsNtks = $exampleVms + $examplenetworks

# Export resource usage for VMs and networks to CSV
$exampleVmsNtks | Export-Csv -Path "C:\users\$env:username\desktop\example_Resource_VMs_Ntks.csv" -NoTypeInformation

# Send email with attached CSV files
$senderEmail = "example@example.org"
$recipientEmails = "examplesupport@example.org"

$subject = "Example Azure Resource Usage Data"
$body = @"
To Example Support Team,

Here are the attached CSV files with the Azure resource usage data.

Regards,
Your Name
"@

$smtpServer = "smtp.example.org"
$mailParams = @{
    From       = $senderEmail
    To         = $recipientEmails
    Subject    = $subject
    Body       = $body
    SmtpServer = $smtpServer
}

$attachments = @(
    "C:\users\$env:username\desktop\example_QuotaUsage_VMs.csv",
    "C:\users\$env:username\desktop\example_Data_VMs.csv",
    "C:\users\$env:username\desktop\example_Status_VMs.csv",
    "C:\users\$env:username\desktop\example_CreationDate_VMs.csv",
    "C:\users\$env:username\desktop\example_Resource_VMs_Ntks.csv",
    "C:\users\$env:username\desktop\example_VMs_Count.csv"
)

$mailParams["Attachments"] = $attachments

Send-MailMessage @mailParams
