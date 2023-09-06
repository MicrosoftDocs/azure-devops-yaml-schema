---
title: PackerBuild@1 - Build machine image v1 task
description: Build a machine image using Packer, which may be used for Azure Virtual machine scale set deployment.
ms.date: 07/31/2023
monikerRange: ">=azure-pipelines-2019.1"
---

# PackerBuild@1 - Build machine image v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Use this task to build a machine image using Packer, which may be used for Azure Virtual machine scale set deployment.

[!INCLUDE [workflow-identity](../content/includes/workflow-identity.md)]

<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020"

```yaml
# Build machine image v1
# Build a machine image using Packer, which may be used for Azure Virtual machine scale set deployment.
- task: PackerBuild@1
  inputs:
    templateType: 'builtin' # 'builtin' | 'custom'. Required. Packer template. Default: builtin.
    #customTemplateLocation: # string. Required when templateType = custom. Packer template location. 
    #customTemplateParameters: '{}' # string. Optional. Use when templateType = custom. Template parameters. Default: {}.
  # Azure Details
    ConnectedServiceName: # string. Required when templateType = builtin. Azure subscription. 
    #isManagedImage: true # boolean. Optional. Use when templateType = builtin. Managed VM disk image. Default: true.
    #managedImageName: # string. Required when isManagedImage = true && templateType = builtin. Managed VM Disk Image Name. 
    location: # string. Required when templateType = builtin. Storage location. 
    storageAccountName: # string. Required when templateType = builtin. Storage account. 
    azureResourceGroup: # string. Required when templateType = builtin. Resource group. 
  # Deployment Inputs
    baseImageSource: 'default' # 'default' | 'customVhd'. Required when templateType = builtin. Base image source. Default: default.
    #baseImage: 'MicrosoftWindowsServer:WindowsServer:2012-R2-Datacenter:windows' # 'MicrosoftWindowsServer:WindowsServer:2012-R2-Datacenter:windows' | 'MicrosoftWindowsServer:WindowsServer:2016-Datacenter:windows' | 'MicrosoftWindowsServer:WindowsServer:2012-Datacenter:windows' | 'MicrosoftWindowsServer:WindowsServer:2008-R2-SP1:windows' | 'Canonical:UbuntuServer:14.04.4-LTS:linux' | 'Canonical:UbuntuServer:16.04-LTS:linux' | 'Canonical:UbuntuServer:18.04-LTS:linux' | 'RedHat:RHEL:7.2:linux' | 'RedHat:RHEL:6.8:linux' | 'OpenLogic:CentOS:7.2:linux' | 'OpenLogic:CentOS:6.8:linux' | 'credativ:Debian:8:linux' | 'credativ:Debian:7:linux' | 'SUSE:openSUSE-Leap:42.2:linux' | 'SUSE:SLES:12-SP2:linux' | 'SUSE:SLES:11-SP4:linux'. Required when baseImageSource = default && templateType = builtin. Base image. Default: MicrosoftWindowsServer:WindowsServer:2012-R2-Datacenter:windows.
    #customImageUrl: # string. Required when baseImageSource = customVhd && templateType = builtin. Base image URL. 
    #customImageOSType: 'windows' # 'windows' | 'linux'. Required when baseImageSource = customVhd && templateType = builtin. Base image OS. Default: windows.
    packagePath: # string. Required when templateType = builtin. Deployment Package. 
    deployScriptPath: # string. Required when templateType = builtin. Deployment script. 
    #deployScriptArguments: # string. Optional. Use when templateType = builtin. Deployment script arguments. 
  # Advanced
    #additionalBuilderParameters: '{"vm_size":"Standard_D3_v2"}' # string. Optional. Use when templateType = builtin. Additional Builder parameters. Default: {"vm_size":"Standard_D3_v2"}.
    #skipTempFileCleanupDuringVMDeprovision: true # boolean. Optional. Use when templateType = builtin. Skip temporary file cleanup during deprovision. Default: true.
    #packerVersion: # string. Optional. Use when templateType = custom. Packer Version. 
  # Output
    #imageUri: # string. Image URL or Name. 
    #imageId: # string. Azure Resource Id.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

```yaml
# Build machine image v1
# Build a machine image using Packer, which may be used for Azure Virtual machine scale set deployment.
- task: PackerBuild@1
  inputs:
    templateType: 'builtin' # 'builtin' | 'custom'. Required. Packer template. Default: builtin.
    #customTemplateLocation: # string. Required when templateType = custom. Packer template location. 
    #customTemplateParameters: '{}' # string. Optional. Use when templateType = custom. Template parameters. Default: {}.
  # Azure Details
    ConnectedServiceName: # string. Required when templateType = builtin. Azure subscription. 
    #isManagedImage: true # boolean. Optional. Use when templateType = builtin. Managed VM disk image. Default: true.
    #managedImageName: # string. Required when isManagedImage = true && templateType = builtin. Managed VM Disk Image Name. 
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
    #additionalBuilderParameters: '{"vm_size":"Standard_D3_v2"}' # string. Optional. Use when templateType = builtin. Additional Builder parameters. Default: {"vm_size":"Standard_D3_v2"}.
    #skipTempFileCleanupDuringVMDeprovision: true # boolean. Optional. Use when templateType = builtin. Skip temporary file cleanup during deprovision. Default: true.
  # Output
    #imageUri: # string. Image URL or Name. 
    #imageId: # string. Azure Resource Id.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="templateType"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`templateType`** - **Packer template**<br>
