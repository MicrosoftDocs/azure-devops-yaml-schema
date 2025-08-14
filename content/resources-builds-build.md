---
title: resources.builds.build definition
description: A build resource used to reference artifacts from a run.
ms.date: 08/14/2025
monikerRange: "<=azure-pipelines"
author: juliakm
ms.author: jukullam
---

# resources.builds.build definition

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
A build resource used to reference artifacts from a run.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range="<=azure-pipelines"

```yaml
builds:
- build: string # Required as first property. Alias or name of build artifact.
  type: string # Required. Name of the artifact type.
  connection: string # Required. Name of the connection. This connection will be used for all the communication related to this artifact.
  source: string # Required. Name of the source definition/build/job.
  version: string
  branch: string
  trigger: none | true # When the artifact mentioned in this build resource completes a build, it is allowed to trigger this pipeline.
```

:::moniker-end

<!-- :::syntax-end::: -->

<!-- :::parents::: -->
:::moniker range="<=azure-pipelines"

Definitions that reference this definition: [resources.builds](resources-builds.md)

:::moniker-end
<!-- :::parents-end::: -->

## Properties

<!-- :::properties::: -->
<!-- :::item name="build"::: -->
:::moniker range="<=azure-pipelines"

**`build`** string. Required as first property.<br><!-- :::editable-content name="propDescription"::: -->
Alias or name of build artifact. Acceptable values: [-_A-Za-z0-9]*.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="type"::: -->
:::moniker range="<=azure-pipelines"

**`type`** string. Required.<br><!-- :::editable-content name="propDescription"::: -->
Name of the artifact type.
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
<!-- :::item name="source"::: -->
:::moniker range="<=azure-pipelines"

**`source`** string. Required.<br><!-- :::editable-content name="propDescription"::: -->
Name of the source definition/build/job.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="version"::: -->
:::moniker range="<=azure-pipelines"

**`version`** string.<br><!-- :::editable-content name="propDescription"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="branch"::: -->
:::moniker range="<=azure-pipelines"

**`branch`** string.<br><!-- :::editable-content name="propDescription"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="trigger"::: -->
:::moniker range="<=azure-pipelines"

**`trigger`** string.<br><!-- :::editable-content name="propDescription"::: -->
When the artifact mentioned in this build resource completes a build, it is allowed to trigger this pipeline. none | true.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::properties-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

If you have an external CI build system that produces artifacts, you can consume artifacts with a build resource. A build resource can be any external CI systems like Jenkins, TeamCity, CircleCI, and so on.

> [!IMPORTANT]
> Triggers are only supported for hosted Jenkins where Azure DevOps has line of sight with Jenkins server.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

```yaml
resources:
  builds:
  - build: Spaceworkz
    type: Jenkins
    connection: MyJenkinsServer 
    source: SpaceworkzProj   # name of the jenkins source project
    trigger: true
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

[Define resources in YAML](/azure/devops/pipelines/process/resources)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->