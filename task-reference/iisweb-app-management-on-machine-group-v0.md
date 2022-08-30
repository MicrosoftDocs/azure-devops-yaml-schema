---
title: IISWebAppManagementOnMachineGroup@0 - IIS web app manage v0 task
description: Create or update websites, web apps, virtual directories, or application pools.
ms.date: 08/18/2022
monikerRange: "<=azure-pipelines"
---

# IISWebAppManagementOnMachineGroup@0 - IIS web app manage v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Create or update websites, web apps, virtual directories, or application pools.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Create or update a Website, Web App, Virtual Directories, and Application Pool.
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
    IISDeploymentType: 'IISWebsite' # 'IISWebsite' | 'IISWebApplication' | 'IISVirtualDirectory' | 'IISApplicationPool'. Required. Configuration type. Default: 'IISWebsite'.
    ActionIISWebsite: 'CreateOrUpdateWebsite' # 'CreateOrUpdateWebsite' | 'StartWebsite' | 'StopWebsite'. Required when IISDeploymentType = IISWebsite. Action. Default: 'CreateOrUpdateWebsite'.
    #ActionIISApplicationPool: 'CreateOrUpdateAppPool' # 'CreateOrUpdateAppPool' | 'StartAppPool' | 'StopAppPool' | 'RecycleAppPool'. Required when IISDeploymentType = IISApplicationPool. Action. Default: 'CreateOrUpdateAppPool'.
    #StartStopWebsiteName: # string. Required when ActionIISWebsite = StartWebsite || ActionIISWebsite = StopWebsite. Website name. 
    #Protocol: 'http' # 'https' | 'http'. Required when IISDeploymentType = randomDeployment. Protocol. Default: 'http'.
    #IPAddress: 'All Unassigned' # string. Required when IISDeploymentType = randomDeployment. IP address. Default: 'All Unassigned'.
    #Port: '80' # string. Required when IISDeploymentType = randomDeployment. Port. Default: '80'.
    #ServerNameIndication: false # boolean. Optional. Use when IISDeploymentType = randomDeployment. Server Name Indication required. Default: false.
    #HostNameWithOutSNI: # string. Optional. Use when IISDeploymentType = randomDeployment. Host name. 
    #HostNameWithHttp: # string. Optional. Use when IISDeploymentType = randomDeployment. Host name. 
    #HostNameWithSNI: # string. Required when IISDeploymentType = randomDeployment. Host name. 
    #SSLCertThumbPrint: # string. Required when IISDeploymentType = randomDeployment. SSL certificate thumbprint. 
    #StartStopRecycleAppPoolName: # string. Required when ActionIISApplicationPool = StartAppPool || ActionIISApplicationPool = StopAppPool || ActionIISApplicationPool = RecycleAppPool. Application pool name. 
  # IIS Website
    WebsiteName: # string. Required. Website name. 
    WebsitePhysicalPath: '%SystemDrive%\inetpub\wwwroot' # string. Required. Physical path. Default: '%SystemDrive%\inetpub\wwwroot'.
    WebsitePhysicalPathAuth: 'WebsiteUserPassThrough' # 'WebsiteUserPassThrough' | 'WebsiteWindowsAuth'. Required. Physical path authentication. Default: 'WebsiteUserPassThrough'.
    #WebsiteAuthUserName: # string. Required when WebsitePhysicalPathAuth = WebsiteWindowsAuth. Username. 
    #WebsiteAuthUserPassword: # string. Optional. Use when WebsitePhysicalPathAuth = WebsiteWindowsAuth. Password. 
    #AddBinding: false # boolean. Add binding. Default: false.
    #CreateOrUpdateAppPoolForWebsite: false # boolean. Create or update app pool. Default: false.
    #ConfigureAuthenticationForWebsite: false # boolean. Configure authentication. Default: false.
  # IIS Bindings
    Bindings: # string. Required. Add bindings. 
  # IIS Application pool
    AppPoolNameForWebsite: # string. Required. Name. 
    DotNetVersionForWebsite: 'v4.0' # 'v4.0' | 'v2.0' | 'No Managed Code'. Required. .NET version. Default: 'v4.0'.
    PipeLineModeForWebsite: 'Integrated' # 'Integrated' | 'Classic'. Required. Managed pipeline mode. Default: 'Integrated'.
    AppPoolIdentityForWebsite: 'ApplicationPoolIdentity' # 'ApplicationPoolIdentity' | 'LocalService' | 'LocalSystem' | 'NetworkService' | 'SpecificUser'. Required. Identity. Default: 'ApplicationPoolIdentity'.
    #AppPoolUsernameForWebsite: # string. Required when AppPoolIdentityForWebsite = SpecificUser. Username. 
    #AppPoolPasswordForWebsite: # string. Optional. Use when AppPoolIdentityForWebsite = SpecificUser. Password. 
  # IIS Authentication
    #AnonymousAuthenticationForWebsite: false # boolean. Anonymous authentication. Default: false.
    #BasicAuthenticationForWebsite: false # boolean. Basic authentication. Default: false.
    #WindowsAuthenticationForWebsite: true # boolean. Windows authentication. Default: true.
  # IIS Virtual directory
    ParentWebsiteNameForVD: # string. Required. Parent website name. 
    VirtualPathForVD: # string. Required. Virtual path. 
    PhysicalPathForVD: '%SystemDrive%\inetpub\wwwroot' # string. Required. Physical path. Default: '%SystemDrive%\inetpub\wwwroot'.
    #VDPhysicalPathAuth: 'VDUserPassThrough' # 'VDUserPassThrough' | 'VDWindowsAuth'. Physical path authentication. Default: 'VDUserPassThrough'.
    #VDAuthUserName: # string. Required when VDPhysicalPathAuth = VDWindowsAuth. Username. 
    #VDAuthUserPassword: # string. Optional. Use when VDPhysicalPathAuth = VDWindowsAuth. Password. 
  # IIS Application
    ParentWebsiteNameForApplication: # string. Required. Parent website name. 
    VirtualPathForApplication: # string. Required. Virtual path. 
    PhysicalPathForApplication: '%SystemDrive%\inetpub\wwwroot' # string. Required. Physical path. Default: '%SystemDrive%\inetpub\wwwroot'.
    #ApplicationPhysicalPathAuth: 'ApplicationUserPassThrough' # 'ApplicationUserPassThrough' | 'ApplicationWindowsAuth'. Physical path authentication. Default: 'ApplicationUserPassThrough'.
    #ApplicationAuthUserName: # string. Required when ApplicationPhysicalPathAuth = ApplicationWindowsAuth. Username. 
    #ApplicationAuthUserPassword: # string. Optional. Use when ApplicationPhysicalPathAuth = ApplicationWindowsAuth. Password. 
    #CreateOrUpdateAppPoolForApplication: false # boolean. Create or update app pool. Default: false.
  # IIS Application pool
    AppPoolNameForApplication: # string. Required. Name. 
    DotNetVersionForApplication: 'v4.0' # 'v4.0' | 'v2.0' | 'No Managed Code'. Required. .NET version. Default: 'v4.0'.
    PipeLineModeForApplication: 'Integrated' # 'Integrated' | 'Classic'. Required. Managed pipeline mode. Default: 'Integrated'.
    AppPoolIdentityForApplication: 'ApplicationPoolIdentity' # 'ApplicationPoolIdentity' | 'LocalService' | 'LocalSystem' | 'NetworkService' | 'SpecificUser'. Required. Identity. Default: 'ApplicationPoolIdentity'.
    #AppPoolUsernameForApplication: # string. Required when AppPoolIdentityForApplication = SpecificUser. Username. 
    #AppPoolPasswordForApplication: # string. Optional. Use when AppPoolIdentityForApplication = SpecificUser. Password. 
  # IIS Application pool
    AppPoolName: # string. Required. Name. 
    DotNetVersion: 'v4.0' # 'v4.0' | 'v2.0' | 'No Managed Code'. Required. .NET version. Default: 'v4.0'.
    PipeLineMode: 'Integrated' # 'Integrated' | 'Classic'. Required. Managed pipeline mode. Default: 'Integrated'.
    AppPoolIdentity: 'ApplicationPoolIdentity' # 'ApplicationPoolIdentity' | 'LocalService' | 'LocalSystem' | 'NetworkService' | 'SpecificUser'. Required. Identity. Default: 'ApplicationPoolIdentity'.
    #AppPoolUsername: # string. Required when AppPoolIdentity = SpecificUser. Username. 
    #AppPoolPassword: # string. Optional. Use when AppPoolIdentity = SpecificUser. Password. 
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
    IISDeploymentType: 'IISWebsite' # 'IISWebsite' | 'IISWebApplication' | 'IISVirtualDirectory' | 'IISApplicationPool'. Required. Configuration type. Default: 'IISWebsite'.
    ActionIISWebsite: 'CreateOrUpdateWebsite' # 'CreateOrUpdateWebsite' | 'StartWebsite' | 'StopWebsite'. Required when IISDeploymentType = IISWebsite. Action. Default: 'CreateOrUpdateWebsite'.
    #ActionIISApplicationPool: 'CreateOrUpdateAppPool' # 'CreateOrUpdateAppPool' | 'StartAppPool' | 'StopAppPool' | 'RecycleAppPool'. Required when IISDeploymentType = IISApplicationPool. Action. Default: 'CreateOrUpdateAppPool'.
    #StartStopWebsiteName: # string. Required when ActionIISWebsite = StartWebsite || ActionIISWebsite = StopWebsite. Website name. 
    #Protocol: 'http' # 'https' | 'http'. Required when IISDeploymentType = randomDeployment. Protocol. Default: 'http'.
    #IPAddress: 'All Unassigned' # string. Required when IISDeploymentType = randomDeployment. IP address. Default: 'All Unassigned'.
    #Port: '80' # string. Required when IISDeploymentType = randomDeployment. Port. Default: '80'.
    #ServerNameIndication: false # boolean. Optional. Use when IISDeploymentType = randomDeployment. Server Name Indication required. Default: false.
    #HostNameWithOutSNI: # string. Optional. Use when IISDeploymentType = randomDeployment. Host name. 
    #HostNameWithHttp: # string. Optional. Use when IISDeploymentType = randomDeployment. Host name. 
    #HostNameWithSNI: # string. Required when IISDeploymentType = randomDeployment. Host name. 
    #SSLCertThumbPrint: # string. Required when IISDeploymentType = randomDeployment. SSL certificate thumbprint. 
    #StartStopRecycleAppPoolName: # string. Required when ActionIISApplicationPool = StartAppPool || ActionIISApplicationPool = StopAppPool || ActionIISApplicationPool = RecycleAppPool. Application pool name. 
  # IIS Website
    WebsiteName: # string. Required. Website name. 
    WebsitePhysicalPath: '%SystemDrive%\inetpub\wwwroot' # string. Required. Physical path. Default: '%SystemDrive%\inetpub\wwwroot'.
    WebsitePhysicalPathAuth: 'WebsiteUserPassThrough' # 'WebsiteUserPassThrough' | 'WebsiteWindowsAuth'. Required. Physical path authentication. Default: 'WebsiteUserPassThrough'.
    #WebsiteAuthUserName: # string. Required when WebsitePhysicalPathAuth = WebsiteWindowsAuth. Username. 
    #WebsiteAuthUserPassword: # string. Optional. Use when WebsitePhysicalPathAuth = WebsiteWindowsAuth. Password. 
    #AddBinding: false # boolean. Add binding. Default: false.
    #CreateOrUpdateAppPoolForWebsite: false # boolean. Create or update app pool. Default: false.
    #ConfigureAuthenticationForWebsite: false # boolean. Configure authentication. Default: false.
  # IIS Bindings
    Bindings: # string. Required. Add bindings. 
  # IIS Application pool
    AppPoolNameForWebsite: # string. Required. Name. 
    DotNetVersionForWebsite: 'v4.0' # 'v4.0' | 'v2.0' | 'No Managed Code'. Required. .NET version. Default: 'v4.0'.
    PipeLineModeForWebsite: 'Integrated' # 'Integrated' | 'Classic'. Required. Managed pipeline mode. Default: 'Integrated'.
    AppPoolIdentityForWebsite: 'ApplicationPoolIdentity' # 'ApplicationPoolIdentity' | 'LocalService' | 'LocalSystem' | 'NetworkService' | 'SpecificUser'. Required. Identity. Default: 'ApplicationPoolIdentity'.
    #AppPoolUsernameForWebsite: # string. Required when AppPoolIdentityForWebsite = SpecificUser. Username. 
    #AppPoolPasswordForWebsite: # string. Optional. Use when AppPoolIdentityForWebsite = SpecificUser. Password. 
  # IIS Authentication
    #AnonymousAuthenticationForWebsite: false # boolean. Anonymous authentication. Default: false.
    #BasicAuthenticationForWebsite: false # boolean. Basic authentication. Default: false.
    #WindowsAuthenticationForWebsite: true # boolean. Windows authentication. Default: true.
  # IIS Virtual directory
    ParentWebsiteNameForVD: # string. Required. Parent website name. 
    VirtualPathForVD: # string. Required. Virtual path. 
    PhysicalPathForVD: '%SystemDrive%\inetpub\wwwroot' # string. Required. Physical path. Default: '%SystemDrive%\inetpub\wwwroot'.
    #VDPhysicalPathAuth: 'VDUserPassThrough' # 'VDUserPassThrough' | 'VDWindowsAuth'. Physical path authentication. Default: 'VDUserPassThrough'.
    #VDAuthUserName: # string. Required when VDPhysicalPathAuth = VDWindowsAuth. Username. 
    #VDAuthUserPassword: # string. Optional. Use when VDPhysicalPathAuth = VDWindowsAuth. Password. 
  # IIS Application
    ParentWebsiteNameForApplication: # string. Required. Parent website name. 
    VirtualPathForApplication: # string. Required. Virtual path. 
    PhysicalPathForApplication: '%SystemDrive%\inetpub\wwwroot' # string. Required. Physical path. Default: '%SystemDrive%\inetpub\wwwroot'.
    #ApplicationPhysicalPathAuth: 'ApplicationUserPassThrough' # 'ApplicationUserPassThrough' | 'ApplicationWindowsAuth'. Physical path authentication. Default: 'ApplicationUserPassThrough'.
    #ApplicationAuthUserName: # string. Required when ApplicationPhysicalPathAuth = ApplicationWindowsAuth. Username. 
    #ApplicationAuthUserPassword: # string. Optional. Use when ApplicationPhysicalPathAuth = ApplicationWindowsAuth. Password. 
    #CreateOrUpdateAppPoolForApplication: false # boolean. Create or update app pool. Default: false.
  # IIS Application pool
    AppPoolNameForApplication: # string. Required. Name. 
    DotNetVersionForApplication: 'v4.0' # 'v4.0' | 'v2.0' | 'No Managed Code'. Required. .NET version. Default: 'v4.0'.
    PipeLineModeForApplication: 'Integrated' # 'Integrated' | 'Classic'. Required. Managed pipeline mode. Default: 'Integrated'.
    AppPoolIdentityForApplication: 'ApplicationPoolIdentity' # 'ApplicationPoolIdentity' | 'LocalService' | 'LocalSystem' | 'NetworkService' | 'SpecificUser'. Required. Identity. Default: 'ApplicationPoolIdentity'.
    #AppPoolUsernameForApplication: # string. Required when AppPoolIdentityForApplication = SpecificUser. Username. 
    #AppPoolPasswordForApplication: # string. Optional. Use when AppPoolIdentityForApplication = SpecificUser. Password. 
  # IIS Application pool
    AppPoolName: # string. Required. Name. 
    DotNetVersion: 'v4.0' # 'v4.0' | 'v2.0' | 'No Managed Code'. Required. .NET version. Default: 'v4.0'.
    PipeLineMode: 'Integrated' # 'Integrated' | 'Classic'. Required. Managed pipeline mode. Default: 'Integrated'.
    AppPoolIdentity: 'ApplicationPoolIdentity' # 'ApplicationPoolIdentity' | 'LocalService' | 'LocalSystem' | 'NetworkService' | 'SpecificUser'. Required. Identity. Default: 'ApplicationPoolIdentity'.
    #AppPoolUsername: # string. Required when AppPoolIdentity = SpecificUser. Username. 
    #AppPoolPassword: # string. Optional. Use when AppPoolIdentity = SpecificUser. Password. 
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
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Check this if you want to install IIS on the machine.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="IISDeploymentType"::: -->
:::moniker range="<=azure-pipelines"

