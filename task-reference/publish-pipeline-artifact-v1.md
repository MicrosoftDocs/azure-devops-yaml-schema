---
title: PublishPipelineArtifact@1 - Publish Pipeline Artifacts v1 task
description: Publish (upload) a file or directory as a named artifact for the current run.
ms.date: 07/02/2024
monikerRange: ">=azure-pipelines-2020"
---

# PublishPipelineArtifact@1 - Publish Pipeline Artifacts v1 task

<!-- :::description::: -->
:::moniker range="=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to publish (upload) a file or directory as a named artifact for the current run.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range=">=azure-pipelines-2020 <=azure-pipelines-2022.2"

<!-- :::editable-content name="description"::: -->
Use this task to publish (upload) a file or directory as a named artifact for the current run.

> [!IMPORTANT]
> This task is supported on Azure DevOps Services only. If you use it on Azure DevOps Server, you'll receive an error message similar to `Pipeline Artifact Task is not supported in on-premises. Please use Build Artifact Task instead.` Use [Publish Build Artifacts](publish-build-artifacts-v1.md) if you're using Azure DevOps Server or TFS 2018.
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
    targetPath: '$(Pipeline.Workspace)' # string. Alias: path. Required. File or directory path. Default: $(Pipeline.Workspace).
    #artifact: # string. Alias: artifactName. Artifact name. 
    publishLocation: 'pipeline' # 'pipeline' | 'filepath'. Alias: artifactType. Required. Artifact publish location. Default: pipeline.
    #fileSharePath: # string. Required when artifactType = filepath. File share path. 
    #parallel: false # boolean. Optional. Use when artifactType = filepath. Parallel copy. Default: false.
    #parallelCount: '8' # string. Optional. Use when artifactType = filepath && parallel = true. Parallel count. Default: 8.
    #properties: # string. Custom properties.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2020 <=azure-pipelines-2020.1"

```yaml
# Publish Pipeline Artifacts v1
# Publish (upload) a file or directory as a named artifact for the current run.
- task: PublishPipelineArtifact@1
  inputs:
    targetPath: '$(Pipeline.Workspace)' # string. Alias: path. Required. File or directory path. Default: $(Pipeline.Workspace).
    #artifact: # string. Alias: artifactName. Artifact name. 
    publishLocation: 'pipeline' # 'pipeline' | 'filepath'. Alias: artifactType. Required. Artifact publish location. Default: pipeline.
    #fileSharePath: # string. Required when artifactType = filepath. File share path. 
    #parallel: false # boolean. Optional. Use when artifactType = filepath. Parallel copy. Default: false.
    #parallelCount: '8' # string. Optional. Use when artifactType = filepath && parallel = true. Parallel count. Default: 8.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="targetPath"::: -->
:::moniker range=">=azure-pipelines-2020"

**`targetPath`** - **File or directory path**<br>
Input alias: `path`. `string`. Required. Default value: `$(Pipeline.Workspace)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the path of the file or directory to publish. Can be absolute or relative to the default working directory. Can include [variables](https://go.microsoft.com/fwlink/?LinkID=550988), but wildcards are not supported. See [Artifacts in Azure Pipelines](/azure/devops/pipelines/artifacts/pipeline-artifacts) for more information.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="artifact"::: -->
:::moniker range=">=azure-pipelines-2020"

**`artifact`** - **Artifact name**<br>
Input alias: `artifactName`. `string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of the artifact to publish. It can be any name you choose, for example `drop`. If not set, the default is a unique ID scoped to the job.

> [!IMPORTANT]
> Artifact name cannot contain `\`, `/`, `"`, `:`, `<`, `>`, `|`, `*`, or `?`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishLocation"::: -->
:::moniker range=">=azure-pipelines-2020"

**`publishLocation`** - **Artifact publish location**<br>
Input alias: `artifactType`. `string`. Required. Allowed values: `pipeline` (Azure Pipelines), `filepath` (A file share). Default value: `pipeline`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies whether to store the artifact in Azure Pipelines or to copy it to a file share that must be accessible from the pipeline agent.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="fileSharePath"::: -->
:::moniker range=">=azure-pipelines-2020"

**`fileSharePath`** - **File share path**<br>
`string`. Required when `artifactType = filepath`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the file share where the artifact files are copied. This can include variables, for example `\\my\\share\\$(Build.DefinitionName)\\$(Build.BuildNumber)`. Publishing artifacts from a Linux or macOS agent to a file share is not supported, for example `\\server\folderName`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="parallel"::: -->
:::moniker range=">=azure-pipelines-2020"

**`parallel`** - **Parallel copy**<br>
`boolean`. Optional. Use when `artifactType = filepath`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies whether to copy files in parallel using multiple threads for greater potential throughput. If this setting is not enabled, one thread will be used.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="parallelCount"::: -->
:::moniker range=">=azure-pipelines-2020"

**`parallelCount`** - **Parallel count**<br>
`string`. Optional. Use when `artifactType = filepath && parallel = true`. Default value: `8`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the degree of parallelism, or the number of threads used, to perform the copy. The value must be between 1 and 128.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="properties"::: -->
:::moniker range=">=azure-pipelines-2022"

**`properties`** - **Custom properties**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the custom properties to associate with the artifact. Use a valid JSON string with the prefix `user-` on all keys.
<!-- :::editable-content-end::: -->
<br>

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

> [!NOTE]
> Publish Pipeline Artifacts is not supported in on-premises. Please use [Publish Build Artifacts](publish-build-artifacts-v1.md) if you're using Azure DevOps Server or TFS 2018. If you use it on Azure DevOps Server, you'll receive an error message similar to `Pipeline Artifact Task is not supported in on-premises. Please use Build Artifact Task instead.`.

The `publish` and `download` keywords are shortcuts for the PublishPipelineArtifact@1 and DownloadPipelineArtifact@2 tasks. See [steps.publish](/azure/devops/pipelines/yaml-schema/steps-publish) and [steps.download](/azure/devops/pipelines/yaml-schema/steps-download) for more details.

> [!TIP]
> You can use the [.artifactignore](/azure/devops/artifacts/reference/artifactignore) file to control which files will be published.

[!INCLUDE [temp](includes/build-step-common-qa.md)]
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range="=azure-pipelines"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.199.0 or greater |
| Task category | Utility |

:::moniker-end

:::moniker range=">=azure-pipelines-2022 <=azure-pipelines-2022.2"

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
