---
title: DownloadSecureFile@1 - Download secure file v1 task
description: Download a secure file to the agent machine.
ms.date: 07/10/2023
monikerRange: "<=azure-pipelines"
---

# DownloadSecureFile@1 - Download secure file v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
Use this task to download a secure file to the agent machine.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Use this task to download a secure file to a temporary location on the agent machine.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Use this task to download a secure file to a temporary location on the build or release agent.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020.1"

```yaml
# Download secure file v1
# Download a secure file to the agent machine.
- task: DownloadSecureFile@1
  inputs:
    secureFile: # string. Required. Secure File. 
    #retryCount: '8' # string. Retry Count. Default: 8.
    #socketTimeout: # string. Socket Timeout.
```

:::moniker-end

:::moniker range="=azure-pipelines-2020"

```yaml
# Download secure file v1
# Download a secure file to the agent machine.
- task: DownloadSecureFile@1
  inputs:
    secureFile: # string. Required. Secure File. 
    #retryCount: '5' # string. Retry Count. Default: 5.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

```yaml
# Download secure file v1
# Download a secure file to a temporary location on the agent machine.
- task: DownloadSecureFile@1
  inputs:
    secureFile: # string. Required. Secure File.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Download Secure File v1
# Download a secure file to a temporary location on the build or release agent.
- task: DownloadSecureFile@1
  inputs:
    secureFile: # string. Required. Secure File.
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

<!-- :::item name="secureFile"::: -->
:::moniker range="<=azure-pipelines"

**`secureFile`** - **Secure File**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name or unique identifier (GUID) of the secure file that is downloaded to the agent machine. The file is deleted when the pipeline job completes.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="retryCount"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`retryCount`** - **Retry Count**<br>
`string`. Default value: `8`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Specifies the number of times to retry downloading a secure file if the download fails.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2020"

**`retryCount`** - **Retry Count**<br>
`string`. Default value: `5`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Specifies the number of times to retry downloading a secure file if the download fails.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="socketTimeout"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`socketTimeout`** - **Socket Timeout**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. When downloading a secure file request in Microsoft, this input specifies the timeout for a socket.
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

This task defines the following [output variables](/azure/devops/pipelines/process/variables#use-output-variables-from-tasks), which you can consume in downstream steps, jobs, and stages.

<!-- :::item name="secureFilePath"::: -->
**`secureFilePath`**<br><!-- :::editable-content name="Value"::: -->
Specifies the location of the secure file that was downloaded.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

Use this task in a pipeline to download a [secure file](/azure/devops/pipelines/library/secure-files) to the agent machine. When specifying the name of the file (using the `secureFile` input), use the name you specified when uploading it, rather than the actual file name.

Once downloaded, use the `name` value that is set on the task (or "Reference name" in the classic editor) to reference the path to the secure file on the agent machine. For example, if the task is given the name `mySecureFile`, its path can be referenced in the pipeline as `$(mySecureFile.secureFilePath)`. Alternatively, downloaded secure files can be found in the directory given by `$(Agent.TempDirectory)`. See a full example [below](#examples).

When the pipeline job completes, whether it succeeds, fails, or is canceled, the secure file is deleted from its download location.

It is unnecessary to use this task with the [Install Apple Certificate](install-apple-certificate-v2.md) or [Install Apple Provisioning Profile](install-apple-provisioning-profile-v1.md) tasks because they automatically download, install, and delete (at the end of the pipeline job) the secure file.

This task currently supports only one file task per instance.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

This example downloads a secure certificate file and installs it to a trusted certificate authority (CA) directory on Linux:

```yaml
- task: DownloadSecureFile@1
  name: caCertificate
  displayName: 'Download CA certificate'
  inputs:
    secureFile: 'myCACertificate.pem'

- script: |
    echo Installing $(caCertificate.secureFilePath) to the trusted CA directory...
    sudo chown root:root $(caCertificate.secureFilePath)
    sudo chmod a+r $(caCertificate.secureFilePath)
    sudo ln -s $(caCertificate.secureFilePath) /etc/ssl/certs/ 
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range=">=azure-pipelines-2022"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | This task runs using the following [command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions): restricted |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | This task has permission to [set the following variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions): secureFilePath |
| Agent version |  2.182.1 or greater |
| Task category | Utility |

:::moniker-end

:::moniker range="<=azure-pipelines-2020.1"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.116.0 or greater |
| Task category | Utility |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
