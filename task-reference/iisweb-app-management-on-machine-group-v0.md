---
title: IISWebAppManagementOnMachineGroup@0 - IIS web app manage v0 task
description: Create or update websites, web apps, virtual directories, or application pools.
ms.date: 09/26/2023
monikerRange: "<=azure-pipelines"
---

# IISWebAppManagementOnMachineGroup@0 - IIS web app manage v0 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to create or update websites, web apps, virtual directories, or application pools.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# IIS web app manage v0
# Create or update websites, web apps, virtual directories, or application pools.
- task: IISWebAppManagementOnMachineGroup@0
  inputs:
    #EnableIIS: false # boolean. Enable IIS. Default: false.
    IISDeploymentType: 'IISWebsite' # 'IISWebsite' | 'IISWebApplication' | 'IISVirtualDirectory' | 'IISApplicationPool'. Required. Configuration type. Default: IISWebsite.
    ActionIISWebsite: 'CreateOrUpdateWebsite' # 'CreateOrUpdateWebsite' | 'StartWebsite' | 'StopWebsite'. Required when IISDeploymentType = IISWebsite. Action. Default: CreateOrUpdateWebsite.
    #ActionIISApplicationPool: 'CreateOrUpdateAppPool' # 'CreateOrUpdateAppPool' | 'StartAppPool' | 'StopAppPool' | 'RecycleAppPool'. Required when IISDeploymentType = IISApplicationPool. Action. Default: CreateOrUpdateAppPool.
    #StartStopWebsiteName: # string. Required when ActionIISWebsite = StartWebsite || ActionIISWebsite = StopWebsite. Website name. 
    #Protocol: 'http' # 'https' | 'http'. Required when IISDeploymentType = randomDeployment. Protocol. Default: http.
    #IPAddress: 'All Unassigned' # string. Required when IISDeploymentType = randomDeployment. IP address. Default: All Unassigned.
    #Port: '80' # string. Required when IISDeploymentType = randomDeployment. Port. Default: 80.
    #ServerNameIndication: false # boolean. Optional. Use when IISDeploymentType = randomDeployment. Server Name Indication required. Default: false.
    #HostNameWithOutSNI: # string. Optional. Use when IISDeploymentType = randomDeployment. Host name. 
    #HostNameWithHttp: # string. Optional. Use when IISDeploymentType = randomDeployment. Host name. 
    #HostNameWithSNI: # string. Required when IISDeploymentType = randomDeployment. Host name. 
    #SSLCertThumbPrint: # string. Required when IISDeploymentType = randomDeployment. SSL certificate thumbprint. 
    #StartStopRecycleAppPoolName: # string. Required when ActionIISApplicationPool = StartAppPool || ActionIISApplicationPool = StopAppPool || ActionIISApplicationPool = RecycleAppPool. Application pool name. 
  # IIS Website
    WebsiteName: # string. Required when ActionIISWebsite = CreateOrUpdateWebsite. Website name. 
    WebsitePhysicalPath: '%SystemDrive%\inetpub\wwwroot' # string. Required when ActionIISWebsite = CreateOrUpdateWebsite. Physical path. Default: %SystemDrive%\inetpub\wwwroot.
    WebsitePhysicalPathAuth: 'WebsiteUserPassThrough' # 'WebsiteUserPassThrough' | 'WebsiteWindowsAuth'. Required when ActionIISWebsite = CreateOrUpdateWebsite. Physical path authentication. Default: WebsiteUserPassThrough.
    #WebsiteAuthUserName: # string. Required when WebsitePhysicalPathAuth = WebsiteWindowsAuth && ActionIISWebsite = CreateOrUpdateWebsite. Username. 
    #WebsiteAuthUserPassword: # string. Optional. Use when WebsitePhysicalPathAuth = WebsiteWindowsAuth && ActionIISWebsite = CreateOrUpdateWebsite. Password. 
    #AddBinding: false # boolean. Optional. Use when ActionIISWebsite = CreateOrUpdateWebsite. Add binding. Default: false.
    #CreateOrUpdateAppPoolForWebsite: false # boolean. Optional. Use when ActionIISWebsite = CreateOrUpdateWebsite. Create or update app pool. Default: false.
    #ConfigureAuthenticationForWebsite: false # boolean. Optional. Use when ActionIISWebsite = CreateOrUpdateWebsite. Configure authentication. Default: false.
  # IIS Bindings
    #Bindings: # string. Required when IISDeploymentType = IISWebsite && ActionIISWebsite = CreateOrUpdateWebsite && AddBinding = true. Add bindings. 
  # IIS Application pool
    #AppPoolNameForWebsite: # string. Required when IISDeploymentType = IISWebsite && ActionIISWebsite = CreateOrUpdateWebsite && CreateOrUpdateAppPoolForWebsite = true. Name. 
    #DotNetVersionForWebsite: 'v4.0' # 'v4.0' | 'v2.0' | 'No Managed Code'. Required when IISDeploymentType = IISWebsite && ActionIISWebsite = CreateOrUpdateWebsite && CreateOrUpdateAppPoolForWebsite = true. .NET version. Default: v4.0.
    #PipeLineModeForWebsite: 'Integrated' # 'Integrated' | 'Classic'. Required when IISDeploymentType = IISWebsite && ActionIISWebsite = CreateOrUpdateWebsite && CreateOrUpdateAppPoolForWebsite = true. Managed pipeline mode. Default: Integrated.
    #AppPoolIdentityForWebsite: 'ApplicationPoolIdentity' # 'ApplicationPoolIdentity' | 'LocalService' | 'LocalSystem' | 'NetworkService' | 'SpecificUser'. Required when IISDeploymentType = IISWebsite && ActionIISWebsite = CreateOrUpdateWebsite && CreateOrUpdateAppPoolForWebsite = true. Identity. Default: ApplicationPoolIdentity.
    #AppPoolUsernameForWebsite: # string. Required when AppPoolIdentityForWebsite = SpecificUser && IISDeploymentType = IISWebsite && ActionIISWebsite = CreateOrUpdateWebsite && CreateOrUpdateAppPoolForWebsite = true. Username. 
    #AppPoolPasswordForWebsite: # string. Optional. Use when AppPoolIdentityForWebsite = SpecificUser && IISDeploymentType = IISWebsite && ActionIISWebsite = CreateOrUpdateWebsite && CreateOrUpdateAppPoolForWebsite = true. Password. 
  # IIS Authentication
    #AnonymousAuthenticationForWebsite: false # boolean. Optional. Use when IISDeploymentType = IISWebsite && ActionIISWebsite = CreateOrUpdateWebsite && ConfigureAuthenticationForWebsite = true. Anonymous authentication. Default: false.
    #BasicAuthenticationForWebsite: false # boolean. Optional. Use when IISDeploymentType = IISWebsite && ActionIISWebsite = CreateOrUpdateWebsite && ConfigureAuthenticationForWebsite = true. Basic authentication. Default: false.
    #WindowsAuthenticationForWebsite: true # boolean. Optional. Use when IISDeploymentType = IISWebsite && ActionIISWebsite = CreateOrUpdateWebsite && ConfigureAuthenticationForWebsite = true. Windows authentication. Default: true.
  # IIS Virtual directory
    #ParentWebsiteNameForVD: # string. Required when IISDeploymentType = IISVirtualDirectory. Parent website name. 
    #VirtualPathForVD: # string. Required when IISDeploymentType = IISVirtualDirectory. Virtual path. 
    #PhysicalPathForVD: '%SystemDrive%\inetpub\wwwroot' # string. Required when IISDeploymentType = IISVirtualDirectory. Physical path. Default: %SystemDrive%\inetpub\wwwroot.
    #VDPhysicalPathAuth: 'VDUserPassThrough' # 'VDUserPassThrough' | 'VDWindowsAuth'. Optional. Use when IISDeploymentType = IISVirtualDirectory. Physical path authentication. Default: VDUserPassThrough.
    #VDAuthUserName: # string. Required when VDPhysicalPathAuth = VDWindowsAuth && IISDeploymentType = IISVirtualDirectory. Username. 
    #VDAuthUserPassword: # string. Optional. Use when VDPhysicalPathAuth = VDWindowsAuth && IISDeploymentType = IISVirtualDirectory. Password. 
  # IIS Application
    #ParentWebsiteNameForApplication: # string. Required when IISDeploymentType = IISWebApplication. Parent website name. 
    #VirtualPathForApplication: # string. Required when IISDeploymentType = IISWebApplication. Virtual path. 
    #PhysicalPathForApplication: '%SystemDrive%\inetpub\wwwroot' # string. Required when IISDeploymentType = IISWebApplication. Physical path. Default: %SystemDrive%\inetpub\wwwroot.
    #ApplicationPhysicalPathAuth: 'ApplicationUserPassThrough' # 'ApplicationUserPassThrough' | 'ApplicationWindowsAuth'. Optional. Use when IISDeploymentType = IISWebApplication. Physical path authentication. Default: ApplicationUserPassThrough.
    #ApplicationAuthUserName: # string. Required when ApplicationPhysicalPathAuth = ApplicationWindowsAuth && IISDeploymentType = IISWebApplication. Username. 
    #ApplicationAuthUserPassword: # string. Optional. Use when ApplicationPhysicalPathAuth = ApplicationWindowsAuth && IISDeploymentType = IISWebApplication. Password. 
    #CreateOrUpdateAppPoolForApplication: false # boolean. Optional. Use when IISDeploymentType = IISWebApplication. Create or update app pool. Default: false.
  # IIS Application pool
    #AppPoolNameForApplication: # string. Required when IISDeploymentType = IISWebApplication && CreateOrUpdateAppPoolForApplication = true. Name. 
    #DotNetVersionForApplication: 'v4.0' # 'v4.0' | 'v2.0' | 'No Managed Code'. Required when IISDeploymentType = IISWebApplication && CreateOrUpdateAppPoolForApplication = true. .NET version. Default: v4.0.
    #PipeLineModeForApplication: 'Integrated' # 'Integrated' | 'Classic'. Required when IISDeploymentType = IISWebApplication && CreateOrUpdateAppPoolForApplication = true. Managed pipeline mode. Default: Integrated.
    #AppPoolIdentityForApplication: 'ApplicationPoolIdentity' # 'ApplicationPoolIdentity' | 'LocalService' | 'LocalSystem' | 'NetworkService' | 'SpecificUser'. Required when IISDeploymentType = IISWebApplication && CreateOrUpdateAppPoolForApplication = true. Identity. Default: ApplicationPoolIdentity.
    #AppPoolUsernameForApplication: # string. Required when AppPoolIdentityForApplication = SpecificUser && IISDeploymentType = IISWebApplication && CreateOrUpdateAppPoolForApplication = true. Username. 
    #AppPoolPasswordForApplication: # string. Optional. Use when AppPoolIdentityForApplication = SpecificUser && IISDeploymentType = IISWebApplication && CreateOrUpdateAppPoolForApplication = true. Password. 
  # IIS Application pool
    AppPoolName: # string. Required when ActionIISApplicationPool = CreateOrUpdateAppPool. Name. 
    DotNetVersion: 'v4.0' # 'v4.0' | 'v2.0' | 'No Managed Code'. Required when ActionIISApplicationPool = CreateOrUpdateAppPool. .NET version. Default: v4.0.
    PipeLineMode: 'Integrated' # 'Integrated' | 'Classic'. Required when ActionIISApplicationPool = CreateOrUpdateAppPool. Managed pipeline mode. Default: Integrated.
    AppPoolIdentity: 'ApplicationPoolIdentity' # 'ApplicationPoolIdentity' | 'LocalService' | 'LocalSystem' | 'NetworkService' | 'SpecificUser'. Required when ActionIISApplicationPool = CreateOrUpdateAppPool. Identity. Default: ApplicationPoolIdentity.
    #AppPoolUsername: # string. Required when AppPoolIdentity = SpecificUser && ActionIISApplicationPool = CreateOrUpdateAppPool. Username. 
    #AppPoolPassword: # string. Optional. Use when AppPoolIdentity = SpecificUser && ActionIISApplicationPool = CreateOrUpdateAppPool. Password. 
  # Advanced
    #AppCmdCommands: # string. Additional appcmd.exe commands.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# IIS Web App Manage v0
