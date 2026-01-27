---
title: cURLUploader@1 - cURL Upload Files v1 task
description: Use cURL to upload files with FTP, FTPS, SFTP, HTTP, and more.
ms.date: 01/27/2026
monikerRange: "=azure-pipelines || =azure-pipelines-server || =azure-pipelines-2022.2 || =azure-pipelines-2022.1 || =azure-pipelines-2022"
---

# cURLUploader@1 - cURL Upload Files v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task with [cURL](https://curl.haxx.se/) to upload files. Supported data transfer protocols include FTP, FTPS, SFTP, HTTP, and others.

> [!NOTE]
> There is a newer version of this task available at [cURLUploader@2](./curl-uploader-v2.md).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="<=azure-pipelines"

```yaml
# cURL Upload Files v1
# Use cURL to upload files with FTP, FTPS, SFTP, HTTP, and more.
- task: cURLUploader@1
  inputs:
    files: # string. Required. Files. 
    #username: # string. Username. 
    #password: # string. Password. 
    url: # string. Required. URL. 
    #options: # string. Optional Arguments. 
  # Advanced
    #redirectStderr: true # boolean. Redirect Standard Error to Standard Out. Default: true.
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
The file(s) to be uploaded. Wildcards can be used. For example, `**\*.zip` for all ZIP files in all subfolders.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="username"::: -->
:::moniker range="<=azure-pipelines"

**`username`** - **Username**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Specifies the username for server authentication.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="password"::: -->
:::moniker range="<=azure-pipelines"

**`password`** - **Password**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Specifies the password for server authentication. Use a new build variable with its lock enabled on the Variables tab to encrypt this value. Use a [secret variable](/azure/devops/pipelines/build/variables) to avoid exposing ths value.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="url"::: -->
:::moniker range="<=azure-pipelines"

**`url`** - **URL**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the URL to where the file(s) will be uploaded. The directory should end with a trailing slash. Possible URL protocols include `DICT://`, `FILE://`, `FTP://`, `FTPS://`, `GOPHER://`, `HTTP://`, `HTTPS://`, `IMAP://`, `IMAPS://`, `LDAP://`, `LDAPS://`, `POP3://`, `POP3S://`, `RTMP://`, `RTSP://`, `SCP://`, `SFTP://`, `SMTP://`, `SMTPS://`, `TELNET://` and `TFTP://`.
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

### Where can I learn FTP commands?

See the [list of raw FTP commands](https://www.nsftools.com/tips/RawFTP.htm).
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