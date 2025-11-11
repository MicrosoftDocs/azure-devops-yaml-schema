---
title: IISWebAppDeployment@1 - IIS Web App deployment (Deprecated) v1 task
description: Deploy using MSDeploy, then create/update websites and app pools.
ms.date: 11/11/2025
monikerRange: "=azure-pipelines || =azure-pipelines-server || =azure-pipelines-2022.2 || =azure-pipelines-2022.1 || =azure-pipelines-2022 || =azure-pipelines-2020.1 || =azure-pipelines-2020"
author: juliakm
ms.author: jukullam
---

# IISWebAppDeployment@1 - IIS Web App deployment (Deprecated) v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-server"

<!-- :::editable-content name="description"::: -->
Use this task to deploy IIS Web App using MSDeploy, then create or update websites and app pools.

> [!IMPORTANT]
> [!INCLUDE [task-deprecation](includes/task-deprecation.md)] Use [IIS Web App Deployment Using WinRM - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=ms-vscs-rm.iiswebapp).
<!-- :::editable-content-end::: -->

<!-- This task is deprecated. -->

:::moniker-end

:::moniker range="<=azure-pipelines-2022.2"

<!-- :::editable-content name="description"::: -->
Use this task to deploy IIS Web App using MSDeploy, then create or update websites and app pools.

> [!IMPORTANT]
> This task is deprecated. Use [IIS Web App Deployment Using WinRM - Viual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=ms-vscs-rm.iiswebapp).
<!-- :::editable-content-end::: -->

<!-- This task is deprecated. -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="<=azure-pipelines"

```yaml
# IIS Web App deployment (Deprecated) v1
# Deploy using MSDeploy, then create/update websites and app pools.
- task: IISWebAppDeployment@1
  inputs:
    EnvironmentName: # string. Required. Machines. 
    #AdminUserName: # string. Admin Login. 
    #AdminPassword: # string. Password. 
    #WinRMProtocol: # 'Http' | 'Https'. Protocol. 
    #TestCertificate: true # boolean. Optional. Use when WinRMProtocol = Https. Test Certificate. Default: true.
  # Deployment
    WebDeployPackage: # string. Required. Web Deploy Package. 
    #WebDeployParamFile: # string. Web Deploy Parameter File. 
    #OverRideParams: # string. Override Parameters. 
  # Website
    #CreateWebSite: false # boolean. Create or Update Website. Default: false.
    #WebSiteName: # string. Required when CreateWebSite = true. Website Name. 
    #WebSitePhysicalPath: '%SystemDrive%\inetpub\wwwroot' # string. Required when CreateWebSite = true. Physical Path. Default: %SystemDrive%\inetpub\wwwroot.
    #WebSitePhysicalPathAuth: 'Application User (Pass-through)' # 'WebSiteUserPassThrough' | 'WebSiteWindowsAuth'. Required when CreateWebSite = true. Physical Path Authentication. Default: Application User (Pass-through).
    #WebSiteAuthUserName: # string. Required when WebSitePhysicalPathAuth = WebSiteWindowsAuth. User Name. 
    #WebSiteAuthUserPassword: # string. Optional. Use when WebSitePhysicalPathAuth = WebSiteWindowsAuth. Password. 
    #AddBinding: true # boolean. Optional. Use when CreateWebSite = true. Add Binding. Default: true.
    #AssignDuplicateBinding: false # boolean. Optional. Use when AddBinding = true. Assign Duplicate Binding. Default: false.
    Protocol: 'http' # 'https' | 'http'. Required when AddBinding = true. Protocol. Default: http.
    IPAddress: 'All Unassigned' # string. Required when AddBinding = true. IP Address. Default: All Unassigned.
    Port: '80' # string. Required when AddBinding = true. Port. Default: 80.
    #ServerNameIndication: false # boolean. Optional. Use when Protocol = https. Server Name Indication Required. Default: false.
    #HostNameWithOutSNI: # string. Optional. Use when ServerNameIndication = false. Host Name. 
    #HostNameWithHttp: # string. Optional. Use when Protocol = http. Host Name. 
    #HostNameWithSNI: # string. Required when ServerNameIndication = true. Host Name. 
    #SSLCertThumbPrint: # string. Required when Protocol = https. SSL Certificate Thumb Print. 
  # Application Pool
    #CreateAppPool: false # boolean. Create or Update Application Pool. Default: false.
    #AppPoolName: # string. Required when CreateAppPool = true. Name. 
    #DotNetVersion: 'v4.0' # 'v4.0' | 'v2.0' | 'No Managed Code'. Required when CreateAppPool = true. .NET Version. Default: v4.0.
    #PipeLineMode: 'Integrated' # 'Integrated' | 'Classic'. Required when CreateAppPool = true. Managed Pipeline Mode. Default: Integrated.
    #AppPoolIdentity: 'ApplicationPoolIdentity' # 'ApplicationPoolIdentity' | 'LocalService' | 'LocalSystem' | 'NetworkService' | 'SpecificUser'. Required when CreateAppPool = true. Identity. Default: ApplicationPoolIdentity.
    #AppPoolUsername: # string. Required when AppPoolIdentity = SpecificUser. Username. 
    #AppPoolPassword: # string. Optional. Use when AppPoolIdentity = SpecificUser. Password. 
  # Advanced
    #AppCmdCommands: # string. Additional AppCmd.exe Commands. 
    #DeployInParallel: true # boolean. Deploy in Parallel. Default: true.
    #ResourceFilteringMethod: 'machineNames' # 'machineNames' | 'tags'. Select Machines By. Default: machineNames.
    #MachineFilter: # string. Deploy to Machines.
```

