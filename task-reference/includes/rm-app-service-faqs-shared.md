---
ms.topic: include
ms.date: 12/10/2019
---

### How should I configure my service connection?

This task requires an [Azure Resource Manager service connection](/azure/devops/pipelines/release/azure-rm-endpoint).

### How should I configure web job deployment with Application Insights?

When you're deploying to an App Service, if you have [Application Insights](/azure/azure-monitor/app/app-insights-overview) configured and you've enabled `Remove additional files at destination`, you also need to enable `Exclude files from the App_Data folder`. Enabling this option keeps the Application Insights extension in a safe state. This step is required because the Application Insights continuous WebJob is installed into the App_Data folder.

### How should I configure my agent if it's behind a proxy while I'm deploying to App Service?

If your self-hosted agent requires a web proxy, you can inform the agent about the proxy during configuration. Doing so allows your agent to connect to Azure Pipelines or Azure DevOps Server through the proxy. [Learn more about running a self-hosted agent behind a web proxy](/azure/devops/pipelines/agents/proxy).
