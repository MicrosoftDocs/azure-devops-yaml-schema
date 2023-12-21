---
title: jobs.job.strategy definition
description: Execution strategy for this job.
ms.date: 12/21/2023
monikerRange: ">=azure-pipelines-2019"
---

# jobs.job.strategy definition

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Execution strategy for this job.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::parents::: -->
:::moniker range=">=azure-pipelines-2019"

Definitions that reference this definition: [pipeline](pipeline.md), [jobs.job](jobs-job.md)

:::moniker-end
<!-- :::parents-end::: -->

## Implementations

<!-- :::implementations-list::: -->
:::moniker range=">=azure-pipelines-2019"

| Implementation | Description |
|---|---|
| [strategy: matrix, maxParallel](#strategyobjectproperties) | Matrix job strategy. |
| [strategy: parallel](#strategyparallel) | Parallel job strategy. |

:::moniker-end
<!-- :::implementations-list-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::implementations::: -->
<!-- :::implementation-item name="strategy: object properties"::: -->
<a name="strategyobjectproperties"></a>
<!-- :::objectAnyOf::: -->
:::moniker range=">=azure-pipelines-2019"

<!-- :::implementation-signature::: -->
## strategy: matrix, maxParallel
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Use of a matrix generates copies of a job, each with different input.
These copies are useful for testing against different configurations or platform versions.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
strategy:
  matrix: # Matrix defining the job strategy; see the following examples.
    { string1: { string2: string3 }
  maxParallel: string # Maximum number of jobs running in parallel.
```
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-properties::: -->
### Properties

<!-- :::item name="matrix"::: -->
**`matrix`** { string1: { string2: string3 }.<br><!-- :::editable-content name="propDescription"::: -->
Matrix defining the job strategy; see the following examples.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="maxParallel"::: -->
**`maxParallel`** string.<br><!-- :::editable-content name="propDescription"::: -->
Maximum number of jobs running in parallel.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::implementation-properties-end::: -->

:::moniker-end
<!-- :::objectAnyOf-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
### Remarks

```yaml
strategy:
  matrix: { string1: { string2: string3 } }
  maxParallel: number
```

For each occurrence of *string1* in the matrix, a copy of the job is generated.
The name *string1* is the copy's name and is appended to the name of the job.
For each occurrence of *string2*, a variable called *string2* with the value *string3* is available to the job.

> [!NOTE]
> Matrix configuration names must contain only basic Latin alphabet letters (A-Z and a-z), digits (0-9), and underscores (`_`).
> They must start with a letter.
> Also, their length must be 100 characters or fewer.

The optional `maxParallel` keyword specifies the maximum number of simultaneous matrix legs to run at once.

::: moniker range=">= azure-pipelines-2020"

If `maxParallel` is unspecified or set to 0, no limit is applied.

::: moniker-end

::: moniker range=">= azure-pipelines-2019 <= azure-pipelines-2019.1"

If `maxParallel` is unspecified, no limit is applied.

::: moniker-end

> [!NOTE]
> The `matrix` syntax doesn't support automatic job scaling but you can implement similar
> functionality using the `each` keyword. For an example, see [expressions](/azure/devops/pipelines/process/expressions).
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
### Examples

#### Build on multiple platforms

This example uses a `matrix` job strategy to build on multiple platforms.

```yaml
# Build NodeJS Express app using Azure Pipelines
# https://learn.microsoft.com/azure/devops/pipelines/ecosystems/javascript?view=azure-devops
strategy:
  matrix:
    linux:
      imageName: 'ubuntu-latest'
    mac:
      imageName: 'macOS-latest'
    windows:
      imageName: 'windows-latest'

pool:
  vmImage: $(imageName)

steps:
- task: NodeTool@0
  inputs:
    versionSpec: '8.x'

- script: |
    npm install
    npm test

- task: PublishTestResults@2
  inputs:
    testResultsFiles: '**/TEST-RESULTS.xml'
    testRunTitle: 'Test results for JavaScript'

- task: PublishCodeCoverageResults@1
  inputs: 
    codeCoverageTool: Cobertura
    summaryFileLocation: '$(System.DefaultWorkingDirectory)/**/*coverage.xml'
    reportDirectory: '$(System.DefaultWorkingDirectory)/**/coverage'

- task: ArchiveFiles@2
  inputs:
    rootFolderOrFile: '$(System.DefaultWorkingDirectory)'
    includeRootFolder: false

- task: PublishBuildArtifacts@1
```

This pipeline uses  [script](./steps-script.md) to run in each platform's integral script interpreter: Bash on macOS and Linux, CMD on Windows.
See [multi-platform scripts](/azure/devops/pipelines/scripts/cross-platform-scripting) to learn more.

#### Build on multiple platforms using self-hosted and Microsoft-hosted agents

The following example builds on both a self-hosted agent and a Microsoft-hosted agent, by specifying both a `vmImage` and a `Pool` variable, like the following example. For the hosted agent, specify `Azure Pipelines` as the pool name, and for self-hosted agents, leave the `vmImage` blank. The blank `vmImage` for the self-hosted agent may result in some unusual entries in the logs but they won't affect the pipeline.

```yml
strategy:
  matrix:
    microsofthosted:
      poolName: Azure Pipelines
      vmImage: ubuntu-latest

    selfhosted:
      poolName: FabrikamPool
      vmImage:

pool:
  name: $(poolName)
  vmImage: $(vmImage)

steps:
- checkout: none
- script: echo test
```

#### Build using different Python versions

```yaml
jobs:
- job: Build
  strategy:
    matrix:
      Python35:
        PYTHON_VERSION: '3.5'
      Python36:
        PYTHON_VERSION: '3.6'
      Python37:
        PYTHON_VERSION: '3.7'
    maxParallel: 2
```

This matrix creates three jobs: "Build Python35," "Build Python36," and "Build Python37."
Within each job, a variable named PYTHON_VERSION is available.
In "Build Python35," the variable is set to "3.5".
It's likewise set to "3.6" in "Build Python36."
Only two jobs run simultaneously.
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->
<!-- :::implementation-item-end::: -->
<!-- :::implementation-item name="strategy: parallel"::: -->
<a name="strategyparallel"></a>
<!-- :::objectAnyOf::: -->
:::moniker range=">=azure-pipelines-2019"

<!-- :::implementation-signature::: -->
## strategy: parallel
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
The parallel job strategy specifies how many duplicates of a job should run.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
strategy:
  parallel: string # Run the job this many times.
```
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-properties::: -->
### Properties

<!-- :::item name="parallel"::: -->
**`parallel`** string.<br><!-- :::editable-content name="propDescription"::: -->
Run the job this many times.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::implementation-properties-end::: -->

:::moniker-end
<!-- :::objectAnyOf-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
### Remarks

The parallel job strategy is useful for slicing up a large test matrix.
The [Visual Studio Test task](/azure/devops/pipelines/tasks/reference/vstest-v2) understands how to divide the test load across the number of scheduled jobs.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
### Examples

```yaml
jobs:
- job: SliceItFourWays
  strategy:
    parallel: 4
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->
<!-- :::implementation-item-end::: -->
<!-- :::implementations-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
