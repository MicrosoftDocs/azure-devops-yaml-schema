---
title: CopyFiles@2 - Copy files v2 task
description: Copy files from a source folder to a target folder using patterns matching file paths (not folder paths).
ms.date: 04/16/2024
monikerRange: "<=azure-pipelines"
---

# CopyFiles@2 - Copy files v2 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to copy files from a source folder to a target folder using match patterns. (The match patterns will only match file paths, not folder paths).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2022"

```yaml
# Copy files v2
# Copy files from a source folder to a target folder using patterns matching file paths (not folder paths).
- task: CopyFiles@2
  inputs:
    #SourceFolder: # string. Source Folder. 
    Contents: '**' # string. Required. Contents. Default: **.
    TargetFolder: # string. Required. Target Folder. 
  # Advanced
    #CleanTargetFolder: false # boolean. Clean Target Folder. Default: false.
    #OverWrite: false # boolean. Overwrite. Default: false.
    #flattenFolders: false # boolean. Flatten Folders. Default: false.
    #preserveTimestamp: false # boolean. Preserve Target Timestamp. Default: false.
    #retryCount: '0' # string. Retry count to copy the file. Default: 0.
    #delayBetweenRetries: '1000' # string. Delay between two retries. Default: 1000.
    #ignoreMakeDirErrors: false # boolean. Ignore errors during creation of target folder. Default: false.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2019.1 <=azure-pipelines-2020.1"

```yaml
# Copy files v2
# Copy files from a source folder to a target folder using patterns matching file paths (not folder paths).
- task: CopyFiles@2
  inputs:
    #SourceFolder: # string. Source Folder. 
    Contents: '**' # string. Required. Contents. Default: **.
    TargetFolder: # string. Required. Target Folder. 
  # Advanced
    #CleanTargetFolder: false # boolean. Clean Target Folder. Default: false.
    #OverWrite: false # boolean. Overwrite. Default: false.
    #flattenFolders: false # boolean. Flatten Folders. Default: false.
    #preserveTimestamp: false # boolean. Preserve Target Timestamp. Default: false.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Copy Files v2
# Copy files from source folder to target folder using match patterns (The match patterns will only match file paths, not folder paths).
- task: CopyFiles@2
  inputs:
    #SourceFolder: # string. Source Folder. 
    Contents: '**' # string. Required. Contents. Default: **.
    TargetFolder: # string. Required. Target Folder. 
  # Advanced
    #CleanTargetFolder: false # boolean. Clean Target Folder. Default: false.
    #OverWrite: false # boolean. Overwrite. Default: false.
    #flattenFolders: false # boolean. Flatten Folders. Default: false.
```

:::moniker-end


<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="SourceFolder"::: -->
:::moniker range="<=azure-pipelines"

**`SourceFolder`** - **Source Folder**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. The folder that contains the files you want to copy. If the folder is empty, then the task copies files from the root folder of the repo as though [**`$(Build.SourcesDirectory)`**](/azure/devops/pipelines/build/variables) was specified.

If your build produces artifacts outside of the sources directory, specify `$(Agent.BuildDirectory)` to copy files from the directory created for the pipeline.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Contents"::: -->
:::moniker range="<=azure-pipelines"

**`Contents`** - **Contents**<br>
`string`. Required. Default value: `**`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The file paths to include as part of the copy. This string supports multiple lines of match patterns.

For example:

* `*` copies all files in the specified source folder.
* `**` copies all files in the specified source folder and all files in all sub-folders.
* `**\bin\**` copies all files recursively from any bin folder.

The pattern is used to match only file paths, not folder paths. Specify patterns, such as `**\bin\**` instead of `**\bin`.

Use the path separator that matches your build agent type. For example, `/` must be used for Linux agents. More examples are shown below.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="TargetFolder"::: -->
:::moniker range="<=azure-pipelines"

**`TargetFolder`** - **Target Folder**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The target folder or UNC path that will contain the copied files. You can use [variables](/azure/devops/pipelines/build/variables). Example: `$(build.artifactstagingdirectory)`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="CleanTargetFolder"::: -->
:::moniker range="<=azure-pipelines"

**`CleanTargetFolder`** - **Clean Target Folder**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Deletes all existing files in the target folder before the copy process.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="OverWrite"::: -->
:::moniker range="<=azure-pipelines"

**`OverWrite`** - **Overwrite**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Replaces the existing files in the target folder.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="flattenFolders"::: -->
:::moniker range="<=azure-pipelines"

**`flattenFolders`** - **Flatten Folders**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Flattens the folder structure and copies all files into the specified target folder.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="preserveTimestamp"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`preserveTimestamp`** - **Preserve Target Timestamp**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Preserves the target file timestamp by using the original source file.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="retryCount"::: -->
:::moniker range=">=azure-pipelines-2022"

**`retryCount`** - **Retry count to copy the file**<br>
`string`. Default value: `0`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the retry count to copy the file. This string is useful for intermittent issues, such as UNC target paths on a remote host.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="delayBetweenRetries"::: -->
:::moniker range=">=azure-pipelines-2022"

**`delayBetweenRetries`** - **Delay between two retries.**<br>
`string`. Default value: `1000`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the delay between two retries. This string is useful for intermittent issues, such as UNC target paths on a remote host.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ignoreMakeDirErrors"::: -->
:::moniker range=">=azure-pipelines-2022"

**`ignoreMakeDirErrors`** - **Ignore errors during creation of target folder.**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Ignores errors that occur during the creation of the target folder. This string is useful for avoiding issues with the parallel execution of tasks by several agents within one target folder.
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

If no files match, the task will still report success.

* If `Overwrite` is `false` and a matched file already exists in the target folder, the task will not report failure but log that the file already exists and skip it.
* If `Overwrite` is `true` and a matched file already exists in the target folder, the matched file will be overwritten.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

### Copy file to artifacts staging directory and publish

```yaml
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

