---
title: PackerBuild@1 - Build machine image v1 task
description: Build a machine image using Packer, which may be used for Azure Virtual machine scale set deployment.
ms.date: 09/01/2022
monikerRange: ">=azure-pipelines-2019.1"
---

# PackerBuild@1 - Build machine image v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Build a machine image using Packer, which may be used for Azure Virtual machine scale set deployment.
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
    templateType: 'builtin' # 'builtin' | 'custom'. Required. Packer template. Default: 'builtin'.
    #customTemplateLocation: # string. Required when templateType = custom. Packer template location. 
    #customTemplateParameters: '{}' # string. Optional. Use when templateType = custom. Template parameters. Default: '{}'.
  # Azure Details
    ConnectedServiceName: # string. Required. Azure subscription. 
    isManagedImage: true # boolean. Required. Managed VM disk image. Default: true.
    managedImageName: # string. Required when isManagedImage = true. Managed VM Disk Image Name. 
    location: # string. Required. Storage location. 
    storageAccountName: # string. Required. Storage account. 
    azureResourceGroup: # string. Required. Resource group. 
  # Deployment Inputs
    baseImageSource: 'default' # 'default' | 'customVhd'. Required. Base image source. Default: 'default'.
    baseImage: 'MicrosoftWindowsServer:WindowsServer:2012-R2-Datacenter:windows' # 'MicrosoftWindowsServer:WindowsServer:2012-R2-Datacenter:windows' | 'MicrosoftWindowsServer:WindowsServer:2016-Datacenter:windows' | 'MicrosoftWindowsServer:WindowsServer:2012-Datacenter:windows' | 'MicrosoftWindowsServer:WindowsServer:2008-R2-SP1:windows' | 'Canonical:UbuntuServer:14.04.4-LTS:linux' | 'Canonical:UbuntuServer:16.04-LTS:linux' | 'Canonical:UbuntuServer:18.04-LTS:linux' | 'RedHat:RHEL:7.2:linux' | 'RedHat:RHEL:6.8:linux' | 'OpenLogic:CentOS:7.2:linux' | 'OpenLogic:CentOS:6.8:linux' | 'credativ:Debian:8:linux' | 'credativ:Debian:7:linux' | 'SUSE:openSUSE-Leap:42.2:linux' | 'SUSE:SLES:12-SP2:linux' | 'SUSE:SLES:11-SP4:linux'. Required when baseImageSource = default. Base image. Default: 'MicrosoftWindowsServer:WindowsServer:2012-R2-Datacenter:windows'.
    #customImageUrl: # string. Required when baseImageSource = customVhd. Base image URL. 
    #customImageOSType: 'windows' # 'windows' | 'linux'. Required when baseImageSource = customVhd. Base image OS. Default: 'windows'.
    packagePath: # string. Required. Deployment Package. 
    deployScriptPath: # string. Required. Deployment script. 
    #deployScriptArguments: # string. Deployment script arguments. 
  # Advanced
    #additionalBuilderParameters: '{"vm_size":"Standard_D3_v2"}' # string. Optional. Use when templateType = builtin. Additional Builder parameters. Default: '{"vm_size":"Standard_D3_v2"}'.
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
    templateType: 'builtin' # 'builtin' | 'custom'. Required. Packer template. Default: 'builtin'.
    #customTemplateLocation: # string. Required when templateType = custom. Packer template location. 
    #customTemplateParameters: '{}' # string. Optional. Use when templateType = custom. Template parameters. Default: '{}'.
  # Azure Details
    ConnectedServiceName: # string. Required. Azure subscription. 
    isManagedImage: true # boolean. Required. Managed VM disk image. Default: true.
    managedImageName: # string. Required when isManagedImage = true. Managed VM Disk Image Name. 
    location: # string. Required. Storage location. 
    storageAccountName: # string. Required. Storage account. 
    azureResourceGroup: # string. Required. Resource group. 
  # Deployment Inputs
    baseImageSource: 'default' # 'default' | 'customVhd'. Required. Base image source. Default: 'default'.
    baseImage: 'MicrosoftWindowsServer:WindowsServer:2012-R2-Datacenter:windows' # 'MicrosoftWindowsServer:WindowsServer:2012-R2-Datacenter:windows' | 'MicrosoftWindowsServer:WindowsServer:2016-Datacenter:windows' | 'MicrosoftWindowsServer:WindowsServer:2012-Datacenter:windows' | 'MicrosoftWindowsServer:WindowsServer:2008-R2-SP1:windows' | 'Canonical:UbuntuServer:14.04.4-LTS:linux' | 'Canonical:UbuntuServer:16.04-LTS:linux' | 'RedHat:RHEL:7.2:linux' | 'RedHat:RHEL:6.8:linux' | 'OpenLogic:CentOS:7.2:linux' | 'OpenLogic:CentOS:6.8:linux' | 'credativ:Debian:8:linux' | 'credativ:Debian:7:linux' | 'SUSE:openSUSE-Leap:42.2:linux' | 'SUSE:SLES:12-SP2:linux' | 'SUSE:SLES:11-SP4:linux'. Required when baseImageSource = default. Base image. Default: 'MicrosoftWindowsServer:WindowsServer:2012-R2-Datacenter:windows'.
    #customImageUrl: # string. Required when baseImageSource = customVhd. Base image URL. 
    #customImageOSType: 'windows' # 'windows' | 'linux'. Required when baseImageSource = customVhd. Base image OS. Default: 'windows'.
    packagePath: # string. Required. Deployment Package. 
    deployScriptPath: # string. Required. Deployment script. 
    #deployScriptArguments: # string. Deployment script arguments. 
  # Advanced
    #additionalBuilderParameters: '{"vm_size":"Standard_D3_v2"}' # string. Additional Builder parameters. Default: '{"vm_size":"Standard_D3_v2"}'.
    #skipTempFileCleanupDuringVMDeprovision: true # boolean. Skip temporary file cleanup during deprovision. Default: true.
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
Type: string. Required. Allowed values: 'builtin', 'custom'. Default value: 'builtin'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select whether you want the task to auto generate Packer template or use custom template provided by you.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customTemplateLocation"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`customTemplateLocation`** - **Packer template location**<br>
Type: string. Required when templateType = custom.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to a custom user-provided template.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customTemplateParameters"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`customTemplateParameters`** - **Template parameters**<br>
Type: string. Optional. Use when templateType = custom. Default value: '{}'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify parameters which will be passed to Packer for building custom template. This should map to "variables" section in your custom template. E.g. if the template has a variable named "drop-location", then add a parameter here with name "drop-location" and a value which you want to use. You can link the value to a release variable as well. To view/edit the additional parameters in a grid, click on "…" next to text box.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ConnectedServiceName"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`ConnectedServiceName`** - **Azure subscription**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the Azure Resource Manager subscription for baking and storing the machine image.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="isManagedImage"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`isManagedImage`** - **Managed VM disk image**<br>
Type: boolean. Required. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Check if generated image should be a managed image.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="managedImageName"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`managedImageName`** - **Managed VM Disk Image Name**<br>
Type: string. Required when isManagedImage = true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The Name of the Managed disk image for Auto Generated Templates.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="location"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`location`** - **Storage location**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Location for storing the built machine image. This location will also be used to create a temporary VM for the purpose of building image.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="storageAccountName"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`storageAccountName`** - **Storage account**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Storage account for storing the built machine image. This storage account must be pre-existing in the location selected.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureResourceGroup"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`azureResourceGroup`** - **Resource group**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Azure Resource group that contains the selected storage account.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="baseImageSource"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`baseImageSource`** - **Base image source**<br>
Type: string. Required. Allowed values: 'default', 'customVhd'. Default value: 'default'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the source of base image. You can either choose from a curated gallery of OS images or provide URL of your custom VHD image. <br/>Please note that if you have selected option to create a Managed image by checking 'Managed VM disk image' option, then you should only choose 'Gallery' option here. 'Custom' source is not supported to create a managed image.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="baseImage"::: -->
:::moniker range=">=azure-pipelines-2020"

