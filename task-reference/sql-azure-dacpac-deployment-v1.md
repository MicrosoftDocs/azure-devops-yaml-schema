---
title: SqlAzureDacpacDeployment@1 - Azure SQL Database deployment v1 task
description: Deploy an Azure SQL Database using DACPAC or run scripts using SQLCMD.
ms.date: 11/30/2023
monikerRange: "<=azure-pipelines"
---

# SqlAzureDacpacDeployment@1 - Azure SQL Database deployment v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Use this task to deploy an Azure SQL Database using DACPAC, or run scripts using SQLCMD.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Use this task to deploy an Azure SQL database using DACPAC, or run scripts using SQLCMD.
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
    #azureConnectionType: 'ConnectedServiceNameARM' # 'ConnectedServiceName' | 'ConnectedServiceNameARM'. Alias: ConnectedServiceNameSelector. Azure Service Connection Type. Default: ConnectedServiceNameARM.
    #azureClassicSubscription: # string. Alias: ConnectedServiceName. Required when ConnectedServiceNameSelector = ConnectedServiceName. Azure Classic Subscription. 
    azureSubscription: # string. Alias: ConnectedServiceNameARM. Required when ConnectedServiceNameSelector = ConnectedServiceNameARM. Azure Subscription. 
  # SQL Database
    AuthenticationType: 'server' # 'server' | 'aadAuthenticationPassword' | 'aadAuthenticationIntegrated' | 'connectionString' | 'servicePrincipal'. Required. Authentication Type. Default: server.
    #ServerName: # string. Required when AuthenticationType = server || AuthenticationType = aadAuthenticationPassword || AuthenticationType = aadAuthenticationIntegrated || AuthenticationType = servicePrincipal. Azure SQL Server. 
    #DatabaseName: # string. Required when AuthenticationType = server || AuthenticationType = aadAuthenticationPassword || AuthenticationType = aadAuthenticationIntegrated || AuthenticationType = servicePrincipal. Database. 
    SqlUsername: # string. Required when AuthenticationType = server. Login. 
    SqlPassword: # string. Required when AuthenticationType = server. Password. 
    #aadSqlUsername: # string. Required when AuthenticationType = aadAuthenticationPassword. Login. 
    #aadSqlPassword: # string. Required when AuthenticationType = aadAuthenticationPassword. Password. 
    #ConnectionString: # string. Required when AuthenticationType = connectionString. Connection String. 
  # Deployment Package
    deployType: 'DacpacTask' # 'DacpacTask' | 'SqlTask' | 'InlineSqlTask'. Alias: TaskNameSelector. Required. Deploy type. Default: DacpacTask.
    DeploymentAction: 'Publish' # 'Publish' | 'Extract' | 'Export' | 'Import' | 'Script' | 'DriftReport' | 'DeployReport'. Required when TaskNameSelector = DacpacTask. Action. Default: Publish.
    #DacpacFile: # string. Required when DeploymentAction = Publish || DeploymentAction = Script || DeploymentAction = DeployReport. DACPAC File. 
    #BacpacFile: # string. Required when DeploymentAction = Import. BACPAC File. 
    #SqlFile: # string. Required when TaskNameSelector = SqlTask. SQL Script. 
    #SqlInline: # string. Required when TaskNameSelector = InlineSqlTask. Inline SQL Script. 
    #PublishProfile: # string. Optional. Use when TaskNameSelector = DacpacTask || DeploymentAction = Script || DeploymentAction = DeployReport. Publish Profile. 
    #AdditionalArguments: # string. Optional. Use when TaskNameSelector = DacpacTask || DeploymentAction = Extract || DeploymentAction = Export || DeploymentAction = Import || DeploymentAction = Script || DeploymentAction = DeployReport || DeploymentAction = DriftReport. Additional SqlPackage.exe Arguments. 
    #SqlAdditionalArguments: # string. Optional. Use when TaskNameSelector = SqlTask. Additional Invoke-Sqlcmd Arguments. 
    #InlineAdditionalArguments: # string. Optional. Use when TaskNameSelector = InlineSqlTask. Additional Invoke-Sqlcmd Arguments. 
  # Firewall
    IpDetectionMethod: 'AutoDetect' # 'AutoDetect' | 'IPAddressRange'. Required. Specify Firewall Rules Using. Default: AutoDetect.
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
    #azureConnectionType: 'ConnectedServiceNameARM' # 'ConnectedServiceName' | 'ConnectedServiceNameARM'. Alias: ConnectedServiceNameSelector. Azure Service Connection Type. Default: ConnectedServiceNameARM.
    #azureClassicSubscription: # string. Alias: ConnectedServiceName. Required when ConnectedServiceNameSelector = ConnectedServiceName. Azure Classic Subscription. 
    azureSubscription: # string. Alias: ConnectedServiceNameARM. Required when ConnectedServiceNameSelector = ConnectedServiceNameARM. Azure Subscription. 
  # SQL Database
    AuthenticationType: 'server' # 'server' | 'aadAuthenticationPassword' | 'aadAuthenticationIntegrated' | 'connectionString'. Required. Authentication Type. Default: server.
    #ServerName: # string. Required when AuthenticationType = server || AuthenticationType = aadAuthenticationPassword || AuthenticationType = aadAuthenticationIntegrated. Azure SQL Server. 
    #DatabaseName: # string. Required when AuthenticationType = server || AuthenticationType = aadAuthenticationPassword || AuthenticationType = aadAuthenticationIntegrated. Database. 
    SqlUsername: # string. Required when AuthenticationType = server. Login. 
    SqlPassword: # string. Required when AuthenticationType = server. Password. 
    #aadSqlUsername: # string. Required when AuthenticationType = aadAuthenticationPassword. Login. 
    #aadSqlPassword: # string. Required when AuthenticationType = aadAuthenticationPassword. Password. 
    #ConnectionString: # string. Required when AuthenticationType = connectionString. Connection String. 
  # Deployment Package
    deployType: 'DacpacTask' # 'DacpacTask' | 'SqlTask' | 'InlineSqlTask'. Alias: TaskNameSelector. Required. Deploy type. Default: DacpacTask.
    DeploymentAction: 'Publish' # 'Publish' | 'Extract' | 'Export' | 'Import' | 'Script' | 'DriftReport' | 'DeployReport'. Required when TaskNameSelector = DacpacTask. Action. Default: Publish.
    #DacpacFile: # string. Required when DeploymentAction = Publish || DeploymentAction = Script || DeploymentAction = DeployReport. DACPAC File. 
    #BacpacFile: # string. Required when DeploymentAction = Import. BACPAC File. 
    #SqlFile: # string. Required when TaskNameSelector = SqlTask. SQL Script. 
    #SqlInline: # string. Required when TaskNameSelector = InlineSqlTask. Inline SQL Script. 
    #PublishProfile: # string. Optional. Use when TaskNameSelector = DacpacTask || DeploymentAction = Script || DeploymentAction = DeployReport. Publish Profile. 
    #AdditionalArguments: # string. Optional. Use when TaskNameSelector = DacpacTask || DeploymentAction = Extract || DeploymentAction = Export || DeploymentAction = Import || DeploymentAction = Script || DeploymentAction = DeployReport || DeploymentAction = DriftReport. Additional SqlPackage.exe Arguments. 
    #SqlAdditionalArguments: # string. Optional. Use when TaskNameSelector = SqlTask. Additional Invoke-Sqlcmd Arguments. 
    #InlineAdditionalArguments: # string. Optional. Use when TaskNameSelector = InlineSqlTask. Additional Invoke-Sqlcmd Arguments. 
  # Firewall
    IpDetectionMethod: 'AutoDetect' # 'AutoDetect' | 'IPAddressRange'. Required. Specify Firewall Rules Using. Default: AutoDetect.
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
    #azureConnectionType: 'ConnectedServiceNameARM' # 'ConnectedServiceName' | 'ConnectedServiceNameARM'. Alias: ConnectedServiceNameSelector. Azure Service Connection Type. Default: ConnectedServiceNameARM.
    #azureClassicSubscription: # string. Alias: ConnectedServiceName. Required when ConnectedServiceNameSelector = ConnectedServiceName. Azure Classic Subscription. 
    azureSubscription: # string. Alias: ConnectedServiceNameARM. Required when ConnectedServiceNameSelector = ConnectedServiceNameARM. Azure Subscription. 
  # SQL DB Details
    ServerName: # string. Required. Azure SQL Server Name. 
    DatabaseName: # string. Required. Database Name. 
    SqlUsername: # string. Required. Server Admin Login. 
    SqlPassword: # string. Required. Password. 
  # Deployment Package
    DeploymentAction: 'Publish' # 'Publish' | 'Extract' | 'Export' | 'Import' | 'Script' | 'DriftReport' | 'DeployReport'. Required. Action. Default: Publish.
    #TaskNameSelector: 'DacpacTask' # 'DacpacTask' | 'SqlTask' | 'InlineSqlTask'. Optional. Use when DeploymentAction = Publish. Type. Default: DacpacTask.
    #DacpacFile: # string. Required when TaskNameSelector = DacpacTask || DeploymentAction = Script || DeploymentAction = DeployReport. DACPAC File. 
    #BacpacFile: # string. Required when DeploymentAction = Import. BACPAC File. 
    #SqlFile: # string. Required when TaskNameSelector = SqlTask. SQL Script. 
    #SqlInline: # string. Required when TaskNameSelector = InlineSqlTask. Inline SQL Script. 
    #PublishProfile: # string. Optional. Use when TaskNameSelector = DacpacTask || DeploymentAction = Script || DeploymentAction = DeployReport. Publish Profile. 
    #AdditionalArguments: # string. Optional. Use when TaskNameSelector = DacpacTask || DeploymentAction = Extract || DeploymentAction = Export || DeploymentAction = Import || DeploymentAction = Script || DeploymentAction = DeployReport || DeploymentAction = DriftReport. Additional SqlPackage.exe Arguments. 
    #SqlAdditionalArguments: # string. Optional. Use when TaskNameSelector = SqlTask. Additional Invoke-Sqlcmd Arguments. 
    #InlineAdditionalArguments: # string. Optional. Use when TaskNameSelector = InlineSqlTask. Additional Invoke-Sqlcmd Arguments. 
  # Firewall
    IpDetectionMethod: 'AutoDetect' # 'AutoDetect' | 'IPAddressRange'. Required. Specify Firewall Rules Using. Default: AutoDetect.
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
Input alias: `ConnectedServiceNameSelector`. `string`. Allowed values: `ConnectedServiceName` (Azure Classic), `ConnectedServiceNameARM` (Azure Resource Manager). Default value: `ConnectedServiceNameARM`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`azureConnectionType`** - **Azure Connection Type**<br>
Input alias: `ConnectedServiceNameSelector`. `string`. Allowed values: `ConnectedServiceName` (Azure Classic), `ConnectedServiceNameARM` (Azure Resource Manager). Default value: `ConnectedServiceNameARM`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureClassicSubscription"::: -->
:::moniker range="<=azure-pipelines"