`string`. Required. Allowed values: `builtin` (Auto generated), `custom` (User provided). Default value: `builtin`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies whether the task auto generates a Packer template or uses a custom template provided by you.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customTemplateLocation"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`customTemplateLocation`** - **Packer template location**<br>
`string`. Required when `templateType = custom`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the path to a custom user-provided template.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customTemplateParameters"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`customTemplateParameters`** - **Template parameters**<br>
`string`. Optional. Use when `templateType = custom`. Default value: `{}`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the parameters which will be passed to the Packer for building a custom template. This should map to a `variables` section in your custom template. For example, if the template has a variable named `drop-location`, then add a parameter here with the name `drop-location` and a value which you want to use. You can link the value to a release variable as well. To view/edit the additional parameters in a grid, click on `…` next to text box.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ConnectedServiceName"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`ConnectedServiceName`** - **Azure subscription**<br>
`string`. Required when `templateType = builtin`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the Azure Resource Manager subscription for baking and storing the machine image.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="isManagedImage"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`isManagedImage`** - **Managed VM disk image**<br>
`boolean`. Optional. Use when `templateType = builtin`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Checks if the generated image should be a managed image.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="managedImageName"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`managedImageName`** - **Managed VM Disk Image Name**<br>
`string`. Required when `isManagedImage = true && templateType = builtin`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of the Managed disk image for auto-generated templates.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="location"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`location`** - **Storage location**<br>
`string`. Required when `templateType = builtin`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the location for storing the built machine image. This location will also be used to create a temporary VM for the purpose of building an image.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="storageAccountName"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`storageAccountName`** - **Storage account**<br>
`string`. Required when `templateType = builtin`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the storage account for storing the built machine image. This storage account must be pre-existing in the location selected.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureResourceGroup"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`azureResourceGroup`** - **Resource group**<br>
`string`. Required when `templateType = builtin`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the Azure Resource group that contains the selected storage account.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="baseImageSource"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`baseImageSource`** - **Base image source**<br>
`string`. Required when `templateType = builtin`. Allowed values: `default` (Gallery), `customVhd` (Custom). Default value: `default`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the source of the base image. You can either choose from a curated gallery of OS images or provide a URL of your custom VHD image.
> [!NOTE]
> If you have selected the option to create a Managed image by checking the `Managed VM disk image` option, then you should only choose the `Gallery` option here. `Custom` source is not supported to create a managed image.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="baseImage"::: -->
:::moniker range=">=azure-pipelines-2020"

**`baseImage`** - **Base image**<br>
`string`. Required when `baseImageSource = default && templateType = builtin`. Allowed values: `MicrosoftWindowsServer:WindowsServer:2012-R2-Datacenter:windows` (Windows 2012-R2-Datacenter), `MicrosoftWindowsServer:WindowsServer:2016-Datacenter:windows` (Windows 2016-Datacenter), `MicrosoftWindowsServer:WindowsServer:2012-Datacenter:windows` (Windows 2012-Datacenter), `MicrosoftWindowsServer:WindowsServer:2008-R2-SP1:windows` (Windows 2008-R2-SP1), `Canonical:UbuntuServer:14.04.4-LTS:linux` (Ubuntu 14.04.4-LTS), `Canonical:UbuntuServer:16.04-LTS:linux` (Ubuntu 16.04-LTS), `Canonical:UbuntuServer:18.04-LTS:linux` (Ubuntu 18.04-LTS), `RedHat:RHEL:7.2:linux` (RHEL 7.2), `RedHat:RHEL:6.8:linux` (RHEL 6.8), `OpenLogic:CentOS:7.2:linux` (CentOS 7.2), `OpenLogic:CentOS:6.8:linux` (CentOS 6.8), `credativ:Debian:8:linux` (Debian 8), `credativ:Debian:7:linux` (Debian 7), `SUSE:openSUSE-Leap:42.2:linux` (openSUSE-Leap 42.2), `SUSE:SLES:12-SP2:linux` (SLES 12-SP2), `SUSE:SLES:11-SP4:linux` (SLES 11-SP4). Default value: `MicrosoftWindowsServer:WindowsServer:2012-R2-Datacenter:windows`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Chooses from a curated list of OS images. This will be used for installing pre-requisite(s) and application(s) before capturing a machine image.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

