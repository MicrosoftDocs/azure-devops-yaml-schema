---
ms.topic: include
ms.date: 11/15/2024
---

You can use template expressions to specify the service connection input. In the following example, the `azureSubscription` is creating using a format string and an expression based on the `environmentName` variable.

```yml
pool:
  vmImage: ubuntu-latest

variables:
  # Format string for the service connection
  azureSubscriptionFormat: 'connectionString-{0}-001'

stages:
- stage: Prepare
  variables:
    environmentName: 'test'
    # Stage level variable with the service connection name
    # Evaluates to conenctionString-test-001
    azureSubscription: ${{ format(variables.azureSubscriptionFormat, variables.environmentName) }}

  jobs:
  - job: RunStuff
    steps:
    - task: AzureCLI@2
      inputs:
        # Set this input to the computed value
        azureSubscription: ${{ variables.azureSubscription }}
        scriptType: bash
        scriptLocation: inlineScript
        inlineScript: 'echo Hello ${{ variables.azureSubscription }}'

    - task: AzurePowerShell@5
      inputs:
        # Set this input to the computed value
        azureSubscription: ${{ variables.azureSubscription }}
        azurePowerShellVersion: 'LatestVersion'
        scriptType: 'InlineScript'
        inline: Write-Host "Hello ${{ variables.azureSubscription }}"
```