---
title: VisualStudioTestPlatformInstaller@1 - Visual Studio test platform installer v1 task
description: Acquire the test platform from nuget.org or the tool cache. Satisfies the ‘vstest’ demand and can be used for running tests and collecting diagnostic data using the Visual Studio Test task.
ms.date: 07/02/2024
monikerRange: "<=azure-pipelines"
---

# VisualStudioTestPlatformInstaller@1 - Visual Studio test platform installer v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to acquire the [Microsoft test platform](https://www.nuget.org/packages/Microsoft.TestPlatform/) from nuget.org or a specified feed, and add it to the tools cache. The installer task satisfies the `vstest` demand, and a subsequent Visual Studio Test task in a build or release pipeline can run without needing a full Visual Studio install on the agent machine.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# Visual Studio test platform installer v1
# Acquire the test platform from nuget.org or the tool cache. Satisfies the ‘vstest’ demand and can be used for running tests and collecting diagnostic data using the Visual Studio Test task.
- task: VisualStudioTestPlatformInstaller@1
  inputs:
  # Package settings
    packageFeedSelector: 'nugetOrg' # 'nugetOrg' | 'customFeed' | 'netShare'. Required. Package Feed. Default: nugetOrg.
    #versionSelector: 'latestPreRelease' # 'latestPreRelease' | 'latestStable' | 'specificVersion'. Required when packageFeedSelector = nugetOrg || packageFeedSelector = customFeed. Version. Default: latestPreRelease.
    #testPlatformVersion: # string. Required when versionSelector = specificVersion. Test Platform Version. 
    #customFeed: # string. Required when packageFeedSelector = customFeed. Package Source. 
    #username: # string. Optional. Use when packageFeedSelector = customFeed. User Name. 
    #password: # string. Optional. Use when packageFeedSelector = customFeed. Password. 
    #netShare: # string. Required when packageFeedSelector = netShare. UNC Path.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Visual Studio Test Platform Installer v1
# Acquires the test platform from nuget.org or the tools cache. Satisfies the ‘vstest’ demand and can be used for running tests and collecting diagnostic data using the Visual Studio Test task.
- task: VisualStudioTestPlatformInstaller@1
  inputs:
  # Package settings
    packageFeedSelector: 'nugetOrg' # 'nugetOrg' | 'customFeed' | 'netShare'. Required. Package Feed. Default: nugetOrg.
    #versionSelector: 'latestPreRelease' # 'latestPreRelease' | 'latestStable' | 'specificVersion'. Required when packageFeedSelector = nugetOrg || packageFeedSelector = customFeed. Version. Default: latestPreRelease.
    #testPlatformVersion: # string. Required when versionSelector = specificVersion. Test Platform Version. 
    #customFeed: # string. Required when packageFeedSelector = customFeed. Package Source. 
    #username: # string. Optional. Use when packageFeedSelector = customFeed. User Name. 
    #password: # string. Optional. Use when packageFeedSelector = customFeed. Password. 
    #netShare: # string. Required when packageFeedSelector = netShare. UNC Path.