**`azureClassicSubscription`** - **Azure Classic Subscription**<br>
Input alias: `ConnectedServiceName`. `string`. Required when `ConnectedServiceNameSelector = ConnectedServiceName`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the target Azure classic subscription for deploying SQL files.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureSubscription"::: -->
:::moniker range="<=azure-pipelines"

**`azureSubscription`** - **Azure Subscription**<br>
Input alias: `ConnectedServiceNameARM`. `string`. Required when `ConnectedServiceNameSelector = ConnectedServiceNameARM`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the target Azure Resource Manager subscription for deploying SQL files.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AuthenticationType"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`AuthenticationType`** - **Authentication Type**<br>
`string`. Required. Allowed values: `server` (SQL Server Authentication), `aadAuthenticationPassword` (Active Directory - Password), `aadAuthenticationIntegrated` (Active Directory - Integrated), `connectionString` (Connection String), `servicePrincipal` (Service Principal). Default value: `server`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the type of database authentication. It can be an SQL Server, Active Directory (integrated), Active Directory (password), connection string, or service principal authentication. Integrated authentication means that the agent accesses the database using its current Active Directory account context.

Specify the option to connect to the Azure SQL Server database. You can provide the Azure SQL Server database details, the SQL Server connection string, AD Authentication (password or integrated), or use a service principal. For SQL Server authentication, use the SQL Server's user credentials. For AD authentication, use the credentials for the AD user configured to the SQL Server.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range=">=azure-pipelines-2019.1 <=azure-pipelines-2020"