:::moniker-end

<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="EnvironmentName"::: -->
:::moniker range="<=azure-pipelines"

**`EnvironmentName`** - **Machines**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a comma-separated list of machine IP addresses or FQDNs, along with ports. The default port is based on the selected protocol, for example `dbserver.fabrikam.com` or `dbserver_int.fabrikam.com:5986,192.168.12.34:5986`. You can also provide the output variable of other tasks, for example `$(variableName)`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AdminUserName"::: -->
:::moniker range="<=azure-pipelines"

**`AdminUserName`** - **Admin Login**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the administrator login for the target machines.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AdminPassword"::: -->
:::moniker range="<=azure-pipelines"

**`AdminPassword`** - **Password**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the administrator password for the target machines. It can accept variables defined in build/release definitions, such as `$(passwordVariable)`. You may mark the variable type as `secret` to secure it.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="WinRMProtocol"::: -->
:::moniker range="<=azure-pipelines"

**`WinRMProtocol`** - **Protocol**<br>
`string`. Allowed values: `Http`, `Https`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the protocol used for the WinRM connection with the machine(s). The default is `HTTPS`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="TestCertificate"::: -->
:::moniker range="<=azure-pipelines"

**`TestCertificate`** - **Test Certificate**<br>
`boolean`. Optional. Use when `WinRMProtocol = Https`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selects the option to skip validating the authenticity of the machine's certificate by a trusted certification authority. The parameter is required for the WinRM `HTTPS` protocol.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="WebDeployPackage"::: -->
:::moniker range="<=azure-pipelines"

**`WebDeployPackage`** - **Web Deploy Package**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the location of the Web Deploy (MSDeploy) zip file on the target machines or on a UNC path like, `\\BudgetIT\WebDeploy\WebDeployPackage.zip`. The UNC path should be accessible to the machine's administrator account. Environment variables are also supported, like `$env:windir`, `$env:systemroot`, and `$env:windir\FabrikamFibre\Web`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="WebDeployParamFile"::: -->
:::moniker range="<=azure-pipelines"

**`WebDeployParamFile`** - **Web Deploy Parameter File**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the location of the parameter file on the target machines or on a UNC path. The parameter file is used to override Web application configuration settings, like the IIS Web application name or database connection string.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="OverRideParams"::: -->
:::moniker range="<=azure-pipelines"

**`OverRideParams`** - **Override Parameters**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Parameters specified here will override the parameters in the MSDeploy zip file and the parameter file. To override more than one parameter, use a line separator.  
For example, `"IIS Web Application Name"="Fabrikam"` or `"ConnectionString"="Server=localhost;Database=Fabrikam;"`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="CreateWebSite"::: -->
:::moniker range="<=azure-pipelines"

**`CreateWebSite`** - **Create or Update Website**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the option to create a website or to update an existing website.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="WebSiteName"::: -->
:::moniker range="<=azure-pipelines"

