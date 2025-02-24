---
title: ServiceFabricDeploy@1 - Service Fabric application deployment v1 task
description: Deploy an Azure Service Fabric application to a cluster.
ms.date: 01/29/2025
monikerRange: "<=azure-pipelines"
---

# ServiceFabricDeploy@1 - Service Fabric application deployment v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to deploy a Service Fabric application to a cluster. This task deploys an Azure Service Fabric application to a cluster according to the settings defined in the publish profile.

[!INCLUDE [workload-identity](./includes/workload-identity-not-supported.md)]
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
    overwriteBehavior: 'SameAppTypeAndVersion' # 'Always' | 'Never' | 'SameAppTypeAndVersion'. Required. Overwrite Behavior. Default: SameAppTypeAndVersion.
    #skipUpgradeSameTypeAndVersion: false # boolean. Skip upgrade for same Type and Version. Default: false.
    #skipPackageValidation: false # boolean. Skip package validation. Default: false.
  # Upgrade Settings
    #useDiffPackage: false # boolean. Use Diff Package. Default: false.
    #overridePublishProfileSettings: false # boolean. Override All Publish Profile Upgrade Settings. Default: false.
    #isUpgrade: true # boolean. Optional. Use when overridePublishProfileSettings = true. Upgrade the Application. Default: true.
    #unregisterUnusedVersions: true # boolean. Unregister Unused Versions. Default: true.
    #upgradeMode: 'Monitored' # 'Monitored' | 'UnmonitoredAuto' | 'UnmonitoredManual'. Required when overridePublishProfileSettings = true && isUpgrade = true. Upgrade Mode. Default: Monitored.
    #FailureAction: 'Rollback' # 'Rollback' | 'Manual'. Required when overridePublishProfileSettings = true && isUpgrade = true && upgradeMode = Monitored. FailureAction. Default: Rollback.
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
    #registryCredentials: 'AzureResourceManagerEndpoint' # 'AzureResourceManagerEndpoint' | 'ContainerRegistryEndpoint' | 'UsernamePassword'. Required when configureDockerSettings = true. Registry Credentials Source. Default: AzureResourceManagerEndpoint.
    #dockerRegistryConnection: # string. Alias: dockerRegistryEndpoint. Required when configureDockerSettings = true && registryCredentials = ContainerRegistryEndpoint. Docker Registry Service Connection. 
    #azureSubscription: # string. Alias: azureSubscriptionEndpoint. Required when configureDockerSettings = true && registryCredentials = AzureResourceManagerEndpoint. Azure subscription. 
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
    overwriteBehavior: 'SameAppTypeAndVersion' # 'Always' | 'Never' | 'SameAppTypeAndVersion'. Required. Overwrite Behavior. Default: SameAppTypeAndVersion.
    #skipUpgradeSameTypeAndVersion: false # boolean. Skip upgrade for same Type and Version. Default: false.
    #skipPackageValidation: false # boolean. Skip package validation. Default: false.
  # Upgrade Settings
    #useDiffPackage: false # boolean. Use Diff Package. Default: false.
    #overridePublishProfileSettings: false # boolean. Override All Publish Profile Upgrade Settings. Default: false.
    #isUpgrade: true # boolean. Optional. Use when overridePublishProfileSettings = true. Upgrade the Application. Default: true.
    #unregisterUnusedVersions: true # boolean. Unregister Unused Versions. Default: true.
    #upgradeMode: 'Monitored' # 'Monitored' | 'UnmonitoredAuto' | 'UnmonitoredManual'. Required when overridePublishProfileSettings = true && isUpgrade = true. Upgrade Mode. Default: Monitored.
    #FailureAction: 'Rollback' # 'Rollback' | 'Manual'. Required when overridePublishProfileSettings = true && isUpgrade = true && upgradeMode = Monitored. FailureAction. Default: Rollback.
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
    #registryCredentials: 'AzureResourceManagerEndpoint' # 'AzureResourceManagerEndpoint' | 'ContainerRegistryEndpoint' | 'UsernamePassword'. Required when configureDockerSettings = true. Registry Credentials Source. Default: AzureResourceManagerEndpoint.
    #dockerRegistryConnection: # string. Alias: dockerRegistryEndpoint. Required when configureDockerSettings = true && registryCredentials = ContainerRegistryEndpoint. Docker Registry Service Connection. 
    #azureSubscription: # string. Alias: azureSubscriptionEndpoint. Required when configureDockerSettings = true && registryCredentials = AzureResourceManagerEndpoint. Azure subscription. 
    #registryUserName: # string. Optional. Use when configureDockerSettings = true && registryCredentials = UsernamePassword. Registry User Name. 
    #registryPassword: # string. Optional. Use when configureDockerSettings = true && registryCredentials = UsernamePassword. Registry Password. 
    #passwordEncrypted: true # boolean. Optional. Use when configureDockerSettings = true && registryCredentials = UsernamePassword. Password Encrypted. Default: true.
