---
title: FtpUpload@1 - FTP upload v1 task
description: Upload files using FTP (task version 1).
ms.date: 09/01/2022
monikerRange: "<=azure-pipelines"
---

# FtpUpload@1 - FTP upload v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Upload files using FTP.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
FTP Upload.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# FTP upload v1
# Upload files using FTP.
- task: FtpUpload@1
  inputs:
    credentialsOption: 'serviceEndpoint' # 'serviceEndpoint' | 'inputs'. Required. Authentication Method. Default: 'serviceEndpoint'.
    serverEndpoint: # string. Required when credsType = serviceEndpoint. FTP Service Connection. 
    #serverUrl: # string. Required when credsType = inputs. Server URL. 
    #username: # string. Required when credsType = inputs. Username. 
    #password: # string. Required when credsType = inputs. Password. 
    rootDirectory: # string. Required. Root folder. 
    filePatterns: '**' # string. Required. File patterns. Default: '**'.
    remoteDirectory: '/upload/$(Build.BuildId)/' # string. Required. Remote directory. Default: '/upload/$(Build.BuildId)/'.
  # Advanced
    clean: false # boolean. Required. Delete remote directory. Default: false.
    cleanContents: false # boolean. Required when clean = false. Clear remote directory contents. Default: false.
    overwrite: true # boolean. Required. Overwrite. Default: true.
    preservePaths: false # boolean. Required. Preserve file paths. Default: false.
    trustSSL: false # boolean. Required. Trust server certificate. Default: false.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# FTP Upload v1
# FTP Upload.
- task: FtpUpload@1
  inputs:
    credentialsOption: 'serviceEndpoint' # 'serviceEndpoint' | 'inputs'. Required. Authentication Method. Default: 'serviceEndpoint'.
    serverEndpoint: # string. Required when credsType = serviceEndpoint. FTP Service Connection. 
    #serverUrl: # string. Required when credsType = inputs. Server URL. 
    #username: # string. Required when credsType = inputs. Username. 
    #password: # string. Required when credsType = inputs. Password. 
    rootDirectory: # string. Required. Root folder. 
    filePatterns: '**' # string. Required. File patterns. Default: '**'.
    remoteDirectory: '/upload/$(Build.BuildId)/' # string. Required. Remote directory. Default: '/upload/$(Build.BuildId)/'.
  # Advanced
    clean: false # boolean. Required. Delete remote directory. Default: false.
    cleanContents: false # boolean. Required when clean = false. Clear remote directory contents. Default: false.
    overwrite: true # boolean. Required. Overwrite. Default: true.
    preservePaths: false # boolean. Required. Preserve file paths. Default: false.
    trustSSL: false # boolean. Required. Trust server certificate. Default: false.
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

<!-- :::item name="credentialsOption"::: -->
:::moniker range="<=azure-pipelines"

**`credentialsOption`** - **Authentication Method**<br>
Input alias: `credsType`. Type: string. Required. Allowed values: 'serviceEndpoint', 'inputs'. Default value: 'serviceEndpoint'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Use FTP service connection or enter connection credentials.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="serverEndpoint"::: -->
:::moniker range=">=azure-pipelines-2019"

**`serverEndpoint`** - **FTP Service Connection**<br>
Type: string. Required when credsType = serviceEndpoint.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the service connection for your FTP server.  To create one, click the Manage link and create a new Generic service connection, enter the FTP server URL for the server URL, e.g. <b>`ftp://server.example.com`</b>, and required credentials.<p>Secure connections will always be made regardless of the specified protocol (<b>`ftp://`</b> or <b>`ftps://`</b>) if the target server supports FTPS.  To allow only secure connections, use the <b>`ftps://`</b> protocol, e.g. <b>`ftps://server.example.com`</b>.  Connections to servers not supporting FTPS will fail if <b>`ftps://`</b> is specified.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`serverEndpoint`** - **FTP Service Endpoint**<br>
Type: string. Required when credsType = serviceEndpoint.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the service connection for your FTP server.  To create one, click the Manage link and create a new Generic service connection, enter the FTP server URL for the server URL, e.g. <b>`ftp://server.example.com`</b>, and required credentials.<p>Secure connections will always be made regardless of the specified protocol (<b>`ftp://`</b> or <b>`ftps://`</b>) if the target server supports FTPS.  To allow only secure connections, use the <b>`ftps://`</b> protocol, e.g. <b>`ftps://server.example.com`</b>.  Connections to servers not supporting FTPS will fail if <b>`ftps://`</b> is specified.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="serverUrl"::: -->
:::moniker range="<=azure-pipelines"

**`serverUrl`** - **Server URL**<br>
Type: string. Required when credsType = inputs.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="username"::: -->
:::moniker range="<=azure-pipelines"

**`username`** - **Username**<br>
Type: string. Required when credsType = inputs.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="password"::: -->
:::moniker range="<=azure-pipelines"

**`password`** - **Password**<br>
Type: string. Required when credsType = inputs.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="rootDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`rootDirectory`** - **Root folder**<br>
Input alias: `rootFolder`. Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The source folder to upload files from.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="filePatterns"::: -->
:::moniker range="<=azure-pipelines"

**`filePatterns`** - **File patterns**<br>
Type: string. Required. Default value: '**'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
File paths or patterns of the files to upload.  Supports multiple lines of minimatch patterns.  [More Information](https://go.microsoft.com/fwlink/?LinkId=800269).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="remoteDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`remoteDirectory`** - **Remote directory**<br>
Input alias: `remotePath`. Type: string. Required. Default value: '/upload/$(Build.BuildId)/'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Upload files to this directory on the remote FTP server.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="clean"::: -->
:::moniker range="<=azure-pipelines"

**`clean`** - **Delete remote directory**<br>
Type: boolean. Required. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Delete the remote directory including its contents before uploading.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="cleanContents"::: -->
:::moniker range="<=azure-pipelines"

**`cleanContents`** - **Clear remote directory contents**<br>
Type: boolean. Required when clean = false. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Recursively delete all contents of the remote directory before uploading.  The existing directory will not be deleted.  For better performance, consider using `Delete remote directory` instead.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="overwrite"::: -->
:::moniker range="<=azure-pipelines"

**`overwrite`** - **Overwrite**<br>
Type: boolean. Required. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Overwrite existing files in the remote directory.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="preservePaths"::: -->
:::moniker range="<=azure-pipelines"

**`preservePaths`** - **Preserve file paths**<br>
Type: boolean. Required. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If selected, the relative local directory structure is recreated under the remote directory where files are uploaded.  Otherwise, files are uploaded directly to the remote directory without creating additional subdirectories.<p>For example, suppose your source folder is: <b>`/home/user/source/`</b> and contains the file: <b>`foo/bar/foobar.txt`</b>, and your remote directory is: <b>`/uploads/`</b>.<br>If selected, the file is uploaded to: <b>`/uploads/foo/bar/foobar.txt`</b>.  Otherwise, to: <b>`/uploads/foobar.txt`</b>.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="trustSSL"::: -->
:::moniker range="<=azure-pipelines"

**`trustSSL`** - **Trust server certificate**<br>
Type: boolean. Required. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selecting this option results in the FTP server's SSL certificate being trusted with ftps://, even if it is self-signed or cannot be validated by a Certificate Authority (CA).
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