# Create or update a Website, Web App, Virtual Directories, and Application Pool.
- task: IISWebAppManagementOnMachineGroup@0
  inputs:
    #EnableIIS: false # boolean. Enable IIS. Default: false.
    IISDeploymentType: 'IISWebsite' # 'IISWebsite' | 'IISWebApplication' | 'IISVirtualDirectory' | 'IISApplicationPool'. Required. Configuration type. Default: IISWebsite.
    ActionIISWebsite: 'CreateOrUpdateWebsite' # 'CreateOrUpdateWebsite' | 'StartWebsite' | 'StopWebsite'. Required when IISDeploymentType = IISWebsite. Action. Default: CreateOrUpdateWebsite.
    #ActionIISApplicationPool: 'CreateOrUpdateAppPool' # 'CreateOrUpdateAppPool' | 'StartAppPool' | 'StopAppPool' | 'RecycleAppPool'. Required when IISDeploymentType = IISApplicationPool. Action. Default: CreateOrUpdateAppPool.
    #StartStopWebsiteName: # string. Required when ActionIISWebsite = StartWebsite || ActionIISWebsite = StopWebsite. Website name. 
    #Protocol: 'http' # 'https' | 'http'. Required when IISDeploymentType = randomDeployment. Protocol. Default: http.
    #IPAddress: 'All Unassigned' # string. Required when IISDeploymentType = randomDeployment. IP address. Default: All Unassigned.
    #Port: '80' # string. Required when IISDeploymentType = randomDeployment. Port. Default: 80.
    #ServerNameIndication: false # boolean. Optional. Use when IISDeploymentType = randomDeployment. Server Name Indication required. Default: false.
    #HostNameWithOutSNI: # string. Optional. Use when IISDeploymentType = randomDeployment. Host name. 
    #HostNameWithHttp: # string. Optional. Use when IISDeploymentType = randomDeployment. Host name. 
    #HostNameWithSNI: # string. Required when IISDeploymentType = randomDeployment. Host name. 
    #SSLCertThumbPrint: # string. Required when IISDeploymentType = randomDeployment. SSL certificate thumbprint. 
    #StartStopRecycleAppPoolName: # string. Required when ActionIISApplicationPool = StartAppPool || ActionIISApplicationPool = StopAppPool || ActionIISApplicationPool = RecycleAppPool. Application pool name. 
  # IIS Website
    WebsiteName: # string. Required when ActionIISWebsite = CreateOrUpdateWebsite. Website name. 
    WebsitePhysicalPath: '%SystemDrive%\inetpub\wwwroot' # string. Required when ActionIISWebsite = CreateOrUpdateWebsite. Physical path. Default: %SystemDrive%\inetpub\wwwroot.
    WebsitePhysicalPathAuth: 'WebsiteUserPassThrough' # 'WebsiteUserPassThrough' | 'WebsiteWindowsAuth'. Required when ActionIISWebsite = CreateOrUpdateWebsite. Physical path authentication. Default: WebsiteUserPassThrough.
    #WebsiteAuthUserName: # string. Required when WebsitePhysicalPathAuth = WebsiteWindowsAuth && ActionIISWebsite = CreateOrUpdateWebsite. Username. 
    #WebsiteAuthUserPassword: # string. Optional. Use when WebsitePhysicalPathAuth = WebsiteWindowsAuth && ActionIISWebsite = CreateOrUpdateWebsite. Password. 
    #AddBinding: false # boolean. Optional. Use when ActionIISWebsite = CreateOrUpdateWebsite. Add binding. Default: false.
    #CreateOrUpdateAppPoolForWebsite: false # boolean. Optional. Use when ActionIISWebsite = CreateOrUpdateWebsite. Create or update app pool. Default: false.
    #ConfigureAuthenticationForWebsite: false # boolean. Optional. Use when ActionIISWebsite = CreateOrUpdateWebsite. Configure authentication. Default: false.
  # IIS Bindings
    #Bindings: # string. Required when IISDeploymentType = IISWebsite && ActionIISWebsite = CreateOrUpdateWebsite && AddBinding = true. Add bindings. 
  # IIS Application pool
    #AppPoolNameForWebsite: # string. Required when IISDeploymentType = IISWebsite && ActionIISWebsite = CreateOrUpdateWebsite && CreateOrUpdateAppPoolForWebsite = true. Name. 
    #DotNetVersionForWebsite: 'v4.0' # 'v4.0' | 'v2.0' | 'No Managed Code'. Required when IISDeploymentType = IISWebsite && ActionIISWebsite = CreateOrUpdateWebsite && CreateOrUpdateAppPoolForWebsite = true. .NET version. Default: v4.0.
    #PipeLineModeForWebsite: 'Integrated' # 'Integrated' | 'Classic'. Required when IISDeploymentType = IISWebsite && ActionIISWebsite = CreateOrUpdateWebsite && CreateOrUpdateAppPoolForWebsite = true. Managed pipeline mode. Default: Integrated.
    #AppPoolIdentityForWebsite: 'ApplicationPoolIdentity' # 'ApplicationPoolIdentity' | 'LocalService' | 'LocalSystem' | 'NetworkService' | 'SpecificUser'. Required when IISDeploymentType = IISWebsite && ActionIISWebsite = CreateOrUpdateWebsite && CreateOrUpdateAppPoolForWebsite = true. Identity. Default: ApplicationPoolIdentity.
    #AppPoolUsernameForWebsite: # string. Required when AppPoolIdentityForWebsite = SpecificUser && IISDeploymentType = IISWebsite && ActionIISWebsite = CreateOrUpdateWebsite && CreateOrUpdateAppPoolForWebsite = true. Username. 
    #AppPoolPasswordForWebsite: # string. Optional. Use when AppPoolIdentityForWebsite = SpecificUser && IISDeploymentType = IISWebsite && ActionIISWebsite = CreateOrUpdateWebsite && CreateOrUpdateAppPoolForWebsite = true. Password. 
  # IIS Authentication
    #AnonymousAuthenticationForWebsite: false # boolean. Optional. Use when IISDeploymentType = IISWebsite && ActionIISWebsite = CreateOrUpdateWebsite && ConfigureAuthenticationForWebsite = true. Anonymous authentication. Default: false.
    #BasicAuthenticationForWebsite: false # boolean. Optional. Use when IISDeploymentType = IISWebsite && ActionIISWebsite = CreateOrUpdateWebsite && ConfigureAuthenticationForWebsite = true. Basic authentication. Default: false.
    #WindowsAuthenticationForWebsite: true # boolean. Optional. Use when IISDeploymentType = IISWebsite && ActionIISWebsite = CreateOrUpdateWebsite && ConfigureAuthenticationForWebsite = true. Windows authentication. Default: true.
  # IIS Virtual directory
    #ParentWebsiteNameForVD: # string. Required when IISDeploymentType = IISVirtualDirectory. Parent website name. 
    #VirtualPathForVD: # string. Required when IISDeploymentType = IISVirtualDirectory. Virtual path. 
    #PhysicalPathForVD: '%SystemDrive%\inetpub\wwwroot' # string. Required when IISDeploymentType = IISVirtualDirectory. Physical path. Default: %SystemDrive%\inetpub\wwwroot.
    #VDPhysicalPathAuth: 'VDUserPassThrough' # 'VDUserPassThrough' | 'VDWindowsAuth'. Optional. Use when IISDeploymentType = IISVirtualDirectory. Physical path authentication. Default: VDUserPassThrough.
    #VDAuthUserName: # string. Required when VDPhysicalPathAuth = VDWindowsAuth && IISDeploymentType = IISVirtualDirectory. Username. 
    #VDAuthUserPassword: # string. Optional. Use when VDPhysicalPathAuth = VDWindowsAuth && IISDeploymentType = IISVirtualDirectory. Password. 
  # IIS Application
    #ParentWebsiteNameForApplication: # string. Required when IISDeploymentType = IISWebApplication. Parent website name. 
    #VirtualPathForApplication: # string. Required when IISDeploymentType = IISWebApplication. Virtual path. 
    #PhysicalPathForApplication: '%SystemDrive%\inetpub\wwwroot' # string. Required when IISDeploymentType = IISWebApplication. Physical path. Default: %SystemDrive%\inetpub\wwwroot.
    #ApplicationPhysicalPathAuth: 'ApplicationUserPassThrough' # 'ApplicationUserPassThrough' | 'ApplicationWindowsAuth'. Optional. Use when IISDeploymentType = IISWebApplication. Physical path authentication. Default: ApplicationUserPassThrough.
    #ApplicationAuthUserName: # string. Required when ApplicationPhysicalPathAuth = ApplicationWindowsAuth && IISDeploymentType = IISWebApplication. Username. 
    #ApplicationAuthUserPassword: # string. Optional. Use when ApplicationPhysicalPathAuth = ApplicationWindowsAuth && IISDeploymentType = IISWebApplication. Password. 
    #CreateOrUpdateAppPoolForApplication: false # boolean. Optional. Use when IISDeploymentType = IISWebApplication. Create or update app pool. Default: false.
  # IIS Application pool
    #AppPoolNameForApplication: # string. Required when IISDeploymentType = IISWebApplication && CreateOrUpdateAppPoolForApplication = true. Name. 
    #DotNetVersionForApplication: 'v4.0' # 'v4.0' | 'v2.0' | 'No Managed Code'. Required when IISDeploymentType = IISWebApplication && CreateOrUpdateAppPoolForApplication = true. .NET version. Default: v4.0.
    #PipeLineModeForApplication: 'Integrated' # 'Integrated' | 'Classic'. Required when IISDeploymentType = IISWebApplication && CreateOrUpdateAppPoolForApplication = true. Managed pipeline mode. Default: Integrated.
    #AppPoolIdentityForApplication: 'ApplicationPoolIdentity' # 'ApplicationPoolIdentity' | 'LocalService' | 'LocalSystem' | 'NetworkService' | 'SpecificUser'. Required when IISDeploymentType = IISWebApplication && CreateOrUpdateAppPoolForApplication = true. Identity. Default: ApplicationPoolIdentity.
    #AppPoolUsernameForApplication: # string. Required when AppPoolIdentityForApplication = SpecificUser && IISDeploymentType = IISWebApplication && CreateOrUpdateAppPoolForApplication = true. Username. 
    #AppPoolPasswordForApplication: # string. Optional. Use when AppPoolIdentityForApplication = SpecificUser && IISDeploymentType = IISWebApplication && CreateOrUpdateAppPoolForApplication = true. Password. 
  # IIS Application pool
    AppPoolName: # string. Required when ActionIISApplicationPool = CreateOrUpdateAppPool. Name. 
    DotNetVersion: 'v4.0' # 'v4.0' | 'v2.0' | 'No Managed Code'. Required when ActionIISApplicationPool = CreateOrUpdateAppPool. .NET version. Default: v4.0.
    PipeLineMode: 'Integrated' # 'Integrated' | 'Classic'. Required when ActionIISApplicationPool = CreateOrUpdateAppPool. Managed pipeline mode. Default: Integrated.
    AppPoolIdentity: 'ApplicationPoolIdentity' # 'ApplicationPoolIdentity' | 'LocalService' | 'LocalSystem' | 'NetworkService' | 'SpecificUser'. Required when ActionIISApplicationPool = CreateOrUpdateAppPool. Identity. Default: ApplicationPoolIdentity.
    #AppPoolUsername: # string. Required when AppPoolIdentity = SpecificUser && ActionIISApplicationPool = CreateOrUpdateAppPool. Username. 
    #AppPoolPassword: # string. Optional. Use when AppPoolIdentity = SpecificUser && ActionIISApplicationPool = CreateOrUpdateAppPool. Password. 
  # Advanced
    #AppCmdCommands: # string. Additional appcmd.exe commands.
