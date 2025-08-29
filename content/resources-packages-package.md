---
title: resources.packages.package definition
description: A package resource used to reference a NuGet or npm GitHub package.
ms.date: 08/14/2025
monikerRange: "<=azure-pipelines"
author: juliakm
ms.author: jukullam
---

# resources.packages.package definition

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
You can consume NuGet and npm GitHub packages as a resource in YAML pipelines. When specifying package resources, set the package as `NuGet` or `npm`.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range="<=azure-pipelines"

```yaml
packages:
- package: string # Required as first property. Alias of package artifact.
  type: string # Required. Type of the package. Ex - NuGet, NPM etc.
  connection: string # Required. Name of the connection. This connection will be used for all the communication related to this artifact.
  name: string # Required. Name of the package.
  version: string
  tag: string
  trigger: none | true # Trigger a new pipeline run when a new version of this package is available.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::parents::: -->
:::moniker range="<=azure-pipelines"

Definitions that reference this definition: [resources.packages](resources-packages.md)

:::moniker-end
<!-- :::parents-end::: -->

## Properties

<!-- :::properties::: -->
<!-- :::item name="package"::: -->
:::moniker range="<=azure-pipelines"

**`package`** string. Required as first property.<br><!-- :::editable-content name="propDescription"::: -->
Alias of package artifact. Acceptable values: [-_A-Za-z0-9]*.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="type"::: -->
:::moniker range="<=azure-pipelines"

**`type`** string. Required.<br><!-- :::editable-content name="propDescription"::: -->
Type of the package. Ex - NuGet, NPM etc.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="connection"::: -->
:::moniker range="<=azure-pipelines"

**`connection`** string. Required.<br><!-- :::editable-content name="propDescription"::: -->
Name of the connection. This connection will be used for all the communication related to this artifact.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="name"::: -->
:::moniker range="<=azure-pipelines"

**`name`** string. Required.<br><!-- :::editable-content name="propDescription"::: -->
Name of the package.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="version"::: -->
:::moniker range="<=azure-pipelines"

**`version`** string.<br><!-- :::editable-content name="propDescription"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="tag"::: -->
:::moniker range="<=azure-pipelines"

**`tag`** string.<br><!-- :::editable-content name="propDescription"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="trigger"::: -->
:::moniker range="<=azure-pipelines"

**`trigger`** string.<br><!-- :::editable-content name="propDescription"::: -->
Trigger a new pipeline run when a new version of this package is available. none | true.
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
## Examples

In this example, there is an [GitHub service connection](/azure/devops/pipelines/library/service-endpoints#common-service-connection-types) named `pat-contoso` to a GitHub npm package named `contoso`. Learn more about [GitHub packages](https://github.com/features/packages). 

```yaml
resources:
  packages:
    - package: contoso
      type: npm
      connection: pat-contoso
      name: yourname/contoso 
      version: 7.130.88 
      trigger: true

pool:
  vmImage: ubuntu-latest

steps:
- getPackage: contoso 
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

- [Add resources to a pipeline](/azure/devops/pipelines/process/resources)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->