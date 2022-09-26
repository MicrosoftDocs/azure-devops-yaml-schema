---
title: JavaToolInstaller@0 - Java tool installer v0 task
description: Acquire a specific version of Java from a user-supplied Azure blob or the tool cache and sets JAVA_HOME.
ms.date: 09/26/2022
monikerRange: "<=azure-pipelines"
---

# JavaToolInstaller@0 - Java tool installer v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Acquire a specific version of Java from a user-supplied Azure blob or the tool cache and sets JAVA_HOME.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Acquires a specific version of Java from a user supplied Azure blob or the tools cache and sets JAVA_HOME. Use this task to change the version of Java used in Java tasks.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2022"

```yaml
# Java tool installer v0
# Acquire a specific version of Java from a user-supplied Azure blob or the tool cache and sets JAVA_HOME.
- task: JavaToolInstaller@0
  inputs:
    versionSpec: '8' # string. Required. JDK version. Default: 8.
    jdkArchitectureOption: # 'x64' | 'x86'. Required. JDK architecture. 
    jdkSourceOption: # 'AzureStorage' | 'LocalDirectory' | 'PreInstalled'. Required. JDK source. 
    #jdkFile: # string. Required when jdkSourceOption == LocalDirectory. JDK file. 
    #azureResourceManagerEndpoint: # string. Required when jdkSourceOption == AzureStorage. Azure subscription. 
    #azureStorageAccountName: # string. Required when jdkSourceOption == AzureStorage. Storage account name. 
    #azureContainerName: # string. Required when jdkSourceOption == AzureStorage. Container name. 
    #azureCommonVirtualFile: # string. Required when jdkSourceOption == AzureStorage. Common virtual path. 
    #jdkDestinationDirectory: # string. Required when jdkSourceOption != PreInstalled. Destination directory. 
    #cleanDestinationDirectory: true # boolean. Required when jdkSourceOption != PreInstalled. Clean destination directory. Default: true.
    #createExtractDirectory: true # boolean. Optional. Use when jdkSourceOption != PreInstalled. Create directory for extracting. Default: true.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2020 <=azure-pipelines-2020.1"

```yaml
# Java tool installer v0
# Acquire a specific version of Java from a user-supplied Azure blob or the tool cache and sets JAVA_HOME.
- task: JavaToolInstaller@0
  inputs:
    versionSpec: '8' # string. Required. JDK version. Default: 8.
    jdkArchitectureOption: # 'x64' | 'x86'. Required. JDK architecture. 
    jdkSourceOption: # 'AzureStorage' | 'LocalDirectory' | 'PreInstalled'. Required. JDK source. 
    #jdkFile: # string. Required when jdkSourceOption == LocalDirectory. JDK file. 
    #azureResourceManagerEndpoint: # string. Required when jdkSourceOption == AzureStorage. Azure subscription. 
    #azureStorageAccountName: # string. Required when jdkSourceOption == AzureStorage. Storage account name. 
    #azureContainerName: # string. Required when jdkSourceOption == AzureStorage. Container name. 
    #azureCommonVirtualFile: # string. Required when jdkSourceOption == AzureStorage. Common virtual path. 
    #jdkDestinationDirectory: # string. Required when jdkSourceOption != PreInstalled. Destination directory. 
    #cleanDestinationDirectory: true # boolean. Required when jdkSourceOption != PreInstalled. Clean destination directory. Default: true.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

