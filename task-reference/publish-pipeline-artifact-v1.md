---
title: PublishPipelineArtifact@1 - Publish Pipeline Artifacts v1 task
description: Publish (upload) a file or directory as a named artifact for the current run.
ms.date: 09/01/2022
monikerRange: ">=azure-pipelines-2020"
---

# PublishPipelineArtifact@1 - Publish Pipeline Artifacts v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
Publish (upload) a file or directory as a named artifact for the current run.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2022"

```yaml
# Publish Pipeline Artifacts v1
# Publish (upload) a file or directory as a named artifact for the current run.
- task: PublishPipelineArtifact@1
  inputs:
    targetPath: '$(Pipeline.Workspace)' # string. Required. File or directory path. Default: '$(Pipeline.Workspace)'.
    #artifact: # string. Artifact name. 
    publishLocation: 'pipeline' # 'pipeline' | 'filepath'. Required. Artifact publish location. Default: 'pipeline'.
    #fileSharePath: # string. Required when artifactType = filepath. File share path. 
    #parallel: false # boolean. Optional. Use when artifactType = filepath. Parallel copy. Default: false.
    #parallelCount: '8' # string. Optional. Use when artifactType = filepath && parallel = true. Parallel count. Default: '8'.
    #properties: # string. Custom properties.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2020 <=azure-pipelines-2020.1"

```yaml
# Publish Pipeline Artifacts v1
# Publish (upload) a file or directory as a named artifact for the current run.
- task: PublishPipelineArtifact@1
  inputs:
    targetPath: '$(Pipeline.Workspace)' # string. Required. File or directory path. Default: '$(Pipeline.Workspace)'.
    #artifact: # string. Artifact name. 
    publishLocation: 'pipeline' # 'pipeline' | 'filepath'. Required. Artifact publish location. Default: 'pipeline'.
    #fileSharePath: # string. Required when artifactType = filepath. File share path. 
    #parallel: false # boolean. Optional. Use when artifactType = filepath. Parallel copy. Default: false.
    #parallelCount: '8' # string. Optional. Use when artifactType = filepath && parallel = true. Parallel count. Default: '8'.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="targetPath"::: -->
:::moniker range=">=azure-pipelines-2020"

**`targetPath`** - **File or directory path**<br>
Input alias: `path`. Type: string. Required. Default value: '$(Pipeline.Workspace)'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The path of the file or directory to publish. Can be absolute or relative to the default working directory. Can include [variables](https://go.microsoft.com/fwlink/?LinkID=550988), but wildcards are not supported. See [Artifacts in Azure Pipelines](/azure/devops/pipelines/artifacts/pipeline-artifacts).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="artifact"::: -->
:::moniker range=">=azure-pipelines-2020"

**`artifact`** - **Artifact name**<br>
Input alias: `artifactName`. Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Name of the artifact to publish. If not set, defaults to a unique ID scoped to the job. It can be whatever you want. For example: drop
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishLocation"::: -->
:::moniker range=">=azure-pipelines-2020"

**`publishLocation`** - **Artifact publish location**<br>
Input alias: `artifactType`. Type: string. Required. Allowed values: 'pipeline', 'filepath'. Default value: 'pipeline'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Choose whether to store the artifact in Azure Pipelines, or to copy it to a file share that must be accessible from the pipeline agent. Options: pipeline, filepath. Default value: pipeline
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="fileSharePath"::: -->
:::moniker range=">=azure-pipelines-2020"

**`fileSharePath`** - **File share path**<br>
Type: string. Required when artifactType = filepath.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The file share to which the artifact files will be copied. This can include variables. Example: \\\\my\\share\\$(Build.DefinitionName)\\$(Build.BuildNumber). Publishing artifacts from a Linux or macOS agent to a file share is not supported. For example: \server\folderName
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="parallel"::: -->
:::moniker range=">=azure-pipelines-2020"

**`parallel`** - **Parallel copy**<br>
Type: boolean. Optional. Use when artifactType = filepath. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select whether to copy files in parallel using multiple threads for greater potential throughput. If this setting is not enabled, one thread will be used. 
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="parallelCount"::: -->
:::moniker range=">=azure-pipelines-2020"

**`parallelCount`** - **Parallel count**<br>
Type: string. Optional. Use when artifactType = filepath && parallel = true. Default value: '8'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter the degree of parallelism, or number of threads used, to perform the copy. The value must be at least 1 and not greater than 128.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="properties"::: -->
:::moniker range=">=azure-pipelines-2022"

**`properties`** - **Custom properties**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter custom properties to associate with the artifact. Valid JSON string expected with all keys having the prefix 'user-'.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2020"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

Publishing is not supported in classic release pipelines.

The `publish` and `download` keywords are shortcuts for the PublishPipelineArtifact@1 and DownloadPipelineArtifact@2 tasks. See [steps.publish](/azure/devops/pipelines/yaml-schema/steps-publish) and [steps.download](/azure/devops/pipelines/yaml-schema/steps-download) for more details.

> [!TIP]
> You can use the [.artifactignore](/azure/devops/artifacts/reference/artifactignore) file to to control which files will be published.

[!INCLUDE [temp](includes/build-step-common-qa.md)]
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
| Agent version |  2.199 or greater |
| Task category | Utility |

:::moniker-end

:::moniker range=">=azure-pipelines-2020 <=azure-pipelines-2020.1"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.159.2 or greater |
| Task category | Utility |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

* Looking to get started with build artifacts? See [Artifacts in Azure Pipelines](/azure/devops/pipelines/artifacts/pipeline-artifacts).
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->