```

:::moniker-end


<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="applicationPackagePath"::: -->
:::moniker range="<=azure-pipelines"

**`applicationPackagePath`** - **Application Package**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the path to the application package that is to be deployed. [Variables](/azure/devops/pipelines/build/variables) and wildcards can be used in the path.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="serviceConnectionName"::: -->
:::moniker range=">=azure-pipelines-2019"

**`serviceConnectionName`** - **Cluster Service Connection**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the Azure Service Fabric service connection to be used to connect to the cluster. The settings defined in this referenced service connection override those defined in the publish profile. Choose `Manage` to register a new service connection.

To connect to the cluster, the service fabric task uses the machine cert store to store the information about the certificate. If two releases run together on one machine using the same certificate, they will start properly. However, if one of the tasks is complete, then the certificate from the machine cert store will be cleaned up, which affects the second release.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishProfilePath"::: -->
:::moniker range="<=azure-pipelines"

**`publishProfilePath`** - **Publish Profile**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Specifies the path to the publish profile file that defines the settings to use. [Variables](/azure/devops/pipelines/build/variables) and wildcards can be used in the path. Learn more about [how to create publish profiles in Visual Studio](/azure/service-fabric/service-fabric-tutorial-deploy-app#publish-the-application-to-the-cluster).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="applicationParameterPath"::: -->
:::moniker range="<=azure-pipelines"

**`applicationParameterPath`** - **Application Parameters**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Specifies the path to the application parameters file. [Variables](/azure/devops/pipelines/build/variables) and wildcards can be used in the path. If specified, this overrides the value in the publish profile. Learn more about [how to create an application parameters file in Visual Studio](/azure/service-fabric/service-fabric-manage-multiple-environment-app-configuration#specifying-parameters-during-application-creation).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="overrideApplicationParameter"::: -->
:::moniker range=">=azure-pipelines-2019"

**`overrideApplicationParameter`** - **Override Application Parameters**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Specifies the variables defined in the build or release pipeline are matched against the `Parameter Name` entries in the application manifest file. Learn more about [how to create an application parameters file in Visual Studio](/azure/service-fabric/service-fabric-manage-multiple-environment-app-configuration#specifying-parameters-during-application-creation).
 Example:
```
 <Parameters> 
 <Parameter Name="SampleApp_PartitionCount" Value="1" /> 
 <Parameter Name="SampleApp_InstanceCount" DefaultValue="-1" /> 
 </Parameters>
