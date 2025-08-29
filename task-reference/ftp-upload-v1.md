---
title: FtpUpload@1 - FTP upload v1 task
description: Upload files using FTP (task version 1).
ms.date: 08/29/2025
monikerRange: "<=azure-pipelines"
---

# FtpUpload@1 - FTP upload v1 task

<!-- :::description::: -->
:::moniker range="=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to upload files to a remote machine using FTP or securely with FTPS.

This version of the task is deprecated; use [FtpUpload@2](./ftp-upload-v2.md).
<!-- :::editable-content-end::: -->

<!-- This task is deprecated. -->

:::moniker-end

:::moniker range="<=azure-pipelines-2022.2"

<!-- :::editable-content name="description"::: -->
Use this task to upload files to a remote machine using FTP or securely with FTPS.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="<=azure-pipelines"

```yaml
# FTP upload v1
# Upload files using FTP.
- task: FtpUpload@1
  inputs:
    credentialsOption: 'serviceEndpoint' # 'serviceEndpoint' | 'inputs'. Alias: credsType. Required. Authentication Method. Default: serviceEndpoint.
    serverEndpoint: # string. Required when credsType = serviceEndpoint. FTP Service Connection. 
    #serverUrl: # string. Required when credsType = inputs. Server URL. 
    #username: # string. Required when credsType = inputs. Username. 
    #password: # string. Required when credsType = inputs. Password. 
    rootDirectory: # string. Alias: rootFolder. Required. Root folder. 
    filePatterns: '**' # string. Required. File patterns. Default: **.
    remoteDirectory: '/upload/$(Build.BuildId)/' # string. Alias: remotePath. Required. Remote directory. Default: /upload/$(Build.BuildId)/.
  # Advanced
    #clean: false # boolean. Delete remote directory. Default: false.
    #cleanContents: false # boolean. Optional. Use when clean = false. Clear remote directory contents. Default: false.
    #overwrite: true # boolean. Overwrite. Default: true.
    #preservePaths: false # boolean. Preserve file paths. Default: false.
    #trustSSL: false # boolean. Trust server certificate. Default: false.
```

:::moniker-end

<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="credentialsOption"::: -->
:::moniker range="<=azure-pipelines"

**`credentialsOption`** - **Authentication Method**<br>
[Input alias](index.md#what-are-task-input-aliases): `credsType`. `string`. Required. Allowed values: `serviceEndpoint` (FTP service connection), `inputs` (Enter credentials). Default value: `serviceEndpoint`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the authentication method. Use an FTP service connection or enter the connection credentials.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="serverEndpoint"::: -->
:::moniker range="<=azure-pipelines"

**`serverEndpoint`** - **FTP Service Connection**<br>
`string`. Required when `credsType = serviceEndpoint`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the service connection for the FTP server. To create one, click the Manage link and create a new generic service connection, and then enter the FTP server URL for the server URL, e.g. `ftp://server.example.com`, and the required credentials.

Secure connections will always be made regardless of the specified protocol (`ftp://` or `ftps://`) if the target server supports FTPS. To allow only secure connections, use the `ftps://` protocol, e.g. `ftps://server.example.com`. Connections to servers not supporting FTPS will fail if `ftps://` is specified.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="serverUrl"::: -->
:::moniker range="<=azure-pipelines"

**`serverUrl`** - **Server URL**<br>
`string`. Required when `credsType = inputs`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the URL for the FTP server.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="username"::: -->
:::moniker range="<=azure-pipelines"

**`username`** - **Username**<br>
`string`. Required when `credsType = inputs`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the user name for the FTP connection.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="password"::: -->
:::moniker range="<=azure-pipelines"

**`password`** - **Password**<br>
`string`. Required when `credsType = inputs`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the password for the FTP connection.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="rootDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`rootDirectory`** - **Root folder**<br>
[Input alias](index.md#what-are-task-input-aliases): `rootFolder`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the source folder to upload files from.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="filePatterns"::: -->
:::moniker range="<=azure-pipelines"

**`filePatterns`** - **File patterns**<br>
`string`. Required. Default value: `**`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the file paths or patterns of the files to upload. The string supports multiple lines of minimatch patterns. Learn more about [file matching patterns](/azure/devops/pipelines/tasks/file-matching-patterns).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="remoteDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`remoteDirectory`** - **Remote directory**<br>
[Input alias](index.md#what-are-task-input-aliases): `remotePath`. `string`. Required. Default value: `/upload/$(Build.BuildId)/`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the directory on the remote FTP server where the task uploads files.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="clean"::: -->
:::moniker range="<=azure-pipelines"

**`clean`** - **Delete remote directory**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Deletes the remote directory, including its contents, before uploading.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="cleanContents"::: -->
:::moniker range="<=azure-pipelines"

**`cleanContents`** - **Clear remote directory contents**<br>
`boolean`. Optional. Use when `clean = false`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Recursively deletes all content in the remote directory before uploading. The existing directory will not be deleted. For better performance, use `clean` instead.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="overwrite"::: -->
:::moniker range="<=azure-pipelines"

**`overwrite`** - **Overwrite**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Overwrites existing files in the remote directory.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="preservePaths"::: -->
:::moniker range="<=azure-pipelines"

**`preservePaths`** - **Preserve file paths**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If selected, the relative local directory structure is recreated under the remote directory where files are uploaded. Otherwise, files are uploaded directly to the remote directory without creating additional subdirectories.

For example, suppose your source folder is `/home/user/source/`, which contains the file `foo/bar/foobar.txt`, and your remote directory is: `/uploads/`. If this boolean is selected, the file is uploaded to `/uploads/foo/bar/foobar.txt`. If this boolean is not selected, the file is uploaded to `/uploads/foobar.txt`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="trustSSL"::: -->
:::moniker range="<=azure-pipelines"

**`trustSSL`** - **Trust server certificate**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Trusts the FTP server's SSL certificate with `ftps://`, even if it is self-signed or cannot be validated by a certificate authority (CA).
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

Use this task to upload files to a remote machine using FTP or securely with FTPS.

:::moniker range="<=azure-pipelines"

> [!NOTE]
> There is a newer version of this task available at [FtpUpload@2](./ftp-upload-v2.md).

:::moniker-end

### Where can I learn more about file matching patterns?

* [File matching patterns reference](/azure/devops/pipelines/tasks/file-matching-patterns)
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

:::moniker range="<=azure-pipelines-2020.1"

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
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->