**`baseImage`** - **Base image**<br>
`string`. Required when `baseImageSource = default && templateType = builtin`. Allowed values: `MicrosoftWindowsServer:WindowsServer:2012-R2-Datacenter:windows` (Windows 2012-R2-Datacenter), `MicrosoftWindowsServer:WindowsServer:2016-Datacenter:windows` (Windows 2016-Datacenter), `MicrosoftWindowsServer:WindowsServer:2012-Datacenter:windows` (Windows 2012-Datacenter), `MicrosoftWindowsServer:WindowsServer:2008-R2-SP1:windows` (Windows 2008-R2-SP1), `Canonical:UbuntuServer:14.04.4-LTS:linux` (Ubuntu 14.04.4-LTS), `Canonical:UbuntuServer:16.04-LTS:linux` (Ubuntu 16.04-LTS), `RedHat:RHEL:7.2:linux` (RHEL 7.2), `RedHat:RHEL:6.8:linux` (RHEL 6.8), `OpenLogic:CentOS:7.2:linux` (CentOS 7.2), `OpenLogic:CentOS:6.8:linux` (CentOS 6.8), `credativ:Debian:8:linux` (Debian 8), `credativ:Debian:7:linux` (Debian 7), `SUSE:openSUSE-Leap:42.2:linux` (openSUSE-Leap 42.2), `SUSE:SLES:12-SP2:linux` (SLES 12-SP2), `SUSE:SLES:11-SP4:linux` (SLES 11-SP4). Default value: `MicrosoftWindowsServer:WindowsServer:2012-R2-Datacenter:windows`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Chooses from a curated list of OS images. This will be used for installing pre-requisite(s) and application(s) before capturing a machine image.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customImageUrl"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`customImageUrl`** - **Base image URL**<br>
`string`. Required when `baseImageSource = customVhd && templateType = builtin`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the URL of a base image. This will be used for installing pre-requisite(s) and application(s) before capturing a machine image.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customImageOSType"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`customImageOSType`** - **Base image OS**<br>
`string`. Required when `baseImageSource = customVhd && templateType = builtin`. Allowed values: `windows`, `linux`. Default value: `windows`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="packagePath"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`packagePath`** - **Deployment Package**<br>
`string`. Required when `templateType = builtin`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the path for a deployment package directory relative to `$(System.DefaultWorkingDirectory)`. Supports a minimatch pattern. Example path: `FrontendWebApp/**/GalleryApp`

>[!NOTE]
> This package will be copied to a temporary virtual machine which Packer creates. If the package contains a large number of files and/or the files are very large in size, the upload can take a long time (possibly running for a few hours). To optimize the upload time, please see if the size of the package can be meaningfully reduced. Another alternative is to use an intermediary Azure storage account. Upload the package to a storage account prior to running this task. For this task, use a package containing a script which will download the required package from the storage account.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deployScriptPath"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`deployScriptPath`** - **Deployment script**<br>
`string`. Required when `templateType = builtin`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the relative path to the powershell script (for Windows) or the shell script (for Linux) which deploys the package. This script should be contained in the package path selected above. Supports a minimatch pattern. Example path: `deploy/**/scripts/windows/deploy.ps1`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deployScriptArguments"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`deployScriptArguments`** - **Deployment script arguments**<br>
`string`. Optional. Use when `templateType = builtin`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the arguments to be passed to the deployment script.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="additionalBuilderParameters"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`additionalBuilderParameters`** - **Additional Builder parameters**<br>
`string`. Optional. Use when `templateType = builtin`. Default value: `{"vm_size":"Standard_D3_v2"}`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
In the auto-generated Packer template mode, the task creates a Packer template with an Azure builder. This builder is used to generate a machine image. You can add keys to the Azure builder to customize the generated Packer template. For example: Setting `ssh_tty=true` if you are using a CentOS base image and you need to have a tty to run `sudo`.
To view/edit the additional parameters in a grid, click on `…` next to text box.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="skipTempFileCleanupDuringVMDeprovision"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`skipTempFileCleanupDuringVMDeprovision`** - **Skip temporary file cleanup during deprovision**<br>
`boolean`. Optional. Use when `templateType = builtin`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
During the deprovisioning of a VM, skips the cleanup of temporary files uploaded to the VM. Learn more about [Azure Virtual Machine Image Builders in Packer](https://www.packer.io/docs/builders/azure.html#skip_clean).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="packerVersion"::: -->
:::moniker range=">=azure-pipelines-2020"

**`packerVersion`** - **Packer Version**<br>
`string`. Optional. Use when `templateType = custom`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the version of Packer to install. This will work only with custom templates.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="imageUri"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`imageUri`** - **Image URL or Name**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a name for the output variable which will store the generated machine image VHD URL for an un-managed VM image or the image name for a managed VM image.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="imageId"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`imageId`** - **Azure Resource Id**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a name for the output variable which will store the Azure Resource ID for the newly created image.  This is for managed images only.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2019.1"

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

:::moniker range=">=azure-pipelines-2019.1"

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