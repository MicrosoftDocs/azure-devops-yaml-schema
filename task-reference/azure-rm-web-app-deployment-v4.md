---
title: AzureRmWebAppDeployment@4 - Azure App Service deploy v4 task
description: Deploy to Azure App Service a web, mobile, or API app using Docker, Java, .NET, .NET Core, Node.js, PHP, Python, or Ruby.
ms.date: 03/21/2024
monikerRange: ">=azure-pipelines-2019"
---

# AzureRmWebAppDeployment@4 - Azure App Service deploy v4 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Use this task to deploy to Azure App Service a web, mobile, or API app using Docker, Java, .NET, .NET Core, Node.js, PHP, Python, or Ruby.

> [!NOTE]
> Use [AzureFunctionApp@1](azure-function-app-v1.md) to deploy Azure Functions apps.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Update Azure App Services on Windows, Web App on Linux with built-in images or Docker containers, ASP.NET, .NET Core, PHP, Python or Node.js based Web applications, Function Apps on Windows or Linux with Docker Containers, Mobile Apps, API applications, and Web Jobs using Web Deploy/[Kudu REST APIs](https://github.com/projectkudu/kudu/wiki/REST-API).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="=azure-pipelines"

```yaml
# Azure App Service deploy v4
# Deploy to Azure App Service a web, mobile, or API app using Docker, Java, .NET, .NET Core, Node.js, PHP, Python, or Ruby.
- task: AzureRmWebAppDeployment@4
  inputs:
    ConnectionType: 'AzureRM' # 'AzureRM' | 'PublishProfile'. Required. Connection type. Default: AzureRM.
    azureSubscription: # string. Alias: ConnectedServiceName. Required when ConnectionType = AzureRM. Azure subscription. 
    #PublishProfilePath: '$(System.DefaultWorkingDirectory)/**/*.pubxml' # string. Required when ConnectionType = PublishProfile. Publish profile path. Default: $(System.DefaultWorkingDirectory)/**/*.pubxml.
    #PublishProfilePassword: # string. Required when ConnectionType = PublishProfile. Publish profile password. 
    appType: 'webApp' # 'webApp' | 'webAppLinux' | 'webAppContainer' | 'webAppHyperVContainer' | 'functionApp' | 'functionAppLinux' | 'functionAppContainer' | 'apiApp' | 'mobileApp'. Alias: WebAppKind. Required when ConnectionType = AzureRM. App Service type. Default: webApp.
    WebAppName: # string. Required when ConnectionType = AzureRM. App Service name. 
    #deployToSlotOrASE: false # boolean. Alias: DeployToSlotOrASEFlag. Optional. Use when ConnectionType = AzureRM && WebAppKind != "". Deploy to Slot or App Service Environment. Default: false.
    #ResourceGroupName: # string. Required when DeployToSlotOrASEFlag = true. Resource group. 
    #SlotName: 'production' # string. Required when DeployToSlotOrASEFlag = true. Slot. Default: production.
    #DockerNamespace: # string. Required when WebAppKind = webAppContainer || WebAppkind = functionAppContainer || WebAppKind = webAppHyperVContainer. Registry or Namespace. 
    #DockerRepository: # string. Required when WebAppKind = webAppContainer || WebAppkind = functionAppContainer || WebAppKind = webAppHyperVContainer. Image. 
    #DockerImageTag: # string. Optional. Use when WebAppKind = webAppContainer || WebAppkind = functionAppContainer || WebAppKind = webAppHyperVContainer. Tag. 
    #VirtualApplication: # string. Optional. Use when WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppKind != webAppHyperVContainer && WebAppkind != functionAppContainer && WebAppKind != functionApp && webAppKind != functionAppLinux && WebAppKind != "". Virtual application. 
    #packageForLinux: '$(System.DefaultWorkingDirectory)/**/*.zip' # string. Alias: Package. Required when ConnectionType = PublishProfile || WebAppKind = webApp || WebAppKind = apiApp || WebAppKind = functionApp || WebAppKind = mobileApp || WebAppKind = webAppLinux || webAppKind = functionAppLinux. Package or folder. Default: $(System.DefaultWorkingDirectory)/**/*.zip.
    #RuntimeStack: # string. Optional. Use when WebAppKind = webAppLinux. Runtime Stack. 
    #RuntimeStackFunction: # 'DOTNET|2.2' | 'DOTNET|3.1' | 'JAVA|8' | 'JAVA|11' | 'NODE|8' | 'NODE|10' | 'NODE|12' | 'NODE|14' | 'PYTHON|3.6' | 'PYTHON|3.7' | 'PYTHON|3.8'. Optional. Use when WebAppKind = functionAppLinux. Runtime Stack. 
    #StartupCommand: # string. Optional. Use when WebAppKind = webAppLinux || WebAppKind = webAppContainer || WebAppkind = functionAppContainer || WebAppKind = functionAppLinux || WebAppKind = webAppHyperVContainer. Startup command. 
  # Post Deployment Action
    #ScriptType: # 'Inline Script' | 'File Path'. Optional. Use when ConnectionType = AzureRM && WebAppKind != "" && WebAppKind != webAppContainer && WebAppKind != webAppHyperVContainer && WebAppkind != functionAppContainer. Deployment script type. 
    #InlineScript: ':: You can provide your deployment commands here. One command per line.' # string. Required when ScriptType == Inline Script && ConnectionType = AzureRM && WebAppKind != "" && WebAppKind != webAppContainer && WebAppKind != webAppHyperVContainer && WebAppkind != functionAppContainer. Inline Script. Default: :: You can provide your deployment commands here. One command per line..
    #ScriptPath: # string. Required when ScriptType == File Path && ConnectionType = AzureRM && WebAppKind != "" && WebAppKind != webAppContainer && WebAppKind != webAppHyperVContainer && WebAppkind != functionAppContainer. Deployment script path. 
  # File Transforms & Variable Substitution Options
    #WebConfigParameters: # string. Optional. Use when WebAppKind != webAppContainer && WebAppKind != webAppHyperVContainer && WebAppkind != functionAppContainer && WebAppKind != webAppLinux && webAppKind != functionAppLinux && Package NotEndsWith .war. Generate web.config parameters for Python, Node.js, Go and Java apps. 
    #enableXmlTransform: false # boolean. Alias: XmlTransformation. Optional. Use when WebAppKind != webAppContainer && WebAppKind != webAppHyperVContainer && WebAppkind != functionAppContainer && WebAppKind != webAppLinux && webAppKind != functionAppLinux && Package NotEndsWith .war. XML transformation. Default: false.
    #enableXmlVariableSubstitution: false # boolean. Alias: XmlVariableSubstitution. Optional. Use when WebAppKind != webAppContainer && WebAppKind != webAppHyperVContainer && WebAppkind != functionAppContainer && WebAppKind != webAppLinux && webAppKind != functionAppLinux && Package NotEndsWith .war. XML variable substitution. Default: false.
    #JSONFiles: # string. Optional. Use when WebAppKind != webAppContainer && WebAppKind != webAppHyperVContainer && WebAppkind != functionAppContainer && WebAppKind != webAppLinux && webAppKind != functionAppLinux && Package NotEndsWith .war. JSON variable substitution. 
  # Application and Configuration Settings
    #AppSettings: # string. Optional. Use when ConnectionType = AzureRM. App settings. 
    #ConfigurationSettings: # string. Optional. Use when ConnectionType = AzureRM. Configuration settings. 
  # Additional Deployment Options
    #enableCustomDeployment: false # boolean. Alias: UseWebDeploy. Optional. Use when ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppKind != webAppHyperVContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar. Select deployment method. Default: false.
    #DeploymentType: 'webDeploy' # 'webDeploy' | 'zipDeploy' | 'runFromZip'. Required when UseWebDeploy == true && ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppKind != webAppHyperVContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar. Deployment method. Default: webDeploy.
    #TakeAppOfflineFlag: true # boolean. Optional. Use when UseWebDeploy == true && DeploymentType != runFromZip && ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppKind != webAppHyperVContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar. Take App Offline. Default: true.
    #SetParametersFile: # string. Optional. Use when UseWebDeploy == true && DeploymentType == webDeploy && ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppKind != webAppHyperVContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar. SetParameters file. 
    #RemoveAdditionalFilesFlag: false # boolean. Optional. Use when UseWebDeploy == true && DeploymentType == webDeploy && ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppKind != webAppHyperVContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar. Remove additional files at destination. Default: false.
    #ExcludeFilesFromAppDataFlag: true # boolean. Optional. Use when UseWebDeploy == true && DeploymentType == webDeploy && ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppKind != webAppHyperVContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar. Exclude files from the App_Data folder. Default: true.
    #AdditionalArguments: '-retryAttempts:6 -retryInterval:10000' # string. Optional. Use when UseWebDeploy == true && DeploymentType == webDeploy && ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppKind != webAppHyperVContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar. Additional arguments. Default: -retryAttempts:6 -retryInterval:10000.
    #RenameFilesFlag: true # boolean. Optional. Use when UseWebDeploy == true && DeploymentType == webDeploy && ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppKind != webAppHyperVContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar. Rename locked files. Default: true.
```

:::moniker-end

:::moniker range="=azure-pipelines-2022.1"

```yaml
# Azure App Service deploy v4
# Deploy to Azure App Service a web, mobile, or API app using Docker, Java, .NET, .NET Core, Node.js, PHP, Python, or Ruby.
- task: AzureRmWebAppDeployment@4
  inputs:
    ConnectionType: 'AzureRM' # 'AzureRM' | 'PublishProfile'. Required. Connection type. Default: AzureRM.
    azureSubscription: # string. Alias: ConnectedServiceName. Required when ConnectionType = AzureRM. Azure subscription. 
    #PublishProfilePath: '$(System.DefaultWorkingDirectory)/**/*.pubxml' # string. Required when ConnectionType = PublishProfile. Publish profile path. Default: $(System.DefaultWorkingDirectory)/**/*.pubxml.
    #PublishProfilePassword: # string. Required when ConnectionType = PublishProfile. Publish profile password. 
    appType: 'webApp' # 'webApp' | 'webAppLinux' | 'webAppContainer' | 'webAppHyperVContainer' | 'functionApp' | 'functionAppLinux' | 'functionAppContainer' | 'apiApp' | 'mobileApp'. Alias: WebAppKind. Required when ConnectionType = AzureRM. App Service type. Default: webApp.
    WebAppName: # string. Required when ConnectionType = AzureRM. App Service name. 
    #deployToSlotOrASE: false # boolean. Alias: DeployToSlotOrASEFlag. Optional. Use when ConnectionType = AzureRM && WebAppKind != "". Deploy to Slot or App Service Environment. Default: false.
    #ResourceGroupName: # string. Required when DeployToSlotOrASEFlag = true. Resource group. 
    #SlotName: 'production' # string. Required when DeployToSlotOrASEFlag = true. Slot. Default: production.
    #DockerNamespace: # string. Required when WebAppKind = webAppContainer || WebAppkind = functionAppContainer || WebAppkind = webAppHyperVContainer. Registry or Namespace. 
    #DockerRepository: # string. Required when WebAppKind = webAppContainer || WebAppkind = functionAppContainer || WebAppkind = webAppHyperVContainer. Image. 
    #DockerImageTag: # string. Optional. Use when WebAppKind = webAppContainer || WebAppkind = functionAppContainer || WebAppkind = webAppHyperVContainer. Tag. 
    #VirtualApplication: # string. Optional. Use when WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppkind != functionAppContainer && WebAppKind != functionApp && webAppKind != functionAppLinux && WebAppKind != "". Virtual application. 
    #packageForLinux: '$(System.DefaultWorkingDirectory)/**/*.zip' # string. Alias: Package. Required when ConnectionType = PublishProfile || WebAppKind = webApp || WebAppKind = apiApp || WebAppKind = functionApp || WebAppKind = mobileApp || WebAppKind = webAppLinux || webAppKind = functionAppLinux. Package or folder. Default: $(System.DefaultWorkingDirectory)/**/*.zip.
    #RuntimeStack: # string. Optional. Use when WebAppKind = webAppLinux. Runtime Stack. 
    #RuntimeStackFunction: # 'DOTNET|2.2' | 'DOTNET|3.1' | 'JAVA|8' | 'JAVA|11' | 'NODE|8' | 'NODE|10' | 'NODE|12' | 'NODE|14' | 'PYTHON|3.6' | 'PYTHON|3.7' | 'PYTHON|3.8'. Optional. Use when WebAppKind = functionAppLinux. Runtime Stack. 
    #StartupCommand: # string. Optional. Use when WebAppKind = webAppLinux || WebAppKind = webAppContainer || WebAppkind = functionAppContainer || WebAppKind = functionAppLinux || WebAppkind = webAppHyperVContainer. Startup command. 
  # Post Deployment Action
    #ScriptType: # 'Inline Script' | 'File Path'. Optional. Use when ConnectionType = AzureRM && WebAppKind != "" && WebAppKind != webAppContainer && WebAppkind != functionAppContainer. Deployment script type. 
    #InlineScript: ':: You can provide your deployment commands here. One command per line.' # string. Required when ScriptType == Inline Script && ConnectionType = AzureRM && WebAppKind != "" && WebAppKind != webAppContainer && WebAppkind != functionAppContainer. Inline Script. Default: :: You can provide your deployment commands here. One command per line..
    #ScriptPath: # string. Required when ScriptType == File Path && ConnectionType = AzureRM && WebAppKind != "" && WebAppKind != webAppContainer && WebAppkind != functionAppContainer. Deployment script path. 
  # File Transforms & Variable Substitution Options
    #WebConfigParameters: # string. Optional. Use when WebAppKind != webAppContainer && WebAppkind != functionAppContainer && WebAppKind != webAppLinux && webAppKind != functionAppLinux && Package NotEndsWith .war. Generate web.config parameters for Python, Node.js, Go and Java apps. 
    #enableXmlTransform: false # boolean. Alias: XmlTransformation. Optional. Use when WebAppKind != webAppContainer && WebAppkind != functionAppContainer && WebAppKind != webAppLinux && webAppKind != functionAppLinux && Package NotEndsWith .war. XML transformation. Default: false.
    #enableXmlVariableSubstitution: false # boolean. Alias: XmlVariableSubstitution. Optional. Use when WebAppKind != webAppContainer && WebAppkind != functionAppContainer && WebAppKind != webAppLinux && webAppKind != functionAppLinux && Package NotEndsWith .war. XML variable substitution. Default: false.
    #JSONFiles: # string. Optional. Use when WebAppKind != webAppContainer && WebAppkind != functionAppContainer && WebAppKind != webAppLinux && webAppKind != functionAppLinux && Package NotEndsWith .war. JSON variable substitution. 
  # Application and Configuration Settings
    #AppSettings: # string. Optional. Use when ConnectionType = AzureRM. App settings. 
    #ConfigurationSettings: # string. Optional. Use when ConnectionType = AzureRM. Configuration settings. 
  # Additional Deployment Options
    #enableCustomDeployment: false # boolean. Alias: UseWebDeploy. Optional. Use when ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar. Select deployment method. Default: false.
    #DeploymentType: 'webDeploy' # 'webDeploy' | 'zipDeploy' | 'runFromZip'. Required when UseWebDeploy == true && ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar. Deployment method. Default: webDeploy.
    #TakeAppOfflineFlag: true # boolean. Optional. Use when UseWebDeploy == true && DeploymentType != runFromZip && ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar. Take App Offline. Default: true.
    #SetParametersFile: # string. Optional. Use when UseWebDeploy == true && DeploymentType == webDeploy && ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar. SetParameters file. 
    #RemoveAdditionalFilesFlag: false # boolean. Optional. Use when UseWebDeploy == true && DeploymentType == webDeploy && ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar. Remove additional files at destination. Default: false.
    #ExcludeFilesFromAppDataFlag: true # boolean. Optional. Use when UseWebDeploy == true && DeploymentType == webDeploy && ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar. Exclude files from the App_Data folder. Default: true.
    #AdditionalArguments: '-retryAttempts:6 -retryInterval:10000' # string. Optional. Use when UseWebDeploy == true && DeploymentType == webDeploy && ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar. Additional arguments. Default: -retryAttempts:6 -retryInterval:10000.
    #RenameFilesFlag: true # boolean. Optional. Use when UseWebDeploy == true && DeploymentType == webDeploy && ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar. Rename locked files. Default: true.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2020.1 <=azure-pipelines-2022"

```yaml
# Azure App Service deploy v4
# Deploy to Azure App Service a web, mobile, or API app using Docker, Java, .NET, .NET Core, Node.js, PHP, Python, or Ruby.
- task: AzureRmWebAppDeployment@4
  inputs:
    ConnectionType: 'AzureRM' # 'AzureRM' | 'PublishProfile'. Required. Connection type. Default: AzureRM.
    azureSubscription: # string. Alias: ConnectedServiceName. Required when ConnectionType = AzureRM. Azure subscription. 
    #PublishProfilePath: '$(System.DefaultWorkingDirectory)/**/*.pubxml' # string. Required when ConnectionType = PublishProfile. Publish profile path. Default: $(System.DefaultWorkingDirectory)/**/*.pubxml.
    #PublishProfilePassword: # string. Required when ConnectionType = PublishProfile. Publish profile password. 
    appType: 'webApp' # 'webApp' | 'webAppLinux' | 'webAppContainer' | 'functionApp' | 'functionAppLinux' | 'functionAppContainer' | 'apiApp' | 'mobileApp'. Alias: WebAppKind. Required when ConnectionType = AzureRM. App Service type. Default: webApp.
    WebAppName: # string. Required when ConnectionType = AzureRM. App Service name. 
    #deployToSlotOrASE: false # boolean. Alias: DeployToSlotOrASEFlag. Optional. Use when ConnectionType = AzureRM && WebAppKind != "". Deploy to Slot or App Service Environment. Default: false.
    #ResourceGroupName: # string. Required when DeployToSlotOrASEFlag = true. Resource group. 
    #SlotName: 'production' # string. Required when DeployToSlotOrASEFlag = true. Slot. Default: production.
    #DockerNamespace: # string. Required when WebAppKind = webAppContainer || WebAppkind = functionAppContainer. Registry or Namespace. 
    #DockerRepository: # string. Required when WebAppKind = webAppContainer || WebAppkind = functionAppContainer. Image. 
    #DockerImageTag: # string. Optional. Use when WebAppKind = webAppContainer || WebAppkind = functionAppContainer. Tag. 
    #VirtualApplication: # string. Optional. Use when WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppkind != functionAppContainer && WebAppKind != functionApp && webAppKind != functionAppLinux && WebAppKind != "". Virtual application. 
    #packageForLinux: '$(System.DefaultWorkingDirectory)/**/*.zip' # string. Alias: Package. Required when ConnectionType = PublishProfile || WebAppKind = webApp || WebAppKind = apiApp || WebAppKind = functionApp || WebAppKind = mobileApp || WebAppKind = webAppLinux || webAppKind = functionAppLinux. Package or folder. Default: $(System.DefaultWorkingDirectory)/**/*.zip.
    #RuntimeStack: # string. Optional. Use when WebAppKind = webAppLinux. Runtime Stack. 
    #RuntimeStackFunction: # 'DOTNET|2.2' | 'DOTNET|3.1' | 'JAVA|8' | 'JAVA|11' | 'NODE|8' | 'NODE|10' | 'NODE|12' | 'NODE|14' | 'PYTHON|3.6' | 'PYTHON|3.7' | 'PYTHON|3.8'. Optional. Use when WebAppKind = functionAppLinux. Runtime Stack. 
    #StartupCommand: # string. Optional. Use when WebAppKind = webAppLinux || WebAppKind = webAppContainer || WebAppkind = functionAppContainer || WebAppKind = functionAppLinux. Startup command. 
  # Post Deployment Action
    #ScriptType: # 'Inline Script' | 'File Path'. Optional. Use when ConnectionType = AzureRM && WebAppKind != "" && WebAppKind != webAppContainer && WebAppkind != functionAppContainer. Deployment script type. 
    #InlineScript: ':: You can provide your deployment commands here. One command per line.' # string. Required when ScriptType == Inline Script && ConnectionType = AzureRM && WebAppKind != "" && WebAppKind != webAppContainer && WebAppkind != functionAppContainer. Inline Script. Default: :: You can provide your deployment commands here. One command per line..
    #ScriptPath: # string. Required when ScriptType == File Path && ConnectionType = AzureRM && WebAppKind != "" && WebAppKind != webAppContainer && WebAppkind != functionAppContainer. Deployment script path. 
  # File Transforms & Variable Substitution Options
    #WebConfigParameters: # string. Optional. Use when WebAppKind != webAppContainer && WebAppkind != functionAppContainer && WebAppKind != webAppLinux && webAppKind != functionAppLinux && Package NotEndsWith .war. Generate web.config parameters for Python, Node.js, Go and Java apps. 
    #enableXmlTransform: false # boolean. Alias: XmlTransformation. Optional. Use when WebAppKind != webAppContainer && WebAppkind != functionAppContainer && WebAppKind != webAppLinux && webAppKind != functionAppLinux && Package NotEndsWith .war. XML transformation. Default: false.
    #enableXmlVariableSubstitution: false # boolean. Alias: XmlVariableSubstitution. Optional. Use when WebAppKind != webAppContainer && WebAppkind != functionAppContainer && WebAppKind != webAppLinux && webAppKind != functionAppLinux && Package NotEndsWith .war. XML variable substitution. Default: false.
    #JSONFiles: # string. Optional. Use when WebAppKind != webAppContainer && WebAppkind != functionAppContainer && WebAppKind != webAppLinux && webAppKind != functionAppLinux && Package NotEndsWith .war. JSON variable substitution. 
  # Application and Configuration Settings
    #AppSettings: # string. Optional. Use when ConnectionType = AzureRM. App settings. 
    #ConfigurationSettings: # string. Optional. Use when ConnectionType = AzureRM. Configuration settings. 
  # Additional Deployment Options
    #enableCustomDeployment: false # boolean. Alias: UseWebDeploy. Optional. Use when ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar. Select deployment method. Default: false.
    #DeploymentType: 'webDeploy' # 'webDeploy' | 'zipDeploy' | 'runFromZip'. Required when UseWebDeploy == true && ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar. Deployment method. Default: webDeploy.
    #TakeAppOfflineFlag: true # boolean. Optional. Use when UseWebDeploy == true && DeploymentType != runFromZip && ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar. Take App Offline. Default: true.
    #SetParametersFile: # string. Optional. Use when UseWebDeploy == true && DeploymentType == webDeploy && ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar. SetParameters file. 
    #RemoveAdditionalFilesFlag: false # boolean. Optional. Use when UseWebDeploy == true && DeploymentType == webDeploy && ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar. Remove additional files at destination. Default: false.
    #ExcludeFilesFromAppDataFlag: true # boolean. Optional. Use when UseWebDeploy == true && DeploymentType == webDeploy && ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar. Exclude files from the App_Data folder. Default: true.
    #AdditionalArguments: '-retryAttempts:6 -retryInterval:10000' # string. Optional. Use when UseWebDeploy == true && DeploymentType == webDeploy && ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar. Additional arguments. Default: -retryAttempts:6 -retryInterval:10000.
    #RenameFilesFlag: true # boolean. Optional. Use when UseWebDeploy == true && DeploymentType == webDeploy && ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar. Rename locked files. Default: true.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2019.1 <=azure-pipelines-2020"

```yaml
# Azure App Service deploy v4
# Deploy to Azure App Service a web, mobile, or API app using Docker, Java, .NET, .NET Core, Node.js, PHP, Python, or Ruby.
- task: AzureRmWebAppDeployment@4
  inputs:
    ConnectionType: 'AzureRM' # 'AzureRM' | 'PublishProfile'. Required. Connection type. Default: AzureRM.
    azureSubscription: # string. Alias: ConnectedServiceName. Required when ConnectionType = AzureRM. Azure subscription. 
    #PublishProfilePath: '$(System.DefaultWorkingDirectory)/**/*.pubxml' # string. Required when ConnectionType = PublishProfile. Publish profile path. Default: $(System.DefaultWorkingDirectory)/**/*.pubxml.
    #PublishProfilePassword: # string. Required when ConnectionType = PublishProfile. Publish profile password. 
    appType: 'webApp' # 'webApp' | 'webAppLinux' | 'webAppContainer' | 'functionApp' | 'functionAppLinux' | 'functionAppContainer' | 'apiApp' | 'mobileApp'. Alias: WebAppKind. Required when ConnectionType = AzureRM. App Service type. Default: webApp.
    WebAppName: # string. Required when ConnectionType = AzureRM. App Service name. 
    #deployToSlotOrASE: false # boolean. Alias: DeployToSlotOrASEFlag. Optional. Use when ConnectionType = AzureRM && WebAppKind != "". Deploy to Slot or App Service Environment. Default: false.
    #ResourceGroupName: # string. Required when DeployToSlotOrASEFlag = true. Resource group. 
    #SlotName: 'production' # string. Required when DeployToSlotOrASEFlag = true. Slot. Default: production.
    #DockerNamespace: # string. Required when WebAppKind = webAppContainer || WebAppkind = functionAppContainer. Registry or Namespace. 
    #DockerRepository: # string. Required when WebAppKind = webAppContainer || WebAppkind = functionAppContainer. Image. 
    #DockerImageTag: # string. Optional. Use when WebAppKind = webAppContainer || WebAppkind = functionAppContainer. Tag. 
    #VirtualApplication: # string. Optional. Use when WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppkind != functionAppContainer && WebAppKind != functionApp && webAppKind != functionAppLinux && WebAppKind != "". Virtual application. 
    #packageForLinux: '$(System.DefaultWorkingDirectory)/**/*.zip' # string. Alias: Package. Required when ConnectionType = PublishProfile || WebAppKind = webApp || WebAppKind = apiApp || WebAppKind = functionApp || WebAppKind = mobileApp || WebAppKind = webAppLinux || webAppKind = functionAppLinux. Package or folder. Default: $(System.DefaultWorkingDirectory)/**/*.zip.
    #RuntimeStack: # string. Optional. Use when WebAppKind = webAppLinux. Runtime Stack. 
    #RuntimeStackFunction: # 'DOCKER|microsoft/azure-functions-dotnet-core2.0:2.0' | 'DOCKER|microsoft/azure-functions-node8:2.0'. Optional. Use when WebAppKind = functionAppLinux. Runtime Stack. 
    #StartupCommand: # string. Optional. Use when WebAppKind = webAppLinux || WebAppKind = webAppContainer || WebAppkind = functionAppContainer || WebAppKind = functionAppLinux. Startup command. 
  # Post Deployment Action
    #ScriptType: # 'Inline Script' | 'File Path'. Optional. Use when ConnectionType = AzureRM && WebAppKind != "" && WebAppKind != webAppContainer && WebAppkind != functionAppContainer. Deployment script type. 
    #InlineScript: ':: You can provide your deployment commands here. One command per line.' # string. Required when ScriptType == Inline Script && ConnectionType = AzureRM && WebAppKind != "" && WebAppKind != webAppContainer && WebAppkind != functionAppContainer. Inline Script. Default: :: You can provide your deployment commands here. One command per line..
    #ScriptPath: # string. Required when ScriptType == File Path && ConnectionType = AzureRM && WebAppKind != "" && WebAppKind != webAppContainer && WebAppkind != functionAppContainer. Deployment script path. 
  # File Transforms & Variable Substitution Options
    #WebConfigParameters: # string. Optional. Use when WebAppKind != webAppContainer && WebAppkind != functionAppContainer && WebAppKind != webAppLinux && webAppKind != functionAppLinux && Package NotEndsWith .war. Generate web.config parameters for Python, Node.js, Go and Java apps. 
    #enableXmlTransform: false # boolean. Alias: XmlTransformation. Optional. Use when WebAppKind != webAppContainer && WebAppkind != functionAppContainer && WebAppKind != webAppLinux && webAppKind != functionAppLinux && Package NotEndsWith .war. XML transformation. Default: false.
    #enableXmlVariableSubstitution: false # boolean. Alias: XmlVariableSubstitution. Optional. Use when WebAppKind != webAppContainer && WebAppkind != functionAppContainer && WebAppKind != webAppLinux && webAppKind != functionAppLinux && Package NotEndsWith .war. XML variable substitution. Default: false.
    #JSONFiles: # string. Optional. Use when WebAppKind != webAppContainer && WebAppkind != functionAppContainer && WebAppKind != webAppLinux && webAppKind != functionAppLinux && Package NotEndsWith .war. JSON variable substitution. 
  # Application and Configuration Settings
    #AppSettings: # string. Optional. Use when ConnectionType = AzureRM. App settings. 
    #ConfigurationSettings: # string. Optional. Use when ConnectionType = AzureRM. Configuration settings. 
  # Additional Deployment Options
    #enableCustomDeployment: false # boolean. Alias: UseWebDeploy. Optional. Use when ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar. Select deployment method. Default: false.
    #DeploymentType: 'webDeploy' # 'webDeploy' | 'zipDeploy' | 'runFromZip'. Required when UseWebDeploy == true && ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar. Deployment method. Default: webDeploy.
    #TakeAppOfflineFlag: true # boolean. Optional. Use when UseWebDeploy == true && DeploymentType != runFromZip && ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar. Take App Offline. Default: true.
    #SetParametersFile: # string. Optional. Use when UseWebDeploy == true && DeploymentType == webDeploy && ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar. SetParameters file. 
    #RemoveAdditionalFilesFlag: false # boolean. Optional. Use when UseWebDeploy == true && DeploymentType == webDeploy && ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar. Remove additional files at destination. Default: false.
    #ExcludeFilesFromAppDataFlag: true # boolean. Optional. Use when UseWebDeploy == true && DeploymentType == webDeploy && ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar. Exclude files from the App_Data folder. Default: true.
    #AdditionalArguments: '-retryAttempts:6 -retryInterval:10000' # string. Optional. Use when UseWebDeploy == true && DeploymentType == webDeploy && ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar. Additional arguments. Default: -retryAttempts:6 -retryInterval:10000.
    #RenameFilesFlag: true # boolean. Optional. Use when UseWebDeploy == true && DeploymentType == webDeploy && ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar. Rename locked files. Default: true.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Azure App Service Deploy v4
# Update Azure App Services on Windows, Web App on Linux with built-in images or Docker containers, ASP.NET, .NET Core, PHP, Python or Node.js based Web applications, Function Apps on Windows or Linux with Docker Containers, Mobile Apps, API applications, Web Jobs using Web Deploy / Kudu REST APIs.
- task: AzureRmWebAppDeployment@4
  inputs:
    ConnectionType: 'AzureRM' # 'AzureRM' | 'PublishProfile'. Required. Connection type. Default: AzureRM.
    azureSubscription: # string. Alias: ConnectedServiceName. Required when ConnectionType = AzureRM. Azure subscription. 
    #PublishProfilePath: '$(System.DefaultWorkingDirectory)/**/*.pubxml' # string. Required when ConnectionType = PublishProfile. Publish profile path. Default: $(System.DefaultWorkingDirectory)/**/*.pubxml.
    #PublishProfilePassword: # string. Required when ConnectionType = PublishProfile. Publish profile password. 
    appType: 'webApp' # 'webApp' | 'webAppLinux' | 'webAppContainer' | 'functionApp' | 'functionAppLinux' | 'functionAppContainer' | 'apiApp' | 'mobileApp'. Alias: WebAppKind. Required when ConnectionType = AzureRM. App Service type. Default: webApp.
    WebAppName: # string. Required when ConnectionType = AzureRM. App Service name. 
    #deployToSlotOrASE: false # boolean. Alias: DeployToSlotOrASEFlag. Optional. Use when ConnectionType = AzureRM && WebAppKind != "". Deploy to Slot or App Service Environment. Default: false.
    #ResourceGroupName: # string. Required when DeployToSlotOrASEFlag = true. Resource group. 
    #SlotName: 'production' # string. Required when DeployToSlotOrASEFlag = true. Slot. Default: production.
    #DockerNamespace: # string. Required when WebAppKind = webAppContainer || WebAppkind = functionAppContainer. Registry or Namespace. 
    #DockerRepository: # string. Required when WebAppKind = webAppContainer || WebAppkind = functionAppContainer. Image. 
    #DockerImageTag: # string. Optional. Use when WebAppKind = webAppContainer || WebAppkind = functionAppContainer. Tag. 
    #VirtualApplication: # string. Optional. Use when WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppkind != functionAppContainer && WebAppKind != functionApp && webAppKind != functionAppLinux && WebAppKind != "". Virtual application. 
    #packageForLinux: '$(System.DefaultWorkingDirectory)/**/*.zip' # string. Alias: Package. Required when ConnectionType = PublishProfile || WebAppKind = webApp || WebAppKind = apiApp || WebAppKind = functionApp || WebAppKind = mobileApp || WebAppKind = webAppLinux || webAppKind = functionAppLinux. Package or folder. Default: $(System.DefaultWorkingDirectory)/**/*.zip.
    #RuntimeStack: # string. Optional. Use when WebAppKind = webAppLinux. Runtime Stack. 
    #RuntimeStackFunction: # 'DOCKER|microsoft/azure-functions-dotnet-core2.0:2.0' | 'DOCKER|microsoft/azure-functions-node8:2.0'. Optional. Use when WebAppKind = functionAppLinux. Runtime Stack. 
    #StartupCommand: # string. Optional. Use when WebAppKind = webAppLinux || WebAppKind = webAppContainer || WebAppkind = functionAppContainer. Startup command. 
  # Post Deployment Action
    #ScriptType: # 'Inline Script' | 'File Path'. Optional. Use when ConnectionType = AzureRM && WebAppKind != "" && WebAppKind != webAppContainer && WebAppkind != functionAppContainer. Deployment script type. 
    #InlineScript: ':: You can provide your deployment commands here. One command per line.' # string. Required when ScriptType == Inline Script && ConnectionType = AzureRM && WebAppKind != "" && WebAppKind != webAppContainer && WebAppkind != functionAppContainer. Inline Script. Default: :: You can provide your deployment commands here. One command per line..
    #ScriptPath: # string. Required when ScriptType == File Path && ConnectionType = AzureRM && WebAppKind != "" && WebAppKind != webAppContainer && WebAppkind != functionAppContainer. Deployment script path. 
  # File Transforms & Variable Substitution Options
    #WebConfigParameters: # string. Optional. Use when WebAppKind != webAppContainer && WebAppkind != functionAppContainer && WebAppKind != webAppLinux && webAppKind != functionAppLinux && Package NotEndsWith .war. Generate web.config parameters for Python, Node.js, Go and Java apps. 
    #enableXmlTransform: false # boolean. Alias: XmlTransformation. Optional. Use when WebAppKind != webAppContainer && WebAppkind != functionAppContainer && WebAppKind != webAppLinux && webAppKind != functionAppLinux && Package NotEndsWith .war. XML transformation. Default: false.
    #enableXmlVariableSubstitution: false # boolean. Alias: XmlVariableSubstitution. Optional. Use when WebAppKind != webAppContainer && WebAppkind != functionAppContainer && WebAppKind != webAppLinux && webAppKind != functionAppLinux && Package NotEndsWith .war. XML variable substitution. Default: false.
    #JSONFiles: # string. Optional. Use when WebAppKind != webAppContainer && WebAppkind != functionAppContainer && WebAppKind != webAppLinux && webAppKind != functionAppLinux && Package NotEndsWith .war. JSON variable substitution. 
  # Application and Configuration Settings
    #AppSettings: # string. Optional. Use when ConnectionType = AzureRM. App settings. 
    #ConfigurationSettings: # string. Optional. Use when ConnectionType = AzureRM. Configuration settings. 
  # Additional Deployment Options
    #enableCustomDeployment: false # boolean. Alias: UseWebDeploy. Optional. Use when ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar. Select deployment method. Default: false.
    #DeploymentType: 'webDeploy' # 'webDeploy' | 'zipDeploy' | 'runFromZip'. Required when UseWebDeploy == true && ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar. Deployment method. Default: webDeploy.
    #TakeAppOfflineFlag: true # boolean. Optional. Use when UseWebDeploy == true && DeploymentType != runFromZip && ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar. Take App Offline. Default: true.
    #SetParametersFile: # string. Optional. Use when UseWebDeploy == true && DeploymentType == webDeploy && ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar. SetParameters file. 
    #RemoveAdditionalFilesFlag: false # boolean. Optional. Use when UseWebDeploy == true && DeploymentType == webDeploy && ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar. Remove additional files at destination. Default: false.
    #ExcludeFilesFromAppDataFlag: true # boolean. Optional. Use when UseWebDeploy == true && DeploymentType == webDeploy && ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar. Exclude files from the App_Data folder. Default: true.
    #AdditionalArguments: '-retryAttempts:6 -retryInterval:10000' # string. Optional. Use when UseWebDeploy == true && DeploymentType == webDeploy && ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar. Additional arguments. Default: -retryAttempts:6 -retryInterval:10000.
    #RenameFilesFlag: true # boolean. Optional. Use when UseWebDeploy == true && DeploymentType == webDeploy && ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar. Rename locked files. Default: true.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="ConnectionType"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`ConnectionType`** - **Connection type**<br>
`string`. Required. Allowed values: `AzureRM` (Azure Resource Manager), `PublishProfile` (Publish Profile). Default value: `AzureRM`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the service connection type to use to deploy the Web App.

Specify `Publish Profile` for using Visual Studio created [Publish profiles](https://aka.ms/vsPublishProfile).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2019"

**`ConnectionType`** - **Connection type**<br>
`string`. Required. Allowed values: `AzureRM` (Azure Resource Manager), `PublishProfile` (Publish Profile). Default value: `AzureRM`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the service connection type to use to deploy the Web App.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureSubscription"::: -->
:::moniker range=">=azure-pipelines-2019"

**`azureSubscription`** - **Azure subscription**<br>
Input alias: `ConnectedServiceName`. `string`. Required when `ConnectionType = AzureRM`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the Azure Resource Manager subscription for the deployment.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="PublishProfilePath"::: -->
:::moniker range=">=azure-pipelines-2019"

**`PublishProfilePath`** - **Publish profile path**<br>
`string`. Required when `ConnectionType = PublishProfile`. Default value: `$(System.DefaultWorkingDirectory)/**/*.pubxml`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The path of the [publish profile](https://aka.ms/vsPublishProfile) created from Visual Studio.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="PublishProfilePassword"::: -->
:::moniker range=">=azure-pipelines-2019"

**`PublishProfilePassword`** - **Publish profile password**<br>
`string`. Required when `ConnectionType = PublishProfile`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
It is recommended to store a password in a secret variable and use that variable here e.g. `$(Password)`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="appType"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`appType`** - **App Service type**<br>
Input alias: `WebAppKind`. `string`. Required when `ConnectionType = AzureRM`. Allowed values: `webApp` (Web App on Windows), `webAppLinux` (Web App on Linux), `webAppContainer` (Web App for Containers (Linux)), `webAppHyperVContainer` (Web App for Containers (Windows)), `functionApp` (Function App on Windows (Not Recommended, Use Azure Functions Task)), `functionAppLinux` (Function App on Linux (Not Recommended, Use Azure Functions Task)), `functionAppContainer` (Function App for Containers (Linux) (Not Recommended, Use Azure Functions for container Task)), `apiApp` (API App), `mobileApp` (Mobile App). Default value: `webApp`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Choose from Web App On Windows, Web App On Linux, Web App for Containers, Function App, Function App on Linux, Function App for Containers and Mobile App.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2022"

**`appType`** - **App Service type**<br>
Input alias: `WebAppKind`. `string`. Required when `ConnectionType = AzureRM`. Allowed values: `webApp` (Web App on Windows), `webAppLinux` (Web App on Linux), `webAppContainer` (Web App for Containers (Linux)), `functionApp` (Function App on Windows), `functionAppLinux` (Function App on Linux), `functionAppContainer` (Function App for Containers (Linux)), `apiApp` (API App), `mobileApp` (Mobile App). Default value: `webApp`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Choose from Web App On Windows, Web App On Linux, Web App for Containers, Function App, Function App on Linux, Function App for Containers and Mobile App.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="WebAppName"::: -->
:::moniker range=">=azure-pipelines-2019"

**`WebAppName`** - **App Service name**<br>
`string`. Required when `ConnectionType = AzureRM`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the name of an existing Azure App Service. App services based on the selected app type will only be listed when using the task assistant.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deployToSlotOrASE"::: -->
:::moniker range=">=azure-pipelines-2019"

**`deployToSlotOrASE`** - **Deploy to Slot or App Service Environment**<br>
Input alias: `DeployToSlotOrASEFlag`. `boolean`. Optional. Use when `ConnectionType = AzureRM && WebAppKind != ""`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the option to deploy to an existing deployment slot or Azure App Service environment. For both targets, the task requires a Resource Group name.
If the deployment target is a slot, by default the deployment is to the **Production** slot. Any other existing slot name can be provided.
If the deployment target is an Azure App Service environment, leave the slot name as `Production` and specify just the Resource Group name.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ResourceGroupName"::: -->
:::moniker range=">=azure-pipelines-2019"

**`ResourceGroupName`** - **Resource group**<br>
`string`. Required when `DeployToSlotOrASEFlag = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The Resource group name is required when the deployment target is either a deployment slot or an App Service Environment.

Specify the Azure Resource group that contains the Azure App Service specified above.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SlotName"::: -->
:::moniker range=">=azure-pipelines-2019"

**`SlotName`** - **Slot**<br>
`string`. Required when `DeployToSlotOrASEFlag = true`. Default value: `production`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify an existing slot other than the Production slot.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DockerNamespace"::: -->
:::moniker range="=azure-pipelines"

**`DockerNamespace`** - **Registry or Namespace**<br>
`string`. Required when `WebAppKind = webAppContainer || WebAppkind = functionAppContainer || WebAppKind = webAppHyperVContainer`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
A globally unique top-level domain name for your specific registry or namespace. Note: The fully qualified image name will be of the format: `{registry or namespace}/{repository}:{tag}`. For example, `myregistry.azurecr.io/nginx:latest`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2022.1"

**`DockerNamespace`** - **Registry or Namespace**<br>
`string`. Required when `WebAppKind = webAppContainer || WebAppkind = functionAppContainer || WebAppkind = webAppHyperVContainer`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
A globally unique top-level domain name for your specific registry or namespace. Note: The fully qualified image name will be of the format: `{registry or namespace}/{repository}:{tag}`. For example, `myregistry.azurecr.io/nginx:latest`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2022"

**`DockerNamespace`** - **Registry or Namespace**<br>
`string`. Required when `WebAppKind = webAppContainer || WebAppkind = functionAppContainer`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
A globally unique top-level domain name for your specific registry or namespace. Note: The fully qualified image name will be of the format: `{registry or namespace}/{repository}:{tag}`. For example, `myregistry.azurecr.io/nginx:latest`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DockerRepository"::: -->
:::moniker range="=azure-pipelines"

**`DockerRepository`** - **Image**<br>
`string`. Required when `WebAppKind = webAppContainer || WebAppkind = functionAppContainer || WebAppKind = webAppHyperVContainer`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of the repository where the container images are stored. Note: The fully qualified image name will be of the format: `{registry or namespace}/{repository}:{tag}`. For example, `myregistry.azurecr.io/nginx:latest`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2022.1"

**`DockerRepository`** - **Image**<br>
`string`. Required when `WebAppKind = webAppContainer || WebAppkind = functionAppContainer || WebAppkind = webAppHyperVContainer`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of the repository where the container images are stored. Note: The fully qualified image name will be of the format: `{registry or namespace}/{repository}:{tag}`. For example, `myregistry.azurecr.io/nginx:latest`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2022"

**`DockerRepository`** - **Image**<br>
`string`. Required when `WebAppKind = webAppContainer || WebAppkind = functionAppContainer`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of the repository where the container images are stored. Note: The fully qualified image name will be of the format: `{registry or namespace}/{repository}:{tag}`. For example, `myregistry.azurecr.io/nginx:latest`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DockerImageTag"::: -->
:::moniker range="=azure-pipelines"

**`DockerImageTag`** - **Tag**<br>
`string`. Optional. Use when `WebAppKind = webAppContainer || WebAppkind = functionAppContainer || WebAppKind = webAppHyperVContainer`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Tags are the mechanism that registries use to apply version information to Docker images. Note: The fully qualified image name will be of the format: `{registry or namespace}/{repository}:{tag}`. For example, `myregistry.azurecr.io/nginx:latest`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2022.1"

**`DockerImageTag`** - **Tag**<br>
`string`. Optional. Use when `WebAppKind = webAppContainer || WebAppkind = functionAppContainer || WebAppkind = webAppHyperVContainer`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Tags are the mechanism that registries use to apply version information to Docker images. Note: The fully qualified image name will be of the format: `{registry or namespace}/{repository}:{tag}`. For example, `myregistry.azurecr.io/nginx:latest`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2022"

**`DockerImageTag`** - **Tag**<br>
`string`. Optional. Use when `WebAppKind = webAppContainer || WebAppkind = functionAppContainer`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Tags are the mechanism that registries use to apply version information to Docker images. Note: The fully qualified image name will be of the format: `{registry or namespace}/{repository}:{tag}`. For example, `myregistry.azurecr.io/nginx:latest`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="VirtualApplication"::: -->
:::moniker range="=azure-pipelines"

**`VirtualApplication`** - **Virtual application**<br>
`string`. Optional. Use when `WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppKind != webAppHyperVContainer && WebAppkind != functionAppContainer && WebAppKind != functionApp && webAppKind != functionAppLinux && WebAppKind != ""`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the name of the Virtual Application that has been configured in the Azure portal. This option is not required for deployments to the website root. The Virtual Application must have been configured before deployment of the web project.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2022.1"

**`VirtualApplication`** - **Virtual application**<br>
`string`. Optional. Use when `WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppkind != functionAppContainer && WebAppKind != functionApp && webAppKind != functionAppLinux && WebAppKind != ""`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the name of the Virtual Application that has been configured in the Azure portal. This option is not required for deployments to the website root. The Virtual Application must have been configured before deployment of the web project.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="packageForLinux"::: -->
:::moniker range=">=azure-pipelines-2019"

**`packageForLinux`** - **Package or folder**<br>
Input alias: `Package`. `string`. Required when `ConnectionType = PublishProfile || WebAppKind = webApp || WebAppKind = apiApp || WebAppKind = functionApp || WebAppKind = mobileApp || WebAppKind = webAppLinux || webAppKind = functionAppLinux`. Default value: `$(System.DefaultWorkingDirectory)/**/*.zip`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The file path to the package, or to a folder containing app service contents generated by MSBuild or a compressed zip or war file.

Variables are [Build](/azure/devops/pipelines/build/variables) and [Release](/azure/devops/pipelines/release/variables#default-variables). [Wildcards](/azure/devops/pipelines/tasks/file-matching-patterns) are supported.

For example, `$(System.DefaultWorkingDirectory)/\*\*/\*.zip` or `$(System.DefaultWorkingDirectory)/\*\*/\*.war`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="RuntimeStack"::: -->
:::moniker range=">=azure-pipelines-2019"

**`RuntimeStack`** - **Runtime Stack**<br>
`string`. Optional. Use when `WebAppKind = webAppLinux`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the framework and version for Function App on Linux.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="RuntimeStackFunction"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`RuntimeStackFunction`** - **Runtime Stack**<br>
`string`. Optional. Use when `WebAppKind = functionAppLinux`. Allowed values: `DOTNET|2.2` (DOTNET|2.2 (functionapp v2)), `DOTNET|3.1` (DOTNET|3.1 (functionapp v3)), `JAVA|8` (JAVA|8 (functionapp v2/v3)), `JAVA|11` (JAVA|11  (functionapp v3)), `NODE|8` (NODE|8 (functionapp v2)), `NODE|10` (NODE|10 (functionapp v2/v3)), `NODE|12` (NODE|12 (functionapp v3)), `NODE|14` (NODE|14 (functionapp v3)), `PYTHON|3.6` (PYTHON|3.6 (functionapp v2/v3)), `PYTHON|3.7` (PYTHON|3.7 (functionapp v2/v3)), `PYTHON|3.8` (PYTHON|3.8 (functionapp v3)).<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the framework and version. Refer to the [Azure Functions runtime versions overview](/azure/azure-functions/functions-versions#languages) for supported runtime versions. Old values like `DOCKER|microsoft/azure-functions-*` are deprecated. Please use the new values from dropdown.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2020"

**`RuntimeStackFunction`** - **Runtime Stack**<br>
`string`. Optional. Use when `WebAppKind = functionAppLinux`. Allowed values: `DOCKER|microsoft/azure-functions-dotnet-core2.0:2.0` (.NET), `DOCKER|microsoft/azure-functions-node8:2.0` (JavaScript).<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the framework and version.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="StartupCommand"::: -->
:::moniker range="=azure-pipelines"

**`StartupCommand`** - **Startup command**<br>
`string`. Optional. Use when `WebAppKind = webAppLinux || WebAppKind = webAppContainer || WebAppkind = functionAppContainer || WebAppKind = functionAppLinux || WebAppKind = webAppHyperVContainer`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the Startup command. For example:

dotnet exec `filename.dll`

dotnet `filename.dll`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2022.1"

**`StartupCommand`** - **Startup command**<br>
`string`. Optional. Use when `WebAppKind = webAppLinux || WebAppKind = webAppContainer || WebAppkind = functionAppContainer || WebAppKind = functionAppLinux || WebAppkind = webAppHyperVContainer`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the Startup command. For example:

dotnet exec `filename.dll`

dotnet `filename.dll`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range=">=azure-pipelines-2020 <=azure-pipelines-2022"

**`StartupCommand`** - **Startup command**<br>
`string`. Optional. Use when `WebAppKind = webAppLinux || WebAppKind = webAppContainer || WebAppkind = functionAppContainer || WebAppKind = functionAppLinux`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the Startup command. For example:

dotnet exec `filename.dll`

dotnet `filename.dll`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

**`StartupCommand`** - **Startup command**<br>
`string`. Optional. Use when `WebAppKind = webAppLinux || WebAppKind = webAppContainer || WebAppkind = functionAppContainer || WebAppKind = functionAppLinux`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the Startup command. For example, `dotnet run` `dotnet filename.dll`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2019"

**`StartupCommand`** - **Startup command**<br>
`string`. Optional. Use when `WebAppKind = webAppLinux || WebAppKind = webAppContainer || WebAppkind = functionAppContainer`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the Startup command.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ScriptType"::: -->
:::moniker range="=azure-pipelines"

**`ScriptType`** - **Deployment script type**<br>
`string`. Optional. Use when `ConnectionType = AzureRM && WebAppKind != "" && WebAppKind != webAppContainer && WebAppKind != webAppHyperVContainer && WebAppkind != functionAppContainer`. Allowed values: `Inline Script`, `File Path` (Script File Path).<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Customizes the deployment by providing a script that runs on the Azure App Service after successful deployment. Choose inline deployment script or the path and name of a script file. Learn more about [Azure App Service Deployment](https://go.microsoft.com/fwlink/?linkid=843471).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2022.1"

**`ScriptType`** - **Deployment script type**<br>
`string`. Optional. Use when `ConnectionType = AzureRM && WebAppKind != "" && WebAppKind != webAppContainer && WebAppkind != functionAppContainer`. Allowed values: `Inline Script`, `File Path` (Script File Path).<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Customizes the deployment by providing a script that runs on the Azure App Service after successful deployment. Choose inline deployment script or the path and name of a script file. Learn more about [Azure App Service Deployment](https://go.microsoft.com/fwlink/?linkid=843471).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="InlineScript"::: -->
:::moniker range="=azure-pipelines"

**`InlineScript`** - **Inline Script**<br>
`string`. Required when `ScriptType == Inline Script && ConnectionType = AzureRM && WebAppKind != "" && WebAppKind != webAppContainer && WebAppKind != webAppHyperVContainer && WebAppkind != functionAppContainer`. Default value: `:: You can provide your deployment commands here. One command per line.`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The script to execute. You can provide your deployment commands here, one command per line. See the following example.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2022.1"

**`InlineScript`** - **Inline Script**<br>
`string`. Required when `ScriptType == Inline Script && ConnectionType = AzureRM && WebAppKind != "" && WebAppKind != webAppContainer && WebAppkind != functionAppContainer`. Default value: `:: You can provide your deployment commands here. One command per line.`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The script to execute. You can provide your deployment commands here, one command per line. See the following example.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ScriptPath"::: -->
:::moniker range="=azure-pipelines"

**`ScriptPath`** - **Deployment script path**<br>
`string`. Required when `ScriptType == File Path && ConnectionType = AzureRM && WebAppKind != "" && WebAppKind != webAppContainer && WebAppKind != webAppHyperVContainer && WebAppkind != functionAppContainer`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The path and name of the script to execute.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2022.1"

**`ScriptPath`** - **Deployment script path**<br>
`string`. Required when `ScriptType == File Path && ConnectionType = AzureRM && WebAppKind != "" && WebAppKind != webAppContainer && WebAppkind != functionAppContainer`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The path and name of the script to execute.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="WebConfigParameters"::: -->
:::moniker range="=azure-pipelines"

**`WebConfigParameters`** - **Generate web.config parameters for Python, Node.js, Go and Java apps**<br>
`string`. Optional. Use when `WebAppKind != webAppContainer && WebAppKind != webAppHyperVContainer && WebAppkind != functionAppContainer && WebAppKind != webAppLinux && webAppKind != functionAppLinux && Package NotEndsWith .war`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
A standard `Web.config` will be generated and deployed to Azure App Service if the application does not have one. The values in `web.config` can be edited and vary based on the application framework. For example, for `node.js` applications, `web.config` will have a Startup file and iis_node module values. This edit feature is only for the generated `web.config`. Learn more about [Azure App Service Deployment](https://go.microsoft.com/fwlink/?linkid=843471).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2022.1"

**`WebConfigParameters`** - **Generate web.config parameters for Python, Node.js, Go and Java apps**<br>
`string`. Optional. Use when `WebAppKind != webAppContainer && WebAppkind != functionAppContainer && WebAppKind != webAppLinux && webAppKind != functionAppLinux && Package NotEndsWith .war`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
A standard `Web.config` will be generated and deployed to Azure App Service if the application does not have one. The values in `web.config` can be edited and vary based on the application framework. For example, for `node.js` applications, `web.config` will have a Startup file and iis_node module values. This edit feature is only for the generated `web.config`. Learn more about [Azure App Service Deployment](https://go.microsoft.com/fwlink/?linkid=843471).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AppSettings"::: -->
:::moniker range=">=azure-pipelines-2019"

**`AppSettings`** - **App settings**<br>
`string`. Optional. Use when `ConnectionType = AzureRM`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Edits web app application settings using the syntax `-key value`. Values containing spaces must be enclosed in double quotes. Examples: `-Port 5000 -RequestTimeout 5000` and `-WEBSITE_TIME_ZONE "Eastern Standard Time"`. To provide two or more key values, the key values must be separated by a space. Example: `-key1 "Value1" -Key2 "Value2"`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ConfigurationSettings"::: -->
:::moniker range=">=azure-pipelines-2019"

**`ConfigurationSettings`** - **Configuration settings**<br>
`string`. Optional. Use when `ConnectionType = AzureRM`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Edits web app configuration settings using the syntax `-key value`. Values containing spaces must be enclosed in double quotes. Example: `-phpVersion 5.6 -linuxFxVersion node|6.11`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="enableCustomDeployment"::: -->
:::moniker range="=azure-pipelines"

**`enableCustomDeployment`** - **Select deployment method**<br>
Input alias: `UseWebDeploy`. `boolean`. Optional. Use when `ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppKind != webAppHyperVContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If unchecked or false, the task auto-detects the best deployment method based on the app type, package format, and other parameters. Check this option in the task assistant to view the supported deployment methods, and choose one for deploying your app.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2022.1"

**`enableCustomDeployment`** - **Select deployment method**<br>
Input alias: `UseWebDeploy`. `boolean`. Optional. Use when `ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If unchecked or false, the task auto-detects the best deployment method based on the app type, package format, and other parameters. Check this option in the task assistant to view the supported deployment methods, and choose one for deploying your app.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DeploymentType"::: -->
:::moniker range="=azure-pipelines"

**`DeploymentType`** - **Deployment method**<br>
`string`. Required when `UseWebDeploy == true && ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppKind != webAppHyperVContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar`. Allowed values: `webDeploy` (Web Deploy), `zipDeploy` (Zip Deploy), `runFromZip` (Run From Package). Default value: `webDeploy`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Determines the deployment method for the app.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2022.1"

**`DeploymentType`** - **Deployment method**<br>
`string`. Required when `UseWebDeploy == true && ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar`. Allowed values: `webDeploy` (Web Deploy), `zipDeploy` (Zip Deploy), `runFromZip` (Run From Package). Default value: `webDeploy`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Determines the deployment method for the app.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="TakeAppOfflineFlag"::: -->
:::moniker range="=azure-pipelines"

**`TakeAppOfflineFlag`** - **Take App Offline**<br>
`boolean`. Optional. Use when `UseWebDeploy == true && DeploymentType != runFromZip && ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppKind != webAppHyperVContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify this option to take the Azure App Service offline by placing an `app_offline.htm` file in the root directory before the synchronization operation begins. The file will be removed after the synchronization completes successfully.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2022.1"

**`TakeAppOfflineFlag`** - **Take App Offline**<br>
`boolean`. Optional. Use when `UseWebDeploy == true && DeploymentType != runFromZip && ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify this option to take the Azure App Service offline by placing an `app_offline.htm` file in the root directory before the synchronization operation begins. The file will be removed after the synchronization completes successfully.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SetParametersFile"::: -->
:::moniker range="=azure-pipelines"

**`SetParametersFile`** - **SetParameters file**<br>
`string`. Optional. Use when `UseWebDeploy == true && DeploymentType == webDeploy && ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppKind != webAppHyperVContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The location of the `SetParameters.xml` file to use.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2022.1"

**`SetParametersFile`** - **SetParameters file**<br>
`string`. Optional. Use when `UseWebDeploy == true && DeploymentType == webDeploy && ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The location of the `SetParameters.xml` file to use.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="RemoveAdditionalFilesFlag"::: -->
:::moniker range="=azure-pipelines"

**`RemoveAdditionalFilesFlag`** - **Remove additional files at destination**<br>
`boolean`. Optional. Use when `UseWebDeploy == true && DeploymentType == webDeploy && ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppKind != webAppHyperVContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify 'true' to delete files on the Azure App Service that have no matching files in the App Service package or folder. This will also remove all files related to any extension installed on this Azure App Service. To prevent this, select the `Exclude files from App_Data folder` checkbox.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2022.1"

**`RemoveAdditionalFilesFlag`** - **Remove additional files at destination**<br>
`boolean`. Optional. Use when `UseWebDeploy == true && DeploymentType == webDeploy && ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify 'true' to delete files on the Azure App Service that have no matching files in the App Service package or folder. This will also remove all files related to any extension installed on this Azure App Service. To prevent this, select the `Exclude files from App_Data folder` checkbox.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ExcludeFilesFromAppDataFlag"::: -->
:::moniker range="=azure-pipelines"

**`ExcludeFilesFromAppDataFlag`** - **Exclude files from the App_Data folder**<br>
`boolean`. Optional. Use when `UseWebDeploy == true && DeploymentType == webDeploy && ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppKind != webAppHyperVContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the option to prevent files in the `App_Data` folder from being deployed to/deleted from the Azure App Service.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2022.1"

**`ExcludeFilesFromAppDataFlag`** - **Exclude files from the App_Data folder**<br>
`boolean`. Optional. Use when `UseWebDeploy == true && DeploymentType == webDeploy && ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the option to prevent files in the `App_Data` folder from being deployed to/deleted from the Azure App Service.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AdditionalArguments"::: -->
:::moniker range="=azure-pipelines"

**`AdditionalArguments`** - **Additional arguments**<br>
`string`. Optional. Use when `UseWebDeploy == true && DeploymentType == webDeploy && ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppKind != webAppHyperVContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar`. Default value: `-retryAttempts:6 -retryInterval:10000`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Additional Web Deploy arguments following the syntax `-key:value`. These will be applied when deploying the Azure App Service. Examples: `-disableLink:AppPoolExtension -disableLink:ContentExtension`. Learn more about [Web Deploy Operation Settings](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd569089(v=ws.10)).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2022.1"

**`AdditionalArguments`** - **Additional arguments**<br>
`string`. Optional. Use when `UseWebDeploy == true && DeploymentType == webDeploy && ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar`. Default value: `-retryAttempts:6 -retryInterval:10000`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Additional Web Deploy arguments following the syntax `-key:value`. These will be applied when deploying the Azure App Service. Examples: `-disableLink:AppPoolExtension -disableLink:ContentExtension`. Learn more about [Web Deploy Operation Settings](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd569089(v=ws.10)).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="RenameFilesFlag"::: -->
:::moniker range="=azure-pipelines"

**`RenameFilesFlag`** - **Rename locked files**<br>
`boolean`. Optional. Use when `UseWebDeploy == true && DeploymentType == webDeploy && ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppKind != webAppHyperVContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the default value to enable the msdeploy flag `MSDEPLOY_RENAME_LOCKED_FILES=1` in Azure App Service application settings. If set, the option enables msdeploy to rename files that are locked during app deployment.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2022.1"

**`RenameFilesFlag`** - **Rename locked files**<br>
`boolean`. Optional. Use when `UseWebDeploy == true && DeploymentType == webDeploy && ConnectionType = AzureRM && WebAppKind != webAppLinux && WebAppKind != webAppContainer && WebAppkind != functionAppContainer && webAppKind != functionAppLinux && WebAppKind != "" && Package NotEndsWith .war && Package NotEndsWith .jar`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the default value to enable the msdeploy flag `MSDEPLOY_RENAME_LOCKED_FILES=1` in Azure App Service application settings. If set, the option enables msdeploy to rename files that are locked during app deployment.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="enableXmlTransform"::: -->
:::moniker range="=azure-pipelines"

**`enableXmlTransform`** - **XML transformation**<br>
Input alias: `XmlTransformation`. `boolean`. Optional. Use when `WebAppKind != webAppContainer && WebAppKind != webAppHyperVContainer && WebAppkind != functionAppContainer && WebAppKind != webAppLinux && webAppKind != functionAppLinux && Package NotEndsWith .war`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The config transforms will be run for `*.Release.config` and `*.<EnvironmentName>.config` on the `*.config file`. Configuration transformations run before variable substitution. [XML transformations](/azure/devops/pipelines/tasks/transforms-variable-substitution#xml-transformation) are supported only for the Windows platform.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2022.1"

**`enableXmlTransform`** - **XML transformation**<br>
Input alias: `XmlTransformation`. `boolean`. Optional. Use when `WebAppKind != webAppContainer && WebAppkind != functionAppContainer && WebAppKind != webAppLinux && webAppKind != functionAppLinux && Package NotEndsWith .war`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The config transforms will be run for `*.Release.config` and `*.<EnvironmentName>.config` on the `*.config file`. Configuration transformations run before variable substitution. [XML transformations](/azure/devops/pipelines/tasks/transforms-variable-substitution#xml-transformation) are supported only for the Windows platform.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="enableXmlVariableSubstitution"::: -->
:::moniker range="=azure-pipelines"

**`enableXmlVariableSubstitution`** - **XML variable substitution**<br>
Input alias: `XmlVariableSubstitution`. `boolean`. Optional. Use when `WebAppKind != webAppContainer && WebAppKind != webAppHyperVContainer && WebAppkind != functionAppContainer && WebAppKind != webAppLinux && webAppKind != functionAppLinux && Package NotEndsWith .war`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Variables defined in the build or release pipeline will be matched against the key or name entries in the `configSections`, `appSettings`, `applicationSettings`, and `connectionStrings` sections of any configuration file and `parameters.xml` file. Variable substitution runs after configuration transformations.

If the same variables are defined in the release pipeline and in the stage, the stage variables will supersede the release pipeline variables. Learn more about [XML variable substitution]](/azure/devops/pipelines/tasks/transforms-variable-substitution#xml-variable-substitution).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2022.1"

**`enableXmlVariableSubstitution`** - **XML variable substitution**<br>
Input alias: `XmlVariableSubstitution`. `boolean`. Optional. Use when `WebAppKind != webAppContainer && WebAppkind != functionAppContainer && WebAppKind != webAppLinux && webAppKind != functionAppLinux && Package NotEndsWith .war`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Variables defined in the build or release pipeline will be matched against the key or name entries in the `configSections`, `appSettings`, `applicationSettings`, and `connectionStrings` sections of any configuration file and `parameters.xml` file. Variable substitution runs after configuration transformations.

If the same variables are defined in the release pipeline and in the stage, the stage variables will supersede the release pipeline variables. Learn more about [XML variable substitution]](/azure/devops/pipelines/tasks/transforms-variable-substitution#xml-variable-substitution).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="JSONFiles"::: -->
:::moniker range="=azure-pipelines"

**`JSONFiles`** - **JSON variable substitution**<br>
`string`. Optional. Use when `WebAppKind != webAppContainer && WebAppKind != webAppHyperVContainer && WebAppkind != functionAppContainer && WebAppKind != webAppLinux && webAppKind != functionAppLinux && Package NotEndsWith .war`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provides a newline-separated list of JSON files to substitute the variable values. File names must be relative to the root folder. To substitute JSON variables that are nested or hierarchical, specify them using `JSONPath` expressions. For example, to replace the value of `ConnectionString` in the sample below, define a variable named `Data.DefaultConnection.ConnectionString` in the build or release pipeline (or release pipelines stage).

```json
{
  "Data": {
    "DefaultConnection": {
      "ConnectionString": "Server=(localdb)\SQLEXPRESS;Database=MyDB;Trusted_Connection=True"
    }
  }
}
```

A variable substitution runs after configuration transformations. Note: Build and release pipeline variables are excluded from substitution. Learn more about [JSON variable substitution](/azure/devops/pipelines/tasks/transforms-variable-substitution#json-variable-substitution).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2022.1"

**`JSONFiles`** - **JSON variable substitution**<br>
`string`. Optional. Use when `WebAppKind != webAppContainer && WebAppkind != functionAppContainer && WebAppKind != webAppLinux && webAppKind != functionAppLinux && Package NotEndsWith .war`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provides a newline-separated list of JSON files to substitute the variable values. File names must be relative to the root folder. To substitute JSON variables that are nested or hierarchical, specify them using `JSONPath` expressions. For example, to replace the value of `ConnectionString` in the sample below, define a variable named `Data.DefaultConnection.ConnectionString` in the build or release pipeline (or release pipelines stage).

```json
{
  "Data": {
    "DefaultConnection": {
      "ConnectionString": "Server=(localdb)\SQLEXPRESS;Database=MyDB;Trusted_Connection=True"
    }
  }
}
```

A variable substitution runs after configuration transformations. Note: Build and release pipeline variables are excluded from substitution. Learn more about [JSON variable substitution](/azure/devops/pipelines/tasks/transforms-variable-substitution#json-variable-substitution).
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

<!-- :::item name="AppServiceApplicationUrl"::: -->
**`AppServiceApplicationUrl`**<br><!-- :::editable-content name="Value"::: -->
Application URL of the selected App Service.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

* [Prerequisites for the task](#prerequisites-for-the-task)
* [Usage notes](#usage-notes)
* [Deployment methods](#deployment-methods)
* [Troubleshooting](#troubleshooting)
* [FAQs](#faqs)

Use this task to deploy to a range of App Services on Azure.
The task works on cross-platform agents running Windows, Linux, or Mac 
and uses several different [underlying deployment technologies](#deployment-methods).

The task works for [ASP.NET](/azure/devops/pipelines/apps/aspnet/build-aspnet-4),
[ASP.NET Core](/azure/devops/pipelines/ecosystems/dotnet-core),
[PHP](/azure/devops/pipelines/ecosystems/php),
[Java](/azure/devops/pipelines/ecosystems/java),
[Python](/azure/devops/pipelines/ecosystems/python),
[Go](/azure/devops/pipelines/ecosystems/go), and
[Node.js](https://www.visualstudio.com/docs/release/examples/nodejs/node-to-azure-webapps) based web applications.

The task can be used to deploy to a range of Azure App Services such as:

* [Web Apps on both Windows and Linux](/azure/app-service/overview)
* [Web Apps for Containers](/azure/app-service/containers/app-service-linux-intro)
* [Function Apps on both Windows and Linux](/azure/azure-functions/)
* [Function Apps for Containers](/azure/azure-functions/)
* [WebJobs](https://azure.microsoft.com/blog/webjobs-goes-into-full-production/)
* Apps configured under [Azure App Service Environments](/azure/app-service/environment/intro)

### Prerequisites for the task

The following prerequisites must be set up in the target machine(s) for the task to work correctly.

* **App Service instance**. The task is used to deploy a Web App project or Azure Function project to an existing Azure App Service instance, which must exist before the task runs.
  The App Service instance can be created from the [Azure portal](https://azure.microsoft.com/documentation/videos/azure-app-service-web-apps-with-yochay-kiriaty/)
  and [configured](/azure/app-service/configure-common) there.
  Alternatively, the [Azure PowerShell task](https://github.com/microsoft/azure-pipelines-tasks/tree/master/Tasks/AzurePowerShellV2) can be used to run
  [AzureRM PowerShell scripts](/powershell/module/azurerm.websites) to provision and configure the Web App.

* **Azure Subscription**. To deploy to Azure, an Azure subscription must be [linked to the pipeline](/azure/devops/pipelines/library/connect-to-azure).
  The task does not work with the Azure Classic service connection, and it will not list these connections in the settings of the task.

### Usage notes

* The task works with the [Azure Resource Manager APIs](/rest/api/resources/) only.
* To ignore SSL errors, define a variable named `VSTS_ARM_REST_IGNORE_SSL_ERRORS` with value `true` in the the pipeline. If you are deploying to a slot configured to auto-swap, the swap will fail unless you set `SCM_SKIP_SSL_VALIDATION` or `SCM_SKIP_ASE_SSL_VALIDATION` to `1` in the app services configuration settings.
* For .NET apps targeting Web App on Windows, avoid deployment failure with the error `ERROR_FILE_IN_USE` by ensuring that
  **Rename locked files** and **Take App Offline** settings are enabled. For zero downtime deployment, use the slot swap option.
* When deploying to an App Service that has Application Insights configured, and you have enabled **Remove additional files at destination**,
  ensure you also enable **Exclude files from the App\_Data folder** in order to maintain the Application insights extension in
  a safe state. This is required because the Application Insights continuous web job is installed into the App\_Data folder.

### Deployment methods

Several deployment methods are available in this task. Web Deploy (msdeploy.exe) is the default.
To change the deployment option, expand **Additional Deployment Options** and enable **Select deployment method**
to choose from additional package-based deployment options.

Based on the type of Azure App Service and agent, the task chooses a suitable deployment technology. The different deployment technologies used by the task are:

* [Web Deploy](#web-deploy)
* [Kudu REST APIs](#kudu-rest-apis)
* [Container Registry](#container-registry)
* [Zip Deploy](#zip-deploy)
* [Run From Package](#run-from-package)
* [War Deploy](#war-deploy)

By default, the task tries to select the appropriate deployment technology
based on the input package type, App Service type, and agent operating system.

### Auto Detect Logic

For windows based agents.

| App Service type | Package type | Deployment Method |
|--|--|--|
| WebApp on Linux or Function App on Linux | Folder/Zip/jar</br>War | Zip Deploy</br>War Deploy|
|WebApp for Containers (Linux) or Function App for Containers (Linux)| Update the App settings | NA |
|WebApp on Windows, Function App on Windows, API App, or Mobile App | War </br>Jar</br>MsBuild package type or deploy to virtual application</br></br></br>Folder/Zip | War Deploy</br>Zip Deploy</br>Web Deploy</br></br>`if postDeploymentScript == true, Zip Deploy`</br>`else, Run From Package` |

On non-Windows agents (for any App Service type), the task relies on [Kudu REST APIs](#kudu-rest-apis) to deploy the app.

#### Web Deploy

[Web Deploy](https://www.iis.net/downloads/microsoft/web-deploy) (msdeploy.exe) can be used to deploy a Web App on Windows or a Function App to the Azure App Service using a Windows agent. Web Deploy is feature-rich and offers options such as:

* **Rename locked files:** Rename any file that is still in use by the web server by enabling the msdeploy flag `MSDEPLOY\_RENAME\_LOCKED\_FILES=1` in the Azure App Service settings. This option, if set, enables msdeploy to rename files that are locked during app deployment.

* **Remove additional files at destination:** Deletes files in the Azure App Service that have no matching files in the App Service artifact package or folder being deployed.

* **Exclude files from the App\_Data folder:** Prevent files in the App\_Data folder (in the artifact package/folder being deployed) being deployed to the Azure App Service

* **Additional Web Deploy arguments:** Arguments that will be applied when deploying the Azure App Service.
  Example: `-disableLink:AppPoolExtension -disableLink:ContentExtension`.
  For more examples of Web Deploy operation settings, see [Web Deploy Operation Settings](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd569089(v=ws.10)).

Install Web Deploy on the agent using the [Microsoft Web Platform Installer](https://www.microsoft.com/web/gallery/install.aspx?appid=wdeploynosmo). Web Deploy 3.5 must be installed without the bundled SQL support. There is no need to choose any custom settings when installing Web Deploy. Web Deploy is installed at `C:/Program Files (x86)/IIS/Microsoft Web Deploy V3`.


#### Kudu REST APIs

[Kudu REST APIs](https://github.com/projectkudu/kudu/wiki/REST-API) work on both Windows and Linux automation agents when the target is a
Web App on Windows, Web App on Linux (built-in source), or Function App. The task uses Kudu to copy files to the Azure App service.


#### Container Registry

Works on both Windows and Linux automation agents when the target is a Web App for Containers. The task updates the app by setting the appropriate
container registry, repository, image name, and tag information. You can also use the task to pass a startup command for the container image.


#### Zip Deploy

Expects a .zip deployment package and deploys the file contents to the **wwwroot** folder of the App Service or Function App in Azure.
This option overwrites all existing contents in the **wwwroot** folder. For more information, see
[Zip deployment for Azure Functions](/azure/azure-functions/deployment-zip-push).

#### Run From Package

Expects the same deployment package as Zip Deploy. However, instead of deploying files to the **wwwroot** folder, the entire package is
mounted by the Functions runtime and files in the **wwwroot** folder become read-only. For more information, see
[Run your Azure Functions from a package file](/azure/azure-functions/run-functions-from-deployment-package).

#### War Deploy

Expects a .war deployment package and deploys the file content to the **wwwroot** folder or **webapps** folder of the App Service in Azure.

### Troubleshooting

:::moniker range=">azure-pipelines-2022.1"

[!INCLUDE [rm-web-app-deployment-authentication](./includes/rm-web-app-deployment-authentication.md)]

:::moniker-end

[!INCLUDE [rm-app-service-troubleshoot-shared](./includes/rm-app-service-troubleshoot-shared.md)]

[!INCLUDE [rm-webapp-functionapp-troubleshoot-shared](./includes/rm-webapp-functionapp-troubleshoot-shared.md)]

#### Web app deployment on Windows is successful but the app is not working

This may be because web.config is not present in your app. You can either add a web.config file to your source or auto-generate one using the File Transforms and Variable Substitution Options of the task.

* Click on the task and go to Generate web.config parameters for Python, Node.js, Go and Java apps.

    :::image type="content" source="media/azure-rm-web-app-deployment-01.png" alt-text="Screenshot of the Generate web.config parameters dialog.":::

* Click on the more button Generate web.config parameters for Python, Node.js, Go and Java apps to edit the parameters.

    :::image type="content" source="media/azure-rm-web-app-deployment-02.png" alt-text="Screenshot of Application framework drop-down.":::

* Select your application type from the drop down.
* Click on OK. This will populate web.config parameters required to generate web.config.

> [!NOTE]
> This section is deprecated and has been replaced with the [File Transform](file-transform-v2.md) task.

#### ERROR_FILE_IN_USE

When deploying .NET apps to Web App on Windows, deployment may fail with error code *ERROR_FILE_IN_USE*. To resolve the error, ensure *Rename locked files* and *Take App Offline* options are enabled in the task. For zero downtime deployments, use slot swap.

You can also use *Run From Package deployment* method to avoid resource locking.

#### Web Deploy Error

If you are using web deploy to deploy your app, in some error scenarios Web Deploy will show an error code in the log. To troubleshoot a web deploy error, see [Web Deploy error codes](/iis/publish/troubleshooting-web-deploy/web-deploy-error-codes).

### Web app deployment on App Service Environment (ASE) is not working
* Ensure that the Azure DevOps build agent is on the same VNET (subnet can be different) as the Internal Load Balancer (ILB) of  ASE. This will enable the agent to pull code from Azure DevOps and deploy to ASE. 
* If you are using Azure DevOps, the agent doesn't need to be accessible from the internet but needs only outbound access to connect to Azure DevOps Service.
* If you are using TFS/Azure DevOps Server deployed in a Virtual Network, the agent can be completely isolated.
* The build agent must be configured with the DNS configuration of the Web App it needs to deploy to. Since the private resources in the Virtual Network don't have entries in Azure DNS, this needs to be added to the hosts file on the agent machine.
* If a self-signed certificate is used for the ASE configuration, the `-allowUntrusted` option needs to be set in the deploy task for MSDeploy. It is also recommended to set the variable `VSTS_ARM_REST_IGNORE_SSL_ERRORS` to true. If a certificate from a certificate authority is used for ASE configuration, this should not be necessary. If you are deploying to a slot configured to auto-swap, the swap will fail unless you set `SCM_SKIP_SSL_VALIDATION` or `SCM_SKIP_ASE_SSL_VALIDATION` to `1` in the app services configuration settings.

### FAQs

#### What's the difference between the `AzureWebApp` and `AzureRmWebAppDeployment` tasks?

The [Azure Web App task](./azure-web-app-v1.md) (`AzureWebApp`) is the simplest way to deploy to an Azure Web App. By default, your deployment happens to the root application in the Azure Web App.

The [Azure App Service Deploy task (`AzureRmWebAppDeployment`)](./azure-rm-web-app-deployment-v4.md) can handle more custom scenarios, such as:

- [Modify configuration settings](/azure/app-service/deploy-azure-pipelines#example-make-variable-substitutions) inside web packages and XML parameters files.
- [Deploy with Web Deploy](/azure/app-service/deploy-azure-pipelines#example-deploy-using-web-deploy), if you're used to the IIS deployment process.
- [Deploy to virtual applications](/azure/app-service/deploy-azure-pipelines#example-deploy-to-a-virtual-application).
- Deploy to other app types, like Container apps, Function apps, WebJobs, or API and Mobile apps.

> [!NOTE]  
> File transforms and variable substitution are also supported by the separate [File Transform task](./file-transform-v2.md) for use in Azure Pipelines. You can use the File Transform task to apply file transformations and variable substitutions on any configuration and parameters files.

[!INCLUDE [rm-app-service-FAQs-shared](./includes/rm-app-service-faqs-shared.md)]
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

* [Deploy to specific app type](#deploy-to-specific-app-type)
* [Deploy to Azure Web App Linux container](#deploy-to-azure-web-app-linux-container)
* [Deploy a web app to a Windows App Service across deployment slots](#deploy-a-web-app-to-a-windows-app-service-across-deployment-slots)
* [Sample Post deployment script](#sample-post-deployment-script)

### Deploy to specific app type

To deploy to a specific app type, set `appType` to any of the following accepted values: `webApp` (Web App on Windows), `webAppLinux` (Web App on Linux), `webAppContainer` (Web App for Containers - Linux), `functionApp` (Function App on Windows), `functionAppLinux` (Function App on Linux), `functionAppContainer` (Function App for Containers - Linux), `apiApp` (API App), `mobileApp` (Mobile App). If not mentioned, `webApp` is taken as the default value.

To enable any advanced deployment options, add the parameter `enableCustomDeployment: true` and include the following parameters as needed.

```yml
# deploymentMethod: 'runFromPackage' # supports zipDeploy as well
    # appOffline: boolean    # Not applicable for 'runFromPackage'
    # setParametersFile: string
    # removeAdditionalFilesFlag: boolean
    # additionalArguments: string
```

### Deploy to Azure Web App Linux container

The following YAML example deploys to an Azure Web App container (Linux).

```yml
pool:
  vmImage: ubuntu-latest

variables:
  azureSubscriptionEndpoint: Contoso
  DockerNamespace: contoso.azurecr.io
  DockerRepository: aspnetcore
  WebAppName: containersdemoapp

steps:

- task: AzureRMWebAppDeployment@4
  displayName: Azure App Service Deploy
  inputs:
    appType: webAppContainer
    ConnectedServiceName: $(azureSubscriptionEndpoint)
    WebAppName: $(WebAppName)
    DockerNamespace: $(DockerNamespace)
    DockerRepository: $(DockerRepository)
    DockerImageTag: $(Build.BuildId)
```

### Deploy a web app to a Windows App Service across deployment slots

The following example deploys a web app to a Windows App Service across deployment slots.

```yml
pool:
  vmImage: 'windows-latest'

variables:
  solution: '**/*.sln'
  buildPlatform: 'Any CPU'
  buildConfiguration: 'Release'

stages:
 - stage: DeployDevStage
    displayName: 'Deploy App to Dev Slot'
    jobs:
      - job:  DeployApp
        displayName: 'Deploy App'
        steps:
        - task: DownloadPipelineArtifact@2
          inputs:
            buildType: 'current'
            artifactName: 'drop'
            targetPath: '$(System.DefaultWorkingDirectory)'
        - task: AzureRmWebAppDeployment@4
          inputs:
            ConnectionType: 'AzureRM'
            azureSubscription: 'Fabrikam Azure Subscription - PartsUnlimited'
            appType: 'webApp'
            WebAppName: 'partsunlimited'
            deployToSlotOrASE: true
            ResourceGroupName: 'rgPartsUnlimited'
            SlotName: 'Dev'
            packageForLinux: '$(System.DefaultWorkingDirectory)/**/*.zip'

  - stage: DeployStagingStage
    displayName: 'Deploy App to Staging Slot'
    dependsOn: DeployDevStage
    jobs:
      - job:  DeployApp
        displayName: 'Deploy App'
        steps:
        - task: DownloadPipelineArtifact@2
          inputs:
            buildType: 'current'
            artifactName: 'drop'
            targetPath: '$(System.DefaultWorkingDirectory)'
        - task: AzureRmWebAppDeployment@4
          inputs:
            appType: webApp
            ConnectionType: AzureRM            
            ConnectedServiceName: 'Fabrikam Azure Subscription - PartsUnlimited'
            ResourceGroupName: 'rgPartsUnlimited'
            WebAppName: 'partsunlimited'
            Package: '$(System.DefaultWorkingDirectory)/**/*.zip'
            deployToSlotOrASE: true
            SlotName: 'staging'
```

### Sample Post deployment script

The task provides an option to customize the deployment by providing a script that will run on the Azure App Service after the app's artifacts have been successfully copied to the App Service. You can choose to provide either an inline deployment script or the path and name of a script file in your artifact folder.

This is very useful when you want to restore your application dependencies directly on the App Service. Restoring packages for Node, PHP, and  python apps helps to avoid timeouts when the application dependency results in a large artifact being copied over from the agent to the Azure App Service.

An example of a deployment script is:

```ps
@echo off
if NOT exist requirements.txt (
 echo No Requirements.txt found.
 EXIT /b 0
)
if NOT exist "$(PYTHON_EXT)/python.exe" (
 echo Python extension not available >&2
 EXIT /b 1
)
echo Installing dependencies
call "$(PYTHON_EXT)/python.exe" -m pip install -U setuptools
if %errorlevel% NEQ 0 (
 echo Failed to install setuptools >&2
 EXIT /b 1
)
call "$(PYTHON_EXT)/python.exe" -m pip install -r requirements.txt
if %errorlevel% NEQ 0 (
 echo Failed to install dependencies>&2
 EXIT /b 1
)
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range=">=azure-pipelines-2019"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.104.1 or greater |
| Task category | Deploy |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

* This task is open source [on GitHub](https://github.com/Microsoft/azure-pipelines-tasks). Feedback and contributions are welcome.
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
