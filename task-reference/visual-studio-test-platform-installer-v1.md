---
title: VisualStudioTestPlatformInstaller@1 - Visual Studio test platform installer v1 task
description: Acquire the test platform from nuget.org or the tool cache. Satisfies the ‘vstest’ demand and can be used for running tests and collecting diagnostic data using the Visual Studio Test task.
ms.date: 09/01/2022
monikerRange: "<=azure-pipelines"
---

# VisualStudioTestPlatformInstaller@1 - Visual Studio test platform installer v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Acquire the test platform from nuget.org or the tool cache. Satisfies the ‘vstest’ demand and can be used for running tests and collecting diagnostic data using the Visual Studio Test task.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Acquires the test platform from nuget.org or the tools cache. Satisfies the ‘vstest’ demand and can be used for running tests and collecting diagnostic data using the Visual Studio Test task.
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
    packageFeedSelector: 'nugetOrg' # 'nugetOrg' | 'customFeed' | 'netShare'. Required. Package Feed. Default: 'nugetOrg'.
    #versionSelector: 'latestPreRelease' # 'latestPreRelease' | 'latestStable' | 'specificVersion'. Required when packageFeedSelector = nugetOrg || packageFeedSelector = customFeed. Version. Default: 'latestPreRelease'.
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
    packageFeedSelector: 'nugetOrg' # 'nugetOrg' | 'customFeed' | 'netShare'. Required. Package Feed. Default: 'nugetOrg'.
    #versionSelector: 'latestPreRelease' # 'latestPreRelease' | 'latestStable' | 'specificVersion'. Required when packageFeedSelector = nugetOrg || packageFeedSelector = customFeed. Version. Default: 'latestPreRelease'.
    #testPlatformVersion: # string. Required when versionSelector = specificVersion. Test Platform Version. 
    #customFeed: # string. Required when packageFeedSelector = customFeed. Package Source. 
    #username: # string. Optional. Use when packageFeedSelector = customFeed. User Name. 
    #password: # string. Optional. Use when packageFeedSelector = customFeed. Password. 
    #netShare: # string. Required when packageFeedSelector = netShare. UNC Path.
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

<!-- :::item name="packageFeedSelector"::: -->
:::moniker range=">=azure-pipelines-2019"

**`packageFeedSelector`** - **Package Feed**<br>
Type: string. Required. Allowed values: 'nugetOrg', 'customFeed', 'netShare'. Default value: 'nugetOrg'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the feed from which the Visual Studio Test Platform nuget packge should be fetched.

**Official NuGet** - Use this option to acquire the [test platform package from NuGet](https://www.nuget.org/packages/Microsoft.TestPlatform/). This option requires internet connectivity on the agent machine.

**Custom feed** - Use this option to acquire the test platform package from a custom feed or a package management feed in Azure DevOps or TFS.

**Network path** - Use this option to install the test platform from a network share. The desired version of Microsoft.TestPlatform.nupkg file must be downloaded from NuGet and placed on a network share that the build/release agent can access.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="versionSelector"::: -->
:::moniker range=">=azure-pipelines-2019"

**`versionSelector`** - **Version**<br>
Type: string. Required when packageFeedSelector = nugetOrg || packageFeedSelector = customFeed. Allowed values: 'latestPreRelease', 'latestStable', 'specificVersion'. Default value: 'latestPreRelease'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Pick whether to install the latest version or a specific version of the Visual Studio Test Platform.
If you use the test platform installer to run Coded UI tests, ensure that the version you choose matches the major version of Visual Studio with which the test binaries were built.
For e.g., if the Coded UI test project was built using Visual Studio 2017 (version 15.x), you must use test platform version 15.x.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`versionSelector`** - **Version**<br>
Type: string. Required. Allowed values: 'latestPreRelease', 'specificVersion'. Default value: 'latestPreRelease'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Pick whether to install the latest version or a specific version of the Visual Studio Test Platform.
If you use the test platform installer to run Coded UI tests, ensure that the version you choose matches the major version of Visual Studio with which the test binaries were built.
For e.g., if the Coded UI test project was built using Visual Studio 2017 (version 15.x), you must use test platform version 15.x.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testPlatformVersion"::: -->
:::moniker range="<=azure-pipelines"

**`testPlatformVersion`** - **Test Platform Version**<br>
Type: string. Required when versionSelector = specificVersion.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the version of Visual Studio Test Platform to install on the agent. Available versions can be viewed on <a href="https://www.nuget.org/packages/Microsoft.TestPlatform/">nuget</a>.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customFeed"::: -->
:::moniker range=">=azure-pipelines-2019"

**`customFeed`** - **Package Source**<br>
Type: string. Required when packageFeedSelector = customFeed.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the URL of a custom feed or a package management feed in Azure DevOps or TFS that contains the test platform package. Public as well as private feeds can be specified.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="username"::: -->
:::moniker range=">=azure-pipelines-2019"

**`username`** - **User Name**<br>
Type: string. Optional. Use when packageFeedSelector = customFeed.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the user name to authenticate with the feed specified in the **Package Source** argument. If using a personal access token (PAT) in the password argument, this input is not required.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="password"::: -->
:::moniker range=">=azure-pipelines-2019"

**`password`** - **Password**<br>
Type: string. Optional. Use when packageFeedSelector = customFeed.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Password or personal access token for authenticating against the specified feed.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="netShare"::: -->
:::moniker range=">=azure-pipelines-2019"

**`netShare`** - **UNC Path**<br>
Type: string. Required when packageFeedSelector = netShare.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the full UNC path to the microsoft.testplatform nupkg file. The desired version of Microsoft.TestPlatform.nupkg must be downloaded from [NuGet](https://www.nuget.org/packages/Microsoft.TestPlatform/) and placed on a network share that the build/release agent can access.
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

:::moniker range="<=azure-pipelines"

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