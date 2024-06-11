---
title: resources definition
description: Resources specifies builds, repositories, pipelines, and other resources used by the pipeline.
ms.date: 06/11/2024
monikerRange: ">=azure-pipelines-2019"
---

# resources definition

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Resources specifies builds, repositories, pipelines, and other resources used by the pipeline.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range=">=azure-pipelines-2020.1"

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

:::moniker range="=azure-pipelines-2020"

```yaml
resources:
  builds: [ build ] # List of build resources referenced by the pipeline.
  containers: [ container ] # List of container images.
  pipelines: [ pipeline ] # List of pipeline resources.
  repositories: [ repository ] # List of repository resources.
  packages: [ package ] # List of package resources.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2019.1"

```yaml
resources:
  builds: [ build ] # List of build resources referenced by the pipeline.
  containers: [ container ] # List of container images.
  pipelines: [ pipeline ] # List of pipeline resources.
  repositories: [ repository ] # List of repository resources.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::parents::: -->
:::moniker range=">=azure-pipelines-2019"

Definitions that reference this definition: [pipeline](pipeline.md)

:::moniker-end
<!-- :::parents-end::: -->

## Properties

<!-- :::properties::: -->
<!-- :::item name="builds"::: -->
:::moniker range=">=azure-pipelines-2019"

**`builds`** [resources.builds](resources-builds.md).<br><!-- :::editable-content name="propDescription"::: -->
List of build resources referenced by the pipeline.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="containers"::: -->
:::moniker range=">=azure-pipelines-2019"

**`containers`** [resources.containers](resources-containers.md).<br><!-- :::editable-content name="propDescription"::: -->
List of container images.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="pipelines"::: -->
:::moniker range=">=azure-pipelines-2019"

**`pipelines`** [resources.pipelines](resources-pipelines.md).<br><!-- :::editable-content name="propDescription"::: -->
List of pipeline resources.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="repositories"::: -->
:::moniker range=">=azure-pipelines-2019"

**`repositories`** [resources.repositories](resources-repositories.md).<br><!-- :::editable-content name="propDescription"::: -->
List of repository resources.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="webhooks"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`webhooks`** [resources.webhooks](resources-webhooks.md).<br><!-- :::editable-content name="propDescription"::: -->
List of webhooks.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="packages"::: -->
:::moniker range=">=azure-pipelines-2020"

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