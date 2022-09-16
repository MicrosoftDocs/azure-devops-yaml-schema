---
title: SqlAzureDacpacDeployment@1 - Azure SQL Database deployment v1 task
description: Deploy an Azure SQL Database using DACPAC or run scripts using SQLCMD.
ms.date: 09/01/2022
monikerRange: "<=azure-pipelines"
---

# SqlAzureDacpacDeployment@1 - Azure SQL Database deployment v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Deploy an Azure SQL Database using DACPAC or run scripts using SQLCMD.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Deploy Azure SQL DB using DACPAC or run scripts using SQLCMD.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020.1"

```yaml
# Azure SQL Database deployment v1
# Deploy an Azure SQL Database using DACPAC or run scripts using SQLCMD.
- task: SqlAzureDacpacDeployment@1
  inputs:
    #azureConnectionType: 'ConnectedServiceNameARM' # 'ConnectedServiceName' | 'ConnectedServiceNameARM'. Azure Service Connection Type. Default: 'ConnectedServiceNameARM'.
    #azureClassicSubscription: # string. Required when ConnectedServiceNameSelector = ConnectedServiceName. Azure Classic Subscription. 
    azureSubscription: # string. Required when ConnectedServiceNameSelector = ConnectedServiceNameARM. Azure Subscription. 
  # SQL Database
    AuthenticationType: 'server' # 'server' | 'aadAuthenticationPassword' | 'aadAuthenticationIntegrated' | 'connectionString' | 'servicePrincipal'. Required. Authentication Type. Default: 'server'.
    #ServerName: # string. Required when AuthenticationType = server || AuthenticationType = aadAuthenticationPassword || AuthenticationType = aadAuthenticationIntegrated || AuthenticationType = servicePrincipal. Azure SQL Server. 
    #DatabaseName: # string. Required when AuthenticationType = server || AuthenticationType = aadAuthenticationPassword || AuthenticationType = aadAuthenticationIntegrated || AuthenticationType = servicePrincipal. Database. 
    SqlUsername: # string. Required when AuthenticationType = server. Login. 
    SqlPassword: # string. Required when AuthenticationType = server. Password. 
    #aadSqlUsername: # string. Required when AuthenticationType = aadAuthenticationPassword. Login. 
    #aadSqlPassword: # string. Required when AuthenticationType = aadAuthenticationPassword. Password. 
    #ConnectionString: # string. Required when AuthenticationType = connectionString. Connection String. 
  # Deployment Package
    deployType: 'DacpacTask' # 'DacpacTask' | 'SqlTask' | 'InlineSqlTask'. Required. Deploy type. Default: 'DacpacTask'.
    DeploymentAction: 'Publish' # 'Publish' | 'Extract' | 'Export' | 'Import' | 'Script' | 'DriftReport' | 'DeployReport'. Required when TaskNameSelector = DacpacTask. Action. Default: 'Publish'.
    #DacpacFile: # string. Required when DeploymentAction = Publish || DeploymentAction = Script || DeploymentAction = DeployReport. DACPAC File. 
    #BacpacFile: # string. Required when DeploymentAction = Import. BACPAC File. 
    #SqlFile: # string. Required when TaskNameSelector = SqlTask. SQL Script. 
    #SqlInline: # string. Required when TaskNameSelector = InlineSqlTask. Inline SQL Script. 
    #PublishProfile: # string. Optional. Use when TaskNameSelector = DacpacTask || DeploymentAction = Script || DeploymentAction = DeployReport. Publish Profile. 
    #AdditionalArguments: # string. Optional. Use when TaskNameSelector = DacpacTask || DeploymentAction = Extract || DeploymentAction = Export || DeploymentAction = Import || DeploymentAction = Script || DeploymentAction = DeployReport || DeploymentAction = DriftReport. Additional SqlPackage.exe Arguments. 
    #SqlAdditionalArguments: # string. Optional. Use when TaskNameSelector = SqlTask. Additional Invoke-Sqlcmd Arguments. 
    #InlineAdditionalArguments: # string. Optional. Use when TaskNameSelector = InlineSqlTask. Additional Invoke-Sqlcmd Arguments. 
  # Firewall
    IpDetectionMethod: 'AutoDetect' # 'AutoDetect' | 'IPAddressRange'. Required. Specify Firewall Rules Using. Default: 'AutoDetect'.
    #StartIpAddress: # string. Required when IpDetectionMethod = IPAddressRange. Start IP Address. 
    #EndIpAddress: # string. Required when IpDetectionMethod = IPAddressRange. End IP Address. 
    #DeleteFirewallRule: true # boolean. Delete Rule After Task Ends. Default: true.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2019.1 <=azure-pipelines-2020"

```yaml
# Azure SQL Database deployment v1
# Deploy an Azure SQL Database using DACPAC or run scripts using SQLCMD.
- task: SqlAzureDacpacDeployment@1
  inputs:
    #azureConnectionType: 'ConnectedServiceNameARM' # 'ConnectedServiceName' | 'ConnectedServiceNameARM'. Azure Service Connection Type. Default: 'ConnectedServiceNameARM'.
    #azureClassicSubscription: # string. Required when ConnectedServiceNameSelector = ConnectedServiceName. Azure Classic Subscription. 
    azureSubscription: # string. Required when ConnectedServiceNameSelector = ConnectedServiceNameARM. Azure Subscription. 
  # SQL Database
    AuthenticationType: 'server' # 'server' | 'aadAuthenticationPassword' | 'aadAuthenticationIntegrated' | 'connectionString'. Required. Authentication Type. Default: 'server'.
    #ServerName: # string. Required when AuthenticationType = server || AuthenticationType = aadAuthenticationPassword || AuthenticationType = aadAuthenticationIntegrated. Azure SQL Server. 
    #DatabaseName: # string. Required when AuthenticationType = server || AuthenticationType = aadAuthenticationPassword || AuthenticationType = aadAuthenticationIntegrated. Database. 
    SqlUsername: # string. Required when AuthenticationType = server. Login. 
    SqlPassword: # string. Required when AuthenticationType = server. Password. 
    #aadSqlUsername: # string. Required when AuthenticationType = aadAuthenticationPassword. Login. 
    #aadSqlPassword: # string. Required when AuthenticationType = aadAuthenticationPassword. Password. 
    #ConnectionString: # string. Required when AuthenticationType = connectionString. Connection String. 
  # Deployment Package
    deployType: 'DacpacTask' # 'DacpacTask' | 'SqlTask' | 'InlineSqlTask'. Required. Deploy type. Default: 'DacpacTask'.
    DeploymentAction: 'Publish' # 'Publish' | 'Extract' | 'Export' | 'Import' | 'Script' | 'DriftReport' | 'DeployReport'. Required when TaskNameSelector = DacpacTask. Action. Default: 'Publish'.
    #DacpacFile: # string. Required when DeploymentAction = Publish || DeploymentAction = Script || DeploymentAction = DeployReport. DACPAC File. 
    #BacpacFile: # string. Required when DeploymentAction = Import. BACPAC File. 
    #SqlFile: # string. Required when TaskNameSelector = SqlTask. SQL Script. 
    #SqlInline: # string. Required when TaskNameSelector = InlineSqlTask. Inline SQL Script. 
    #PublishProfile: # string. Optional. Use when TaskNameSelector = DacpacTask || DeploymentAction = Script || DeploymentAction = DeployReport. Publish Profile. 
    #AdditionalArguments: # string. Optional. Use when TaskNameSelector = DacpacTask || DeploymentAction = Extract || DeploymentAction = Export || DeploymentAction = Import || DeploymentAction = Script || DeploymentAction = DeployReport || DeploymentAction = DriftReport. Additional SqlPackage.exe Arguments. 
    #SqlAdditionalArguments: # string. Optional. Use when TaskNameSelector = SqlTask. Additional Invoke-Sqlcmd Arguments. 
    #InlineAdditionalArguments: # string. Optional. Use when TaskNameSelector = InlineSqlTask. Additional Invoke-Sqlcmd Arguments. 
  # Firewall
    IpDetectionMethod: 'AutoDetect' # 'AutoDetect' | 'IPAddressRange'. Required. Specify Firewall Rules Using. Default: 'AutoDetect'.
    #StartIpAddress: # string. Required when IpDetectionMethod = IPAddressRange. Start IP Address. 
    #EndIpAddress: # string. Required when IpDetectionMethod = IPAddressRange. End IP Address. 
    #DeleteFirewallRule: true # boolean. Delete Rule After Task Ends. Default: true.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Azure SQL Database Deployment v1
