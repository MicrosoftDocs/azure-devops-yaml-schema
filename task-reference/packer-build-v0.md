---
title: PackerBuild@0 - Build machine image v0 task
description: Build a machine image using Packer, which may be used for Azure Virtual machine scale set deployment (task version 0).
ms.date: 02/27/2024
monikerRange: "<=azure-pipelines"
---

# PackerBuild@0 - Build machine image v0 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to build a machine image using Packer, which may be used for Azure Virtual machine scale set deployment.

[!INCLUDE [workload-identity](./includes/workload-identity-not-supported.md)]
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# Build machine image v0
# Build a machine image using Packer, which may be used for Azure Virtual machine scale set deployment.
- task: PackerBuild@0
  inputs:
    templateType: 'builtin' # 'builtin' | 'custom'. Required. Packer template. Default: builtin.
    #customTemplateLocation: # string. Required when templateType = custom. Packer template location. 
    #customTemplateParameters: '{}' # string. Optional. Use when templateType = custom. Template parameters. Default: {}.
  # Azure Details
    ConnectedServiceName: # string. Required when templateType = builtin. Azure subscription. 
    location: # string. Required when templateType = builtin. Storage location. 
    storageAccountName: # string. Required when templateType = builtin. Storage account. 
    azureResourceGroup: # string. Required when templateType = builtin. Resource group. 
  # Deployment Inputs
    baseImageSource: 'default' # 'default' | 'customVhd'. Required when templateType = builtin. Base image source. Default: default.
    #baseImage: 'MicrosoftWindowsServer:WindowsServer:2012-R2-Datacenter:windows' # 'MicrosoftWindowsServer:WindowsServer:2012-R2-Datacenter:windows' | 'MicrosoftWindowsServer:WindowsServer:2016-Datacenter:windows' | 'MicrosoftWindowsServer:WindowsServer:2012-Datacenter:windows' | 'MicrosoftWindowsServer:WindowsServer:2008-R2-SP1:windows' | 'Canonical:UbuntuServer:14.04.4-LTS:linux' | 'Canonical:UbuntuServer:16.04-LTS:linux' | 'RedHat:RHEL:7.2:linux' | 'RedHat:RHEL:6.8:linux' | 'OpenLogic:CentOS:7.2:linux' | 'OpenLogic:CentOS:6.8:linux' | 'credativ:Debian:8:linux' | 'credativ:Debian:7:linux' | 'SUSE:openSUSE-Leap:42.2:linux' | 'SUSE:SLES:12-SP2:linux' | 'SUSE:SLES:11-SP4:linux'. Required when baseImageSource = default && templateType = builtin. Base image. Default: MicrosoftWindowsServer:WindowsServer:2012-R2-Datacenter:windows.
    #customImageUrl: # string. Required when baseImageSource = customVhd && templateType = builtin. Base image URL. 
    #customImageOSType: 'windows' # 'windows' | 'linux'. Required when baseImageSource = customVhd && templateType = builtin. Base image OS. Default: windows.
    packagePath: # string. Required when templateType = builtin. Deployment Package. 
    deployScriptPath: # string. Required when templateType = builtin. Deployment script. 
    #deployScriptArguments: # string. Optional. Use when templateType = builtin. Deployment script arguments. 
  # Advanced
    #additionalBuilderParameters: '{}' # string. Optional. Use when templateType = builtin. Additional Builder parameters. Default: {}.
    #skipTempFileCleanupDuringVMDeprovision: true # boolean. Optional. Use when templateType = builtin. Skip temporary file cleanup during deprovision. Default: true.
  # Output
    #imageUri: # string. Image URL.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Build Machine Image v0
