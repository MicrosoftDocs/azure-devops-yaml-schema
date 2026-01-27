---
title: resources definition
description: Resources specifies builds, repositories, pipelines, and other resources used by the pipeline.
ms.date: 01/27/2026
monikerRange: "<=azure-pipelines"
author: juliakm
ms.author: jukullam
---

# resources definition

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Resources specifies builds, repositories, pipelines, and other resources used by the pipeline.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range="<=azure-pipelines"

```yaml
resources:
  builds: [ build ] # List of build resources referenced by the pipeline.
  containers: [ container ] # List of container images.
  pipelines: [ pipeline ] # List of pipeline resources.
  repositories: [ repository ] # List of repository resources.
  webhooks: [ webhook ] # List of webhooks.
  packages: [ package ] # List of package resources.
```

:::moniker-end

<!-- :::syntax-end::: -->

<!-- :::parents::: -->
:::moniker range="<=azure-pipelines"

Definitions that reference this definition: [pipeline](pipeline.md)

:::moniker-end
<!-- :::parents-end::: -->

## Properties

<!-- :::properties::: -->
<a name="builds-property"></a>
<!-- :::item name="builds"::: -->
:::moniker range="<=azure-pipelines"

**`builds`** [resources.builds](resources-builds.md).<br><!-- :::editable-content name="propDescription"::: -->
List of build resources referenced by the pipeline.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<a name="containers-property"></a>
<!-- :::item name="containers"::: -->
:::moniker range="<=azure-pipelines"

**`containers`** [resources.containers](resources-containers.md).<br><!-- :::editable-content name="propDescription"::: -->
List of container images.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<a name="pipelines-property"></a>
<!-- :::item name="pipelines"::: -->
:::moniker range="<=azure-pipelines"

**`pipelines`** [resources.pipelines](resources-pipelines.md).<br><!-- :::editable-content name="propDescription"::: -->
List of pipeline resources.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<a name="repositories-property"></a>
<!-- :::item name="repositories"::: -->
:::moniker range="<=azure-pipelines"

**`repositories`** [resources.repositories](resources-repositories.md).<br><!-- :::editable-content name="propDescription"::: -->
List of repository resources.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<a name="webhooks-property"></a>
<!-- :::item name="webhooks"::: -->
:::moniker range="<=azure-pipelines"

**`webhooks`** [resources.webhooks](resources-webhooks.md).<br><!-- :::editable-content name="propDescription"::: -->
List of webhooks.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<a name="packages-property"></a>
<!-- :::item name="packages"::: -->
:::moniker range="<=azure-pipelines"

**`packages`** [resources.packages](resources-packages.md).<br><!-- :::editable-content name="propDescription"::: -->
List of package resources.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::properties-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

- [Add resources to a pipeline](/azure/devops/pipelines/process/resources)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->