# Deploy Azure SQL DB using DACPAC or run scripts using SQLCMD.
- task: SqlAzureDacpacDeployment@1
  inputs:
    #azureConnectionType: 'ConnectedServiceNameARM' # 'ConnectedServiceName' | 'ConnectedServiceNameARM'. Azure Service Connection Type. Default: 'ConnectedServiceNameARM'.
    #azureClassicSubscription: # string. Required when ConnectedServiceNameSelector = ConnectedServiceName. Azure Classic Subscription. 
    azureSubscription: # string. Required when ConnectedServiceNameSelector = ConnectedServiceNameARM. Azure Subscription. 
  # SQL DB Details
    ServerName: # string. Required. Azure SQL Server Name. 
    DatabaseName: # string. Required. Database Name. 
    SqlUsername: # string. Required. Server Admin Login. 
    SqlPassword: # string. Required. Password. 
  # Deployment Package
    DeploymentAction: 'Publish' # 'Publish' | 'Extract' | 'Export' | 'Import' | 'Script' | 'DriftReport' | 'DeployReport'. Required. Action. Default: 'Publish'.
    #TaskNameSelector: 'DacpacTask' # 'DacpacTask' | 'SqlTask' | 'InlineSqlTask'. Optional. Use when DeploymentAction = Publish. Type. Default: 'DacpacTask'.
    #DacpacFile: # string. Required when TaskNameSelector = DacpacTask || DeploymentAction = Script || DeploymentAction = DeployReport. DACPAC File. 
    #BacpacFile: # string. Required when DeploymentAction = Import. BACPAC File. 
    #SqlFile: # string. Required when TaskNameSelector = SqlTask. SQL Script. 
    #SqlInline: # string. Required when TaskNameSelector = InlineSqlTask. Inline SQL Script. 
    #PublishProfile: # string. Optional. Use when TaskNameSelector = DacpacTask || DeploymentAction = Script || DeploymentAction = DeployReport. Publish Profile. 
    #AdditionalArguments: # string. Optional. Use when TaskNameSelector = DacpacTask || DeploymentAction = Extract || DeploymentAction = Export || DeploymentAction = Import || DeploymentAction = Script || DeploymentAction = DeployReport || DeploymentAction = DriftReport. Additional SqlPackage.exe Arguments. 
    #SqlAdditionalArguments: # string. Optional. Use when TaskNameSelector = SqlTask. Additional Invoke-Sqlcmd Arguments. 
    #InlineAdditionalArguments: # string. Optional. Use when TaskNameSelector = InlineSqlTask. Additional Invoke-Sqlcmd Arguments. 
  # Firewall
    IpDetectionMethod: 'AutoDetect' # 'AutoDetect' | 'IPAddressRange'. Required. Specify Firewall Rules Using. Default: 'AutoDetect'.
    #StartIpAddress: # string. Required when IpDetectionMethod = IPAddressRange. Start IP Address. 
    #EndIpAddress: # string. Required when IpDetectionMethod = IPAddressRange. End IP Address. 
    #DeleteFirewallRule: true # boolean. Delete Rule After Task Ends. Default: true.