**`IISDeploymentType`** - **Configuration type**<br>
Type: string. Required. Allowed values: 'IISWebsite', 'IISWebApplication', 'IISVirtualDirectory', 'IISApplicationPool'. Default value: 'IISWebsite'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
You can create or update sites, applications, virtual directories, and application pools.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ActionIISWebsite"::: -->
:::moniker range="<=azure-pipelines"

**`ActionIISWebsite`** - **Action**<br>
Type: string. Required when IISDeploymentType = IISWebsite. Allowed values: 'CreateOrUpdateWebsite', 'StartWebsite', 'StopWebsite'. Default value: 'CreateOrUpdateWebsite'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the appropriate action that you want to perform on an IIS website. 

"Create Or Update" will create a website or update an existing website.

 Start, Stop will start or stop the website respectively.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ActionIISApplicationPool"::: -->
:::moniker range="<=azure-pipelines"

**`ActionIISApplicationPool`** - **Action**<br>
Type: string. Required when IISDeploymentType = IISApplicationPool. Allowed values: 'CreateOrUpdateAppPool', 'StartAppPool', 'StopAppPool', 'RecycleAppPool'. Default value: 'CreateOrUpdateAppPool'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the appropriate action that you want to perform on an IIS Application Pool. 

"Create Or Update" will create app-pool or update an existing one.