**`AuthenticationType`** - **Authentication Type**<br>
`string`. Required. Allowed values: `server` (SQL Server Authentication), `aadAuthenticationPassword` (Active Directory - Password), `aadAuthenticationIntegrated` (Active Directory - Integrated), `connectionString` (Connection String). Default value: `server`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the type of database authentication. It can be an SQL Server, Active Directory (integrated), Active Directory (password), connection string, or service principal authentication. Integrated authentication means that the agent accesses the database using its current Active Directory account context.

Specify the option to connect to the Azure SQL Server database. You can provide the Azure SQL Server database details, the SQL Server connection string, AD Authentication (password or integrated), or use a service principal. For SQL Server authentication, use the SQL Server's user credentials. For AD authentication, use the credentials for the AD user configured to the SQL Server.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ServerName"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`ServerName`** - **Azure SQL Server**<br>
`string`. Required when `AuthenticationType = server || AuthenticationType = aadAuthenticationPassword || AuthenticationType = aadAuthenticationIntegrated || AuthenticationType = servicePrincipal`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the Azure SQL Server name, like `Fabrikam.database.windows.net,1433` or `Fabrikam.database.windows.net`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range=">=azure-pipelines-2019.1 <=azure-pipelines-2020"

**`ServerName`** - **Azure SQL Server**<br>
`string`. Required when `AuthenticationType = server || AuthenticationType = aadAuthenticationPassword || AuthenticationType = aadAuthenticationIntegrated`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the Azure SQL Server name, like `Fabrikam.database.windows.net,1433` or `Fabrikam.database.windows.net`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="<=azure-pipelines-2019"

