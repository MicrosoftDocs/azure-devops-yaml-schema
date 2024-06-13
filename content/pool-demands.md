---
title: pool.demands definition
description: Demands (for a private pool).
ms.date: 06/11/2024
monikerRange: ">=azure-pipelines-2019"
---

# pool.demands definition

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Demands (for a private pool).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::parents::: -->
:::moniker range=">=azure-pipelines-2019"

Definitions that reference this definition: [pool](pool.md)

:::moniker-end
<!-- :::parents-end::: -->

## Implementations

<!-- :::implementations-list::: -->
:::moniker range=">=azure-pipelines-2019"

| Implementation | Description |
|---|---|
| [demands: string](#demandsstring) | Specify a demand for a private pool. |
| [demands: string list](#demandsstringlist) | Specify a list of demands for a private pool. |

:::moniker-end
<!-- :::implementations-list-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
### Remarks

Use demands to make sure that the [capabilities](/azure/devops/pipelines/agents/agents#capabilities) your pipeline needs are present on the agents that run it. Demands are asserted automatically by tasks or manually by you.

> [!NOTE]
>
> Demands and capabilities are designed for use with self-hosted agents so that jobs can be matched with an agent that 
> meets the requirements of the job. When using Microsoft-hosted agents, you select an image for the agent that 
> matches the requirements of the job, so although it is possible to add capabilities to a Microsoft-hosted agent, you don't need 
> to use capabilities with Microsoft-hosted agents.

You can check for the presence of a capability ([Exists operation](#exists-operation)) or you can check for a specific string in a capability ([Equals operation](#equals-operation)). Checking for the existence of a capability (exists) and checking for a specific string in a capability (equals) are the only two supported operations for demands.

### Task demands

Some tasks won't run unless one or more demands are met by the agent. For example, the [Visual Studio Build](/azure/devops/pipelines/tasks/reference/vsbuild-v1) task demands that `msbuild` and `visualstudio` are installed on the agent.

### Manually entered agent demands

You might need to use self-hosted agents with special capabilities. For example, your pipeline may require **SpecialSoftware** on agents in the `Default` pool. Or, if you have multiple agents with different operating systems in the same pool, you may have a pipeline that requires a Linux agent.

### Exists operation

The exists operation checks for the presence of a capability with the specific name. The comparison is not case sensitive.

```yaml
pool:
  name: MyPool
  demands: myCustomCapability # exists check for myCustomCapability
 ```

### Equals operation

The equals operation checks for the existence of a capability, and if present, checks its value with the specified value. If the capability is not present or the values don't match, the operation evaluates to false. The comparisons are not case sensitive.

```yaml
pool:
  name: MyPool
  demands: Agent.Version -equals 2.144.0 # equals check for Agent.Version 2.144.0
```

### Agent variables as system capabilities

Self-hosted agents have the following system capabilities with similar names to agent variables, but they are not variables and don't require variable syntax when checking for exists or equals in a demand.

* Agent.Name
* Agent.Version
* Agent.ComputerName
* Agent.HomeDirectory
* Agent.OS
* Agent.OSArchitecture
* Agent.OSVersion (Windows agents only)
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::implementations::: -->
<!-- :::implementation-item name="demands: string"::: -->
<a name="demandsstring"></a>
<!-- :::stringAnyOf::: -->
:::moniker range=">=azure-pipelines-2019"

<!-- :::implementation-signature::: -->
## demands: string
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Specify a demand for a private pool.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
demands: string # Specify a demand for a private pool.
```
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-string-item::: -->
**`demands`** string.<br>
<!-- :::editable-content name="description"::: -->
Specify a demand for a private pool.
<!-- :::editable-content-end::: -->
<!-- :::implementation-string-item-end::: -->

:::moniker-end
<!-- :::stringAnyOf-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
### Examples

To add a single demand to your YAML build pipeline, add the `demands:` line to the `pool` section.

```yaml
pool:
  name: Default
  demands: SpecialSoftware # exists check for SpecialSoftware
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->
<!-- :::implementation-item-end::: -->
<!-- :::implementation-item name="demands: string list"::: -->
<a name="demandsstringlist"></a>
<!-- :::arrayAnyOf::: -->
:::moniker range=">=azure-pipelines-2019"

<!-- :::implementation-signature::: -->
## demands: string list
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Specify a list of demands for a private pool.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
demands: [ string ] # Specify a list of demands for a private pool.
```
<!-- :::implementation-syntax-end::: -->

### List types

<!-- :::implementation-list-types::: -->
| Type | Description |
|---|---|
| string | Specify a list of demands for a private pool. |
<!-- :::implementation-list-types-end::: -->

:::moniker-end
<!-- :::arrayAnyOf-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
### Examples

To specify multiple demands, add one per line.

```yaml
pool:
  name: MyPool
  demands:
  - myCustomCapability   # exists check for myCustomCapability
  - Agent.Version -equals 2.144.0 # equals check for Agent.Version 2.144.0
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->
<!-- :::implementation-item-end::: -->
<!-- :::implementations-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

* [Agent capabilities](/azure/devops/pipelines/agents/agents#capabilities)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
