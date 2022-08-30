---
title: AzureSpringCloud@0 - Azure Spring Cloud v0 task
description: Deploy applications to Azure Spring Cloud and manage deployments.
ms.date: 08/10/2022
monikerRange: ">=azure-pipelines-2022"
---

# AzureSpringCloud@0 - Azure Spring Cloud v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2022"

<!-- :::editable-content name="description"::: -->
Deploy applications to Azure Spring Cloud and manage deployments.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2022"

```yaml
# Azure Spring Cloud v0
# Deploy applications to Azure Spring Cloud and manage deployments.
- task: AzureSpringCloud@0
  inputs:
    azureSubscription: # string. Required. Azure subscription. 
    Action: 'Deploy' # 'Deploy' | 'Set Production' | 'Delete Staging Deployment'. Required. Action. Default: 'Deploy'.
    AzureSpringCloud: # string. Required. Azure Spring Cloud Name. 
    AppName: # string. Required. App. 
    #UseStagingDeployment: true # boolean. Required when Action = Deploy || Action = Set Production. Use Staging Deployment. Default: true.
    #CreateNewDeployment: false # boolean. Optional. Use when Action = Deploy && UseStagingDeployment = false. Create a new staging deployment if one does not exist. Default: false.
    #DeploymentName: # string. Optional. Use when UseStagingDeployment = false && Action != Delete Staging Deployment. Deployment. 
    #Package: '$(System.DefaultWorkingDirectory)/**/*.jar' # string. Optional. Use when Action = Deploy. Package or folder. Default: '$(System.DefaultWorkingDirectory)/**/*.jar'.
  # Application and Configuration Settings
    #EnvironmentVariables: # string. Optional. Use when Action = Deploy. Environment Variables. 
    #JvmOptions: # string. Optional. Use when Action = Deploy. JVM Options. 
    #RuntimeVersion: 'Java_11' # 'Java_8' | 'Java_11' | 'NetCore_31'. Optional. Use when Action = Deploy. Runtime Version. Default: 'Java_11'.
    #DotNetCoreMainEntryPath: # string. Optional. Use when RuntimeVersion = NetCore_31. Main Entry Path. 
    #Version: # string. Optional. Use when Action = Deploy. Version.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="azureSubscription"::: -->
:::moniker range=">=azure-pipelines-2022"

**`azureSubscription`** - **Azure subscription**<br>
Input alias: `ConnectedServiceName`. Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the Azure Resource Manager subscription for the deployment.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Action"::: -->
:::moniker range=">=azure-pipelines-2022"

**`Action`** - **Action**<br>
Type: string. Required. Allowed values: 'Deploy', 'Set Production', 'Delete Staging Deployment'. Default value: 'Deploy'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Action to be performed on Azure Spring Cloud.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AzureSpringCloud"::: -->
:::moniker range=">=azure-pipelines-2022"

**`AzureSpringCloud`** - **Azure Spring Cloud Name**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the Azure Spring Cloud service to which to deploy.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AppName"::: -->
:::moniker range=">=azure-pipelines-2022"

**`AppName`** - **App**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the Azure Spring Cloud app to deploy.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="UseStagingDeployment"::: -->
:::moniker range=">=azure-pipelines-2022"

**`UseStagingDeployment`** - **Use Staging Deployment**<br>
Type: boolean. Required when Action = Deploy || Action = Set Production. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Automatically select the deployment that's set as Staging at the time the task runs.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="CreateNewDeployment"::: -->
:::moniker range=">=azure-pipelines-2022"

**`CreateNewDeployment`** - **Create a new staging deployment if one does not exist.**<br>
Type: boolean. Optional. Use when Action = Deploy && UseStagingDeployment = false. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Whether to target the deployment that's set as Staging at the time of execution. If unchecked, the 'Deployment Name' setting must be set.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DeploymentName"::: -->
:::moniker range=">=azure-pipelines-2022"

**`DeploymentName`** - **Deployment**<br>
Type: string. Optional. Use when UseStagingDeployment = false && Action != Delete Staging Deployment.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The deployment to which this task will apply. Lowercase letters and numbers only; must start with a letter.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Package"::: -->
:::moniker range=">=azure-pipelines-2022"

**`Package`** - **Package or folder**<br>
Type: string. Optional. Use when Action = Deploy. Default value: '$(System.DefaultWorkingDirectory)/**/*.jar'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
File path to the package or a folder containing the Spring Cloud app contents.<br />Variables ( [Build](/azure/devops/pipelines/build/variables) | [Release](/azure/devops/pipelines/release/variables#default-variables)), wildcards are supported. <br/> For example, $(System.DefaultWorkingDirectory)/\*\*/\*.jar.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="EnvironmentVariables"::: -->
:::moniker range=">=azure-pipelines-2022"

**`EnvironmentVariables`** - **Environment Variables**<br>
Type: string. Optional. Use when Action = Deploy.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Edit the app's environment variables.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="JvmOptions"::: -->
:::moniker range=">=azure-pipelines-2022"

**`JvmOptions`** - **JVM Options**<br>
Type: string. Optional. Use when Action = Deploy.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Edit the app's JVM options. A String containing JVM Options. Example: `-Xms1024m -Xmx2048m`.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="RuntimeVersion"::: -->
:::moniker range=">=azure-pipelines-2022"

**`RuntimeVersion`** - **Runtime Version**<br>
Type: string. Optional. Use when Action = Deploy. Allowed values: 'Java_8', 'Java_11', 'NetCore_31'. Default value: 'Java_11'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The runtime on which the app will run.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DotNetCoreMainEntryPath"::: -->
:::moniker range=">=azure-pipelines-2022"

**`DotNetCoreMainEntryPath`** - **Main Entry Path**<br>
Type: string. Optional. Use when RuntimeVersion = NetCore_31.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The path to the .NET executable relative to zip root.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Version"::: -->
:::moniker range=">=azure-pipelines-2022"

**`Version`** - **Version**<br>
Type: string. Optional. Use when Action = Deploy.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2022"

This task defines the following [output variables](/azure/devops/pipelines/process/variables#use-output-variables-from-tasks), which you can consume in downstream steps, jobs, and stages.

<!-- :::item name="testEndpoint"::: -->
**`testEndpoint`**<br><!-- :::editable-content name="Value"::: -->
After the 'Deploy' action only. Contains private URL for accessing the updated deployment.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->

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

:::moniker range=">=azure-pipelines-2022"

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
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->