---
title: resources.packages list definition
description: resources.packages list definition reference.
ms.date: 08/08/2022
monikerRange: "= azure-pipelines || = azure-pipelines-2020 || = azure-pipelines-2020.1 || = azure-pipelines-2022"
---

# resources.packages list definition


List of package resources referenced by the pipeline.


:::moniker range="= azure-pipelines-2020"

<!-- :::api-definition signature="packageResources[packageResource]" version="azure-pipelines-2020"::: -->

```yaml
packages: [ package ] # 
```


Properties that use this definition: [resources.packages](resources.md)

## List types

| Type     | Description |
|----------|-------------|
| [resources.packages.package](resources-packages-package.md) | A package resource used to reference a NuGet or npm GitHub package. |

<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020.1"

<!-- :::api-definition signature="packageResources[packageResource]" version="azure-pipelines-2020.1"::: -->

```yaml
packages: [ package ] # 
```


Properties that use this definition: [resources.packages](resources.md)

## List types

| Type     | Description |
|----------|-------------|
| [resources.packages.package](resources-packages-package.md) | A package resource used to reference a NuGet or npm GitHub package. |

<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2022"

<!-- :::api-definition signature="packageResources[packageResource]" version="azure-pipelines-2022"::: -->

```yaml
packages: [ package ] # 
```


Properties that use this definition: [resources.packages](resources.md)

## List types

| Type     | Description |
|----------|-------------|
| [resources.packages.package](resources-packages-package.md) | A package resource used to reference a NuGet or npm GitHub package. |

<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines"

<!-- :::api-definition signature="packageResources[packageResource]" version="azure-pipelines"::: -->

```yaml
packages: [ package ] # 
```


Properties that use this definition: [resources.packages](resources.md)

## List types

| Type     | Description |
|----------|-------------|
| [resources.packages.package](resources-packages-package.md) | A package resource used to reference a NuGet or npm GitHub package. |

<!-- :::api-definition-end::: -->

:::moniker-end


<!-- Remarks -->


<!-- Examples -->


## See also

- [Add resources to a pipeline](/azure/devops/pipelines/process/resources)

