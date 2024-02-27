---
title: resources.containers.container.trigger definition
description: Specify none to disable, true to trigger on all image tags, or use the full syntax as described in the following examples.
ms.date: 02/27/2024
monikerRange: ">=azure-pipelines-2020"
---

# resources.containers.container.trigger definition

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
Specifies the trigger conditions for a container resource.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::parents::: -->
:::moniker range=">=azure-pipelines-2020"

Definitions that reference this definition: [resources.containers.container](resources-containers-container.md)

:::moniker-end
<!-- :::parents-end::: -->

## Implementations

<!-- :::implementations-list::: -->
:::moniker range=">=azure-pipelines-2020"

| Implementation | Description |
|---|---|
| [trigger: enabled, tags](#triggerobjectproperties) | Specify a list of tags to trigger on. |
| [trigger: none | true](#triggerstring) | Specify none to disable or true to trigger on all image tags. |

:::moniker-end
<!-- :::implementations-list-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

Specify none to disable, true to trigger on all image tags, or use the full syntax as described in the following examples.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::implementations::: -->
<!-- :::implementation-item name="trigger: object properties"::: -->
<a name="triggerobjectproperties"></a>
<!-- :::objectAnyOf::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::implementation-signature::: -->
## trigger: enabled, tags
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Configure which tags trigger a run.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
trigger:
  enabled: boolean # Whether the trigger is enabled; defaults to true.
  tags: includeExcludeStringFilters | [ string ] # Tag names to include or exclude for triggering a run.
```
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-properties::: -->
### Properties

<!-- :::item name="enabled"::: -->
**`enabled`** [boolean](boolean.md).<br><!-- :::editable-content name="propDescription"::: -->
Whether the trigger is enabled; defaults to true.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="tags"::: -->
**`tags`** [includeExcludeStringFilters](include-exclude-string-filters.md).<br><!-- :::editable-content name="propDescription"::: -->
Tag names to include or exclude for triggering a run.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::implementation-properties-end::: -->

:::moniker-end
<!-- :::objectAnyOf-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
### Examples

In the following example, the trigger is enabled for tags matching `production*`.

```yaml
resources:         
  containers:
  - container: petStore      
    type: ACR  
    azureSubscription: ContosoARMConnection
    resourceGroup: ContosoGroup
    registry: petStoreRegistry
    repository: myPets
    trigger: 
      tags:
        include: 
        - production*
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->
<!-- :::implementation-item-end::: -->
<!-- :::implementation-item name="trigger: string"::: -->
<a name="triggerstring"></a>
<!-- :::stringAnyOf::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::implementation-signature::: -->
## trigger: none | true
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Specify none to disable or true to trigger on all image tags.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
trigger: none | true # Specify none to disable or true to trigger on all image tags.
```
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-string-item::: -->
**`trigger`** string. Allowed values: none | true.<br>
<!-- :::editable-content name="description"::: -->
Specify none to disable or true to trigger on all image tags.
<!-- :::editable-content-end::: -->
<!-- :::implementation-string-item-end::: -->

:::moniker-end
<!-- :::stringAnyOf-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
### Remarks

Specify `none` to disable the trigger, or `true` to enable. If not specified, the default is `none`. To configure triggers based on specific tags, see the following section.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
### Examples

```yaml
resources:         
  containers:
  - container: petStore      
    type: ACR  
    azureSubscription: ContosoARMConnection
    resourceGroup: ContosoGroup
    registry: petStoreRegistry
    repository: myPets
    trigger: 
      tags: none # Triggers disabled
```

```yaml
resources:         
  containers:
  - container: petStore      
    type: ACR  
    azureSubscription: ContosoARMConnection
    resourceGroup: ContosoGroup
    registry: petStoreRegistry
    repository: myPets
    trigger: 
      tags: true # Triggers enabled for all tags
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->
<!-- :::implementation-item-end::: -->
<!-- :::implementations-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

* [Define a container resource](/azure/devops/pipelines/process/resources#define-a-containers-resource)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