# Build machine image using Packer. This image can be used for Azure Virtual machine scale set deployment.
- task: PackerBuild@0
  inputs:
    templateType: 'builtin' # 'builtin' | 'custom'. Required. Packer template. Default: builtin.
    #customTemplateLocation: # string. Required when templateType = custom. Packer template location. 
    #customTemplateParameters: '{}' # string. Optional. Use when templateType = custom. Template parameters. Default: {}.
  # Azure Details
    ConnectedServiceName: # string. Required when templateType = builtin. Azure subscription. 
    location: # string. Required when templateType = builtin. Storage location. 
    storageAccountName: # string. Required when templateType = builtin. Storage account. 
    azureResourceGroup: # string. Required when templateType = builtin. Resource group. 
  # Deployment Inputs
    baseImageSource: 'default' # 'default' | 'customVhd'. Required when templateType = builtin. Base image source. Default: default.
    #baseImage: 'MicrosoftWindowsServer:WindowsServer:2012-R2-Datacenter:windows' # 'MicrosoftWindowsServer:WindowsServer:2012-R2-Datacenter:windows' | 'MicrosoftWindowsServer:WindowsServer:2016-Datacenter:windows' | 'MicrosoftWindowsServer:WindowsServer:2012-Datacenter:windows' | 'MicrosoftWindowsServer:WindowsServer:2008-R2-SP1:windows' | 'Canonical:UbuntuServer:14.04.4-LTS:linux' | 'Canonical:UbuntuServer:16.04-LTS:linux' | 'RedHat:RHEL:7.2:linux' | 'RedHat:RHEL:6.8:linux' | 'OpenLogic:CentOS:7.2:linux' | 'OpenLogic:CentOS:6.8:linux' | 'credativ:Debian:8:linux' | 'credativ:Debian:7:linux' | 'SUSE:openSUSE-Leap:42.2:linux' | 'SUSE:SLES:12-SP2:linux' | 'SUSE:SLES:11-SP4:linux'. Required when baseImageSource = default && templateType = builtin. Base image. Default: MicrosoftWindowsServer:WindowsServer:2012-R2-Datacenter:windows.
    #customImageUrl: # string. Required when baseImageSource = customVhd && templateType = builtin. Base image URL. 
    #customImageOSType: 'windows' # 'windows' | 'linux'. Required when baseImageSource = customVhd && templateType = builtin. Base image OS. Default: windows.
    packagePath: # string. Required when templateType = builtin. Deployment Package. 
    deployScriptPath: # string. Required when templateType = builtin. Deployment script. 
    #deployScriptArguments: # string. Optional. Use when templateType = builtin. Deployment script arguments. 
  # Advanced
    #additionalBuilderParameters: '{}' # string. Optional. Use when templateType = builtin. Additional Builder parameters. Default: {}.
    #skipTempFileCleanupDuringVMDeprovision: true # boolean. Optional. Use when templateType = builtin. Skip temporary file cleanup during deprovision. Default: true.
  # Output
    #imageUri: # string. Image URL.
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

<!-- :::item name="templateType"::: -->
:::moniker range="<=azure-pipelines"

**`templateType`** - **Packer template**<br>
`string`. Required. Allowed values: `builtin` (Auto generated), `custom` (User provided). Default value: `builtin`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies whether you want the task to auto generate a Packer template or use a custom template provided by you.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customTemplateLocation"::: -->
:::moniker range="<=azure-pipelines"

**`customTemplateLocation`** - **Packer template location**<br>
`string`. Required when `templateType = custom`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the path to a custom user-provided template.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customTemplateParameters"::: -->
:::moniker range="<=azure-pipelines"

**`customTemplateParameters`** - **Template parameters**<br>
`string`. Optional. Use when `templateType = custom`. Default value: `{}`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies parameters which will be passed to Packer for building a custom template. This should map to the `variables` section in your custom template. For example, if the template has a variable named `drop-location`, then add a parameter here with the name `drop-location` and a value which you want to use. You can link the value to a release variable as well. To view/edit the additional parameters in a grid, click on `…` next to the text box.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ConnectedServiceName"::: -->
:::moniker range="<=azure-pipelines"

**`ConnectedServiceName`** - **Azure subscription**<br>
`string`. Required when `templateType = builtin`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the Azure Resource Manager subscription for baking and storing the machine image.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="location"::: -->
:::moniker range="<=azure-pipelines"

**`location`** - **Storage location**<br>
`string`. Required when `templateType = builtin`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the location for storing the built machine image. This location will also be used to create a temporary VM for the purpose of building an image.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="storageAccountName"::: -->
:::moniker range="<=azure-pipelines"

**`storageAccountName`** - **Storage account**<br>
`string`. Required when `templateType = builtin`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the storage account for storing the built machine image. This storage account must be pre-existing in the location selected.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureResourceGroup"::: -->
:::moniker range="<=azure-pipelines"

**`azureResourceGroup`** - **Resource group**<br>
`string`. Required when `templateType = builtin`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the Azure Resource group that contains the selected storage account.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="baseImageSource"::: -->
:::moniker range="<=azure-pipelines"

**`baseImageSource`** - **Base image source**<br>
`string`. Required when `templateType = builtin`. Allowed values: `default` (Gallery), `customVhd` (Custom). Default value: `default`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the source of a base image. You can either choose from a curated gallery of OS images or provide a URL of your custom image.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="baseImage"::: -->
:::moniker range="<=azure-pipelines"

