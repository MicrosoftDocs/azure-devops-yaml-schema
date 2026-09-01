---
title: GradleAuthenticate@0 - Gradle Authenticate v0 task
description: Authenticate Gradle builds with Azure Artifacts feeds using Workload Identity Federation or an access token. (task version 0)
ms.date: 09/01/2026
monikerRange: "=azure-pipelines"
---

# GradleAuthenticate@0 - Gradle Authenticate v0 task

<!-- :::description::: -->
:::moniker range=">azure-pipelines-server"

<!-- :::editable-content name="description"::: -->
Use this task before your Gradle build to authenticate with Azure Artifacts feeds for dependency restore and plugin resolution. The task installs and configures a CI version of the Gradle credential provider for the job, then authenticates by using either a Workload Identity Federation (WIF) service connection or the build access token that is already available to the job.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="=azure-pipelines"

```yaml
# Gradle Authenticate v0
# Authenticate Gradle builds with Azure Artifacts feeds using Workload Identity Federation or an access token.
- task: GradleAuthenticate@0
  inputs:
    #buildFiles: # string. Build files. 
    #repositoryUrl: # string. Repository URL(s). 
    #adoServiceConnection: # string. Service connection. 
    #pluginToolVersion: # string. Plugin tool version. 
    #gradleUserHome: # string. Gradle user home.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<a name="buildfiles-property"></a>
<!-- :::item name="buildFiles"::: -->
:::moniker range=">azure-pipelines-server"

**`buildFiles`** - **Build files**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide a newline-separated list of Gradle files for the task to scan for Azure Artifacts feed URLs. Include each Gradle file that defines repositories for the build, such as `settings.gradle`, `settings.gradle.kts`, `build.gradle`, or `build.gradle.kts`. If your build uses the Gradle `plugins {}` block in `settings.gradle`, include that file so the task can detect the plugin version automatically.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="repositoryurl-property"></a>
<!-- :::item name="repositoryUrl"::: -->
:::moniker range=">azure-pipelines-server"

**`repositoryUrl`** - **Repository URL(s)**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide a newline-separated list of Azure Artifacts repository URLs to authenticate. When you specify this input, the task uses the provided URLs instead of scanning build files to discover repository URLs. If you also provide **Build files**, the task can still use them for plugin version detection.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="adoserviceconnection-property"></a>
<!-- :::item name="adoServiceConnection"::: -->
:::moniker range=">azure-pipelines-server"

**`adoServiceConnection`** - **Service connection**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of an Azure DevOps Service Connection that uses Workload Identity Federation (WIF) for authentication. If you leave this input empty, the task falls back to token-based authentication by using `ARTIFACTS_GRADLE_AUTH_ACCESS_TOKEN` when it is set, or `SYSTEM_ACCESSTOKEN` otherwise.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="plugintoolversion-property"></a>
<!-- :::item name="pluginToolVersion"::: -->
:::moniker range=">azure-pipelines-server"

**`pluginToolVersion`** - **Plugin tool version**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Override the version of the Gradle authentication plugin installed by the task. By default, the task uses the latest compatible version. Use this input only when you need a specific plugin version.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="gradleuserhome-property"></a>
<!-- :::item name="gradleUserHome"::: -->
:::moniker range=">azure-pipelines-server"

**`gradleUserHome`** - **Gradle user home**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Override the Gradle user home directory. By default, the task uses `GRADLE_USER_HOME` when it is set, or `~/.gradle` otherwise. Set this input when your build uses a custom Gradle user home location.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">azure-pipelines-server"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

Run this task in the same job and before the Gradle command that needs access to Azure Artifacts. The task prepares the authentication configuration required for subsequent Gradle steps in the job.

The task supports two authentication modes:

- If you provide **Service connection**, the task configures [Workload Identity Federation](/azure/devops/pipelines/release/configure-workload-identity) for each discovered Azure Artifacts feed.
- If you don't provide **Service connection**, the task uses the build access token from the environment. It first checks for `ARTIFACTS_GRADLE_AUTH_ACCESS_TOKEN`; if that variable isn't set, it uses `SYSTEM_ACCESSTOKEN`.

Use **Build files** or **Repository URL(s)** to tell the task where to look for Azure Artifacts feeds. If scanning finds no Azure Artifacts URLs, the task completes successfully but doesn't configure authentication for any feeds.

### How feed discovery works

- If you provide **Repository URL(s)**, the task uses those URLs for authentication and doesn't scan build files to discover other repository URLs.

- If you provide both **Repository URL(s)** and **Build files**, only the specified repository URLs will be configured during that run, even if the build files contain additional Azure Artifacts repositories.

- If you also provide **Build files**, the task still uses them to determine the credential provider plugin version.

- If you don't provide **Repository URL(s)**, the task scans the files listed in **Build files** for Azure Artifacts feed URLs, such as `https://pkgs.dev.azure.com/...`.

