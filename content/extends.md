---
title: extends definition
description: Extends a pipeline using a template.
ms.date: 12/18/2025
monikerRange: "<=azure-pipelines"
author: juliakm
ms.author: jukullam
ai-usage: ai-assisted
---

# extends definition

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Extend a pipeline using a template.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range="<=azure-pipelines"

```yaml
extends:
  template: string # The template referenced by the pipeline to extend.
  parameters: # Parameters used in the extend.
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
<!-- :::item name="template"::: -->
:::moniker range="<=azure-pipelines"

**`template`** string.<br><!-- :::editable-content name="propDescription"::: -->
The template referenced by the pipeline to extend.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="parameters"::: -->
:::moniker range="<=azure-pipelines"

**`parameters`** template parameters.<br><!-- :::editable-content name="propDescription"::: -->
Parameters used in the extend.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::properties-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Usage

The `extends` keyword allows a pipeline to use another pipeline (or template) as a base. This is useful for:

- **Reusing pipeline structure**: Create a base pipeline that multiple projects can extend
- **Enforcing standards**: Define required stages, jobs, or steps that all pipelines must include
- **Reducing duplication**: Share common configuration across pipelines
- **Template inheritance**: Build pipelines from templates with parameters

A pipeline can extend a single template. The template file should be a complete, valid pipeline structure. When you use `extends`, your pipeline YAML becomes a template that references the base template and optionally overrides parameters.

### Extends vs includes

- **`extends`**: Creates a pipeline that inherits from a template. Used at the root level of a pipeline.
- **`include`**: Imports template content directly. Used at specific points within a pipeline.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

### Basic extends example

The simplest way to use `extends` is to have a pipeline inherit stages and jobs from a base template.

```yaml
# File: base-pipeline.yml
# This is the base template that other pipelines extend
trigger:
  - main

pool:
  vmImage: 'ubuntu-latest'

stages:
- stage: Build
  jobs:
  - job: BuildJob
    steps:
    - script: echo Building...
      displayName: 'Build step'
```

```yaml
# File: azure-pipelines.yml
# This pipeline extends the base template
extends:
  template: base-pipeline.yml
```

In this example, the pipeline in `azure-pipelines.yml` inherits the trigger, pool, stages, and jobs from `base-pipeline.yml`.

### Extends with parameters

You can pass parameters to a template when extending it:

```yaml
# File: base-pipeline.yml
parameters:
- name: buildConfiguration
  type: string
  default: 'Debug'

trigger:
  - main

pool:
  vmImage: 'ubuntu-latest'

stages:
- stage: Build
  jobs:
  - job: BuildJob
    steps:
    - script: echo Building with configuration ${{ parameters.buildConfiguration }}
      displayName: 'Build step'
```

```yaml
# File: azure-pipelines.yml
extends:
  template: base-pipeline.yml
  parameters:
    buildConfiguration: 'Release'
```

### Multi-stage pipeline with extends

You can use `extends` to inherit multiple stages from a template. This is useful for teams that want a consistent pipeline structure across projects.

```yaml
# File: multi-stage-template.yml
# This template defines a complete three-stage pipeline
trigger:
  - main

pool:
  vmImage: 'ubuntu-latest'

stages:
- stage: Build
  displayName: 'Build Stage'
  jobs:
  - job: BuildJob
    displayName: 'Build Job'
    steps:
    - script: npm install
      displayName: 'Install dependencies'
    - script: npm run build
      displayName: 'Build application'

- stage: Test
  displayName: 'Test Stage'
  dependsOn: Build
  jobs:
  - job: TestJob
    displayName: 'Run Tests'
    steps:
    - script: npm run test
      displayName: 'Run unit tests'
    - script: npm run lint
      displayName: 'Run linter'

- stage: Deploy
  displayName: 'Deploy Stage'
  dependsOn: Test
  jobs:
  - job: DeployJob
    displayName: 'Deploy Job'
    steps:
    - script: npm run deploy
      displayName: 'Deploy to production'
```

```yaml
# File: azure-pipelines.yml
extends:
  template: multi-stage-template.yml
```

In this example, the pipeline automatically inherits all three stages (Build, Test, and Deploy) with their dependencies and job definitions from the template.

### Type-safe parameters with extends

Templates and their parameters are turned into constants before the pipeline runs.
Template parameters provide type safety to input parameters.
In this example, the template `start.yml` defines the parameter `buildSteps`, which is then used in `azure-pipelines.yml`. If a buildStep gets passed with a script step, then it's rejected and the pipeline build fails.

```yaml
# File: start.yml
parameters:
- name: buildSteps # the name of the parameter is buildSteps
  type: stepList # data type is StepList
  default: [] # default value of buildSteps
stages:
- stage: secure_buildstage
  pool:
    vmImage: windows-latest
  jobs:
  - job: secure_buildjob
    steps:
    - script: echo This happens before code 
      displayName: 'Base: Pre-build'
    - script: echo Building
      displayName: 'Base: Build'

    - ${{ each step in parameters.buildSteps }}:
      - ${{ each pair in step }}:
          ${{ if ne(pair.value, 'CmdLine@2') }}:
            ${{ pair.key }}: ${{ pair.value }}       
          ${{ if eq(pair.value, 'CmdLine@2') }}: 
            # Step is rejected by raising a YAML syntax error: Unexpected value 'CmdLine@2'
            '${{ pair.value }}': error         

    - script: echo This happens after code
      displayName: 'Base: Signing'
```

```yaml
# File: azure-pipelines.yml
trigger:
- main

extends:
  template: start.yml
  parameters:
    buildSteps:  
      - bash: echo Test #Passes
        displayName: succeed
      - bash: echo "Test"
        displayName: succeed
      # Step is rejected by raising a YAML syntax error: Unexpected value 'CmdLine@2'
      - task: CmdLine@2
        inputs:
          script: echo "Script Test"
      # Step is rejected by raising a YAML syntax error: Unexpected value 'CmdLine@2'
      - script: echo "Script Test"
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