**`baseImage`** - **Base image**<br>
Type: string. Required when baseImageSource = default. Allowed values: 'MicrosoftWindowsServer:WindowsServer:2012-R2-Datacenter:windows', 'MicrosoftWindowsServer:WindowsServer:2016-Datacenter:windows', 'MicrosoftWindowsServer:WindowsServer:2012-Datacenter:windows', 'MicrosoftWindowsServer:WindowsServer:2008-R2-SP1:windows', 'Canonical:UbuntuServer:14.04.4-LTS:linux', 'Canonical:UbuntuServer:16.04-LTS:linux', 'Canonical:UbuntuServer:18.04-LTS:linux', 'RedHat:RHEL:7.2:linux', 'RedHat:RHEL:6.8:linux', 'OpenLogic:CentOS:7.2:linux', 'OpenLogic:CentOS:6.8:linux', 'credativ:Debian:8:linux', 'credativ:Debian:7:linux', 'SUSE:openSUSE-Leap:42.2:linux', 'SUSE:SLES:12-SP2:linux', 'SUSE:SLES:11-SP4:linux'. Default value: 'MicrosoftWindowsServer:WindowsServer:2012-R2-Datacenter:windows'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Choose from curated list of OS images. This will be used for installing pre-requisite(s) and application(s) before capturing machine image.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

