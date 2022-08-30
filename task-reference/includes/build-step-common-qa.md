---
ms.topic: include
ms.date: 08/29/2022
---

### I'm having issues with publishing my artifacts. How can I view the detailed logs?

To enable detailed logs for your pipeline:

1. Edit your pipeline and select **Variables**
1. Add a new variable with the name `System.Debug` and value `true`
1. **Save**

#### Which variables are available to me?

A: `$(Build.SourcesDirectory)` and `$(Agent.BuildDirectory)` are just few of the variables you can use in your pipeline. Variables are available as [expressions](/azure/devops/pipelines/process/expressions) or scripts.

See [Define variables](/azure/devops/pipelines/process/variables), [predefined variables](/azure/devops/pipelines/build/variables), and [Classic release and artifacts variables](/azure/devops/pipelines/release/variables)  to learn about the different types of variables.

#### The task allows me to publish artifacts in deployment job in yaml pipeline, but I am not able to use it in downstream pipeline?

A:  Deployment jobs do not have the context of source branches and are hence not appropriate for publishing artifacts. They have been primarily designed to consume artifacts. A workaround would be to isolate that logic into a separate job (with dependencies on your deployment jobs).