```

:::moniker-end

:::moniker range="=azure-pipelines-2018"

```yaml
# YAML Syntax is not supported in TFS 2018.
# Use the classic designer to add and configure tasks.
# See the following Inputs section for details on the inputs that this task supports.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="azureConnectionType"::: -->
:::moniker range=">=azure-pipelines-2019"

**`azureConnectionType`** - **Azure Service Connection Type**<br>
Input alias: `ConnectedServiceNameSelector`. Type: string. Allowed values: 'ConnectedServiceName', 'ConnectedServiceNameARM'. Default value: 'ConnectedServiceNameARM'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`azureConnectionType`** - **Azure Connection Type**<br>
Input alias: `ConnectedServiceNameSelector`. Type: string. Allowed values: 'ConnectedServiceName', 'ConnectedServiceNameARM'. Default value: 'ConnectedServiceNameARM'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureClassicSubscription"::: -->
:::moniker range="<=azure-pipelines"

**`azureClassicSubscription`** - **Azure Classic Subscription**<br>
Input alias: `ConnectedServiceName`. Type: string. Required when ConnectedServiceNameSelector = ConnectedServiceName.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Target Azure Classic subscription for deploying SQL files.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureSubscription"::: -->
:::moniker range="<=azure-pipelines"

**`azureSubscription`** - **Azure Subscription**<br>
Input alias: `ConnectedServiceNameARM`. Type: string. Required when ConnectedServiceNameSelector = ConnectedServiceNameARM.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Target Azure Resource Manager subscription for deploying SQL files.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AuthenticationType"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`AuthenticationType`** - **Authentication Type**<br>
Type: string. Required. Allowed values: 'server', 'aadAuthenticationPassword', 'aadAuthenticationIntegrated', 'connectionString', 'servicePrincipal'. Default value: 'server'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Type of database authentication, can be SQL Server Authentication, Active Directory - Integrated, Active Directory - Password, Connection String, or Service Principal. Integrated authentication means that the agent will access the database using its current Active Directory account context.
Specify the option to connect to the Azure SQL Server Database. The options are either to provide the Azure SQL Server Database details, or the SQL Server connection string, or AAD Authentication password or integrated or use a Service Principal. For SQL server authentication, use SQL server's user credentials and for AD authentication, use credentials of AD user configured to SQL server.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range=">=azure-pipelines-2019.1 <=azure-pipelines-2020"