```

:::moniker-end

:::moniker range="=azure-pipelines-2018"

```yaml
# YAML Syntax is not supported in TFS 2018.
# Use the classic designer to add and configure tasks.
# See the following Inputs section for details on the inputs that this task supports.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="EnableIIS"::: -->
:::moniker range="<=azure-pipelines"

**`EnableIIS`** - **Enable IIS**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Set to `true` if you want to install IIS on the machine.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="IISDeploymentType"::: -->
:::moniker range="<=azure-pipelines"

**`IISDeploymentType`** - **Configuration type**<br>
`string`. Required. Allowed values: `IISWebsite` (IIS Website), `IISWebApplication` (IIS Web Application), `IISVirtualDirectory` (IIS Virtual Directory), `IISApplicationPool` (IIS Application Pool). Default value: `IISWebsite`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the configuration type: website, web application, virtual directory, or application pool.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ActionIISWebsite"::: -->
:::moniker range="<=azure-pipelines"

**`ActionIISWebsite`** - **Action**<br>
`string`. Required when `IISDeploymentType = IISWebsite`. Allowed values: `CreateOrUpdateWebsite` (Create Or Update), `StartWebsite` (Start), `StopWebsite` (Stop). Default value: `CreateOrUpdateWebsite`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the appropriate action that you want to perform on an IIS website.