**`ServerName`** - **Azure SQL Server Name**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the Azure SQL Server name, like `Fabrikam.database.windows.net,1433` or `Fabrikam.database.windows.net`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DatabaseName"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`DatabaseName`** - **Database**<br>
`string`. Required when `AuthenticationType = server || AuthenticationType = aadAuthenticationPassword || AuthenticationType = aadAuthenticationIntegrated || AuthenticationType = servicePrincipal`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of the Azure SQL database where the files are deployed.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range=">=azure-pipelines-2019.1 <=azure-pipelines-2020"

**`DatabaseName`** - **Database**<br>
`string`. Required when `AuthenticationType = server || AuthenticationType = aadAuthenticationPassword || AuthenticationType = aadAuthenticationIntegrated`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of the Azure SQL database where the files are deployed.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="<=azure-pipelines-2019"

**`DatabaseName`** - **Database Name**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of the Azure SQL database where the files are deployed.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SqlUsername"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`SqlUsername`** - **Login**<br>
`string`. Required when `AuthenticationType = server`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the Azure SQL Server administrator login.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2019"

**`SqlUsername`** - **Server Admin Login**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the Azure SQL Server administrator login or Active Directory user name.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`SqlUsername`** - **Server Admin Login**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the Azure SQL Server administrator login or Active Directory user name.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SqlPassword"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`SqlPassword`** - **Password**<br>
`string`. Required when `AuthenticationType = server`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the password for the Azure SQL Server administrator. Variables defined in the build or release pipelines as `$(passwordVariable)` are accepted. You can mark the variable type as `secret` to secure it.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2019"

**`SqlPassword`** - **Password**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the password for the Azure SQL Server administrator. Variables defined in the build or release pipelines as `$(passwordVariable)` are accepted. You can mark the variable type as `secret` to secure it.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`SqlPassword`** - **Password**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the password for the Azure SQL Server administrator. Variables defined in the build or release pipelines as `$(passwordVariable)` are accepted. You can mark the variable type as `secret` to secure it.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="aadSqlUsername"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`aadSqlUsername`** - **Login**<br>
`string`. Required when `AuthenticationType = aadAuthenticationPassword`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the Active Directory user name.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="aadSqlPassword"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`aadSqlPassword`** - **Password**<br>
`string`. Required when `AuthenticationType = aadAuthenticationPassword`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the password for the Active Directory user. Variables defined in the build or release pipelines as `$(passwordVariable)` are accepted. You can mark the variable type as `secret` to secure it.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ConnectionString"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`ConnectionString`** - **Connection String**<br>
`string`. Required when `AuthenticationType = connectionString`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the Azure SQL Server connection string, like `Server=testServer.database.windows.net;Database=testdb;User ID=AccountPlaceholder;Password=$(securePassword);`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deployType"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`deployType`** - **Deploy type**<br>
Input alias: `TaskNameSelector`. `string`. Required. Allowed values: `DacpacTask` (SQL DACPAC File), `SqlTask` (SQL Script File), `InlineSqlTask` (Inline SQL Script). Default value: `DacpacTask`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DeploymentAction"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`DeploymentAction`** - **Action**<br>
`string`. Required when `TaskNameSelector = DacpacTask`. Allowed values: `Publish`, `Extract`, `Export`, `Import`, `Script`, `DriftReport` (Drift Report), `DeployReport` (Deploy Report). Default value: `Publish`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies one of the SQL actions from the list. Learn more about the [SQL actions list](/sql/tools/sqlpackage/sqlpackage).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2019"