Start, Stop, Recycle will start, stop or recycle the application pool respectively.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="StartStopWebsiteName"::: -->
:::moniker range="<=azure-pipelines"

**`StartStopWebsiteName`** - **Website name**<br>
Type: string. Required when ActionIISWebsite = StartWebsite || ActionIISWebsite = StopWebsite.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide the name of the IIS website.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="WebsiteName"::: -->
:::moniker range="<=azure-pipelines"

**`WebsiteName`** - **Website name**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide the name of the IIS website to create or update.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="WebsitePhysicalPath"::: -->
:::moniker range="<=azure-pipelines"

**`WebsitePhysicalPath`** - **Physical path**<br>
Type: string. Required. Default value: '%SystemDrive%\inetpub\wwwroot'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide the physical path where the website content will be stored. The content can reside on the local Computer, or in a remote directory, or on a network share, like C:\Fabrikam or \\\\ContentShare\Fabrikam.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="WebsitePhysicalPathAuth"::: -->
:::moniker range="<=azure-pipelines"

**`WebsitePhysicalPathAuth`** - **Physical path authentication**<br>
Type: string. Required. Allowed values: 'WebsiteUserPassThrough', 'WebsiteWindowsAuth'. Default value: 'WebsiteUserPassThrough'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the authentication mechanism that will be used to access the physical path of the website.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="WebsiteAuthUserName"::: -->
:::moniker range="<=azure-pipelines"

