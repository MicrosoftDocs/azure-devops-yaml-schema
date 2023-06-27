---
title: AzureSpringCloud@0 - Azure Spring Cloud v0 task
description: Deploy applications to Azure Spring Cloud and manage deployments.
ms.date: 06/22/2023
monikerRange: ">=azure-pipelines-2022"
---

# AzureSpringCloud@0 - Azure Spring Cloud v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2022"

<!-- :::editable-content name="description"::: -->
This task deploys applications to Azure Spring Apps and manages those deployments.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="=azure-pipelines"

```yaml
# Azure Spring Apps v0
# Deploy applications to Azure Spring Apps and manage deployments.
- task: AzureSpringCloud@0
  inputs:
    azureSubscription: # string. Alias: ConnectedServiceName. Required. Azure subscription. 
    Action: 'Deploy' # 'Deploy' | 'Set Production' | 'Delete Staging Deployment'. Required. Action. Default: Deploy.
    AzureSpringCloud: # string. Required. Azure Spring Apps Name. 
    AppName: # string. Required. App. 
    #DeploymentType: 'Artifacts' # 'Artifacts' | 'CustomContainer'. Optional. Use when Action = Deploy. Deployment Type. Default: Artifacts.
    #UseStagingDeployment: true # boolean. Optional. Use when Action = Deploy || Action = Set Production. Use Staging Deployment. Default: true.
    #CreateNewDeployment: false # boolean. Optional. Use when Action = Deploy && UseStagingDeployment = false. Create a new staging deployment if one does not exist. Default: false.
    #DeploymentName: # string. Optional. Use when UseStagingDeployment = false && Action != Delete Staging Deployment. Deployment. 
    #Package: '$(System.DefaultWorkingDirectory)/**/*.jar' # string. Optional. Use when Action = Deploy && DeploymentType = Artifacts. Package or folder. Default: $(System.DefaultWorkingDirectory)/**/*.jar.
    #RegistryServer: 'docker.io' # string. Optional. Use when Action = Deploy && DeploymentType = CustomContainer. Registry Server. Default: docker.io.
    #RegistryUsername: # string. Optional. Use when Action = Deploy && DeploymentType = CustomContainer. Registry Username. 
    #RegistryPassword: # string. Optional. Use when Action = Deploy && DeploymentType = CustomContainer. Registry Password. 
    #ImageName: 'hello-world:v1' # string. Optional. Use when Action = Deploy && DeploymentType = CustomContainer. Image Name and Tag. Default: hello-world:v1.
    #ImageCommand: # string. Optional. Use when Action = Deploy && DeploymentType = CustomContainer. Image Command. 
    #ImageArgs: # string. Optional. Use when Action = Deploy && DeploymentType = CustomContainer. Image Arguments. 
    #ImageLanguageFramework: # 'springboot'. Optional. Use when Action = Deploy && DeploymentType = CustomContainer. Language Framework. 
  # Application and Configuration Settings
    #Builder: # string. Optional. Use when Action = Deploy && DeploymentType = Artifacts. Builder. 
    #EnvironmentVariables: # string. Optional. Use when Action = Deploy. Environment Variables. 
    #JvmOptions: # string. Optional. Use when Action = Deploy && DeploymentType = Artifacts. JVM Options. 
    #RuntimeVersion: 'Java_11' # 'Java_8' | 'Java_11' | 'NetCore_31'. Optional. Use when Action = Deploy && DeploymentType = Artifacts. Runtime Version. Default: Java_11.
    #DotNetCoreMainEntryPath: # string. Optional. Use when RuntimeVersion = NetCore_31. Main Entry Path. 
    #Version: # string. Optional. Use when Action = Deploy. Version.
```

:::moniker-end

:::moniker range="=azure-pipelines-2022"

