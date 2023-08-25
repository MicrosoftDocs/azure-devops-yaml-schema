---
title: cURLUploader@2 - cURL Upload Files v2 task
description: Use cURL's supported protocols to upload files.
ms.date: 08/25/2023
monikerRange: "<=azure-pipelines"
---

# cURLUploader@2 - cURL Upload Files v2 task

<!-- :::description::: -->
:::moniker range="=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Use cURL to upload files.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2018 || >=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Use this task with [cURL](https://curl.haxx.se/) to upload files. Supported data transfer protocols include FTP, FTPS, SFTP, HTTP, and others.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# cURL Upload Files v2
# Use cURL's supported protocols to upload files.
- task: cURLUploader@2
  inputs:
    files: # string. Required. Files. 
    #authType: 'ServiceEndpoint' # 'ServiceEndpoint' | 'UserAndPass'. Authentication Method. Default: ServiceEndpoint.
    serviceEndpoint: # string. Required when authType = ServiceEndpoint. Service Connection. 
    #username: # string. Optional. Use when authType = UserAndPass. Username. 
    #password: # string. Optional. Use when authType = UserAndPass. Password. 
    #url: # string. Required when authType = UserAndPass. URL. 
    #remotePath: 'upload/$(Build.BuildId)/' # string. Remote Directory. Default: upload/$(Build.BuildId)/.
    #options: # string. Optional Arguments. 
  # Advanced
    #redirectStderr: true # boolean. Redirect Standard Error to Standard Out. Default: true.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# cURL Upload Files v2
# Use cURL to upload files.
- task: cURLUploader@2
  inputs:
    files: # string. Required. Files. 
    #authType: 'ServiceEndpoint' # 'ServiceEndpoint' | 'UserAndPass'. Authentication Method. Default: ServiceEndpoint.
    serviceEndpoint: # string. Required when authType = ServiceEndpoint. Service Connection. 
    #username: # string. Optional. Use when authType = UserAndPass. Username. 
    #password: # string. Optional. Use when authType = UserAndPass. Password. 
    #url: # string. Required when authType = UserAndPass. URL. 
    #remotePath: 'upload/$(Build.BuildId)/' # string. Remote Directory. Default: upload/$(Build.BuildId)/.
    #options: # string. Optional Arguments. 
  # Advanced
    #redirectStderr: true # boolean. Redirect Standard Error to Standard Out. Default: true.
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

<!-- :::item name="files"::: -->
:::moniker range="<=azure-pipelines"

**`files`** - **Files**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
File(s) to be uploaded. Wildcards can be used. For example, `**/*.zip` for all ZIP files in all subfolders.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="authType"::: -->
:::moniker range=">=azure-pipelines-2019"

**`authType`** - **Authentication Method**<br>
`string`. Allowed values: `ServiceEndpoint` (Service connection), `UserAndPass` (Username and password). Default value: `ServiceEndpoint`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the authentication method for server authentication.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`authType`** - **Authentication Method**<br>
`string`. Allowed values: `ServiceEndpoint` (Service Endpoint), `UserAndPass` (Username and Password). Default value: `ServiceEndpoint`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the authentication method for the server authentication.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="serviceEndpoint"::: -->
:::moniker range=">=azure-pipelines-2019"

**`serviceEndpoint`** - **Service Connection**<br>
`string`. Required when `authType = ServiceEndpoint`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the service connection with the credentials for the server authentication. Use the Generic service connection type for the service connection.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`serviceEndpoint`** - **Service Endpoint**<br>
`string`. Required when `authType = ServiceEndpoint`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the service connection with the credentials for the server authentication. Use the Generic service connection type for the service connection.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="username"::: -->
:::moniker range="<=azure-pipelines"

**`username`** - **Username**<br>
`string`. Optional. Use when `authType = UserAndPass`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the username for server authentication.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="password"::: -->
:::moniker range="<=azure-pipelines"

**`password`** - **Password**<br>
`string`. Optional. Use when `authType = UserAndPass`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the password for server authentication. Use a new build variable with its lock enabled on the Variables tab to encrypt this value. Use a [secret variable](/azure/devops/pipelines/build/variables) to avoid exposing ths value.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="url"::: -->
:::moniker range="<=azure-pipelines"

**`url`** - **URL**<br>
`string`. Required when `authType = UserAndPass`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the URL to where the file(s) will be uploaded. The directory should end with a trailing slash. Possible URL protocols include `DICT://`, `FILE://`, `FTP://`, `FTPS://`, `GOPHER://`, `HTTP://`, `HTTPS://`, `IMAP://`, `IMAPS://`, `LDAP://`, `LDAPS://`, `POP3://`, `POP3S://`, `RTMP://`, `RTSP://`, `SCP://`, `SFTP://`, `SMTP://`, `SMTPS://`, `TELNET://` and `TFTP://`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="remotePath"::: -->
:::moniker range=">=azure-pipelines-2019"

**`remotePath`** - **Remote Directory**<br>
`string`. Default value: `upload/$(Build.BuildId)/`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Specifies the sub-folder on the remote server for the URL supplied in the credentials.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`remotePath`** - **Remote Directory**<br>
`string`. Default value: `/upload/$(Build.BuildId)/`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Specifies the sub-folder on the remote server for the URL supplied in the credentials.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="options"::: -->
:::moniker range="<=azure-pipelines"

**`options`** - **Optional Arguments**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. The additional arguments that will be passed to cURL.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="redirectStderr"::: -->
:::moniker range="<=azure-pipelines"

**`redirectStderr`** - **Redirect Standard Error to Standard Out**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Adds `--stderr -` as an argument to cURL. By default, cURL writes its progress bar to `stderr`, which is interpreted by the build as error output. Enabling this checkbox suppresses that behavior.
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

Use this task to use [cURL](https://curl.haxx.se/) to upload files with supported protocols
such as FTP, FTPS, SFTP, HTTP, and more.

[!INCLUDE [include](includes/qa-minimatch.md)]

### Where can I learn FTP commands?

* [List of raw FTP commands](https://www.nsftools.com/tips/RawFTP.htm)
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
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
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | This task has permission to [set the following variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions): Setting variables is disabled |
| Agent version |  2.182.1 or greater |
| Task category | Utility |

:::moniker-end

:::moniker range=">=azure-pipelines-2019.1 <=azure-pipelines-2020.1"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version | All supported agent versions. |
| Task category | Utility |

:::moniker-end

:::moniker range="<=azure-pipelines-2019"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | Self-hosted agents must have [capabilities](/azure/devops/pipelines/agents/agents#capabilities) that match the following [demands](/azure/devops/pipelines/process/demands) to run jobs that use this task: curl |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version | All supported agent versions. |
| Task category | Utility |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