**`DeploymentAction`** - **Action**<br>
`string`. Required. Allowed values: `Publish`, `Extract`, `Export`, `Import`, `Script`, `DriftReport` (Drift Report), `DeployReport` (Deploy Report). Default value: `Publish`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies one of the SQL actions from the list. Learn more about the [SQL actions list](/sql/tools/sqlpackage/sqlpackage).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DacpacFile"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`DacpacFile`** - **DACPAC File**<br>
`string`. Required when `DeploymentAction = Publish || DeploymentAction = Script || DeploymentAction = DeployReport`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the location of the DACPAC file on the automation agent or on a UNC path that's accessible to the automation agent, like `\\BudgetIT\Web\Deploy\FabrikamDB.dacpac`. Predefined system variables, like `$(agent.releaseDirectory)`, can also be used.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2019"

**`DacpacFile`** - **DACPAC File**<br>
`string`. Required when `TaskNameSelector = DacpacTask || DeploymentAction = Script || DeploymentAction = DeployReport`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the location of the DACPAC file on the automation agent or on a UNC path that's accessible to the automation agent, like `\\BudgetIT\Web\Deploy\FabrikamDB.dacpac`. Predefined system variables, like `$(agent.releaseDirectory)`, can also be used.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`DacpacFile`** - **DACPAC File**<br>
`string`. Required when `TaskNameSelector = DacpacTask`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the location of the DACPAC file on the automation agent or on a UNC path that's accessible to the automation agent, like `\\BudgetIT\Web\Deploy\FabrikamDB.dacpac`. Predefined system variables, like `$(agent.releaseDirectory)`, can also be used.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="BacpacFile"::: -->
:::moniker range=">=azure-pipelines-2019"

**`BacpacFile`** - **BACPAC File**<br>
`string`. Required when `DeploymentAction = Import`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the location of the BACPAC file on the automation agent or on a UNC path that's accessible to the automation agent, like `\\BudgetIT\Web\Deploy\FabrikamDB.bacpac`. Predefined system variables, like `$(agent.releaseDirectory)`, can also be used.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SqlFile"::: -->
:::moniker range="<=azure-pipelines"

**`SqlFile`** - **SQL Script**<br>
`string`. Required when `TaskNameSelector = SqlTask`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the location of the SQL script file on the automation agent or on a UNC path that's accessible to the automation agent, like `\\BudgetIT\Web\Deploy\FabrikamDB.sql`. Predefined system variables, like `$(agent.releaseDirectory)`, can also be used.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SqlInline"::: -->
:::moniker range="<=azure-pipelines"

**`SqlInline`** - **Inline SQL Script**<br>
`string`. Required when `TaskNameSelector = InlineSqlTask`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the SQL script to execute on the previously selected database.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="PublishProfile"::: -->
:::moniker range=">=azure-pipelines-2019"

**`PublishProfile`** - **Publish Profile**<br>
`string`. Optional. Use when `TaskNameSelector = DacpacTask || DeploymentAction = Script || DeploymentAction = DeployReport`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provides fine-grained control over Azure SQL database creation or upgrades.  
Specifies the path to the publish profile XML file on the automation agent machine or on a UNC share. If the publish profile contains secrets, like credentials, upload it to the [secure files](/azure/devops/pipelines/library/secure-files) library where it is securely stored with encryption. Next, use the [Download secure file](download-secure-file-v1.md) task at the start of your pipeline to download it to the agent machine when the pipeline runs. Delete it when the pipeline is complete. Predefined system variables, like `$(agent.buildDirectory)` or `$(agent.releaseDirectory)`, can also be used.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`PublishProfile`** - **Publish Profile**<br>
`string`. Optional. Use when `TaskNameSelector = DacpacTask`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provides fine-grained control over Azure SQL database creation or upgrades.  
Specifies the path to the publish profile XML file on the automation agent machine or on a UNC share. If the publish profile contains secrets, like credentials, upload it to the [secure files](/azure/devops/pipelines/library/secure-files) library where it is securely stored with encryption. Next, use the [Download secure file](download-secure-file-v1.md) task at the start of your pipeline to download it to the agent machine when the pipeline runs. Delete it when the pipeline is complete. Predefined system variables, like `$(agent.buildDirectory)` or `$(agent.releaseDirectory)`, can also be used.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AdditionalArguments"::: -->
:::moniker range=">=azure-pipelines-2019"

