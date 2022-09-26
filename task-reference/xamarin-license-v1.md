---
title: XamarinLicense@1 - Xamarin License v1 task
description: XamarinLicense@1 is deprecated.
ms.date: 09/26/2022
monikerRange: "<=azure-pipelines"
---

# XamarinLicense@1 - Xamarin License v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
XamarinLicense@1 is deprecated. Upgrade to free version of Xamarin: https://store.xamarin.com.
<!-- :::editable-content-end::: -->

This task is deprecated.

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019"

```yaml
# Xamarin License v1
# [Deprecated] Upgrade to free version of Xamarin: https://store.xamarin.com.
- task: XamarinLicense@1
  inputs:
    action: 'Activate' # 'Activate' | 'Deactivate'. Required. Action. Default: Activate.
    email: # string. Required. Email. 
    password: # string. Required. Password. 
    product: 'MA' # 'MA' | 'MT' | 'MM'. Required. Xamarin Product. Default: MA.
  # Advanced
    #timeout: '30' # string. Timeout in Seconds. Default: 30.
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

<!-- :::item name="action"::: -->
:::moniker range="<=azure-pipelines"

**`action`** - **Action**<br>
`string`. Required. Allowed values: `Activate`, `Deactivate`. Default value: `Activate`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="email"::: -->
:::moniker range="<=azure-pipelines"

**`email`** - **Email**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Xamarin account email address.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="password"::: -->
:::moniker range="<=azure-pipelines"

**`password`** - **Password**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Xamarin account password. Use a new build variable with its lock enabled on the Variables tab to encrypt this value.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="product"::: -->
:::moniker range="<=azure-pipelines"

**`product`** - **Xamarin Product**<br>
`string`. Required. Allowed values: `MA` (Xamarin.Android), `MT` (Xamarin.iOS), `MM` (Xamarin.Mac). Default value: `MA`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Xamarin product name.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="timeout"::: -->
:::moniker range="<=azure-pipelines"

**`timeout`** - **Timeout in Seconds**<br>
`string`. Default value: `30`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
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

This task is deprecated because you no longer need a Xamarin license to [build your Xamarin app](/azure/devops/pipelines/ecosystems/xamarin). Use the free version of Xamarin from [https://store.xamarin.com](https://store.xamarin.com).
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
| Pipeline types | YAML, Classic build |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.83.0 or greater |
| Task category | Utility |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

* [build your Xamarin app](/azure/devops/pipelines/ecosystems/xamarin)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->