```
 If your application has a parameter defined as in the above example, and you want to change the partition count to `2`, you can define a release pipeline or an environment variable `SampleApp_PartitionCount` and its value as `2`.

 > [!NOTE]
> If the same variables are defined in the release pipeline and in the environment, then the environment variables will supersede the release pipeline variables.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="compressPackage"::: -->
:::moniker range="<=azure-pipelines"

**`compressPackage`** - **Compress Package**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Specifies whether the application package should be compressed before copying to the image store. If enabled, this overrides the value in the publish profile. Learn more about [compressing packages](/azure/service-fabric/service-fabric-package-apps#compress-a-package).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="copyPackageTimeoutSec"::: -->
:::moniker range="<=azure-pipelines"

**`copyPackageTimeoutSec`** - **CopyPackageTimeoutSec**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Specifies the timeout in seconds for copying application package to the image store. If specified, this overrides the value in the publish profile.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="registerPackageTimeoutSec"::: -->
:::moniker range="<=azure-pipelines"

**`registerPackageTimeoutSec`** - **RegisterPackageTimeoutSec**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Specifies the timeout in seconds for registering or un-registering an application package.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="overwriteBehavior"::: -->
:::moniker range="<=azure-pipelines"

**`overwriteBehavior`** - **Overwrite Behavior**<br>
`string`. Required. Allowed values: `Always`, `Never`, `SameAppTypeAndVersion`. Default value: `SameAppTypeAndVersion`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Overwrites behavior if an application exists in the cluster with the same name and upgrades have not been configured.

`Never` will not remove the existing application. This is the default behavior.

`Always` will remove the existing application, even if its application type and version is different from the application being created.

`SameAppTypeAndVersion` will remove the existing application only if its application type and version is the same as the application being created.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="skipUpgradeSameTypeAndVersion"::: -->
:::moniker range="<=azure-pipelines"

**`skipUpgradeSameTypeAndVersion`** - **Skip upgrade for same Type and Version**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Specifies whether an upgrade will be skipped if the same application type and version already exists in the cluster; otherwise, the upgrade fails during validation. If enabled, re-deployments are idempotent.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="skipPackageValidation"::: -->
:::moniker range="<=azure-pipelines"

**`skipPackageValidation`** - **Skip package validation**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Specifies whether the package should be validated or not before deployment. Learn more about [package validation](/azure/service-fabric/service-fabric-package-apps#test-the-package).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="useDiffPackage"::: -->
:::moniker range="<=azure-pipelines"

**`useDiffPackage`** - **Use Diff Package**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Upgrades by using a diff package that contains only the updated application files, the updated application manifest, and the service manifest files.

A diff package is created by comparing the package specified in the application package input against the package that is currently registered in the target cluster. If a service version in the cluster's current package is the same as the new package, then this service package will be removed from the new application package. Learn more about [diff packages](/azure/service-fabric/service-fabric-application-upgrade-advanced#upgrade-with-a-diff-package).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="overridePublishProfileSettings"::: -->
:::moniker range="<=azure-pipelines"

**`overridePublishProfileSettings`** - **Override All Publish Profile Upgrade Settings**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Overrides all upgrade settings with either specified values or the default value (if not specified). Learn more about [upgrade settings](/azure/service-fabric/service-fabric-application-upgrade-parameters#visual-studio-and-powershell-parameters).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="isUpgrade"::: -->
:::moniker range="<=azure-pipelines"

**`isUpgrade`** - **Upgrade the Application**<br>
`boolean`. Optional. Use when `overridePublishProfileSettings = true`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Overwrites the application if the value is set to `false`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="unregisterUnusedVersions"::: -->
:::moniker range="<=azure-pipelines"

**`unregisterUnusedVersions`** - **Unregister Unused Versions**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Indicates whether all unused versions of the application type will be removed after an upgrade.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="upgradeMode"::: -->
:::moniker range="<=azure-pipelines"

**`upgradeMode`** - **Upgrade Mode**<br>
`string`. Required when `overridePublishProfileSettings = true && isUpgrade = true`. Allowed values: `Monitored`, `UnmonitoredAuto`, `UnmonitoredManual`. Default value: `Monitored`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="FailureAction"::: -->
:::moniker range="<=azure-pipelines"

**`FailureAction`** - **FailureAction**<br>
`string`. Required when `overridePublishProfileSettings = true && isUpgrade = true && upgradeMode = Monitored`. Allowed values: `Rollback`, `Manual`. Default value: `Rollback`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="UpgradeReplicaSetCheckTimeoutSec"::: -->
:::moniker range="<=azure-pipelines"

**`UpgradeReplicaSetCheckTimeoutSec`** - **UpgradeReplicaSetCheckTimeoutSec**<br>
`string`. Optional. Use when `overridePublishProfileSettings = true && isUpgrade = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="TimeoutSec"::: -->
:::moniker range="<=azure-pipelines"

