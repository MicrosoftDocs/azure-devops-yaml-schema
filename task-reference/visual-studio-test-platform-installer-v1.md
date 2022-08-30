---
title: VisualStudioTestPlatformInstaller@1 - Visual Studio test platform installer v1 task
description: Acquire the test platform from nuget.org or the tool cache. Satisfies the ‘vstest’ demand and can be used for running tests and collecting diagnostic data using the Visual Studio Test task.
ms.date: 08/18/2022
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
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="versionSelector"::: -->
:::moniker range=">=azure-pipelines-2019"

**`versionSelector`** - **Version**<br>
Type: string. Required when packageFeedSelector = nugetOrg || packageFeedSelector = customFeed. Allowed values: 'latestPreRelease', 'latestStable', 'specificVersion'. Default value: 'latestPreRelease'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Pick whether to install the latest version or a specific version of the Visual Studio Test Platform.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`versionSelector`** - **Version**<br>
Type: string. Required. Allowed values: 'latestPreRelease', 'specificVersion'. Default value: 'latestPreRelease'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Pick whether to install the latest version or a specific version of the Visual Studio Test Platform.
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
Fetch the testplatform package from the specified package feed. Can be a public or a private feed.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="username"::: -->
:::moniker range=">=azure-pipelines-2019"

**`username`** - **User Name**<br>
Type: string. Optional. Use when packageFeedSelector = customFeed.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
User name for authenticating against the specified feed. If providing a PAT token as password, username is optional.
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
Specify the full UNC path to the microsoft.testplatform nupkg file.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
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