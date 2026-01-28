---
title: stages.template definition
description: You can define a set of stages in one file and use it multiple times in other files.
ms.date: 01/27/2026
monikerRange: "<=azure-pipelines"
author: juliakm
ms.author: jukullam
---

# stages.template definition

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
You can define a set of stages in one file and use it multiple times in other files.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range="<=azure-pipelines"

```yaml
stages:
- template: string # Required as first property. Reference to a template for this stage.
  parameters: # Parameters used in a stage template.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::parents::: -->
:::moniker range="<=azure-pipelines"

Definitions that reference this definition: [stages](stages.md)

:::moniker-end
<!-- :::parents-end::: -->

## Properties

<!-- :::properties::: -->
<!-- :::item name="template"::: -->
:::moniker range="<=azure-pipelines"

**`template`** string. Required as first property.<br><!-- :::editable-content name="propDescription"::: -->
Reference to a template for this stage.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="parameters"::: -->
:::moniker range="<=azure-pipelines"

**`parameters`** template parameters.<br><!-- :::editable-content name="propDescription"::: -->
Parameters used in a stage template.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::properties-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

Reference the stage template in the main pipeline.

```yaml
- template: string # name of template to include
  parameters: { string: any } # provided parameters
```

Define the stages in the template.

```yaml
parameters: { string: any } # expected parameters
stages: [ stage ]
```
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

In this example, a stage is repeated twice for two different testing regimes.
The stage itself is specified only once.

```yaml
# File: stages/test.yml

parameters:
  name: ''
  testFile: ''

stages:
- stage: Test_${{ parameters.name }}
  jobs:
  - job: ${{ parameters.name }}_Windows
    pool:
      vmImage: windows-latest
    steps:
    - script: npm install
    - script: npm test -- --file=${{ parameters.testFile }}
  - job: ${{ parameters.name }}_Mac
    pool:
      vmImage: macos-latest
    steps:
    - script: npm install
    - script: npm test -- --file=${{ parameters.testFile }}
```

```yaml
# File: azure-pipelines.yml

stages:
- template: stages/test.yml  # Template reference
  parameters:
    name: Mini
    testFile: tests/miniSuite.js

- template: stages/test.yml  # Template reference
  parameters:
    name: Full
    testFile: tests/fullSuite.js
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

- [Template types & usage](/azure/devops/pipelines/process/templates)
- [Security through templates](/azure/devops/pipelines/security/templates)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->