---
title: BicepDeploy@0 - Bicep Deploy v0 task
description: Deploy and Manage Azure Resources using Bicep Files. (task version 0)
ms.date: 04/27/2026
monikerRange: "=azure-pipelines"
---

# BicepDeploy@0 - Bicep Deploy v0 task

<!-- :::description::: -->
:::moniker range=">azure-pipelines-server"

<!-- :::editable-content name="description"::: -->
The Bicep Deploy task is used to deploy and manage Azure resources using [Bicep](/azure/azure-resource-manager/bicep/overview) files. Bicep is a domain-specific language (DSL) that uses declarative syntax to deploy Azure resources. This task supports both standard Azure deployments and [Azure Deployment Stacks](/azure/azure-resource-manager/bicep/deployment-stacks), providing a simplified and more maintainable way to manage your Azure infrastructure as code.

The task handles:

- Creating or updating Azure resources using Bicep templates
- Validating Bicep templates before deployment
- Previewing changes with What-If operations
- Managing deployment stacks with lifecycle policies
- Deleting deployments and deployment stacks
- Installing and managing Bicep CLI versions automatically

The task supports:

- **Native Bicep Support**: Direct deployment from `.bicep` and `.bicepparam` files without requiring pre-compilation to ARM templates
- **Deployment Stacks**: Full support for Azure Deployment Stacks with deny settings, unmanaged resource policies, and lifecycle management
- **Automatic Bicep CLI Management**: Automatically downloads and caches the specified version of Bicep CLI
- **Cross-Platform**: Works with Windows, Linux, and macOS agents
- **Multiple Deployment Scopes**: Supports Resource Group, Subscription, Management Group, and Tenant scopes
- **What-If Operations**: Preview changes before applying them to your Azure environment
- **Flexible Parameter Input**: Support for inline YAML/JSON parameters and traditional parameter files
- **Output Masking**: Automatically mask sensitive outputs like secrets and connection strings
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="=azure-pipelines"

