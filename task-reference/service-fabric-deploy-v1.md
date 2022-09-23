---
title: ServiceFabricDeploy@1 - Service Fabric application deployment v1 task
description: Deploy an Azure Service Fabric application to a cluster.
ms.date: 09/01/2022
monikerRange: "<=azure-pipelines"
---

# ServiceFabricDeploy@1 - Service Fabric application deployment v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Deploy an Azure Service Fabric application to a cluster.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Deploy a Service Fabric application to a cluster.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# Service Fabric application deployment v1
# Deploy an Azure Service Fabric application to a cluster.
- task: ServiceFabricDeploy@1
  inputs:
    applicationPackagePath: # string. Required. Application Package. 
    serviceConnectionName: # string. Required. Cluster Service Connection. 
    #publishProfilePath: # string. Publish Profile. 
    #applicationParameterPath: # string. Application Parameters. 
    #overrideApplicationParameter: false # boolean. Override Application Parameters. Default: false.
  # Advanced Settings
    #compressPackage: false # boolean. Compress Package. Default: false.
    #copyPackageTimeoutSec: # string. CopyPackageTimeoutSec. 
    #registerPackageTimeoutSec: # string. RegisterPackageTimeoutSec. 
    overwriteBehavior: 'SameAppTypeAndVersion' # 'Always' | 'Never' | 'SameAppTypeAndVersion'. Required. Overwrite Behavior. Default: 'SameAppTypeAndVersion'.
    #skipUpgradeSameTypeAndVersion: false # boolean. Skip upgrade for same Type and Version. Default: false.
    #skipPackageValidation: false # boolean. Skip package validation. Default: false.
  # Upgrade Settings
    #useDiffPackage: false # boolean. Use Diff Package. Default: false.
    #overridePublishProfileSettings: false # boolean. Override All Publish Profile Upgrade Settings. Default: false.
    #isUpgrade: true # boolean. Optional. Use when overridePublishProfileSettings = true. Upgrade the Application. Default: true.
    #unregisterUnusedVersions: true # boolean. Unregister Unused Versions. Default: true.
    #upgradeMode: 'Monitored' # 'Monitored' | 'UnmonitoredAuto' | 'UnmonitoredManual'. Required when overridePublishProfileSettings = true && isUpgrade = true. Upgrade Mode. Default: 'Monitored'.
    #FailureAction: 'Rollback' # 'Rollback' | 'Manual'. Required when overridePublishProfileSettings = true && isUpgrade = true && upgradeMode = Monitored. FailureAction. Default: 'Rollback'.
    #UpgradeReplicaSetCheckTimeoutSec: # string. Optional. Use when overridePublishProfileSettings = true && isUpgrade = true. UpgradeReplicaSetCheckTimeoutSec. 
    #TimeoutSec: # string. Optional. Use when overridePublishProfileSettings = true && isUpgrade = true. TimeoutSec. 
    #ForceRestart: false # boolean. Optional. Use when overridePublishProfileSettings = true && isUpgrade = true. ForceRestart. Default: false.
    #HealthCheckRetryTimeoutSec: # string. Optional. Use when overridePublishProfileSettings = true && isUpgrade = true && upgradeMode = Monitored. HealthCheckRetryTimeoutSec. 
    #HealthCheckWaitDurationSec: # string. Optional. Use when overridePublishProfileSettings = true && isUpgrade = true && upgradeMode = Monitored. HealthCheckWaitDurationSec. 
    #HealthCheckStableDurationSec: # string. Optional. Use when overridePublishProfileSettings = true && isUpgrade = true && upgradeMode = Monitored. HealthCheckStableDurationSec. 
    #UpgradeDomainTimeoutSec: # string. Optional. Use when overridePublishProfileSettings = true && isUpgrade = true && upgradeMode = Monitored. UpgradeDomainTimeoutSec. 
    #ConsiderWarningAsError: false # boolean. Optional. Use when overridePublishProfileSettings = true && isUpgrade = true && upgradeMode = Monitored. ConsiderWarningAsError. Default: false.
    #DefaultServiceTypeHealthPolicy: # string. Optional. Use when overridePublishProfileSettings = true && isUpgrade = true && upgradeMode = Monitored. DefaultServiceTypeHealthPolicy. 
    #MaxPercentUnhealthyDeployedApplications: # string. Optional. Use when overridePublishProfileSettings = true && isUpgrade = true && upgradeMode = Monitored. MaxPercentUnhealthyDeployedApplications. 
    #UpgradeTimeoutSec: # string. Optional. Use when overridePublishProfileSettings = true && isUpgrade = true && upgradeMode = Monitored. UpgradeTimeoutSec. 
    #ServiceTypeHealthPolicyMap: # string. Optional. Use when overridePublishProfileSettings = true && isUpgrade = true && upgradeMode = Monitored. ServiceTypeHealthPolicyMap. 
  # Docker Settings
    #configureDockerSettings: false # boolean. Configure Docker settings. Default: false.
    #registryCredentials: 'AzureResourceManagerEndpoint' # 'AzureResourceManagerEndpoint' | 'ContainerRegistryEndpoint' | 'UsernamePassword'. Required when configureDockerSettings = true. Registry Credentials Source. Default: 'AzureResourceManagerEndpoint'.
    #dockerRegistryConnection: # string. Required when configureDockerSettings = true && registryCredentials = ContainerRegistryEndpoint. Docker Registry Service Connection. 
    #azureSubscription: # string. Required when configureDockerSettings = true && registryCredentials = AzureResourceManagerEndpoint. Azure subscription. 
    #registryUserName: # string. Optional. Use when configureDockerSettings = true && registryCredentials = UsernamePassword. Registry User Name. 
    #registryPassword: # string. Optional. Use when configureDockerSettings = true && registryCredentials = UsernamePassword. Registry Password. 
    #passwordEncrypted: true # boolean. Optional. Use when configureDockerSettings = true && registryCredentials = UsernamePassword. Password Encrypted. Default: true.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Service Fabric Application Deployment v1