```yaml
# Java tool installer v0
# Acquire a specific version of Java from a user-supplied Azure blob or the tool cache and sets JAVA_HOME.
- task: JavaToolInstaller@0
  inputs:
    versionSpec: '8' # string. Required. JDK version. Default: 8.
    jdkArchitectureOption: # 'x64' | 'x86'. Required. JDK architecture. 
    jdkSourceOption: # 'AzureStorage' | 'LocalDirectory'. Required. JDK source. 
    #jdkFile: # string. Required when jdkSourceOption == LocalDirectory. JDK file. 
    #azureResourceManagerEndpoint: # string. Required when jdkSourceOption == AzureStorage. Azure subscription. 
    #azureStorageAccountName: # string. Required when jdkSourceOption == AzureStorage. Storage account name. 
    #azureContainerName: # string. Required when jdkSourceOption == AzureStorage. Container name. 
    #azureCommonVirtualFile: # string. Required when jdkSourceOption == AzureStorage. Common virtual path. 
    jdkDestinationDirectory: # string. Required. Destination directory. 
    cleanDestinationDirectory: true # boolean. Required. Clean destination directory. Default: true.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Java Tool Installer v0
# Acquires a specific version of Java from a user supplied Azure blob or the tools cache and sets JAVA_HOME. Use this task to change the version of Java used in Java tasks.
- task: JavaToolInstaller@0
  inputs:
    versionSpec: '8' # string. Required. JDK version. Default: 8.
    jdkArchitectureOption: # 'x64' | 'x86'. Required. JDK architecture. 
    jdkSourceOption: # 'AzureStorage' | 'LocalDirectory'. Required. JDK source. 
    #jdkFile: # string. Required when jdkSourceOption == LocalDirectory. JDK file. 
    #azureResourceManagerEndpoint: # string. Required when jdkSourceOption == AzureStorage. Azure subscription. 
    #azureStorageAccountName: # string. Required when jdkSourceOption == AzureStorage. Storage account name. 
    #azureContainerName: # string. Required when jdkSourceOption == AzureStorage. Container name. 
    #azureCommonVirtualFile: # string. Required when jdkSourceOption == AzureStorage. Common virtual path. 
    jdkDestinationDirectory: # string. Required. Destination directory. 
    cleanDestinationDirectory: true # boolean. Required. Clean destination directory. Default: true.
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

<!-- :::item name="versionSpec"::: -->
:::moniker range=">=azure-pipelines-2019"

**`versionSpec`** - **JDK version**<br>
`string`. Required. Default value: `8`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
A number that specifies the JDK version to make available on the path. Use a whole number version, such as 10.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`versionSpec`** - **JDK version**<br>
`string`. Required. Default value: `1.8`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
A number that specifies the JDK version to make available on the path. Use a whole number version, such as 10.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jdkArchitectureOption"::: -->
:::moniker range="<=azure-pipelines"

**`jdkArchitectureOption`** - **JDK architecture**<br>
`string`. Required. Allowed values: `x64`, `x86`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The architecture (x86, x64) of the JDK.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jdkSourceOption"::: -->
:::moniker range=">=azure-pipelines-2020"

**`jdkSourceOption`** - **JDK source**<br>
`string`. Required. Allowed values: `AzureStorage` (Azure Storage), `LocalDirectory` (Local Directory), `PreInstalled` (Pre-installed).<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Source for the compressed JDK.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="<=azure-pipelines-2019.1"

**`jdkSourceOption`** - **JDK source**<br>
`string`. Required. Allowed values: `AzureStorage` (Azure Storage), `LocalDirectory` (Local Directory).<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Source for the compressed JDK.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jdkFile"::: -->
:::moniker range="<=azure-pipelines"

**`jdkFile`** - **JDK file**<br>
`string`. Required when `jdkSourceOption == LocalDirectory`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to where the compressed JDK is located. The path could be in your source repository or a local path on the agent.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureResourceManagerEndpoint"::: -->
:::moniker range="<=azure-pipelines"

**`azureResourceManagerEndpoint`** - **Azure subscription**<br>
`string`. Required when `jdkSourceOption == AzureStorage`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Choose the Azure Resource Manager subscription for the JDK.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureStorageAccountName"::: -->
:::moniker range="<=azure-pipelines"

**`azureStorageAccountName`** - **Storage account name**<br>
`string`. Required when `jdkSourceOption == AzureStorage`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Azure Classic and Resource Manager storage accounts are listed. Select the storage account name in which the JDK is located.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureContainerName"::: -->
:::moniker range="<=azure-pipelines"

**`azureContainerName`** - **Container name**<br>
`string`. Required when `jdkSourceOption == AzureStorage`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Name of the container in the storage account in which the JDK is located.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureCommonVirtualFile"::: -->
:::moniker range="<=azure-pipelines"

**`azureCommonVirtualFile`** - **Common virtual path**<br>
`string`. Required when `jdkSourceOption == AzureStorage`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to the JDK inside the Azure storage container.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jdkDestinationDirectory"::: -->
:::moniker range=">=azure-pipelines-2020"

**`jdkDestinationDirectory`** - **Destination directory**<br>
`string`. Required when `jdkSourceOption != PreInstalled`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Destination directory into which JDK should be extracted. On Linux and Windows, this is used as the destination directory for JDK installation. On macOS, this directory is used as a temporary folder for extracting of .dmg's since macOS doesn't support installing of JDK to specific directory.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="<=azure-pipelines-2019.1"

**`jdkDestinationDirectory`** - **Destination directory**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Destination directory into which JDK should be extracted. On Linux and Windows, this is used as the destination directory for JDK installation. On macOS, this directory is used as a temporary folder for extracting of .dmg's since macOS doesn't support installing of JDK to specific directory.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="cleanDestinationDirectory"::: -->
:::moniker range=">=azure-pipelines-2020"

**`cleanDestinationDirectory`** - **Clean destination directory**<br>
`boolean`. Required when `jdkSourceOption != PreInstalled`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select this option to clean the destination directory before JDK is extracted into it.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="<=azure-pipelines-2019.1"

**`cleanDestinationDirectory`** - **Clean destination directory**<br>
`boolean`. Required. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select this option to clean the destination directory before JDK is extracted into it.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="createExtractDirectory"::: -->
:::moniker range=">=azure-pipelines-2022"

**`createExtractDirectory`** - **Create directory for extracting**<br>
`boolean`. Optional. Use when `jdkSourceOption != PreInstalled`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
By default, task is creating a directory similar to this JAVA_HOME_8_X64_OpenJDK_zip for extracting JDK. This option allows to disable creation of this folder, in this case, JDK will be located in the root of jdkDestinationDirectory.
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

Use this task to acquire a specific version of Java from a user supplied Azure blob,
from a location in the source or on the agent, or from the tools cache. The task also sets the JAVA_HOME environment variable.
Use this task to change the version of Java used in Java tasks.

> [!NOTE]
>
> To run **Java Tool Installer** task on macOS it is required for user under which agent is running to have permission to execute **sudo** command without a password. 
> You can follow the next steps to enable this permission:
> 1) Run *sudo visudo* command, it will open sudoers file for editing.
> 2) Go to the bottom of the file and add the following line: *user ALL=NOPASSWD: /usr/sbin/installer* (Replace 'user' by the actual user alias)
> 3) Save and close the file.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

Here's an example of getting the archive file from a local directory on Linux.
The file should be an archive (.zip, .gz) of the `JAVA_HOME` directory so that it includes the `bin`, `lib`, `include`, `jre`, etc. directories.

```yaml
  - task: JavaToolInstaller@0
    inputs:
      versionSpec: "11"
      jdkArchitectureOption: x64
      jdkSourceOption: LocalDirectory
      jdkFile: "/builds/openjdk-11.0.2_linux-x64_bin.tar.gz"
      jdkDestinationDirectory: "/builds/binaries/externals"
      cleanDestinationDirectory: true