**`baseImage`** - **Base image**<br>
Type: string. Required when baseImageSource = default. Allowed values: 'MicrosoftWindowsServer:WindowsServer:2012-R2-Datacenter:windows', 'MicrosoftWindowsServer:WindowsServer:2016-Datacenter:windows', 'MicrosoftWindowsServer:WindowsServer:2012-Datacenter:windows', 'MicrosoftWindowsServer:WindowsServer:2008-R2-SP1:windows', 'Canonical:UbuntuServer:14.04.4-LTS:linux', 'Canonical:UbuntuServer:16.04-LTS:linux', 'RedHat:RHEL:7.2:linux', 'RedHat:RHEL:6.8:linux', 'OpenLogic:CentOS:7.2:linux', 'OpenLogic:CentOS:6.8:linux', 'credativ:Debian:8:linux', 'credativ:Debian:7:linux', 'SUSE:openSUSE-Leap:42.2:linux', 'SUSE:SLES:12-SP2:linux', 'SUSE:SLES:11-SP4:linux'. Default value: 'MicrosoftWindowsServer:WindowsServer:2012-R2-Datacenter:windows'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Choose from curated list of OS images. This will be used for installing pre-requisite(s) and application(s) before capturing machine image.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customImageUrl"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`customImageUrl`** - **Base image URL**<br>
Type: string. Required when baseImageSource = customVhd.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify URL of base image. This will be used for installing pre-requisite(s) and application(s) before capturing machine image.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customImageOSType"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`customImageOSType`** - **Base image OS**<br>
Type: string. Required when baseImageSource = customVhd. Allowed values: 'windows', 'linux'. Default value: 'windows'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="packagePath"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`packagePath`** - **Deployment Package**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the path for deployment package directory relative to $(System.DefaultWorkingDirectory). Supports minimatch pattern. Example path: FrontendWebApp/**/GalleryApp <br/> Please note that this package will be copied to temporary virtual machine which Packer creates. If the package contains large number of files and/or the files are very large in size, the upload can take quite long time (possibly running into few hours). To optimize the upload time, please see if size of the package can be meaningfully reduced. Another alternative is to use an intermediary Azure storage account. Upload the package to a storage account prior to running this task. And for this task, use a package containing a script which will download the required package from the storage account.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deployScriptPath"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`deployScriptPath`** - **Deployment script**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the relative path to powershell script(for Windows) or shell script(for Linux) which deploys the package. This script should be contained in the package path selected above. Supports minimatch pattern. Example path: deploy/**/scripts/windows/deploy.ps1.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deployScriptArguments"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`deployScriptArguments`** - **Deployment script arguments**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the arguments to be passed to deployment script.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="additionalBuilderParameters"::: -->
:::moniker range=">=azure-pipelines-2020"

**`additionalBuilderParameters`** - **Additional Builder parameters**<br>
Type: string. Optional. Use when templateType = builtin. Default value: '{"vm_size":"Standard_D3_v2"}'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
In auto generated Packer template mode the task creates a Packer template with an Azure builder. This builder is used to generate a machine image. You can add keys to the Azure builder to customize the generated Packer template. For example setting ssh_tty=true in case you are using a CentOS base image and you need to have a tty to run sudo.<br/>To view/edit the additional parameters in a grid, click on “…” next to text box.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

**`additionalBuilderParameters`** - **Additional Builder parameters**<br>
Type: string. Default value: '{"vm_size":"Standard_D3_v2"}'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
In auto generated Packer template mode the task creates a Packer template with an Azure builder. This builder is used to generate a machine image. You can add keys to the Azure builder to customize the generated Packer template. For example setting ssh_tty=true in case you are using a CentOS base image and you need to have a tty to run sudo.<br/>To view/edit the additional parameters in a grid, click on “…” next to text box.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="skipTempFileCleanupDuringVMDeprovision"::: -->
:::moniker range=">=azure-pipelines-2020"

**`skipTempFileCleanupDuringVMDeprovision`** - **Skip temporary file cleanup during deprovision**<br>
Type: boolean. Optional. Use when templateType = builtin. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
During deprovisioning of VM, skip clean-up of temporary files uploaded to VM. Refer [here](https://www.packer.io/docs/builders/azure.html#skip_clean).
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

**`skipTempFileCleanupDuringVMDeprovision`** - **Skip temporary file cleanup during deprovision**<br>
Type: boolean. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
During deprovisioning of VM, skip clean-up of temporary files uploaded to VM. Refer [here](https://www.packer.io/docs/builders/azure.html#skip_clean).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="packerVersion"::: -->
:::moniker range=">=azure-pipelines-2020"

**`packerVersion`** - **Packer Version**<br>
Type: string. Optional. Use when templateType = custom.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the version of Packer to install. This will work only with custom templates.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="imageUri"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`imageUri`** - **Image URL or Name**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide a name for the output variable which will store generated machine image VHD url for un-managed VM image or image name for managed VM image.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="imageId"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`imageId`** - **Azure Resource Id**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide a name for the output variable which will store the azure resource id for the newly created image.  This is for managed images only.
<!-- :::editable-content-end::: -->

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