---
title: cURLUploader@1 - cURL Upload Files v1 task
description: Use cURL to upload files with FTP, FTPS, SFTP, HTTP, and more.
ms.date: 08/18/2022
monikerRange: "<=azure-pipelines"
---

# cURLUploader@1 - cURL Upload Files v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use cURL to upload files with FTP, FTPS, SFTP, HTTP, and more.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019"

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
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
File(s) to be uploaded. Wildcards can be used. For example, `**\*.zip` for all ZIP files in all subfolders.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="username"::: -->
:::moniker range="<=azure-pipelines"

**`username`** - **Username**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the username for server authentication.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="password"::: -->
:::moniker range="<=azure-pipelines"

**`password`** - **Password**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the password for server authentication. Use a new build variable with its lock enabled on the Variables tab to encrypt this value.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="url"::: -->
:::moniker range="<=azure-pipelines"

**`url`** - **URL**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the URL to where the file(s) will be uploaded. The directory should end with a trailing slash. Possible URL protocols include `DICT://`, `FILE://`, `FTP://`, `FTPS://`, `GOPHER://`, `HTTP://`, `HTTPS://`, `IMAP://`, `IMAPS://`, `LDAP://`, `LDAPS://`, `POP3://`, `POP3S://`, `RTMP://`, `RTSP://`, `SCP://`, `SFTP://`, `SMTP://`, `SMTPS://`, `TELNET://` and `TFTP://`.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="options"::: -->
:::moniker range="<=azure-pipelines"

**`options`** - **Optional Arguments**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Additional arguments that will be passed to cURL.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="redirectStderr"::: -->
:::moniker range="<=azure-pipelines"

**`redirectStderr`** - **Redirect Standard Error to Standard Out**<br>
Type: boolean. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Adds '--stderr -' as an argument to cURL. By default, cURL writes its progress bar to stderr, which is interpreted by the build as error output. Enabling this checkbox suppresses that behavior.
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