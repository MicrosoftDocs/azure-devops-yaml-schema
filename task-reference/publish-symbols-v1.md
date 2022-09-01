---
title: PublishSymbols@1 - Index sources and publish symbols v1 task
description: Index your source code and publish symbols to a file share.
ms.date: 09/01/2022
monikerRange: "<=azure-pipelines"
---

# PublishSymbols@1 - Index sources and publish symbols v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Index your source code and publish symbols to a file share.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019"

```yaml
# Index sources and publish symbols v1
# Index your source code and publish symbols to a file share.
- task: PublishSymbols@1
  inputs:
    #SymbolsPath: # string. Path to publish symbols. 
    SearchPattern: '**/bin/**/*.pdb' # string. Required. Search pattern. Default: '**/bin/**/*.pdb'.
    #SymbolsFolder: # string. Path to symbols folder. 
  # Advanced
    #SkipIndexing: false # boolean. Skip indexing. Default: false.
    #TreatNotIndexedAsWarning: false # boolean. Warn if not indexed. Default: false.
    #SymbolsMaximumWaitTime: # string. Max wait time (min). 
    #SymbolsProduct: # string. Product. 
    #SymbolsVersion: # string. Version. 
    #SymbolsArtifactName: 'Symbols_$(BuildConfiguration)' # string. Artifact name. Default: 'Symbols_$(BuildConfiguration)'.
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

<!-- :::item name="SymbolsPath"::: -->
:::moniker range="<=azure-pipelines"

**`SymbolsPath`** - **Path to publish symbols**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the path to the symbol store share.  If this value is not set, source indexing will occur but symbols will not be published.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SearchPattern"::: -->
:::moniker range="<=azure-pipelines"

**`SearchPattern`** - **Search pattern**<br>
Type: string. Required. Default value: '**/bin/**/*.pdb'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The pattern used to discover the pdb files to publish.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SymbolsFolder"::: -->
:::moniker range="<=azure-pipelines"

**`SymbolsFolder`** - **Path to symbols folder**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The path to the folder that is searched for symbol files.  The default is $(Build.SourcesDirectory).  Otherwise specify a rooted path, for example: $(Build.BinariesDirectory)/MyProject.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SkipIndexing"::: -->
:::moniker range="<=azure-pipelines"

**`SkipIndexing`** - **Skip indexing**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Indicates whether to skip injecting source server information into the PDB files.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="TreatNotIndexedAsWarning"::: -->
:::moniker range="<=azure-pipelines"

**`TreatNotIndexedAsWarning`** - **Warn if not indexed**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Indicates whether to warn if sources are not indexed for a PDB file. Otherwise the messages are logged as normal output.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SymbolsMaximumWaitTime"::: -->
:::moniker range="<=azure-pipelines"

**`SymbolsMaximumWaitTime`** - **Max wait time (min)**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The number of minutes to wait before failing the step.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SymbolsProduct"::: -->
:::moniker range="<=azure-pipelines"

**`SymbolsProduct`** - **Product**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the product parameter to symstore.exe.  The default is $(Build.DefinitionName).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SymbolsVersion"::: -->
:::moniker range="<=azure-pipelines"

**`SymbolsVersion`** - **Version**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the version parameter to symstore.exe.  The default is $(Build.BuildNumber).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SymbolsArtifactName"::: -->
:::moniker range="<=azure-pipelines"

**`SymbolsArtifactName`** - **Artifact name**<br>
Type: string. Default value: 'Symbols_$(BuildConfiguration)'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the artifact name to use for the Symbols artifact.  The default is Symbols_$(BuildConfiguration).
<!-- :::editable-content-end::: -->

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
| Pipeline types | YAML, Classic build |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.95.0 or greater |
| Task category | Build |

:::moniker-end

:::moniker range="=azure-pipelines-2018"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build |
| Runs on | All |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.95.0 or greater |
| Task category | Build |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->