**`WebsiteAuthUserName`** - **Username**<br>
Type: string. Required when WebsitePhysicalPathAuth = WebsiteWindowsAuth.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide the user name that will be used to access the website's physical path.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="WebsiteAuthUserPassword"::: -->
:::moniker range="<=azure-pipelines"

**`WebsiteAuthUserPassword`** - **Password**<br>
Type: string. Optional. Use when WebsitePhysicalPathAuth = WebsiteWindowsAuth.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide the user's password that will be used to access the website's physical path. <br/>The best practice is to create a variable in the build or release pipeline, and mark it as 'Secret' to secure it, and then use it here, like '$(userCredentials)'. <br> Note: Special characters in password are interpreted as per <a href="https://go.microsoft.com/fwlink/?linkid=843470">command-line arguments</a>.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AddBinding"::: -->
:::moniker range="<=azure-pipelines"

**`AddBinding`** - **Add binding**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the option to add port binding for the website.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Protocol"::: -->
:::moniker range="<=azure-pipelines"

**`Protocol`** - **Protocol**<br>
Type: string. Required when IISDeploymentType = randomDeployment. Allowed values: 'https', 'http'. Default value: 'http'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select HTTP for the website to have an HTTP binding, or select HTTPS for the website to have a Secure Sockets Layer (SSL) binding.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="IPAddress"::: -->
:::moniker range="<=azure-pipelines"