**`AuthenticationType`** - **Authentication Type**<br>
Type: string. Required. Allowed values: 'server', 'aadAuthenticationPassword', 'aadAuthenticationIntegrated', 'connectionString'. Default value: 'server'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Type of database authentication, can be SQL Server Authentication, Active Directory - Integrated, Active Directory - Password, Connection String, or Service Principal. Integrated authentication means that the agent will access the database using its current Active Directory account context.
Specify the option to connect to the Azure SQL Server Database. The options are either to provide the Azure SQL Server Database details, or the SQL Server connection string, or AAD Authentication password or integrated. For SQL server authentication, use SQL server's user credentials and for AD authentication, use credentials of AD user configured to SQL server.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ServerName"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`ServerName`** - **Azure SQL Server**<br>
Type: string. Required when AuthenticationType = server || AuthenticationType = aadAuthenticationPassword || AuthenticationType = aadAuthenticationIntegrated || AuthenticationType = servicePrincipal.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Azure SQL Server name, like Fabrikam.database.windows.net,1433 or Fabrikam.database.windows.net.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range=">=azure-pipelines-2019.1 <=azure-pipelines-2020"

**`ServerName`** - **Azure SQL Server**<br>
Type: string. Required when AuthenticationType = server || AuthenticationType = aadAuthenticationPassword || AuthenticationType = aadAuthenticationIntegrated.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Azure SQL Server name, like Fabrikam.database.windows.net,1433 or Fabrikam.database.windows.net.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2019"

**`ServerName`** - **Azure SQL Server Name**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Azure SQL Server name, like Fabrikam.database.windows.net,1433 or Fabrikam.database.windows.net.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DatabaseName"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`DatabaseName`** - **Database**<br>
Type: string. Required when AuthenticationType = server || AuthenticationType = aadAuthenticationPassword || AuthenticationType = aadAuthenticationIntegrated || AuthenticationType = servicePrincipal.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Name of the Azure SQL Database, where the files will be deployed.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range=">=azure-pipelines-2019.1 <=azure-pipelines-2020"

