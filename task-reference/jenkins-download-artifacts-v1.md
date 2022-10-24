---
title: JenkinsDownloadArtifacts@1 - Jenkins download artifacts v1 task
description: Download artifacts produced by a Jenkins job.
ms.date: 10/21/2022
monikerRange: "<=azure-pipelines"
---

# JenkinsDownloadArtifacts@1 - Jenkins download artifacts v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Download artifacts produced by a Jenkins job.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# Jenkins download artifacts v1
# Download artifacts produced by a Jenkins job.
- task: JenkinsDownloadArtifacts@1
  inputs:
    jenkinsServerConnection: # string. Alias: serverEndpoint. Required. Jenkins service connection. 
    jobName: # string. Required. Job name. 
    #jenkinsJobType: # string. Optional. Use when jobName = invalidjobName. Jenkins job type. 
    saveTo: 'jenkinsArtifacts' # string. Required. Save to. Default: jenkinsArtifacts.
  # Advanced
    jenkinsBuild: 'LastSuccessfulBuild' # 'LastSuccessfulBuild' | 'BuildNumber'. Required. Download artifacts produced by. Default: LastSuccessfulBuild.
    #jenkinsBuildNumber: '1' # string. Required when jenkinsBuild == BuildNumber. Jenkins build number. Default: 1.
    #itemPattern: '**' # string. Item Pattern. Default: **.
    #downloadCommitsAndWorkItems: false # boolean. Download Commits and WorkItems. Default: false.
    #startJenkinsBuildNumber: # string. Optional. Use when downloadCommitsAndWorkItems == true && jenkinsBuild == BuildNumber. Download commits and work items from. 
    #artifactDetailsFileNameSuffix: # string. Optional. Use when downloadCommitsAndWorkItems == invalid. Commit and WorkItem FileName. 
  # Propagated Artifacts
    #propagatedArtifacts: false # boolean. Artifacts are propagated to Azure. Default: false.
    #artifactProvider: 'azureStorage' # 'azureStorage'. Required when propagatedArtifacts == notValid. Artifact Provider. Default: azureStorage.
    #ConnectedServiceNameARM: # string. Required when propagatedArtifacts == true. Azure Subscription. 
    #storageAccountName: # string. Required when propagatedArtifacts == true. Storage Account Name. 
    #containerName: # string. Required when propagatedArtifacts == true. Container Name. 
    #commonVirtualPath: # string. Optional. Use when propagatedArtifacts == true. Common Virtual Path.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Jenkins Download Artifacts v1
# Download artifacts produced by a Jenkins job.
- task: JenkinsDownloadArtifacts@1
  inputs:
    jenkinsServerConnection: # string. Alias: serverEndpoint. Required. Jenkins service connection. 
    jobName: # string. Required. Job name. 
    #jenkinsJobType: # string. Optional. Use when jobName = invalidjobName. Jenkins job type. 
    saveTo: 'jenkinsArtifacts' # string. Required. Save to. Default: jenkinsArtifacts.
  # Advanced
    jenkinsBuild: 'LastSuccessfulBuild' # 'LastSuccessfulBuild' | 'BuildNumber'. Required. Download artifacts produced by. Default: LastSuccessfulBuild.
    #jenkinsBuildNumber: '1' # string. Required when jenkinsBuild == BuildNumber. Jenkins build number. Default: 1.
    #itemPattern: '**' # string. Item Pattern. Default: **.
    #downloadCommitsAndWorkItems: false # boolean. Download Commits and WorkItems. Default: false.
    #startJenkinsBuildNumber: # string. Optional. Use when downloadCommitsAndWorkItems == true && jenkinsBuild == BuildNumber. Download commits and work items from. 
    #artifactDetailsFileNameSuffix: # string. Optional. Use when downloadCommitsAndWorkItems == invalid. Commit and WorkItem FileName. 
  # Propagated Artifacts
    #propagatedArtifacts: false # boolean. Artifacts are propagated to Azure. Default: false.
    #artifactProvider: 'azureStorage' # 'azureStorage'. Required when propagatedArtifacts == notValid. Artifact Provider. Default: azureStorage.
    #ConnectedServiceNameARM: # string. Required when propagatedArtifacts == true. Azure Subscription. 
    #storageAccountName: # string. Required when propagatedArtifacts == true. Storage Account Name. 
    #containerName: # string. Required when propagatedArtifacts == true. Container Name. 
    #commonVirtualPath: # string. Optional. Use when propagatedArtifacts == true. Common Virtual Path.
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

<!-- :::item name="jenkinsServerConnection"::: -->
:::moniker range=">=azure-pipelines-2019"

**`jenkinsServerConnection`** - **Jenkins service connection**<br>
Input alias: `serverEndpoint`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the service connection for your Jenkins instance. To create one, click the Manage link and create a new Jenkins service connection.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`jenkinsServerConnection`** - **Jenkins service endpoint**<br>
Input alias: `serverEndpoint`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the service connection for your Jenkins instance. To create one, click the Manage link and create a new Jenkins service connection.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jobName"::: -->
:::moniker range="<=azure-pipelines"

