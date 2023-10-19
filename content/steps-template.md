---
title: steps.template definition
description: Define a set of steps in one file and use it multiple times in another file.
ms.date: 10/19/2023
monikerRange: ">=azure-pipelines-2019"
---

# steps.template definition

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Define a set of steps in one file and use it multiple times in another file.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range=">=azure-pipelines-2019"

```yaml
steps:
- template: string # Required as first property. Reference to a template for this step.
  parameters: # Parameters used in a step template.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::parents::: -->
:::moniker range=">=azure-pipelines-2019"

Definitions that reference this definition: [steps](steps.md)

:::moniker-end
<!-- :::parents-end::: -->

## Properties

<!-- :::properties::: -->
<!-- :::item name="template"::: -->
:::moniker range=">=azure-pipelines-2019"

**`template`** string. Required as first property.<br><!-- :::editable-content name="propDescription"::: -->
Reference to a template for this step.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="parameters"::: -->
:::moniker range=">=azure-pipelines-2019"

**`parameters`** template parameters.<br><!-- :::editable-content name="propDescription"::: -->
Parameters used in a step template.
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

In the main pipeline:

```yaml
steps:
- template: string  # reference to template
  parameters: { string: any } # provided parameters
```

In the included template:

```yaml
parameters: { string: any } # expected parameters
steps: [ script | bash | pwsh | powershell | checkout | task | templateReference ]
```

```yaml
# File: steps/build.yml

steps:
- script: npm install
- script: npm test
```

```yaml
# File: azure-pipelines.yml

jobs:
- job: macOS
  pool:
    vmImage: macOS-latest
  steps:
  - template: steps/build.yml # Template reference

- job: Linux
  pool:
    vmImage: ubuntu-latest
  steps:
  - template: steps/build.yml # Template reference

- job: Windows
  pool:
    vmImage: windows-latest
  steps:
  - template: steps/build.yml # Template reference
  - script: sign              # Extra step on Windows only
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

See [templates](/azure/devops/pipelines/process/templates) for more about working with templates.
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->