**`WebSiteName`** - **Website Name**<br>
`string`. Required when `CreateWebSite = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of the IIS website that will be created if it does not exist, or it will be updated if it is already present on the IIS server. The name of the website should be the same as that specified in the web deploy zip package file. If a parameter file and override parameters setting is also specified, then the name of the website should be the same as that in the override parameters setting.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="WebSitePhysicalPath"::: -->
:::moniker range="<=azure-pipelines"

**`WebSitePhysicalPath`** - **Physical Path**<br>
`string`. Required when `CreateWebSite = true`. Default value: `%SystemDrive%\inetpub\wwwroot`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the physical path where the website content is stored. The content can reside on the local computer or on a remote directory or share, like `C:\Fabrikam` or `\\ContentShare\Fabrikam`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="WebSitePhysicalPathAuth"::: -->
:::moniker range="<=azure-pipelines"

**`WebSitePhysicalPathAuth`** - **Physical Path Authentication**<br>
`string`. Required when `CreateWebSite = true`. Allowed values: `WebSiteUserPassThrough` (Application User (Pass-through)), `WebSiteWindowsAuth` (Windows Authentication). Default value: `Application User (Pass-through)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the authentication mechanism for accessing the physical path of the website.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="WebSiteAuthUserName"::: -->
:::moniker range="<=azure-pipelines"

**`WebSiteAuthUserName`** - **User Name**<br>
`string`. Required when `WebSitePhysicalPathAuth = WebSiteWindowsAuth`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the user name for accessing the website's physical path.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="WebSiteAuthUserPassword"::: -->
:::moniker range="<=azure-pipelines"

**`WebSiteAuthUserPassword`** - **Password**<br>
`string`. Optional. Use when `WebSitePhysicalPathAuth = WebSiteWindowsAuth`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the password for accessing the website's physical path. If you are using a gMSA, this is not required.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AddBinding"::: -->
:::moniker range="<=azure-pipelines"

**`AddBinding`** - **Add Binding**<br>
`boolean`. Optional. Use when `CreateWebSite = true`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the option to add port binding for the website.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AssignDuplicateBinding"::: -->
:::moniker range="<=azure-pipelines"

**`AssignDuplicateBinding`** - **Assign Duplicate Binding**<br>
`boolean`. Optional. Use when `AddBinding = true`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the option to add the bindings specified here (even if there is another website with the same bindings). If there are binding conflicts, only one of the websites will start.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Protocol"::: -->
:::moniker range="<=azure-pipelines"

**`Protocol`** - **Protocol**<br>
`string`. Required when `AddBinding = true`. Allowed values: `https`, `http`. Default value: `http`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies either HTTP for the website to have an HTTP binding or HTTPS for the website to have a Secure Sockets Layer (SSL) binding.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="IPAddress"::: -->
:::moniker range="<=azure-pipelines"

**`IPAddress`** - **IP Address**<br>
`string`. Required when `AddBinding = true`. Default value: `All Unassigned`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies an IP address that users can use to access the website. If **All Unassigned** is selected, the site will respond to requests for all IP addresses on the port and the optional host name that is specified for the site. The site will not respond to requests if another site on the server has a binding on the same port but with a specific IP address.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Port"::: -->
:::moniker range="<=azure-pipelines"

**`Port`** - **Port**<br>
`string`. Required when `AddBinding = true`. Default value: `80`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the port on which Hypertext Transfer Protocol Stack (HTTP.sys) must monitor for requests made to this website.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ServerNameIndication"::: -->
:::moniker range="<=azure-pipelines"

**`ServerNameIndication`** - **Server Name Indication Required**<br>
`boolean`. Optional. Use when `Protocol = https`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Determines whether the website requires Server Name Indication (SNI). SNI extends the SSL and TLS protocols to indicate what host name the client is attempting to connect to. It allows multiple secure websites with different certificates to use the same IP address.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="HostNameWithOutSNI"::: -->
:::moniker range="<=azure-pipelines"

**`HostNameWithOutSNI`** - **Host Name**<br>
`string`. Optional. Use when `ServerNameIndication = false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Assigns one or more host names (or domain names) to a computer that uses a single IP address. If a host name is specified then the clients must use the host name instead of the IP address to access the website.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="HostNameWithHttp"::: -->
:::moniker range="<=azure-pipelines"

**`HostNameWithHttp`** - **Host Name**<br>
`string`. Optional. Use when `Protocol = http`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Assigns one or more host names (or domain names) to a computer that uses a single IP address. If a host name is specified then the clients must use the host name instead of the IP address to access the website.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="HostNameWithSNI"::: -->
:::moniker range="<=azure-pipelines"

**`HostNameWithSNI`** - **Host Name**<br>
`string`. Required when `ServerNameIndication = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Assigns one or more host names (or domain names) to a computer that uses a single IP address. If a host name is specified then the clients must use the host name instead of the IP address to access the website.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SSLCertThumbPrint"::: -->
:::moniker range="<=azure-pipelines"