**`baseImage`** - **Base image**<br>
`string`. Required when `baseImageSource = default && templateType = builtin`. Allowed values: `MicrosoftWindowsServer:WindowsServer:2012-R2-Datacenter:windows` (Windows 2012-R2-Datacenter), `MicrosoftWindowsServer:WindowsServer:2016-Datacenter:windows` (Windows 2016-Datacenter), `MicrosoftWindowsServer:WindowsServer:2012-Datacenter:windows` (Windows 2012-Datacenter), `MicrosoftWindowsServer:WindowsServer:2008-R2-SP1:windows` (Windows 2008-R2-SP1), `Canonical:UbuntuServer:14.04.4-LTS:linux` (Ubuntu 14.04.4-LTS), `Canonical:UbuntuServer:16.04-LTS:linux` (Ubuntu 16.04-LTS), `RedHat:RHEL:7.2:linux` (RHEL 7.2), `RedHat:RHEL:6.8:linux` (RHEL 6.8), `OpenLogic:CentOS:7.2:linux` (CentOS 7.2), `OpenLogic:CentOS:6.8:linux` (CentOS 6.8), `credativ:Debian:8:linux` (Debian 8), `credativ:Debian:7:linux` (Debian 7), `SUSE:openSUSE-Leap:42.2:linux` (openSUSE-Leap 42.2), `SUSE:SLES:12-SP2:linux` (SLES 12-SP2), `SUSE:SLES:11-SP4:linux` (SLES 11-SP4). Default value: `MicrosoftWindowsServer:WindowsServer:2012-R2-Datacenter:windows`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Chooses from a curated list of OS images. This is used for installing pre-requisite(s) and application(s) before capturing a machine image.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customImageUrl"::: -->
:::moniker range="<=azure-pipelines"

**`customImageUrl`** - **Base image URL**<br>
`string`. Required when `baseImageSource = customVhd && templateType = builtin`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the URL of a base image. This is used for installing pre-requisite(s) and application(s) before capturing a machine image.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customImageOSType"::: -->
:::moniker range="<=azure-pipelines"

**`customImageOSType`** - **Base image OS**<br>
`string`. Required when `baseImageSource = customVhd && templateType = builtin`. Allowed values: `windows`, `linux`. Default value: `windows`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="packagePath"::: -->
:::moniker range="<=azure-pipelines"

**`packagePath`** - **Deployment Package**<br>
`string`. Required when `templateType = builtin`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the path for the deployment package directory relative to `$(System.DefaultWorkingDirectory)`. Supports a minimatch pattern. Example path: `FrontendWebApp/**/GalleryApp`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deployScriptPath"::: -->
:::moniker range="<=azure-pipelines"

**`deployScriptPath`** - **Deployment script**<br>
`string`. Required when `templateType = builtin`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the relative path to a powershell script (for Windows) or a shell script (for Linux) which deploys the package. This script should be contained in the package path selected above. Supports a minimatch pattern. Example path: `deploy/**/scripts/windows/deploy.ps1`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deployScriptArguments"::: -->
:::moniker range="<=azure-pipelines"

**`deployScriptArguments`** - **Deployment script arguments**<br>
`string`. Optional. Use when `templateType = builtin`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the arguments to be passed to the deployment script.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="additionalBuilderParameters"::: -->
:::moniker range="<=azure-pipelines"

**`additionalBuilderParameters`** - **Additional Builder parameters**<br>
`string`. Optional. Use when `templateType = builtin`. Default value: `{}`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
In an auto-generated Packer template mode, the task creates a Packer template with an Azure builder. This builder is used to generate a machine image. You can add keys to the Azure builder to customize the generated Packer template. For example, setting `ssh_tty=true` in case you are using a CentOS base image, and you need to have a tty to run sudo.

To view or edit the additional parameters in a grid, click on `…` next to text box.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="skipTempFileCleanupDuringVMDeprovision"::: -->
:::moniker range="<=azure-pipelines"

**`skipTempFileCleanupDuringVMDeprovision`** - **Skip temporary file cleanup during deprovision**<br>
`boolean`. Optional. Use when `templateType = builtin`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
During the deprovisioning of a VM, skips the cleanup of temporary files uploaded to the VM. For more information, refer to [Azure Virtual Machine Image Builders](https://www.packer.io/docs/builders/azure.html#skip_clean).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="imageUri"::: -->
:::moniker range="<=azure-pipelines"

**`imageUri`** - **Image URL**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a name for the output variable which stores the generated machine image URL.
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

Use this task to build a machine image using Packer. This image can be used for Azure Virtual machine scale set deployment.

> [!NOTE]
> If you want to enable detailed logs, navigate to **Pipelines** > **Edit** > **Variables**, and then add a new variable *PACKER_LOG* and set its value to 1.
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
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.0.0 or greater |
| Task category | Deploy |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->