---
title: PipAuthenticate@1 - Python pip authenticate v1 task
description: Authentication task for the pip client used for installing Python distributions.
ms.date: 08/29/2025
monikerRange: "<=azure-pipelines"
author: ramiMSFT
ms.author: rabououn
---

# PipAuthenticate@1 - Python pip authenticate v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to provide authentication for the `pip` client that installs Python distributions.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="<=azure-pipelines"

```yaml
# Python pip authenticate v1
# Authentication task for the pip client used for installing Python distributions.
- task: PipAuthenticate@1
  inputs:
  # Feeds and Authentication
    #artifactFeeds: # string. My feeds (select below). 
    #pythonDownloadServiceConnections: # string. Feeds from external organizations. 
    #onlyAddExtraIndex: false # boolean. Don't set primary index URL. Default: false.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="artifactFeeds"::: -->
:::moniker range="<=azure-pipelines"

**`artifactFeeds`** - **My feeds (select below)**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a comma-separated list of Azure Artifacts feeds to authenticate with pip.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="pythonDownloadServiceConnections"::: -->
:::moniker range="<=azure-pipelines"

**`pythonDownloadServiceConnections`** - **Feeds from external organizations**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a comma-separated list of [pip service connection](/azure/devops/pipelines/library/service-endpoints) names from external organizations to authenticate with pip.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="onlyAddExtraIndex"::: -->
:::moniker range="<=azure-pipelines"

**`onlyAddExtraIndex`** - **Don't set primary index URL**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If this task is set to `true`, no feed will be set as the primary index URL. All of the configured feeds/endpoints will be set as extra index URLs.
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

Provides authentication for the `pip` client that is used to install Python distributions.

* [When in my pipeline should I run this task?](#when-in-my-pipeline-should-i-run-this-task)
* [What if I want my pipelines to be able to save from upstream sources?](#what-if-i-want-my-pipelines-to-be-able-to-save-from-upstream-sources)
* [My agent is behind a web proxy. Will PipAuthenticate set up pip to use my proxy?](#my-agent-is-behind-a-web-proxy-will-pipauthenticate-set-up-pip-to-use-my-proxy)
* [My Pipeline needs to access a feed in a different project](#my-pipeline-needs-to-access-a-feed-in-a-different-project)

### When in my pipeline should I run this task?

This task must run before you use pip to download Python distributions to an authenticated package source such as Azure Artifacts. There are no other ordering requirements. Multiple invocations of this task will not stack credentials. Every run of the task will erase any previously stored credentials.

### What if I want my pipelines to be able to save from upstream sources?

Check the [permissions table](/azure/devops/artifacts/feeds/feed-permissions#pipelines-permissions) to determine what permissions you want your pipeline to have. Then, determine which [identity](/azure/devops/pipelines/process/access-tokens#scoped-build-identities) you want to give those permissions to. To save packages from upstream sources, your identity needs `Feed and Upstream Reader (Collaborator)` permissions.

### My agent is behind a web proxy. Will PipAuthenticate set up pip to use my proxy?

No. While this task itself will work behind a [web proxy your agent has been configured to use](/azure/devops/pipelines/agents/proxy), it does not configure pip to use the proxy.

To do so, you can:
* Set the environment variables `http_proxy`, `https_proxy` and optionally `no_proxy` to your proxy settings. See [Pip official guidelines](https://pip.pypa.io/en/stable/user_guide/#using-a-proxy-server) for details. These are commonly used variables, which other non-Python tools (e.g. curl) may also use.
    > [!CAUTION]
    >The `http_proxy` and `no_proxy` variables are case-sensitive on Linux and Mac operating systems and must be lowercase. Attempting to use an Azure Pipelines variable to set the environment variable will not work, as it will be converted to uppercase. Instead, set the environment variables on the self-hosted agent's machine and restart the agent.
* Add the proxy settings to the [pip config file](https://pip.pypa.io/en/stable/user_guide/#config-file) file using `proxy` key.
* Use the `--proxy` command-line option to specify proxy in the form `[user:passwd@]proxy.server:port`.

### My Pipeline needs to access a feed in a different project

If the pipeline is running in a different project than the project hosting the feed, you must set up the other project to grant read/write access to the build service. See [Package permissions in Azure Pipelines](/azure/devops/artifacts/feeds/feed-permissions#pipelines-permissions) for more details.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

### Download Python distributions from Azure Artifacts feeds without consulting official Python registry

In this example, we are setting authentication for downloading from private Azure Artifacts feeds. The authenticate task creates environment variables `PIP_INDEX_URL` and `PIP_EXTRA_INDEX_URL` that are required to download the distributions. The task sets the variables with authentication credentials the task generates for the provided Artifacts feeds. `HelloTestPackage` must be present in either `myTestFeed1` or `myTestFeed2`; otherwise, the install will fail.

For project-scoped feeds that are in a different project than where the pipeline is running, you must manually give the project and the feed access to the pipeline's project's build service.

```YAML
- task: PipAuthenticate@1
  displayName: 'Pip Authenticate'
  inputs:
    # Provide list of feed names which you want to authenticate.
    # Project scoped feeds must include the project name in addition to the feed name.
    artifactFeeds: 'project1/myTestFeed1, myTestFeed2'

# Use command line tool to 'pip install'.
- script: |
    pip install HelloTestPackage
```

### Consult official Python registry and then download Python distributions from Azure Artifacts feeds

In this example, we are setting authentication for downloading from a private Azure Artifacts feed, but [pypi](https://pypi.org) is consulted first. The authenticate task creates an environment variable `PIP_EXTRA_INDEX_URL`, which contains auth credentials required to download the distributions. `HelloTestPackage` will be downloaded from the authenticated feeds only if it's not present in [pypi](https://pypi.org).

For project-scoped feeds that are in a different project than where the pipeline is running, you must manually give the project and the feed access to the pipeline's project's build service.

```YAML
- task: PipAuthenticate@1
  displayName: 'Pip Authenticate'
  inputs:
    # Provide list of feed names which you want to authenticate.
    # Project scoped feeds must include the project name in addition to the feed name.
    artifactFeeds: 'project1/myTestFeed1, myTestFeed2'
    # Setting this variable to "true" will force pip to get distributions from official python registry first and fallback to feeds mentioned above if distributions are not found there.
    onlyAddExtraIndex: true

# Use command line tool to 'pip install'.
- script: |
    pip install HelloTestPackage
```

### Download Python distributions from other private Python servers

In this example, we are setting authentication for downloading from an external Python distribution server. Create a [pip service connection](/azure/devops/pipelines/library/service-endpoints#python-package-download-service-connection) entry for the external service. The authenticate task uses the service connection to create an environment variable `PIP_INDEX_URL`, which contains auth credentials required to download the distributions. `HelloTestPackage` has to be present in the `pypitest` service connection; otherwise, install will fail. If you want [pypi](https://pypi.org) to be consulted first, set `onlyAddExtraIndex` to `true`.

```YAML
- task: PipAuthenticate@1
  displayName: 'Pip Authenticate'
  inputs:
    # In this case, name of the service connection is "pypitest". 
    pythonDownloadServiceConnections: pypitest

# Use command line tool to 'pip install'.
- script: |
    pip install HelloTestPackage
```
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
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.144.0 or greater |
| Task category | Package |

:::moniker-end

:::moniker range="<=azure-pipelines-2022"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.120.0 or greater |
| Task category | Package |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