**`IPAddress`** - **IP address**<br>
Type: string. Required when IISDeploymentType = randomDeployment. Default value: 'All Unassigned'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide an IP address that end-users can use to access this website. <br>If 'All Unassigned' is selected, then the website will respond to requests for all IP addresses on the port and for the host name, unless another website on the server has a binding on the same port but with a specific IP address.<br>.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Port"::: -->
:::moniker range="<=azure-pipelines"

**`Port`** - **Port**<br>
Type: string. Required when IISDeploymentType = randomDeployment. Default value: '80'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide the port, where the Hypertext Transfer Protocol Stack (HTTP.sys) will listen to the website requests.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ServerNameIndication"::: -->
:::moniker range="<=azure-pipelines"

**`ServerNameIndication`** - **Server Name Indication required**<br>
Type: boolean. Optional. Use when IISDeploymentType = randomDeployment. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the option to set the Server Name Indication (SNI) for the website. <br>SNI extends the SSL and TLS protocols to indicate the host name that the clients are attempting to connect to. It allows, multiple secure websites with different certificates, to use the same IP address.<br>.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="HostNameWithOutSNI"::: -->
:::moniker range="<=azure-pipelines"

**`HostNameWithOutSNI`** - **Host name**<br>
Type: string. Optional. Use when IISDeploymentType = randomDeployment.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter a host name (or domain name) for the website. <br>If a host name is specified, then the clients must use the host name instead of the IP address to access the website.<br>.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="HostNameWithHttp"::: -->
:::moniker range="<=azure-pipelines"

**`HostNameWithHttp`** - **Host name**<br>
Type: string. Optional. Use when IISDeploymentType = randomDeployment.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter a host name (or domain name) for the website. <br>If a host name is specified, then the clients must use the host name instead of the IP address to access the website.<br>.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="HostNameWithSNI"::: -->
:::moniker range="<=azure-pipelines"

**`HostNameWithSNI`** - **Host name**<br>
Type: string. Required when IISDeploymentType = randomDeployment.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter a host name (or domain name) for the website. <br>If a host name is specified, then the clients must use the host name instead of the IP address to access the website.<br>.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SSLCertThumbPrint"::: -->
:::moniker range="<=azure-pipelines"