**`jobName`** - **Job name**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of the Jenkins job to download artifacts from.  This must exactly match the job name on the Jenkins server.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jenkinsJobType"::: -->
:::moniker range="<=azure-pipelines"

**`jenkinsJobType`** - **Jenkins job type**<br>
`string`. Optional. Use when `jobName = invalidjobName`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Jenkins job type, detected automatically.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="saveTo"::: -->
:::moniker range="<=azure-pipelines"

**`saveTo`** - **Save to**<br>
`string`. Required. Default value: `jenkinsArtifacts`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Jenkins artifacts will be downloaded and saved to this directory.  This directory will be created if it does not exist.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jenkinsBuild"::: -->
:::moniker range="<=azure-pipelines"

**`jenkinsBuild`** - **Download artifacts produced by**<br>
`string`. Required. Allowed values: `LastSuccessfulBuild` (Last Successful Build), `BuildNumber` (Build Number). Default value: `LastSuccessfulBuild`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Download artifacts produced by the last successful build or from a specific build instance.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jenkinsBuildNumber"::: -->
:::moniker range="<=azure-pipelines"

**`jenkinsBuildNumber`** - **Jenkins build number**<br>
`string`. Required when `jenkinsBuild == BuildNumber`. Default value: `1`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Download artifacts produced by this build.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="itemPattern"::: -->
:::moniker range="<=azure-pipelines"

**`itemPattern`** - **Item Pattern**<br>
`string`. Default value: `**`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify files to be downloaded as multi line minimatch pattern. [More Information](/azure/devops/pipelines/tasks/file-matching-patterns) <p>The default pattern (`**`) will download all files across all artifacts produced by the Jenkins job. To download all files within artifact drop, use `drop/**`.</p>
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="downloadCommitsAndWorkItems"::: -->
:::moniker range="<=azure-pipelines"

**`downloadCommitsAndWorkItems`** - **Download Commits and WorkItems**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enables downloading the commits and work item details associated with the Jenkins Job.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="startJenkinsBuildNumber"::: -->
:::moniker range=">=azure-pipelines-2019"

**`startJenkinsBuildNumber`** - **Download commits and work items from**<br>
`string`. Optional. Use when `downloadCommitsAndWorkItems == true && jenkinsBuild == BuildNumber`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional start build number for downloading commits and work items. If provided, all commits and work items between start build number and build number given as input to download artifacts will be downloaded.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`startJenkinsBuildNumber`** - **Download commits and workitems from**<br>
`string`. Optional. Use when `downloadCommitsAndWorkItems == true && jenkinsBuild == BuildNumber`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional start build number for downloading commits and work items. If provided, all commits and work items between start build number and build number given as input to download artifacts will be downloaded.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="artifactDetailsFileNameSuffix"::: -->
:::moniker range="<=azure-pipelines"

**`artifactDetailsFileNameSuffix`** - **Commit and WorkItem FileName**<br>
`string`. Optional. Use when `downloadCommitsAndWorkItems == invalid`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional file name suffix for commits and work item attachments. Attachments will be created with commits_{suffix}.json and workitem_{suffix}.json. If this input is not provided, attachments will be created with the name commits.json and workitems.json.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="propagatedArtifacts"::: -->
:::moniker range="<=azure-pipelines"

**`propagatedArtifacts`** - **Artifacts are propagated to Azure**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Check this if Jenkins artifacts were propagated to Azure. To upload Jenkins artifacts to Azure, refer to this [Jenkins plugin](https://wiki.jenkins.io/display/JENKINS/Windows+Azure+Storage+Plugin).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="artifactProvider"::: -->
:::moniker range="<=azure-pipelines"

**`artifactProvider`** - **Artifact Provider**<br>
`string`. Required when `propagatedArtifacts == notValid`. Allowed values: `azureStorage` (Azure Storage). Default value: `azureStorage`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Choose the external storage provider used in Jenkins job to upload the artifacts.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ConnectedServiceNameARM"::: -->
:::moniker range="<=azure-pipelines"

**`ConnectedServiceNameARM`** - **Azure Subscription**<br>
`string`. Required when `propagatedArtifacts == true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Choose the Azure Resource Manager subscription for the artifacts.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="storageAccountName"::: -->
:::moniker range="<=azure-pipelines"

**`storageAccountName`** - **Storage Account Name**<br>
`string`. Required when `propagatedArtifacts == true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Azure Classic and Resource Manager storage accounts are listed. Select the storage account name in which the artifacts are propagated.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="containerName"::: -->
:::moniker range="<=azure-pipelines"

**`containerName`** - **Container Name**<br>
`string`. Required when `propagatedArtifacts == true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Name of the container in the storage account to which artifacts are uploaded.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="commonVirtualPath"::: -->
:::moniker range="<=azure-pipelines"

**`commonVirtualPath`** - **Common Virtual Path**<br>
`string`. Optional. Use when `propagatedArtifacts == true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to the artifacts inside the Azure storage container.
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

Use this task to download artifacts produced by a Jenkins job.
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
| Agent version |  2.144.0 or greater |
| Task category | Utility |

:::moniker-end

:::moniker range="<=azure-pipelines-2020.1"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version | All supported agent versions. |
| Task category | Utility |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
