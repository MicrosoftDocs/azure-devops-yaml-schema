---
title: PublishBuildArtifacts@1 - Publish build artifacts v1 task
description: Publish build artifacts to Azure Pipelines or a Windows file share.
ms.date: 10/21/2022
monikerRange: "<=azure-pipelines"
---

# PublishBuildArtifacts@1 - Publish build artifacts v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Publish build artifacts to Azure Pipelines or a Windows file share.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Publish build artifacts to Azure Pipelines/TFS or a file share.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2018"

<!-- :::editable-content name="description"::: -->
Publish build artifacts to Visual Studio Team Services/TFS or a file share.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2022"

```yaml
# Publish build artifacts v1
# Publish build artifacts to Azure Pipelines or a Windows file share.
- task: PublishBuildArtifacts@1
  inputs:
    PathtoPublish: '$(Build.ArtifactStagingDirectory)' # string. Required. Path to publish. Default: $(Build.ArtifactStagingDirectory).
    ArtifactName: 'drop' # string. Required. Artifact name. Default: drop.
    publishLocation: 'Container' # 'Container' | 'FilePath'. Alias: ArtifactType. Required. Artifact publish location. Default: Container.
    #TargetPath: # string. Required when ArtifactType = FilePath. File share path. 
    #Parallel: false # boolean. Optional. Use when ArtifactType = FilePath. Parallel copy. Default: false.
    #ParallelCount: '8' # string. Optional. Use when ArtifactType = FilePath && Parallel = true. Parallel count. Default: 8.
  # Advanced
    #FileCopyOptions: # string. Optional. Use when ArtifactType = FilePath. File copy options. 
    #StoreAsTar: false # boolean. Tar the artifact before uploading. Default: false.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2020 <=azure-pipelines-2020.1"

```yaml
# Publish build artifacts v1
# Publish build artifacts to Azure Pipelines or a Windows file share.
- task: PublishBuildArtifacts@1
  inputs:
    PathtoPublish: '$(Build.ArtifactStagingDirectory)' # string. Required. Path to publish. Default: $(Build.ArtifactStagingDirectory).
    ArtifactName: 'drop' # string. Required. Artifact name. Default: drop.
    publishLocation: 'Container' # 'Container' | 'FilePath'. Alias: ArtifactType. Required. Artifact publish location. Default: Container.
    #TargetPath: # string. Required when ArtifactType = FilePath. File share path. 
    #Parallel: false # boolean. Optional. Use when ArtifactType = FilePath. Parallel copy. Default: false.
    #ParallelCount: '8' # string. Optional. Use when ArtifactType = FilePath && Parallel = true. Parallel count. Default: 8.
  # Advanced
    #FileCopyOptions: # string. Optional. Use when ArtifactType = FilePath. File copy options.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

```yaml
# Publish build artifacts v1
# Publish build artifacts to Azure Pipelines or a Windows file share.
- task: PublishBuildArtifacts@1
  inputs:
    PathtoPublish: '$(Build.ArtifactStagingDirectory)' # string. Required. Path to publish. Default: $(Build.ArtifactStagingDirectory).
    ArtifactName: 'drop' # string. Required. Artifact name. Default: drop.
    publishLocation: 'Container' # 'Container' | 'FilePath'. Alias: ArtifactType. Required. Artifact publish location. Default: Container.
    #TargetPath: # string. Required when ArtifactType = FilePath. File share path. 
    #Parallel: false # boolean. Optional. Use when ArtifactType = FilePath. Parallel copy. Default: false.
    #ParallelCount: '8' # string. Optional. Use when ArtifactType = FilePath && Parallel = true. Parallel count. Default: 8.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Publish Build Artifacts v1
# Publish build artifacts to Azure Pipelines/TFS or a file share.
- task: PublishBuildArtifacts@1
  inputs:
    PathtoPublish: '$(Build.ArtifactStagingDirectory)' # string. Required. Path to publish. Default: $(Build.ArtifactStagingDirectory).
    ArtifactName: 'drop' # string. Required. Artifact name. Default: drop.
    publishLocation: 'Container' # 'Container' | 'FilePath'. Alias: ArtifactType. Required. Artifact publish location. Default: Container.
    #TargetPath: # string. Required when ArtifactType = FilePath. File share path. 
    #Parallel: false # boolean. Optional. Use when ArtifactType = FilePath. Parallel copy. Default: false.
    #ParallelCount: '8' # string. Optional. Use when ArtifactType = FilePath && Parallel = true. Parallel count. Default: 8.
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

<!-- :::item name="PathtoPublish"::: -->
:::moniker range=">=azure-pipelines-2019"

**`PathtoPublish`** - **Path to publish**<br>
`string`. Required. Default value: `$(Build.ArtifactStagingDirectory)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The folder or file path to publish. This can be a fully-qualified path or a path relative to the root of the repository. Wildcards are not supported. [Variables](/azure/devops/pipelines/build/variables) are supported. Example: `$(Build.ArtifactStagingDirectory)`. For more information, see [Artifacts in pipelines - overview](/azure/devops/pipelines/artifacts/artifacts-overview).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`PathtoPublish`** - **Path to publish**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The folder or file path to publish. This can be a fully-qualified path or a path relative to the root of the repository. Wildcards are not supported. [Variables](/azure/devops/pipelines/build/variables) are supported. Example: `$(Build.ArtifactStagingDirectory)`. For more information, see [Artifacts in pipelines - overview](/azure/devops/pipelines/artifacts/artifacts-overview).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ArtifactName"::: -->
:::moniker range=">=azure-pipelines-2019"