```yaml
# Bicep Deploy v0
# Deploy and Manage Azure Resources using Bicep Files.
- task: BicepDeploy@0
  inputs:
  # Azure Details
    type: 'deployment' # 'deployment' | 'deploymentStack'. Required. Execution type. Default: deployment.
    #operation: 'create' # 'create' | 'validate' | 'whatIf' | 'delete'. Required when type = deployment || (type = deploymentStack && operation != whatIf). Operation. Default: create.
    scope: 'resourceGroup' # 'resourceGroup' | 'subscription' | 'managementGroup' | 'tenant'. Required. Deployment scope. Default: resourceGroup.
    #name: # string. Deployment name. 
    azureResourceManagerConnection: # string. Alias: ConnectedServiceName. Required. Azure Resource Manager connection. 
    #subscriptionId: # string. Required when scope != tenant && scope != managementGroup. Subscription. 
    resourceGroupName: # string. Required when scope = resourceGroup. Resource group. 
    #location: # string. Optional. Use when scope != resourceGroup. Location. 
    #tenantId: # string. Required when scope = tenant. Tenant ID. 
    #managementGroupId: # string. Required when scope = managementGroup. Management group ID. 
  # Template
    #templateFile: # string. Template file. 
    #parametersFile: # string. Parameters file. 
    #parameters: # string. Override parameters. 
  # Deployment Stack Options
    #actionOnUnmanageResources: 'detach' # 'delete' | 'detach'. Required when type = deploymentStack. Action on unmanaged resources. Default: detach.
    #actionOnUnmanageResourceGroups: # 'delete' | 'detach'. Optional. Use when type = deploymentStack. Action on unmanaged resource groups. 
    #actionOnUnmanageManagementGroups: # 'delete' | 'detach'. Optional. Use when type = deploymentStack. Action on unmanaged management groups. 
    #denySettingsMode: 'none' # 'none' | 'denyDelete' | 'denyWriteAndDelete'. Required when type = deploymentStack. Deny settings mode. Default: none.
    #denySettingsExcludedActions: # string. Optional. Use when type = deploymentStack && denySettingsMode != none. Deny settings excluded actions. 
    #denySettingsExcludedPrincipals: # string. Optional. Use when type = deploymentStack && denySettingsMode != none. Deny settings excluded principals. 
    #denySettingsApplyToChildScopes: false # boolean. Optional. Use when type = deploymentStack && denySettingsMode != none. Apply deny settings to child scopes. Default: false.
    #bypassStackOutOfSyncError: false # boolean. Optional. Use when type = deploymentStack. Bypass stack out of sync error. Default: false.
  # Advanced
    #description: # string. Description. 
    #tags: # string. Optional. Use when type = deploymentStack. Tags. 
    #bicepVersion: # string. Bicep version. 
    #maskedOutputs: # string. Masked outputs. 
    #environment: 'azureCloud' # 'azureCloud' | 'azureChinaCloud' | 'azureGermanCloud' | 'azureUSGovernment'. Azure environment. Default: azureCloud.
    #whatIfExcludeChangeTypes: # string. Optional. Use when operation = whatIf. What-If exclude change types. 
    #validationLevel: # 'provider' | 'template' | 'providerNoRbac'. Optional. Use when type = deployment && (operation = validate || operation = whatIf). Validation level.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="type"::: -->
:::moniker range=">azure-pipelines-server"

**`type`** - **Execution type**<br>
`string`. Required. Allowed values: `deployment`, `deploymentStack` (Deployment Stack). Default value: `deployment`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the execution type: deployment or deploymentStack.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="operation"::: -->
:::moniker range=">azure-pipelines-server"

**`operation`** - **Operation**<br>
`string`. Required when `type = deployment || (type = deploymentStack && operation != whatIf)`. Allowed values: `create` (Create or update), `validate`, `whatIf` (What-If (preview changes)), `delete`. Default value: `create`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the operation to perform. Deployment supports: create, validate, whatIf. Deployment Stack supports: create, validate, delete.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="scope"::: -->
:::moniker range=">azure-pipelines-server"

**`scope`** - **Deployment scope**<br>
`string`. Required. Allowed values: `resourceGroup` (Resource Group), `subscription`, `managementGroup` (Management Group), `tenant`. Default value: `resourceGroup`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the scope at which resources are deployed.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="name"::: -->
:::moniker range=">azure-pipelines-server"

**`name`** - **Deployment name**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of the deployment or deployment stack. If not provided, a default name will be generated.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureResourceManagerConnection"::: -->
:::moniker range=">azure-pipelines-server"

**`azureResourceManagerConnection`** - **Azure Resource Manager connection**<br>
[Input alias](index.md#what-are-task-input-aliases): `ConnectedServiceName`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the Azure Resource Manager service connection.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="subscriptionId"::: -->
:::moniker range=">azure-pipelines-server"

**`subscriptionId`** - **Subscription**<br>
`string`. Required when `scope != tenant && scope != managementGroup`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the Azure subscription. Required if scope is subscription or resourceGroup.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resourceGroupName"::: -->
:::moniker range=">azure-pipelines-server"

**`resourceGroupName`** - **Resource group**<br>
`string`. Required when `scope = resourceGroup`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide the name of the resource group.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="location"::: -->
:::moniker range=">azure-pipelines-server"

**`location`** - **Location**<br>
`string`. Optional. Use when `scope != resourceGroup`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Location to store deployment metadata. Required for subscription, managementGroup, and tenant scopes.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="tenantId"::: -->
:::moniker range=">azure-pipelines-server"

**`tenantId`** - **Tenant ID**<br>
`string`. Required when `scope = tenant`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the tenant ID. Required if scope is tenant.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="managementGroupId"::: -->
:::moniker range=">azure-pipelines-server"

**`managementGroupId`** - **Management group ID**<br>
`string`. Required when `scope = managementGroup`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the management group ID. Required if scope is managementGroup.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="templateFile"::: -->
:::moniker range=">azure-pipelines-server"

**`templateFile`** - **Template file**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the path to the Bicep template file (.bicep).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="parametersFile"::: -->
:::moniker range=">azure-pipelines-server"

**`parametersFile`** - **Parameters file**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the path to the parameters file (.json or .bicepparam).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="parameters"::: -->
:::moniker range=">azure-pipelines-server"

**`parameters`** - **Override parameters**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify inline parameters as a JSON or YAML object. Example: {"param1": "value1", "param2": "value2"}.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="actionOnUnmanageResources"::: -->
:::moniker range=">azure-pipelines-server"

**`actionOnUnmanageResources`** - **Action on unmanaged resources**<br>
`string`. Required when `type = deploymentStack`. Allowed values: `delete`, `detach`. Default value: `detach`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the action to take on resources not defined in the template.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="actionOnUnmanageResourceGroups"::: -->
:::moniker range=">azure-pipelines-server"

**`actionOnUnmanageResourceGroups`** - **Action on unmanaged resource groups**<br>
`string`. Optional. Use when `type = deploymentStack`. Allowed values: `delete`, `detach`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the action to take on resource groups not defined in the template.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="actionOnUnmanageManagementGroups"::: -->
:::moniker range=">azure-pipelines-server"

**`actionOnUnmanageManagementGroups`** - **Action on unmanaged management groups**<br>
`string`. Optional. Use when `type = deploymentStack`. Allowed values: `delete`, `detach`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the action to take on management groups not defined in the template.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="denySettingsMode"::: -->
:::moniker range=">azure-pipelines-server"

**`denySettingsMode`** - **Deny settings mode**<br>
`string`. Required when `type = deploymentStack`. Allowed values: `none`, `denyDelete` (Deny Delete), `denyWriteAndDelete` (Deny Write and Delete). Default value: `none`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the mode of the deny settings to prevent unauthorized changes.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="denySettingsExcludedActions"::: -->
:::moniker range=">azure-pipelines-server"

**`denySettingsExcludedActions`** - **Deny settings excluded actions**<br>
`string`. Optional. Use when `type = deploymentStack && denySettingsMode != none`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Comma-separated list of actions to exclude from deny settings.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="denySettingsExcludedPrincipals"::: -->
:::moniker range=">azure-pipelines-server"

**`denySettingsExcludedPrincipals`** - **Deny settings excluded principals**<br>
`string`. Optional. Use when `type = deploymentStack && denySettingsMode != none`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Comma-separated list of principal IDs to exclude from deny settings.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="denySettingsApplyToChildScopes"::: -->
:::moniker range=">azure-pipelines-server"

**`denySettingsApplyToChildScopes`** - **Apply deny settings to child scopes**<br>
`boolean`. Optional. Use when `type = deploymentStack && denySettingsMode != none`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
When enabled, deny settings also apply to child scopes of managed resources.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="bypassStackOutOfSyncError"::: -->
:::moniker range=">azure-pipelines-server"

**`bypassStackOutOfSyncError`** - **Bypass stack out of sync error**<br>
`boolean`. Optional. Use when `type = deploymentStack`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Bypass errors when the deployment stack is out of sync.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="description"::: -->
:::moniker range=">azure-pipelines-server"

**`description`** - **Description**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Description for the deployment or deployment stack.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="tags"::: -->
:::moniker range=">azure-pipelines-server"

**`tags`** - **Tags**<br>
`string`. Optional. Use when `type = deploymentStack`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Tags as JSON or YAML object. Example: {"Environment": "Development", "Owner": "TeamName"}.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="bicepVersion"::: -->
:::moniker range=">azure-pipelines-server"

**`bicepVersion`** - **Bicep version**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the version of Bicep to use (e.g., '0.38.5'). If not provided, the latest version will be used.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="maskedOutputs"::: -->
:::moniker range=">azure-pipelines-server"

**`maskedOutputs`** - **Masked outputs**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Comma-separated list of output names to mask values for (e.g., secrets).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="environment"::: -->
:::moniker range=">azure-pipelines-server"

**`environment`** - **Azure environment**<br>
`string`. Allowed values: `azureCloud` (Azure Cloud), `azureChinaCloud` (Azure China Cloud), `azureGermanCloud` (Azure German Cloud), `azureUSGovernment` (Azure US Government). Default value: `azureCloud`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the Azure environment to use.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="whatIfExcludeChangeTypes"::: -->
:::moniker range=">azure-pipelines-server"

**`whatIfExcludeChangeTypes`** - **What-If exclude change types**<br>
`string`. Optional. Use when `operation = whatIf`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Comma-separated list of change types to exclude from What-If operation (e.g., noChange, ignore).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="validationLevel"::: -->
:::moniker range=">azure-pipelines-server"

**`validationLevel`** - **Validation level**<br>
`string`. Optional. Use when `type = deployment && (operation = validate || operation = whatIf)`. Allowed values: `provider`, `template`, `providerNoRbac` (Provider (No RBAC)).<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Validation level for deployment operations.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">azure-pipelines-server"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

### Prerequisites

#### Azure Subscription

To deploy to Azure, an Azure subscription must be linked to Azure Pipelines using a service connection:

1. Navigate to **Project Settings** → **Service connections**
2. Create a new service connection of type **Azure Resource Manager**
3. Choose authentication method:
   - **Service Principal (automatic)** - Recommended for most scenarios
   - **Service Principal (manual)** - For advanced configurations
   - **Managed Identity** - For Azure-hosted agents with managed identities
   - **Workload Identity Federation** - For enhanced security without secrets

For troubleshooting service connections, refer to the [Azure RM endpoint documentation](/azure/devops/pipelines/library/connect-to-azure).

#### Agent Requirements

- **Minimum Agent Version**: 2.144.0
- **Supported OS**: Windows, Linux, macOS
- **Node.js**: Node.js 20 or higher (included in modern hosted agents)
- **Bicep CLI**: Automatically installed by the task (no manual installation required)

### Deployment Outputs

The task automatically creates pipeline variables for all outputs defined in your Bicep template. These variables can be used in subsequent tasks.

- [Defining Outputs in Bicep](#defining-outputs-in-bicep)
- [How Outputs Become Available](#how-outputs-become-available)
- [Accessing Outputs in PowerShell](#accessing-outputs-in-powershell)
- [Accessing Outputs in Bash](#accessing-outputs-in-bash)

#### Defining Outputs in Bicep

Outputs are defined in the Bicep template using the `output` keyword. For example:

```bicep
output storageAccountName string = storageAccount.name
output webAppUrl string = webApp.properties.defaultHostName
output intOutput int = 42
output objectOutput object = {
  key1: 'value1'
  key2: 'value2'
}
```

For detailed guidance, refer to the [Bicep Outputs documentation](/azure/azure-resource-manager/bicep/outputs).

#### How Outputs Become Available

After the deployment completes successfully, all outputs are automatically converted to Azure Pipelines variables with the same names as defined in your Bicep template. These variables are created at the pipeline level and can be directly referenced in subsequent tasks using the standard variable syntax: `$(outputName)`.

#### Accessing Outputs in PowerShell

```yaml
- task: BicepDeploy@0
  displayName: 'Deploy Infrastructure'
  inputs:
    azureResourceManagerConnection: 'Azure-Connection'
    subscriptionId: '$(subscriptionId)'
    resourceGroupName: 'my-resource-group'
    templateFile: 'infra/main.bicep'

