---
ms.topic: include
ms.date: 10/10/2024
---

### Use AzurePipelinesCredential in integration tests

The Azure Identity libraries for .NET, C++, Go, Java, JavaScript, and Python [provide support for workload identity federation](https://devblogs.microsoft.com/azure-sdk/improve-security-posture-in-azure-service-connections-with-azurepipelinescredential/), so code executed from the [AzureCLI@2](../azure-cli-v2.md) and [AzurePowerShell@5](../azure-powershell-v5.md) tasks can authenticate with Microsoft Entra ID (for example, to access Azure) using the `AzurePipelinesCredential` class.

Many customers are using Azure SDK client libraries in integration tests invoked from other tasks. The [DotNetCoreCLI@2](../dotnet-core-cli-v2.md), [Maven@4](../maven-v4.md) and [VSTest@3](../vstest-v3.md) tasks can access Azure resources using the `AzurePipelinesCredential` class.

You can set the `connectedServiceName` property to an Azure service connection configured with workload identity federation. The `AzurePipelinesCredential` requires [SYSTEM_ACCESSTOKEN](/azure/devops/pipelines/build/variables#systemaccesstoken) to be set.

The following example shows the `connectedService` input on the `DotNetCoreCLI@2` task. `VSTest@3` and `Maven@4` usage is similar.

```yaml
- task: DotNetCoreCLI@2
  inputs:
    command: 'run'
    connectedServiceName: <Azure service connection configured with workload identity federation>
  env:
    SYSTEM_ACCESSTOKEN: $(System.AccessToken)
```

For more information on `AzurePipelinesCredential`, see [Improve security posture in Azure service connections with AzurePipelinesCredential](https://devblogs.microsoft.com/azure-sdk/improve-security-posture-in-azure-service-connections-with-azurepipelinescredential/).
