---
title: AzureRmWebAppDeployment@3 - Azure App Service deploy v3 task
description: Deploy to Azure App Service a web, mobile, or API app using Docker, Java, .NET, .NET Core, Node.js, PHP, Python, or Ruby (task version 3).
ms.date: 09/26/2023
monikerRange: "<=azure-pipelines"
---

# AzureRmWebAppDeployment@3 - Azure App Service deploy v3 task

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
Update Azure App Services on Windows, Web App on Linux with built-in images or docker containers, ASP.NET, .NET Core, PHP, Python or Node.js based Web applications, Function Apps, Mobile Apps, API applications, and Web Jobs using Web Deploy/[Kudu REST APIs](https://github.com/projectkudu/kudu/wiki/REST-API).
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2018"

<!-- :::editable-content name="description"::: -->
Update Azure WebApp Services On Windows, Web App on Linux with built-in images or docker containers, ASP.NET, .NET Core, PHP, Python or Node based Web applications, Function Apps, Mobile Apps, Api applications, and Web Jobs using Web Deploy/[Kudu REST APIs](https://github.com/projectkudu/kudu/wiki/REST-API).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# Azure App Service deploy v3
# Deploy to Azure App Service a web, mobile, or API app using Docker, Java, .NET, .NET Core, Node.js, PHP, Python, or Ruby.
- task: AzureRmWebAppDeployment@3
  inputs:
    azureSubscription: # string. Alias: ConnectedServiceName. Required. Azure subscription. 
    appType: 'app' # 'app' | 'applinux' | 'functionapp' | 'api' | 'mobileapp'. Alias: WebAppKind. Required. App type. Default: app.
    WebAppName: # string. Required. App Service name. 
    #DeployToSlotFlag: false # boolean. Optional. Use when WebAppKind != "". Deploy to slot. Default: false.
    #ResourceGroupName: # string. Required when DeployToSlotFlag = true. Resource group. 
    #SlotName: # string. Required when DeployToSlotFlag = true. Slot. 
    #ImageSource: 'Registry' # 'Registry' | 'Builtin'. Optional. Use when WebAppKind = applinux || WebAppKind = linux. Image Source. Default: Registry.
    #AzureContainerRegistry: # string. Required when ImageSource = AzureContainerRegistry. Registry. 
    #AzureContainerRegistryLoginServer: # string. Optional. Use when ImageSource = invalidimagesource. Registry Login Server Name. 
    #AzureContainerRegistryImage: # string. Required when ImageSource = AzureContainerRegistry. Image. 
    #AzureContainerRegistryTag: # string. Optional. Use when ImageSource = AzureContainerRegistry. Tag. 
    #DockerRepositoryAccess: 'public' # 'private' | 'public'. Required when ImageSource = invalidImage. Repository Access. Default: public.
    #dockerRegistryConnection: # string. Alias: RegistryConnectedServiceName. Required when DockerRepositoryAccess = private || ImageSource = PrivateRegistry. Registry Connection. 
    #PrivateRegistryImage: # string. Required when ImageSource = PrivateRegistry. Image. 
    #PrivateRegistryTag: # string. Optional. Use when ImageSource = PrivateRegistry. Tag. 
    #DockerNamespace: # string. Required when WebAppKind != app && WebAppKind != functionapp && WebAppKind != api && WebAppKind != mobileapp && ImageSource  = Registry. Registry or Namespace. 
    #DockerRepository: # string. Required when WebAppKind != app && WebAppKind != functionapp && WebAppKind != api && WebAppKind != mobileapp && ImageSource  = Registry. Image. 
    #DockerImageTag: # string. Optional. Use when WebAppKind != app && WebAppKind != functionapp && WebAppKind != api && WebAppKind != mobileapp && ImageSource  = Registry. Tag. 
    #VirtualApplication: # string. Optional. Use when WebAppKind != linux && WebAppKind != applinux && WebAppKind != "". Virtual application. 
    #Package: '$(System.DefaultWorkingDirectory)/**/*.zip' # string. Required when WebAppKind != linux && WebAppKind != applinux &&  WebAppKind != "". Package or folder. Default: $(System.DefaultWorkingDirectory)/**/*.zip.
    #packageForLinux: '$(System.DefaultWorkingDirectory)/**/*.zip' # string. Alias: BuiltinLinuxPackage. Required when WebAppKind != app && WebAppKind != functionapp && WebAppKind != api && WebAppKind != mobileapp && ImageSource = Builtin. Package or folder. Default: $(System.DefaultWorkingDirectory)/**/*.zip.
    #RuntimeStack: # string. Required when WebAppKind != app && WebAppKind != functionapp && WebAppKind != api && WebAppKind != mobileapp && ImageSource = Builtin. Runtime Stack. 
    #StartupCommand: # string. Optional. Use when WebAppKind = applinux || WebAppKind = linux. Startup command. 
  # Output
    #WebAppUri: # string. Optional. Use when WebAppKind != "". App Service URL. 
  # Post Deployment Action
    #ScriptType: # 'Inline Script' | 'File Path'. Optional. Use when WebAppKind != "". Deployment script type. 
    #InlineScript: ':: You can provide your deployment commands here. One command per line.' # string. Required when ScriptType == Inline Script && WebAppKind != "". Inline Script. Default: :: You can provide your deployment commands here. One command per line..
    #ScriptPath: # string. Required when ScriptType == File Path && WebAppKind != "". Deployment script path. 
  # File Transforms & Variable Substitution Options
    #GenerateWebConfig: false # boolean. Optional. Use when WebAppKind != linux && WebAppKind != applinux && WebAppKind != "" && Package NotEndsWith .war. Generate Web.config. Default: false.
    #WebConfigParameters: # string. Required when GenerateWebConfig == true && WebAppKind != linux && WebAppKind != applinux && WebAppKind != "" && Package NotEndsWith .war. Web.config parameters. 
    #enableXmlTransform: false # boolean. Alias: XmlTransformation. Optional. Use when WebAppKind != linux && WebAppKind != applinux && WebAppKind != "" && Package NotEndsWith .war. XML transformation. Default: false.
    #enableXmlVariableSubstitution: false # boolean. Alias: XmlVariableSubstitution. Optional. Use when WebAppKind != linux && WebAppKind != applinux && WebAppKind != "" && Package NotEndsWith .war. XML variable substitution. Default: false.
    #JSONFiles: # string. Optional. Use when WebAppKind != linux && WebAppKind != applinux && WebAppKind != "" && Package NotEndsWith .war. JSON variable substitution. 
  # Application and Configuration Settings
    #AppSettings: # string. App settings. 
    #ConfigurationSettings: # string. Configuration settings. 
  # Additional Deployment Options
    #TakeAppOfflineFlag: false # boolean. Optional. Use when WebAppKind != linux && WebAppKind != applinux && WebAppKind != "". Take App Offline. Default: false.
    #UseWebDeploy: false # boolean. Optional. Use when WebAppKind != linux && WebAppKind != applinux && WebAppKind != "". Publish using Web Deploy. Default: false.
    #SetParametersFile: # string. Optional. Use when UseWebDeploy == true && WebAppKind != linux && WebAppKind != applinux && WebAppKind != "". SetParameters file. 
    #RemoveAdditionalFilesFlag: false # boolean. Optional. Use when UseWebDeploy == true && WebAppKind != linux && WebAppKind != applinux && WebAppKind != "". Remove additional files at destination. Default: false.
    #ExcludeFilesFromAppDataFlag: false # boolean. Optional. Use when UseWebDeploy == true && WebAppKind != linux && WebAppKind != applinux && WebAppKind != "". Exclude files from the App_Data folder. Default: false.
    #AdditionalArguments: # string. Optional. Use when UseWebDeploy == true && WebAppKind != linux && WebAppKind != applinux && WebAppKind != "". Additional arguments. 
    #RenameFilesFlag: false # boolean. Optional. Use when UseWebDeploy == true && WebAppKind != linux && WebAppKind != applinux && WebAppKind != "". Rename locked files. Default: false.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Azure App Service Deploy v3
# Update Azure App Services on Windows, Web App on Linux with built-in images or Docker containers, ASP.NET, .NET Core, PHP, Python or Node.js based Web applications, Function Apps, Mobile Apps, API applications, Web Jobs using Web Deploy / Kudu REST APIs.
- task: AzureRmWebAppDeployment@3
  inputs:
    azureSubscription: # string. Alias: ConnectedServiceName. Required. Azure subscription. 
    appType: 'app' # 'app' | 'applinux' | 'functionapp' | 'api' | 'mobileapp'. Alias: WebAppKind. Required. App type. Default: app.
    WebAppName: # string. Required. App Service name. 
    #DeployToSlotFlag: false # boolean. Optional. Use when WebAppKind != "". Deploy to slot. Default: false.
    #ResourceGroupName: # string. Required when DeployToSlotFlag = true. Resource group. 
    #SlotName: # string. Required when DeployToSlotFlag = true. Slot. 
    #ImageSource: 'Registry' # 'Registry' | 'Builtin'. Optional. Use when WebAppKind = applinux || WebAppKind = linux. Image Source. Default: Registry.
    #AzureContainerRegistry: # string. Required when ImageSource = AzureContainerRegistry. Registry. 
    #AzureContainerRegistryLoginServer: # string. Optional. Use when ImageSource = invalidimagesource. Registry Login Server Name. 
    #AzureContainerRegistryImage: # string. Required when ImageSource = AzureContainerRegistry. Image. 
    #AzureContainerRegistryTag: # string. Optional. Use when ImageSource = AzureContainerRegistry. Tag. 
    #DockerRepositoryAccess: 'public' # 'private' | 'public'. Required when ImageSource = invalidImage. Repository Access. Default: public.
    #dockerRegistryConnection: # string. Alias: RegistryConnectedServiceName. Required when DockerRepositoryAccess = private || ImageSource = PrivateRegistry. Registry Connection. 
    #PrivateRegistryImage: # string. Required when ImageSource = PrivateRegistry. Image. 
    #PrivateRegistryTag: # string. Optional. Use when ImageSource = PrivateRegistry. Tag. 
    #DockerNamespace: # string. Required when WebAppKind != app && WebAppKind != functionapp && WebAppKind != api && WebAppKind != mobileapp && ImageSource  = Registry. Registry or Namespace. 
    #DockerRepository: # string. Required when WebAppKind != app && WebAppKind != functionapp && WebAppKind != api && WebAppKind != mobileapp && ImageSource  = Registry. Image. 
    #DockerImageTag: # string. Optional. Use when WebAppKind != app && WebAppKind != functionapp && WebAppKind != api && WebAppKind != mobileapp && ImageSource  = Registry. Tag. 
    #VirtualApplication: # string. Optional. Use when WebAppKind != linux && WebAppKind != applinux && WebAppKind != "". Virtual application. 
    #Package: '$(System.DefaultWorkingDirectory)/**/*.zip' # string. Required when WebAppKind != linux && WebAppKind != applinux &&  WebAppKind != "". Package or folder. Default: $(System.DefaultWorkingDirectory)/**/*.zip.
    #packageForLinux: '$(System.DefaultWorkingDirectory)/**/*.zip' # string. Alias: BuiltinLinuxPackage. Required when WebAppKind != app && WebAppKind != functionapp && WebAppKind != api && WebAppKind != mobileapp && ImageSource = Builtin. Package or folder. Default: $(System.DefaultWorkingDirectory)/**/*.zip.
    #RuntimeStack: # string. Required when WebAppKind != app && WebAppKind != functionapp && WebAppKind != api && WebAppKind != mobileapp && ImageSource = Builtin. Runtime Stack. 
    #StartupCommand: # string. Optional. Use when WebAppKind = applinux || WebAppKind = linux. Startup command. 
  # Output
    #WebAppUri: # string. Optional. Use when WebAppKind != "". App Service URL. 
  # Post Deployment Action
    #ScriptType: # 'Inline Script' | 'File Path'. Optional. Use when WebAppKind != "". Deployment script type. 
    #InlineScript: ':: You can provide your deployment commands here. One command per line.' # string. Required when ScriptType == Inline Script && WebAppKind != "". Inline Script. Default: :: You can provide your deployment commands here. One command per line..
    #ScriptPath: # string. Required when ScriptType == File Path && WebAppKind != "". Deployment script path. 
  # File Transforms & Variable Substitution Options
    #GenerateWebConfig: false # boolean. Optional. Use when WebAppKind != linux && WebAppKind != applinux && WebAppKind != "" && Package NotEndsWith .war. Generate Web.config. Default: false.
    #WebConfigParameters: # string. Required when GenerateWebConfig == true && WebAppKind != linux && WebAppKind != applinux && WebAppKind != "" && Package NotEndsWith .war. Web.config parameters. 
    #enableXmlTransform: false # boolean. Alias: XmlTransformation. Optional. Use when WebAppKind != linux && WebAppKind != applinux && WebAppKind != "" && Package NotEndsWith .war. XML transformation. Default: false.
    #enableXmlVariableSubstitution: false # boolean. Alias: XmlVariableSubstitution. Optional. Use when WebAppKind != linux && WebAppKind != applinux && WebAppKind != "" && Package NotEndsWith .war. XML variable substitution. Default: false.
    #JSONFiles: # string. Optional. Use when WebAppKind != linux && WebAppKind != applinux && WebAppKind != "" && Package NotEndsWith .war. JSON variable substitution. 
  # Application and Configuration Settings
    #AppSettings: # string. App settings. 
    #ConfigurationSettings: # string. Configuration settings. 
  # Additional Deployment Options
    #TakeAppOfflineFlag: false # boolean. Optional. Use when WebAppKind != linux && WebAppKind != applinux && WebAppKind != "". Take App Offline. Default: false.
    #UseWebDeploy: false # boolean. Optional. Use when WebAppKind != linux && WebAppKind != applinux && WebAppKind != "". Publish using Web Deploy. Default: false.
    #SetParametersFile: # string. Optional. Use when UseWebDeploy == true && WebAppKind != linux && WebAppKind != applinux && WebAppKind != "". SetParameters file. 
    #RemoveAdditionalFilesFlag: false # boolean. Optional. Use when UseWebDeploy == true && WebAppKind != linux && WebAppKind != applinux && WebAppKind != "". Remove additional files at destination. Default: false.
    #ExcludeFilesFromAppDataFlag: false # boolean. Optional. Use when UseWebDeploy == true && WebAppKind != linux && WebAppKind != applinux && WebAppKind != "". Exclude files from the App_Data folder. Default: false.
    #AdditionalArguments: # string. Optional. Use when UseWebDeploy == true && WebAppKind != linux && WebAppKind != applinux && WebAppKind != "". Additional arguments. 
    #RenameFilesFlag: false # boolean. Optional. Use when UseWebDeploy == true && WebAppKind != linux && WebAppKind != applinux && WebAppKind != "". Rename locked files. Default: false.
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

<!-- :::item name="azureSubscription"::: -->
:::moniker range="<=azure-pipelines"

**`azureSubscription`** - **Azure subscription**<br>
Input alias: `ConnectedServiceName`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the Azure Resource Manager subscription for the deployment.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="appType"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`appType`** - **App type**<br>
Input alias: `WebAppKind`. `string`. Required. Allowed values: `app` (Web App), `applinux` (Linux Web App), `functionapp` (Function App (Not Recommended, Use Azure Functions Task)), `api` (API App), `mobileapp` (Mobile App). Default value: `app`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the type of web app to deploy.

Note: Specify Linux Web App for built-in platform images or custom container image deployments.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="<=azure-pipelines-2022"

**`appType`** - **App type**<br>
Input alias: `WebAppKind`. `string`. Required. Allowed values: `app` (Web App), `applinux` (Linux Web App), `functionapp` (Function App), `api` (API App), `mobileapp` (Mobile App). Default value: `app`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the type of web app to deploy.

Note: Specify Linux Web App for built-in platform images or custom container image deployments.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="WebAppName"::: -->
:::moniker range="<=azure-pipelines"

**`WebAppName`** - **App Service name**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the name of an existing Azure App Service. App services based on the selected app type will only be listed when using the task assistant.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DeployToSlotFlag"::: -->
:::moniker range="<=azure-pipelines"

**`DeployToSlotFlag`** - **Deploy to slot**<br>
`boolean`. Optional. Use when `WebAppKind != ""`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Use this option to deploy to an existing slot other than the Production slot. If this option is not selected, then the Azure App Service will be deployed to the Production slot.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ResourceGroupName"::: -->
:::moniker range="<=azure-pipelines"

**`ResourceGroupName`** - **Resource group**<br>
`string`. Required when `DeployToSlotFlag = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the Azure Resource group that contains the Azure App Service specified above.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SlotName"::: -->
:::moniker range="<=azure-pipelines"

**`SlotName`** - **Slot**<br>
`string`. Required when `DeployToSlotFlag = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify an existing slot other than the Production slot.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ImageSource"::: -->
:::moniker range="<=azure-pipelines"

**`ImageSource`** - **Image Source**<br>
`string`. Optional. Use when `WebAppKind = applinux || WebAppKind = linux`. Allowed values: `Registry` (Container Registry), `Builtin` (Built-in Image). Default value: `Registry`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
App Service on Linux offers two different options to publish your application:

Custom image deployment or app deployment with a built-in platform image.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AzureContainerRegistry"::: -->
:::moniker range="<=azure-pipelines"

**`AzureContainerRegistry`** - **Registry**<br>
`string`. Required when `ImageSource = AzureContainerRegistry`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
A globally unique top-level domain name for your specific registry.

Note: A fully qualified image name will be of the format: **`<registry>`**/`<repository>`:`<tag>`. For example, **`myregistry.azurecr.io`**/`nginx:latest`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AzureContainerRegistryLoginServer"::: -->
:::moniker range="<=azure-pipelines"

**`AzureContainerRegistryLoginServer`** - **Registry Login Server Name**<br>
`string`. Optional. Use when `ImageSource = invalidimagesource`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify an Azure container registry login server name.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AzureContainerRegistryImage"::: -->
:::moniker range="<=azure-pipelines"

**`AzureContainerRegistryImage`** - **Image**<br>
`string`. Required when `ImageSource = AzureContainerRegistry`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of the repository where the container images are stored.

Note: A fully qualified image name will be of the format: `<registry>`/**`<repository>`**:`<tag>`. For example, `myregistry.azurecr.io`/**`nginx`**:`latest`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AzureContainerRegistryTag"::: -->
:::moniker range="<=azure-pipelines"

**`AzureContainerRegistryTag`** - **Tag**<br>
`string`. Optional. Use when `ImageSource = AzureContainerRegistry`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
This is the mechanism that registries use to give Docker images a version.

Note: A fully qualified image name will be of the format: `<registry>`/`<repository>`:**`<tag>`**. For example, `myregistry.azurecr.io`/`nginx`:**`latest`**.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DockerRepositoryAccess"::: -->
:::moniker range="<=azure-pipelines"

**`DockerRepositoryAccess`** - **Repository Access**<br>
`string`. Required when `ImageSource = invalidImage`. Allowed values: `private`, `public`. Default value: `public`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the Docker repository access.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="dockerRegistryConnection"::: -->
:::moniker range="<=azure-pipelines"

**`dockerRegistryConnection`** - **Registry Connection**<br>
Input alias: `RegistryConnectedServiceName`. `string`. Required when `DockerRepositoryAccess = private || ImageSource = PrivateRegistry`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the registry connection.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="PrivateRegistryImage"::: -->
:::moniker range="<=azure-pipelines"

**`PrivateRegistryImage`** - **Image**<br>
`string`. Required when `ImageSource = PrivateRegistry`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of the repository where the container images are stored.

Note: A fully qualified image name will be of the format: `<registry>`**`<repository>`**:`<tag>`. For example, `myregistry.azurecr.io`/**`nginx`**:`latest`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="PrivateRegistryTag"::: -->
:::moniker range="<=azure-pipelines"

**`PrivateRegistryTag`** - **Tag**<br>
`string`. Optional. Use when `ImageSource = PrivateRegistry`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Tags are the mechanism that registries use to give Docker images a version.

 Note: A fully qualified image name will be of the format: '`<registry>`/`<repository>`:**`<tag>`**'. For example, `myregistry.azurecr.io`/`nginx`:**`latest`**.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DockerNamespace"::: -->
:::moniker range="<=azure-pipelines"

**`DockerNamespace`** - **Registry or Namespace**<br>
`string`. Required when `WebAppKind != app && WebAppKind != functionapp && WebAppKind != api && WebAppKind != mobileapp && ImageSource  = Registry`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
A globally unique top-level domain name for your specific registry or namespace.

 Note: A fully qualified image name will be of the format: **`<registry or namespace>`**/`<repository>`:`<tag>`. For example, **`myregistry.azurecr.io`**/`nginx`:`latest`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DockerRepository"::: -->
:::moniker range="<=azure-pipelines"

**`DockerRepository`** - **Image**<br>
`string`. Required when `WebAppKind != app && WebAppKind != functionapp && WebAppKind != api && WebAppKind != mobileapp && ImageSource  = Registry`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of the repository where the container images are stored.

 Note: A fully qualified image name will be of the format: '`<registry or namespace>`/**`<repository>`**:`<tag>`. For example, `myregistry.azurecr.io`/**`nginx`**:`latest`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DockerImageTag"::: -->
:::moniker range="<=azure-pipelines"

**`DockerImageTag`** - **Tag**<br>
`string`. Optional. Use when `WebAppKind != app && WebAppKind != functionapp && WebAppKind != api && WebAppKind != mobileapp && ImageSource  = Registry`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
This is the mechanism that registries use to give Docker images a version.

 Note: A fully qualified image name will be of the format: '`<registry or namespace>`/`<repository>`:**`<tag>`**'. For example, `myregistry.azurecr.io`/`nginx`:**`latest`**.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="VirtualApplication"::: -->
:::moniker range="<=azure-pipelines"

**`VirtualApplication`** - **Virtual application**<br>
`string`. Optional. Use when `WebAppKind != linux && WebAppKind != applinux && WebAppKind != ""`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the name of the Virtual Application that has been configured in the Azure portal. The option is not required for deployments to the App Service root.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Package"::: -->
:::moniker range="<=azure-pipelines"

**`Package`** - **Package or folder**<br>
`string`. Required when `WebAppKind != linux && WebAppKind != applinux &&  WebAppKind != ""`. Default value: `$(System.DefaultWorkingDirectory)/**/*.zip`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The file path to the package or a folder containing app service contents generated by MSBuild or a compressed zip or war file.

Variables are [Build](/azure/devops/pipelines/build/variables) and [Release](/azure/devops/pipelines/release/variables#default-variables). [Wildcards](/azure/devops/pipelines/tasks/file-matching-patterns) are supported.

For example, `$(System.DefaultWorkingDirectory)/\*\*/\*.zip` or `$(System.DefaultWorkingDirectory)/\*\*/\*.war`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="packageForLinux"::: -->
:::moniker range="<=azure-pipelines"

**`packageForLinux`** - **Package or folder**<br>
Input alias: `BuiltinLinuxPackage`. `string`. Required when `WebAppKind != app && WebAppKind != functionapp && WebAppKind != api && WebAppKind != mobileapp && ImageSource = Builtin`. Default value: `$(System.DefaultWorkingDirectory)/**/*.zip`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The file path to the package or a folder containing app service contents generated by MSBuild or a compressed zip or war file.

Variables are [Build](https://www.visualstudio.com/docs/build/define/variables) and [Release](https://www.visualstudio.com/docs/release/author-release-definition/understanding-tasks#predefvariables). [Wildcards](/azure/devops/pipelines/tasks/file-matching-patterns) are supported.

For example, `$(System.DefaultWorkingDirectory)/\*\*/\*.zip` or `$(System.DefaultWorkingDirectory)/\*\*/\*.war`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="RuntimeStack"::: -->
:::moniker range=">=azure-pipelines-2019"

**`RuntimeStack`** - **Runtime Stack**<br>
`string`. Required when `WebAppKind != app && WebAppKind != functionapp && WebAppKind != api && WebAppKind != mobileapp && ImageSource = Builtin`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the framework and version.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`RuntimeStack`** - **Runtime Stack**<br>
`string`. Required when `WebAppKind != app && WebAppKind != functionapp && WebAppKind != api && WebAppKind != mobileapp && ImageSource = Builtin`. Allowed values: `node|4.4` (Node.js 4.4), `node|4.5` (Node.js 4.5), `node|6.2` (Node.js 6.2), `node|6.6` (Node.js 6.6), `node|6.9` (Node.js 6.9), `node|6.10` (Node.js 6.10), `node|6.11` (Node.js 6.11), `node|8.0` (Node.js 8.0), `node|8.1` (Node.js 8.1), `php|5.6` (PHP 5.6), `php|7.0` (PHP 7.0), `dotnetcore|1.0` (.NET Core 1.0), `dotnetcore|1.1` (.NET Core 1.1), `dotnetcore|2.0` (.NET Core 2.0), `ruby|2.3` (Ruby 2.3).<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the framework and version.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="StartupCommand"::: -->
:::moniker range="<=azure-pipelines"

**`StartupCommand`** - **Startup command**<br>
`string`. Optional. Use when `WebAppKind = applinux || WebAppKind = linux`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the startup command.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="WebAppUri"::: -->
:::moniker range="<=azure-pipelines"

**`WebAppUri`** - **App Service URL**<br>
`string`. Optional. Use when `WebAppKind != ""`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify a name for the output variable that is generated for the URL of the Azure App Service. The variable can be used in subsequent tasks.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ScriptType"::: -->
:::moniker range="<=azure-pipelines"

**`ScriptType`** - **Deployment script type**<br>
`string`. Optional. Use when `WebAppKind != ""`. Allowed values: `Inline Script`, `File Path` (Script File Path).<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Customizes the deployment by providing a script that will run on the Azure App service once the task has completed the deployment successfully . For example, this can restore packages for Node, PHP, and Python applications. Learn more about [Azure App Service Deployment](https://go.microsoft.com/fwlink/?linkid=843471).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="InlineScript"::: -->
:::moniker range="<=azure-pipelines"

**`InlineScript`** - **Inline Script**<br>
`string`. Required when `ScriptType == Inline Script && WebAppKind != ""`. Default value: `:: You can provide your deployment commands here. One command per line.`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ScriptPath"::: -->
:::moniker range="<=azure-pipelines"

**`ScriptPath`** - **Deployment script path**<br>
`string`. Required when `ScriptType == File Path && WebAppKind != ""`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="GenerateWebConfig"::: -->
:::moniker range=">=azure-pipelines-2019"

**`GenerateWebConfig`** - **Generate Web.config**<br>
`boolean`. Optional. Use when `WebAppKind != linux && WebAppKind != applinux && WebAppKind != "" && Package NotEndsWith .war`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
A standard `Web.config` will be generated and deployed to Azure App Service if the application does not have one. The values in `web.config` can be edited and vary based on the application framework. For example, for the `node.js` application, `web.config` will have startup file and `iis_node` module values. Learn more about [Azure App Service Deployment](https://go.microsoft.com/fwlink/?linkid=843471).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`GenerateWebConfig`** - **Generate Web.config**<br>
`boolean`. Optional. Use when `WebAppKind != linux && WebAppKind != applinux && WebAppKind != ""`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
A standard `Web.config` will be generated and deployed to Azure App Service if the application does not have one. The values in `web.config` can be edited and vary based on the application framework. For example, for the `node.js` application, `web.config` will have startup file and `iis_node` module values. Learn more about [Azure App Service Deployment](https://go.microsoft.com/fwlink/?linkid=843471).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="WebConfigParameters"::: -->
:::moniker range=">=azure-pipelines-2019"

**`WebConfigParameters`** - **Web.config parameters**<br>
`string`. Required when `GenerateWebConfig == true && WebAppKind != linux && WebAppKind != applinux && WebAppKind != "" && Package NotEndsWith .war`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Edits values like startup files in the generated `web.config` file. This edit feature is only for the generated `web.config`. Learn more about [Azure App Service Deployment](https://go.microsoft.com/fwlink/?linkid=843471).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`WebConfigParameters`** - **Web.config parameters**<br>
`string`. Required when `GenerateWebConfig == true && WebAppKind != linux && WebAppKind != applinux && WebAppKind != ""`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Edits values like startup files in the generated `web.config` file. This edit feature is only for the generated `web.config`. Learn more about [Azure App Service Deployment](https://go.microsoft.com/fwlink/?linkid=843471).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AppSettings"::: -->
:::moniker range="<=azure-pipelines"

**`AppSettings`** - **App settings**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Edits web app application settings following the syntax -key value . Values containing spaces should be enclosed in double quotes.
Examples: `-Port 5000` `-RequestTimeout 5000` `-WEBSITE_TIME_ZONE` `"Eastern Standard Time"`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ConfigurationSettings"::: -->
:::moniker range="<=azure-pipelines"

**`ConfigurationSettings`** - **Configuration settings**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Edits web app configuration settings following the syntax `-key` value. Values containing spaces should be enclosed in double quotes.

Examples: `-phpVersion 5.6` `-linuxFxVersion: node|6.11`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="TakeAppOfflineFlag"::: -->
:::moniker range="<=azure-pipelines"

**`TakeAppOfflineFlag`** - **Take App Offline**<br>
`boolean`. Optional. Use when `WebAppKind != linux && WebAppKind != applinux && WebAppKind != ""`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Use this option to take the Azure App Service offline by placing an `app_offline.htm` file in the root directory of the App Service before the sync operation begins. The file will be removed after the sync operation completes successfully.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="UseWebDeploy"::: -->
:::moniker range="<=azure-pipelines"

**`UseWebDeploy`** - **Publish using Web Deploy**<br>
`boolean`. Optional. Use when `WebAppKind != linux && WebAppKind != applinux && WebAppKind != ""`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
`Publish using Web Deploy` options are supported only when using Windows agent. On other platforms, the task relies on [Kudu REST APIs](https://github.com/projectkudu/kudu/wiki/REST-API) to deploy the Azure App Service, and following options are not supported.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SetParametersFile"::: -->
:::moniker range="<=azure-pipelines"

**`SetParametersFile`** - **SetParameters file**<br>
`string`. Optional. Use when `UseWebDeploy == true && WebAppKind != linux && WebAppKind != applinux && WebAppKind != ""`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The location of the `SetParameters.xml` file to use.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="RemoveAdditionalFilesFlag"::: -->
:::moniker range="<=azure-pipelines"

**`RemoveAdditionalFilesFlag`** - **Remove additional files at destination**<br>
`boolean`. Optional. Use when `UseWebDeploy == true && WebAppKind != linux && WebAppKind != applinux && WebAppKind != ""`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Use this option to delete files on the Azure App Service that have no matching files in the App Service package or folder.

Note: This will also remove all files related to any extension installed on this Azure App Service. To prevent this, select the `Exclude files from App_Data folder` checkbox.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ExcludeFilesFromAppDataFlag"::: -->
:::moniker range="<=azure-pipelines"

**`ExcludeFilesFromAppDataFlag`** - **Exclude files from the App_Data folder**<br>
`boolean`. Optional. Use when `UseWebDeploy == true && WebAppKind != linux && WebAppKind != applinux && WebAppKind != ""`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Use this option to prevent files in the `App_Data` folder from being deployed to/deleted from the Azure App Service.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AdditionalArguments"::: -->
:::moniker range="<=azure-pipelines"

**`AdditionalArguments`** - **Additional arguments**<br>
`string`. Optional. Use when `UseWebDeploy == true && WebAppKind != linux && WebAppKind != applinux && WebAppKind != ""`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The additional Web Deploy arguments following the syntax `-key:value`.

These will be applied when deploying the Azure App Service. Examples: `-disableLink:AppPoolExtension` `-disableLink:ContentExtension`.

See more examples of [Web Deploy Operation Settings](https://go.microsoft.com/fwlink/?linkid=838471).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="RenameFilesFlag"::: -->
:::moniker range="<=azure-pipelines"

**`RenameFilesFlag`** - **Rename locked files**<br>
`boolean`. Optional. Use when `UseWebDeploy == true && WebAppKind != linux && WebAppKind != applinux && WebAppKind != ""`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Use this option to enable msdeploy flag `MSDEPLOY_RENAME_LOCKED_FILES=1` in Azure App Service application settings. The option enables msdeploy to rename locked files that are locked during app deployment.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="enableXmlTransform"::: -->
:::moniker range=">=azure-pipelines-2019"

**`enableXmlTransform`** - **XML transformation**<br>
Input alias: `XmlTransformation`. `boolean`. Optional. Use when `WebAppKind != linux && WebAppKind != applinux && WebAppKind != "" && Package NotEndsWith .war`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The config transforms will be run for `*.Release.config` and `*.<EnvironmentName>.config` on the `*.config file`.

Config transforms will be run prior to the Variable Substitution.

XML transformations are supported only for Windows platform.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`enableXmlTransform`** - **XML transformation**<br>
Input alias: `XmlTransformation`. `boolean`. Optional. Use when `WebAppKind != linux && WebAppKind != applinux && WebAppKind != ""`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The config transforms will be run for `*.Release.config` and `*.<EnvironmentName>.config` on the `*.config file`.

Config transforms will be run prior to the Variable Substitution.

XML transformations are supported only for Windows platform.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="enableXmlVariableSubstitution"::: -->
:::moniker range=">=azure-pipelines-2019"

**`enableXmlVariableSubstitution`** - **XML variable substitution**<br>
Input alias: `XmlVariableSubstitution`. `boolean`. Optional. Use when `WebAppKind != linux && WebAppKind != applinux && WebAppKind != "" && Package NotEndsWith .war`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Variables defined in the build or release pipeline will be matched against the `key` or `name` entries in the `appSettings`, `applicationSettings`, and `connectionStrings` sections of any config file and `parameters.xml`. Variable Substitution is run after config transforms.

Note: If the same variables are defined in the release pipeline and in the environment, then the environment variables will supersede the release pipeline variables.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`enableXmlVariableSubstitution`** - **XML variable substitution**<br>
Input alias: `XmlVariableSubstitution`. `boolean`. Optional. Use when `WebAppKind != linux && WebAppKind != applinux && WebAppKind != ""`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Variables defined in the build or release pipeline will be matched against the `key` or `name` entries in the `appSettings`, `applicationSettings`, and `connectionStrings` sections of any config file and `parameters.xml`. Variable Substitution is run after config transforms.

Note: If the same variables are defined in the release pipeline and in the environment, then the environment variables will supersede the release pipeline variables.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="JSONFiles"::: -->
:::moniker range=">=azure-pipelines-2019"

**`JSONFiles`** - **JSON variable substitution**<br>
`string`. Optional. Use when `WebAppKind != linux && WebAppKind != applinux && WebAppKind != "" && Package NotEndsWith .war`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provides a new lines-separated list of JSON files to substitute the variable values. Files names are to be provided relative to the root folder.

To substitute JSON variables that are nested or hierarchical, specify them using `JSONPath` expressions.

For example, to replace the value of `ConnectionString` in the sample below, you need to define a variable as `Data.DefaultConnection.ConnectionString` in the build/release pipeline (or the release pipeline’s environment).

```json
{
  "Data": {
    "DefaultConnection": {
      "ConnectionString": "Server=(localdb)\SQLEXPRESS;Database=MyDB;Trusted_Connection=True"
    }
  }
}
```

Variable Substitution is run after configuration transforms.

Note: pipeline variables are excluded in substitution.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`JSONFiles`** - **JSON variable substitution**<br>
`string`. Optional. Use when `WebAppKind != linux && WebAppKind != applinux && WebAppKind != ""`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provides a new lines-separated list of JSON files to substitute the variable values. Files names are to be provided relative to the root folder.

To substitute JSON variables that are nested or hierarchical, specify them using `JSONPath` expressions.

For example, to replace the value of `ConnectionString` in the sample below, you need to define a variable as `Data.DefaultConnection.ConnectionString` in the build/release pipeline (or the release pipeline’s environment).

```json
{
  "Data": {
    "DefaultConnection": {
      "ConnectionString": "Server=(localdb)\SQLEXPRESS;Database=MyDB;Trusted_Connection=True"
    }
  }
}
```

Variable Substitution is run after configuration transforms.

Note: pipeline variables are excluded in substitution.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range="<=azure-pipelines"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

There is a newer version of this task available. For more information, see [AzureRmWebAppDeployment@4](./azure-rm-web-app-deployment-v4.md).

:::moniker range=">azure-pipelines-2022.1"

### Troubleshooting

[!INCLUDE [rm-web-app-deployment-authentication](./includes/rm-web-app-deployment-authentication.md)]

:::moniker-end
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
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

:::moniker range="=azure-pipelines-2018"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent |
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
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->