# Deploy a Service Fabric application to a cluster.
- task: ServiceFabricDeploy@1
  inputs:
    applicationPackagePath: # string. Required. Application Package. 
    serviceConnectionName: # string. Required. Cluster Service Connection. 
    #publishProfilePath: # string. Publish Profile. 
    #applicationParameterPath: # string. Application Parameters. 
    #overrideApplicationParameter: false # boolean. Override Application Parameters. Default: false.
  # Advanced Settings
    #compressPackage: false # boolean. Compress Package. Default: false.
    #copyPackageTimeoutSec: # string. CopyPackageTimeoutSec. 
    #registerPackageTimeoutSec: # string. RegisterPackageTimeoutSec. 
    overwriteBehavior: 'SameAppTypeAndVersion' # 'Always' | 'Never' | 'SameAppTypeAndVersion'. Required. Overwrite Behavior. Default: 'SameAppTypeAndVersion'.
    #skipUpgradeSameTypeAndVersion: false # boolean. Skip upgrade for same Type and Version. Default: false.
    #skipPackageValidation: false # boolean. Skip package validation. Default: false.
  # Upgrade Settings
    #useDiffPackage: false # boolean. Use Diff Package. Default: false.
    #overridePublishProfileSettings: false # boolean. Override All Publish Profile Upgrade Settings. Default: false.
    #isUpgrade: true # boolean. Optional. Use when overridePublishProfileSettings = true. Upgrade the Application. Default: true.
    #unregisterUnusedVersions: true # boolean. Unregister Unused Versions. Default: true.
    #upgradeMode: 'Monitored' # 'Monitored' | 'UnmonitoredAuto' | 'UnmonitoredManual'. Required when overridePublishProfileSettings = true && isUpgrade = true. Upgrade Mode. Default: 'Monitored'.
    #FailureAction: 'Rollback' # 'Rollback' | 'Manual'. Required when overridePublishProfileSettings = true && isUpgrade = true && upgradeMode = Monitored. FailureAction. Default: 'Rollback'.
    #UpgradeReplicaSetCheckTimeoutSec: # string. Optional. Use when overridePublishProfileSettings = true && isUpgrade = true. UpgradeReplicaSetCheckTimeoutSec. 
    #TimeoutSec: # string. Optional. Use when overridePublishProfileSettings = true && isUpgrade = true. TimeoutSec. 
    #ForceRestart: false # boolean. Optional. Use when overridePublishProfileSettings = true && isUpgrade = true. ForceRestart. Default: false.
    #HealthCheckRetryTimeoutSec: # string. Optional. Use when overridePublishProfileSettings = true && isUpgrade = true && upgradeMode = Monitored. HealthCheckRetryTimeoutSec. 
    #HealthCheckWaitDurationSec: # string. Optional. Use when overridePublishProfileSettings = true && isUpgrade = true && upgradeMode = Monitored. HealthCheckWaitDurationSec. 
    #HealthCheckStableDurationSec: # string. Optional. Use when overridePublishProfileSettings = true && isUpgrade = true && upgradeMode = Monitored. HealthCheckStableDurationSec. 
    #UpgradeDomainTimeoutSec: # string. Optional. Use when overridePublishProfileSettings = true && isUpgrade = true && upgradeMode = Monitored. UpgradeDomainTimeoutSec. 
    #ConsiderWarningAsError: false # boolean. Optional. Use when overridePublishProfileSettings = true && isUpgrade = true && upgradeMode = Monitored. ConsiderWarningAsError. Default: false.
    #DefaultServiceTypeHealthPolicy: # string. Optional. Use when overridePublishProfileSettings = true && isUpgrade = true && upgradeMode = Monitored. DefaultServiceTypeHealthPolicy. 
    #MaxPercentUnhealthyDeployedApplications: # string. Optional. Use when overridePublishProfileSettings = true && isUpgrade = true && upgradeMode = Monitored. MaxPercentUnhealthyDeployedApplications. 
    #UpgradeTimeoutSec: # string. Optional. Use when overridePublishProfileSettings = true && isUpgrade = true && upgradeMode = Monitored. UpgradeTimeoutSec. 
    #ServiceTypeHealthPolicyMap: # string. Optional. Use when overridePublishProfileSettings = true && isUpgrade = true && upgradeMode = Monitored. ServiceTypeHealthPolicyMap. 
  # Docker Settings
    #configureDockerSettings: false # boolean. Configure Docker settings. Default: false.
    #registryCredentials: 'AzureResourceManagerEndpoint' # 'AzureResourceManagerEndpoint' | 'ContainerRegistryEndpoint' | 'UsernamePassword'. Required when configureDockerSettings = true. Registry Credentials Source. Default: 'AzureResourceManagerEndpoint'.
    #dockerRegistryConnection: # string. Required when configureDockerSettings = true && registryCredentials = ContainerRegistryEndpoint. Docker Registry Service Connection. 
    #azureSubscription: # string. Required when configureDockerSettings = true && registryCredentials = AzureResourceManagerEndpoint. Azure subscription. 
    #registryUserName: # string. Optional. Use when configureDockerSettings = true && registryCredentials = UsernamePassword. Registry User Name. 
    #registryPassword: # string. Optional. Use when configureDockerSettings = true && registryCredentials = UsernamePassword. Registry Password. 
    #passwordEncrypted: true # boolean. Optional. Use when configureDockerSettings = true && registryCredentials = UsernamePassword. Password Encrypted. Default: true.
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