**`SSLCertThumbPrint`** - **SSL certificate thumbprint**<br>
Type: string. Required when IISDeploymentType = randomDeployment.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide the thumb-print of the Secure Socket Layer certificate that the website is going to use for the HTTPS communication as a 40 character long hexadecimal string. The SSL certificate should be already installed on the Computer, at Local Computer, Personal store.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Bindings"::: -->
:::moniker range="<=azure-pipelines"

**`Bindings`** - **Add bindings**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Click on the extension [...] button to add bindings for the website.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="CreateOrUpdateAppPoolForWebsite"::: -->
:::moniker range="<=azure-pipelines"

**`CreateOrUpdateAppPoolForWebsite`** - **Create or update app pool**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the option to create or update an application pool. If checked, the website will be created in the specified app pool.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ConfigureAuthenticationForWebsite"::: -->
:::moniker range="<=azure-pipelines"

**`ConfigureAuthenticationForWebsite`** - **Configure authentication**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the option to configure authentication for website.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AppPoolNameForWebsite"::: -->
:::moniker range="<=azure-pipelines"

**`AppPoolNameForWebsite`** - **Name**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide the name of the IIS application pool to create or update.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DotNetVersionForWebsite"::: -->
:::moniker range="<=azure-pipelines"

**`DotNetVersionForWebsite`** - **.NET version**<br>
Type: string. Required. Allowed values: 'v4.0', 'v2.0', 'No Managed Code'. Default value: 'v4.0'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the version of the .NET Framework that is loaded by the application pool. <br>If the applications assigned to this application pool do not contain managed code, then select the 'No Managed Code' option from the list.<br>.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="PipeLineModeForWebsite"::: -->
:::moniker range="<=azure-pipelines"

**`PipeLineModeForWebsite`** - **Managed pipeline mode**<br>
Type: string. Required. Allowed values: 'Integrated', 'Classic'. Default value: 'Integrated'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the managed pipeline mode that specifies how IIS processes requests for managed content. Use classic mode only when the applications in the application pool cannot run in the Integrated mode.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AppPoolIdentityForWebsite"::: -->
:::moniker range="<=azure-pipelines"

**`AppPoolIdentityForWebsite`** - **Identity**<br>
Type: string. Required. Allowed values: 'ApplicationPoolIdentity', 'LocalService', 'LocalSystem', 'NetworkService', 'SpecificUser'. Default value: 'ApplicationPoolIdentity'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Configure the account under which an application pool's worker process runs. Select one of the predefined security accounts or configure a custom account.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AppPoolUsernameForWebsite"::: -->
:::moniker range="<=azure-pipelines"

**`AppPoolUsernameForWebsite`** - **Username**<br>
Type: string. Required when AppPoolIdentityForWebsite = SpecificUser.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide the username of the custom account that you want to use.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AppPoolPasswordForWebsite"::: -->
:::moniker range="<=azure-pipelines"

**`AppPoolPasswordForWebsite`** - **Password**<br>
Type: string. Optional. Use when AppPoolIdentityForWebsite = SpecificUser.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide the password for custom account. <br/>The best practice is to create a variable in the build or release pipeline, and mark it as 'Secret' to secure it, and then use it here, like '$(userCredentials)'. <br> Note: Special characters in password are interpreted as per <a href="https://go.microsoft.com/fwlink/?linkid=843470">command-line arguments</a>.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AnonymousAuthenticationForWebsite"::: -->
:::moniker range="<=azure-pipelines"

**`AnonymousAuthenticationForWebsite`** - **Anonymous authentication**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the option to enable anonymous authentication for website.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="BasicAuthenticationForWebsite"::: -->
:::moniker range="<=azure-pipelines"

**`BasicAuthenticationForWebsite`** - **Basic authentication**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the option to enable basic authentication for website.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="WindowsAuthenticationForWebsite"::: -->
:::moniker range="<=azure-pipelines"

**`WindowsAuthenticationForWebsite`** - **Windows authentication**<br>
Type: boolean. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the option to enable windows authentication for website.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ParentWebsiteNameForVD"::: -->
:::moniker range="<=azure-pipelines"

**`ParentWebsiteNameForVD`** - **Parent website name**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide the name of the parent Website of the virtual directory.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="VirtualPathForVD"::: -->
:::moniker range="<=azure-pipelines"

**`VirtualPathForVD`** - **Virtual path**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide the virtual path of the virtual directory. 

Example: To create a virtual directory Site/Application/VDir enter /Application/Vdir. The parent website and application should be already existing.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="PhysicalPathForVD"::: -->
:::moniker range="<=azure-pipelines"

