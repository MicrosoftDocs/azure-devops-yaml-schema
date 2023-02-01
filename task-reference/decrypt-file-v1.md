---
title: DecryptFile@1 - Decrypt file (OpenSSL) v1 task
description: Decrypt a file using OpenSSL.
ms.date: 02/01/2023
monikerRange: "<=azure-pipelines"
---

# DecryptFile@1 - Decrypt file (OpenSSL) v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Use this task to decrypt files using OpenSSL.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
A thin utility task for file decryption using OpenSSL.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# Decrypt file (OpenSSL) v1
# Decrypt a file using OpenSSL.
- task: DecryptFile@1
  inputs:
    cipher: 'des3' # string. Required. Cypher. Default: des3.
    inFile: # string. Required. Encrypted file. 
    passphrase: # string. Required. Passphrase. 
    #outFile: # string. Decrypted file path. 
  # Advanced
    #workingDirectory: # string. Alias: cwd. Working directory.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Decrypt File (OpenSSL) v1
# A thin utility task for file decryption using OpenSSL.
- task: DecryptFile@1
  inputs:
    cipher: 'des3' # string. Required. Cypher. Default: des3.
    inFile: # string. Required. Encrypted file. 
    passphrase: # string. Required. Passphrase. 
    #outFile: # string. Decrypted file path. 
  # Advanced
    #workingDirectory: # string. Alias: cwd. Working directory.
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

<!-- :::item name="cipher"::: -->
:::moniker range="<=azure-pipelines"

**`cipher`** - **Cypher**<br>
`string`. Required. Default value: `des3`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The encryption cypher to use. See [cypher suite names](https://go.microsoft.com/fwlink/?LinkID=627129) for a complete list of possible values.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="inFile"::: -->
:::moniker range="<=azure-pipelines"

**`inFile`** - **Encrypted file**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The relative path of the file to decrypt.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="passphrase"::: -->
:::moniker range="<=azure-pipelines"

**`passphrase`** - **Passphrase**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The passphrase to use for decryption. **Use a variable to encrypt the passphrase.**
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="outFile"::: -->
:::moniker range="<=azure-pipelines"

**`outFile`** - **Decrypted file path**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The optional filename for the decrypted file. Defaults to the encrypted file with an `.out` extension.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="workingDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`workingDirectory`** - **Working directory**<br>
Input alias: `cwd`. `string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The optional working directory for decryption. Defaults to the root of the repository.
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

Use this task to decrypt files using OpenSSL.
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
