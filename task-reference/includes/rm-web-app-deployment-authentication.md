---
ms.topic: include
ms.date: 10/25/2023
---

#### I can't Web Deploy to my Azure App Service using Microsoft Entra ID authentication from my Windows agent

The Azure App Service deploy task supports connecting to Microsoft Azure with an ARM service connection using Microsoft Entra ID, unless the following three conditions are present:

* You are using Web Deploy package format on a Windows agent
* Your agent is running with an older version of **msdeploy.exe** (for example when using the **windows-2019** hosted agent image)
* Basic authentication is disabled for your Azure App Service

If these three conditions are present, you will receive an error like `App Service is configured to not use basic authentication. This requires Web Deploy msdeploy.exe version 7.1.7225.2108 or higher. You need a version of Visual Studio that includes an updated version of msdeploy.exe. For more information, visit https://aka.ms/azdo-webapp-msdeploy.`

To resolve this issue, you can choose from the following options, in order of preference.

1. Update the agent image. If you are using hosted agents, move from **windows-2019** to **windows-2022** (or **windows-latest**). If you are using self-hosted agents, install Visual Studio 2022 on the agent to get a newer version of **msdeploy.exe**.
1. If you are dependent on an older agent image and can't update the agent for your pipeline, consider splitting the job so that the Azure App Service deploy task runs on **windows-2022** (or **windows-latest**).
1. If neither of these options is possible, you can [enable basic authentication](/azure/app-service/deploy-configure-credentials#disable-basic-authentication) for your Azure App Service.
1. 