```yaml
# Azure Spring Cloud v0
# Deploy applications to Azure Spring Cloud and manage deployments.
- task: AzureSpringCloud@0
  inputs:
    azureSubscription: # string. Alias: ConnectedServiceName. Required. Azure subscription. 
    Action: 'Deploy' # 'Deploy' | 'Set Production' | 'Delete Staging Deployment'. Required. Action. Default: Deploy.
    AzureSpringCloud: # string. Required. Azure Spring Cloud Name. 
    AppName: # string. Required. App. 
    #UseStagingDeployment: true # boolean. Optional. Use when Action = Deploy || Action = Set Production. Use Staging Deployment. Default: true.
    #CreateNewDeployment: false # boolean. Optional. Use when Action = Deploy && UseStagingDeployment = false. Create a new staging deployment if one does not exist. Default: false.
    #DeploymentName: # string. Optional. Use when UseStagingDeployment = false && Action != Delete Staging Deployment. Deployment. 
    #Package: '$(System.DefaultWorkingDirectory)/**/*.jar' # string. Optional. Use when Action = Deploy. Package or folder. Default: $(System.DefaultWorkingDirectory)/**/*.jar.
  # Application and Configuration Settings
    #EnvironmentVariables: # string. Optional. Use when Action = Deploy. Environment Variables. 
    #JvmOptions: # string. Optional. Use when Action = Deploy. JVM Options. 
    #RuntimeVersion: 'Java_11' # 'Java_8' | 'Java_11' | 'NetCore_31'. Optional. Use when Action = Deploy. Runtime Version. Default: Java_11.
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
Input alias: `ConnectedServiceName`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the [Azure Resource Manager subscription](/azure/devops/pipelines/library/connect-to-azure) for the deployment.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Action"::: -->
:::moniker range=">=azure-pipelines-2022"

**`Action`** - **Action**<br>
`string`. Required. Allowed values: `Deploy`, `Set Production` (Set Production Deployment), `Delete Staging Deployment`. Default value: `Deploy`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The action to be performed on Azure Spring Apps.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AzureSpringCloud"::: -->
:::moniker range="=azure-pipelines"

**`AzureSpringCloud`** - **Azure Spring Apps Name**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name or resource ID of the Azure Spring Apps instance to deploy.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2022"

**`AzureSpringCloud`** - **Azure Spring Cloud Name**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name or resource ID of the Azure Spring Apps instance to deploy.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AppName"::: -->
:::moniker range=">=azure-pipelines-2022"

**`AppName`** - **App**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of the Azure Spring Apps app to deploy. The app must exist prior to the task execution.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DeploymentType"::: -->
:::moniker range="=azure-pipelines"

**`DeploymentType`** - **Deployment Type**<br>
`string`. Optional. Use when `Action = Deploy`. Allowed values: `Artifacts`, `CustomContainer` (Custom Container). Default value: `Artifacts`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
To deploy with source code or Java package, choose "Artifacts"; To deploy with container image, choose "Custom Container".
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="UseStagingDeployment"::: -->
:::moniker range=">=azure-pipelines-2022"

**`UseStagingDeployment`** - **Use Staging Deployment**<br>
`boolean`. Optional. Use when `Action = Deploy || Action = Set Production`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
At the time the task runs, this input automatically selects the deployment that's set as `staging`.

If set to `true`, apply the task to the [deployment](/azure/spring-apps/concept-understand-app-and-deployment) that is set as the staging deployment at time of execution. If omitted, the `DeploymentName` parameter must be set.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="CreateNewDeployment"::: -->
:::moniker range=">=azure-pipelines-2022"

**`CreateNewDeployment`** - **Create a new staging deployment if one does not exist.**<br>
`boolean`. Optional. Use when `Action = Deploy && UseStagingDeployment = false`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If set to `true`, and the deployment specified by `DeploymentName` does not exist at execution time, it will be created. If omitted, the `DeploymentName` parameter must be set.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DeploymentName"::: -->
:::moniker range=">=azure-pipelines-2022"

**`DeploymentName`** - **Deployment**<br>
`string`. Optional. Use when `UseStagingDeployment = false && Action != Delete Staging Deployment`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The [deployment](/azure/spring-apps/concept-understand-app-and-deployment) to which this task will apply. If not using blue-green deployments, set this field to `default`. The value must start with a letter and consist of lowercase letters and numbers only.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Package"::: -->
:::moniker range="=azure-pipelines"

**`Package`** - **Package or folder**<br>
`string`. Optional. Use when `Action = Deploy && DeploymentType = Artifacts`. Default value: `$(System.DefaultWorkingDirectory)/**/*.jar`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The file path to the package or folder containing the Azure Spring Apps app contents (`.jar` file for Java, `.zip` for .NET Core).  
Variables ( [Build](/azure/devops/pipelines/build/variables) | [Release](/azure/devops/pipelines/release/variables#default-variables)) and wildcards are supported.  
For example, `$(System.DefaultWorkingDirectory)/**/*.jar`
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2022"

**`Package`** - **Package or folder**<br>
`string`. Optional. Use when `Action = Deploy`. Default value: `$(System.DefaultWorkingDirectory)/**/*.jar`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The file path to the package or folder containing the Azure Spring Apps app contents (`.jar` file for Java, `.zip` for .NET Core).  
Variables ( [Build](/azure/devops/pipelines/build/variables) | [Release](/azure/devops/pipelines/release/variables#default-variables)) and wildcards are supported.  
For example, `$(System.DefaultWorkingDirectory)/**/*.jar`
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Builder"::: -->
:::moniker range="=azure-pipelines"

**`Builder`** - **Builder**<br>
`string`. Optional. Use when `Action = Deploy && DeploymentType = Artifacts`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select a builder of VMware Tanzu® Build Service™, this can be used in enterprise tier. <br/> For detailed description, please check [Use Tanzu Build Service](/azure/spring-cloud/how-to-enterprise-build-service?tabs=azure-portal).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="RegistryServer"::: -->
:::moniker range="=azure-pipelines"

**`RegistryServer`** - **Registry Server**<br>
`string`. Optional. Use when `Action = Deploy && DeploymentType = CustomContainer`. Default value: `docker.io`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The registry of the container image.  Default: docker.io.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="RegistryUsername"::: -->
:::moniker range="=azure-pipelines"

**`RegistryUsername`** - **Registry Username**<br>
`string`. Optional. Use when `Action = Deploy && DeploymentType = CustomContainer`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The username of the container registry.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="RegistryPassword"::: -->
:::moniker range="=azure-pipelines"

**`RegistryPassword`** - **Registry Password**<br>
`string`. Optional. Use when `Action = Deploy && DeploymentType = CustomContainer`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The password of the container registry.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ImageName"::: -->
:::moniker range="=azure-pipelines"

**`ImageName`** - **Image Name and Tag**<br>
`string`. Optional. Use when `Action = Deploy && DeploymentType = CustomContainer`. Default value: `hello-world:v1`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The container image tag.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ImageCommand"::: -->
:::moniker range="=azure-pipelines"

**`ImageCommand`** - **Image Command**<br>
`string`. Optional. Use when `Action = Deploy && DeploymentType = CustomContainer`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The command of the container image.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ImageArgs"::: -->
:::moniker range="=azure-pipelines"

**`ImageArgs`** - **Image Arguments**<br>
`string`. Optional. Use when `Action = Deploy && DeploymentType = CustomContainer`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The arguments of the container image.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ImageLanguageFramework"::: -->
:::moniker range="=azure-pipelines"

**`ImageLanguageFramework`** - **Language Framework**<br>
`string`. Optional. Use when `Action = Deploy && DeploymentType = CustomContainer`. Allowed values: `springboot`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="EnvironmentVariables"::: -->
:::moniker range=">=azure-pipelines-2022"

**`EnvironmentVariables`** - **Environment Variables**<br>
`string`. Optional. Use when `Action = Deploy`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The environment variables to be entered using the syntax `-key value` (for example: `-CUSTOMER_NAME Contoso` `-WEBSITE_TIME_ZONE`). Values containing spaces should be enclosed in double quotes (for example: `"Eastern Standard Time"`).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="JvmOptions"::: -->
:::moniker range="=azure-pipelines"

**`JvmOptions`** - **JVM Options**<br>
`string`. Optional. Use when `Action = Deploy && DeploymentType = Artifacts`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Edits the app's JVM options. A string containing JVM options, such as `-Xms1024m -Xmx2048m`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2022"

**`JvmOptions`** - **JVM Options**<br>
`string`. Optional. Use when `Action = Deploy`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Edits the app's JVM options. A string containing JVM options, such as `-Xms1024m -Xmx2048m`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="RuntimeVersion"::: -->
:::moniker range="=azure-pipelines"

**`RuntimeVersion`** - **Runtime Version**<br>
`string`. Optional. Use when `Action = Deploy && DeploymentType = Artifacts`. Allowed values: `Java_8` (Java 8), `Java_11` (Java 11), `NetCore_31` (.Net Core 3.1). Default value: `Java_11`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The runtime version on which the app will run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2022"

**`RuntimeVersion`** - **Runtime Version**<br>
`string`. Optional. Use when `Action = Deploy`. Allowed values: `Java_8` (Java 8), `Java_11` (Java 11), `NetCore_31` (.Net Core 3.1). Default value: `Java_11`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The runtime version on which the app will run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DotNetCoreMainEntryPath"::: -->
:::moniker range=">=azure-pipelines-2022"

**`DotNetCoreMainEntryPath`** - **Main Entry Path**<br>
`string`. Optional. Use when `RuntimeVersion = NetCore_31`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The path to the .NET executable relative to the zip root.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Version"::: -->
:::moniker range=">=azure-pipelines-2022"

**`Version`** - **Version**<br>
`string`. Optional. Use when `Action = Deploy`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The deployment version. If not set, the version is left unchanged.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
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
## Remarks

Use this task to deploy applications to [Azure Spring Cloud](/azure/spring-cloud/) and to manage Azure Spring Cloud [deployments](/azure/spring-cloud/concept-understand-app-and-deployment).
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

The following examples demonstrate common usage scenarios. For more information, see [Automate application deployments to Azure Spring Cloud](/azure/spring-cloud/how-to-cicd?pivots=programming-language-java).

### Deleting a staging deployment

The "Delete Staging Deployment" action allows you to delete the deployment not receiving production traffic. This frees up resources used by that deployment and makes room for a new staging deployment:

```yml
variables:
  azureSubscription: Contoso