### Copy executables and a readme file

#### Goal

You want to copy just the readme and the files needed to run this C# console app:

```
`-- ConsoleApplication1
    |-- ConsoleApplication1.sln
    |-- readme.txt
    `-- ClassLibrary1
        |-- ClassLibrary1.csproj
    `-- ClassLibrary2
        |-- ClassLibrary2.csproj
    `-- ConsoleApplication1
        |-- ConsoleApplication1.csproj
```

> [!NOTE]
> _ConsoleApplication1.sln_ contains a _bin_ folder with .dll and .exe files, see the Results below to see what gets moved!

On the Variables tab, ```$(BuildConfiguration)``` is set to ```release```.

#### [YAML](#tab/yaml/)

**Example with multiple match patterns:**

```yaml
steps:
- task: CopyFiles@2
  displayName: 'Copy Files to: $(Build.ArtifactStagingDirectory)'
  inputs:
    Contents: |
      ConsoleApplication1\ConsoleApplication1\bin\**\*.exe
      ConsoleApplication1\ConsoleApplication1\bin\**\*.dll
      ConsoleApplication1\readme.txt
    TargetFolder: '$(Build.ArtifactStagingDirectory)'
```

**Example with OR condition:**

```yaml
steps:
- task: CopyFiles@2
  displayName: 'Copy Files to: $(Build.ArtifactStagingDirectory)'
  inputs:
    Contents: |
      ConsoleApplication1\ConsoleApplication1\bin\**\?(*.exe|*.dll)
      ConsoleApplication1\readme.txt
    TargetFolder: '$(Build.ArtifactStagingDirectory)'
```

**Example with NOT condition:**

```yaml
steps:
- task: CopyFiles@2
  displayName: 'Copy Files to: $(Build.ArtifactStagingDirectory)'
  inputs:
    Contents: |
      ConsoleApplication1\**\bin\**\!(*.pdb|*.config)
      !ConsoleApplication1\**\ClassLibrary*\**
      ConsoleApplication1\readme.txt
    TargetFolder: '$(Build.ArtifactStagingDirectory)'
```

**Example with variables in content section**

```yaml
- task: CopyFiles@2
  inputs:
    Contents: '$(Build.Repository.LocalPath)/**' 
    TargetFolder: '$(Build.ArtifactStagingDirectory)'
```


#### [Classic](#tab/classic/)

* Source folder

  ```
  $(Build.SourcesDirectory)
  ```

* Contents

    **Example with multiple match patterns:**

    ```
    ConsoleApplication1\ConsoleApplication1\bin\**\*.exe
    ConsoleApplication1\ConsoleApplication1\bin\**\*.dll
    ConsoleApplication1\readme.txt
    ```

    **Example with OR condition:**
    ```
    ConsoleApplication1\ConsoleApplication1\bin\**\?(*.exe|*.dll)
    ConsoleApplication1\readme.txt
    ```

    **Example with NOT condition:**
    ```
    ConsoleApplication1\**\bin\**\!(*.pdb|*.config)
    !ConsoleApplication1\**\ClassLibrary*\**
    ConsoleApplication1\readme.txt
    ```

* Target folder

  ```
  $(Build.ArtifactStagingDirectory)
  ```

* * *
#### Results

These files are copied to the staging directory:

```
`-- ConsoleApplication1
    |-- readme.txt
    `-- ConsoleApplication1
        `-- bin
            `-- Release
                | -- ClassLibrary1.dll
                | -- ClassLibrary2.dll
                | -- ConsoleApplication1.exe
```

### Copy everything from the source directory except the .git folder


#### [YAML](#tab/yaml/)

**Example with multiple match patterns:**

```yaml
steps:
- task: CopyFiles@2
  displayName: 'Copy Files to: $(Build.ArtifactStagingDirectory)'
  inputs:
    SourceFolder: '$(Build.SourcesDirectory)'
    Contents: |
      **/*
      !.git/**/*
    TargetFolder: '$(Build.ArtifactStagingDirectory)'
```

#### [Classic](#tab/classic/)

* Source folder

  ```
  $(Build.SourcesDirectory)
  ```

* Contents

**Example with multiple match patterns:**

 ```
     **/*
     !.git/**/*
```

* Target folder

  ```
  $(Build.ArtifactStagingDirectory)
  ```

* * *
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range=">=azure-pipelines-2022"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | This task runs using the following [command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions): restricted |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | This task has permission to [set the following variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions): Setting variables is disabled |
| Agent version |  2.182.1 or greater |
| Task category | Utility |

:::moniker-end

:::moniker range="<=azure-pipelines-2020.1"

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
* [How do I use this task to publish artifacts](/azure/devops/pipelines/artifacts/pipeline-artifacts)
* Learn how to use [verbose logs](/azure/devops/pipelines/troubleshooting/review-logs#configure-verbose-logs) for [troubleshooting](/azure/devops/pipelines/troubleshooting/troubleshooting).
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