**`SSLCertThumbPrint`** - **SSL Certificate Thumb Print**<br>
`string`. Required when `Protocol = https`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the thumb-print of the Secure Socket Layer certificate that the website is going to use. The certificate should already be installed on the machine and present under the Local Computer Personal store.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="CreateAppPool"::: -->
:::moniker range="<=azure-pipelines"

**`CreateAppPool`** - **Create or Update Application Pool**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the option to create an application pool or to update an existing application pool.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AppPoolName"::: -->
:::moniker range="<=azure-pipelines"

**`AppPoolName`** - **Name**<br>
`string`. Required when `CreateAppPool = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of the IIS application pool to create or update. The existing application pool will be updated with the settings specified.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DotNetVersion"::: -->
:::moniker range="<=azure-pipelines"

**`DotNetVersion`** - **.NET Version**<br>
`string`. Required when `CreateAppPool = true`. Allowed values: `v4.0`, `v2.0`, `No Managed Code`. Default value: `v4.0`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the version of the .NET Framework that is loaded by this application pool. If the applications assigned to this application pool do not contain managed code, select the **No Managed Code** option from the list.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="PipeLineMode"::: -->
:::moniker range="<=azure-pipelines"

**`PipeLineMode`** - **Managed Pipeline Mode**<br>
`string`. Required when `CreateAppPool = true`. Allowed values: `Integrated`, `Classic`. Default value: `Integrated`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Managed pipeline mode specifies how IIS processes requests for managed content. Use classic mode only when the applications in the application pool cannot run in integrated mode.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AppPoolIdentity"::: -->
:::moniker range="<=azure-pipelines"

**`AppPoolIdentity`** - **Identity**<br>
`string`. Required when `CreateAppPool = true`. Allowed values: `ApplicationPoolIdentity`, `LocalService`, `LocalSystem`, `NetworkService`, `SpecificUser` (Custom Account). Default value: `ApplicationPoolIdentity`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Configures the account under which an application pool's worker process runs. Specify one of the predefined security accounts, or configure a custom account.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AppPoolUsername"::: -->
:::moniker range="<=azure-pipelines"

**`AppPoolUsername`** - **Username**<br>
`string`. Required when `AppPoolIdentity = SpecificUser`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AppPoolPassword"::: -->
:::moniker range="<=azure-pipelines"

**`AppPoolPassword`** - **Password**<br>
`string`. Optional. Use when `AppPoolIdentity = SpecificUser`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If you are using a gMSA, this is not required.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AppCmdCommands"::: -->
:::moniker range="<=azure-pipelines"

**`AppCmdCommands`** - **Additional AppCmd.exe Commands**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies additional `AppCmd.exe` commands to set the website or application pool properties. For more than one command, use a line separator.  
For example:  
\<list app pools\>  
\<list sites\>
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DeployInParallel"::: -->
:::moniker range="<=azure-pipelines"

**`DeployInParallel`** - **Deploy in Parallel**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If set to `true`, the Web application is deployed in-parallel on the target machines.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ResourceFilteringMethod"::: -->
:::moniker range="<=azure-pipelines"

**`ResourceFilteringMethod`** - **Select Machines By**<br>
`string`. Allowed values: `machineNames` (Machine Names), `tags`. Default value: `machineNames`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Specifies a subset of machines by providing machine names or tags.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="MachineFilter"::: -->
:::moniker range="<=azure-pipelines"

**`MachineFilter`** - **Deploy to Machines**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
This input is only valid for machine groups and is not supported for a flat list of machines or output variables yet.

Specifies a list of machines, like `dbserver.fabrikam.com, webserver.fabrikam.com, 192.168.12.34` or tags, like `Role:DB; OS:Win8.1`. If multiple tags are provided, the task will run in all of the machines with the specified tags. For Azure Resource Groups, specify the virtual machine's name, like `ffweb, ffdb`. The default runs the task in all machines.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range="<=azure-pipelines"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

> [!IMPORTANT]
> This task is deprecated. Use [IIS Web App Deployment Using WinRM - Viual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=ms-vscs-rm.iiswebapp).
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range="<=azure-pipelines"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.91.0 or greater |
| Task category | Deploy |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
