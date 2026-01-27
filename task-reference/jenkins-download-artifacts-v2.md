---
title: JenkinsDownloadArtifacts@2 - Jenkins download artifacts v2 task
description: Download artifacts produced by a Jenkins job.
ms.date: 01/27/2026
monikerRange: "=azure-pipelines || =azure-pipelines-server"
author: ramiMSFT
ms.author: rabououn
---

# JenkinsDownloadArtifacts@2 - Jenkins download artifacts v2 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-server"

<!-- :::editable-content name="description"::: -->
Download artifacts produced by a Jenkins job.

> [!NOTE]
> This version of the task uses Azure RBAC to connect to Azure storage. For more information, see [Configure Azure RBAC to access Azure storage](#configure-azure-rbac-to-access-azure-storage).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-server"

```yaml
# Jenkins download artifacts v2
# Download artifacts produced by a Jenkins job.
- task: JenkinsDownloadArtifacts@2
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
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="jenkinsServerConnection"::: -->
:::moniker range=">=azure-pipelines-server"

**`jenkinsServerConnection`** - **Jenkins service connection**<br>
[Input alias](index.md#what-are-task-input-aliases): `serverEndpoint`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the service connection for your Jenkins instance. To create one, click the Manage link and create a new Jenkins service connection.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jobName"::: -->
:::moniker range=">=azure-pipelines-server"

**`jobName`** - **Job name**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of the Jenkins job to download artifacts from.  This must exactly match the job name on the Jenkins server.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jenkinsJobType"::: -->
:::moniker range=">=azure-pipelines-server"

**`jenkinsJobType`** - **Jenkins job type**<br>
`string`. Optional. Use when `jobName = invalidjobName`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Jenkins job type, detected automatically.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="saveTo"::: -->
:::moniker range=">=azure-pipelines-server"

**`saveTo`** - **Save to**<br>
`string`. Required. Default value: `jenkinsArtifacts`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Jenkins artifacts will be downloaded and saved to this directory.  This directory will be created if it does not exist.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jenkinsBuild"::: -->
:::moniker range=">=azure-pipelines-server"

**`jenkinsBuild`** - **Download artifacts produced by**<br>
`string`. Required. Allowed values: `LastSuccessfulBuild` (Last Successful Build), `BuildNumber` (Build Number). Default value: `LastSuccessfulBuild`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Download artifacts produced by the last successful build, or from a specific build instance.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jenkinsBuildNumber"::: -->
:::moniker range=">=azure-pipelines-server"

**`jenkinsBuildNumber`** - **Jenkins build number**<br>
`string`. Required when `jenkinsBuild == BuildNumber`. Default value: `1`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Download artifacts produced by this build.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="itemPattern"::: -->
:::moniker range=">=azure-pipelines-server"

**`itemPattern`** - **Item Pattern**<br>
`string`. Default value: `**`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify files to be downloaded as multi line minimatch pattern. [More Information](https://aka.ms/minimatchexamples) <p>The default pattern (\*\*) will download all files across all artifacts produced by the Jenkins job. To download all files within artifact drop use drop/**.</p>.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="downloadCommitsAndWorkItems"::: -->
:::moniker range=">=azure-pipelines-server"

**`downloadCommitsAndWorkItems`** - **Download Commits and WorkItems**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enables downloading the commits and work item details associated with the Jenkins Job.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="startJenkinsBuildNumber"::: -->
:::moniker range=">=azure-pipelines-server"

**`startJenkinsBuildNumber`** - **Download commits and work items from**<br>
`string`. Optional. Use when `downloadCommitsAndWorkItems == true && jenkinsBuild == BuildNumber`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional start build number for downloading commits and work items. If provided, all commits and work items between start build number and build number given as input to download artifacts will be downloaded.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="artifactDetailsFileNameSuffix"::: -->
:::moniker range=">=azure-pipelines-server"

**`artifactDetailsFileNameSuffix`** - **Commit and WorkItem FileName**<br>
`string`. Optional. Use when `downloadCommitsAndWorkItems == invalid`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional file name suffix for commits and work item attachments. Attachments will be created with commits_{suffix}.json and workitem_{suffix}.json. If this input is not provided, attachments will be created with the name commits.json and workitems.json.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="propagatedArtifacts"::: -->
:::moniker range=">=azure-pipelines-server"

**`propagatedArtifacts`** - **Artifacts are propagated to Azure**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Check this if Jenkins artifacts were propagated to Azure. To upload Jenkins artifacts to azure, refer to this [Jenkins plugin](https://wiki.jenkins.io/display/JENKINS/Windows+Azure+Storage+Plugin).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="artifactProvider"::: -->
:::moniker range=">=azure-pipelines-server"

**`artifactProvider`** - **Artifact Provider**<br>
`string`. Required when `propagatedArtifacts == notValid`. Allowed values: `azureStorage` (Azure Storage). Default value: `azureStorage`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Choose the external storage provider used in Jenkins job to upload the artifacts.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ConnectedServiceNameARM"::: -->
:::moniker range=">=azure-pipelines-server"

**`ConnectedServiceNameARM`** - **Azure Subscription**<br>
`string`. Required when `propagatedArtifacts == true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Choose the Azure Resource Manager subscription for the artifacts.

> [!NOTE]
> This version of the task uses Azure RBAC to connect to Azure storage. For more information, see [Configure Azure RBAC to access Azure storage](#configure-azure-rbac-to-access-azure-storage).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="storageAccountName"::: -->
:::moniker range=">=azure-pipelines-server"

**`storageAccountName`** - **Storage Account Name**<br>
`string`. Required when `propagatedArtifacts == true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Azure Classic and Resource Manager stoarge accounts are listed. Select the Storage account name in which the artifacts are propagated.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="containerName"::: -->
:::moniker range=">=azure-pipelines-server"

**`containerName`** - **Container Name**<br>
`string`. Required when `propagatedArtifacts == true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Name of the container in the storage account to which artifacts are uploaded.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="commonVirtualPath"::: -->
:::moniker range=">=azure-pipelines-server"

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

:::moniker range=">=azure-pipelines-server"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

### Configure Azure RBAC to access Azure storage

This version of the task uses an [Azure Resource Manager service connection](/azure/devops/pipelines/library/connect-to-azure) configured using workload identity federation and Azure RBAC to connect to Azure storage instead of storage account keys or shared access signatures (SAS). To connect to Azure storage from this task, you must assign the [Storage Blob Data Contributor](/azure/role-based-access-control/built-in-roles/storage#storage-blob-data-contributor) role on the storage account to the identity of the service connection configured for `ConnectedServiceNameARM`. For more information, see [Assign an Azure role for access to blob data](/azure/storage/blobs/assign-azure-role-data-access) and [Steps to assign a role](/azure/role-based-access-control/role-assignments-steps).
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range=">=azure-pipelines-server"

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
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->