**`PhysicalPathForVD`** - **Physical path**<br>
Type: string. Required. Default value: '%SystemDrive%\inetpub\wwwroot'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide the physical path where the virtual directory's content will be stored. The content can reside on the local Computer, or in a remote directory, or on a network share, like C:\Fabrikam or \\\\ContentShare\Fabrikam.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="VDPhysicalPathAuth"::: -->
:::moniker range="<=azure-pipelines"

**`VDPhysicalPathAuth`** - **Physical path authentication**<br>
Type: string. Allowed values: 'VDUserPassThrough', 'VDWindowsAuth'. Default value: 'VDUserPassThrough'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the authentication mechanism that will be used to access the physical path of the virtual directory.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="VDAuthUserName"::: -->
:::moniker range="<=azure-pipelines"

**`VDAuthUserName`** - **Username**<br>
Type: string. Required when VDPhysicalPathAuth = VDWindowsAuth.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide the user name that will be used to access the virtual directory's physical path.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="VDAuthUserPassword"::: -->
:::moniker range="<=azure-pipelines"

**`VDAuthUserPassword`** - **Password**<br>
Type: string. Optional. Use when VDPhysicalPathAuth = VDWindowsAuth.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide the user's password that will be used to access the virtual directory's physical path. <br/>The best practice is to create a variable in the build or release pipeline, and mark it as 'Secret' to secure it, and then use it here, like '$(userCredentials)'. <br> Note: Special characters in password are interpreted as per <a href="https://go.microsoft.com/fwlink/?linkid=843470">command-line arguments</a>.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ParentWebsiteNameForApplication"::: -->
:::moniker range="<=azure-pipelines"

**`ParentWebsiteNameForApplication`** - **Parent website name**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide the name of the parent Website under which the application will be created or updated.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="VirtualPathForApplication"::: -->
:::moniker range="<=azure-pipelines"

**`VirtualPathForApplication`** - **Virtual path**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide the virtual path of the application. 

Example: To create an application Site/Application enter /Application. The parent website should be already existing.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="PhysicalPathForApplication"::: -->
:::moniker range="<=azure-pipelines"

**`PhysicalPathForApplication`** - **Physical path**<br>
Type: string. Required. Default value: '%SystemDrive%\inetpub\wwwroot'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide the physical path where the application's content will be stored. The content can reside on the local Computer, or in a remote directory, or on a network share, like C:\Fabrikam or \\\\ContentShare\Fabrikam.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ApplicationPhysicalPathAuth"::: -->
:::moniker range="<=azure-pipelines"

**`ApplicationPhysicalPathAuth`** - **Physical path authentication**<br>
Type: string. Allowed values: 'ApplicationUserPassThrough', 'ApplicationWindowsAuth'. Default value: 'ApplicationUserPassThrough'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the authentication mechanism that will be used to access the physical path of the application.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ApplicationAuthUserName"::: -->
:::moniker range="<=azure-pipelines"

**`ApplicationAuthUserName`** - **Username**<br>
Type: string. Required when ApplicationPhysicalPathAuth = ApplicationWindowsAuth.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide the user name that will be used to access the application's physical path.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ApplicationAuthUserPassword"::: -->
:::moniker range="<=azure-pipelines"

**`ApplicationAuthUserPassword`** - **Password**<br>
Type: string. Optional. Use when ApplicationPhysicalPathAuth = ApplicationWindowsAuth.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide the user's password that will be used to access the application's physical path. <br/>The best practice is to create a variable in the build or release pipeline, and mark it as 'Secret' to secure it, and then use it here, like '$(userCredentials)'. <br> Note: Special characters in password are interpreted as per <a href="https://go.microsoft.com/fwlink/?linkid=843470">command-line arguments</a>.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="CreateOrUpdateAppPoolForApplication"::: -->
:::moniker range="<=azure-pipelines"

**`CreateOrUpdateAppPoolForApplication`** - **Create or update app pool**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the option to create or update an application pool. If checked, the application will be created in the specified app pool.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AppPoolNameForApplication"::: -->
:::moniker range="<=azure-pipelines"

**`AppPoolNameForApplication`** - **Name**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide the name of the IIS application pool to create or update.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DotNetVersionForApplication"::: -->
:::moniker range="<=azure-pipelines"

**`DotNetVersionForApplication`** - **.NET version**<br>
Type: string. Required. Allowed values: 'v4.0', 'v2.0', 'No Managed Code'. Default value: 'v4.0'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the version of the .NET Framework that is loaded by the application pool. <br>If the applications assigned to this application pool do not contain managed code, then select the 'No Managed Code' option from the list.<br>.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="PipeLineModeForApplication"::: -->
:::moniker range="<=azure-pipelines"