**Create Or Update** will create a website or update an existing website.

**Start, Stop** will start or stop the website respectively.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ActionIISApplicationPool"::: -->
:::moniker range="<=azure-pipelines"

**`ActionIISApplicationPool`** - **Action**<br>
`string`. Required when `IISDeploymentType = IISApplicationPool`. Allowed values: `CreateOrUpdateAppPool` (Create Or Update), `StartAppPool` (Start), `StopAppPool` (Stop), `RecycleAppPool` (Recycle). Default value: `CreateOrUpdateAppPool`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the appropriate action that you want to perform on an IIS application pool.

**Create Or Update** will create an application pool or update an existing application pool.

**Start, Stop, Recycle** will start, stop or recycle the application pool respectively.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="StartStopWebsiteName"::: -->
:::moniker range="<=azure-pipelines"

**`StartStopWebsiteName`** - **Website name**<br>
`string`. Required when `ActionIISWebsite = StartWebsite || ActionIISWebsite = StopWebsite`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of the IIS website.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="WebsiteName"::: -->
:::moniker range="<=azure-pipelines"

**`WebsiteName`** - **Website name**<br>
`string`. Required when `ActionIISWebsite = CreateOrUpdateWebsite`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of the IIS website to create or update.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="WebsitePhysicalPath"::: -->
:::moniker range="<=azure-pipelines"