**`ArtifactName`** - **Artifact name**<br>
`string`. Required. Default value: `drop`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of the artifact to create in the publish location.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`ArtifactName`** - **Artifact name**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of the artifact to create in the publish location.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishLocation"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`publishLocation`** - **Artifact publish location**<br>
Input alias: `ArtifactType`. `string`. Required. Allowed values: `Container` (Azure Pipelines), `FilePath` (A file share). Default value: `Container`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Choose whether to store the artifact in Azure Pipelines (Container), or to copy it to a file share (FilePath) that must be accessible from the build agent. For more information, see [Artifacts in Azure Pipelines](/azure/devops/pipelines/artifacts/build-artifacts).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2019"

**`publishLocation`** - **Artifact publish location**<br>
Input alias: `ArtifactType`. `string`. Required. Allowed values: `Container` (Azure Pipelines/TFS), `FilePath` (A file share). Default value: `Container`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Choose whether to store the artifact in Azure Pipelines (Container), or to copy it to a file share (FilePath) that must be accessible from the build agent. For more information, see [Artifacts in Azure Pipelines](/azure/devops/pipelines/artifacts/build-artifacts).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`publishLocation`** - **Artifact publish location**<br>
Input alias: `ArtifactType`. `string`. Required. Allowed values: `Container` (Visual Studio Team Services/TFS), `FilePath` (A file share).<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Choose whether to store the artifact in Azure Pipelines (Container), or to copy it to a file share (FilePath) that must be accessible from the build agent. For more information, see [Artifacts in Azure Pipelines](/azure/devops/pipelines/artifacts/build-artifacts).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="TargetPath"::: -->
:::moniker range=">=azure-pipelines-2019"

**`TargetPath`** - **File share path**<br>
`string`. Required when `ArtifactType = FilePath`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the path to the file share where you want to copy the files. The path must be a fully-qualified path or a valid path relative to the root directory of your repository. Publishing artifacts from a Linux or macOS agent to a file share is not supported. Example: `\\my\share\$(Build.DefinitionName)\$(Build.BuildNumber)`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`TargetPath`** - **File share path**<br>
`string`. Optional. Use when `ArtifactType = FilePath`. Default value: `\\my\share\$(Build.DefinitionName)\$(Build.BuildNumber)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the path to the file share where you want to copy the files. The path must be a fully-qualified path or a valid path relative to the root directory of your repository. Publishing artifacts from a Linux or macOS agent to a file share is not supported. Example: `\\my\share\$(Build.DefinitionName)\$(Build.BuildNumber)`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Parallel"::: -->
:::moniker range="<=azure-pipelines"

**`Parallel`** - **Parallel copy**<br>
`boolean`. Optional. Use when `ArtifactType = FilePath`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select whether to copy files in parallel using multiple threads for greater potential throughput. If this setting is not enabled, a single thread will be used.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ParallelCount"::: -->
:::moniker range="<=azure-pipelines"

**`ParallelCount`** - **Parallel count**<br>
`string`. Optional. Use when `ArtifactType = FilePath && Parallel = true`. Default value: `8`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter the degree of parallelism (the number of threads) used to perform the copy. The value must be at least 1 and not greater than 128. Choose a value based on CPU capabilities of the build agent.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="FileCopyOptions"::: -->
:::moniker range=">=azure-pipelines-2020"

**`FileCopyOptions`** - **File copy options**<br>
`string`. Optional. Use when `ArtifactType = FilePath`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Pass additional options to the Robocopy command. For example, the recursive minimatch pattern `**/*`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="StoreAsTar"::: -->
:::moniker range=">=azure-pipelines-2022"

**`StoreAsTar`** - **Tar the artifact before uploading**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Add all files from the publish path to a tar archive before uploading. This allows you to preserve the UNIX file permissions. Use `extractTars` option of the[DownloadBuildArtifacts](download-build-artifacts-v1.md) task to extract the downloaded items automatically. This setting is ignored on Windows agents.
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

> [!NOTE]
> You cannot use **Bin**, **App_Data** and other folder names reserved by IIS as an Artifact name because this content is not served in response to Web requests. Please see [ASP.NET Web Project Folder Structure](/previous-versions/ex526337(v=vs.140)) for more details.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

```yml
steps:
- task: CopyFiles@2
  inputs:
    contents: '_buildOutput/**'
    targetFolder: $(Build.ArtifactStagingDirectory)
- task: PublishBuildArtifacts@1
  inputs:
    pathToPublish: $(Build.ArtifactStagingDirectory)
    artifactName: MyBuildOutputs
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range="<=azure-pipelines"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.91.0 or greater |
| Task category | Utility |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

* [File matching patterns reference](/azure/devops/pipelines/tasks/file-matching-patterns)
* [How do I use this task to publish artifacts](/devops/pipelines/artifacts/pipeline-artifacts)
* Learn how to use [verbose logs](/azure/devops/pipelines/troubleshooting/review-logs#configure-verbose-logs) for [troubleshooting](/azure/devops/pipelines/troubleshooting/troubleshooting).
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->