**`PipeLineModeForApplication`** - **Managed pipeline mode**<br>
Type: string. Required. Allowed values: 'Integrated', 'Classic'. Default value: 'Integrated'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the managed pipeline mode that specifies how IIS processes requests for managed content. Use classic mode only when the applications in the application pool cannot run in the Integrated mode.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AppPoolIdentityForApplication"::: -->
:::moniker range="<=azure-pipelines"

**`AppPoolIdentityForApplication`** - **Identity**<br>
Type: string. Required. Allowed values: 'ApplicationPoolIdentity', 'LocalService', 'LocalSystem', 'NetworkService', 'SpecificUser'. Default value: 'ApplicationPoolIdentity'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Configure the account under which an application pool's worker process runs. Select one of the predefined security accounts or configure a custom account.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AppPoolUsernameForApplication"::: -->
:::moniker range="<=azure-pipelines"

**`AppPoolUsernameForApplication`** - **Username**<br>
Type: string. Required when AppPoolIdentityForApplication = SpecificUser.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide the username of the custom account that you want to use.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AppPoolPasswordForApplication"::: -->
:::moniker range="<=azure-pipelines"

**`AppPoolPasswordForApplication`** - **Password**<br>
Type: string. Optional. Use when AppPoolIdentityForApplication = SpecificUser.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide the password for custom account. <br/>The best practice is to create a variable in the build or release pipeline, and mark it as 'Secret' to secure it, and then use it here, like '$(userCredentials)'. <br> Note: Special characters in password are interpreted as per <a href="https://go.microsoft.com/fwlink/?linkid=843470">command-line arguments</a>.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AppPoolName"::: -->
:::moniker range="<=azure-pipelines"

**`AppPoolName`** - **Name**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide the name of the IIS application pool to create or update.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DotNetVersion"::: -->
:::moniker range="<=azure-pipelines"

**`DotNetVersion`** - **.NET version**<br>
Type: string. Required. Allowed values: 'v4.0', 'v2.0', 'No Managed Code'. Default value: 'v4.0'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the version of the .NET Framework that is loaded by the application pool. <br>If the applications assigned to this application pool do not contain managed code, then select the 'No Managed Code' option from the list.<br>.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="PipeLineMode"::: -->
:::moniker range="<=azure-pipelines"

**`PipeLineMode`** - **Managed pipeline mode**<br>
Type: string. Required. Allowed values: 'Integrated', 'Classic'. Default value: 'Integrated'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the managed pipeline mode that specifies how IIS processes requests for managed content. Use classic mode only when the applications in the application pool cannot run in the Integrated mode.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AppPoolIdentity"::: -->
:::moniker range="<=azure-pipelines"

**`AppPoolIdentity`** - **Identity**<br>
Type: string. Required. Allowed values: 'ApplicationPoolIdentity', 'LocalService', 'LocalSystem', 'NetworkService', 'SpecificUser'. Default value: 'ApplicationPoolIdentity'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Configure the account under which an application pool's worker process runs. Select one of the predefined security accounts or configure a custom account.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AppPoolUsername"::: -->
:::moniker range="<=azure-pipelines"

**`AppPoolUsername`** - **Username**<br>
Type: string. Required when AppPoolIdentity = SpecificUser.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide the username of the custom account that you want to use.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AppPoolPassword"::: -->
:::moniker range="<=azure-pipelines"

**`AppPoolPassword`** - **Password**<br>
Type: string. Optional. Use when AppPoolIdentity = SpecificUser.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide the password for custom account. <br/>The best practice is to create a variable in the build or release pipeline, and mark it as 'Secret' to secure it, and then use it here, like '$(userCredentials)'. <br> Note: Special characters in password are interpreted as per <a href="https://go.microsoft.com/fwlink/?linkid=843470">command-line arguments</a>.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="StartStopRecycleAppPoolName"::: -->
:::moniker range="<=azure-pipelines"

**`StartStopRecycleAppPoolName`** - **Application pool name**<br>
Type: string. Required when ActionIISApplicationPool = StartAppPool || ActionIISApplicationPool = StopAppPool || ActionIISApplicationPool = RecycleAppPool.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide the name of the IIS application pool.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AppCmdCommands"::: -->
:::moniker range="<=azure-pipelines"

**`AppCmdCommands`** - **Additional appcmd.exe commands**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter additional AppCmd.exe commands. For more than one command use a line separator, like <br/> list apppools <br/> list sites<br/> recycle apppool /apppool.name:ExampleAppPoolName.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range="<=azure-pipelines"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
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