**`WebsitePhysicalPath`** - **Physical path**<br>
`string`. Required when `ActionIISWebsite = CreateOrUpdateWebsite`. Default value: `%SystemDrive%\inetpub\wwwroot`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the physical path where the website content will be stored. The content can reside on the local computer, in a remote directory, or on a network share, like `C:\Fabrikam` or `\\ContentShare\Fabrikam`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="WebsitePhysicalPathAuth"::: -->
:::moniker range="<=azure-pipelines"

**`WebsitePhysicalPathAuth`** - **Physical path authentication**<br>
`string`. Required when `ActionIISWebsite = CreateOrUpdateWebsite`. Allowed values: `WebsiteUserPassThrough` (Application User (Pass-through)), `WebsiteWindowsAuth` (Windows Authentication). Default value: `WebsiteUserPassThrough`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the authentication mechanism that will be used to access the physical path of the website.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="WebsiteAuthUserName"::: -->
:::moniker range="<=azure-pipelines"

**`WebsiteAuthUserName`** - **Username**<br>
`string`. Required when `WebsitePhysicalPathAuth = WebsiteWindowsAuth && ActionIISWebsite = CreateOrUpdateWebsite`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the user name that will be used to access the website's physical path.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="WebsiteAuthUserPassword"::: -->
:::moniker range="<=azure-pipelines"

**`WebsiteAuthUserPassword`** - **Password**<br>
`string`. Optional. Use when `WebsitePhysicalPathAuth = WebsiteWindowsAuth && ActionIISWebsite = CreateOrUpdateWebsite`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the user's password that will be used to access the website's physical path.  
The best practice is to create a variable in the build or release pipeline, mark it as `Secret` to secure it, and then provide it when using this input, like `$(userCredentials)`.  
*Note:* Special characters in the password are interpreted per [command-line arguments](/cpp/c-language/parsing-c-command-line-arguments).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AddBinding"::: -->
:::moniker range="<=azure-pipelines"

**`AddBinding`** - **Add binding**<br>
`boolean`. Optional. Use when `ActionIISWebsite = CreateOrUpdateWebsite`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the option to add port binding for the website.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Protocol"::: -->
:::moniker range="<=azure-pipelines"

**`Protocol`** - **Protocol**<br>
`string`. Required when `IISDeploymentType = randomDeployment`. Allowed values: `https`, `http`. Default value: `http`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies either HTTP for the website to have an HTTP binding or HTTPS for the website to have a Secure Sockets Layer (SSL) binding.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="IPAddress"::: -->
:::moniker range="<=azure-pipelines"

**`IPAddress`** - **IP address**<br>
`string`. Required when `IISDeploymentType = randomDeployment`. Default value: `All Unassigned`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies an IP address that end-users can use to access this website.  
If **All Unassigned** is selected, then the website will respond to requests for all IP addresses on the port and for the host name. The website will not respond to requests if another website on the server has a binding on the same port but with a specific IP address.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Port"::: -->
:::moniker range="<=azure-pipelines"

**`Port`** - **Port**<br>
`string`. Required when `IISDeploymentType = randomDeployment`. Default value: `80`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the port where the Hypertext Transfer Protocol Stack (HTTP.sys) will monitor the website requests.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ServerNameIndication"::: -->
:::moniker range="<=azure-pipelines"

**`ServerNameIndication`** - **Server Name Indication required**<br>
`boolean`. Optional. Use when `IISDeploymentType = randomDeployment`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the option to set the Server Name Indication (SNI) for the website.  
SNI extends the SSL and TLS protocols to indicate the host name that the clients are attempting to connect to. It allows multiple secure websites with different certificates to use the same IP address.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="HostNameWithOutSNI"::: -->
:::moniker range="<=azure-pipelines"

**`HostNameWithOutSNI`** - **Host name**<br>
`string`. Optional. Use when `IISDeploymentType = randomDeployment`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a host name (or domain name) for the website.  
If a host name is specified, the clients must use the host name instead of the IP address to access the website.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="HostNameWithHttp"::: -->
:::moniker range="<=azure-pipelines"

