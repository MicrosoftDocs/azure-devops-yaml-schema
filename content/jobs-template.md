---
title: jobs.template definition
description: A set of jobs defined in a template.
ms.date: 08/14/2025
monikerRange: "<=azure-pipelines"
author: juliakm
ms.author: jukullam
---

# jobs.template definition

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
A set of jobs defined in a template.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range="<=azure-pipelines"

```yaml
jobs:
- template: string # Required as first property. Reference to a template for this deployment.
  parameters: # Parameters used in a deployment template.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::parents::: -->
:::moniker range="<=azure-pipelines"

Definitions that reference this definition: [jobs](jobs.md)

:::moniker-end
<!-- :::parents-end::: -->

## Properties

<!-- :::properties::: -->
<!-- :::item name="template"::: -->
:::moniker range="<=azure-pipelines"

**`template`** string. Required as first property.<br><!-- :::editable-content name="propDescription"::: -->
Reference to a template for this deployment.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="parameters"::: -->
:::moniker range="<=azure-pipelines"

**`parameters`** template parameters.<br><!-- :::editable-content name="propDescription"::: -->
Parameters used in a deployment template.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::properties-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

You can define a set of jobs in one file and use it multiple times in other files. See [templates](/azure/devops/pipelines/process/templates) for more about working with job templates.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

In the main pipeline:

```yaml
- template: string # name of template to include
  parameters: { string: any } # provided parameters
```

In the included template:

```yaml
parameters: { string: any } # expected parameters
jobs: [ job ]
```

In this example, a single job is repeated on three platforms.
The job itself is specified only once.

```yaml
# File: jobs/build.yml

parameters:
  name: ''
  pool: ''
  sign: false

jobs:
- job: ${{ parameters.name }}
  pool: ${{ parameters.pool }}
  steps:
  - script: npm install
  - script: npm test
  - ${{ if eq(parameters.sign, 'true') }}:
    - script: sign
```

```yaml
# File: azure-pipelines.yml

jobs:
- template: jobs/build.yml  # Template reference
  parameters:
    name: macOS
    pool:
      vmImage: macOS-latest

- template: jobs/build.yml  # Template reference
  parameters:
    name: Linux
    pool:
      vmImage: ubuntu-latest

- template: jobs/build.yml  # Template reference
  parameters:
    name: Windows
    pool:
      vmImage: windows-latest
    sign: true  # Extra step on Windows only
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

See [templates](/azure/devops/pipelines/process/templates) for more about working with job templates.
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->