- If you leave Build files empty and don't provide Repository URL(s), the task automatically searches for common Gradle files in the working directory:
    - `settings.gradle`
    - `settings.gradle.kts`
    - `build.gradle`
    - `build.gradle.kts`

### How plugin version resolution works

The task determines which version of the CI Gradle credential provider to use for the build. By default, the task uses the latest compatible version. The task determines the version in the following order:

1. A plugin version declared in the Gradle files.
2. The value specified in **Plugin tool version**.
3. A version detected from the resolved credential provider package.
4. A fallback version.

If your repository uses `settings.gradle` with the Gradle `plugins {}` block, include that file in **Build files** so the task can discover the plugin version correctly.

### What the task changes

For the current job, the task:

- stages a temporary local Maven-style layout for the CI Gradle credential provider
- writes an authentication configuration file for the discovered feeds
- writes a temporary Gradle init script in the Gradle user home directory
- sets environment variables that the init script and credential provider use during the Gradle build

The task also registers post-job cleanup so that these temporary files are removed after the job finishes.

### Multiple invocations in one job

You can run `GradleAuthenticate@0` more than once in the same job. This is useful when different Gradle builds in the job need different feed sets or different service connections. Later invocations add to the existing temporary configuration and replace entries for the same feed URL when needed.

### Permissions

This task configures authentication, but it doesn't grant feed permissions. If the pipeline accesses a feed in another project or organization, make sure the pipeline identity or service connection has the required access. For more information, see [Package permissions in Azure Pipelines](/azure/devops/artifacts/feeds/feed-permissions#pipelines-permissions).
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

- [Authenticate feeds discovered from Gradle files by using Workload Identity Federation](#authenticate-feeds-discovered-from-gradle-files-by-using-workload-identity-federation)
- [Authenticate explicit feed URLs by using a job access token](#authenticate-explicit-feed-urls-by-using-a-job-access-token)

### Authenticate feeds discovered from Gradle files by using Workload Identity Federation

In this example, the task scans the listed Gradle files for Azure Artifacts feed URLs, detects the credential provider plugin version from `settings.gradle`, and configures WIF authentication by using an Azure DevOps service connection.

```yaml
steps:
- task: GradleAuthenticate@0
  displayName: 'Authenticate Azure Artifacts for Gradle'
  inputs:
    buildFiles: |
      settings.gradle
      build.gradle
    adoServiceConnection: 'Gradle-WIF-Connection'

- task: Gradle@4
  displayName: 'Run Gradle build'
  inputs:
    gradleWrapperFile: 'gradlew'
    tasks: 'build'
```

Use this pattern when your repository already contains the Azure Artifacts feed URLs in Gradle configuration and you want the task to infer as much as possible.

### Authenticate explicit feed URLs by using a job access token

In this example, the task authenticates a specific Azure Artifacts feed without scanning any Gradle files. This is useful when the repository URL is known up front or when the relevant feed isn't declared in a file that the task can inspect.

```yaml
steps:
- task: GradleAuthenticate@0
  displayName: 'Authenticate explicit Azure Artifacts feed'
  inputs:
    repositoryUrl: |
      'https://pkgs.dev.azure.com/contoso/Fabrikam/_packaging/SharedFeed/maven/v1'
    pluginToolVersion: '1.0.0'

- task: Gradle@4
  displayName: 'Publish package'
  inputs:
    gradleWrapperFile: 'gradlew'
    tasks: 'publish'
  env:
    SYSTEM_ACCESSTOKEN: $(System.AccessToken)
```

Use this pattern when token-based authentication is sufficient and you want to target one or more known Azure Artifacts feed URLs directly.
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
| Agent version |  2.144.0 or greater |
| Task category | Package |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->