<!-- :::item name="applicationPackagePath"::: -->
:::moniker range="<=azure-pipelines"

**`applicationPackagePath`** - **Application Package**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to the application package that is to be deployed. [Variables](https://go.microsoft.com/fwlink/?LinkID=550988) and wildcards can be used in the path.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="serviceConnectionName"::: -->
:::moniker range=">=azure-pipelines-2019"

**`serviceConnectionName`** - **Cluster Service Connection**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select an Azure Service Fabric service connection to be used to connect to the cluster. The settings defined in this referenced service connection will override those defined in the publish profile. Choose 'Manage' to register a new service connection.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`serviceConnectionName`** - **Cluster Connection**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select an Azure Service Fabric service connection to be used to connect to the cluster. The settings defined in this referenced service connection will override those defined in the publish profile. Choose 'Manage' to register a new service connection.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishProfilePath"::: -->
:::moniker range="<=azure-pipelines"

**`publishProfilePath`** - **Publish Profile**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to the publish profile file that defines the settings to use. [Variables](https://go.microsoft.com/fwlink/?LinkID=550988) and wildcards can be used in the path.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="applicationParameterPath"::: -->
:::moniker range="<=azure-pipelines"

**`applicationParameterPath`** - **Application Parameters**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to the application parameters file. [Variables](https://go.microsoft.com/fwlink/?LinkID=550988) and wildcards can be used in the path. If specified, this will override the value in the publish profile.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="overrideApplicationParameter"::: -->
:::moniker range=">=azure-pipelines-2019"

**`overrideApplicationParameter`** - **Override Application Parameters**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Variables defined in the build or release pipeline will be matched against the 'Parameter Name' entries in the application manifest file. 
 Example: If your application has a parameter defined as below.
```
 <Parameters> 
 <Parameter Name="SampleApp_PartitionCount" Value="1" /> 
 <Parameter Name="SampleApp_InstanceCount" DefaultValue="-1" /> 
 </Parameters>
```
 and you want to change the partition count to 2, you can define a release pipeline or an environment variable "SampleApp_PartitionCount" and its value as "2". 

 Note: If same variables are defined in the release pipeline and in the environment, then the environment variables will supersede the release pipeline variables.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="compressPackage"::: -->
:::moniker range="<=azure-pipelines"

**`compressPackage`** - **Compress Package**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Indicates whether the application package should be compressed before copying to the image store. If enabled, this will override the value in the publish profile.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="copyPackageTimeoutSec"::: -->
:::moniker range="<=azure-pipelines"

**`copyPackageTimeoutSec`** - **CopyPackageTimeoutSec**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Timeout in seconds for copying application package to image store. If specified, this will override the value in the publish profile.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="registerPackageTimeoutSec"::: -->
:::moniker range="<=azure-pipelines"

**`registerPackageTimeoutSec`** - **RegisterPackageTimeoutSec**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Timeout in seconds for registering or un-registering application package.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="overwriteBehavior"::: -->
:::moniker range="<=azure-pipelines"

**`overwriteBehavior`** - **Overwrite Behavior**<br>
Type: string. Required. Allowed values: 'Always', 'Never', 'SameAppTypeAndVersion'. Default value: 'SameAppTypeAndVersion'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Overwrite Behavior if an application exists in the cluster with the same name, and upgrades have not been configured.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="skipUpgradeSameTypeAndVersion"::: -->
:::moniker range="<=azure-pipelines"

**`skipUpgradeSameTypeAndVersion`** - **Skip upgrade for same Type and Version**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Indicates whether an upgrade will be skipped if the same application type and version already exists in the cluster, otherwise the upgrade fails during validation. If enabled, re-deployments are idempotent.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="skipPackageValidation"::: -->
:::moniker range="<=azure-pipelines"

**`skipPackageValidation`** - **Skip package validation**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Indicates whether the package should be validated or not before deployment.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="useDiffPackage"::: -->
:::moniker range="<=azure-pipelines"

**`useDiffPackage`** - **Use Diff Package**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Upgrade by using a diff package that contains only the updated application files, the updated application manifest, and the service manifest files.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="overridePublishProfileSettings"::: -->
:::moniker range="<=azure-pipelines"

**`overridePublishProfileSettings`** - **Override All Publish Profile Upgrade Settings**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
This will override all upgrade settings with either the values specified below or the default value if not specified.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="isUpgrade"::: -->
:::moniker range="<=azure-pipelines"

**`isUpgrade`** - **Upgrade the Application**<br>
Type: boolean. Optional. Use when overridePublishProfileSettings = true. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="unregisterUnusedVersions"::: -->
:::moniker range="<=azure-pipelines"

**`unregisterUnusedVersions`** - **Unregister Unused Versions**<br>
Type: boolean. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Indicates whether all unused versions of the application type will be removed after an upgrade.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="upgradeMode"::: -->
:::moniker range="<=azure-pipelines"

**`upgradeMode`** - **Upgrade Mode**<br>
Type: string. Required when overridePublishProfileSettings = true && isUpgrade = true. Allowed values: 'Monitored', 'UnmonitoredAuto', 'UnmonitoredManual'. Default value: 'Monitored'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="FailureAction"::: -->
:::moniker range="<=azure-pipelines"

**`FailureAction`** - **FailureAction**<br>
Type: string. Required when overridePublishProfileSettings = true && isUpgrade = true && upgradeMode = Monitored. Allowed values: 'Rollback', 'Manual'. Default value: 'Rollback'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="UpgradeReplicaSetCheckTimeoutSec"::: -->
:::moniker range="<=azure-pipelines"

**`UpgradeReplicaSetCheckTimeoutSec`** - **UpgradeReplicaSetCheckTimeoutSec**<br>
Type: string. Optional. Use when overridePublishProfileSettings = true && isUpgrade = true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="TimeoutSec"::: -->
:::moniker range="<=azure-pipelines"

**`TimeoutSec`** - **TimeoutSec**<br>
Type: string. Optional. Use when overridePublishProfileSettings = true && isUpgrade = true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ForceRestart"::: -->
:::moniker range="<=azure-pipelines"

**`ForceRestart`** - **ForceRestart**<br>
Type: boolean. Optional. Use when overridePublishProfileSettings = true && isUpgrade = true. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="HealthCheckRetryTimeoutSec"::: -->
:::moniker range="<=azure-pipelines"

**`HealthCheckRetryTimeoutSec`** - **HealthCheckRetryTimeoutSec**<br>
Type: string. Optional. Use when overridePublishProfileSettings = true && isUpgrade = true && upgradeMode = Monitored.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="HealthCheckWaitDurationSec"::: -->
:::moniker range="<=azure-pipelines"

**`HealthCheckWaitDurationSec`** - **HealthCheckWaitDurationSec**<br>
Type: string. Optional. Use when overridePublishProfileSettings = true && isUpgrade = true && upgradeMode = Monitored.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="HealthCheckStableDurationSec"::: -->
:::moniker range="<=azure-pipelines"

**`HealthCheckStableDurationSec`** - **HealthCheckStableDurationSec**<br>
Type: string. Optional. Use when overridePublishProfileSettings = true && isUpgrade = true && upgradeMode = Monitored.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="UpgradeDomainTimeoutSec"::: -->
:::moniker range="<=azure-pipelines"

**`UpgradeDomainTimeoutSec`** - **UpgradeDomainTimeoutSec**<br>
Type: string. Optional. Use when overridePublishProfileSettings = true && isUpgrade = true && upgradeMode = Monitored.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ConsiderWarningAsError"::: -->
:::moniker range="<=azure-pipelines"

**`ConsiderWarningAsError`** - **ConsiderWarningAsError**<br>
Type: boolean. Optional. Use when overridePublishProfileSettings = true && isUpgrade = true && upgradeMode = Monitored. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DefaultServiceTypeHealthPolicy"::: -->
:::moniker range="<=azure-pipelines"

**`DefaultServiceTypeHealthPolicy`** - **DefaultServiceTypeHealthPolicy**<br>
Type: string. Optional. Use when overridePublishProfileSettings = true && isUpgrade = true && upgradeMode = Monitored.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="MaxPercentUnhealthyDeployedApplications"::: -->
:::moniker range="<=azure-pipelines"

**`MaxPercentUnhealthyDeployedApplications`** - **MaxPercentUnhealthyDeployedApplications**<br>
Type: string. Optional. Use when overridePublishProfileSettings = true && isUpgrade = true && upgradeMode = Monitored.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="UpgradeTimeoutSec"::: -->
:::moniker range="<=azure-pipelines"

**`UpgradeTimeoutSec`** - **UpgradeTimeoutSec**<br>
Type: string. Optional. Use when overridePublishProfileSettings = true && isUpgrade = true && upgradeMode = Monitored.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ServiceTypeHealthPolicyMap"::: -->
:::moniker range="<=azure-pipelines"

**`ServiceTypeHealthPolicyMap`** - **ServiceTypeHealthPolicyMap**<br>
Type: string. Optional. Use when overridePublishProfileSettings = true && isUpgrade = true && upgradeMode = Monitored.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configureDockerSettings"::: -->
:::moniker range="<=azure-pipelines"

**`configureDockerSettings`** - **Configure Docker settings**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Configures the application with the specified Docker settings.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="registryCredentials"::: -->
:::moniker range="<=azure-pipelines"

**`registryCredentials`** - **Registry Credentials Source**<br>
Type: string. Required when configureDockerSettings = true. Allowed values: 'AzureResourceManagerEndpoint', 'ContainerRegistryEndpoint', 'UsernamePassword'. Default value: 'AzureResourceManagerEndpoint'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Choose how credentials for the Docker registry will be provided.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="dockerRegistryConnection"::: -->
:::moniker range=">=azure-pipelines-2019"

**`dockerRegistryConnection`** - **Docker Registry Service Connection**<br>
Input alias: `dockerRegistryEndpoint`. Type: string. Required when configureDockerSettings = true && registryCredentials = ContainerRegistryEndpoint.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select a Docker registry service connection. Required for commands that need to authenticate with a registry.<br/>Note: task will try to encrypt the registry secret before transmitting it to service fabric cluster. However, it needs cluster's server certiticate to be installed on agent machine in order to do so. If certificate is not present, secret will not be encrypted.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`dockerRegistryConnection`** - **Docker Registry Connection**<br>
Input alias: `dockerRegistryEndpoint`. Type: string. Required when configureDockerSettings = true && registryCredentials = ContainerRegistryEndpoint.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select a Docker registry service connection. Required for commands that need to authenticate with a registry.<br/>Note: task will try to encrypt the registry secret before transmitting it to service fabric cluster. However, it needs cluster's server certiticate to be installed on agent machine in order to do so. If certificate is not present, secret will not be encrypted.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureSubscription"::: -->
:::moniker range="<=azure-pipelines"

**`azureSubscription`** - **Azure subscription**<br>
Input alias: `azureSubscriptionEndpoint`. Type: string. Required when configureDockerSettings = true && registryCredentials = AzureResourceManagerEndpoint.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select an Azure subscription.<br/>Note: task will try to encrypt the registry secret before transmitting it to service fabric cluster. However, it needs cluster's server certiticate to be installed on agent machine in order to do so. If certificate is not present, secret will not be encrypted.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="registryUserName"::: -->
:::moniker range="<=azure-pipelines"

**`registryUserName`** - **Registry User Name**<br>
Type: string. Optional. Use when configureDockerSettings = true && registryCredentials = UsernamePassword.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Username for the Docker registry.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="registryPassword"::: -->
:::moniker range="<=azure-pipelines"

**`registryPassword`** - **Registry Password**<br>
Type: string. Optional. Use when configureDockerSettings = true && registryCredentials = UsernamePassword.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Password for the Docker registry. If the password is not encrypted, it is recommended that you use a custom release pipeline secret variable to store it.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="passwordEncrypted"::: -->
:::moniker range="<=azure-pipelines"

**`passwordEncrypted`** - **Password Encrypted**<br>
Type: boolean. Optional. Use when configureDockerSettings = true && registryCredentials = UsernamePassword. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
It is recommended to encrypt your password using [Invoke-ServiceFabricEncryptText](/azure/service-fabric/service-fabric-application-secret-management#encrypt-application-secrets). If you do not, and a certificate matching the Server Certificate Thumbprint in the Cluster Service Connection is installed on the build agent, it will be used to encrypt the password; otherwise an error will occur.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ReplicaQuorumTimeoutSec"::: -->
:::moniker range="=azure-pipelines-2018"

**`ReplicaQuorumTimeoutSec`** - **ReplicaQuorumTimeoutSec**<br>
Type: string. Optional. Use when overridePublishProfileSettings = true && isUpgrade = true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

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

Use this task to deploy a Service Fabric application to a cluster. This task deploys an Azure Service Fabric application to a cluster according to the settings defined in the publish profile.

### Service Fabric

This task uses a Service Fabric installation to connect and deploy to a Service Fabric cluster. [Download and install Service Fabric](https://aka.ms/servicefabric) on the build agent.
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
| [Demands](/azure/devops/pipelines/process/demands) | Self-hosted agents must have [capabilities](/azure/devops/pipelines/agents/agents#capabilities) that match the following [demands](/azure/devops/pipelines/process/demands) to run jobs that use this task: Cmd |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.95.0 or greater |
| Task category | Deploy |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->