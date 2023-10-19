---
title: boolean definition
description: Represents a boolean value in a pipeline.
ms.date: 10/19/2023
monikerRange: ">=azure-pipelines-2019"
---

# boolean definition

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Represents a boolean value in a pipeline.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range=">=azure-pipelines-2019"

```yaml
boolean: string # true | y | yes | on | false | n | no | off. 
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::string-item::: -->
:::moniker range=">=azure-pipelines-2019"

**`boolean`** string. Allowed values: true | y | yes | on | false | n | no | off.<br>
<!-- :::editable-content name="description"::: -->
Azure pipelines uses any of the previous string values to represent a boolean value in a pipeline.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::string-item-end::: -->

<!-- :::parents::: -->
:::moniker range=">=azure-pipelines-2022.1"

> [!NOTE]
> This definition is a supporting definition and is not intended for use directly in a pipeline. This article provides the YAML syntax for this supporting type, but does not show usage examples. For more information on using the definitions that this type supports, see the following definition links.

Definitions that reference this definition: [pipeline](pipeline.md), [trigger](trigger.md), [pr](pr.md), [jobs.job.container](jobs-job-container.md), [schedules.cron](schedules-cron.md), [variables.name](variables-name.md), [mountReadOnly](mount-read-only.md), [steps.task](steps-task.md), [steps.script](steps-script.md), [steps.powershell](steps-powershell.md), [steps.pwsh](steps-pwsh.md), [steps.bash](steps-bash.md), [steps.checkout](steps-checkout.md), [steps.download](steps-download.md), [steps.downloadBuild](steps-download-build.md), [steps.getPackage](steps-get-package.md), [steps.publish](steps-publish.md), [steps.reviewApp](steps-review-app.md), [resources.containers.container](resources-containers-container.md), [resources.containers.container.trigger](resources-containers-container-trigger.md), [resources.pipelines.pipeline.trigger](resources-pipelines-pipeline-trigger.md)

:::moniker-end

:::moniker range=">=azure-pipelines-2020.1 <=azure-pipelines-2022"

> [!NOTE]
> This definition is a supporting definition and is not intended for use directly in a pipeline. This article provides the YAML syntax for this supporting type, but does not show usage examples. For more information on using the definitions that this type supports, see the following definition links.

Definitions that reference this definition: [trigger](trigger.md), [pr](pr.md), [jobs.job.container](jobs-job-container.md), [schedules.cron](schedules-cron.md), [variables.name](variables-name.md), [mountReadOnly](mount-read-only.md), [steps.task](steps-task.md), [steps.script](steps-script.md), [steps.powershell](steps-powershell.md), [steps.pwsh](steps-pwsh.md), [steps.bash](steps-bash.md), [steps.checkout](steps-checkout.md), [steps.download](steps-download.md), [steps.downloadBuild](steps-download-build.md), [steps.getPackage](steps-get-package.md), [steps.publish](steps-publish.md), [steps.reviewApp](steps-review-app.md), [resources.containers.container](resources-containers-container.md), [resources.containers.container.trigger](resources-containers-container-trigger.md), [resources.pipelines.pipeline.trigger](resources-pipelines-pipeline-trigger.md)

:::moniker-end

:::moniker range="=azure-pipelines-2020"

> [!NOTE]
> This definition is a supporting definition and is not intended for use directly in a pipeline. This article provides the YAML syntax for this supporting type, but does not show usage examples. For more information on using the definitions that this type supports, see the following definition links.

Definitions that reference this definition: [trigger](trigger.md), [pr](pr.md), [jobs.job.container](jobs-job-container.md), [schedules.cron](schedules-cron.md), [variables.name](variables-name.md), [steps.task](steps-task.md), [steps.script](steps-script.md), [steps.powershell](steps-powershell.md), [steps.pwsh](steps-pwsh.md), [steps.bash](steps-bash.md), [steps.checkout](steps-checkout.md), [steps.download](steps-download.md), [steps.downloadBuild](steps-download-build.md), [steps.getPackage](steps-get-package.md), [steps.publish](steps-publish.md), [steps.reviewApp](steps-review-app.md), [resources.containers.container](resources-containers-container.md), [resources.containers.container.trigger](resources-containers-container-trigger.md), [resources.pipelines.pipeline.trigger](resources-pipelines-pipeline-trigger.md)

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

> [!NOTE]
> This definition is a supporting definition and is not intended for use directly in a pipeline. This article provides the YAML syntax for this supporting type, but does not show usage examples. For more information on using the definitions that this type supports, see the following definition links.

Definitions that reference this definition: [trigger](trigger.md), [pr](pr.md), [steps.task](steps-task.md), [steps.script](steps-script.md), [steps.powershell](steps-powershell.md), [steps.pwsh](steps-pwsh.md), [steps.bash](steps-bash.md), [steps.checkout](steps-checkout.md), [steps.download](steps-download.md), [steps.downloadBuild](steps-download-build.md), [steps.publish](steps-publish.md), [resources.containers.container](resources-containers-container.md)

:::moniker-end

:::moniker range="=azure-pipelines-2019"

> [!NOTE]
> This definition is a supporting definition and is not intended for use directly in a pipeline. This article provides the YAML syntax for this supporting type, but does not show usage examples. For more information on using the definitions that this type supports, see the following definition links.

Definitions that reference this definition: [trigger](trigger.md), [steps.task](steps-task.md), [steps.script](steps-script.md), [steps.powershell](steps-powershell.md), [steps.pwsh](steps-pwsh.md), [steps.bash](steps-bash.md), [steps.checkout](steps-checkout.md), [steps.download](steps-download.md), [steps.downloadBuild](steps-download-build.md), [steps.publish](steps-publish.md), [resources.containers.container](resources-containers-container.md)

:::moniker-end
<!-- :::parents-end::: -->

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
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->