**`DatabaseName`** - **Database**<br>
Type: string. Required when AuthenticationType = server || AuthenticationType = aadAuthenticationPassword || AuthenticationType = aadAuthenticationIntegrated.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Name of the Azure SQL Database, where the files will be deployed.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2019"

**`DatabaseName`** - **Database Name**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Name of the Azure SQL Database, where the files will be deployed.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SqlUsername"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`SqlUsername`** - **Login**<br>
Type: string. Required when AuthenticationType = server.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the Azure SQL Server administrator login.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019"

**`SqlUsername`** - **Server Admin Login**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the Azure SQL Server administrator login or Active Directory user name.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`SqlUsername`** - **Server Admin Login**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the Azure SQL Server administrator login or Active Directory user name.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SqlPassword"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`SqlPassword`** - **Password**<br>
Type: string. Required when AuthenticationType = server.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Password for the Azure SQL Server administrator.<br>It can accept variable defined in build or release pipelines as '$(passwordVariable)'.<br>You may mark the variable type as 'secret' to secure it.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019"

**`SqlPassword`** - **Password**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Password for the Azure SQL Server administrator.<br>It can accept variable defined in build or release pipelines as '$(passwordVariable)'.<br>You may mark the variable type as 'secret' to secure it.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`SqlPassword`** - **Password**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Password for the Azure SQL Server administrator.<br>It can accept variable defined in Build/Release Definitions as '$(passwordVariable)'.<br>You may mark the variable type as 'secret' to secure it.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="aadSqlUsername"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`aadSqlUsername`** - **Login**<br>
Type: string. Required when AuthenticationType = aadAuthenticationPassword.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the Active directory username.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="aadSqlPassword"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`aadSqlPassword`** - **Password**<br>
Type: string. Required when AuthenticationType = aadAuthenticationPassword.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Password for the Active directory user.<br>It can accept variable defined in build or release pipelines as '$(passwordVariable)'.<br>You may mark the variable type as 'secret' to secure it.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ConnectionString"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`ConnectionString`** - **Connection String**<br>
Type: string. Required when AuthenticationType = connectionString.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the Azure SQL Server connection string like "Server=testServer.database.windows.net;Database=testdb;User ID=AccountPlaceholder;Password=$(securePassword);".
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deployType"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`deployType`** - **Deploy type**<br>
Input alias: `TaskNameSelector`. Type: string. Required. Allowed values: 'DacpacTask', 'SqlTask', 'InlineSqlTask'. Default value: 'DacpacTask'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DeploymentAction"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`DeploymentAction`** - **Action**<br>
Type: string. Required when TaskNameSelector = DacpacTask. Allowed values: 'Publish', 'Extract', 'Export', 'Import', 'Script', 'DriftReport', 'DeployReport'. Default value: 'Publish'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Choose one of the SQL Actions from the list. For more details refer <a href="https://go.microsoft.com/fwlink/?linkid=875177">link</a>.​.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019"

**`DeploymentAction`** - **Action**<br>
Type: string. Required. Allowed values: 'Publish', 'Extract', 'Export', 'Import', 'Script', 'DriftReport', 'DeployReport'. Default value: 'Publish'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Choose one of the SQL Actions from the list. For more details refer <a href="https://go.microsoft.com/fwlink/?linkid=875177">link</a>.​.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DacpacFile"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`DacpacFile`** - **DACPAC File**<br>
Type: string. Required when DeploymentAction = Publish || DeploymentAction = Script || DeploymentAction = DeployReport.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Location of the DACPAC file on the automation agent or on a UNC path accessible to the automation agent like, \\\\BudgetIT\Web\Deploy\FabrikamDB.dacpac. Predefined system variables like, $(agent.releaseDirectory) can also be used here.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019"