```

:::moniker-end


<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="packageFeedSelector"::: -->
:::moniker range=">=azure-pipelines-2019"

**`packageFeedSelector`** - **Package Feed**<br>
`string`. Required. Allowed values: `nugetOrg` (Official Nuget), `customFeed` (Custom Feed), `netShare` (Network path). Default value: `nugetOrg`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the feed where the task fetches the Visual Studio Test Platform NuGet package.

**`nugetOrg`** - **Official NuGet**: Acquires the [test platform package from NuGet](https://www.nuget.org/packages/Microsoft.TestPlatform/). This option requires internet connectivity on the agent machine.

**`customFeed`** - **Custom feed**: Acquires the test platform package from a custom feed or a package management feed in Azure DevOps or TFS.

**`netShare`** - **Network path**: Installs the test platform from a network share. The specified `Microsoft.TestPlatform.nupkg` version must be downloaded from NuGet and placed on a network share that the build/release agent can access.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="versionSelector"::: -->
:::moniker range=">=azure-pipelines-2019"

**`versionSelector`** - **Version**<br>
`string`. Required when `packageFeedSelector = nugetOrg || packageFeedSelector = customFeed`. Allowed values: `latestPreRelease` (Latest (Includes Pre-Release)), `latestStable` (Latest Stable), `specificVersion` (Specific Version). Default value: `latestPreRelease`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Installs the latest version or a specific version of the Visual Studio Test Platform. If you use the test platform installer to run Coded UI tests, the chosen Visual Studio Test Platform must match the major version of the Visual Studio installation that built the test binaries. For example, if the Coded UI test project was built using Visual Studio 2017 (version 15.x), you must use Test Platform version 15.x.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testPlatformVersion"::: -->
:::moniker range="<=azure-pipelines"

**`testPlatformVersion`** - **Test Platform Version**<br>
`string`. Required when `versionSelector = specificVersion`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the version of Visual Studio Test Platform to install on the agent. Available versions can be viewed on [NuGet](https://www.nuget.org/packages/Microsoft.TestPlatform/).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customFeed"::: -->
:::moniker range=">=azure-pipelines-2019"

**`customFeed`** - **Package Source**<br>
`string`. Required when `packageFeedSelector = customFeed`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the URL of a custom feed or a package management feed in Azure DevOps or TFS that contains the test platform package. Public and private feeds can be specified.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="username"::: -->
:::moniker range=">=azure-pipelines-2019"

**`username`** - **User Name**<br>
`string`. Optional. Use when `packageFeedSelector = customFeed`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the user name to authenticate the feed specified in the **Package Source** argument. This input is not required if the `password` input uses a personal access token (PAT).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="password"::: -->
:::moniker range=">=azure-pipelines-2019"

**`password`** - **Password**<br>
`string`. Optional. Use when `packageFeedSelector = customFeed`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the password or personal access token (PAT) for authenticating the feed specified in the `customFeed` input.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="netShare"::: -->
:::moniker range=">=azure-pipelines-2019"

**`netShare`** - **UNC Path**<br>
`string`. Required when `packageFeedSelector = netShare`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the full UNC path to the `Microsoft.TestPlatform.nupkg` file. The specified `Microsoft.TestPlatform.nupkg` version must be downloaded from [NuGet](https://www.nuget.org/packages/Microsoft.TestPlatform/) and placed on a network share that the build/release agent can access.
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
> If you are using a hosted agent, check the [software table](/azure/devops/pipelines/agents/hosted#software) for the agent you are using to see if Visual Studio is installed. If Visual Studio is installed, you don't need to run the Visual Studio test platform installer task.

Use this task to acquire the [Microsoft test platform](https://www.nuget.org/packages/Microsoft.TestPlatform/) from nuget.org or a specified feed, and add it to the tools cache. The installer task satisfies the `vstest` demand, and a subsequent [Visual Studio Test task](vstest-v2.md) in a build or release pipeline can run without needing a full Visual Studio install on the agent machine.

> [!NOTE]
>
> * The **Visual Studio Test Platform Installer** task must appear before the **Visual Studio Test** task in the build or release pipeline.
> * The **Test platform version** option in the **Visual Studio Test** task must be set to **Installed by Tools Installer**.

See [Run automated tests from test plans](/azure/devops/test/run-automated-tests-from-test-hub).
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range=">=azure-pipelines-2022.1"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | Running this task satisfies the following [demands](/azure/devops/pipelines/process/demands) for any subsequent tasks in the same job: VsTest |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.144.0 or greater |
| Task category | Tool |

:::moniker-end

:::moniker range="<=azure-pipelines-2022"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | Running this task satisfies the following [demands](/azure/devops/pipelines/process/demands) for any subsequent tasks in the same job: VsTest |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.103.0 or greater |
| Task category | Tool |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