- task: PowerShell@2
  displayName: 'Use Deployment Outputs'
  inputs:
    targetType: 'inline'
    script: |
      Write-Host "Storage Account Name: $(storageAccountName)"
      Write-Host "Web App URL: $(webAppUrl)"
```

#### Accessing Outputs in Bash

```yaml
- task: BicepDeploy@0
  displayName: 'Deploy Infrastructure'
  inputs:
    azureResourceManagerConnection: 'Azure-Connection'
    subscriptionId: '$(subscriptionId)'
    resourceGroupName: 'my-resource-group'
    templateFile: 'infra/main.bicep'

- task: Bash@3
  displayName: 'Use Deployment Outputs'
  inputs:
    targetType: 'inline'
    script: |
      echo "Storage Account Name: $(storageAccountName)"
      echo "Web App URL: $(webAppUrl)"
```
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

### Example 1: Basic Deployment

```yaml
- task: BicepDeploy@0
  displayName: 'Deploy Bicep Template'
  inputs:
    azureResourceManagerConnection: 'Azure-Connection'
    subscriptionId: '$(subscriptionId)'
    resourceGroupName: 'my-resource-group'
    templateFile: 'infra/main.bicep'
    parametersFile: 'infra/main.bicepparam'
```

### Example 2: Deployment Stack

```yaml
- task: BicepDeploy@0
  displayName: 'Deploy with Stack Protection'
  inputs:
    type: 'deploymentStack'
    operation: 'create'
    name: 'production-stack'
    azureResourceManagerConnection: 'Azure-Connection'
    subscriptionId: '$(subscriptionId)'
    resourceGroupName: 'production-rg'
    templateFile: 'infra/main.bicep'
    parametersFile: 'infra/production.bicepparam'
    actionOnUnmanageResources: 'delete'
    denySettingsMode: 'denyWriteAndDelete'
```

### Example 3: Subscription-Level Deployment

```yaml
- task: BicepDeploy@0
  displayName: 'Deploy Subscription Resources'
  inputs:
    scope: 'subscription'
    azureResourceManagerConnection: 'Azure-Connection'
    subscriptionId: '$(subscriptionId)'
    location: 'eastus'
    templateFile: 'infra/subscription.bicep'
    parametersFile: 'infra/subscription.bicepparam'
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range="=azure-pipelines"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.144.0 or greater |
| Task category | Deploy |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->