---
title: XamarinLicense@1 - Xamarin License v1 task
description: XamarinLicense@1 is deprecated.
ms.date: 05/06/2025
monikerRange: "<=azure-pipelines"
author: steved0x
ms.author: sdanie
---

# XamarinLicense@1 - Xamarin License v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
XamarinLicense@1 is deprecated because you no longer need a Xamarin license to [build your Xamarin app](/azure/devops/pipelines/ecosystems/xamarin). You can now use the free version of [Xamarin](https://store.xamarin.com).

This task was originally used in a build or release pipeline to activate or deactivate Xamarin licenses.

> [!NOTE]
> This task is deprecated and was retired May 1, 2024.
<!-- :::editable-content-end::: -->

<!-- This task is deprecated. -->

:::moniker-end

<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="<=azure-pipelines"

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

<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="action"::: -->
:::moniker range="<=azure-pipelines"

**`action`** - **Action**<br>
`string`. Required. Allowed values: `Activate`, `Deactivate`. Default value: `Activate`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies `activate` for the first instance of this build task before any instances of the `Xamarin.Android` or `Xamarin.iOS` tasks. Specifies `deactivate` for the second instance of this build task after all instances of the `Xamarin.Android` and `Xamarin.iOS` tasks. You should also select `Always run` under `Control options` for the last instance of the Xamarin license task.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="email"::: -->
:::moniker range="<=azure-pipelines"

**`email`** - **Email**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the Xamarin account email address.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="password"::: -->
:::moniker range="<=azure-pipelines"

**`password`** - **Password**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the Xamarin account password. Use a [secret variable](/azure/devops/pipelines/build/variables) with its lock enabled on the variables tab to encrypt this value.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="product"::: -->
:::moniker range="<=azure-pipelines"

**`product`** - **Xamarin Product**<br>
`string`. Required. Allowed values: `MA` (Xamarin.Android), `MT` (Xamarin.iOS), `MM` (Xamarin.Mac). Default value: `MA`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the Xamarin product name.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="timeout"::: -->
:::moniker range="<=azure-pipelines"

**`timeout`** - **Timeout in Seconds**<br>
`string`. Default value: `30`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies how long you want to allow the build task to wait for the activation or deactivation.
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