**`DacpacFile`** - **DACPAC File**<br>
Type: string. Required when TaskNameSelector = DacpacTask || DeploymentAction = Script || DeploymentAction = DeployReport.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Location of the DACPAC file on the automation agent or on a UNC path accessible to the automation agent like, \\\\BudgetIT\Web\Deploy\FabrikamDB.dacpac. Predefined system variables like, $(agent.releaseDirectory) can also be used here.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`DacpacFile`** - **DACPAC File**<br>
Type: string. Required when TaskNameSelector = DacpacTask.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Location of the DACPAC file on the automation agent or on a UNC path accessible to the automation agent like, \\\\BudgetIT\Web\Deploy\FabrikamDB.dacpac. Predefined system variables like, $(agent.releaseDirectory) can also be used here.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="BacpacFile"::: -->
:::moniker range=">=azure-pipelines-2019"

**`BacpacFile`** - **BACPAC File**<br>
Type: string. Required when DeploymentAction = Import.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Location of the BACPAC file on the automation agent or on a UNC path accessible to the automation agent like, \\\\BudgetIT\Web\Deploy\FabrikamDB.bacpac. Predefined system variables like, $(agent.releaseDirectory) can also be used here.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SqlFile"::: -->
:::moniker range="<=azure-pipelines"

**`SqlFile`** - **SQL Script**<br>
Type: string. Required when TaskNameSelector = SqlTask.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Location of the SQL script file on the automation agent or on a UNC path accessible to the automation agent like, \\\\BudgetIT\Web\Deploy\FabrikamDB.sql. Predefined system variables like, $(agent.releaseDirectory) can also be used here.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SqlInline"::: -->
:::moniker range="<=azure-pipelines"

**`SqlInline`** - **Inline SQL Script**<br>
Type: string. Required when TaskNameSelector = InlineSqlTask.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter the SQL script to execute on the Database selected above.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="PublishProfile"::: -->
:::moniker range=">=azure-pipelines-2019"

**`PublishProfile`** - **Publish Profile**<br>
Type: string. Optional. Use when TaskNameSelector = DacpacTask || DeploymentAction = Script || DeploymentAction = DeployReport.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Publish profile provides fine-grained control over Azure SQL Database creation or upgrades. Specify the path to the Publish profile XML file on the automation agent machine or on a UNC share. If the publish profile contains secrets like credentials, upload it to the [secure files](/azure/devops/pipelines/library/secure-files) library where it is securely stored with encryption. Then use the [Download secure file](download-secure-file-v1.md) task at the start of your pipeline to download it to the agent machine when the pipeline runs and delete it when the pipeline is complete. Predefined system variables like, $(agent.buildDirectory) or $(agent.releaseDirectory) can also be used here.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`PublishProfile`** - **Publish Profile**<br>
Type: string. Optional. Use when TaskNameSelector = DacpacTask.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Publish profile provides fine-grained control over Azure SQL Database creation or upgrades. Specify the path to the Publish profile XML file on the automation agent or on a UNC share. If the publish profile contains secrets like credentials, upload it to the [secure files](/azure/devops/pipelines/library/secure-files) library where it is securely stored with encryption. Then use the [Download secure file](download-secure-file-v1.md) task at the start of your pipeline to download it to the agent machine when the pipeline runs and delete it when the pipeline is complete. Predefined system variables like, $(agent.buildDirectory) or $(agent.releaseDirectory) can also be used here.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AdditionalArguments"::: -->
:::moniker range=">=azure-pipelines-2019"

**`AdditionalArguments`** - **Additional SqlPackage.exe Arguments**<br>
Type: string. Optional. Use when TaskNameSelector = DacpacTask || DeploymentAction = Extract || DeploymentAction = Export || DeploymentAction = Import || DeploymentAction = Script || DeploymentAction = DeployReport || DeploymentAction = DriftReport.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Additional SqlPackage.exe arguments that will be applied when deploying the Azure SQL Database, in case DACPAC option is selected like, `/p:IgnoreAnsiNulls=True /p:IgnoreComments=True`. These arguments will override the settings in the Publish profile XML file (if provided).
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`AdditionalArguments`** - **Additional SqlPackage.exe Arguments**<br>
Type: string. Optional. Use when TaskNameSelector = DacpacTask.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Additional SqlPackage.exe arguments that will be applied when deploying the Azure SQL Database, in case DACPAC option is selected like, `/p:IgnoreAnsiNulls=True /p:IgnoreComments=True`. These arguments will override the settings in the Publish profile XML file (if provided).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SqlAdditionalArguments"::: -->
:::moniker range="<=azure-pipelines"