steps:
- task: AzureSpringCloud@0
  continueOnError: true # Don't fail the pipeline if a staging deployment doesn't already exist.
  inputs:
    continueOnError: true
    inputs:
    azureSubscription: $(azureSubscription)
    Action: 'Delete Staging Deployment'
    AppName: customer-api
    AzureSpringCloud: contoso-dev-az-spr-cld
```

### Deploying

#### To production

The following example deploys to the default production deployment in Azure Spring Cloud. This is the only possible deployment scenario when using the Basic SKU:

> [!NOTE]
> The package search pattern should only return exactly one package. If the build task produces multiple JAR packages such as *sources.jar* and *javadoc.jar*, you need to refine the search pattern so that it only matches the application binary artifact.

```yml
variables:
  azureSubscription: Contoso

steps:
- task: AzureSpringCloud@0
    inputs:
    azureSubscription: $(azureSubscription)
    Action: 'Deploy'
    AzureSpringCloud: contoso-dev-az-spr-cld
    AppName: customer-api
    UseStagingDeployment: false
    DeploymentName: default
    Package: '$(System.DefaultWorkingDirectory)/**/*customer-api*.jar'
```

#### Blue-green

The following example deploys to a pre-existing staging deployment. This deployment will not receive production traffic until it is set as a production deployment.

```yml
variables:
  azureSubscription: Contoso

steps:
- task: AzureSpringCloud@0
    inputs:
    azureSubscription: $(azureSubscription)
    Action: 'Deploy'
    AzureSpringCloud: contoso-dev-az-spr-cld
    AppName: customer-api
    UseStagingDeployment: true
    Package: '$(System.DefaultWorkingDirectory)/**/*customer-api*.jar'
```

For more on blue-green deployments, including an alternative approach, see [Blue-green deployment strategies](/azure/spring-cloud/concepts-blue-green-deployment-strategies).

### Setting production deployment

The following example sets the current staging deployment as production, effectively swapping which deployment receives production traffic.

```yml
variables:
  azureSubscription: Contoso

steps:
- task: AzureSpringCloud@0
    inputs:
    azureSubscription: $(azureSubscription)
    Action: 'Set Production'
    AzureSpringCloud: contoso-dev-az-spr-cld
    AppName: customer-api
    UseStagingDeployment: true
```
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
