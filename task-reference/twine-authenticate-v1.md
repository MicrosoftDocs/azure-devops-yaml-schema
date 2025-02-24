---
title: TwineAuthenticate@1 - Python twine upload authenticate v1 task
description: Authenticate for uploading Python distributions using twine. Add '-r FeedName/EndpointName --config-file $(PYPIRC_PATH)' to your twine upload command. For feeds present in this organization, use the feed name as the repository (-r). Otherwise, use the endpoint name defined in the service connection.
ms.date: 02/24/2025
monikerRange: ">=azure-pipelines-2020"
---

# TwineAuthenticate@1 - Python twine upload authenticate v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
Use this task to authenticate uploads of Python distributions using twine. Add `-r FeedName/EndpointName --config-file $(PYPIRC_PATH)` to your twine upload command. For feeds present in this organization, use the feed name as the repository (`-r`). Otherwise, use the endpoint name defined in the service connection.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2022.1"

```yaml
# Python twine upload authenticate v1
# Authenticate for uploading Python distributions using twine. Add '-r FeedName/EndpointName --config-file $(PYPIRC_PATH)' to your twine upload command. For feeds present in this organization, use the feed name as the repository (-r). Otherwise, use the endpoint name defined in the service connection.
- task: TwineAuthenticate@1
  inputs:
  # Feeds and Authentication
    #artifactFeed: # string. My feed name (select below). 
    #pythonUploadServiceConnection: # string. Feed from external organizations.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2020 <=azure-pipelines-2022"

```yaml
# Python twine upload authenticate v1
# Authenticate for uploading Python distributions using twine. Add '-r FeedName/EndpointName --config-file $(PYPIRC_PATH)' to your twine upload command. For feeds present in this organization, use the feed name as the repository (-r). Otherwise, use the endpoint name defined in the service connection.
- task: TwineAuthenticate@1
  inputs:
  # Feeds and Authentication
    #artifactFeed: # string. My feed (select below). 
    #pythonUploadServiceConnection: # string. Feed from external organizations.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="artifactFeed"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`artifactFeed`** - **My feed name (select below)**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the Azure artifact's feed name to authenticate with twine. The authenticating feed must be present within the organization. For project-scoped feeds, use the syntax `projectName/feedNameSelect`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range=">=azure-pipelines-2020 <=azure-pipelines-2022"

**`artifactFeed`** - **My feed (select below)**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the Azure artifact's feed name to authenticate with twine. The authenticating feed must be present within the organization. For project-scoped feeds, use the syntax `projectName/feedNameSelect`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="pythonUploadServiceConnection"::: -->
:::moniker range=">=azure-pipelines-2020"

**`pythonUploadServiceConnection`** - **Feed from external organizations**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
A [twine service connection](/azure/devops/pipelines/library/service-endpoints#python-package-upload-service-connection) name from an external organization to authenticate with twine. The credentials stored in the endpoint must have package upload permissions.
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

Provides `twine` credentials to a `PYPIRC_PATH` environment variable for the scope of the build. This enables you to publish Python packages to feeds with `twine` from your build.

* [When in my pipeline should I run this task?](#when-in-my-pipeline-should-i-run-this-task)
* [My agent is behind a web proxy. Will TwineAuthenticate set up twine to use my proxy?](#my-agent-is-behind-a-web-proxy-will-twineauthenticate-set-up-twine-to-use-my-proxy)
* [My Pipeline needs to access a feed in a different project](#my-pipeline-needs-to-access-a-feed-in-a-different-project)

### When in my pipeline should I run this task?

This task must run before you use twine to upload Python distributions to an authenticated package source, such as Azure Artifacts. There are no other ordering requirements. Multiple invocations of this task will not stack credentials. Every task run will erase any previously stored credentials.

### My agent is behind a web proxy. Will TwineAuthenticate set up twine to use my proxy?

No. While this task itself will work behind a [web proxy your agent has been configured to use](/azure/devops/pipelines/agents/proxy), it does not configure twine to use the proxy.

### My Pipeline needs to access a feed in a different project

If the pipeline is running in a different project than the project hosting the feed, you must set up the other project to grant read/write access to the build service. See [Package permissions in Azure Pipelines](/azure/devops/artifacts/feeds/feed-permissions#pipelines-permissions) for more details.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

The following examples demonstrate how to publish python distribution to Azure Artifacts feed and the official python registry.

* [Publish Python distribution to Azure Artifacts feed](#publish-python-distribution-to-azure-artifacts-feed)
* [Publish Python distribution to the official Python registry](#publish-python-distribution-to-the-official-python-registry)

### Publish Python distribution to Azure Artifacts feed

In this example, we are setting authentication for publishing to a private Azure Artifacts Feed. The authenticate task creates a `.pypirc` file that contains the auth credentials required to publish a distribution to the feed.

```YAML 
# Install python distributions like wheel, twine etc
- script: |
     pip install wheel
     pip install twine
  
# Build the python distribution from source
- script: |
     python setup.py bdist_wheel
   
- task: TwineAuthenticate@1
  displayName: Twine Authenticate
  inputs:
    # In this case, name of the feed is 'myTestFeed' in the project 'myTestProject'. Project is needed because the feed is project scoped.
    artifactFeed: myTestProject/myTestFeed
  
# Use command line script to 'twine upload', use -r to pass the repository name and --config-file to pass the environment variable set by the authenticate task.
- script: |
     python -m twine upload -r myTestFeed --config-file $(PYPIRC_PATH) dist/*.whl
```

The `artifactFeed` input will contain the project and the feed name if the feed is project scoped. If the feed is organization scoped, only the feed name must be provided. [Learn more](/azure/devops/artifacts/feeds/project-scoped-feeds).

### Publish Python distribution to the official Python registry

In this example, we are setting up authentication for publishing to the official Python registry. Create a [twine service connection](/azure/devops/pipelines/library/service-endpoints#python-package-upload-service-connection) entry for [pypi](https://pypi.org). The authenticate task uses that service connection to create a `.pypirc` file that contains the auth credentials required to publish the distribution.

```YAML 
# Install python distributions like wheel, twine etc
- script: |
     pip install wheel
     pip install twine
  
# Build the python distribution from source
- script: |
     python setup.py bdist_wheel
   
- task: TwineAuthenticate@1
  displayName: Twine Authenticate
  inputs:
    # In this case, name of the service connection is "pypitest".
    pythonUploadServiceConnection: pypitest
  
# Use command line script to 'twine upload', use -r to pass the repository name and --config-file to pass the environment variable set by the authenticate task.
- script: |
     python -m twine upload -r "pypitest" --config-file $(PYPIRC_PATH) dist/*.whl
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

:::moniker range=">=azure-pipelines-2020 <=azure-pipelines-2022"

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