**`HostNameWithHttp`** - **Host name**<br>
`string`. Optional. Use when `IISDeploymentType = randomDeployment`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a host name (or domain name) for the website.  
If a host name is specified, the clients must use the host name instead of the IP address to access the website.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="HostNameWithSNI"::: -->
:::moniker range="<=azure-pipelines"

**`HostNameWithSNI`** - **Host name**<br>
`string`. Required when `IISDeploymentType = randomDeployment`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a host name (or domain name) for the website.  
If a host name is specified, the clients must use the host name instead of the IP address to access the website.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SSLCertThumbPrint"::: -->
:::moniker range="<=azure-pipelines"

**`SSLCertThumbPrint`** - **SSL certificate thumbprint**<br>
`string`. Required when `IISDeploymentType = randomDeployment`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the thumb-print of the Secure Socket Layer certificate that the website uses for the HTTPS communication. The thumb-print is a 40 character long hexadecimal string. The SSL certificate should already be installed on the computer in the Local Computer Personal store.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Bindings"::: -->
:::moniker range="<=azure-pipelines"

**`Bindings`** - **Add bindings**<br>
`string`. Required when `IISDeploymentType = IISWebsite && ActionIISWebsite = CreateOrUpdateWebsite && AddBinding = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Click on the extension button `...` to add bindings for the website.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="CreateOrUpdateAppPoolForWebsite"::: -->
:::moniker range="<=azure-pipelines"

**`CreateOrUpdateAppPoolForWebsite`** - **Create or update app pool**<br>
`boolean`. Optional. Use when `ActionIISWebsite = CreateOrUpdateWebsite`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the option to create or update an application pool. If checked, the website will be created in the specified application pool.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ConfigureAuthenticationForWebsite"::: -->
:::moniker range="<=azure-pipelines"

**`ConfigureAuthenticationForWebsite`** - **Configure authentication**<br>
`boolean`. Optional. Use when `ActionIISWebsite = CreateOrUpdateWebsite`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the option to configure authentication for the website.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AppPoolNameForWebsite"::: -->
:::moniker range="<=azure-pipelines"

**`AppPoolNameForWebsite`** - **Name**<br>
`string`. Required when `IISDeploymentType = IISWebsite && ActionIISWebsite = CreateOrUpdateWebsite && CreateOrUpdateAppPoolForWebsite = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of the IIS application pool to create or update.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DotNetVersionForWebsite"::: -->
:::moniker range="<=azure-pipelines"

**`DotNetVersionForWebsite`** - **.NET version**<br>
`string`. Required when `IISDeploymentType = IISWebsite && ActionIISWebsite = CreateOrUpdateWebsite && CreateOrUpdateAppPoolForWebsite = true`. Allowed values: `v4.0`, `v2.0`, `No Managed Code`. Default value: `v4.0`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the version of the .NET Framework that is loaded by the application pool. If the applications assigned to this application pool do not contain managed code, select the **No Managed Code** option from the list.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="PipeLineModeForWebsite"::: -->
:::moniker range="<=azure-pipelines"

**`PipeLineModeForWebsite`** - **Managed pipeline mode**<br>
`string`. Required when `IISDeploymentType = IISWebsite && ActionIISWebsite = CreateOrUpdateWebsite && CreateOrUpdateAppPoolForWebsite = true`. Allowed values: `Integrated`, `Classic`. Default value: `Integrated`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the managed pipeline mode to determine how IIS processes requests for managed content. Use classic mode only when the applications in the application pool cannot run in integrated mode.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AppPoolIdentityForWebsite"::: -->
:::moniker range="<=azure-pipelines"

**`AppPoolIdentityForWebsite`** - **Identity**<br>
`string`. Required when `IISDeploymentType = IISWebsite && ActionIISWebsite = CreateOrUpdateWebsite && CreateOrUpdateAppPoolForWebsite = true`. Allowed values: `ApplicationPoolIdentity` (Application Pool Identity), `LocalService` (Local Service), `LocalSystem` (Local System), `NetworkService` (Network Service), `SpecificUser` (Custom Account). Default value: `ApplicationPoolIdentity`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Configures the account under which an application pool's worker process runs. Specifies one of the predefined security accounts or configures a custom account.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AppPoolUsernameForWebsite"::: -->
:::moniker range="<=azure-pipelines"

**`AppPoolUsernameForWebsite`** - **Username**<br>
`string`. Required when `AppPoolIdentityForWebsite = SpecificUser && IISDeploymentType = IISWebsite && ActionIISWebsite = CreateOrUpdateWebsite && CreateOrUpdateAppPoolForWebsite = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the username of the custom account that you want to use.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AppPoolPasswordForWebsite"::: -->
:::moniker range="<=azure-pipelines"

**`AppPoolPasswordForWebsite`** - **Password**<br>
`string`. Optional. Use when `AppPoolIdentityForWebsite = SpecificUser && IISDeploymentType = IISWebsite && ActionIISWebsite = CreateOrUpdateWebsite && CreateOrUpdateAppPoolForWebsite = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the password for the custom account.  
The best practice is to create a variable in the build or release pipeline, mark it as `Secret` to secure it, and then provide it when using this input, like `$(userCredentials)`.  
*Note:* Special characters in the password are interpreted per [command-line arguments](/cpp/c-language/parsing-c-command-line-arguments).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AnonymousAuthenticationForWebsite"::: -->
:::moniker range="<=azure-pipelines"

**`AnonymousAuthenticationForWebsite`** - **Anonymous authentication**<br>
`boolean`. Optional. Use when `IISDeploymentType = IISWebsite && ActionIISWebsite = CreateOrUpdateWebsite && ConfigureAuthenticationForWebsite = true`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the option to enable anonymous authentication for a website.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="BasicAuthenticationForWebsite"::: -->
:::moniker range="<=azure-pipelines"

**`BasicAuthenticationForWebsite`** - **Basic authentication**<br>
`boolean`. Optional. Use when `IISDeploymentType = IISWebsite && ActionIISWebsite = CreateOrUpdateWebsite && ConfigureAuthenticationForWebsite = true`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the option to enable basic authentication for a website.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="WindowsAuthenticationForWebsite"::: -->
:::moniker range="<=azure-pipelines"