**`SqlAdditionalArguments`** - **Additional Invoke-Sqlcmd Arguments**<br>
Type: string. Optional. Use when TaskNameSelector = SqlTask.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Additional Invoke-Sqlcmd arguments that will be applied when executing the given SQL query on the Azure SQL Database like, `-ConnectionTimeout 100 -OutputSqlErrors`.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="InlineAdditionalArguments"::: -->
:::moniker range="<=azure-pipelines"

**`InlineAdditionalArguments`** - **Additional Invoke-Sqlcmd Arguments**<br>
Type: string. Optional. Use when TaskNameSelector = InlineSqlTask.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Additional Invoke-Sqlcmd arguments that will be applied when executing the given SQL query on the Azure SQL Database like, `-ConnectionTimeout 100 -OutputSqlErrors`.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="IpDetectionMethod"::: -->
:::moniker range="<=azure-pipelines"

**`IpDetectionMethod`** - **Specify Firewall Rules Using**<br>
Type: string. Required. Allowed values: 'AutoDetect', 'IPAddressRange'. Default value: 'AutoDetect'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
For the task to run, the IP Address of the automation agent has to be added to the 'Allowed IP Addresses' in the Azure SQL Server's Firewall. Select auto-detect to automatically add firewall exception for range of possible IP Address of automation agent or specify the range explicitly.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="StartIpAddress"::: -->
:::moniker range="<=azure-pipelines"

**`StartIpAddress`** - **Start IP Address**<br>
Type: string. Required when IpDetectionMethod = IPAddressRange.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The starting IP Address of the automation agent machine pool like 196.21.30.50.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="EndIpAddress"::: -->
:::moniker range="<=azure-pipelines"

**`EndIpAddress`** - **End IP Address**<br>
Type: string. Required when IpDetectionMethod = IPAddressRange.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The ending IP Address of the automation agent machine pool like 196.21.30.65.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DeleteFirewallRule"::: -->
:::moniker range="<=azure-pipelines"

**`DeleteFirewallRule`** - **Delete Rule After Task Ends**<br>
Type: boolean. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If selected, then after the task ends, the IP Addresses specified here are deleted from the 'Allowed IP Addresses' list of the Azure SQL Server's Firewall.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="TaskNameSelector"::: -->
:::moniker range="=azure-pipelines-2019"

**`TaskNameSelector`** - **Type**<br>
Type: string. Optional. Use when DeploymentAction = Publish. Allowed values: 'DacpacTask', 'SqlTask', 'InlineSqlTask'. Default value: 'DacpacTask'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`TaskNameSelector`** - **Type**<br>
Type: string. Allowed values: 'DacpacTask', 'SqlTask', 'InlineSqlTask'. Default value: 'DacpacTask'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2019"

This task defines the following [output variables](/azure/devops/pipelines/process/variables#use-output-variables-from-tasks), which you can consume in downstream steps, jobs, and stages.

<!-- :::item name="SqlDeploymentOutputFile"::: -->
**`SqlDeploymentOutputFile`**<br><!-- :::editable-content name="Value"::: -->
Generated output file path when deployment package action is either of Extract, Export, Script, Drift Report, Deploy Report.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2018"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range="<=azure-pipelines"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent |
| [Demands](/azure/devops/pipelines/process/demands) | Self-hosted agents must have [capabilities](/azure/devops/pipelines/agents/agents#capabilities) that match the following [demands](/azure/devops/pipelines/process/demands) to run jobs that use this task: sqlpackage |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.103.0 or greater |
| Task category | Deploy |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->