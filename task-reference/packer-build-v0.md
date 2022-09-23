---
title: PackerBuild@0 - Build machine image v0 task
description: Build a machine image using Packer, which may be used for Azure Virtual machine scale set deployment (task version 0).
ms.date: 09/01/2022
monikerRange: "<=azure-pipelines"
---

# PackerBuild@0 - Build machine image v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Build a machine image using Packer, which may be used for Azure Virtual machine scale set deployment.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Build machine image using Packer. This image can be used for Azure Virtual machine scale set deployment.
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
    templateType: 'builtin' # 'builtin' | 'custom'. Required. Packer template. Default: 'builtin'.
    #customTemplateLocation: # string. Required when templateType = custom. Packer template location. 
    #customTemplateParameters: '{}' # string. Optional. Use when templateType = custom. Template parameters. Default: '{}'.
  # Azure Details
    ConnectedServiceName: # string. Required. Azure subscription. 
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
    #additionalBuilderParameters: '{}' # string. Additional Builder parameters. Default: '{}'.
    #skipTempFileCleanupDuringVMDeprovision: true # boolean. Skip temporary file cleanup during deprovision. Default: true.
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
    templateType: 'builtin' # 'builtin' | 'custom'. Required. Packer template. Default: 'builtin'.
    #customTemplateLocation: # string. Required when templateType = custom. Packer template location. 
    #customTemplateParameters: '{}' # string. Optional. Use when templateType = custom. Template parameters. Default: '{}'.
  # Azure Details
    ConnectedServiceName: # string. Required. Azure subscription. 
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
    #additionalBuilderParameters: '{}' # string. Additional Builder parameters. Default: '{}'.
    #skipTempFileCleanupDuringVMDeprovision: true # boolean. Skip temporary file cleanup during deprovision. Default: true.
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
Type: string. Required. Allowed values: 'builtin', 'custom'. Default value: 'builtin'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select whether you want the task to auto generate Packer template or use custom template provided by you.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customTemplateLocation"::: -->
:::moniker range="<=azure-pipelines"

**`customTemplateLocation`** - **Packer template location**<br>
Type: string. Required when templateType = custom.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to a custom user-provided template.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customTemplateParameters"::: -->
:::moniker range="<=azure-pipelines"

**`customTemplateParameters`** - **Template parameters**<br>
Type: string. Optional. Use when templateType = custom. Default value: '{}'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify parameters which will be passed to Packer for building custom template. This should map to "variables" section in your custom template. E.g. if the template has a variable named "drop-location", then add a parameter here with name "drop-location" and a value which you want to use. You can link the value to a release variable as well. To view/edit the additional parameters in a grid, click on "…" next to text box.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ConnectedServiceName"::: -->
:::moniker range="<=azure-pipelines"

**`ConnectedServiceName`** - **Azure subscription**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the Azure Resource Manager subscription for baking and storing the machine image.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="location"::: -->
:::moniker range="<=azure-pipelines"

**`location`** - **Storage location**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Location for storing the built machine image. This location will also be used to create a temporary VM for the purpose of building image.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="storageAccountName"::: -->
:::moniker range="<=azure-pipelines"

**`storageAccountName`** - **Storage account**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Storage account for storing the built machine image. This storage account must be pre-existing in the location selected.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureResourceGroup"::: -->
:::moniker range="<=azure-pipelines"

**`azureResourceGroup`** - **Resource group**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Azure Resource group that contains the selected storage account.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="baseImageSource"::: -->
:::moniker range="<=azure-pipelines"

**`baseImageSource`** - **Base image source**<br>
Type: string. Required. Allowed values: 'default', 'customVhd'. Default value: 'default'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the source of base image. You can either choose from a curated gallery of OS images or provide URL of your custom image.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="baseImage"::: -->
:::moniker range="<=azure-pipelines"

**`baseImage`** - **Base image**<br>
Type: string. Required when baseImageSource = default. Allowed values: 'MicrosoftWindowsServer:WindowsServer:2012-R2-Datacenter:windows', 'MicrosoftWindowsServer:WindowsServer:2016-Datacenter:windows', 'MicrosoftWindowsServer:WindowsServer:2012-Datacenter:windows', 'MicrosoftWindowsServer:WindowsServer:2008-R2-SP1:windows', 'Canonical:UbuntuServer:14.04.4-LTS:linux', 'Canonical:UbuntuServer:16.04-LTS:linux', 'RedHat:RHEL:7.2:linux', 'RedHat:RHEL:6.8:linux', 'OpenLogic:CentOS:7.2:linux', 'OpenLogic:CentOS:6.8:linux', 'credativ:Debian:8:linux', 'credativ:Debian:7:linux', 'SUSE:openSUSE-Leap:42.2:linux', 'SUSE:SLES:12-SP2:linux', 'SUSE:SLES:11-SP4:linux'. Default value: 'MicrosoftWindowsServer:WindowsServer:2012-R2-Datacenter:windows'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Choose from curated list of OS images. This will be used for installing pre-requisite(s) and application(s) before capturing machine image.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customImageUrl"::: -->
:::moniker range="<=azure-pipelines"

**`customImageUrl`** - **Base image URL**<br>
Type: string. Required when baseImageSource = customVhd.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify URL of base image. This will be used for installing pre-requisite(s) and application(s) before capturing machine image.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customImageOSType"::: -->
:::moniker range="<=azure-pipelines"

**`customImageOSType`** - **Base image OS**<br>
Type: string. Required when baseImageSource = customVhd. Allowed values: 'windows', 'linux'. Default value: 'windows'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="packagePath"::: -->
:::moniker range="<=azure-pipelines"

**`packagePath`** - **Deployment Package**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the path for deployment package directory relative to $(System.DefaultWorkingDirectory). Supports minimatch pattern. Example path: FrontendWebApp/**/GalleryApp.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deployScriptPath"::: -->
:::moniker range="<=azure-pipelines"

**`deployScriptPath`** - **Deployment script**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the relative path to powershell script(for Windows) or shell script(for Linux) which deploys the package. This script should be contained in the package path selected above. Supports minimatch pattern. Example path: deploy/**/scripts/windows/deploy.ps1.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deployScriptArguments"::: -->
:::moniker range="<=azure-pipelines"

**`deployScriptArguments`** - **Deployment script arguments**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the arguments to be passed to deployment script.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="additionalBuilderParameters"::: -->
:::moniker range="<=azure-pipelines"

**`additionalBuilderParameters`** - **Additional Builder parameters**<br>
Type: string. Default value: '{}'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
In auto generated Packer template mode the task creates a Packer template with an Azure builder. This builder is used to generate a machine image. You can add keys to the Azure builder to customize the generated Packer template. For example setting ssh_tty=true in case you are using a CentOS base image and you need to have a tty to run sudo.<br/>To view/edit the additional parameters in a grid, click on “…” next to text box.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="skipTempFileCleanupDuringVMDeprovision"::: -->
:::moniker range="<=azure-pipelines"

**`skipTempFileCleanupDuringVMDeprovision`** - **Skip temporary file cleanup during deprovision**<br>
Type: boolean. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
During deprovisioning of VM, skip clean-up of temporary files uploaded to VM. Refer [here](https://www.packer.io/docs/builders/azure.html#skip_clean).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="imageUri"::: -->
:::moniker range="<=azure-pipelines"

**`imageUri`** - **Image URL**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide a name for the output variable which will store generated machine image URL.
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