**`WindowsAuthenticationForWebsite`** - **Windows authentication**<br>
`boolean`. Optional. Use when `IISDeploymentType = IISWebsite && ActionIISWebsite = CreateOrUpdateWebsite && ConfigureAuthenticationForWebsite = true`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the option to enable windows authentication for a website.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ParentWebsiteNameForVD"::: -->
:::moniker range="<=azure-pipelines"

**`ParentWebsiteNameForVD`** - **Parent website name**<br>
`string`. Required when `IISDeploymentType = IISVirtualDirectory`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of the parent website of the virtual directory.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="VirtualPathForVD"::: -->
:::moniker range="<=azure-pipelines"

**`VirtualPathForVD`** - **Virtual path**<br>
`string`. Required when `IISDeploymentType = IISVirtualDirectory`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the virtual path of the virtual directory.

For example, to create a virtual directory `Site/Application/VDir`, enter `/Application/Vdir`. The parent website and application should already exist.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="PhysicalPathForVD"::: -->
:::moniker range="<=azure-pipelines"

**`PhysicalPathForVD`** - **Physical path**<br>
`string`. Required when `IISDeploymentType = IISVirtualDirectory`. Default value: `%SystemDrive%\inetpub\wwwroot`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the physical path where the virtual directory's content is stored. The content can reside on the local computer, in a remote directory, or on a network share, like `C:\Fabrikam` or `\\ContentShare\Fabrikam`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="VDPhysicalPathAuth"::: -->
:::moniker range="<=azure-pipelines"

**`VDPhysicalPathAuth`** - **Physical path authentication**<br>
`string`. Optional. Use when `IISDeploymentType = IISVirtualDirectory`. Allowed values: `VDUserPassThrough` (Application User (Pass-through)), `VDWindowsAuth` (Windows Authentication). Default value: `VDUserPassThrough`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the authentication mechanism that is used to access the physical path of the virtual directory.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="VDAuthUserName"::: -->
:::moniker range="<=azure-pipelines"

**`VDAuthUserName`** - **Username**<br>
`string`. Required when `VDPhysicalPathAuth = VDWindowsAuth && IISDeploymentType = IISVirtualDirectory`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the user name that is used to access the virtual directory's physical path.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="VDAuthUserPassword"::: -->
:::moniker range="<=azure-pipelines"

**`VDAuthUserPassword`** - **Password**<br>
`string`. Optional. Use when `VDPhysicalPathAuth = VDWindowsAuth && IISDeploymentType = IISVirtualDirectory`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the user's password that is used to access the virtual directory's physical path.  
The best practice is to create a variable in the build or release pipeline, mark it as `Secret` to secure it, and then provide it when using this input, like `$(userCredentials)`.  
*Note:* Special characters in the password are interpreted per [command-line arguments](/cpp/c-language/parsing-c-command-line-arguments).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ParentWebsiteNameForApplication"::: -->
:::moniker range="<=azure-pipelines"

**`ParentWebsiteNameForApplication`** - **Parent website name**<br>
`string`. Required when `IISDeploymentType = IISWebApplication`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of the parent website under which the application will be created or updated.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="VirtualPathForApplication"::: -->
:::moniker range="<=azure-pipelines"

**`VirtualPathForApplication`** - **Virtual path**<br>
`string`. Required when `IISDeploymentType = IISWebApplication`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the virtual path of the application.

For example, to create an application `Site/Application`, enter `/Application`. The parent website should already exist.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="PhysicalPathForApplication"::: -->
:::moniker range="<=azure-pipelines"

**`PhysicalPathForApplication`** - **Physical path**<br>
`string`. Required when `IISDeploymentType = IISWebApplication`. Default value: `%SystemDrive%\inetpub\wwwroot`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the physical path where the application's content is stored. The content can reside on the local computer, in a remote directory, or on a network share, like `C:\Fabrikam` or `\\ContentShare\Fabrikam`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ApplicationPhysicalPathAuth"::: -->
:::moniker range="<=azure-pipelines"

**`ApplicationPhysicalPathAuth`** - **Physical path authentication**<br>
`string`. Optional. Use when `IISDeploymentType = IISWebApplication`. Allowed values: `ApplicationUserPassThrough` (Application User (Pass-through)), `ApplicationWindowsAuth` (Windows Authentication). Default value: `ApplicationUserPassThrough`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the authentication mechanism that is used to access the physical path of the application.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ApplicationAuthUserName"::: -->
:::moniker range="<=azure-pipelines"

**`ApplicationAuthUserName`** - **Username**<br>
`string`. Required when `ApplicationPhysicalPathAuth = ApplicationWindowsAuth && IISDeploymentType = IISWebApplication`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the user name that is used to access the application's physical path.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ApplicationAuthUserPassword"::: -->
:::moniker range="<=azure-pipelines"

**`ApplicationAuthUserPassword`** - **Password**<br>
`string`. Optional. Use when `ApplicationPhysicalPathAuth = ApplicationWindowsAuth && IISDeploymentType = IISWebApplication`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the user's password that is used to access the application's physical path.  
The best practice is to create a variable in the build or release pipeline, mark it as `Secret` to secure it, and then provide it when using this input, like `$(userCredentials)`.  
*Note:* Special characters in the password are interpreted per [command-line arguments](/cpp/c-language/parsing-c-command-line-arguments).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="CreateOrUpdateAppPoolForApplication"::: -->
:::moniker range="<=azure-pipelines"

**`CreateOrUpdateAppPoolForApplication`** - **Create or update app pool**<br>
`boolean`. Optional. Use when `IISDeploymentType = IISWebApplication`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the option to create or update an application pool. If checked, the application will be created in the specified application pool.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AppPoolNameForApplication"::: -->
:::moniker range="<=azure-pipelines"

