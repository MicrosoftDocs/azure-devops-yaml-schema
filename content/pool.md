---
title: pool definition
description: Which pool to use for a job of the pipeline.
ms.date: 06/11/2024
monikerRange: ">=azure-pipelines-2019"
---

# pool definition

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
The `pool` keyword specifies which [pool](/azure/devops/pipelines/agents/pools-queues) to use for a job of the pipeline.
A `pool` specification also holds information about the job's strategy for running.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::parents::: -->
:::moniker range=">=azure-pipelines-2020"

Definitions that reference this definition: [pipeline](pipeline.md), [stages.stage](stages-stage.md), [jobs.job](jobs-job.md), [jobs.deployment](jobs-deployment.md), [preDeployHook](pre-deploy-hook.md), [deployHook](deploy-hook.md), [routeTrafficHook](route-traffic-hook.md), [postRouteTrafficHook](post-route-traffic-hook.md), [onFailureHook](on-failure-hook.md), [onSuccessHook](on-success-hook.md)

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2019.1"

Definitions that reference this definition: [pipeline](pipeline.md), [jobs.job](jobs-job.md)

:::moniker-end
<!-- :::parents-end::: -->

## Implementations

<!-- :::implementations-list::: -->
:::moniker range="=azure-pipelines"

| Implementation | Description |
|---|---|
| [pool: string](#poolstring) | Specify a private pool by name. |
| [pool: name, demands, vmImage](#poolobjectproperties) | Full syntax for using demands and Microsoft-hosted pools. |

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2022.2"

| Implementation | Description |
|---|---|
| [pool: string](#poolstring) | Specify a private pool by name. |
| [pool: name, demands](#poolobjectproperties) | Which pool to use for a job of the pipeline. |

:::moniker-end
<!-- :::implementations-list-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

::: moniker range=">= azure-pipelines-2019 <= azure-pipelines-2019.1"

In Azure DevOps Server 2019 you can specify a pool at the job level in YAML, and at the pipeline level in the pipeline settings UI. In Azure DevOps Server 2019.1 you can also specify a pool at the pipeline level in YAML if you have a single implicit job.
:::moniker-end

::: moniker range=">= azure-pipelines-2020"
You can specify a pool at the pipeline, stage, or job level.
:::moniker-end

The pool specified at the lowest level of the hierarchy is used to run the job.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::implementations::: -->
<!-- :::implementation-item name="pool: string"::: -->
<a name="poolstring"></a>
<!-- :::stringAnyOf::: -->
:::moniker range=">=azure-pipelines-2019"

<!-- :::implementation-signature::: -->
## pool: string
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Specify a private pool by name to use for a job of the pipeline.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
pool: string # Specify a private pool by name.
```
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-string-item::: -->
**`pool`** string.<br>
<!-- :::editable-content name="description"::: -->
Specify a private pool by name.
<!-- :::editable-content-end::: -->
<!-- :::implementation-string-item-end::: -->

:::moniker-end
<!-- :::stringAnyOf-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
### Remarks

Use this syntax to specify a private pool by name.

> [!NOTE]
> If your pool name has a space in it, enclose the pool name in single quotes, like `pool: 'My pool'`.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
### Examples

To use a private pool with no demands:

```yaml
pool: MyPool
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->
<!-- :::implementation-item-end::: -->
<!-- :::implementation-item name="pool: object properties"::: -->
<a name="poolobjectproperties"></a>
<!-- :::objectAnyOf::: -->
:::moniker range="=azure-pipelines"

<!-- :::implementation-signature::: -->
## pool: name, demands, vmImage
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Full syntax for using demands and Microsoft-hosted pools.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
pool:
  name: string # Name of a pool.
  demands: string | [ string ] # Demands (for a private pool).
  vmImage: string # Name of the VM image you want to use; valid only in the Microsoft-hosted pool.
```
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-properties::: -->
### Properties

<!-- :::item name="name"::: -->
**`name`** string.<br><!-- :::editable-content name="propDescription"::: -->
Name of a pool.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="demands"::: -->
**`demands`** [pool.demands](pool-demands.md).<br><!-- :::editable-content name="propDescription"::: -->
Demands (for a private pool).
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="vmImage"::: -->
**`vmImage`** string.<br><!-- :::editable-content name="propDescription"::: -->
Name of the VM image you want to use; valid only in the Microsoft-hosted pool.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::implementation-properties-end::: -->

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2022.2"

<!-- :::implementation-signature::: -->
## pool: name, demands
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Which pool to use for a job of the pipeline.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
pool:
  name: string # Name of a pool.
  demands: string | [ string ] # Demands (for a private pool).
```
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-properties::: -->
### Properties

<!-- :::item name="name"::: -->
**`name`** string.<br><!-- :::editable-content name="propDescription"::: -->
Name of a pool.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="demands"::: -->
**`demands`** [pool.demands](pool-demands.md).<br><!-- :::editable-content name="propDescription"::: -->
Demands (for a private pool).
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::implementation-properties-end::: -->

:::moniker-end
<!-- :::objectAnyOf-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
### Remarks

:::moniker range="= azure-pipelines"

Specify a Microsoft-hosted pool using the `vmImage` property.

::: moniker-end

If your self-hosted agent pool name has a space in it, enclose the pool name in single quotes, like `name: 'My pool'`.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
### Examples

:::moniker range="= azure-pipelines"

To use a Microsoft-hosted pool, omit the name and specify one of the available [hosted images](/azure/devops/pipelines/agents/hosted#use-a-microsoft-hosted-agent):

```yaml
pool:
  vmImage: ubuntu-latest
```

::: moniker-end

You can specify demands for a private pool using the full syntax.

To add a single demand to your YAML build pipeline, add the `demands:` line to the `pool` section.

```yaml
pool:
  name: Default
  demands: SpecialSoftware # exists check for SpecialSoftware
```

Or if you need to add multiple demands, add one per line.

```yaml
pool:
  name: MyPool
  demands:
  - myCustomCapability   # exists check for myCustomCapability
  - Agent.Version -equals 2.144.0 # equals check for Agent.Version 2.144.0
```

Checking for the existence of a capability (exists) and checking for a specific string in a capability (equals) are the only two supported operations for demands.

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

For more information, see [Specify demands](/azure/devops/pipelines/process/demands).
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->
<!-- :::implementation-item-end::: -->
<!-- :::implementations-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

* [Specify demands](/azure/devops/pipelines/process/demands)
* Learn more about [conditions](/azure/devops/pipelines/process/conditions) and [timeouts](/azure/devops/pipelines/process/phases#timeouts).
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