**`TimeoutSec`** - **TimeoutSec**<br>
`string`. Optional. Use when `overridePublishProfileSettings = true && isUpgrade = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ForceRestart"::: -->
:::moniker range="<=azure-pipelines"

**`ForceRestart`** - **ForceRestart**<br>
`boolean`. Optional. Use when `overridePublishProfileSettings = true && isUpgrade = true`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="HealthCheckRetryTimeoutSec"::: -->
:::moniker range="<=azure-pipelines"

**`HealthCheckRetryTimeoutSec`** - **HealthCheckRetryTimeoutSec**<br>
`string`. Optional. Use when `overridePublishProfileSettings = true && isUpgrade = true && upgradeMode = Monitored`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="HealthCheckWaitDurationSec"::: -->
:::moniker range="<=azure-pipelines"

**`HealthCheckWaitDurationSec`** - **HealthCheckWaitDurationSec**<br>
`string`. Optional. Use when `overridePublishProfileSettings = true && isUpgrade = true && upgradeMode = Monitored`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="HealthCheckStableDurationSec"::: -->
:::moniker range="<=azure-pipelines"

**`HealthCheckStableDurationSec`** - **HealthCheckStableDurationSec**<br>
`string`. Optional. Use when `overridePublishProfileSettings = true && isUpgrade = true && upgradeMode = Monitored`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="UpgradeDomainTimeoutSec"::: -->
:::moniker range="<=azure-pipelines"

**`UpgradeDomainTimeoutSec`** - **UpgradeDomainTimeoutSec**<br>
`string`. Optional. Use when `overridePublishProfileSettings = true && isUpgrade = true && upgradeMode = Monitored`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ConsiderWarningAsError"::: -->
:::moniker range="<=azure-pipelines"

**`ConsiderWarningAsError`** - **ConsiderWarningAsError**<br>
`boolean`. Optional. Use when `overridePublishProfileSettings = true && isUpgrade = true && upgradeMode = Monitored`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DefaultServiceTypeHealthPolicy"::: -->
:::moniker range="<=azure-pipelines"

**`DefaultServiceTypeHealthPolicy`** - **DefaultServiceTypeHealthPolicy**<br>
`string`. Optional. Use when `overridePublishProfileSettings = true && isUpgrade = true && upgradeMode = Monitored`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="MaxPercentUnhealthyDeployedApplications"::: -->
:::moniker range="<=azure-pipelines"

**`MaxPercentUnhealthyDeployedApplications`** - **MaxPercentUnhealthyDeployedApplications**<br>
`string`. Optional. Use when `overridePublishProfileSettings = true && isUpgrade = true && upgradeMode = Monitored`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="UpgradeTimeoutSec"::: -->
:::moniker range="<=azure-pipelines"

**`UpgradeTimeoutSec`** - **UpgradeTimeoutSec**<br>
`string`. Optional. Use when `overridePublishProfileSettings = true && isUpgrade = true && upgradeMode = Monitored`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ServiceTypeHealthPolicyMap"::: -->
:::moniker range="<=azure-pipelines"

**`ServiceTypeHealthPolicyMap`** - **ServiceTypeHealthPolicyMap**<br>
`string`. Optional. Use when `overridePublishProfileSettings = true && isUpgrade = true && upgradeMode = Monitored`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configureDockerSettings"::: -->
:::moniker range="<=azure-pipelines"

**`configureDockerSettings`** - **Configure Docker settings**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Configures the application with the specified Docker settings.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="registryCredentials"::: -->
:::moniker range=">=azure-pipelines-2019"

**`registryCredentials`** - **Registry Credentials Source**<br>
`string`. Required when `configureDockerSettings = true`. Allowed values: `AzureResourceManagerEndpoint` (Azure Resource Manager Service Connection), `ContainerRegistryEndpoint` (Container Registry Service Connection), `UsernamePassword` (Username and Password). Default value: `AzureResourceManagerEndpoint`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies how credentials for the Docker registry are provided.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="dockerRegistryConnection"::: -->
:::moniker range=">=azure-pipelines-2019"

**`dockerRegistryConnection`** - **Docker Registry Service Connection**<br>
Input alias: `dockerRegistryEndpoint`. `string`. Required when `configureDockerSettings = true && registryCredentials = ContainerRegistryEndpoint`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a Docker registry service connection. Required for commands that need to authenticate with a registry.

> [!NOTE]
> The task tries to encrypt the registry secret before transmitting it to the service fabric cluster. However, the task needs the cluster's server certificate to be installed on the agent machine. If the certificate is not present, the registry secret will not be encrypted.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureSubscription"::: -->
:::moniker range="<=azure-pipelines"

**`azureSubscription`** - **Azure subscription**<br>
Input alias: `azureSubscriptionEndpoint`. `string`. Required when `configureDockerSettings = true && registryCredentials = AzureResourceManagerEndpoint`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies an Azure subscription.

> [!NOTE]
> The task will try to encrypt the registry secret before transmitting it to the service fabric cluster. However, the task needs the cluster's server certificate to be installed on the agent machine. If the certificate is not present, the registry secret will not be encrypted.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="registryUserName"::: -->
:::moniker range="<=azure-pipelines"

**`registryUserName`** - **Registry User Name**<br>
`string`. Optional. Use when `configureDockerSettings = true && registryCredentials = UsernamePassword`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the username for the Docker registry.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="registryPassword"::: -->
:::moniker range="<=azure-pipelines"

**`registryPassword`** - **Registry Password**<br>
`string`. Optional. Use when `configureDockerSettings = true && registryCredentials = UsernamePassword`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the password for the Docker registry. If the password is not encrypted, you should use a custom release pipeline secret variable to store it.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="passwordEncrypted"::: -->
:::moniker range="<=azure-pipelines"

**`passwordEncrypted`** - **Password Encrypted**<br>
`boolean`. Optional. Use when `configureDockerSettings = true && registryCredentials = UsernamePassword`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
You should encrypt your password using [Invoke-ServiceFabricEncryptText](/azure/service-fabric/service-fabric-application-secret-management#encrypt-application-secrets). If you do not, and a certificate matching the Server Certificate Thumbprint in the Cluster Service Connection is installed on the build agent, that certificate will be used to encrypt the password; otherwise, an error will occur.
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