**`AppPoolNameForApplication`** - **Name**<br>
`string`. Required when `IISDeploymentType = IISWebApplication && CreateOrUpdateAppPoolForApplication = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of the IIS application pool to create or update.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DotNetVersionForApplication"::: -->
:::moniker range="<=azure-pipelines"

**`DotNetVersionForApplication`** - **.NET version**<br>
`string`. Required when `IISDeploymentType = IISWebApplication && CreateOrUpdateAppPoolForApplication = true`. Allowed values: `v4.0`, `v2.0`, `No Managed Code`. Default value: `v4.0`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the version of the .NET Framework that is loaded by the application pool. If the applications assigned to this application pool do not contain managed code, select the **No Managed Code** option from the list.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="PipeLineModeForApplication"::: -->
:::moniker range="<=azure-pipelines"

**`PipeLineModeForApplication`** - **Managed pipeline mode**<br>
`string`. Required when `IISDeploymentType = IISWebApplication && CreateOrUpdateAppPoolForApplication = true`. Allowed values: `Integrated`, `Classic`. Default value: `Integrated`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the managed pipeline mode to determine how IIS processes requests for managed content. Use classic mode only when the applications in the application pool cannot run in the integrated mode.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AppPoolIdentityForApplication"::: -->
:::moniker range="<=azure-pipelines"

**`AppPoolIdentityForApplication`** - **Identity**<br>
`string`. Required when `IISDeploymentType = IISWebApplication && CreateOrUpdateAppPoolForApplication = true`. Allowed values: `ApplicationPoolIdentity` (Application Pool Identity), `LocalService` (Local Service), `LocalSystem` (Local System), `NetworkService` (Network Service), `SpecificUser` (Custom Account). Default value: `ApplicationPoolIdentity`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Configures the account under which an application pool's worker process runs. Specifies one of the predefined security accounts or configures a custom account.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AppPoolUsernameForApplication"::: -->
:::moniker range="<=azure-pipelines"

**`AppPoolUsernameForApplication`** - **Username**<br>
`string`. Required when `AppPoolIdentityForApplication = SpecificUser && IISDeploymentType = IISWebApplication && CreateOrUpdateAppPoolForApplication = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the username of the custom account that you want to use.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AppPoolPasswordForApplication"::: -->
:::moniker range="<=azure-pipelines"

**`AppPoolPasswordForApplication`** - **Password**<br>
`string`. Optional. Use when `AppPoolIdentityForApplication = SpecificUser && IISDeploymentType = IISWebApplication && CreateOrUpdateAppPoolForApplication = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the password for the custom account.  
The best practice is to create a variable in the build or release pipeline, mark it as `Secret` to secure it, and then provide it when using this input, like `$(userCredentials)`.  
*Note:* Special characters in the password are interpreted per [command-line arguments](/cpp/c-language/parsing-c-command-line-arguments).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AppPoolName"::: -->
:::moniker range="<=azure-pipelines"

**`AppPoolName`** - **Name**<br>
`string`. Required when `ActionIISApplicationPool = CreateOrUpdateAppPool`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of the IIS application pool to create or update.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DotNetVersion"::: -->
:::moniker range="<=azure-pipelines"

**`DotNetVersion`** - **.NET version**<br>
`string`. Required when `ActionIISApplicationPool = CreateOrUpdateAppPool`. Allowed values: `v4.0`, `v2.0`, `No Managed Code`. Default value: `v4.0`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the version of the .NET Framework that is loaded by the application pool. If the applications assigned to this application pool do not contain managed code, select the **No Managed Code** option from the list.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="PipeLineMode"::: -->
:::moniker range="<=azure-pipelines"

**`PipeLineMode`** - **Managed pipeline mode**<br>
`string`. Required when `ActionIISApplicationPool = CreateOrUpdateAppPool`. Allowed values: `Integrated`, `Classic`. Default value: `Integrated`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the managed pipeline mode to determine how IIS processes requests for managed content. Use classic mode only when the applications in the application pool cannot run in the integrated mode.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AppPoolIdentity"::: -->
:::moniker range="<=azure-pipelines"

**`AppPoolIdentity`** - **Identity**<br>
`string`. Required when `ActionIISApplicationPool = CreateOrUpdateAppPool`. Allowed values: `ApplicationPoolIdentity` (Application Pool Identity), `LocalService` (Local Service), `LocalSystem` (Local System), `NetworkService` (Network Service), `SpecificUser` (Custom Account). Default value: `ApplicationPoolIdentity`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Configures the account under which an application pool's worker process runs. Specifies one of the predefined security accounts or configures a custom account.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AppPoolUsername"::: -->
:::moniker range="<=azure-pipelines"

**`AppPoolUsername`** - **Username**<br>
`string`. Required when `AppPoolIdentity = SpecificUser && ActionIISApplicationPool = CreateOrUpdateAppPool`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the username of the custom account that you want to use.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AppPoolPassword"::: -->
:::moniker range="<=azure-pipelines"

**`AppPoolPassword`** - **Password**<br>
`string`. Optional. Use when `AppPoolIdentity = SpecificUser && ActionIISApplicationPool = CreateOrUpdateAppPool`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the password for the custom account.  
The best practice is to create a variable in the build or release pipeline, mark it as `Secret` to secure it, and then provide it when using this input, like `$(userCredentials)`.  
*Note:* Special characters in the password are interpreted per [command-line arguments](/cpp/c-language/parsing-c-command-line-arguments).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="StartStopRecycleAppPoolName"::: -->
:::moniker range="<=azure-pipelines"

**`StartStopRecycleAppPoolName`** - **Application pool name**<br>
`string`. Required when `ActionIISApplicationPool = StartAppPool || ActionIISApplicationPool = StopAppPool || ActionIISApplicationPool = RecycleAppPool`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of the IIS application pool.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AppCmdCommands"::: -->
:::moniker range="<=azure-pipelines"

**`AppCmdCommands`** - **Additional appcmd.exe commands**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies additional `AppCmd.exe` commands. For more than one command, use a line separator.  
For example:  
`list apppools`  
`list sites`  
`recycle apppool /apppool.name:ExampleAppPoolName`
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

Use this task to create or update a website, web app, virtual directory, or application pool.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range=">=azure-pipelines-2020"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.111.0 or greater |
| Task category | Deploy |

:::moniker-end

:::moniker range="<=azure-pipelines-2019.1"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | Classic release |
| Runs on | DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.111.0 or greater |
| Task category | Deploy |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->