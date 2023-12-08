---
title: Notation@0 - Notation v0 task
description: Azure Pipepine Task for setting up Notation CLI, sign and verify with Notation.
ms.date: 12/08/2023
monikerRange: "=azure-pipelines"
---

# Notation@0 - Notation v0 task

<!-- :::description::: -->
:::moniker range="=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Azure Pipepine Task for setting up Notation CLI, sign and verify with Notation.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="=azure-pipelines"

```yaml
# Notation v0
# Azure Pipepine Task for setting up Notation CLI, sign and verify with Notation.
- task: Notation@0
  inputs:
    command: 'install' # 'install' | 'sign' | 'verify'. Required. Command to run. Default: install.
  # Command Configuration
    #isCustomVersion: false # boolean. Optional. Use when command = install. Custom Version. Default: false.
    #version: '1.0.1' # string. Required when command = install && isCustomVersion = false. Version. Default: 1.0.1.
    #url: # string. Required when command = install && isCustomVersion = true. Download URL. 
    #checksum: # string. Required when command = install && isCustomVersion = true. Checksum. 
    #artifactRefs: # string. Optional. Use when command = verify || command = sign. Artifact references. 
    #trustPolicy: # string. Required when command = verify. Trust Policy File Path. 
    #trustStore: # string. Required when command = verify. Trust Store Folder Path. 
  # Advanced Configuration
    #signatureFormat: 'cose' # 'cose' | 'jws'. Optional. Use when command = sign && command = sign || command = verify. Signature Format. Default: cose.
    #allowReferrersAPI: false # boolean. Optional. Use when command = sign || command = verify. [Experimental] Allow Referrers API. Default: false.
  # Plugin Configuration
    #plugin: 'azureKeyVault' # 'azureKeyVault'. Required when command = sign. Plugin. Default: azureKeyVault.
    #akvPluginVersion: '1.0.1' # string. Required when plugin = azureKeyVault && command = sign. Plugin Version. Default: 1.0.1.
    #azurekvServiceConection: # string. Optional. Use when plugin = azureKeyVault && command = sign. Azure Key Vault service connection. 
    #keyid: # string. Required when plugin = azureKeyVault && command = sign. Key ID. 
    #caCertBundle: # string. Optional. Use when plugin = azureKeyVault && command = sign. Certificate Bundle File Path. 
    #selfSigned: false # boolean. Optional. Use when plugin = azureKeyVault && command = sign. Self-signed Certificate. Default: false.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="command"::: -->
:::moniker range="=azure-pipelines"

**`command`** - **Command to run**<br>
`string`. Required. Allowed values: `install`, `sign`, `verify`. Default value: `install`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
example: install.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="isCustomVersion"::: -->
:::moniker range="=azure-pipelines"

**`isCustomVersion`** - **Custom Version**<br>
`boolean`. Optional. Use when `command = install`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If checked, you can provide a custom version for the task.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="version"::: -->
:::moniker range="=azure-pipelines"

**`version`** - **Version**<br>
`string`. Required when `command = install && isCustomVersion = false`. Default value: `1.0.1`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The version of Notation to install. Example: 1.0.0, 1, 1.0, 1.0.0.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="url"::: -->
:::moniker range="=azure-pipelines"

**`url`** - **Download URL**<br>
`string`. Required when `command = install && isCustomVersion = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
example: https://github.com/notaryproject/notation/releases/download/v1.0.0/notation_1.0.0_linux_amd64.tar.gz.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="checksum"::: -->
:::moniker range="=azure-pipelines"

**`checksum`** - **Checksum**<br>
`string`. Required when `command = install && isCustomVersion = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The SHA-256 checksum of the downloaded file.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="artifactRefs"::: -->
:::moniker range="=azure-pipelines"

**`artifactRefs`** - **Artifact references**<br>
`string`. Optional. Use when `command = verify || command = sign`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Container artifact references for signing. If it was not specified, use the artifact reference from previous Docker push task. Example: <registry name>/<repository name>@<digest> If multiple, separate by comma.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="signatureFormat"::: -->
:::moniker range="=azure-pipelines"

**`signatureFormat`** - **Signature Format**<br>
`string`. Optional. Use when `command = sign && command = sign || command = verify`. Allowed values: `cose`, `jws`. Default value: `cose`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Signature envelope format, options: "jws", "cose" (default "jws").
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="allowReferrersAPI"::: -->
:::moniker range="=azure-pipelines"

**`allowReferrersAPI`** - **[Experimental] Allow Referrers API**<br>
`boolean`. Optional. Use when `command = sign || command = verify`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Use the Referrers API to sign signatures, if not supported (returns 404), fallback to the Referrers tag schema.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="plugin"::: -->
:::moniker range="=azure-pipelines"

**`plugin`** - **Plugin**<br>
`string`. Required when `command = sign`. Allowed values: `azureKeyVault` (Azure Key Vault Plugin). Default value: `azureKeyVault`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="akvPluginVersion"::: -->
:::moniker range="=azure-pipelines"

**`akvPluginVersion`** - **Plugin Version**<br>
`string`. Required when `plugin = azureKeyVault && command = sign`. Default value: `1.0.1`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The version of the Azure Key Vault plugin to be installed. please visit the [release page](https://github.com/Azure/notation-azure-kv/releases) for the available versions.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azurekvServiceConection"::: -->
:::moniker range="=azure-pipelines"

**`azurekvServiceConection`** - **Azure Key Vault service connection**<br>
`string`. Optional. Use when `plugin = azureKeyVault && command = sign`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the Azure subscription for the key vault if prefer to use service connection for authentication.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="keyid"::: -->
:::moniker range="=azure-pipelines"

**`keyid`** - **Key ID**<br>
`string`. Required when `plugin = azureKeyVault && command = sign`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The Key ID is the key or certificate identifier for Azure Key Vault.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="caCertBundle"::: -->
:::moniker range="=azure-pipelines"

**`caCertBundle`** - **Certificate Bundle File Path**<br>
`string`. Optional. Use when `plugin = azureKeyVault && command = sign`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
A file with root and all intermediate certificates, starting from the root certificate, following the order in the certificate chain.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="selfSigned"::: -->
:::moniker range="=azure-pipelines"

**`selfSigned`** - **Self-signed Certificate**<br>
`boolean`. Optional. Use when `plugin = azureKeyVault && command = sign`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="trustPolicy"::: -->
:::moniker range="=azure-pipelines"

**`trustPolicy`** - **Trust Policy File Path**<br>
`string`. Required when `command = verify`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The path to the [trust policy](https://github.com/notaryproject/specifications/blob/v1.0.0/specs/trust-store-trust-policy.md#trust-policy) file relative to the repository. Example: ./path/to/trust-policy.json.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="trustStore"::: -->
:::moniker range="=azure-pipelines"

**`trustStore`** - **Trust Store Folder Path**<br>
`string`. Required when `command = verify`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The path to the directory containing the [trust store](https://github.com/notaryproject/specifications/blob/v1.0.0/specs/trust-store-trust-policy.md#trust-store) relative to the repository. Example: ./path/to/truststore/.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range="=azure-pipelines"

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
| Task category | Utility |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->