**`AdditionalArguments`** - **Additional SqlPackage.exe Arguments**<br>
`string`. Optional. Use when `TaskNameSelector = DacpacTask || DeploymentAction = Extract || DeploymentAction = Export || DeploymentAction = Import || DeploymentAction = Script || DeploymentAction = DeployReport || DeploymentAction = DriftReport`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the additional `SqlPackage.exe` arguments that will be applied when deploying the Azure SQL database if the DACPAC option is selected, like `/p:IgnoreAnsiNulls=True /p:IgnoreComments=True`. These arguments will override the settings in the publish profile XML file (if provided).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`AdditionalArguments`** - **Additional SqlPackage.exe Arguments**<br>
`string`. Optional. Use when `TaskNameSelector = DacpacTask`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the additional `SqlPackage.exe` arguments that will be applied when deploying the Azure SQL database if the DACPAC option is selected, like `/p:IgnoreAnsiNulls=True /p:IgnoreComments=True`. These arguments will override the settings in the publish profile XML file (if provided).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SqlAdditionalArguments"::: -->
:::moniker range="<=azure-pipelines"

**`SqlAdditionalArguments`** - **Additional Invoke-Sqlcmd Arguments**<br>
`string`. Optional. Use when `TaskNameSelector = SqlTask`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the additional Invoke-Sqlcmd arguments that are applied when executing the given SQL query on the Azure SQL database, like `-ConnectionTimeout 100 -OutputSqlErrors`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="InlineAdditionalArguments"::: -->
:::moniker range="<=azure-pipelines"

**`InlineAdditionalArguments`** - **Additional Invoke-Sqlcmd Arguments**<br>
`string`. Optional. Use when `TaskNameSelector = InlineSqlTask`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the additional Invoke-Sqlcmd arguments that are applied when executing the given SQL query on the Azure SQL Database, like `-ConnectionTimeout 100 -OutputSqlErrors`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="IpDetectionMethod"::: -->
:::moniker range="<=azure-pipelines"

**`IpDetectionMethod`** - **Specify Firewall Rules Using**<br>
`string`. Required. Allowed values: `AutoDetect`, `IPAddressRange`. Default value: `AutoDetect`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
For the task to run, the IP address of the automation agent must be added to the **Allowed IP Addresses** in the Azure SQL Server's firewall. Select auto-detect to automatically add the firewall exception for the range of the possible IP address of the automation agent, or specify the range explicitly.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="StartIpAddress"::: -->
:::moniker range="<=azure-pipelines"

**`StartIpAddress`** - **Start IP Address**<br>
`string`. Required when `IpDetectionMethod = IPAddressRange`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the starting IP address of the automation agent machine pool, like `196.21.30.50`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="EndIpAddress"::: -->
:::moniker range="<=azure-pipelines"

**`EndIpAddress`** - **End IP Address**<br>
`string`. Required when `IpDetectionMethod = IPAddressRange`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the ending IP address of the automation agent machine pool, like `196.21.30.65`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DeleteFirewallRule"::: -->
:::moniker range="<=azure-pipelines"

**`DeleteFirewallRule`** - **Delete Rule After Task Ends**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If selected, after the task ends, the IP addresses specified here are deleted from the **Allowed IP Addresses** list in the Azure SQL Server's firewall.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="TaskNameSelector"::: -->
:::moniker range="=azure-pipelines-2019"

**`TaskNameSelector`** - **Type**<br>
`string`. Optional. Use when `DeploymentAction = Publish`. Allowed values: `DacpacTask` (SQL DACPAC File), `SqlTask` (SQL Script File), `InlineSqlTask` (Inline SQL Script). Default value: `DacpacTask`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`TaskNameSelector`** - **Type**<br>
`string`. Allowed values: `DacpacTask` (SQL DACPAC File), `SqlTask` (SQL Script File), `InlineSqlTask` (Inline SQL Script). Default value: `DacpacTask`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

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
The generated output file path when the deployment package action is `Extract`, `Export`, `Script`, `DriftReport`, or `DeployReport`.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2018"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

Use this task to deploy an Azure SQL database using a DACPAC, or run scripts using SQLCMD.

> [!IMPORTANT]
> This task is only supported in a Windows environment. If you are trying to use Azure Active Directory (Azure AD) integrated authentication, you must create a private agent. Azure AD integrated authentication is not supported for hosted agents.
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