```

Here's an example of downloading the archive file from Azure Storage.
The file should be an archive (.zip, .gz) of the `JAVA_HOME` directory so that it includes the `bin`, `lib`, `include`, `jre`, etc. directories.

```yaml
- task: JavaToolInstaller@0
  inputs:
    versionSpec: '6'
    jdkArchitectureOption: 'x64'
    jdkSourceOption: AzureStorage
    azureResourceManagerEndpoint: myARMServiceConnection
    azureStorageAccountName: myAzureStorageAccountName
    azureContainerName: myAzureStorageContainerName
    azureCommonVirtualFile: 'jdk1.6.0_45.zip'
    jdkDestinationDirectory: '$(agent.toolsDirectory)/jdk6'
    cleanDestinationDirectory: false
```

Here's an example of using "pre-installed" feature. This feature allows you to use Java versions that are pre-installed on the Microsoft-hosted agent. You can find available pre-installed versions of Java in [the included software column in the hosted agents table](/azure/devops/pipelines/agents/hosted#software).

```yaml
- task: JavaToolInstaller@0
  inputs:
    versionSpec: '8'
    jdkArchitectureOption: 'x86'
    jdkSourceOption: 'PreInstalled'
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
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | Running this task satisfies the following [demands](/azure/devops/pipelines/process/demands) for any subsequent tasks in the same job: Java, JDK |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | This task runs using the following [command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions): restricted |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | This task has permission to [set the following variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions): PATH, JAVA_HOME* |
| Agent version |  2.182.1 or greater |
| Task category | Tool |

:::moniker-end

:::moniker range="=azure-pipelines-2020.1"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | Running this task satisfies the following [demands](/azure/devops/pipelines/process/demands) for any subsequent tasks in the same job: Java, JDK |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version | All supported agent versions. |
| Task category | Tool |

:::moniker-end

:::moniker range="<=azure-pipelines-2020"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | Running this task satisfies the following [demands](/azure/devops/pipelines/process/demands) for any subsequent tasks in the same job: Java |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version | All supported agent versions. |
| Task category | Tool |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

For an explanation of tool installers and examples, see [Tool installers](/azure/devops/pipelines/process/tasks#tool-installers).
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->