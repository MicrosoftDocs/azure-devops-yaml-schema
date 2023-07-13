---
title: Azure Pipelines task reference
description: Reference for the built-in tasks for Azure Pipelines & TFS.
ms.date: 07/12/2023
monikerRange: "<=azure-pipelines"
---

# Azure Pipelines task reference

A task performs an action in a pipeline. For example, a task can build an app, interact with Azure resources, install a tool, or run a test. Tasks are the building blocks for defining automation in a pipeline. The articles in this section describe the built-in tasks for Azure Pipelines.

For how-tos and tutorials about authoring pipelines using tasks, including creating custom tasks, custom extensions, and finding tasks on the Visual Studio Marketplace, see [Tasks concepts](/azure/devops/pipelines/process/tasks) and [Azure Pipelines documentation](/azure/devops/pipelines/).

> [!IMPORTANT]  
> :::row:::
>    :::column span="1":::
>       :::image type="content" source="media/version-selector.png" alt-text="Screenshot of how to select a version from Azure DevOps Content Version selector.":::
>    :::column-end:::
>    :::column span="2":::
>       To view the task reference for tasks available for your platform, make sure that you select the correct Azure DevOps version from the version selector which is located above the table of contents. Feature support differs depending on whether you are working from Azure DevOps Services or an on-premises version of Azure DevOps Server.  
>       To learn which on-premises version you are using, see [Look up your Azure DevOps platform and version](/azure/devops/user-guide/lookup-platform-version).
>    :::column-end:::
> :::row-end:::
<!-- :::taskIndex::: -->
:::moniker range="=azure-pipelines"

## Build tasks

| Task | Description |
|---|---|
| **.NET Core**<br>[DotNetCoreCLI@2](dotnet-core-cli-v2.md)<br>[DotNetCoreCLI@1](dotnet-core-cli-v1.md)<br>[DotNetCoreCLI@0](dotnet-core-cli-v0.md) | Build, test, package, or publish a dotnet application, or run a custom dotnet command. |
| **Android Build**<br>[AndroidBuild@1](android-build-v1.md) | AndroidBuild@1 is deprecated. Use Gradle. |
| **Android Signing**<br>[AndroidSigning@3](android-signing-v3.md)<br>[AndroidSigning@2](android-signing-v2.md)<br>[AndroidSigning@1](android-signing-v1.md) | Sign and align Android APK files. |
| **Ant**<br>[Ant@1](ant-v1.md) | Build with Apache Ant. |
| **Azure IoT Edge**<br>[AzureIoTEdge@2](azure-iot-edge-v2.md) | Build and deploy an Azure IoT Edge image. |
| **CMake**<br>[CMake@1](cmake-v1.md) | Build with the CMake cross-platform build system. |
| **Container Build**<br>[ContainerBuild@0](container-build-v0.md) | Container Build Task. |
| **Docker**<br>[Docker@2](docker-v2.md)<br>[Docker@1](docker-v1.md)<br>[Docker@0](docker-v0.md) | Build or push Docker images, login or logout, start or stop containers, or run a Docker command. |
| **Docker Compose**<br>[DockerCompose@0](docker-compose-v0.md) | Build, push or run multi-container Docker applications. Task can be used with Docker or Azure Container registry. |
| **Download GitHub Nuget Packages**<br>[DownloadGitHubNugetPackage@1](download-github-nuget-package-v1.md) | Restore your nuget packages using dotnet CLI. |
| **Go**<br>[Go@0](go-v0.md) | Get, build, or test a Go application, or run a custom Go command. |
| **Gradle**<br>[Gradle@3](gradle-v3.md)<br>[Gradle@2](gradle-v2.md)<br>[Gradle@1](gradle-v1.md) | Build using a Gradle wrapper script. |
| **Grunt**<br>[Grunt@0](grunt-v0.md) | Run the Grunt JavaScript task runner. |
| **gulp**<br>[gulp@1](gulp-v1.md)<br>[gulp@0](gulp-v0.md) | Run the gulp Node.js streaming task-based build system. |
| **Index sources and publish symbols**<br>[PublishSymbols@2](publish-symbols-v2.md)<br>[PublishSymbols@1](publish-symbols-v1.md) | Index your source code and publish symbols to a file share or Azure Artifacts symbol server. |
| **Jenkins queue job**<br>[JenkinsQueueJob@2](jenkins-queue-job-v2.md) | Queue a job on a Jenkins server. |
| **Jenkins Queue Job**<br>[JenkinsQueueJob@1](jenkins-queue-job-v1.md) | Queue a job on a Jenkins server. |
| **Maven**<br>[Maven@4](maven-v4.md)<br>[Maven@3](maven-v3.md)<br>[Maven@2](maven-v2.md)<br>[Maven@1](maven-v1.md) | Build, test, and deploy with Apache Maven. |
| **MSBuild**<br>[MSBuild@1](msbuild-v1.md) | Build with MSBuild. |
| **Prepare Analysis Configuration**<br>[SonarQubePrepare@5](sonar-qube-prepare-v5.md)<br>[SonarQubePrepare@4](sonar-qube-prepare-v4.md) | Prepare SonarQube analysis configuration. |
| **Publish Quality Gate Result**<br>[SonarQubePublish@5](sonar-qube-publish-v5.md)<br>[SonarQubePublish@4](sonar-qube-publish-v4.md) | Publish SonarQube's Quality Gate result on the Azure DevOps build result, to be used after the actual analysis. |
| **Run Code Analysis**<br>[SonarQubeAnalyze@5](sonar-qube-analyze-v5.md)<br>[SonarQubeAnalyze@4](sonar-qube-analyze-v4.md) | Run scanner and upload the results to the SonarQube server. |
| **Visual Studio build**<br>[VSBuild@1](vsbuild-v1.md) | Build with MSBuild and set the Visual Studio version property. |
| **Xamarin.Android**<br>[XamarinAndroid@1](xamarin-android-v1.md) | Build an Android app with Xamarin. |
| **Xamarin.iOS**<br>[XamariniOS@2](xamarin-ios-v2.md)<br>[XamariniOS@1](xamarin-ios-v1.md) | Build an iOS app with Xamarin on macOS. |
| **Xcode**<br>[Xcode@5](xcode-v5.md)<br>[Xcode@4](xcode-v4.md) | Build, test, or archive an Xcode workspace on macOS. Optionally package an app. |
| **Xcode Build**<br>[Xcode@3](xcode-v3.md)<br>[Xcode@2](xcode-v2.md) | Build an Xcode workspace on macOS. |
| **Xcode Package iOS**<br>[XcodePackageiOS@0](xcode-package-ios-v0.md) | Generate an .ipa file from Xcode build output using xcrun (Xcode 7 or below). |
## Deploy tasks

| Task | Description |
|---|---|
| **App Center distribute**<br>[AppCenterDistribute@3](app-center-distribute-v3.md)<br>[AppCenterDistribute@2](app-center-distribute-v2.md)<br>[AppCenterDistribute@1](app-center-distribute-v1.md)<br>[AppCenterDistribute@0](app-center-distribute-v0.md) | Distribute app builds to testers and users via Visual Studio App Center. |
| **ARM template deployment**<br>[AzureResourceManagerTemplateDeployment@3](azure-resource-manager-template-deployment-v3.md) | Deploy an Azure Resource Manager (ARM) template to all the deployment scopes. |
| **Azure App Service Classic (Deprecated)**<br>[AzureWebPowerShellDeployment@1](azure-web-powershell-deployment-v1.md) | Create or update Azure App Service using Azure PowerShell. |
| **Azure App Service deploy**<br>[AzureRmWebAppDeployment@4](azure-rm-web-app-deployment-v4.md)<br>[AzureRmWebAppDeployment@3](azure-rm-web-app-deployment-v3.md)<br>[AzureRmWebAppDeployment@2](azure-rm-web-app-deployment-v2.md) | Deploy to Azure App Service a web, mobile, or API app using Docker, Java, .NET, .NET Core, Node.js, PHP, Python, or Ruby. |
| **Azure App Service manage**<br>[AzureAppServiceManage@0](azure-app-service-manage-v0.md) | Start, stop, restart, slot swap, slot delete, install site extensions or enable continuous monitoring for an Azure App Service. |
| **Azure App Service Settings**<br>[AzureAppServiceSettings@1](azure-app-service-settings-v1.md) | Update/Add App settings an Azure Web App for Linux or Windows. |
| **Azure CLI**<br>[AzureCLI@2](azure-cli-v2.md)<br>[AzureCLI@1](azure-cli-v1.md) | Run Azure CLI commands against an Azure subscription in a PowerShell Core/Shell script when running on Linux agent or PowerShell/PowerShell Core/Batch script when running on Windows agent. |
| **Azure CLI Preview**<br>[AzureCLI@0](azure-cli-v0.md) | Run a Shell or Batch script with Azure CLI commands against an azure subscription. |
| **Azure Cloud Service deployment**<br>[AzureCloudPowerShellDeployment@2](azure-cloud-powershell-deployment-v2.md)<br>[AzureCloudPowerShellDeployment@1](azure-cloud-powershell-deployment-v1.md) | Deploy an Azure Cloud Service. |
| **Azure Container Apps Deploy**<br>[AzureContainerApps@1](azure-container-apps-v1.md)<br>[AzureContainerApps@0](azure-container-apps-v0.md) | An Azure DevOps Task to build and deploy Azure Container Apps. |
| **Azure Database for MySQL deployment**<br>[AzureMysqlDeployment@1](azure-mysql-deployment-v1.md) | Run your scripts and make changes to your Azure Database for MySQL. |
| **Azure file copy**<br>[AzureFileCopy@5](azure-file-copy-v5.md)<br>[AzureFileCopy@4](azure-file-copy-v4.md)<br>[AzureFileCopy@3](azure-file-copy-v3.md)<br>[AzureFileCopy@2](azure-file-copy-v2.md)<br>[AzureFileCopy@1](azure-file-copy-v1.md) | Copy files to Azure Blob Storage or virtual machines. |
| **Azure Function on Kubernetes**<br>[AzureFunctionOnKubernetes@1](azure-function-on-kubernetes-v1.md)<br>[AzureFunctionOnKubernetes@0](azure-function-on-kubernetes-v0.md) | Deploy Azure function to Kubernetes cluster. |
| **Azure Functions Deploy**<br>[AzureFunctionApp@2](azure-function-app-v2.md)<br>[AzureFunctionApp@1](azure-function-app-v1.md) | Update a function app with .NET, Python, JavaScript, PowerShell, Java based web applications. |
| **Azure Functions for container**<br>[AzureFunctionAppContainer@1](azure-function-app-container-v1.md) | Update a function app with a Docker container. |
| **Azure Key Vault**<br>[AzureKeyVault@2](azure-key-vault-v2.md)<br>[AzureKeyVault@1](azure-key-vault-v1.md) | Download Azure Key Vault secrets. |
| **Azure Monitor alerts (Deprecated)**<br>[AzureMonitorAlerts@0](azure-monitor-alerts-v0.md) | Configure alerts on available metrics for an Azure resource (Deprecated). |
| **Azure PowerShell**<br>[AzurePowerShell@5](azure-powershell-v5.md)<br>[AzurePowerShell@4](azure-powershell-v4.md)<br>[AzurePowerShell@3](azure-powershell-v3.md)<br>[AzurePowerShell@2](azure-powershell-v2.md)<br>[AzurePowerShell@1](azure-powershell-v1.md) | Run a PowerShell script within an Azure environment. |
| **Azure resource group deployment**<br>[AzureResourceGroupDeployment@2](azure-resource-group-deployment-v2.md) | Deploy an Azure Resource Manager (ARM) template to a resource group and manage virtual machines. |
| **Azure Resource Group Deployment**<br>[AzureResourceGroupDeployment@1](azure-resource-group-deployment-v1.md) | Deploy, start, stop, delete Azure Resource Groups. |
| **Azure Spring Apps**<br>[AzureSpringCloud@0](azure-spring-cloud-v0.md) | Deploy applications to Azure Spring Apps and manage deployments. |
| **Azure SQL Database deployment**<br>[SqlAzureDacpacDeployment@1](sql-azure-dacpac-deployment-v1.md) | Deploy an Azure SQL Database using DACPAC or run scripts using SQLCMD. |
| **Azure VM scale set deployment**<br>[AzureVmssDeployment@0](azure-vmss-deployment-v0.md) | Deploy a virtual machine scale set image. |
| **Azure Web App**<br>[AzureWebApp@1](azure-web-app-v1.md) | Deploy an Azure Web App for Linux or Windows. |
| **Azure Web App for Containers**<br>[AzureWebAppContainer@1](azure-web-app-container-v1.md) | Deploy containers to Azure App Service. |
| **Build machine image**<br>[PackerBuild@1](packer-build-v1.md)<br>[PackerBuild@0](packer-build-v0.md) | Build a machine image using Packer, which may be used for Azure Virtual machine scale set deployment. |
| **Check Azure Policy compliance**<br>[AzurePolicyCheckGate@0](azure-policy-check-gate-v0.md) | Security and compliance assessment for Azure Policy. |
| **Chef**<br>[Chef@1](chef-v1.md) | Deploy to Chef environments by editing environment attributes. |
| **Chef Knife**<br>[ChefKnife@1](chef-knife-v1.md) | Run scripts with Knife commands on your Chef workstation. |
| **Copy files over SSH**<br>[CopyFilesOverSSH@0](copy-files-over-ssh-v0.md) | Copy files or build artifacts to a remote machine over SSH. |
| **Deploy to Kubernetes**<br>[KubernetesManifest@1](kubernetes-manifest-v1.md)<br>[KubernetesManifest@0](kubernetes-manifest-v0.md) | Use Kubernetes manifest files to deploy to clusters or even bake the manifest files to be used for deployments using Helm charts. |
| **IIS web app deploy**<br>[IISWebAppDeploymentOnMachineGroup@0](iisweb-app-deployment-on-machine-group-v0.md) | Deploy a website or web application using Web Deploy. |
| **IIS Web App deployment (Deprecated)**<br>[IISWebAppDeployment@1](iisweb-app-deployment-v1.md) | Deploy using MSDeploy, then create/update websites and app pools. |
| **IIS web app manage**<br>[IISWebAppManagementOnMachineGroup@0](iisweb-app-management-on-machine-group-v0.md) | Create or update websites, web apps, virtual directories, or application pools. |
| **Invoke REST API**<br>[InvokeRESTAPI@1](invoke-rest-api-v1.md)<br>[InvokeRESTAPI@0](invoke-rest-api-v0.md) | Invoke a REST API as a part of your pipeline. |
| **Kubectl**<br>[Kubernetes@1](kubernetes-v1.md)<br>[Kubernetes@0](kubernetes-v0.md) | Deploy, configure, update a Kubernetes cluster in Azure Container Service by running kubectl commands. |
| **Manual intervention**<br>[ManualIntervention@8](manual-intervention-v8.md) | Pause deployment and wait for manual intervention. |
| **Manual validation**<br>[ManualValidation@0](manual-validation-v0.md) | [PREVIEW] Pause a pipeline run to wait for manual interaction. Works only with YAML pipelines. |
| **MySQL database deploy**<br>[MysqlDeploymentOnMachineGroup@1](mysql-deployment-on-machine-group-v1.md) | Run scripts and make changes to a MySQL Database. |
| **Package and deploy Helm charts**<br>[HelmDeploy@0](helm-deploy-v0.md) | Deploy, configure, update a Kubernetes cluster in Azure Container Service by running helm commands. |
| **PowerShell on target machines**<br>[PowerShellOnTargetMachines@3](powershell-on-target-machines-v3.md) | Execute PowerShell scripts on remote machines using PSSession and Invoke-Command for remoting. |
| **PowerShell on Target Machines**<br>[PowerShellOnTargetMachines@2](powershell-on-target-machines-v2.md)<br>[PowerShellOnTargetMachines@1](powershell-on-target-machines-v1.md) | Execute PowerShell scripts on remote machine(s). |
| **Service Fabric application deployment**<br>[ServiceFabricDeploy@1](service-fabric-deploy-v1.md) | Deploy an Azure Service Fabric application to a cluster. |
| **Service Fabric Compose deploy**<br>[ServiceFabricComposeDeploy@0](service-fabric-compose-deploy-v0.md) | Deploy a Docker Compose application to an Azure Service Fabric cluster. |
| **SQL Server database deploy**<br>[SqlDacpacDeploymentOnMachineGroup@0](sql-dacpac-deployment-on-machine-group-v0.md) | Deploy a SQL Server database using DACPAC or SQL scripts. |
| **SQL Server database deploy (Deprecated)**<br>[SqlServerDacpacDeployment@1](sql-server-dacpac-deployment-v1.md) | Deploy a SQL Server database using DACPAC. |
| **SSH**<br>[SSH@0](ssh-v0.md) | Run shell commands or a script on a remote machine using SSH. |
| **Windows machine file copy**<br>[WindowsMachineFileCopy@2](windows-machine-file-copy-v2.md)<br>[WindowsMachineFileCopy@1](windows-machine-file-copy-v1.md) | Copy files to remote Windows machines. |
## Package tasks

| Task | Description |
|---|---|
| **CocoaPods**<br>[CocoaPods@0](cocoa-pods-v0.md) | Install CocoaPods dependencies for Swift and Objective-C Cocoa projects. |
| **Conda environment**<br>[CondaEnvironment@1](conda-environment-v1.md)<br>[CondaEnvironment@0](conda-environment-v0.md) | This task is deprecated. Use `conda` directly in script to work with Anaconda environments. |
| **Download Github Npm Package**<br>[DownloadGithubNpmPackage@1](download-github-npm-package-v1.md) | Install npm packages from GitHub. |
| **Maven Authenticate**<br>[MavenAuthenticate@0](maven-authenticate-v0.md) | Provides credentials for Azure Artifacts feeds and external maven repositories. |
| **npm**<br>[Npm@1](npm-v1.md)<br>[Npm@0](npm-v0.md) | Install and publish npm packages, or run an npm command. Supports npmjs.com and authenticated registries like Azure Artifacts. |
| **npm authenticate (for task runners)**<br>[npmAuthenticate@0](npm-authenticate-v0.md) | Don't use this task if you're also using the npm task. Provides npm credentials to an .npmrc file in your repository for the scope of the build. This enables npm task runners like gulp and Grunt to authenticate with private registries. |
| **NuGet**<br>[NuGetCommand@2](nuget-command-v2.md) | Restore, pack, or push NuGet packages, or run a NuGet command. Supports NuGet.org and authenticated feeds like Azure Artifacts and MyGet. Uses NuGet.exe and works with .NET Framework apps. For .NET Core and .NET Standard apps, use the .NET Core task. |
| **NuGet authenticate**<br>[NuGetAuthenticate@1](nuget-authenticate-v1.md)<br>[NuGetAuthenticate@0](nuget-authenticate-v0.md) | Configure NuGet tools to authenticate with Azure Artifacts and other NuGet repositories. Requires NuGet >= 4.8.5385, dotnet >= 6, or MSBuild >= 15.8.166.59604. |
| **NuGet command**<br>[NuGet@0](nuget-v0.md) | Deprecated: use the “NuGet” task instead. It works with the new Tool Installer framework so you can easily use new versions of NuGet without waiting for a task update, provides better support for authenticated feeds outside this organization/collection, and uses NuGet 4 by default. |
| **NuGet Installer**<br>[NuGetInstaller@0](nuget-installer-v0.md) | Installs or restores missing NuGet packages. Use NuGetAuthenticate@0 task for latest capabilities. |
| **NuGet packager**<br>[NuGetPackager@0](nuget-packager-v0.md) | Deprecated: use the “NuGet” task instead. It works with the new Tool Installer framework so you can easily use new versions of NuGet without waiting for a task update, provides better support for authenticated feeds outside this organization/collection, and uses NuGet 4 by default. |
| **NuGet publisher**<br>[NuGetPublisher@0](nuget-publisher-v0.md) | Deprecated: use the “NuGet” task instead. It works with the new Tool Installer framework so you can easily use new versions of NuGet without waiting for a task update, provides better support for authenticated feeds outside this organization/collection, and uses NuGet 4 by default. |
| **NuGet Restore**<br>[NuGetRestore@1](nuget-restore-v1.md) | Restores NuGet packages in preparation for a Visual Studio Build step. |
| **PyPI publisher**<br>[PyPIPublisher@0](py-pi-publisher-v0.md) | Create and upload an sdist or wheel to a PyPI-compatible index using Twine. |
| **Python pip authenticate**<br>[PipAuthenticate@1](pip-authenticate-v1.md)<br>[PipAuthenticate@0](pip-authenticate-v0.md) | Authentication task for the pip client used for installing Python distributions. |
| **Python twine upload authenticate**<br>[TwineAuthenticate@1](twine-authenticate-v1.md)<br>[TwineAuthenticate@0](twine-authenticate-v0.md) | Authenticate for uploading Python distributions using twine. Add '-r FeedName/EndpointName --config-file $(PYPIRC_PATH)' to your twine upload command. For feeds present in this organization, use the feed name as the repository (-r). Otherwise, use the endpoint name defined in the service connection. |
| **Universal packages**<br>[UniversalPackages@0](universal-packages-v0.md) | Download or publish Universal Packages. |
| **Xamarin Component Restore**<br>[XamarinComponentRestore@0](xamarin-component-restore-v0.md) | This task is deprecated. Use 'NuGet' instead. |
## Test tasks

| Task | Description |
|---|---|
| **App Center test**<br>[AppCenterTest@1](app-center-test-v1.md) | Test app packages with Visual Studio App Center. |
| **Azure Load Testing**<br>[AzureLoadTest@1](azure-load-test-v1.md) | Automate performance regression testing with Azure Load Testing. |
| **Container Structure Test**<br>[ContainerStructureTest@0](container-structure-test-v0.md) | Uses container-structure-test (https://github.com/GoogleContainerTools/container-structure-test) to validate the structure of an image based on four categories of tests - command tests, file existence tests, file content tests and metadata tests. |
| **Mobile Center Test**<br>[VSMobileCenterTest@0](vsmobile-center-test-v0.md) | Test mobile app packages with Visual Studio Mobile Center. |
| **Publish code coverage results**<br>[PublishCodeCoverageResults@2](publish-code-coverage-results-v2.md)<br>[PublishCodeCoverageResults@1](publish-code-coverage-results-v1.md) | Publish any of the code coverage results from a build. |
| **Publish test results**<br>[PublishTestResults@1](publish-test-results-v1.md) | Publish test results to Azure Pipelines. |
| **Publish Test Results**<br>[PublishTestResults@2](publish-test-results-v2.md) | Publish test results to Azure Pipelines. |
| **Run functional tests**<br>[RunVisualStudioTestsusingTestAgent@1](run-visual-studio-testsusing-test-agent-v1.md) | Deprecated: This task and it’s companion task (Visual Studio Test Agent Deployment) are deprecated. Use the 'Visual Studio Test' task instead. The VSTest task can run unit as well as functional tests. Run tests on one or more agents using the multi-agent job setting. Use the 'Visual Studio Test Platform' task to run tests without needing Visual Studio on the agent. VSTest task also brings new capabilities such as automatically rerunning failed tests. |
| **Visual Studio Test**<br>[VSTest@2](vstest-v2.md)<br>[VSTest@1](vstest-v1.md) | Run unit and functional tests (Selenium, Appium, Coded UI test, etc.) using the Visual Studio Test (VsTest) runner. Test frameworks that have a Visual Studio test adapter such as MsTest, xUnit, NUnit, Chutzpah (for JavaScript tests using QUnit, Mocha and Jasmine), etc. can be run. Tests can be distributed on multiple agents using this task (version 2). |
| **Visual Studio test agent deployment**<br>[DeployVisualStudioTestAgent@2](deploy-visual-studio-test-agent-v2.md) | DeployVisualStudioTestAgent@2 is deprecated. Use the Visual Studio Test task to run unit and functional tests. |
| **Visual Studio Test Agent Deployment**<br>[DeployVisualStudioTestAgent@1](deploy-visual-studio-test-agent-v1.md) | Deploy and configure Test Agent to run tests on a set of machines. |
| **Xamarin Test Cloud**<br>[XamarinTestCloud@1](xamarin-test-cloud-v1.md) | [Deprecated] Test mobile apps with Xamarin Test Cloud using Xamarin.UITest. Instead, use the 'App Center test' task. |
## Tool tasks

| Task | Description |
|---|---|
| **.NET Core SDK/runtime installer**<br>[DotNetCoreInstaller@1](dotnet-core-installer-v1.md)<br>[DotNetCoreInstaller@0](dotnet-core-installer-v0.md) | Acquire a specific version of the .NET Core SDK from the internet or local cache and add it to the PATH. |
| **Docker CLI installer**<br>[DockerInstaller@0](docker-installer-v0.md) | Install Docker CLI on agent machine. |
| **Duffle tool installer**<br>[DuffleInstaller@0](duffle-installer-v0.md) | Install a specified version of Duffle for installing and managing CNAB bundles. |
| **Go tool installer**<br>[GoTool@0](go-tool-v0.md) | Find in cache or download a specific version of Go and add it to the PATH. |
| **Helm tool installer**<br>[HelmInstaller@1](helm-installer-v1.md)<br>[HelmInstaller@0](helm-installer-v0.md) | Install Helm on an agent machine. |
| **Install Azure Func Core Tools**<br>[FuncToolsInstaller@0](func-tools-installer-v0.md) | Install Azure Func Core Tools. |
| **Java tool installer**<br>[JavaToolInstaller@0](java-tool-installer-v0.md) | Acquire a specific version of Java from a user-supplied Azure blob or the tool cache and sets JAVA_HOME. |
| **Kubectl tool installer**<br>[KubectlInstaller@0](kubectl-installer-v0.md) | Install Kubectl on agent machine. |
| **Kubelogin tool installer**<br>[KubeloginInstaller@0](kubelogin-installer-v0.md) | Helps to install kubelogin. |
| **Node.js tool installer**<br>[NodeTool@0](node-tool-v0.md) | Finds or downloads and caches the specified version spec of Node.js and adds it to the PATH. |
| **NuGet tool installer**<br>[NuGetToolInstaller@1](nuget-tool-installer-v1.md)<br>[NuGetToolInstaller@0](nuget-tool-installer-v0.md) | Acquires a specific version of NuGet from the internet or the tools cache and adds it to the PATH. Use this task to change the version of NuGet used in the NuGet tasks. |
| **Use .NET Core**<br>[UseDotNet@2](use-dotnet-v2.md) | Acquires a specific version of the .NET Core SDK from the internet or the local cache and adds it to the PATH. Use this task to change the version of .NET Core used in subsequent tasks. Additionally provides proxy support. |
| **Use Node.js ecosystem**<br>[UseNode@1](use-node-v1.md) | Set up a Node.js environment and add it to the PATH, additionally providing proxy support. |
| **Use Python version**<br>[UsePythonVersion@0](use-python-version-v0.md) | Use the specified version of Python from the tool cache, optionally adding it to the PATH. |
| **Use Ruby version**<br>[UseRubyVersion@0](use-ruby-version-v0.md) | Use the specified version of Ruby from the tool cache, optionally adding it to the PATH. |
| **Visual Studio test platform installer**<br>[VisualStudioTestPlatformInstaller@1](visual-studio-test-platform-installer-v1.md) | Acquire the test platform from nuget.org or the tool cache. Satisfies the ‘vstest’ demand and can be used for running tests and collecting diagnostic data using the Visual Studio Test task. |
## Utility tasks

| Task | Description |
|---|---|
| **Archive files**<br>[ArchiveFiles@2](archive-files-v2.md) | Compress files into .7z, .tar.gz, or .zip. |
| **Archive Files**<br>[ArchiveFiles@1](archive-files-v1.md) | Archive files using compression formats such as .7z, .rar, .tar.gz, and .zip. |
| **Azure Network Load Balancer**<br>[AzureNLBManagement@1](azure-nlb-management-v1.md) | Connect or disconnect an Azure virtual machine's network interface to a Load Balancer's back end address pool. |
| **Bash**<br>[Bash@3](bash-v3.md) | Run a Bash script on macOS, Linux, or Windows. |
| **Batch script**<br>[BatchScript@1](batch-script-v1.md) | Run a Windows command or batch script and optionally allow it to change the environment. |
| **Cache**<br>[Cache@2](cache-v2.md) | Cache files between runs. |
| **Cache (Beta)**<br>[CacheBeta@1](cache-beta-v1.md)<br>[CacheBeta@0](cache-beta-v0.md) | Cache files between runs. |
| **Command Line**<br>[CmdLine@2](cmd-line-v2.md)<br>[CmdLine@1](cmd-line-v1.md) | Run a command line script using Bash on Linux and macOS and cmd.exe on Windows. |
| **Copy and Publish Build Artifacts**<br>[CopyPublishBuildArtifacts@1](copy-publish-build-artifacts-v1.md) | CopyPublishBuildArtifacts@1 is deprecated. Use the Copy Files task and the Publish Build Artifacts task instead. |
| **Copy files**<br>[CopyFiles@2](copy-files-v2.md) | Copy files from a source folder to a target folder using patterns matching file paths (not folder paths). |
| **Copy Files**<br>[CopyFiles@1](copy-files-v1.md) | Copy files from source folder to target folder using minimatch patterns (The minimatch patterns will only match file paths, not folder paths). |
| **cURL Upload Files**<br>[cURLUploader@2](curl-uploader-v2.md)<br>[cURLUploader@1](curl-uploader-v1.md) | Use cURL's supported protocols to upload files. |
| **Decrypt file (OpenSSL)**<br>[DecryptFile@1](decrypt-file-v1.md) | Decrypt a file using OpenSSL. |
| **Delay**<br>[Delay@1](delay-v1.md) | Delay further execution of a workflow by a fixed time. |
| **Delete files**<br>[DeleteFiles@1](delete-files-v1.md) | Delete folders, or files matching a pattern. |
| **Deploy Azure Static Web App**<br>[AzureStaticWebApp@0](azure-static-web-app-v0.md) | Build and deploy an Azure Static Web App. |
| **Download artifacts from file share**<br>[DownloadFileshareArtifacts@1](download-fileshare-artifacts-v1.md) | Download artifacts from a file share, like \\share\drop. |
| **Download build artifacts**<br>[DownloadBuildArtifacts@1](download-build-artifacts-v1.md)<br>[DownloadBuildArtifacts@0](download-build-artifacts-v0.md) | Download files that were saved as artifacts of a completed build. |
| **Download GitHub Release**<br>[DownloadGitHubRelease@0](download-github-release-v0.md) | Downloads a GitHub Release from a repository. |
| **Download package**<br>[DownloadPackage@1](download-package-v1.md)<br>[DownloadPackage@0](download-package-v0.md) | Download a package from a package management feed in Azure Artifacts. |
| **Download Pipeline Artifacts**<br>[DownloadPipelineArtifact@2](download-pipeline-artifact-v2.md)<br>[DownloadPipelineArtifact@1](download-pipeline-artifact-v1.md)<br>[DownloadPipelineArtifact@0](download-pipeline-artifact-v0.md) | Download build and pipeline artifacts. |
| **Download secure file**<br>[DownloadSecureFile@1](download-secure-file-v1.md) | Download a secure file to the agent machine. |
| **Extract files**<br>[ExtractFiles@1](extract-files-v1.md) | Extract a variety of archive and compression files such as .7z, .rar, .tar.gz, and .zip. |
| **File transform**<br>[FileTransform@2](file-transform-v2.md)<br>[FileTransform@1](file-transform-v1.md) | Replace tokens with variable values in XML or JSON configuration files. |
| **FTP upload**<br>[FtpUpload@2](ftp-upload-v2.md)<br>[FtpUpload@1](ftp-upload-v1.md) | Upload files using FTP. |
| **GitHub Comment**<br>[GitHubComment@0](github-comment-v0.md) | Write a comment to your GitHub entity i.e. issue or a pull request (PR). |
| **GitHub Release**<br>[GitHubRelease@1](github-release-v1.md)<br>[GitHubRelease@0](github-release-v0.md) | Create, edit, or delete a GitHub release. |
| **Install Apple certificate**<br>[InstallAppleCertificate@2](install-apple-certificate-v2.md) | Install an Apple certificate required to build on a macOS agent machine. |
| **Install Apple Certificate**<br>[InstallAppleCertificate@1](install-apple-certificate-v1.md)<br>[InstallAppleCertificate@0](install-apple-certificate-v0.md) | Install an Apple certificate required to build on a macOS agent. |
| **Install Apple provisioning profile**<br>[InstallAppleProvisioningProfile@1](install-apple-provisioning-profile-v1.md) | Install an Apple provisioning profile required to build on a macOS agent machine. |
| **Install Apple Provisioning Profile**<br>[InstallAppleProvisioningProfile@0](install-apple-provisioning-profile-v0.md) | Install an Apple provisioning profile required to build on a macOS agent. |
| **Install SSH key**<br>[InstallSSHKey@0](install-ssh-key-v0.md) | Install an SSH key prior to a build or deployment. |
| **Invoke Azure Function**<br>[AzureFunction@1](azure-function-v1.md)<br>[AzureFunction@0](azure-function-v0.md) | Invoke an Azure Function. |
| **Jenkins download artifacts**<br>[JenkinsDownloadArtifacts@1](jenkins-download-artifacts-v1.md) | Download artifacts produced by a Jenkins job. |
| **Node.js tasks runner installer**<br>[NodeTaskRunnerInstaller@0](node-task-runner-installer-v0.md) | Install specific Node.js version to run node tasks. |
| **PowerShell**<br>[PowerShell@2](powershell-v2.md)<br>[PowerShell@1](powershell-v1.md) | Run a PowerShell script on Linux, macOS, or Windows. |
| **Publish build artifacts**<br>[PublishBuildArtifacts@1](publish-build-artifacts-v1.md) | Publish build artifacts to Azure Pipelines or a Windows file share. |
| **Publish Pipeline Artifacts**<br>[PublishPipelineArtifact@1](publish-pipeline-artifact-v1.md)<br>[PublishPipelineArtifact@0](publish-pipeline-artifact-v0.md) | Publish (upload) a file or directory as a named artifact for the current run. |
| **Publish Pipeline Metadata**<br>[PublishPipelineMetadata@0](publish-pipeline-metadata-v0.md) | Publish Pipeline Metadata to Evidence store. |
| **Publish To Azure Service Bus**<br>[PublishToAzureServiceBus@1](publish-to-azure-service-bus-v1.md)<br>[PublishToAzureServiceBus@0](publish-to-azure-service-bus-v0.md) | Sends a message to Azure Service Bus using a service connection (no agent is required). |
| **Python script**<br>[PythonScript@0](python-script-v0.md) | Run a Python file or inline script. |
| **Query Azure Monitor alerts**<br>[AzureMonitor@1](azure-monitor-v1.md) | Observe the configured Azure Monitor rules for active alerts. |
| **Query Classic Azure Monitor alerts**<br>[AzureMonitor@0](azure-monitor-v0.md) | Observe the configured classic Azure Monitor rules for active alerts. |
| **Query work items**<br>[queryWorkItems@0](query-work-items-v0.md) | Execute a work item query and check the number of items returned. |
| **Review App**<br>[ReviewApp@0](review-app-v0.md) | Use this task under deploy phase provider to create a resource dynamically. |
| **Service Fabric PowerShell**<br>[ServiceFabricPowerShell@1](service-fabric-powershell-v1.md) | Run a PowerShell script in the context of an Azure Service Fabric cluster connection. |
| **Shell script**<br>[ShellScript@2](shell-script-v2.md) | Run a shell script using Bash. |
| **Update Service Fabric App Versions**<br>[ServiceFabricUpdateAppVersions@1](service-fabric-update-app-versions-v1.md) | Automatically updates the versions of a packaged Service Fabric application. |
| **Update Service Fabric manifests**<br>[ServiceFabricUpdateManifests@2](service-fabric-update-manifests-v2.md) | Automatically update portions of application and service manifests in a packaged Azure Service Fabric application. |
| **Xamarin License**<br>[XamarinLicense@1](xamarin-license-v1.md) | [Deprecated] Upgrade to free version of Xamarin: https://store.xamarin.com. |

:::moniker-end

:::moniker range="=azure-pipelines-2022"

## Build tasks

| Task | Description |
|---|---|
| **.NET Core**<br>[DotNetCoreCLI@2](dotnet-core-cli-v2.md)<br>[DotNetCoreCLI@1](dotnet-core-cli-v1.md)<br>[DotNetCoreCLI@0](dotnet-core-cli-v0.md) | Build, test, package, or publish a dotnet application, or run a custom dotnet command. |
| **Android Build**<br>[AndroidBuild@1](android-build-v1.md) | AndroidBuild@1 is deprecated. Use Gradle. |
| **Android Signing**<br>[AndroidSigning@3](android-signing-v3.md)<br>[AndroidSigning@2](android-signing-v2.md)<br>[AndroidSigning@1](android-signing-v1.md) | Sign and align Android APK files. |
| **Ant**<br>[Ant@1](ant-v1.md) | Build with Apache Ant. |
| **Azure IoT Edge**<br>[AzureIoTEdge@2](azure-iot-edge-v2.md) | Build and deploy an Azure IoT Edge image. |
| **CMake**<br>[CMake@1](cmake-v1.md) | Build with the CMake cross-platform build system. |
| **Container Build**<br>[ContainerBuild@0](container-build-v0.md) | Container Build Task. |
| **Docker**<br>[Docker@2](docker-v2.md)<br>[Docker@1](docker-v1.md)<br>[Docker@0](docker-v0.md) | Build or push Docker images, login or logout, start or stop containers, or run a Docker command. |
| **Docker Compose**<br>[DockerCompose@0](docker-compose-v0.md) | Build, push or run multi-container Docker applications. Task can be used with Docker or Azure Container registry. |
| **Download GitHub Nuget Packages**<br>[DownloadGitHubNugetPackage@1](download-github-nuget-package-v1.md) | Restore your nuget packages using dotnet CLI. |
| **Go**<br>[Go@0](go-v0.md) | Get, build, or test a Go application, or run a custom Go command. |
| **Gradle**<br>[Gradle@3](gradle-v3.md)<br>[Gradle@2](gradle-v2.md)<br>[Gradle@1](gradle-v1.md) | Build using a Gradle wrapper script. |
| **Grunt**<br>[Grunt@0](grunt-v0.md) | Run the Grunt JavaScript task runner. |
| **gulp**<br>[gulp@1](gulp-v1.md)<br>[gulp@0](gulp-v0.md) | Run the gulp Node.js streaming task-based build system. |
| **Index sources and publish symbols**<br>[PublishSymbols@2](publish-symbols-v2.md)<br>[PublishSymbols@1](publish-symbols-v1.md) | Index your source code and publish symbols to a file share or Azure Artifacts symbol server. |
| **Jenkins queue job**<br>[JenkinsQueueJob@2](jenkins-queue-job-v2.md) | Queue a job on a Jenkins server. |
| **Jenkins Queue Job**<br>[JenkinsQueueJob@1](jenkins-queue-job-v1.md) | Queue a job on a Jenkins server. |
| **Maven**<br>[Maven@3](maven-v3.md)<br>[Maven@2](maven-v2.md)<br>[Maven@1](maven-v1.md) | Build, test, and deploy with Apache Maven. |
| **MSBuild**<br>[MSBuild@1](msbuild-v1.md) | Build with MSBuild. |
| **Visual Studio build**<br>[VSBuild@1](vsbuild-v1.md) | Build with MSBuild and set the Visual Studio version property. |
| **Xamarin.Android**<br>[XamarinAndroid@1](xamarin-android-v1.md) | Build an Android app with Xamarin. |
| **Xamarin.iOS**<br>[XamariniOS@2](xamarin-ios-v2.md)<br>[XamariniOS@1](xamarin-ios-v1.md) | Build an iOS app with Xamarin on macOS. |
| **Xcode**<br>[Xcode@5](xcode-v5.md)<br>[Xcode@4](xcode-v4.md) | Build, test, or archive an Xcode workspace on macOS. Optionally package an app. |
| **Xcode Build**<br>[Xcode@3](xcode-v3.md)<br>[Xcode@2](xcode-v2.md) | Build an Xcode workspace on macOS. |
| **Xcode Package iOS**<br>[XcodePackageiOS@0](xcode-package-ios-v0.md) | Generate an .ipa file from Xcode build output using xcrun (Xcode 7 or below). |
## Deploy tasks

| Task | Description |
|---|---|
| **App Center distribute**<br>[AppCenterDistribute@3](app-center-distribute-v3.md)<br>[AppCenterDistribute@2](app-center-distribute-v2.md)<br>[AppCenterDistribute@1](app-center-distribute-v1.md)<br>[AppCenterDistribute@0](app-center-distribute-v0.md) | Distribute app builds to testers and users via Visual Studio App Center. |
| **ARM template deployment**<br>[AzureResourceManagerTemplateDeployment@3](azure-resource-manager-template-deployment-v3.md) | Deploy an Azure Resource Manager (ARM) template to all the deployment scopes. |
| **Azure App Service Classic (Deprecated)**<br>[AzureWebPowerShellDeployment@1](azure-web-powershell-deployment-v1.md) | Create or update Azure App Service using Azure PowerShell. |
| **Azure App Service deploy**<br>[AzureRmWebAppDeployment@4](azure-rm-web-app-deployment-v4.md)<br>[AzureRmWebAppDeployment@3](azure-rm-web-app-deployment-v3.md)<br>[AzureRmWebAppDeployment@2](azure-rm-web-app-deployment-v2.md) | Deploy to Azure App Service a web, mobile, or API app using Docker, Java, .NET, .NET Core, Node.js, PHP, Python, or Ruby. |
| **Azure App Service manage**<br>[AzureAppServiceManage@0](azure-app-service-manage-v0.md) | Start, stop, restart, slot swap, slot delete, install site extensions or enable continuous monitoring for an Azure App Service. |
| **Azure App Service Settings**<br>[AzureAppServiceSettings@1](azure-app-service-settings-v1.md) | Update/Add App settings an Azure Web App for Linux or Windows. |
| **Azure CLI**<br>[AzureCLI@2](azure-cli-v2.md)<br>[AzureCLI@1](azure-cli-v1.md) | Run Azure CLI commands against an Azure subscription in a PowerShell Core/Shell script when running on Linux agent or PowerShell/PowerShell Core/Batch script when running on Windows agent. |
| **Azure CLI Preview**<br>[AzureCLI@0](azure-cli-v0.md) | Run a Shell or Batch script with Azure CLI commands against an azure subscription. |
| **Azure Cloud Service deployment**<br>[AzureCloudPowerShellDeployment@1](azure-cloud-powershell-deployment-v1.md) | Deploy an Azure Cloud Service. |
| **Azure Database for MySQL deployment**<br>[AzureMysqlDeployment@1](azure-mysql-deployment-v1.md) | Run your scripts and make changes to your Azure Database for MySQL. |
| **Azure file copy**<br>[AzureFileCopy@4](azure-file-copy-v4.md)<br>[AzureFileCopy@3](azure-file-copy-v3.md)<br>[AzureFileCopy@2](azure-file-copy-v2.md)<br>[AzureFileCopy@1](azure-file-copy-v1.md) | Copy files to Azure Blob Storage or virtual machines. |
| **Azure Function on Kubernetes**<br>[AzureFunctionOnKubernetes@0](azure-function-on-kubernetes-v0.md) | Deploy Azure function to Kubernetes cluster. |
| **Azure Functions Deploy**<br>[AzureFunctionApp@1](azure-function-app-v1.md) | Update a function app with .NET, Python, JavaScript, PowerShell, Java based web applications. |
| **Azure Functions for container**<br>[AzureFunctionAppContainer@1](azure-function-app-container-v1.md) | Update a function app with a Docker container. |
| **Azure Key Vault**<br>[AzureKeyVault@2](azure-key-vault-v2.md)<br>[AzureKeyVault@1](azure-key-vault-v1.md) | Download Azure Key Vault secrets. |
| **Azure Monitor alerts (Deprecated)**<br>[AzureMonitorAlerts@0](azure-monitor-alerts-v0.md) | Configure alerts on available metrics for an Azure resource (Deprecated). |
| **Azure PowerShell**<br>[AzurePowerShell@5](azure-powershell-v5.md)<br>[AzurePowerShell@4](azure-powershell-v4.md)<br>[AzurePowerShell@3](azure-powershell-v3.md)<br>[AzurePowerShell@2](azure-powershell-v2.md)<br>[AzurePowerShell@1](azure-powershell-v1.md) | Run a PowerShell script within an Azure environment. |
| **Azure resource group deployment**<br>[AzureResourceGroupDeployment@2](azure-resource-group-deployment-v2.md) | Deploy an Azure Resource Manager (ARM) template to a resource group and manage virtual machines. |
| **Azure Resource Group Deployment**<br>[AzureResourceGroupDeployment@1](azure-resource-group-deployment-v1.md) | Deploy, start, stop, delete Azure Resource Groups. |
| **Azure Spring Cloud**<br>[AzureSpringCloud@0](azure-spring-cloud-v0.md) | Deploy applications to Azure Spring Cloud and manage deployments. |
| **Azure SQL Database deployment**<br>[SqlAzureDacpacDeployment@1](sql-azure-dacpac-deployment-v1.md) | Deploy an Azure SQL Database using DACPAC or run scripts using SQLCMD. |
| **Azure VM scale set deployment**<br>[AzureVmssDeployment@0](azure-vmss-deployment-v0.md) | Deploy a virtual machine scale set image. |
| **Azure Web App**<br>[AzureWebApp@1](azure-web-app-v1.md) | Deploy an Azure Web App for Linux or Windows. |
| **Azure Web App for Containers**<br>[AzureWebAppContainer@1](azure-web-app-container-v1.md) | Deploy containers to Azure App Service. |
| **Build machine image**<br>[PackerBuild@1](packer-build-v1.md)<br>[PackerBuild@0](packer-build-v0.md) | Build a machine image using Packer, which may be used for Azure Virtual machine scale set deployment. |
| **Check Azure Policy compliance**<br>[AzurePolicyCheckGate@0](azure-policy-check-gate-v0.md) | Security and compliance assessment for Azure Policy. |
| **Chef**<br>[Chef@1](chef-v1.md) | Deploy to Chef environments by editing environment attributes. |
| **Chef Knife**<br>[ChefKnife@1](chef-knife-v1.md) | Run scripts with Knife commands on your Chef workstation. |
| **Copy files over SSH**<br>[CopyFilesOverSSH@0](copy-files-over-ssh-v0.md) | Copy files or build artifacts to a remote machine over SSH. |
| **Deploy to Kubernetes**<br>[KubernetesManifest@0](kubernetes-manifest-v0.md) | Use Kubernetes manifest files to deploy to clusters or even bake the manifest files to be used for deployments using Helm charts. |
| **IIS web app deploy**<br>[IISWebAppDeploymentOnMachineGroup@0](iisweb-app-deployment-on-machine-group-v0.md) | Deploy a website or web application using Web Deploy. |
| **IIS Web App deployment (Deprecated)**<br>[IISWebAppDeployment@1](iisweb-app-deployment-v1.md) | Deploy using MSDeploy, then create/update websites and app pools. |
| **IIS web app manage**<br>[IISWebAppManagementOnMachineGroup@0](iisweb-app-management-on-machine-group-v0.md) | Create or update websites, web apps, virtual directories, or application pools. |
| **Invoke REST API**<br>[InvokeRESTAPI@1](invoke-rest-api-v1.md)<br>[InvokeRESTAPI@0](invoke-rest-api-v0.md) | Invoke a REST API as a part of your pipeline. |
| **Kubectl**<br>[Kubernetes@1](kubernetes-v1.md)<br>[Kubernetes@0](kubernetes-v0.md) | Deploy, configure, update a Kubernetes cluster in Azure Container Service by running kubectl commands. |
| **Manual intervention**<br>[ManualIntervention@8](manual-intervention-v8.md) | Pause deployment and wait for manual intervention. |
| **Manual validation**<br>[ManualValidation@0](manual-validation-v0.md) | [PREVIEW] Pause a pipeline run to wait for manual interaction. Works only with YAML pipelines. |
| **MySQL database deploy**<br>[MysqlDeploymentOnMachineGroup@1](mysql-deployment-on-machine-group-v1.md) | Run scripts and make changes to a MySQL Database. |
| **Package and deploy Helm charts**<br>[HelmDeploy@0](helm-deploy-v0.md) | Deploy, configure, update a Kubernetes cluster in Azure Container Service by running helm commands. |
| **PowerShell on target machines**<br>[PowerShellOnTargetMachines@3](powershell-on-target-machines-v3.md) | Execute PowerShell scripts on remote machines using PSSession and Invoke-Command for remoting. |
| **PowerShell on Target Machines**<br>[PowerShellOnTargetMachines@2](powershell-on-target-machines-v2.md)<br>[PowerShellOnTargetMachines@1](powershell-on-target-machines-v1.md) | Execute PowerShell scripts on remote machine(s). |
| **Service Fabric application deployment**<br>[ServiceFabricDeploy@1](service-fabric-deploy-v1.md) | Deploy an Azure Service Fabric application to a cluster. |
| **Service Fabric Compose deploy**<br>[ServiceFabricComposeDeploy@0](service-fabric-compose-deploy-v0.md) | Deploy a Docker Compose application to an Azure Service Fabric cluster. |
| **SQL Server database deploy**<br>[SqlDacpacDeploymentOnMachineGroup@0](sql-dacpac-deployment-on-machine-group-v0.md) | Deploy a SQL Server database using DACPAC or SQL scripts. |
| **SQL Server database deploy (Deprecated)**<br>[SqlServerDacpacDeployment@1](sql-server-dacpac-deployment-v1.md) | Deploy a SQL Server database using DACPAC. |
| **SSH**<br>[SSH@0](ssh-v0.md) | Run shell commands or a script on a remote machine using SSH. |
| **Windows machine file copy**<br>[WindowsMachineFileCopy@2](windows-machine-file-copy-v2.md)<br>[WindowsMachineFileCopy@1](windows-machine-file-copy-v1.md) | Copy files to remote Windows machines. |
## Package tasks

| Task | Description |
|---|---|
| **CocoaPods**<br>[CocoaPods@0](cocoa-pods-v0.md) | Install CocoaPods dependencies for Swift and Objective-C Cocoa projects. |
| **Conda environment**<br>[CondaEnvironment@1](conda-environment-v1.md)<br>[CondaEnvironment@0](conda-environment-v0.md) | This task is deprecated. Use `conda` directly in script to work with Anaconda environments. |
| **Download Github Npm Package**<br>[DownloadGithubNpmPackage@1](download-github-npm-package-v1.md) | Install npm packages from GitHub. |
| **Maven Authenticate**<br>[MavenAuthenticate@0](maven-authenticate-v0.md) | Provides credentials for Azure Artifacts feeds and external maven repositories. |
| **npm**<br>[Npm@1](npm-v1.md)<br>[Npm@0](npm-v0.md) | Install and publish npm packages, or run an npm command. Supports npmjs.com and authenticated registries like Azure Artifacts. |
| **npm authenticate (for task runners)**<br>[npmAuthenticate@0](npm-authenticate-v0.md) | Don't use this task if you're also using the npm task. Provides npm credentials to an .npmrc file in your repository for the scope of the build. This enables npm task runners like gulp and Grunt to authenticate with private registries. |
| **NuGet**<br>[NuGetCommand@2](nuget-command-v2.md) | Restore, pack, or push NuGet packages, or run a NuGet command. Supports NuGet.org and authenticated feeds like Azure Artifacts and MyGet. Uses NuGet.exe and works with .NET Framework apps. For .NET Core and .NET Standard apps, use the .NET Core task. |
| **NuGet authenticate**<br>[NuGetAuthenticate@1](nuget-authenticate-v1.md)<br>[NuGetAuthenticate@0](nuget-authenticate-v0.md) | Configure NuGet tools to authenticate with Azure Artifacts and other NuGet repositories. Requires NuGet >= 4.8.5385, dotnet >= 6, or MSBuild >= 15.8.166.59604. |
| **NuGet command**<br>[NuGet@0](nuget-v0.md) | Deprecated: use the “NuGet” task instead. It works with the new Tool Installer framework so you can easily use new versions of NuGet without waiting for a task update, provides better support for authenticated feeds outside this organization/collection, and uses NuGet 4 by default. |
| **NuGet Installer**<br>[NuGetInstaller@0](nuget-installer-v0.md) | Installs or restores missing NuGet packages. Use NuGetAuthenticate@0 task for latest capabilities. |
| **NuGet packager**<br>[NuGetPackager@0](nuget-packager-v0.md) | Deprecated: use the “NuGet” task instead. It works with the new Tool Installer framework so you can easily use new versions of NuGet without waiting for a task update, provides better support for authenticated feeds outside this organization/collection, and uses NuGet 4 by default. |
| **NuGet publisher**<br>[NuGetPublisher@0](nuget-publisher-v0.md) | Deprecated: use the “NuGet” task instead. It works with the new Tool Installer framework so you can easily use new versions of NuGet without waiting for a task update, provides better support for authenticated feeds outside this organization/collection, and uses NuGet 4 by default. |
| **NuGet Restore**<br>[NuGetRestore@1](nuget-restore-v1.md) | Restores NuGet packages in preparation for a Visual Studio Build step. |
| **PyPI publisher**<br>[PyPIPublisher@0](py-pi-publisher-v0.md) | Create and upload an sdist or wheel to a PyPI-compatible index using Twine. |
| **Python pip authenticate**<br>[PipAuthenticate@1](pip-authenticate-v1.md)<br>[PipAuthenticate@0](pip-authenticate-v0.md) | Authentication task for the pip client used for installing Python distributions. |
| **Python twine upload authenticate**<br>[TwineAuthenticate@1](twine-authenticate-v1.md)<br>[TwineAuthenticate@0](twine-authenticate-v0.md) | Authenticate for uploading Python distributions using twine. Add '-r FeedName/EndpointName --config-file $(PYPIRC_PATH)' to your twine upload command. For feeds present in this organization, use the feed name as the repository (-r). Otherwise, use the endpoint name defined in the service connection. |
| **Universal packages**<br>[UniversalPackages@0](universal-packages-v0.md) | Download or publish Universal Packages. |
| **Xamarin Component Restore**<br>[XamarinComponentRestore@0](xamarin-component-restore-v0.md) | This task is deprecated. Use 'NuGet' instead. |
## Test tasks

| Task | Description |
|---|---|
| **App Center test**<br>[AppCenterTest@1](app-center-test-v1.md) | Test app packages with Visual Studio App Center. |
| **Container Structure Test**<br>[ContainerStructureTest@0](container-structure-test-v0.md) | Uses container-structure-test (https://github.com/GoogleContainerTools/container-structure-test) to validate the structure of an image based on four categories of tests - command tests, file existence tests, file content tests and metadata tests. |
| **Mobile Center Test**<br>[VSMobileCenterTest@0](vsmobile-center-test-v0.md) | Test mobile app packages with Visual Studio Mobile Center. |
| **Publish code coverage results**<br>[PublishCodeCoverageResults@1](publish-code-coverage-results-v1.md) | Publish Cobertura or JaCoCo code coverage results from a build. |
| **Publish test results**<br>[PublishTestResults@1](publish-test-results-v1.md) | Publish test results to Azure Pipelines. |
| **Publish Test Results**<br>[PublishTestResults@2](publish-test-results-v2.md) | Publish test results to Azure Pipelines. |
| **Run functional tests**<br>[RunVisualStudioTestsusingTestAgent@1](run-visual-studio-testsusing-test-agent-v1.md) | Deprecated: This task and it’s companion task (Visual Studio Test Agent Deployment) are deprecated. Use the 'Visual Studio Test' task instead. The VSTest task can run unit as well as functional tests. Run tests on one or more agents using the multi-agent job setting. Use the 'Visual Studio Test Platform' task to run tests without needing Visual Studio on the agent. VSTest task also brings new capabilities such as automatically rerunning failed tests. |
| **Visual Studio Test**<br>[VSTest@2](vstest-v2.md)<br>[VSTest@1](vstest-v1.md) | Run unit and functional tests (Selenium, Appium, Coded UI test, etc.) using the Visual Studio Test (VsTest) runner. Test frameworks that have a Visual Studio test adapter such as MsTest, xUnit, NUnit, Chutzpah (for JavaScript tests using QUnit, Mocha and Jasmine), etc. can be run. Tests can be distributed on multiple agents using this task (version 2). |
| **Visual Studio test agent deployment**<br>[DeployVisualStudioTestAgent@2](deploy-visual-studio-test-agent-v2.md) | DeployVisualStudioTestAgent@2 is deprecated. Use the Visual Studio Test task to run unit and functional tests. |
| **Visual Studio Test Agent Deployment**<br>[DeployVisualStudioTestAgent@1](deploy-visual-studio-test-agent-v1.md) | Deploy and configure Test Agent to run tests on a set of machines. |
| **Xamarin Test Cloud**<br>[XamarinTestCloud@1](xamarin-test-cloud-v1.md) | [Deprecated] Test mobile apps with Xamarin Test Cloud using Xamarin.UITest. Instead, use the 'App Center test' task. |
## Tool tasks

| Task | Description |
|---|---|
| **.NET Core SDK/runtime installer**<br>[DotNetCoreInstaller@1](dotnet-core-installer-v1.md)<br>[DotNetCoreInstaller@0](dotnet-core-installer-v0.md) | Acquire a specific version of the .NET Core SDK from the internet or local cache and add it to the PATH. |
| **Docker CLI installer**<br>[DockerInstaller@0](docker-installer-v0.md) | Install Docker CLI on agent machine. |
| **Duffle tool installer**<br>[DuffleInstaller@0](duffle-installer-v0.md) | Install a specified version of Duffle for installing and managing CNAB bundles. |
| **Go tool installer**<br>[GoTool@0](go-tool-v0.md) | Find in cache or download a specific version of Go and add it to the PATH. |
| **Helm tool installer**<br>[HelmInstaller@1](helm-installer-v1.md)<br>[HelmInstaller@0](helm-installer-v0.md) | Install Helm on an agent machine. |
| **Install Azure Func Core Tools**<br>[FuncToolsInstaller@0](func-tools-installer-v0.md) | Install Azure Func Core Tools. |
| **Java tool installer**<br>[JavaToolInstaller@0](java-tool-installer-v0.md) | Acquire a specific version of Java from a user-supplied Azure blob or the tool cache and sets JAVA_HOME. |
| **Kubectl tool installer**<br>[KubectlInstaller@0](kubectl-installer-v0.md) | Install Kubectl on agent machine. |
| **Node.js tool installer**<br>[NodeTool@0](node-tool-v0.md) | Finds or downloads and caches the specified version spec of Node.js and adds it to the PATH. |
| **NuGet tool installer**<br>[NuGetToolInstaller@1](nuget-tool-installer-v1.md)<br>[NuGetToolInstaller@0](nuget-tool-installer-v0.md) | Acquires a specific version of NuGet from the internet or the tools cache and adds it to the PATH. Use this task to change the version of NuGet used in the NuGet tasks. |
| **Use .NET Core**<br>[UseDotNet@2](use-dotnet-v2.md) | Acquires a specific version of the .NET Core SDK from the internet or the local cache and adds it to the PATH. Use this task to change the version of .NET Core used in subsequent tasks. Additionally provides proxy support. |
| **Use Node.js ecosystem**<br>[UseNode@1](use-node-v1.md) | Set up a Node.js environment and add it to the PATH, additionally providing proxy support. |
| **Use Python version**<br>[UsePythonVersion@0](use-python-version-v0.md) | Use the specified version of Python from the tool cache, optionally adding it to the PATH. |
| **Use Ruby version**<br>[UseRubyVersion@0](use-ruby-version-v0.md) | Use the specified version of Ruby from the tool cache, optionally adding it to the PATH. |
| **Visual Studio test platform installer**<br>[VisualStudioTestPlatformInstaller@1](visual-studio-test-platform-installer-v1.md) | Acquire the test platform from nuget.org or the tool cache. Satisfies the ‘vstest’ demand and can be used for running tests and collecting diagnostic data using the Visual Studio Test task. |
## Utility tasks

| Task | Description |
|---|---|
| **Archive files**<br>[ArchiveFiles@2](archive-files-v2.md) | Compress files into .7z, .tar.gz, or .zip. |
| **Archive Files**<br>[ArchiveFiles@1](archive-files-v1.md) | Archive files using compression formats such as .7z, .rar, .tar.gz, and .zip. |
| **Azure Network Load Balancer**<br>[AzureNLBManagement@1](azure-nlb-management-v1.md) | Connect or disconnect an Azure virtual machine's network interface to a Load Balancer's back end address pool. |
| **Bash**<br>[Bash@3](bash-v3.md) | Run a Bash script on macOS, Linux, or Windows. |
| **Batch script**<br>[BatchScript@1](batch-script-v1.md) | Run a Windows command or batch script and optionally allow it to change the environment. |
| **Cache**<br>[Cache@2](cache-v2.md) | Cache files between runs. |
| **Cache (Beta)**<br>[CacheBeta@1](cache-beta-v1.md)<br>[CacheBeta@0](cache-beta-v0.md) | Cache files between runs. |
| **Command Line**<br>[CmdLine@2](cmd-line-v2.md)<br>[CmdLine@1](cmd-line-v1.md) | Run a command line script using Bash on Linux and macOS and cmd.exe on Windows. |
| **Copy and Publish Build Artifacts**<br>[CopyPublishBuildArtifacts@1](copy-publish-build-artifacts-v1.md) | CopyPublishBuildArtifacts@1 is deprecated. Use the Copy Files task and the Publish Build Artifacts task instead. |
| **Copy files**<br>[CopyFiles@2](copy-files-v2.md) | Copy files from a source folder to a target folder using patterns matching file paths (not folder paths). |
| **Copy Files**<br>[CopyFiles@1](copy-files-v1.md) | Copy files from source folder to target folder using minimatch patterns (The minimatch patterns will only match file paths, not folder paths). |
| **cURL Upload Files**<br>[cURLUploader@2](curl-uploader-v2.md)<br>[cURLUploader@1](curl-uploader-v1.md) | Use cURL's supported protocols to upload files. |
| **Decrypt file (OpenSSL)**<br>[DecryptFile@1](decrypt-file-v1.md) | Decrypt a file using OpenSSL. |
| **Delay**<br>[Delay@1](delay-v1.md) | Delay further execution of a workflow by a fixed time. |
| **Delete files**<br>[DeleteFiles@1](delete-files-v1.md) | Delete folders, or files matching a pattern. |
| **Deploy Azure Static Web App**<br>[AzureStaticWebApp@0](azure-static-web-app-v0.md) | Build and deploy an Azure Static Web App. |
| **Download artifacts from file share**<br>[DownloadFileshareArtifacts@1](download-fileshare-artifacts-v1.md) | Download artifacts from a file share, like \\share\drop. |
| **Download build artifacts**<br>[DownloadBuildArtifacts@0](download-build-artifacts-v0.md) | Download files that were saved as artifacts of a completed build. |
| **Download GitHub Release**<br>[DownloadGitHubRelease@0](download-github-release-v0.md) | Downloads a GitHub Release from a repository. |
| **Download package**<br>[DownloadPackage@1](download-package-v1.md)<br>[DownloadPackage@0](download-package-v0.md) | Download a package from a package management feed in Azure Artifacts. |
| **Download Pipeline Artifacts**<br>[DownloadPipelineArtifact@2](download-pipeline-artifact-v2.md)<br>[DownloadPipelineArtifact@1](download-pipeline-artifact-v1.md)<br>[DownloadPipelineArtifact@0](download-pipeline-artifact-v0.md) | Download build and pipeline artifacts. |
| **Download secure file**<br>[DownloadSecureFile@1](download-secure-file-v1.md) | Download a secure file to the agent machine. |
| **Extract files**<br>[ExtractFiles@1](extract-files-v1.md) | Extract a variety of archive and compression files such as .7z, .rar, .tar.gz, and .zip. |
| **File transform**<br>[FileTransform@2](file-transform-v2.md)<br>[FileTransform@1](file-transform-v1.md) | Replace tokens with variable values in XML or JSON configuration files. |
| **FTP upload**<br>[FtpUpload@2](ftp-upload-v2.md)<br>[FtpUpload@1](ftp-upload-v1.md) | Upload files using FTP. |
| **GitHub Comment**<br>[GitHubComment@0](github-comment-v0.md) | Write a comment to your GitHub entity i.e. issue or a pull request (PR). |
| **GitHub Release**<br>[GitHubRelease@1](github-release-v1.md)<br>[GitHubRelease@0](github-release-v0.md) | Create, edit, or delete a GitHub release. |
| **Install Apple certificate**<br>[InstallAppleCertificate@2](install-apple-certificate-v2.md) | Install an Apple certificate required to build on a macOS agent machine. |
| **Install Apple Certificate**<br>[InstallAppleCertificate@1](install-apple-certificate-v1.md)<br>[InstallAppleCertificate@0](install-apple-certificate-v0.md) | Install an Apple certificate required to build on a macOS agent. |
| **Install Apple provisioning profile**<br>[InstallAppleProvisioningProfile@1](install-apple-provisioning-profile-v1.md) | Install an Apple provisioning profile required to build on a macOS agent machine. |
| **Install Apple Provisioning Profile**<br>[InstallAppleProvisioningProfile@0](install-apple-provisioning-profile-v0.md) | Install an Apple provisioning profile required to build on a macOS agent. |
| **Install SSH key**<br>[InstallSSHKey@0](install-ssh-key-v0.md) | Install an SSH key prior to a build or deployment. |
| **Invoke Azure Function**<br>[AzureFunction@1](azure-function-v1.md)<br>[AzureFunction@0](azure-function-v0.md) | Invoke an Azure Function. |
| **Jenkins download artifacts**<br>[JenkinsDownloadArtifacts@1](jenkins-download-artifacts-v1.md) | Download artifacts produced by a Jenkins job. |
| **PowerShell**<br>[PowerShell@2](powershell-v2.md)<br>[PowerShell@1](powershell-v1.md) | Run a PowerShell script on Linux, macOS, or Windows. |
| **Publish build artifacts**<br>[PublishBuildArtifacts@1](publish-build-artifacts-v1.md) | Publish build artifacts to Azure Pipelines or a Windows file share. |
| **Publish Pipeline Artifacts**<br>[PublishPipelineArtifact@1](publish-pipeline-artifact-v1.md)<br>[PublishPipelineArtifact@0](publish-pipeline-artifact-v0.md) | Publish (upload) a file or directory as a named artifact for the current run. |
| **Publish Pipeline Metadata**<br>[PublishPipelineMetadata@0](publish-pipeline-metadata-v0.md) | Publish Pipeline Metadata to Evidence store. |
| **Publish To Azure Service Bus**<br>[PublishToAzureServiceBus@1](publish-to-azure-service-bus-v1.md)<br>[PublishToAzureServiceBus@0](publish-to-azure-service-bus-v0.md) | Sends a message to Azure Service Bus using a service connection (no agent is required). |
| **Python script**<br>[PythonScript@0](python-script-v0.md) | Run a Python file or inline script. |
| **Query Azure Monitor alerts**<br>[AzureMonitor@1](azure-monitor-v1.md) | Observe the configured Azure Monitor rules for active alerts. |
| **Query Classic Azure Monitor alerts**<br>[AzureMonitor@0](azure-monitor-v0.md) | Observe the configured classic Azure Monitor rules for active alerts. |
| **Query work items**<br>[queryWorkItems@0](query-work-items-v0.md) | Execute a work item query and check the number of items returned. |
| **Review App**<br>[ReviewApp@0](review-app-v0.md) | Use this task under deploy phase provider to create a resource dynamically. |
| **Service Fabric PowerShell**<br>[ServiceFabricPowerShell@1](service-fabric-powershell-v1.md) | Run a PowerShell script in the context of an Azure Service Fabric cluster connection. |
| **Shell script**<br>[ShellScript@2](shell-script-v2.md) | Run a shell script using Bash. |
| **Update Service Fabric App Versions**<br>[ServiceFabricUpdateAppVersions@1](service-fabric-update-app-versions-v1.md) | Automatically updates the versions of a packaged Service Fabric application. |
| **Update Service Fabric manifests**<br>[ServiceFabricUpdateManifests@2](service-fabric-update-manifests-v2.md) | Automatically update portions of application and service manifests in a packaged Azure Service Fabric application. |
| **Xamarin License**<br>[XamarinLicense@1](xamarin-license-v1.md) | [Deprecated] Upgrade to free version of Xamarin: https://store.xamarin.com. |

:::moniker-end

:::moniker range="=azure-pipelines-2020.1"

## Build tasks

| Task | Description |
|---|---|
| **.NET Core**<br>[DotNetCoreCLI@2](dotnet-core-cli-v2.md)<br>[DotNetCoreCLI@1](dotnet-core-cli-v1.md)<br>[DotNetCoreCLI@0](dotnet-core-cli-v0.md) | Build, test, package, or publish a dotnet application, or run a custom dotnet command. |
| **Android Build**<br>[AndroidBuild@1](android-build-v1.md) | AndroidBuild@1 is deprecated. Use Gradle. |
| **Android Signing**<br>[AndroidSigning@3](android-signing-v3.md)<br>[AndroidSigning@2](android-signing-v2.md)<br>[AndroidSigning@1](android-signing-v1.md) | Sign and align Android APK files. |
| **Ant**<br>[Ant@1](ant-v1.md) | Build with Apache Ant. |
| **Azure IoT Edge**<br>[AzureIoTEdge@2](azure-iot-edge-v2.md) | Build and deploy an Azure IoT Edge image. |
| **CMake**<br>[CMake@1](cmake-v1.md) | Build with the CMake cross-platform build system. |
| **Container Build**<br>[ContainerBuild@0](container-build-v0.md) | Container Build Task. |
| **Docker**<br>[Docker@2](docker-v2.md)<br>[Docker@1](docker-v1.md)<br>[Docker@0](docker-v0.md) | Build or push Docker images, login or logout, start or stop containers, or run a Docker command. |
| **Docker Compose**<br>[DockerCompose@0](docker-compose-v0.md) | Build, push or run multi-container Docker applications. Task can be used with Docker or Azure Container registry. |
| **Download GitHub Nuget Packages**<br>[DownloadGitHubNugetPackage@1](download-github-nuget-package-v1.md) | Restore your nuget packages using dotnet CLI. |
| **Go**<br>[Go@0](go-v0.md) | Get, build, or test a Go application, or run a custom Go command. |
| **Gradle**<br>[Gradle@2](gradle-v2.md)<br>[Gradle@1](gradle-v1.md) | Build using a Gradle wrapper script. |
| **Grunt**<br>[Grunt@0](grunt-v0.md) | Run the Grunt JavaScript task runner. |
| **gulp**<br>[gulp@1](gulp-v1.md)<br>[gulp@0](gulp-v0.md) | Run the gulp Node.js streaming task-based build system. |
| **Index sources and publish symbols**<br>[PublishSymbols@2](publish-symbols-v2.md)<br>[PublishSymbols@1](publish-symbols-v1.md) | Index your source code and publish symbols to a file share or Azure Artifacts symbol server. |
| **Jenkins queue job**<br>[JenkinsQueueJob@2](jenkins-queue-job-v2.md) | Queue a job on a Jenkins server. |
| **Jenkins Queue Job**<br>[JenkinsQueueJob@1](jenkins-queue-job-v1.md) | Queue a job on a Jenkins server. |
| **Maven**<br>[Maven@3](maven-v3.md)<br>[Maven@2](maven-v2.md)<br>[Maven@1](maven-v1.md) | Build, test, and deploy with Apache Maven. |
| **MSBuild**<br>[MSBuild@1](msbuild-v1.md) | Build with MSBuild. |
| **Visual Studio build**<br>[VSBuild@1](vsbuild-v1.md) | Build with MSBuild and set the Visual Studio version property. |
| **Xamarin.Android**<br>[XamarinAndroid@1](xamarin-android-v1.md) | Build an Android app with Xamarin. |
| **Xamarin.iOS**<br>[XamariniOS@2](xamarin-ios-v2.md)<br>[XamariniOS@1](xamarin-ios-v1.md) | Build an iOS app with Xamarin on macOS. |
| **Xcode**<br>[Xcode@5](xcode-v5.md)<br>[Xcode@4](xcode-v4.md) | Build, test, or archive an Xcode workspace on macOS. Optionally package an app. |
| **Xcode Build**<br>[Xcode@3](xcode-v3.md)<br>[Xcode@2](xcode-v2.md) | Build an Xcode workspace on macOS. |
| **Xcode Package iOS**<br>[XcodePackageiOS@0](xcode-package-ios-v0.md) | Generate an .ipa file from Xcode build output using xcrun (Xcode 7 or below). |
## Deploy tasks

| Task | Description |
|---|---|
| **App Center distribute**<br>[AppCenterDistribute@3](app-center-distribute-v3.md)<br>[AppCenterDistribute@2](app-center-distribute-v2.md)<br>[AppCenterDistribute@1](app-center-distribute-v1.md)<br>[AppCenterDistribute@0](app-center-distribute-v0.md) | Distribute app builds to testers and users via Visual Studio App Center. |
| **ARM template deployment**<br>[AzureResourceManagerTemplateDeployment@3](azure-resource-manager-template-deployment-v3.md) | Deploy an Azure Resource Manager (ARM) template to all the deployment scopes. |
| **Azure App Service Classic (Deprecated)**<br>[AzureWebPowerShellDeployment@1](azure-web-powershell-deployment-v1.md) | Create or update Azure App Service using Azure PowerShell. |
| **Azure App Service deploy**<br>[AzureRmWebAppDeployment@4](azure-rm-web-app-deployment-v4.md)<br>[AzureRmWebAppDeployment@3](azure-rm-web-app-deployment-v3.md)<br>[AzureRmWebAppDeployment@2](azure-rm-web-app-deployment-v2.md) | Deploy to Azure App Service a web, mobile, or API app using Docker, Java, .NET, .NET Core, Node.js, PHP, Python, or Ruby. |
| **Azure App Service manage**<br>[AzureAppServiceManage@0](azure-app-service-manage-v0.md) | Start, stop, restart, slot swap, slot delete, install site extensions or enable continuous monitoring for an Azure App Service. |
| **Azure App Service Settings**<br>[AzureAppServiceSettings@1](azure-app-service-settings-v1.md) | Update/Add App settings an Azure Web App for Linux or Windows. |
| **Azure CLI**<br>[AzureCLI@2](azure-cli-v2.md)<br>[AzureCLI@1](azure-cli-v1.md) | Run Azure CLI commands against an Azure subscription in a PowerShell Core/Shell script when running on Linux agent or PowerShell/PowerShell Core/Batch script when running on Windows agent. |
| **Azure CLI Preview**<br>[AzureCLI@0](azure-cli-v0.md) | Run a Shell or Batch script with Azure CLI commands against an azure subscription. |
| **Azure Cloud Service deployment**<br>[AzureCloudPowerShellDeployment@1](azure-cloud-powershell-deployment-v1.md) | Deploy an Azure Cloud Service. |
| **Azure Database for MySQL deployment**<br>[AzureMysqlDeployment@1](azure-mysql-deployment-v1.md) | Run your scripts and make changes to your Azure Database for MySQL. |
| **Azure file copy**<br>[AzureFileCopy@4](azure-file-copy-v4.md)<br>[AzureFileCopy@3](azure-file-copy-v3.md)<br>[AzureFileCopy@2](azure-file-copy-v2.md)<br>[AzureFileCopy@1](azure-file-copy-v1.md) | Copy files to Azure Blob Storage or virtual machines. |
| **Azure Function on Kubernetes**<br>[AzureFunctionOnKubernetes@0](azure-function-on-kubernetes-v0.md) | Deploy Azure function to Kubernetes cluster. |
| **Azure Functions Deploy**<br>[AzureFunctionApp@1](azure-function-app-v1.md) | Update a function app with .NET, Python, JavaScript, PowerShell, Java based web applications. |
| **Azure Functions for container**<br>[AzureFunctionAppContainer@1](azure-function-app-container-v1.md) | Update a function app with a Docker container. |
| **Azure Key Vault**<br>[AzureKeyVault@1](azure-key-vault-v1.md) | Download Azure Key Vault secrets. |
| **Azure Monitor alerts (Deprecated)**<br>[AzureMonitorAlerts@0](azure-monitor-alerts-v0.md) | Configure alerts on available metrics for an Azure resource (Deprecated). |
| **Azure PowerShell**<br>[AzurePowerShell@5](azure-powershell-v5.md)<br>[AzurePowerShell@4](azure-powershell-v4.md)<br>[AzurePowerShell@3](azure-powershell-v3.md)<br>[AzurePowerShell@2](azure-powershell-v2.md)<br>[AzurePowerShell@1](azure-powershell-v1.md) | Run a PowerShell script within an Azure environment. |
| **Azure resource group deployment**<br>[AzureResourceGroupDeployment@2](azure-resource-group-deployment-v2.md) | Deploy an Azure Resource Manager (ARM) template to a resource group and manage virtual machines. |
| **Azure Resource Group Deployment**<br>[AzureResourceGroupDeployment@1](azure-resource-group-deployment-v1.md) | Deploy, start, stop, delete Azure Resource Groups. |
| **Azure SQL Database deployment**<br>[SqlAzureDacpacDeployment@1](sql-azure-dacpac-deployment-v1.md) | Deploy an Azure SQL Database using DACPAC or run scripts using SQLCMD. |
| **Azure VM scale set deployment**<br>[AzureVmssDeployment@0](azure-vmss-deployment-v0.md) | Deploy a virtual machine scale set image. |
| **Azure Web App**<br>[AzureWebApp@1](azure-web-app-v1.md) | Deploy an Azure Web App for Linux or Windows. |
| **Azure Web App for Containers**<br>[AzureWebAppContainer@1](azure-web-app-container-v1.md) | Deploy containers to Azure App Service. |
| **Build machine image**<br>[PackerBuild@1](packer-build-v1.md)<br>[PackerBuild@0](packer-build-v0.md) | Build a machine image using Packer, which may be used for Azure Virtual machine scale set deployment. |
| **Check Azure Policy compliance**<br>[AzurePolicyCheckGate@0](azure-policy-check-gate-v0.md) | Security and compliance assessment for Azure Policy. |
| **Chef**<br>[Chef@1](chef-v1.md) | Deploy to Chef environments by editing environment attributes. |
| **Chef Knife**<br>[ChefKnife@1](chef-knife-v1.md) | Run scripts with Knife commands on your Chef workstation. |
| **Copy files over SSH**<br>[CopyFilesOverSSH@0](copy-files-over-ssh-v0.md) | Copy files or build artifacts to a remote machine over SSH. |
| **Deploy to Kubernetes**<br>[KubernetesManifest@0](kubernetes-manifest-v0.md) | Use Kubernetes manifest files to deploy to clusters or even bake the manifest files to be used for deployments using Helm charts. |
| **IIS web app deploy**<br>[IISWebAppDeploymentOnMachineGroup@0](iisweb-app-deployment-on-machine-group-v0.md) | Deploy a website or web application using Web Deploy. |
| **IIS Web App deployment (Deprecated)**<br>[IISWebAppDeployment@1](iisweb-app-deployment-v1.md) | Deploy using MSDeploy, then create/update websites and app pools. |
| **IIS web app manage**<br>[IISWebAppManagementOnMachineGroup@0](iisweb-app-management-on-machine-group-v0.md) | Create or update websites, web apps, virtual directories, or application pools. |
| **Invoke REST API**<br>[InvokeRESTAPI@1](invoke-rest-api-v1.md)<br>[InvokeRESTAPI@0](invoke-rest-api-v0.md) | Invoke a REST API as a part of your pipeline. |
| **Kubectl**<br>[Kubernetes@1](kubernetes-v1.md)<br>[Kubernetes@0](kubernetes-v0.md) | Deploy, configure, update a Kubernetes cluster in Azure Container Service by running kubectl commands. |
| **Manual intervention**<br>[ManualIntervention@8](manual-intervention-v8.md) | Pause deployment and wait for manual intervention. |
| **Manual validation**<br>[ManualValidation@0](manual-validation-v0.md) | [PREVIEW] Pause a pipeline run to wait for manual interaction. Works only with YAML pipelines. |
| **MySQL database deploy**<br>[MysqlDeploymentOnMachineGroup@1](mysql-deployment-on-machine-group-v1.md) | Run scripts and make changes to a MySQL Database. |
| **Package and deploy Helm charts**<br>[HelmDeploy@0](helm-deploy-v0.md) | Deploy, configure, update a Kubernetes cluster in Azure Container Service by running helm commands. |
| **PowerShell on target machines**<br>[PowerShellOnTargetMachines@3](powershell-on-target-machines-v3.md) | Execute PowerShell scripts on remote machines using PSSession and Invoke-Command for remoting. |
| **PowerShell on Target Machines**<br>[PowerShellOnTargetMachines@2](powershell-on-target-machines-v2.md)<br>[PowerShellOnTargetMachines@1](powershell-on-target-machines-v1.md) | Execute PowerShell scripts on remote machine(s). |
| **Service Fabric application deployment**<br>[ServiceFabricDeploy@1](service-fabric-deploy-v1.md) | Deploy an Azure Service Fabric application to a cluster. |
| **Service Fabric Compose deploy**<br>[ServiceFabricComposeDeploy@0](service-fabric-compose-deploy-v0.md) | Deploy a Docker Compose application to an Azure Service Fabric cluster. |
| **SQL Server database deploy**<br>[SqlDacpacDeploymentOnMachineGroup@0](sql-dacpac-deployment-on-machine-group-v0.md) | Deploy a SQL Server database using DACPAC or SQL scripts. |
| **SQL Server database deploy (Deprecated)**<br>[SqlServerDacpacDeployment@1](sql-server-dacpac-deployment-v1.md) | Deploy a SQL Server database using DACPAC. |
| **SSH**<br>[SSH@0](ssh-v0.md) | Run shell commands or a script on a remote machine using SSH. |
| **Windows machine file copy**<br>[WindowsMachineFileCopy@2](windows-machine-file-copy-v2.md)<br>[WindowsMachineFileCopy@1](windows-machine-file-copy-v1.md) | Copy files to remote Windows machines. |
## Package tasks

| Task | Description |
|---|---|
| **CocoaPods**<br>[CocoaPods@0](cocoa-pods-v0.md) | Install CocoaPods dependencies for Swift and Objective-C Cocoa projects. |
| **Conda environment**<br>[CondaEnvironment@1](conda-environment-v1.md)<br>[CondaEnvironment@0](conda-environment-v0.md) | This task is deprecated. Use `conda` directly in script to work with Anaconda environments. |
| **Download Github Npm Package**<br>[DownloadGithubNpmPackage@1](download-github-npm-package-v1.md) | Install npm packages from GitHub. |
| **Maven Authenticate**<br>[MavenAuthenticate@0](maven-authenticate-v0.md) | Provides credentials for Azure Artifacts feeds and external maven repositories. |
| **npm**<br>[Npm@1](npm-v1.md)<br>[Npm@0](npm-v0.md) | Install and publish npm packages, or run an npm command. Supports npmjs.com and authenticated registries like Azure Artifacts. |
| **npm authenticate (for task runners)**<br>[npmAuthenticate@0](npm-authenticate-v0.md) | Don't use this task if you're also using the npm task. Provides npm credentials to an .npmrc file in your repository for the scope of the build. This enables npm task runners like gulp and Grunt to authenticate with private registries. |
| **NuGet**<br>[NuGetCommand@2](nuget-command-v2.md) | Restore, pack, or push NuGet packages, or run a NuGet command. Supports NuGet.org and authenticated feeds like Azure Artifacts and MyGet. Uses NuGet.exe and works with .NET Framework apps. For .NET Core and .NET Standard apps, use the .NET Core task. |
| **NuGet authenticate**<br>[NuGetAuthenticate@0](nuget-authenticate-v0.md) | Configure NuGet tools to authenticate with Azure Artifacts and other NuGet repositories. Requires NuGet >= 4.8.5385, dotnet >= 2.1.400, or MSBuild >= 15.8.166.59604. |
| **NuGet command**<br>[NuGet@0](nuget-v0.md) | Deprecated: use the “NuGet” task instead. It works with the new Tool Installer framework so you can easily use new versions of NuGet without waiting for a task update, provides better support for authenticated feeds outside this organization/collection, and uses NuGet 4 by default. |
| **NuGet Installer**<br>[NuGetInstaller@0](nuget-installer-v0.md) | Installs or restores missing NuGet packages. Use NuGetAuthenticate@0 task for latest capabilities. |
| **NuGet packager**<br>[NuGetPackager@0](nuget-packager-v0.md) | Deprecated: use the “NuGet” task instead. It works with the new Tool Installer framework so you can easily use new versions of NuGet without waiting for a task update, provides better support for authenticated feeds outside this organization/collection, and uses NuGet 4 by default. |
| **NuGet publisher**<br>[NuGetPublisher@0](nuget-publisher-v0.md) | Deprecated: use the “NuGet” task instead. It works with the new Tool Installer framework so you can easily use new versions of NuGet without waiting for a task update, provides better support for authenticated feeds outside this organization/collection, and uses NuGet 4 by default. |
| **NuGet Restore**<br>[NuGetRestore@1](nuget-restore-v1.md) | Restores NuGet packages in preparation for a Visual Studio Build step. |
| **PyPI publisher**<br>[PyPIPublisher@0](py-pi-publisher-v0.md) | Create and upload an sdist or wheel to a PyPI-compatible index using Twine. |
| **Python pip authenticate**<br>[PipAuthenticate@1](pip-authenticate-v1.md)<br>[PipAuthenticate@0](pip-authenticate-v0.md) | Authentication task for the pip client used for installing Python distributions. |
| **Python twine upload authenticate**<br>[TwineAuthenticate@1](twine-authenticate-v1.md)<br>[TwineAuthenticate@0](twine-authenticate-v0.md) | Authenticate for uploading Python distributions using twine. Add '-r FeedName/EndpointName --config-file $(PYPIRC_PATH)' to your twine upload command. For feeds present in this organization, use the feed name as the repository (-r). Otherwise, use the endpoint name defined in the service connection. |
| **Universal packages**<br>[UniversalPackages@0](universal-packages-v0.md) | Download or publish Universal Packages. |
| **Xamarin Component Restore**<br>[XamarinComponentRestore@0](xamarin-component-restore-v0.md) | This task is deprecated. Use 'NuGet' instead. |
## Test tasks

| Task | Description |
|---|---|
| **App Center test**<br>[AppCenterTest@1](app-center-test-v1.md) | Test app packages with Visual Studio App Center. |
| **Container Structure Test**<br>[ContainerStructureTest@0](container-structure-test-v0.md) | Uses container-structure-test (https://github.com/GoogleContainerTools/container-structure-test) to validate the structure of an image based on four categories of tests - command tests, file existence tests, file content tests and metadata tests. |
| **Mobile Center Test**<br>[VSMobileCenterTest@0](vsmobile-center-test-v0.md) | Test mobile app packages with Visual Studio Mobile Center. |
| **Publish code coverage results**<br>[PublishCodeCoverageResults@1](publish-code-coverage-results-v1.md) | Publish Cobertura or JaCoCo code coverage results from a build. |
| **Publish test results**<br>[PublishTestResults@1](publish-test-results-v1.md) | Publish test results to Azure Pipelines. |
| **Publish Test Results**<br>[PublishTestResults@2](publish-test-results-v2.md) | Publish test results to Azure Pipelines. |
| **Run functional tests**<br>[RunVisualStudioTestsusingTestAgent@1](run-visual-studio-testsusing-test-agent-v1.md) | Deprecated: This task and it’s companion task (Visual Studio Test Agent Deployment) are deprecated. Use the 'Visual Studio Test' task instead. The VSTest task can run unit as well as functional tests. Run tests on one or more agents using the multi-agent job setting. Use the 'Visual Studio Test Platform' task to run tests without needing Visual Studio on the agent. VSTest task also brings new capabilities such as automatically rerunning failed tests. |
| **Visual Studio Test**<br>[VSTest@2](vstest-v2.md)<br>[VSTest@1](vstest-v1.md) | Run unit and functional tests (Selenium, Appium, Coded UI test, etc.) using the Visual Studio Test (VsTest) runner. Test frameworks that have a Visual Studio test adapter such as MsTest, xUnit, NUnit, Chutzpah (for JavaScript tests using QUnit, Mocha and Jasmine), etc. can be run. Tests can be distributed on multiple agents using this task (version 2). |
| **Visual Studio test agent deployment**<br>[DeployVisualStudioTestAgent@2](deploy-visual-studio-test-agent-v2.md) | DeployVisualStudioTestAgent@2 is deprecated. Use the Visual Studio Test task to run unit and functional tests. |
| **Visual Studio Test Agent Deployment**<br>[DeployVisualStudioTestAgent@1](deploy-visual-studio-test-agent-v1.md) | Deploy and configure Test Agent to run tests on a set of machines. |
| **Xamarin Test Cloud**<br>[XamarinTestCloud@1](xamarin-test-cloud-v1.md) | [Deprecated] Test mobile apps with Xamarin Test Cloud using Xamarin.UITest. Instead, use the 'App Center test' task. |
## Tool tasks

| Task | Description |
|---|---|
| **.NET Core SDK/runtime installer**<br>[DotNetCoreInstaller@1](dotnet-core-installer-v1.md)<br>[DotNetCoreInstaller@0](dotnet-core-installer-v0.md) | Acquire a specific version of the .NET Core SDK from the internet or local cache and add it to the PATH. |
| **Docker CLI installer**<br>[DockerInstaller@0](docker-installer-v0.md) | Install Docker CLI on agent machine. |
| **Duffle tool installer**<br>[DuffleInstaller@0](duffle-installer-v0.md) | Install a specified version of Duffle for installing and managing CNAB bundles. |
| **Go tool installer**<br>[GoTool@0](go-tool-v0.md) | Find in cache or download a specific version of Go and add it to the PATH. |
| **Helm tool installer**<br>[HelmInstaller@1](helm-installer-v1.md)<br>[HelmInstaller@0](helm-installer-v0.md) | Install Helm on an agent machine. |
| **Install Azure Func Core Tools**<br>[FuncToolsInstaller@0](func-tools-installer-v0.md) | Install Azure Func Core Tools. |
| **Java tool installer**<br>[JavaToolInstaller@0](java-tool-installer-v0.md) | Acquire a specific version of Java from a user-supplied Azure blob or the tool cache and sets JAVA_HOME. |
| **Kubectl tool installer**<br>[KubectlInstaller@0](kubectl-installer-v0.md) | Install Kubectl on agent machine. |
| **Node.js tool installer**<br>[NodeTool@0](node-tool-v0.md) | Finds or downloads and caches the specified version spec of Node.js and adds it to the PATH. |
| **NuGet tool installer**<br>[NuGetToolInstaller@1](nuget-tool-installer-v1.md)<br>[NuGetToolInstaller@0](nuget-tool-installer-v0.md) | Acquires a specific version of NuGet from the internet or the tools cache and adds it to the PATH. Use this task to change the version of NuGet used in the NuGet tasks. |
| **Use .NET Core**<br>[UseDotNet@2](use-dotnet-v2.md) | Acquires a specific version of the .NET Core SDK from the internet or the local cache and adds it to the PATH. Use this task to change the version of .NET Core used in subsequent tasks. Additionally provides proxy support. |
| **Use Node.js ecosystem**<br>[UseNode@1](use-node-v1.md) | Set up a Node.js environment and add it to the PATH, additionally providing proxy support. |
| **Use Python version**<br>[UsePythonVersion@0](use-python-version-v0.md) | Use the specified version of Python from the tool cache, optionally adding it to the PATH. |
| **Use Ruby version**<br>[UseRubyVersion@0](use-ruby-version-v0.md) | Use the specified version of Ruby from the tool cache, optionally adding it to the PATH. |
| **Visual Studio test platform installer**<br>[VisualStudioTestPlatformInstaller@1](visual-studio-test-platform-installer-v1.md) | Acquire the test platform from nuget.org or the tool cache. Satisfies the ‘vstest’ demand and can be used for running tests and collecting diagnostic data using the Visual Studio Test task. |
## Utility tasks

| Task | Description |
|---|---|
| **Archive files**<br>[ArchiveFiles@2](archive-files-v2.md) | Compress files into .7z, .tar.gz, or .zip. |
| **Archive Files**<br>[ArchiveFiles@1](archive-files-v1.md) | Archive files using compression formats such as .7z, .rar, .tar.gz, and .zip. |
| **Azure Network Load Balancer**<br>[AzureNLBManagement@1](azure-nlb-management-v1.md) | Connect or disconnect an Azure virtual machine's network interface to a Load Balancer's back end address pool. |
| **Bash**<br>[Bash@3](bash-v3.md) | Run a Bash script on macOS, Linux, or Windows. |
| **Batch script**<br>[BatchScript@1](batch-script-v1.md) | Run a Windows command or batch script and optionally allow it to change the environment. |
| **Cache**<br>[Cache@2](cache-v2.md) | Cache files between runs. |
| **Cache (Beta)**<br>[CacheBeta@1](cache-beta-v1.md)<br>[CacheBeta@0](cache-beta-v0.md) | Cache files between runs. |
| **Command Line**<br>[CmdLine@2](cmd-line-v2.md)<br>[CmdLine@1](cmd-line-v1.md) | Run a command line script using Bash on Linux and macOS and cmd.exe on Windows. |
| **Copy and Publish Build Artifacts**<br>[CopyPublishBuildArtifacts@1](copy-publish-build-artifacts-v1.md) | CopyPublishBuildArtifacts@1 is deprecated. Use the Copy Files task and the Publish Build Artifacts task instead. |
| **Copy files**<br>[CopyFiles@2](copy-files-v2.md) | Copy files from a source folder to a target folder using patterns matching file paths (not folder paths). |
| **Copy Files**<br>[CopyFiles@1](copy-files-v1.md) | Copy files from source folder to target folder using minimatch patterns (The minimatch patterns will only match file paths, not folder paths). |
| **cURL Upload Files**<br>[cURLUploader@2](curl-uploader-v2.md)<br>[cURLUploader@1](curl-uploader-v1.md) | Use cURL's supported protocols to upload files. |
| **Decrypt file (OpenSSL)**<br>[DecryptFile@1](decrypt-file-v1.md) | Decrypt a file using OpenSSL. |
| **Delay**<br>[Delay@1](delay-v1.md) | Delay further execution of a workflow by a fixed time. |
| **Delete files**<br>[DeleteFiles@1](delete-files-v1.md) | Delete folders, or files matching a pattern. |
| **Download artifacts from file share**<br>[DownloadFileshareArtifacts@1](download-fileshare-artifacts-v1.md) | Download artifacts from a file share, like \\share\drop. |
| **Download build artifacts**<br>[DownloadBuildArtifacts@0](download-build-artifacts-v0.md) | Download files that were saved as artifacts of a completed build. |
| **Download GitHub Release**<br>[DownloadGitHubRelease@0](download-github-release-v0.md) | Downloads a GitHub Release from a repository. |
| **Download package**<br>[DownloadPackage@1](download-package-v1.md)<br>[DownloadPackage@0](download-package-v0.md) | Download a package from a package management feed in Azure Artifacts. |
| **Download Pipeline Artifacts**<br>[DownloadPipelineArtifact@2](download-pipeline-artifact-v2.md)<br>[DownloadPipelineArtifact@1](download-pipeline-artifact-v1.md)<br>[DownloadPipelineArtifact@0](download-pipeline-artifact-v0.md) | Download build and pipeline artifacts. |
| **Download secure file**<br>[DownloadSecureFile@1](download-secure-file-v1.md) | Download a secure file to the agent machine. |
| **Extract files**<br>[ExtractFiles@1](extract-files-v1.md) | Extract a variety of archive and compression files such as .7z, .rar, .tar.gz, and .zip. |
| **File transform**<br>[FileTransform@2](file-transform-v2.md)<br>[FileTransform@1](file-transform-v1.md) | Replace tokens with variable values in XML or JSON configuration files. |
| **FTP upload**<br>[FtpUpload@2](ftp-upload-v2.md)<br>[FtpUpload@1](ftp-upload-v1.md) | Upload files using FTP. |
| **GitHub Comment**<br>[GitHubComment@0](github-comment-v0.md) | Write a comment to your GitHub entity i.e. issue or a pull request (PR). |
| **GitHub Release**<br>[GitHubRelease@1](github-release-v1.md)<br>[GitHubRelease@0](github-release-v0.md) | Create, edit, or delete a GitHub release. |
| **Install Apple certificate**<br>[InstallAppleCertificate@2](install-apple-certificate-v2.md) | Install an Apple certificate required to build on a macOS agent machine. |
| **Install Apple Certificate**<br>[InstallAppleCertificate@1](install-apple-certificate-v1.md)<br>[InstallAppleCertificate@0](install-apple-certificate-v0.md) | Install an Apple certificate required to build on a macOS agent. |
| **Install Apple provisioning profile**<br>[InstallAppleProvisioningProfile@1](install-apple-provisioning-profile-v1.md) | Install an Apple provisioning profile required to build on a macOS agent machine. |
| **Install Apple Provisioning Profile**<br>[InstallAppleProvisioningProfile@0](install-apple-provisioning-profile-v0.md) | Install an Apple provisioning profile required to build on a macOS agent. |
| **Install SSH key**<br>[InstallSSHKey@0](install-ssh-key-v0.md) | Install an SSH key prior to a build or deployment. |
| **Invoke Azure Function**<br>[AzureFunction@1](azure-function-v1.md)<br>[AzureFunction@0](azure-function-v0.md) | Invoke an Azure Function. |
| **Jenkins download artifacts**<br>[JenkinsDownloadArtifacts@1](jenkins-download-artifacts-v1.md) | Download artifacts produced by a Jenkins job. |
| **PowerShell**<br>[PowerShell@2](powershell-v2.md)<br>[PowerShell@1](powershell-v1.md) | Run a PowerShell script on Linux, macOS, or Windows. |
| **Publish build artifacts**<br>[PublishBuildArtifacts@1](publish-build-artifacts-v1.md) | Publish build artifacts to Azure Pipelines or a Windows file share. |
| **Publish Pipeline Artifacts**<br>[PublishPipelineArtifact@1](publish-pipeline-artifact-v1.md)<br>[PublishPipelineArtifact@0](publish-pipeline-artifact-v0.md) | Publish (upload) a file or directory as a named artifact for the current run. |
| **Publish Pipeline Metadata**<br>[PublishPipelineMetadata@0](publish-pipeline-metadata-v0.md) | Publish Pipeline Metadata to Evidence store. |
| **Publish To Azure Service Bus**<br>[PublishToAzureServiceBus@1](publish-to-azure-service-bus-v1.md)<br>[PublishToAzureServiceBus@0](publish-to-azure-service-bus-v0.md) | Sends a message to Azure Service Bus using a service connection (no agent is required). |
| **Python script**<br>[PythonScript@0](python-script-v0.md) | Run a Python file or inline script. |
| **Query Azure Monitor alerts**<br>[AzureMonitor@1](azure-monitor-v1.md) | Observe the configured Azure Monitor rules for active alerts. |
| **Query Classic Azure Monitor alerts**<br>[AzureMonitor@0](azure-monitor-v0.md) | Observe the configured classic Azure Monitor rules for active alerts. |
| **Query work items**<br>[queryWorkItems@0](query-work-items-v0.md) | Execute a work item query and check the number of items returned. |
| **Review App**<br>[ReviewApp@0](review-app-v0.md) | Use this task under deploy phase provider to create a resource dynamically. |
| **Service Fabric PowerShell**<br>[ServiceFabricPowerShell@1](service-fabric-powershell-v1.md) | Run a PowerShell script in the context of an Azure Service Fabric cluster connection. |
| **Shell script**<br>[ShellScript@2](shell-script-v2.md) | Run a shell script using Bash. |
| **Update Service Fabric App Versions**<br>[ServiceFabricUpdateAppVersions@1](service-fabric-update-app-versions-v1.md) | Automatically updates the versions of a packaged Service Fabric application. |
| **Update Service Fabric manifests**<br>[ServiceFabricUpdateManifests@2](service-fabric-update-manifests-v2.md) | Automatically update portions of application and service manifests in a packaged Azure Service Fabric application. |
| **Xamarin License**<br>[XamarinLicense@1](xamarin-license-v1.md) | [Deprecated] Upgrade to free version of Xamarin: https://store.xamarin.com. |

:::moniker-end

:::moniker range="=azure-pipelines-2020"

## Build tasks

| Task | Description |
|---|---|
| **.NET Core**<br>[DotNetCoreCLI@2](dotnet-core-cli-v2.md)<br>[DotNetCoreCLI@1](dotnet-core-cli-v1.md)<br>[DotNetCoreCLI@0](dotnet-core-cli-v0.md) | Build, test, package, or publish a dotnet application, or run a custom dotnet command. |
| **Android Build**<br>[AndroidBuild@1](android-build-v1.md) | AndroidBuild@1 is deprecated. Use Gradle. |
| **Android Signing**<br>[AndroidSigning@3](android-signing-v3.md)<br>[AndroidSigning@2](android-signing-v2.md)<br>[AndroidSigning@1](android-signing-v1.md) | Sign and align Android APK files. |
| **Ant**<br>[Ant@1](ant-v1.md) | Build with Apache Ant. |
| **Azure IoT Edge**<br>[AzureIoTEdge@2](azure-iot-edge-v2.md) | Build and deploy an Azure IoT Edge image. |
| **CMake**<br>[CMake@1](cmake-v1.md) | Build with the CMake cross-platform build system. |
| **Container Build**<br>[ContainerBuild@0](container-build-v0.md) | Container Build Task. |
| **Docker**<br>[Docker@2](docker-v2.md)<br>[Docker@1](docker-v1.md)<br>[Docker@0](docker-v0.md) | Build or push Docker images, login or logout, or run a Docker command. |
| **Docker Compose**<br>[DockerCompose@0](docker-compose-v0.md) | Build, push or run multi-container Docker applications. Task can be used with Docker or Azure Container registry. |
| **Download GitHub Nuget Packages**<br>[DownloadGitHubNugetPackage@1](download-github-nuget-package-v1.md) | Restore your nuget packages using dotnet CLI. |
| **Go**<br>[Go@0](go-v0.md) | Get, build, or test a Go application, or run a custom Go command. |
| **Gradle**<br>[Gradle@2](gradle-v2.md)<br>[Gradle@1](gradle-v1.md) | Build using a Gradle wrapper script. |
| **Grunt**<br>[Grunt@0](grunt-v0.md) | Run the Grunt JavaScript task runner. |
| **gulp**<br>[gulp@1](gulp-v1.md)<br>[gulp@0](gulp-v0.md) | Run the gulp Node.js streaming task-based build system. |
| **Index sources and publish symbols**<br>[PublishSymbols@2](publish-symbols-v2.md)<br>[PublishSymbols@1](publish-symbols-v1.md) | Index your source code and publish symbols to a file share or Azure Artifacts symbol server. |
| **Jenkins queue job**<br>[JenkinsQueueJob@2](jenkins-queue-job-v2.md) | Queue a job on a Jenkins server. |
| **Jenkins Queue Job**<br>[JenkinsQueueJob@1](jenkins-queue-job-v1.md) | Queue a job on a Jenkins server. |
| **Maven**<br>[Maven@3](maven-v3.md)<br>[Maven@2](maven-v2.md)<br>[Maven@1](maven-v1.md) | Build, test, and deploy with Apache Maven. |
| **MSBuild**<br>[MSBuild@1](msbuild-v1.md) | Build with MSBuild. |
| **Visual Studio build**<br>[VSBuild@1](vsbuild-v1.md) | Build with MSBuild and set the Visual Studio version property. |
| **Xamarin.Android**<br>[XamarinAndroid@1](xamarin-android-v1.md) | Build an Android app with Xamarin. |
| **Xamarin.iOS**<br>[XamariniOS@2](xamarin-ios-v2.md)<br>[XamariniOS@1](xamarin-ios-v1.md) | Build an iOS app with Xamarin on macOS. |
| **Xcode**<br>[Xcode@5](xcode-v5.md)<br>[Xcode@4](xcode-v4.md) | Build, test, or archive an Xcode workspace on macOS. Optionally package an app. |
| **Xcode Build**<br>[Xcode@3](xcode-v3.md)<br>[Xcode@2](xcode-v2.md) | Build an Xcode workspace on macOS. |
| **Xcode Package iOS**<br>[XcodePackageiOS@0](xcode-package-ios-v0.md) | Generate an .ipa file from Xcode build output using xcrun (Xcode 7 or below). |
## Deploy tasks

| Task | Description |
|---|---|
| **App Center distribute**<br>[AppCenterDistribute@3](app-center-distribute-v3.md)<br>[AppCenterDistribute@2](app-center-distribute-v2.md)<br>[AppCenterDistribute@1](app-center-distribute-v1.md)<br>[AppCenterDistribute@0](app-center-distribute-v0.md) | Distribute app builds to testers and users via Visual Studio App Center. |
| **ARM template deployment**<br>[AzureResourceManagerTemplateDeployment@3](azure-resource-manager-template-deployment-v3.md) | Deploy an Azure Resource Manager (ARM) template to all the deployment scopes. |
| **Azure App Service Classic (Deprecated)**<br>[AzureWebPowerShellDeployment@1](azure-web-powershell-deployment-v1.md) | Create or update Azure App Service using Azure PowerShell. |
| **Azure App Service deploy**<br>[AzureRmWebAppDeployment@4](azure-rm-web-app-deployment-v4.md)<br>[AzureRmWebAppDeployment@3](azure-rm-web-app-deployment-v3.md)<br>[AzureRmWebAppDeployment@2](azure-rm-web-app-deployment-v2.md) | Deploy to Azure App Service a web, mobile, or API app using Docker, Java, .NET, .NET Core, Node.js, PHP, Python, or Ruby. |
| **Azure App Service manage**<br>[AzureAppServiceManage@0](azure-app-service-manage-v0.md) | Start, stop, restart, slot swap, slot delete, install site extensions or enable continuous monitoring for an Azure App Service. |
| **Azure App Service Settings**<br>[AzureAppServiceSettings@1](azure-app-service-settings-v1.md) | Update/Add App settings an Azure Web App for Linux or Windows. |
| **Azure CLI**<br>[AzureCLI@2](azure-cli-v2.md)<br>[AzureCLI@1](azure-cli-v1.md) | Run Azure CLI commands against an Azure subscription in a PowerShell Core/Shell script when running on Linux agent or PowerShell/Powershell Core/Batch script when running on Windows agent. |
| **Azure CLI Preview**<br>[AzureCLI@0](azure-cli-v0.md) | Run a Shell or Batch script with Azure CLI commands against an azure subscription. |
| **Azure Cloud Service deployment**<br>[AzureCloudPowerShellDeployment@1](azure-cloud-powershell-deployment-v1.md) | Deploy an Azure Cloud Service. |
| **Azure Database for MySQL deployment**<br>[AzureMysqlDeployment@1](azure-mysql-deployment-v1.md) | Run your scripts and make changes to your Azure Database for MySQL. |
| **Azure file copy**<br>[AzureFileCopy@4](azure-file-copy-v4.md)<br>[AzureFileCopy@3](azure-file-copy-v3.md)<br>[AzureFileCopy@2](azure-file-copy-v2.md)<br>[AzureFileCopy@1](azure-file-copy-v1.md) | Copy files to Azure Blob Storage or virtual machines. |
| **Azure Function on Kubernetes**<br>[AzureFunctionOnKubernetes@0](azure-function-on-kubernetes-v0.md) | Deploy Azure function to Kubernetes cluster. |
| **Azure Functions Deploy**<br>[AzureFunctionApp@1](azure-function-app-v1.md) | Update a function app with .NET, Python, JavaScript, PowerShell, Java based web applications. |
| **Azure Functions for container**<br>[AzureFunctionAppContainer@1](azure-function-app-container-v1.md) | Update a function app with a Docker container. |
| **Azure Key Vault**<br>[AzureKeyVault@1](azure-key-vault-v1.md) | Download Azure Key Vault secrets. |
| **Azure Monitor alerts (Deprecated)**<br>[AzureMonitorAlerts@0](azure-monitor-alerts-v0.md) | Configure alerts on available metrics for an Azure resource (Deprecated). |
| **Azure PowerShell**<br>[AzurePowerShell@5](azure-powershell-v5.md)<br>[AzurePowerShell@4](azure-powershell-v4.md)<br>[AzurePowerShell@3](azure-powershell-v3.md)<br>[AzurePowerShell@2](azure-powershell-v2.md)<br>[AzurePowerShell@1](azure-powershell-v1.md) | Run a PowerShell script within an Azure environment. |
| **Azure resource group deployment**<br>[AzureResourceGroupDeployment@2](azure-resource-group-deployment-v2.md) | Deploy an Azure Resource Manager (ARM) template to a resource group and manage virtual machines. |
| **Azure Resource Group Deployment**<br>[AzureResourceGroupDeployment@1](azure-resource-group-deployment-v1.md) | Deploy, start, stop, delete Azure Resource Groups. |
| **Azure SQL Database deployment**<br>[SqlAzureDacpacDeployment@1](sql-azure-dacpac-deployment-v1.md) | Deploy an Azure SQL Database using DACPAC or run scripts using SQLCMD. |
| **Azure VM scale set deployment**<br>[AzureVmssDeployment@0](azure-vmss-deployment-v0.md) | Deploy a virtual machine scale set image. |
| **Azure Web App**<br>[AzureWebApp@1](azure-web-app-v1.md) | Deploy an Azure Web App for Linux or Windows. |
| **Azure Web App for Containers**<br>[AzureWebAppContainer@1](azure-web-app-container-v1.md) | Deploy containers to Azure App Service. |
| **Build machine image**<br>[PackerBuild@1](packer-build-v1.md)<br>[PackerBuild@0](packer-build-v0.md) | Build a machine image using Packer, which may be used for Azure Virtual machine scale set deployment. |
| **Check Azure Policy compliance**<br>[AzurePolicyCheckGate@0](azure-policy-check-gate-v0.md) | Security and compliance assessment for Azure Policy. |
| **Chef**<br>[Chef@1](chef-v1.md) | Deploy to Chef environments by editing environment attributes. |
| **Chef Knife**<br>[ChefKnife@1](chef-knife-v1.md) | Run scripts with Knife commands on your Chef workstation. |
| **Copy files over SSH**<br>[CopyFilesOverSSH@0](copy-files-over-ssh-v0.md) | Copy files or build artifacts to a remote machine over SSH. |
| **Deploy to Kubernetes**<br>[KubernetesManifest@0](kubernetes-manifest-v0.md) | Use Kubernetes manifest files to deploy to clusters or even bake the manifest files to be used for deployments using Helm charts. |
| **IIS web app deploy**<br>[IISWebAppDeploymentOnMachineGroup@0](iisweb-app-deployment-on-machine-group-v0.md) | Deploy a website or web application using Web Deploy. |
| **IIS Web App deployment (Deprecated)**<br>[IISWebAppDeployment@1](iisweb-app-deployment-v1.md) | Deploy using MSDeploy, then create/update websites and app pools. |
| **IIS web app manage**<br>[IISWebAppManagementOnMachineGroup@0](iisweb-app-management-on-machine-group-v0.md) | Create or update websites, web apps, virtual directories, or application pools. |
| **Invoke REST API**<br>[InvokeRESTAPI@1](invoke-rest-api-v1.md)<br>[InvokeRESTAPI@0](invoke-rest-api-v0.md) | Invoke a REST API as a part of your pipeline. |
| **Kubectl**<br>[Kubernetes@1](kubernetes-v1.md)<br>[Kubernetes@0](kubernetes-v0.md) | Deploy, configure, update a Kubernetes cluster in Azure Container Service by running kubectl commands. |
| **Manual intervention**<br>[ManualIntervention@8](manual-intervention-v8.md) | Pause deployment and wait for manual intervention. |
| **MySQL database deploy**<br>[MysqlDeploymentOnMachineGroup@1](mysql-deployment-on-machine-group-v1.md) | Run scripts and make changes to a MySQL Database. |
| **Package and deploy Helm charts**<br>[HelmDeploy@0](helm-deploy-v0.md) | Deploy, configure, update a Kubernetes cluster in Azure Container Service by running helm commands. |
| **PowerShell on target machines**<br>[PowerShellOnTargetMachines@3](powershell-on-target-machines-v3.md) | Execute PowerShell scripts on remote machines using PSSession and Invoke-Command for remoting. |
| **PowerShell on Target Machines**<br>[PowerShellOnTargetMachines@2](powershell-on-target-machines-v2.md)<br>[PowerShellOnTargetMachines@1](powershell-on-target-machines-v1.md) | Execute PowerShell scripts on remote machine(s). |
| **Service Fabric application deployment**<br>[ServiceFabricDeploy@1](service-fabric-deploy-v1.md) | Deploy an Azure Service Fabric application to a cluster. |
| **Service Fabric Compose deploy**<br>[ServiceFabricComposeDeploy@0](service-fabric-compose-deploy-v0.md) | Deploy a Docker Compose application to an Azure Service Fabric cluster. |
| **SQL Server database deploy**<br>[SqlDacpacDeploymentOnMachineGroup@0](sql-dacpac-deployment-on-machine-group-v0.md) | Deploy a SQL Server database using DACPAC or SQL scripts. |
| **SQL Server database deploy (Deprecated)**<br>[SqlServerDacpacDeployment@1](sql-server-dacpac-deployment-v1.md) | Deploy a SQL Server database using DACPAC. |
| **SSH**<br>[SSH@0](ssh-v0.md) | Run shell commands or a script on a remote machine using SSH. |
| **Windows machine file copy**<br>[WindowsMachineFileCopy@2](windows-machine-file-copy-v2.md)<br>[WindowsMachineFileCopy@1](windows-machine-file-copy-v1.md) | Copy files to remote Windows machines. |
## Package tasks

| Task | Description |
|---|---|
| **CocoaPods**<br>[CocoaPods@0](cocoa-pods-v0.md) | Install CocoaPods dependencies for Swift and Objective-C Cocoa projects. |
| **Conda environment**<br>[CondaEnvironment@1](conda-environment-v1.md)<br>[CondaEnvironment@0](conda-environment-v0.md) | This task is deprecated. Use `conda` directly in script to work with Anaconda environments. |
| **Download Github Npm Package**<br>[DownloadGithubNpmPackage@1](download-github-npm-package-v1.md) | Install npm packages from GitHub. |
| **Maven Authenticate**<br>[MavenAuthenticate@0](maven-authenticate-v0.md) | Provides credentials for Azure Artifacts feeds and external maven repositories. |
| **npm**<br>[Npm@1](npm-v1.md)<br>[Npm@0](npm-v0.md) | Install and publish npm packages, or run an npm command. Supports npmjs.com and authenticated registries like Azure Artifacts. |
| **npm authenticate (for task runners)**<br>[npmAuthenticate@0](npm-authenticate-v0.md) | Don't use this task if you're also using the npm task. Provides npm credentials to an .npmrc file in your repository for the scope of the build. This enables npm task runners like gulp and Grunt to authenticate with private registries. |
| **NuGet**<br>[NuGetCommand@2](nuget-command-v2.md) | Restore, pack, or push NuGet packages, or run a NuGet command. Supports NuGet.org and authenticated feeds like Azure Artifacts and MyGet. Uses NuGet.exe and works with .NET Framework apps. For .NET Core and .NET Standard apps, use the .NET Core task. |
| **NuGet authenticate**<br>[NuGetAuthenticate@0](nuget-authenticate-v0.md) | Configure NuGet tools to authenticate with Azure Artifacts and other NuGet repositories. Requires NuGet >= 4.8.5385, dotnet >= 2.1.400, or MSBuild >= 15.8.166.59604. |
| **NuGet command**<br>[NuGet@0](nuget-v0.md) | Deprecated: use the “NuGet” task instead. It works with the new Tool Installer framework so you can easily use new versions of NuGet without waiting for a task update, provides better support for authenticated feeds outside this organization/collection, and uses NuGet 4 by default. |
| **NuGet Installer**<br>[NuGetInstaller@0](nuget-installer-v0.md) | Installs or restores missing NuGet packages. Use NuGetAuthenticate@0 task for latest capabilities. |
| **NuGet packager**<br>[NuGetPackager@0](nuget-packager-v0.md) | Deprecated: use the “NuGet” task instead. It works with the new Tool Installer framework so you can easily use new versions of NuGet without waiting for a task update, provides better support for authenticated feeds outside this organization/collection, and uses NuGet 4 by default. |
| **NuGet publisher**<br>[NuGetPublisher@0](nuget-publisher-v0.md) | Deprecated: use the “NuGet” task instead. It works with the new Tool Installer framework so you can easily use new versions of NuGet without waiting for a task update, provides better support for authenticated feeds outside this organization/collection, and uses NuGet 4 by default. |
| **NuGet Restore**<br>[NuGetRestore@1](nuget-restore-v1.md) | Restores NuGet packages in preparation for a Visual Studio Build step. |
| **PyPI publisher**<br>[PyPIPublisher@0](py-pi-publisher-v0.md) | Create and upload an sdist or wheel to a PyPI-compatible index using Twine. |
| **Python pip authenticate**<br>[PipAuthenticate@1](pip-authenticate-v1.md)<br>[PipAuthenticate@0](pip-authenticate-v0.md) | Authentication task for the pip client used for installing Python distributions. |
| **Python twine upload authenticate**<br>[TwineAuthenticate@1](twine-authenticate-v1.md)<br>[TwineAuthenticate@0](twine-authenticate-v0.md) | Authenticate for uploading Python distributions using twine. Add '-r FeedName/EndpointName --config-file $(PYPIRC_PATH)' to your twine upload command. For feeds present in this organization, use the feed name as the repository (-r). Otherwise, use the endpoint name defined in the service connection. |
| **Universal packages**<br>[UniversalPackages@0](universal-packages-v0.md) | Download or publish Universal Packages. |
| **Xamarin Component Restore**<br>[XamarinComponentRestore@0](xamarin-component-restore-v0.md) | This task is deprecated. Use 'NuGet' instead. |
## Test tasks

| Task | Description |
|---|---|
| **App Center test**<br>[AppCenterTest@1](app-center-test-v1.md) | Test app packages with Visual Studio App Center. |
| **Container Structure Test**<br>[ContainerStructureTest@0](container-structure-test-v0.md) | Uses container-structure-test (https://github.com/GoogleContainerTools/container-structure-test) to validate the structure of an image based on four categories of tests - command tests, file existence tests, file content tests and metadata tests. |
| **Mobile Center Test**<br>[VSMobileCenterTest@0](vsmobile-center-test-v0.md) | Test mobile app packages with Visual Studio Mobile Center. |
| **Publish code coverage results**<br>[PublishCodeCoverageResults@1](publish-code-coverage-results-v1.md) | Publish Cobertura or JaCoCo code coverage results from a build. |
| **Publish test results**<br>[PublishTestResults@1](publish-test-results-v1.md) | Publish test results to Azure Pipelines. |
| **Publish Test Results**<br>[PublishTestResults@2](publish-test-results-v2.md) | Publish test results to Azure Pipelines. |
| **Run functional tests**<br>[RunVisualStudioTestsusingTestAgent@1](run-visual-studio-testsusing-test-agent-v1.md) | Deprecated: This task and it’s companion task (Visual Studio Test Agent Deployment) are deprecated. Use the 'Visual Studio Test' task instead. The VSTest task can run unit as well as functional tests. Run tests on one or more agents using the multi-agent job setting. Use the 'Visual Studio Test Platform' task to run tests without needing Visual Studio on the agent. VSTest task also brings new capabilities such as automatically rerunning failed tests. |
| **Visual Studio Test**<br>[VSTest@2](vstest-v2.md)<br>[VSTest@1](vstest-v1.md) | Run unit and functional tests (Selenium, Appium, Coded UI test, etc.) using the Visual Studio Test (VsTest) runner. Test frameworks that have a Visual Studio test adapter such as MsTest, xUnit, NUnit, Chutzpah (for JavaScript tests using QUnit, Mocha and Jasmine), etc. can be run. Tests can be distributed on multiple agents using this task (version 2). |
| **Visual Studio test agent deployment**<br>[DeployVisualStudioTestAgent@2](deploy-visual-studio-test-agent-v2.md) | DeployVisualStudioTestAgent@2 is deprecated. Use the Visual Studio Test task to run unit and functional tests. |
| **Visual Studio Test Agent Deployment**<br>[DeployVisualStudioTestAgent@1](deploy-visual-studio-test-agent-v1.md) | Deploy and configure Test Agent to run tests on a set of machines. |
| **Xamarin Test Cloud**<br>[XamarinTestCloud@1](xamarin-test-cloud-v1.md) | [Deprecated] Test mobile apps with Xamarin Test Cloud using Xamarin.UITest. Instead, use the 'App Center test' task. |
## Tool tasks

| Task | Description |
|---|---|
| **.NET Core SDK/runtime installer**<br>[DotNetCoreInstaller@1](dotnet-core-installer-v1.md)<br>[DotNetCoreInstaller@0](dotnet-core-installer-v0.md) | Acquire a specific version of the .NET Core SDK from the internet or local cache and add it to the PATH. |
| **Docker CLI installer**<br>[DockerInstaller@0](docker-installer-v0.md) | Install Docker CLI on agent machine. |
| **Duffle tool installer**<br>[DuffleInstaller@0](duffle-installer-v0.md) | Install a specified version of Duffle for installing and managing CNAB bundles. |
| **Go tool installer**<br>[GoTool@0](go-tool-v0.md) | Find in cache or download a specific version of Go and add it to the PATH. |
| **Helm tool installer**<br>[HelmInstaller@1](helm-installer-v1.md)<br>[HelmInstaller@0](helm-installer-v0.md) | Install Helm on an agent machine. |
| **Install Azure Func Core Tools**<br>[FuncToolsInstaller@0](func-tools-installer-v0.md) | Install Azure Func Core Tools. |
| **Java tool installer**<br>[JavaToolInstaller@0](java-tool-installer-v0.md) | Acquire a specific version of Java from a user-supplied Azure blob or the tool cache and sets JAVA_HOME. |
| **Kubectl tool installer**<br>[KubectlInstaller@0](kubectl-installer-v0.md) | Install Kubectl on agent machine. |
| **Node.js tool installer**<br>[NodeTool@0](node-tool-v0.md) | Finds or downloads and caches the specified version spec of Node.js and adds it to the PATH. |
| **NuGet tool installer**<br>[NuGetToolInstaller@1](nuget-tool-installer-v1.md)<br>[NuGetToolInstaller@0](nuget-tool-installer-v0.md) | Acquires a specific version of NuGet from the internet or the tools cache and adds it to the PATH. Use this task to change the version of NuGet used in the NuGet tasks. |
| **Use .NET Core**<br>[UseDotNet@2](use-dotnet-v2.md) | Acquires a specific version of the .NET Core SDK from the internet or the local cache and adds it to the PATH. Use this task to change the version of .NET Core used in subsequent tasks. Additionally provides proxy support. |
| **Use Node.js ecosystem**<br>[UseNode@1](use-node-v1.md) | Set up a Node.js environment and add it to the PATH, additionally providing proxy support. |
| **Use Python version**<br>[UsePythonVersion@0](use-python-version-v0.md) | Use the specified version of Python from the tool cache, optionally adding it to the PATH. |
| **Use Ruby version**<br>[UseRubyVersion@0](use-ruby-version-v0.md) | Use the specified version of Ruby from the tool cache, optionally adding it to the PATH. |
| **Visual Studio test platform installer**<br>[VisualStudioTestPlatformInstaller@1](visual-studio-test-platform-installer-v1.md) | Acquire the test platform from nuget.org or the tool cache. Satisfies the ‘vstest’ demand and can be used for running tests and collecting diagnostic data using the Visual Studio Test task. |
## Utility tasks

| Task | Description |
|---|---|
| **Archive files**<br>[ArchiveFiles@2](archive-files-v2.md) | Compress files into .7z, .tar.gz, or .zip. |
| **Archive Files**<br>[ArchiveFiles@1](archive-files-v1.md) | Archive files using compression formats such as .7z, .rar, .tar.gz, and .zip. |
| **Azure Network Load Balancer**<br>[AzureNLBManagement@1](azure-nlb-management-v1.md) | Connect or disconnect an Azure virtual machine's network interface to a Load Balancer's back end address pool. |
| **Bash**<br>[Bash@3](bash-v3.md) | Run a Bash script on macOS, Linux, or Windows. |
| **Batch script**<br>[BatchScript@1](batch-script-v1.md) | Run a Windows command or batch script and optionally allow it to change the environment. |
| **Cache**<br>[Cache@2](cache-v2.md) | Cache files between runs. |
| **Cache (Beta)**<br>[CacheBeta@1](cache-beta-v1.md)<br>[CacheBeta@0](cache-beta-v0.md) | Cache files between runs. |
| **Command Line**<br>[CmdLine@2](cmd-line-v2.md)<br>[CmdLine@1](cmd-line-v1.md) | Run a command line script using Bash on Linux and macOS and cmd.exe on Windows. |
| **Copy and Publish Build Artifacts**<br>[CopyPublishBuildArtifacts@1](copy-publish-build-artifacts-v1.md) | CopyPublishBuildArtifacts@1 is deprecated. Use the Copy Files task and the Publish Build Artifacts task instead. |
| **Copy files**<br>[CopyFiles@2](copy-files-v2.md) | Copy files from a source folder to a target folder using patterns matching file paths (not folder paths). |
| **Copy Files**<br>[CopyFiles@1](copy-files-v1.md) | Copy files from source folder to target folder using minimatch patterns (The minimatch patterns will only match file paths, not folder paths). |
| **cURL Upload Files**<br>[cURLUploader@2](curl-uploader-v2.md)<br>[cURLUploader@1](curl-uploader-v1.md) | Use cURL's supported protocols to upload files. |
| **Decrypt file (OpenSSL)**<br>[DecryptFile@1](decrypt-file-v1.md) | Decrypt a file using OpenSSL. |
| **Delay**<br>[Delay@1](delay-v1.md) | Delay further execution of a workflow by a fixed time. |
| **Delete files**<br>[DeleteFiles@1](delete-files-v1.md) | Delete folders, or files matching a pattern. |
| **Download artifacts from file share**<br>[DownloadFileshareArtifacts@1](download-fileshare-artifacts-v1.md) | Download artifacts from a file share, like \\share\drop. |
| **Download build artifacts**<br>[DownloadBuildArtifacts@0](download-build-artifacts-v0.md) | Download files that were saved as artifacts of a completed build. |
| **Download GitHub Release**<br>[DownloadGitHubRelease@0](download-github-release-v0.md) | Downloads a GitHub Release from a repository. |
| **Download package**<br>[DownloadPackage@1](download-package-v1.md)<br>[DownloadPackage@0](download-package-v0.md) | Download a package from a package management feed in Azure Artifacts. |
| **Download Pipeline Artifacts**<br>[DownloadPipelineArtifact@2](download-pipeline-artifact-v2.md)<br>[DownloadPipelineArtifact@1](download-pipeline-artifact-v1.md)<br>[DownloadPipelineArtifact@0](download-pipeline-artifact-v0.md) | Download build and pipeline artifacts. |
| **Download secure file**<br>[DownloadSecureFile@1](download-secure-file-v1.md) | Download a secure file to the agent machine. |
| **Extract files**<br>[ExtractFiles@1](extract-files-v1.md) | Extract a variety of archive and compression files such as .7z, .rar, .tar.gz, and .zip. |
| **File transform**<br>[FileTransform@2](file-transform-v2.md)<br>[FileTransform@1](file-transform-v1.md) | Replace tokens with variable values in XML or JSON configuration files. |
| **FTP upload**<br>[FtpUpload@2](ftp-upload-v2.md)<br>[FtpUpload@1](ftp-upload-v1.md) | Upload files using FTP. |
| **GitHub Comment**<br>[GitHubComment@0](github-comment-v0.md) | Write a comment to your GitHub entity i.e. issue or a pull request (PR). |
| **GitHub Release**<br>[GitHubRelease@1](github-release-v1.md)<br>[GitHubRelease@0](github-release-v0.md) | Create, edit, or delete a GitHub release. |
| **Install Apple certificate**<br>[InstallAppleCertificate@2](install-apple-certificate-v2.md) | Install an Apple certificate required to build on a macOS agent machine. |
| **Install Apple Certificate**<br>[InstallAppleCertificate@1](install-apple-certificate-v1.md)<br>[InstallAppleCertificate@0](install-apple-certificate-v0.md) | Install an Apple certificate required to build on a macOS agent. |
| **Install Apple provisioning profile**<br>[InstallAppleProvisioningProfile@1](install-apple-provisioning-profile-v1.md) | Install an Apple provisioning profile required to build on a macOS agent machine. |
| **Install Apple Provisioning Profile**<br>[InstallAppleProvisioningProfile@0](install-apple-provisioning-profile-v0.md) | Install an Apple provisioning profile required to build on a macOS agent. |
| **Install SSH key**<br>[InstallSSHKey@0](install-ssh-key-v0.md) | Install an SSH key prior to a build or deployment. |
| **Invoke Azure Function**<br>[AzureFunction@1](azure-function-v1.md)<br>[AzureFunction@0](azure-function-v0.md) | Invoke an Azure Function. |
| **Jenkins download artifacts**<br>[JenkinsDownloadArtifacts@1](jenkins-download-artifacts-v1.md) | Download artifacts produced by a Jenkins job. |
| **PowerShell**<br>[PowerShell@2](powershell-v2.md)<br>[PowerShell@1](powershell-v1.md) | Run a PowerShell script on Linux, macOS, or Windows. |
| **Publish build artifacts**<br>[PublishBuildArtifacts@1](publish-build-artifacts-v1.md) | Publish build artifacts to Azure Pipelines or a Windows file share. |
| **Publish Pipeline Artifacts**<br>[PublishPipelineArtifact@1](publish-pipeline-artifact-v1.md)<br>[PublishPipelineArtifact@0](publish-pipeline-artifact-v0.md) | Publish (upload) a file or directory as a named artifact for the current run. |
| **Publish Pipeline Metadata**<br>[PublishPipelineMetadata@0](publish-pipeline-metadata-v0.md) | Publish Pipeline Metadata to Evidence store. |
| **Publish To Azure Service Bus**<br>[PublishToAzureServiceBus@1](publish-to-azure-service-bus-v1.md)<br>[PublishToAzureServiceBus@0](publish-to-azure-service-bus-v0.md) | Sends a message to Azure Service Bus using a service connection (no agent is required). |
| **Python script**<br>[PythonScript@0](python-script-v0.md) | Run a Python file or inline script. |
| **Query Azure Monitor alerts**<br>[AzureMonitor@1](azure-monitor-v1.md) | Observe the configured Azure Monitor rules for active alerts. |
| **Query Classic Azure Monitor alerts**<br>[AzureMonitor@0](azure-monitor-v0.md) | Observe the configured classic Azure Monitor rules for active alerts. |
| **Query work items**<br>[queryWorkItems@0](query-work-items-v0.md) | Execute a work item query and check the number of items returned. |
| **Review App**<br>[ReviewApp@0](review-app-v0.md) | Use this task under deploy phase provider to create a resource dynamically. |
| **Service Fabric PowerShell**<br>[ServiceFabricPowerShell@1](service-fabric-powershell-v1.md) | Run a PowerShell script in the context of an Azure Service Fabric cluster connection. |
| **Shell script**<br>[ShellScript@2](shell-script-v2.md) | Run a shell script using Bash. |
| **Update Service Fabric App Versions**<br>[ServiceFabricUpdateAppVersions@1](service-fabric-update-app-versions-v1.md) | Automatically updates the versions of a packaged Service Fabric application. |
| **Update Service Fabric manifests**<br>[ServiceFabricUpdateManifests@2](service-fabric-update-manifests-v2.md) | Automatically update portions of application and service manifests in a packaged Azure Service Fabric application. |
| **Xamarin License**<br>[XamarinLicense@1](xamarin-license-v1.md) | [Deprecated] Upgrade to free version of Xamarin: https://store.xamarin.com. |

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

## Build tasks

| Task | Description |
|---|---|
| **.NET Core**<br>[DotNetCoreCLI@2](dotnet-core-cli-v2.md)<br>[DotNetCoreCLI@1](dotnet-core-cli-v1.md)<br>[DotNetCoreCLI@0](dotnet-core-cli-v0.md) | Build, test, package, or publish a dotnet application, or run a custom dotnet command. |
| **Android Build**<br>[AndroidBuild@1](android-build-v1.md) | AndroidBuild@1 is deprecated. Use Gradle. |
| **Android Signing**<br>[AndroidSigning@3](android-signing-v3.md)<br>[AndroidSigning@2](android-signing-v2.md)<br>[AndroidSigning@1](android-signing-v1.md) | Sign and align Android APK files. |
| **Ant**<br>[Ant@1](ant-v1.md) | Build with Apache Ant. |
| **Azure IoT Edge**<br>[AzureIoTEdge@2](azure-iot-edge-v2.md) | Build and deploy an Azure IoT Edge image. |
| **CMake**<br>[CMake@1](cmake-v1.md) | Build with the CMake cross-platform build system. |
| **Docker**<br>[Docker@2](docker-v2.md)<br>[Docker@1](docker-v1.md)<br>[Docker@0](docker-v0.md) | Build or push Docker images, login or logout, or run a Docker command. |
| **Docker Compose**<br>[DockerCompose@0](docker-compose-v0.md) | Build, push or run multi-container Docker applications. Task can be used with Docker or Azure Container registry. |
| **Go**<br>[Go@0](go-v0.md) | Get, build, or test a Go application, or run a custom Go command. |
| **Gradle**<br>[Gradle@2](gradle-v2.md)<br>[Gradle@1](gradle-v1.md) | Build using a Gradle wrapper script. |
| **Grunt**<br>[Grunt@0](grunt-v0.md) | Run the Grunt JavaScript task runner. |
| **Gulp**<br>[Gulp@1](gulp-v1.md)<br>[Gulp@0](gulp-v0.md) | Node.js streaming task based build system. |
| **Index sources and publish symbols**<br>[PublishSymbols@2](publish-symbols-v2.md)<br>[PublishSymbols@1](publish-symbols-v1.md) | Index your source code and publish symbols to a file share or Azure Artifacts symbol server. |
| **Jenkins queue job**<br>[JenkinsQueueJob@2](jenkins-queue-job-v2.md) | Queue a job on a Jenkins server. |
| **Jenkins Queue Job**<br>[JenkinsQueueJob@1](jenkins-queue-job-v1.md) | Queue a job on a Jenkins server. |
| **Maven**<br>[Maven@3](maven-v3.md)<br>[Maven@2](maven-v2.md)<br>[Maven@1](maven-v1.md) | Build, test, and deploy with Apache Maven. |
| **MSBuild**<br>[MSBuild@1](msbuild-v1.md) | Build with MSBuild. |
| **Visual Studio build**<br>[VSBuild@1](vsbuild-v1.md) | Build with MSBuild and set the Visual Studio version property. |
| **Xamarin.Android**<br>[XamarinAndroid@1](xamarin-android-v1.md) | Build an Android app with Xamarin. |
| **Xamarin.iOS**<br>[XamariniOS@2](xamarin-ios-v2.md)<br>[XamariniOS@1](xamarin-ios-v1.md) | Build an iOS app with Xamarin on macOS. |
| **Xcode**<br>[Xcode@5](xcode-v5.md)<br>[Xcode@4](xcode-v4.md) | Build, test, or archive an Xcode workspace on macOS. Optionally package an app. |
| **Xcode Build**<br>[Xcode@3](xcode-v3.md)<br>[Xcode@2](xcode-v2.md) | Build an Xcode workspace on macOS. |
| **Xcode Package iOS**<br>[XcodePackageiOS@0](xcode-package-ios-v0.md) | Generate an .ipa file from Xcode build output using xcrun (Xcode 7 or below). |
## Deploy tasks

| Task | Description |
|---|---|
| **App Center distribute**<br>[AppCenterDistribute@3](app-center-distribute-v3.md)<br>[AppCenterDistribute@2](app-center-distribute-v2.md)<br>[AppCenterDistribute@1](app-center-distribute-v1.md)<br>[AppCenterDistribute@0](app-center-distribute-v0.md) | Distribute app builds to testers and users via Visual Studio App Center. |
| **Azure App Service Classic (Deprecated)**<br>[AzureWebPowerShellDeployment@1](azure-web-powershell-deployment-v1.md) | Create or update Azure App Service using Azure PowerShell. |
| **Azure App Service deploy**<br>[AzureRmWebAppDeployment@4](azure-rm-web-app-deployment-v4.md)<br>[AzureRmWebAppDeployment@3](azure-rm-web-app-deployment-v3.md)<br>[AzureRmWebAppDeployment@2](azure-rm-web-app-deployment-v2.md) | Deploy to Azure App Service a web, mobile, or API app using Docker, Java, .NET, .NET Core, Node.js, PHP, Python, or Ruby. |
| **Azure App Service manage**<br>[AzureAppServiceManage@0](azure-app-service-manage-v0.md) | Start, stop, restart, slot swap, install site extensions or enable continuous monitoring for an Azure App Service. |
| **Azure CLI**<br>[AzureCLI@1](azure-cli-v1.md) | Run Azure CLI commands against an Azure subscription in a Shell script when running on Linux agent or Batch script when running on Windows agent. |
| **Azure CLI Preview**<br>[AzureCLI@0](azure-cli-v0.md) | Run a Shell or Batch script with Azure CLI commands against an azure subscription. |
| **Azure Cloud Service deployment**<br>[AzureCloudPowerShellDeployment@1](azure-cloud-powershell-deployment-v1.md) | Deploy an Azure Cloud Service. |
| **Azure Database for MySQL deployment**<br>[AzureMysqlDeployment@1](azure-mysql-deployment-v1.md) | Run your scripts and make changes to your Azure Database for MySQL. |
| **Azure file copy**<br>[AzureFileCopy@3](azure-file-copy-v3.md)<br>[AzureFileCopy@2](azure-file-copy-v2.md)<br>[AzureFileCopy@1](azure-file-copy-v1.md) | Copy files to Azure Blob Storage or virtual machines. |
| **Azure Function for container**<br>[AzureFunctionAppContainer@1](azure-function-app-container-v1.md) | Update Function Apps with Docker containers. |
| **Azure Functions Deploy**<br>[AzureFunctionApp@1](azure-function-app-v1.md) | Deploy an Azure Function for Linux or Windows. |
| **Azure Key Vault**<br>[AzureKeyVault@1](azure-key-vault-v1.md) | Download Azure Key Vault secrets. |
| **Azure Monitor alerts**<br>[AzureMonitorAlerts@0](azure-monitor-alerts-v0.md) | Configure alerts on available metrics for an Azure resource. |
| **Azure PowerShell**<br>[AzurePowerShell@4](azure-powershell-v4.md)<br>[AzurePowerShell@3](azure-powershell-v3.md)<br>[AzurePowerShell@2](azure-powershell-v2.md)<br>[AzurePowerShell@1](azure-powershell-v1.md) | Run a PowerShell script within an Azure environment. |
| **Azure resource group deployment**<br>[AzureResourceGroupDeployment@2](azure-resource-group-deployment-v2.md) | Deploy an Azure Resource Manager (ARM) template to a resource group and manage virtual machines. |
| **Azure Resource Group Deployment**<br>[AzureResourceGroupDeployment@1](azure-resource-group-deployment-v1.md) | Deploy, start, stop, delete Azure Resource Groups. |
| **Azure SQL Database deployment**<br>[SqlAzureDacpacDeployment@1](sql-azure-dacpac-deployment-v1.md) | Deploy an Azure SQL Database using DACPAC or run scripts using SQLCMD. |
| **Azure VM scale set deployment**<br>[AzureVmssDeployment@0](azure-vmss-deployment-v0.md) | Deploy a virtual machine scale set image. |
| **Azure Web App**<br>[AzureWebApp@1](azure-web-app-v1.md) | Deploy an Azure Web App for Linux or Windows. |
| **Azure Web App for Containers**<br>[AzureWebAppContainer@1](azure-web-app-container-v1.md) | Deploy containers to Azure App Service. |
| **Build machine image**<br>[PackerBuild@1](packer-build-v1.md)<br>[PackerBuild@0](packer-build-v0.md) | Build a machine image using Packer, which may be used for Azure Virtual machine scale set deployment. |
| **Check Azure Policy compliance**<br>[AzurePolicyCheckGate@0](azure-policy-check-gate-v0.md) | Security and compliance assessment for Azure Policy. |
| **Chef**<br>[Chef@1](chef-v1.md) | Deploy to Chef environments by editing environment attributes. |
| **Chef Knife**<br>[ChefKnife@1](chef-knife-v1.md) | Run scripts with Knife commands on your Chef workstation. |
| **Copy files over SSH**<br>[CopyFilesOverSSH@0](copy-files-over-ssh-v0.md) | Copy files or build artifacts to a remote machine over SSH. |
| **Deploy Kubernetes manifests**<br>[KubernetesManifest@0](kubernetes-manifest-v0.md) | Use Kubernetes manifest files to deploy to clusters or even bake the manifest files to be used for deployments using Helm charts. |
| **Deploy to Kubernetes**<br>[Kubernetes@1](kubernetes-v1.md)<br>[Kubernetes@0](kubernetes-v0.md) | Deploy, configure, update a Kubernetes cluster in Azure Container Service by running kubectl commands. |
| **IIS web app deploy**<br>[IISWebAppDeploymentOnMachineGroup@0](iisweb-app-deployment-on-machine-group-v0.md) | Deploy a website or web application using Web Deploy. |
| **IIS Web App deployment (Deprecated)**<br>[IISWebAppDeployment@1](iisweb-app-deployment-v1.md) | Deploy using MSDeploy, then create/update websites and app pools. |
| **IIS web app manage**<br>[IISWebAppManagementOnMachineGroup@0](iisweb-app-management-on-machine-group-v0.md) | Create or update websites, web apps, virtual directories, or application pools. |
| **Invoke REST API**<br>[InvokeRESTAPI@1](invoke-rest-api-v1.md)<br>[InvokeRESTAPI@0](invoke-rest-api-v0.md) | Invoke a REST API as a part of your pipeline. |
| **Manual intervention**<br>[ManualIntervention@8](manual-intervention-v8.md) | Pause deployment and wait for manual intervention. |
| **MySQL database deploy**<br>[MysqlDeploymentOnMachineGroup@1](mysql-deployment-on-machine-group-v1.md) | Run scripts and make changes to a MySQL Database. |
| **Package and deploy Helm charts**<br>[HelmDeploy@0](helm-deploy-v0.md) | Deploy, configure, update a Kubernetes cluster in Azure Container Service by running helm commands. |
| **PowerShell on target machines**<br>[PowerShellOnTargetMachines@3](powershell-on-target-machines-v3.md) | Execute PowerShell scripts on remote machines using PSSession and Invoke-Command for remoting. |
| **PowerShell on Target Machines**<br>[PowerShellOnTargetMachines@2](powershell-on-target-machines-v2.md)<br>[PowerShellOnTargetMachines@1](powershell-on-target-machines-v1.md) | Execute PowerShell scripts on remote machine(s). |
| **Service Fabric application deployment**<br>[ServiceFabricDeploy@1](service-fabric-deploy-v1.md) | Deploy an Azure Service Fabric application to a cluster. |
| **Service Fabric Compose deploy**<br>[ServiceFabricComposeDeploy@0](service-fabric-compose-deploy-v0.md) | Deploy a Docker Compose application to an Azure Service Fabric cluster. |
| **SQL Server database deploy**<br>[SqlDacpacDeploymentOnMachineGroup@0](sql-dacpac-deployment-on-machine-group-v0.md) | Deploy a SQL Server database using DACPAC or SQL scripts. |
| **SQL Server database deploy (Deprecated)**<br>[SqlServerDacpacDeployment@1](sql-server-dacpac-deployment-v1.md) | Deploy a SQL Server database using DACPAC. |
| **SSH**<br>[SSH@0](ssh-v0.md) | Run shell commands or a script on a remote machine using SSH. |
| **Windows machine file copy**<br>[WindowsMachineFileCopy@2](windows-machine-file-copy-v2.md)<br>[WindowsMachineFileCopy@1](windows-machine-file-copy-v1.md) | Copy files to remote Windows machines. |
## Package tasks

| Task | Description |
|---|---|
| **CocoaPods**<br>[CocoaPods@0](cocoa-pods-v0.md) | Install CocoaPods dependencies for Swift and Objective-C Cocoa projects. |
| **Conda environment**<br>[CondaEnvironment@1](conda-environment-v1.md)<br>[CondaEnvironment@0](conda-environment-v0.md) | This task is deprecated. Use `conda` directly in script to work with Anaconda environments. |
| **npm**<br>[Npm@1](npm-v1.md)<br>[Npm@0](npm-v0.md) | Install and publish npm packages, or run an npm command. Supports npmjs.com and authenticated registries like Azure Artifacts. |
| **npm Authenticate (for task runners)**<br>[npmAuthenticate@0](npm-authenticate-v0.md) | Don't use this task if you're also using the npm task. Provides npm credentials to an .npmrc file in your repository for the scope of the build. This enables npm task runners like Gulp and Grunt to authenticate with private registries. |
| **NuGet**<br>[NuGetCommand@2](nuget-command-v2.md) | Restore, pack, or push NuGet packages, or run a NuGet command. Supports NuGet.org and authenticated feeds like Azure Artifacts and MyGet. Uses NuGet.exe and works with .NET Framework apps. For .NET Core and .NET Standard apps, use the .NET Core task. |
| **NuGet command**<br>[NuGet@0](nuget-v0.md) | Deprecated: use the “NuGet” task instead. It works with the new Tool Installer framework so you can easily use new versions of NuGet without waiting for a task update, provides better support for authenticated feeds outside this organization/collection, and uses NuGet 4 by default. |
| **NuGet Installer**<br>[NuGetInstaller@0](nuget-installer-v0.md) | Installs or restores missing NuGet packages. |
| **NuGet packager**<br>[NuGetPackager@0](nuget-packager-v0.md) | Deprecated: use the “NuGet” task instead. It works with the new Tool Installer framework so you can easily use new versions of NuGet without waiting for a task update, provides better support for authenticated feeds outside this organization/collection, and uses NuGet 4 by default. |
| **NuGet publisher**<br>[NuGetPublisher@0](nuget-publisher-v0.md) | Deprecated: use the “NuGet” task instead. It works with the new Tool Installer framework so you can easily use new versions of NuGet without waiting for a task update, provides better support for authenticated feeds outside this organization/collection, and uses NuGet 4 by default. |
| **NuGet Restore**<br>[NuGetRestore@1](nuget-restore-v1.md) | Restores NuGet packages in preparation for a Visual Studio Build step. |
| **PyPI publisher**<br>[PyPIPublisher@0](py-pi-publisher-v0.md) | Create and upload an sdist or wheel to a PyPI-compatible index using Twine. |
| **Python pip authenticate**<br>[PipAuthenticate@0](pip-authenticate-v0.md) | Authentication task for the pip client used for installing Python distributions. |
| **Python twine upload authenticate**<br>[TwineAuthenticate@0](twine-authenticate-v0.md) | Authenticate for uploading Python distributions using twine. Add '-r FeedName/EndpointName --config-file $(PYPIRC_PATH)' to your twine upload command. For feeds present in this organization, use the feed name as the repository (-r). Otherwise, use the endpoint name defined in the service connection. |
| **Universal packages**<br>[UniversalPackages@0](universal-packages-v0.md) | Download or publish Universal Packages. |
| **Xamarin Component Restore**<br>[XamarinComponentRestore@0](xamarin-component-restore-v0.md) | This task is deprecated. Use 'NuGet' instead. |
## Test tasks

| Task | Description |
|---|---|
| **App Center test**<br>[AppCenterTest@1](app-center-test-v1.md) | Test app packages with Visual Studio App Center. |
| **Mobile Center Test**<br>[VSMobileCenterTest@0](vsmobile-center-test-v0.md) | Test mobile app packages with Visual Studio Mobile Center. |
| **Publish code coverage results**<br>[PublishCodeCoverageResults@1](publish-code-coverage-results-v1.md) | Publish Cobertura or JaCoCo code coverage results from a build. |
| **Publish test results**<br>[PublishTestResults@1](publish-test-results-v1.md) | Publish test results to Azure Pipelines. |
| **Publish Test Results**<br>[PublishTestResults@2](publish-test-results-v2.md) | Publish test results to Azure Pipelines. |
| **Run functional tests**<br>[RunVisualStudioTestsusingTestAgent@1](run-visual-studio-testsusing-test-agent-v1.md) | Deprecated: This task and it’s companion task (Visual Studio Test Agent Deployment) are deprecated. Use the 'Visual Studio Test' task instead. The VSTest task can run unit as well as functional tests. Run tests on one or more agents using the multi-agent job setting. Use the 'Visual Studio Test Platform' task to run tests without needing Visual Studio on the agent. VSTest task also brings new capabilities such as automatically rerunning failed tests. |
| **Visual Studio Test**<br>[VSTest@2](vstest-v2.md)<br>[VSTest@1](vstest-v1.md) | Run unit and functional tests (Selenium, Appium, Coded UI test, etc.) using the Visual Studio Test (VsTest) runner. Test frameworks that have a Visual Studio test adapter such as MsTest, xUnit, NUnit, Chutzpah (for JavaScript tests using QUnit, Mocha and Jasmine), etc. can be run. Tests can be distributed on multiple agents using this task (version 2). |
| **Visual Studio test agent deployment**<br>[DeployVisualStudioTestAgent@2](deploy-visual-studio-test-agent-v2.md) | DeployVisualStudioTestAgent@2 is deprecated. Use the Visual Studio Test task to run unit and functional tests. |
| **Visual Studio Test Agent Deployment**<br>[DeployVisualStudioTestAgent@1](deploy-visual-studio-test-agent-v1.md) | Deploy and configure Test Agent to run tests on a set of machines. |
| **Xamarin Test Cloud**<br>[XamarinTestCloud@1](xamarin-test-cloud-v1.md) | [Deprecated] Test mobile apps with Xamarin Test Cloud using Xamarin.UITest. Instead, use the 'App Center test' task. |
## Tool tasks

| Task | Description |
|---|---|
| **.NET Core SDK/runtime installer**<br>[DotNetCoreInstaller@1](dotnet-core-installer-v1.md)<br>[DotNetCoreInstaller@0](dotnet-core-installer-v0.md) | Acquire a specific version of the .NET Core SDK from the internet or local cache and add it to the PATH. |
| **Docker CLI installer**<br>[DockerInstaller@0](docker-installer-v0.md) | Install Docker CLI on agent machine. |
| **Duffle tool installer**<br>[DuffleInstaller@0](duffle-installer-v0.md) | Install a specified version of Duffle for installing and managing CNAB bundles. |
| **Go tool installer**<br>[GoTool@0](go-tool-v0.md) | Find in cache or download a specific version of Go and add it to the PATH. |
| **Helm tool installer**<br>[HelmInstaller@1](helm-installer-v1.md)<br>[HelmInstaller@0](helm-installer-v0.md) | Install Helm on an agent machine. |
| **Java tool installer**<br>[JavaToolInstaller@0](java-tool-installer-v0.md) | Acquire a specific version of Java from a user-supplied Azure blob or the tool cache and sets JAVA_HOME. |
| **Kubectl tool installer**<br>[KubectlInstaller@0](kubectl-installer-v0.md) | Install Kubectl on agent machine. |
| **Node.js tool installer**<br>[NodeTool@0](node-tool-v0.md) | Finds or downloads and caches the specified version spec of Node.js and adds it to the PATH. |
| **NuGet tool installer**<br>[NuGetToolInstaller@1](nuget-tool-installer-v1.md)<br>[NuGetToolInstaller@0](nuget-tool-installer-v0.md) | Acquires a specific version of NuGet from the internet or the tools cache and adds it to the PATH. Use this task to change the version of NuGet used in the NuGet tasks. |
| **Use dotnet**<br>[UseDotNet@2](use-dotnet-v2.md) | Acquires a specific version of the .NET Core SDK from the internet or the local cache and adds it to the PATH. Use this task to change the version of .NET Core used in subsequent tasks. Additionally provides proxy support. |
| **Use Node.js ecosystem**<br>[UseNode@1](use-node-v1.md) | Set up a Node.js environment and add it to the PATH, additionally providing proxy support. |
| **Use Python version**<br>[UsePythonVersion@0](use-python-version-v0.md) | Use the specified version of Python from the tool cache, optionally adding it to the PATH. |
| **Use Ruby version**<br>[UseRubyVersion@0](use-ruby-version-v0.md) | Use the specified version of Ruby from the tool cache, optionally adding it to the PATH. |
| **Visual Studio test platform installer**<br>[VisualStudioTestPlatformInstaller@1](visual-studio-test-platform-installer-v1.md) | Acquire the test platform from nuget.org or the tool cache. Satisfies the ‘vstest’ demand and can be used for running tests and collecting diagnostic data using the Visual Studio Test task. |
## Utility tasks

| Task | Description |
|---|---|
| **Archive files**<br>[ArchiveFiles@2](archive-files-v2.md) | Compress files into .7z, .tar.gz, or .zip. |
| **Archive Files**<br>[ArchiveFiles@1](archive-files-v1.md) | Archive files using compression formats such as .7z, .rar, .tar.gz, and .zip. |
| **Azure Network Load Balancer**<br>[AzureNLBManagement@1](azure-nlb-management-v1.md) | Connect or disconnect an Azure virtual machine's network interface to a Load Balancer's back end address pool. |
| **Bash**<br>[Bash@3](bash-v3.md) | Run a Bash script on macOS, Linux, or Windows. |
| **Batch script**<br>[BatchScript@1](batch-script-v1.md) | Run a Windows command or batch script and optionally allow it to change the environment. |
| **Command Line**<br>[CmdLine@2](cmd-line-v2.md)<br>[CmdLine@1](cmd-line-v1.md) | Run a command line script using Bash on Linux and macOS and cmd.exe on Windows. |
| **Copy and Publish Build Artifacts**<br>[CopyPublishBuildArtifacts@1](copy-publish-build-artifacts-v1.md) | CopyPublishBuildArtifacts@1 is deprecated. Use the Copy Files task and the Publish Build Artifacts task instead. |
| **Copy files**<br>[CopyFiles@2](copy-files-v2.md) | Copy files from a source folder to a target folder using patterns matching file paths (not folder paths). |
| **Copy Files**<br>[CopyFiles@1](copy-files-v1.md) | Copy files from source folder to target folder using minimatch patterns (The minimatch patterns will only match file paths, not folder paths). |
| **cURL Upload Files**<br>[cURLUploader@2](curl-uploader-v2.md)<br>[cURLUploader@1](curl-uploader-v1.md) | Use cURL's supported protocols to upload files. |
| **Decrypt file (OpenSSL)**<br>[DecryptFile@1](decrypt-file-v1.md) | Decrypt a file using OpenSSL. |
| **Delay**<br>[Delay@1](delay-v1.md) | Delay further execution of a workflow by a fixed time. |
| **Delete files**<br>[DeleteFiles@1](delete-files-v1.md) | Delete folders, or files matching a pattern. |
| **Download artifacts from file share**<br>[DownloadFileshareArtifacts@1](download-fileshare-artifacts-v1.md) | Download artifacts from a file share, like \\share\drop. |
| **Download build artifacts**<br>[DownloadBuildArtifacts@0](download-build-artifacts-v0.md) | Download files that were saved as artifacts of a completed build. |
| **Download GitHub Release**<br>[DownloadGitHubRelease@0](download-github-release-v0.md) | Downloads a GitHub Release from a repository. |
| **Download package**<br>[DownloadPackage@1](download-package-v1.md)<br>[DownloadPackage@0](download-package-v0.md) | Download a package from a package management feed in Azure Artifacts. |
| **Download Pipeline Artifacts**<br>[DownloadPipelineArtifact@1](download-pipeline-artifact-v1.md)<br>[DownloadPipelineArtifact@0](download-pipeline-artifact-v0.md) | Download Pipeline Artifact. |
| **Download secure file**<br>[DownloadSecureFile@1](download-secure-file-v1.md) | Download a secure file to a temporary location on the agent machine. |
| **Extract files**<br>[ExtractFiles@1](extract-files-v1.md) | Extract a variety of archive and compression files such as .7z, .rar, .tar.gz, and .zip. |
| **File transform**<br>[FileTransform@1](file-transform-v1.md) | Replace tokens with variable values in XML or JSON configuration files. |
| **FTP upload**<br>[FtpUpload@2](ftp-upload-v2.md)<br>[FtpUpload@1](ftp-upload-v1.md) | Upload files using FTP. |
| **GitHub Release**<br>[GitHubRelease@0](github-release-v0.md) | Create, edit, or delete a GitHub release. |
| **Install Apple certificate**<br>[InstallAppleCertificate@2](install-apple-certificate-v2.md) | Install an Apple certificate required to build on a macOS agent machine. |
| **Install Apple Certificate**<br>[InstallAppleCertificate@1](install-apple-certificate-v1.md)<br>[InstallAppleCertificate@0](install-apple-certificate-v0.md) | Install an Apple certificate required to build on a macOS agent. |
| **Install Apple provisioning profile**<br>[InstallAppleProvisioningProfile@1](install-apple-provisioning-profile-v1.md) | Install an Apple provisioning profile required to build on a macOS agent machine. |
| **Install Apple Provisioning Profile**<br>[InstallAppleProvisioningProfile@0](install-apple-provisioning-profile-v0.md) | Install an Apple provisioning profile required to build on a macOS agent. |
| **Install SSH key**<br>[InstallSSHKey@0](install-ssh-key-v0.md) | Install an SSH key prior to a build or deployment. |
| **Invoke Azure Function**<br>[AzureFunction@1](azure-function-v1.md)<br>[AzureFunction@0](azure-function-v0.md) | Invoke an Azure Function. |
| **Jenkins download artifacts**<br>[JenkinsDownloadArtifacts@1](jenkins-download-artifacts-v1.md) | Download artifacts produced by a Jenkins job. |
| **PowerShell**<br>[PowerShell@2](powershell-v2.md)<br>[PowerShell@1](powershell-v1.md) | Run a PowerShell script on Linux, macOS, or Windows. |
| **Publish build artifacts**<br>[PublishBuildArtifacts@1](publish-build-artifacts-v1.md) | Publish build artifacts to Azure Pipelines or a Windows file share. |
| **Publish Pipeline Artifacts**<br>[PublishPipelineArtifact@0](publish-pipeline-artifact-v0.md) | Publish Pipeline Artifact. |
| **Publish To Azure Service Bus**<br>[PublishToAzureServiceBus@1](publish-to-azure-service-bus-v1.md)<br>[PublishToAzureServiceBus@0](publish-to-azure-service-bus-v0.md) | Sends a message to Azure Service Bus using a service connection (no agent is required). |
| **Python script**<br>[PythonScript@0](python-script-v0.md) | Run a Python file or inline script. |
| **Query Azure Monitor alerts**<br>[AzureMonitor@1](azure-monitor-v1.md) | Observe the configured Azure Monitor rules for active alerts. |
| **Query Classic Azure Monitor alerts**<br>[AzureMonitor@0](azure-monitor-v0.md) | Observe the configured classic Azure Monitor rules for active alerts. |
| **Query work items**<br>[queryWorkItems@0](query-work-items-v0.md) | Execute a work item query and check the number of items returned. |
| **Service Fabric PowerShell**<br>[ServiceFabricPowerShell@1](service-fabric-powershell-v1.md) | Run a PowerShell script in the context of an Azure Service Fabric cluster connection. |
| **Shell Script**<br>[ShellScript@2](shell-script-v2.md) | Run a shell script using bash. |
| **Update Service Fabric App Versions**<br>[ServiceFabricUpdateAppVersions@1](service-fabric-update-app-versions-v1.md) | Automatically updates the versions of a packaged Service Fabric application. |
| **Update Service Fabric manifests**<br>[ServiceFabricUpdateManifests@2](service-fabric-update-manifests-v2.md) | Automatically update portions of application and service manifests in a packaged Azure Service Fabric application. |
| **Xamarin License**<br>[XamarinLicense@1](xamarin-license-v1.md) | [Deprecated] Upgrade to free version of Xamarin: https://store.xamarin.com. |

:::moniker-end

:::moniker range="=azure-pipelines-2019"

## Build tasks

| Task | Description |
|---|---|
| **.NET Core**<br>[DotNetCoreCLI@2](dotnet-core-cli-v2.md)<br>[DotNetCoreCLI@1](dotnet-core-cli-v1.md)<br>[DotNetCoreCLI@0](dotnet-core-cli-v0.md) | Build, test, package, or publish a dotnet application, or run a custom dotnet command. For package commands, supports NuGet.org and authenticated feeds like Package Management and MyGet. |
| **Android Build**<br>[AndroidBuild@1](android-build-v1.md) | AndroidBuild@1 is deprecated. Use Gradle. |
| **Android Signing**<br>[AndroidSigning@3](android-signing-v3.md)<br>[AndroidSigning@2](android-signing-v2.md)<br>[AndroidSigning@1](android-signing-v1.md) | Sign and align Android APK files. |
| **Ant**<br>[Ant@1](ant-v1.md) | Build with Apache Ant. |
| **CMake**<br>[CMake@1](cmake-v1.md) | Build with the CMake cross-platform build system. |
| **Docker**<br>[Docker@1](docker-v1.md)<br>[Docker@0](docker-v0.md) | Build, tag, push, or run Docker images, or run a Docker command. Task can be used with Docker or Azure Container registry. |
| **Docker Compose**<br>[DockerCompose@0](docker-compose-v0.md) | Build, push or run multi-container Docker applications. Task can be used with Docker or Azure Container registry. |
| **Go**<br>[Go@0](go-v0.md) | Get, build, or test a Go application, or run a custom Go command. |
| **Gradle**<br>[Gradle@2](gradle-v2.md)<br>[Gradle@1](gradle-v1.md) | Build using a Gradle wrapper script. |
| **Grunt**<br>[Grunt@0](grunt-v0.md) | The JavaScript Task Runner. |
| **Gulp**<br>[Gulp@0](gulp-v0.md) | Node.js streaming task based build system. |
| **Index sources and publish symbols**<br>[PublishSymbols@2](publish-symbols-v2.md)<br>[PublishSymbols@1](publish-symbols-v1.md) | Index your source code and publish symbols to a file share or Azure Artifacts Symbol Server. |
| **Jenkins Queue Job**<br>[JenkinsQueueJob@2](jenkins-queue-job-v2.md)<br>[JenkinsQueueJob@1](jenkins-queue-job-v1.md) | Queue a job on a Jenkins server. |
| **Maven**<br>[Maven@3](maven-v3.md)<br>[Maven@2](maven-v2.md)<br>[Maven@1](maven-v1.md) | Build with Apache Maven. |
| **MSBuild**<br>[MSBuild@1](msbuild-v1.md) | Build with MSBuild. |
| **Visual Studio Build**<br>[VSBuild@1](vsbuild-v1.md) | Build with MSBuild and set the Visual Studio version property. |
| **Xamarin.Android**<br>[XamarinAndroid@1](xamarin-android-v1.md) | Build an Android app with Xamarin. |
| **Xamarin.iOS**<br>[XamariniOS@2](xamarin-ios-v2.md)<br>[XamariniOS@1](xamarin-ios-v1.md) | Build an iOS app with Xamarin on macOS. |
| **Xcode**<br>[Xcode@5](xcode-v5.md)<br>[Xcode@4](xcode-v4.md) | Build, test, or archive an Xcode workspace on macOS. Optionally package an app. |
| **Xcode Build**<br>[Xcode@3](xcode-v3.md)<br>[Xcode@2](xcode-v2.md) | Build an Xcode workspace on macOS. |
| **Xcode Package iOS**<br>[XcodePackageiOS@0](xcode-package-ios-v0.md) | Generate an .ipa file from Xcode build output using xcrun (Xcode 7 or below). |
## Deploy tasks

| Task | Description |
|---|---|
| **App Center distribute**<br>[AppCenterDistribute@0](app-center-distribute-v0.md) | Distribute app builds to testers and users via App Center. |
| **App Center Distribute**<br>[AppCenterDistribute@1](app-center-distribute-v1.md) | Distribute app builds to testers and users via App Center. |
| **Azure App Service Classic (Deprecated)**<br>[AzureWebPowerShellDeployment@1](azure-web-powershell-deployment-v1.md) | Create or update Azure App Service using Azure PowerShell. |
| **Azure App Service deploy**<br>[AzureRmWebAppDeployment@2](azure-rm-web-app-deployment-v2.md) | Update Azure App Service using Web Deploy / Kudu REST APIs. |
| **Azure App Service Deploy**<br>[AzureRmWebAppDeployment@4](azure-rm-web-app-deployment-v4.md)<br>[AzureRmWebAppDeployment@3](azure-rm-web-app-deployment-v3.md) | Update Azure App Services on Windows, Web App on Linux with built-in images or Docker containers, ASP.NET, .NET Core, PHP, Python or Node.js based Web applications, Function Apps on Windows or Linux with Docker Containers, Mobile Apps, API applications, Web Jobs using Web Deploy / Kudu REST APIs. |
| **Azure App Service Manage**<br>[AzureAppServiceManage@0](azure-app-service-manage-v0.md) | Start, Stop, Restart, Slot swap, Install site extensions or Enable Continuous Monitoring for an Azure App Service. |
| **Azure CLI**<br>[AzureCLI@1](azure-cli-v1.md) | Run a Shell or Batch script with Azure CLI commands against an azure subscription. |
| **Azure CLI Preview**<br>[AzureCLI@0](azure-cli-v0.md) | Run a Shell or Batch script with Azure CLI commands against an azure subscription. |
| **Azure Cloud Service Deployment**<br>[AzureCloudPowerShellDeployment@1](azure-cloud-powershell-deployment-v1.md) | Deploy an Azure Cloud Service. |
| **Azure Database for MySQL Deployment**<br>[AzureMysqlDeployment@1](azure-mysql-deployment-v1.md) | Run your scripts and make changes to your Azure Database for MySQL. |
| **Azure File Copy**<br>[AzureFileCopy@2](azure-file-copy-v2.md)<br>[AzureFileCopy@1](azure-file-copy-v1.md) | Copy files to Azure blob or VM(s). |
| **Azure Key Vault**<br>[AzureKeyVault@1](azure-key-vault-v1.md) | Download Azure Key Vault Secrets. |
| **Azure Monitor Alerts**<br>[AzureMonitorAlerts@0](azure-monitor-alerts-v0.md) | Configure alerts on available metrics for an Azure resource. |
| **Azure PowerShell**<br>[AzurePowerShell@3](azure-powershell-v3.md)<br>[AzurePowerShell@2](azure-powershell-v2.md)<br>[AzurePowerShell@1](azure-powershell-v1.md) | Run a PowerShell script within an Azure environment. |
| **Azure Resource Group Deployment**<br>[AzureResourceGroupDeployment@2](azure-resource-group-deployment-v2.md)<br>[AzureResourceGroupDeployment@1](azure-resource-group-deployment-v1.md) | Deploy an Azure resource manager (ARM) template to a resource group. You can also start, stop, delete, deallocate all Virtual Machines (VM) in a resource group. |
| **Azure SQL Database Deployment**<br>[SqlAzureDacpacDeployment@1](sql-azure-dacpac-deployment-v1.md) | Deploy Azure SQL DB using DACPAC or run scripts using SQLCMD. |
| **Azure VM scale set Deployment**<br>[AzureVmssDeployment@0](azure-vmss-deployment-v0.md) | Deploy Virtual Machine scale set image. |
| **Build Machine Image**<br>[PackerBuild@0](packer-build-v0.md) | Build machine image using Packer. This image can be used for Azure Virtual machine scale set deployment. |
| **Chef**<br>[Chef@1](chef-v1.md) | Deploy to Chef environments by editing environment attributes. |
| **Chef Knife**<br>[ChefKnife@1](chef-knife-v1.md) | Run Scripts with knife commands on your chef workstation. |
| **Copy Files Over SSH**<br>[CopyFilesOverSSH@0](copy-files-over-ssh-v0.md) | Copy files or build artifacts to a remote machine over SSH. |
| **Deploy to Kubernetes**<br>[Kubernetes@1](kubernetes-v1.md)<br>[Kubernetes@0](kubernetes-v0.md) | Deploy, configure, update your Kubernetes cluster in Azure Container Service by running kubectl commands. |
| **IIS Web App Deploy**<br>[IISWebAppDeploymentOnMachineGroup@0](iisweb-app-deployment-on-machine-group-v0.md) | Deploy a website or web application using Web Deploy. |
| **IIS Web App deployment (Deprecated)**<br>[IISWebAppDeployment@1](iisweb-app-deployment-v1.md) | Deploy by MSDeploy, create/update website & app pools. |
| **IIS Web App Manage**<br>[IISWebAppManagementOnMachineGroup@0](iisweb-app-management-on-machine-group-v0.md) | Create or update a Website, Web App, Virtual Directories, and Application Pool. |
| **Invoke REST API**<br>[InvokeRESTAPI@1](invoke-rest-api-v1.md)<br>[InvokeRESTAPI@0](invoke-rest-api-v0.md) | Invoke a REST API as a part of your pipeline. |
| **Manual Intervention**<br>[ManualIntervention@8](manual-intervention-v8.md) | Pause deployment and wait for intervention. |
| **Package and deploy Helm charts**<br>[HelmDeploy@0](helm-deploy-v0.md) | Deploy, configure, update your Kubernetes cluster in Azure Container Service by running helm commands. |
| **PowerShell on Target Machines**<br>[PowerShellOnTargetMachines@3](powershell-on-target-machines-v3.md)<br>[PowerShellOnTargetMachines@2](powershell-on-target-machines-v2.md)<br>[PowerShellOnTargetMachines@1](powershell-on-target-machines-v1.md) | Execute PowerShell scripts on remote machine(s). This version of the task uses PSSession and Invoke-Command for remoting. |
| **Service Fabric Application Deployment**<br>[ServiceFabricDeploy@1](service-fabric-deploy-v1.md) | Deploy a Service Fabric application to a cluster. |
| **Service Fabric Compose Deploy**<br>[ServiceFabricComposeDeploy@0](service-fabric-compose-deploy-v0.md) | Deploy a docker-compose application to a Service Fabric cluster. |
| **SQL Server Database Deploy**<br>[SqlDacpacDeploymentOnMachineGroup@0](sql-dacpac-deployment-on-machine-group-v0.md) | Deploy to SQL Server Database using DACPAC or SQL scripts. |
| **SQL Server database deploy (Deprecated)**<br>[SqlServerDacpacDeployment@1](sql-server-dacpac-deployment-v1.md) | Deploy SQL Server Database using DACPAC. |
| **SSH**<br>[SSH@0](ssh-v0.md) | Run shell commands or a script on a remote machine using SSH. |
| **Windows Machine File Copy**<br>[WindowsMachineFileCopy@2](windows-machine-file-copy-v2.md)<br>[WindowsMachineFileCopy@1](windows-machine-file-copy-v1.md) | Copy files to remote machine(s). |
## Package tasks

| Task | Description |
|---|---|
| **CocoaPods**<br>[CocoaPods@0](cocoa-pods-v0.md) | CocoaPods is a dependency manager for Swift and Objective-C Cocoa projects. This task runs 'pod install'. |
| **Conda Environment**<br>[CondaEnvironment@1](conda-environment-v1.md)<br>[CondaEnvironment@0](conda-environment-v0.md) | Create and activate a Conda environment. |
| **npm**<br>[Npm@1](npm-v1.md)<br>[Npm@0](npm-v0.md) | Install and publish npm packages, or run an npm command. Supports npmjs.com and authenticated registries like Package Management. |
| **npm Authenticate (for task runners)**<br>[npmAuthenticate@0](npm-authenticate-v0.md) | Don't use this task if you're also using the npm task. Provides npm credentials to an .npmrc file in your repository for the scope of the build. This enables npm task runners like Gulp and Grunt to authenticate with private registries. |
| **NuGet**<br>[NuGetCommand@2](nuget-command-v2.md) | Restore, pack, or push NuGet packages, or run a NuGet command. Supports NuGet.org and authenticated feeds like Package Management and MyGet. Uses NuGet.exe and works with .NET Framework apps. For .NET Core and .NET Standard apps, use the .NET Core task. |
| **NuGet Command**<br>[NuGet@0](nuget-v0.md) | Deprecated: use the “NuGet” task instead. It works with the new Tool Installer framework so you can easily use new versions of NuGet without waiting for a task update, provides better support for authenticated feeds outside this account/collection, and uses NuGet 4 by default. |
| **NuGet Installer**<br>[NuGetInstaller@0](nuget-installer-v0.md) | Installs or restores missing NuGet packages. |
| **NuGet Packager**<br>[NuGetPackager@0](nuget-packager-v0.md) | Deprecated: use the “NuGet” task instead. It works with the new Tool Installer framework so you can easily use new versions of NuGet without waiting for a task update, provides better support for authenticated feeds outside this account/collection, and uses NuGet 4 by default. |
| **NuGet Publisher**<br>[NuGetPublisher@0](nuget-publisher-v0.md) | Deprecated: use the “NuGet” task instead. It works with the new Tool Installer framework so you can easily use new versions of NuGet without waiting for a task update, provides better support for authenticated feeds outside this account/collection, and uses NuGet 4 by default. |
| **NuGet Restore**<br>[NuGetRestore@1](nuget-restore-v1.md) | Restores NuGet packages in preparation for a Visual Studio Build step. |
| **PyPI Publisher**<br>[PyPIPublisher@0](py-pi-publisher-v0.md) | Create and upload an sdist or wheel to a PyPI-compatible index using Twine. |
| **Python Pip Authenticate**<br>[PipAuthenticate@0](pip-authenticate-v0.md) | Authentication task for pip client used for installing python distributions. |
| **Python Twine Upload Authenticate**<br>[TwineAuthenticate@0](twine-authenticate-v0.md) | Authentication for uploading python distributions using twine. Please add "-r FeedName/EndpointName --config-file $(PYPIRC_PATH)" to your twine upload command. For feeds present in this organization use feed name as repository(-r) otherwise use the endpoint name defined in the service connection. |
| **Universal Packages**<br>[UniversalPackages@0](universal-packages-v0.md) | Download or publish Universal Packages. |
| **Xamarin Component Restore**<br>[XamarinComponentRestore@0](xamarin-component-restore-v0.md) | This task is deprecated. Use 'NuGet' instead. |
## Test tasks

| Task | Description |
|---|---|
| **App Center Test**<br>[AppCenterTest@1](app-center-test-v1.md) | Test app packages with Visual Studio App Center. |
| **Mobile Center Test**<br>[VSMobileCenterTest@0](vsmobile-center-test-v0.md) | Test mobile app packages with Visual Studio Mobile Center. |
| **Publish Code Coverage Results**<br>[PublishCodeCoverageResults@1](publish-code-coverage-results-v1.md) | Publish Cobertura or JaCoCo code coverage results from a build. |
| **Publish Test Results**<br>[PublishTestResults@2](publish-test-results-v2.md)<br>[PublishTestResults@1](publish-test-results-v1.md) | Publish Test Results to Azure Pipelines/TFS. |
| **Run Functional Tests**<br>[RunVisualStudioTestsusingTestAgent@1](run-visual-studio-testsusing-test-agent-v1.md) | Deprecated: This task and it’s companion task (Visual Studio Test Agent Deployment) are deprecated. Use the 'Visual Studio Test' task instead. The VSTest task can run unit as well as functional tests. Run tests on one or more agents using the multi-agent job setting. Use the 'Visual Studio Test Platform' task to run tests without needing Visual Studio on the agent. VSTest task also brings new capabilities such as automatically rerunning failed tests. |
| **Visual Studio Test**<br>[VSTest@2](vstest-v2.md)<br>[VSTest@1](vstest-v1.md) | Run unit and functional tests (Selenium, Appium, Coded UI test, etc.) using the Visual Studio Test (VsTest) runner. Test frameworks that have a Visual Studio test adapter such as MsTest, xUnit, NUnit, Chutzpah (for JavaScript tests using QUnit, Mocha and Jasmine), etc. can be run. Tests can be distributed on multiple agents using this task (version 2). |
| **Visual Studio Test Agent Deployment**<br>[DeployVisualStudioTestAgent@2](deploy-visual-studio-test-agent-v2.md)<br>[DeployVisualStudioTestAgent@1](deploy-visual-studio-test-agent-v1.md) | DeployVisualStudioTestAgent@2 is deprecated. Use the Visual Studio Test task to run unit and functional tests. |
| **Xamarin Test Cloud**<br>[XamarinTestCloud@1](xamarin-test-cloud-v1.md) | [Depreciated] Testing mobile apps with Xamarin Test Cloud using Xamarin.UITest - recommended task is now AppCenterTest. |
## Tool tasks

| Task | Description |
|---|---|
| **.NET Core SDK/runtime installer**<br>[DotNetCoreInstaller@0](dotnet-core-installer-v0.md) | Acquire a specific version of the .NET Core SDK from the internet or local cache and add it to the PATH. |
| **Go Tool Installer**<br>[GoTool@0](go-tool-v0.md) | Finds or downloads a specific version of Go in the tools cache and adds it to the PATH. Use this to set the version of Go used in subsequent tasks. |
| **Helm tool installer**<br>[HelmInstaller@0](helm-installer-v0.md) | Install Helm and Kubernetes on agent machine. |
| **Java Tool Installer**<br>[JavaToolInstaller@0](java-tool-installer-v0.md) | Acquires a specific version of Java from a user supplied Azure blob or the tools cache and sets JAVA_HOME. Use this task to change the version of Java used in Java tasks. |
| **Node Tool Installer**<br>[NodeTool@0](node-tool-v0.md) | Finds or Downloads and caches specified version spec of Node and adds it to the PATH. |
| **NuGet Tool Installer**<br>[NuGetToolInstaller@0](nuget-tool-installer-v0.md) | Acquires a specific version of NuGet from the internet or the tools cache and adds it to the PATH. Use this task to change the version of NuGet used in the NuGet tasks. |
| **Use Python Version**<br>[UsePythonVersion@0](use-python-version-v0.md) | Retrieves the specified version of Python from the tool cache. Optionally add it to PATH. |
| **Use Ruby Version**<br>[UseRubyVersion@0](use-ruby-version-v0.md) | Retrieves the specified version of Ruby from the tool cache. Optionally add it to PATH. |
| **Visual Studio Test Platform Installer**<br>[VisualStudioTestPlatformInstaller@1](visual-studio-test-platform-installer-v1.md) | Acquires the test platform from nuget.org or the tools cache. Satisfies the ‘vstest’ demand and can be used for running tests and collecting diagnostic data using the Visual Studio Test task. |
## Utility tasks

| Task | Description |
|---|---|
| **Archive Files**<br>[ArchiveFiles@2](archive-files-v2.md)<br>[ArchiveFiles@1](archive-files-v1.md) | Archive files using compression formats such as .7z, .rar, .tar.gz, and .zip. |
| **Azure Network Load Balancer**<br>[AzureNLBManagement@1](azure-nlb-management-v1.md) | Connect/Disconnect an Azure virtual machine's network interface to a Load Balancer's backend address pool. |
| **Bash**<br>[Bash@3](bash-v3.md) | Run a Bash script on macOS, Linux, or Windows. |
| **Batch Script**<br>[BatchScript@1](batch-script-v1.md) | Run a windows cmd or bat script and optionally allow it to change the environment. |
| **Command Line**<br>[CmdLine@2](cmd-line-v2.md)<br>[CmdLine@1](cmd-line-v1.md) | Run a command line script using Bash on Linux and macOS and cmd.exe on Windows. |
| **Copy and Publish Build Artifacts**<br>[CopyPublishBuildArtifacts@1](copy-publish-build-artifacts-v1.md) | CopyPublishBuildArtifacts@1 is deprecated. Use the Copy Files task and the Publish Build Artifacts task instead. |
| **Copy Files**<br>[CopyFiles@2](copy-files-v2.md)<br>[CopyFiles@1](copy-files-v1.md) | Copy files from source folder to target folder using match patterns (The match patterns will only match file paths, not folder paths). |
| **cURL Upload Files**<br>[cURLUploader@2](curl-uploader-v2.md)<br>[cURLUploader@1](curl-uploader-v1.md) | Use cURL to upload files. |
| **Decrypt File (OpenSSL)**<br>[DecryptFile@1](decrypt-file-v1.md) | A thin utility task for file decryption using OpenSSL. |
| **Delay**<br>[Delay@1](delay-v1.md) | Delay further execution of the workflow by a fixed time. |
| **Delete Files**<br>[DeleteFiles@1](delete-files-v1.md) | Delete files or folders. (The minimatch patterns will only match file paths, not folder paths). |
| **Download Build Artifacts**<br>[DownloadBuildArtifacts@0](download-build-artifacts-v0.md) | Download Build Artifacts. |
| **Download Fileshare Artifacts**<br>[DownloadFileshareArtifacts@1](download-fileshare-artifacts-v1.md) | Download artifacts from a file share e.g \\share\drop. |
| **Download Package**<br>[DownloadPackage@0](download-package-v0.md) | Download a package from a Package Management feed in Azure Artifacts or TFS. 
 Requires the Package Management extension. |
| **Download Pipeline Artifacts**<br>[DownloadPipelineArtifact@0](download-pipeline-artifact-v0.md) | Download Pipeline Artifact. |
| **Download Secure File**<br>[DownloadSecureFile@1](download-secure-file-v1.md) | Download a secure file to a temporary location on the build or release agent. |
| **Extract Files**<br>[ExtractFiles@1](extract-files-v1.md) | Extract a variety of archive and compression files such as .7z, .rar, .tar.gz, and .zip. |
| **FTP Upload**<br>[FtpUpload@1](ftp-upload-v1.md) | FTP Upload. |
| **Install Apple Certificate**<br>[InstallAppleCertificate@2](install-apple-certificate-v2.md)<br>[InstallAppleCertificate@1](install-apple-certificate-v1.md)<br>[InstallAppleCertificate@0](install-apple-certificate-v0.md) | Install an Apple certificate required to build on a macOS agent. |
| **Install Apple Provisioning Profile**<br>[InstallAppleProvisioningProfile@1](install-apple-provisioning-profile-v1.md)<br>[InstallAppleProvisioningProfile@0](install-apple-provisioning-profile-v0.md) | Install an Apple provisioning profile required to build on a macOS agent. |
| **Install SSH Key**<br>[InstallSSHKey@0](install-ssh-key-v0.md) | Install an SSH key prior to a build or release. |
| **Invoke Azure Function**<br>[AzureFunction@1](azure-function-v1.md)<br>[AzureFunction@0](azure-function-v0.md) | Invoke an Azure Function as a part of your pipeline. |
| **Jenkins Download Artifacts**<br>[JenkinsDownloadArtifacts@1](jenkins-download-artifacts-v1.md) | Download artifacts produced by a Jenkins job. |
| **PowerShell**<br>[PowerShell@2](powershell-v2.md)<br>[PowerShell@1](powershell-v1.md) | Run a PowerShell script on Windows, macOS, or Linux. |
| **Publish Build Artifacts**<br>[PublishBuildArtifacts@1](publish-build-artifacts-v1.md) | Publish build artifacts to Azure Pipelines/TFS or a file share. |
| **Publish Pipeline Artifacts**<br>[PublishPipelineArtifact@0](publish-pipeline-artifact-v0.md) | Publish Pipeline Artifact. |
| **Publish To Azure Service Bus**<br>[PublishToAzureServiceBus@1](publish-to-azure-service-bus-v1.md)<br>[PublishToAzureServiceBus@0](publish-to-azure-service-bus-v0.md) | Sends a message to azure service bus using a service connection (no agent required). |
| **Python Script**<br>[PythonScript@0](python-script-v0.md) | Run a Python script. |
| **Query Azure Monitor Alerts**<br>[AzureMonitor@0](azure-monitor-v0.md) | Observe the configured Azure monitor rules for active alerts. |
| **Query Work Items**<br>[queryWorkItems@0](query-work-items-v0.md) | Executes a work item query and checks for the number of items returned. |
| **Service Fabric PowerShell**<br>[ServiceFabricPowerShell@1](service-fabric-powershell-v1.md) | Run a PowerShell script within the context of an Azure Service Fabric cluster connection. |
| **Shell Script**<br>[ShellScript@2](shell-script-v2.md) | Run a shell script using bash. |
| **Update Service Fabric App Versions**<br>[ServiceFabricUpdateAppVersions@1](service-fabric-update-app-versions-v1.md) | Automatically updates the versions of a packaged Service Fabric application. |
| **Update Service Fabric Manifests**<br>[ServiceFabricUpdateManifests@2](service-fabric-update-manifests-v2.md) | Automatically updates portions of the application and service manifests within a packaged Service Fabric application. |
| **Xamarin License**<br>[XamarinLicense@1](xamarin-license-v1.md) | [Deprecated] Upgrade to free version of Xamarin: https://store.xamarin.com. |

:::moniker-end

:::moniker range="=azure-pipelines-2018"

## Build tasks

| Task | Description |
|---|---|
| **.NET Core**<br>[DotNetCoreCLI@2](dotnet-core-cli-v2.md)<br>[DotNetCoreCLI@1](dotnet-core-cli-v1.md)<br>[DotNetCoreCLI@0](dotnet-core-cli-v0.md) | Build, test, package, or publish a dotnet application, or run a custom dotnet command. For package commands, supports NuGet.org and authenticated feeds like Package Management and MyGet. |
| **Android Build**<br>[AndroidBuild@1](android-build-v1.md) | AndroidBuild@1 is deprecated. Use Gradle. |
| **Android Signing**<br>[AndroidSigning@2](android-signing-v2.md)<br>[AndroidSigning@1](android-signing-v1.md) | Sign and align Android APK files. |
| **Ant**<br>[Ant@1](ant-v1.md) | Build with Apache Ant. |
| **CMake**<br>[CMake@1](cmake-v1.md) | Build with the CMake cross-platform build system. |
| **Docker**<br>[Docker@0](docker-v0.md) | Build, tag, push, or run Docker images, or run a Docker command. Task can be used with Docker or Azure Container registry. |
| **Docker Compose**<br>[DockerCompose@0](docker-compose-v0.md) | Build, push or run multi-container Docker applications. Task can be used with Docker or Azure Container registry. |
| **Gradle**<br>[Gradle@2](gradle-v2.md)<br>[Gradle@1](gradle-v1.md) | Build using a Gradle wrapper script. |
| **Grunt**<br>[Grunt@0](grunt-v0.md) | The JavaScript Task Runner. |
| **Gulp**<br>[Gulp@0](gulp-v0.md) | Node.js streaming task based build system. |
| **Index sources and publish symbols**<br>[PublishSymbols@2](publish-symbols-v2.md)<br>[PublishSymbols@1](publish-symbols-v1.md) | Index your source code and publish symbols to a file share or Visual Studio Team Services Symbol Server. |
| **Jenkins Queue Job**<br>[JenkinsQueueJob@2](jenkins-queue-job-v2.md)<br>[JenkinsQueueJob@1](jenkins-queue-job-v1.md) | Queue a job on a Jenkins server. |
| **Maven**<br>[Maven@2](maven-v2.md)<br>[Maven@1](maven-v1.md) | Build with Apache Maven. |
| **MSBuild**<br>[MSBuild@1](msbuild-v1.md) | Build with MSBuild. |
| **Visual Studio Build**<br>[VSBuild@1](vsbuild-v1.md) | Build with MSBuild and set the Visual Studio version property. |
| **Xamarin.Android**<br>[XamarinAndroid@1](xamarin-android-v1.md) | Build an Android app with Xamarin. |
| **Xamarin.iOS**<br>[XamariniOS@1](xamarin-ios-v1.md) | Build an iOS app with Xamarin on macOS. |
| **Xcode**<br>[Xcode@4](xcode-v4.md) | Build, test, or archive an Xcode workspace on macOS. Optionally package an app. |
| **Xcode Build**<br>[Xcode@3](xcode-v3.md)<br>[Xcode@2](xcode-v2.md) | Build an Xcode workspace on macOS. |
| **Xcode Package iOS**<br>[XcodePackageiOS@0](xcode-package-ios-v0.md) | Generate an .ipa file from Xcode build output using xcrun (Xcode 7 or below). |
## Deploy tasks

| Task | Description |
|---|---|
| **App Center distribute**<br>[AppCenterDistribute@0](app-center-distribute-v0.md) | Distribute app builds to testers and users via App Center. |
| **Azure App Service Classic (Deprecated)**<br>[AzureWebPowerShellDeployment@1](azure-web-powershell-deployment-v1.md) | Create or update Azure App Service using Azure PowerShell. |
| **Azure App Service deploy**<br>[AzureRmWebAppDeployment@2](azure-rm-web-app-deployment-v2.md) | Update Azure App Service using Web Deploy / Kudu REST APIs. |
| **Azure App Service Deploy**<br>[AzureRmWebAppDeployment@3](azure-rm-web-app-deployment-v3.md) | Update Azure WebApp Services On Windows, Web App On Linux with built-in images or docker containers, ASP.NET, .NET Core, PHP, Python or Node based Web applications, Function Apps, Mobile Apps, Api applications, Web Jobs using Web Deploy / Kudu REST APIs. |
| **Azure App Service Manage**<br>[AzureAppServiceManage@0](azure-app-service-manage-v0.md) | Start, Stop, Restart, Slot swap, Install site extensions or Enable Continuous Monitoring for an Azure App Service. |
| **Azure CLI**<br>[AzureCLI@1](azure-cli-v1.md) | Run a Shell or Batch script with Azure CLI commands against an azure subscription. |
| **Azure CLI Preview**<br>[AzureCLI@0](azure-cli-v0.md) | Run a Shell or Batch script with Azure CLI commands against an azure subscription. |
| **Azure Cloud Service Deployment**<br>[AzureCloudPowerShellDeployment@1](azure-cloud-powershell-deployment-v1.md) | Deploy an Azure Cloud Service. |
| **Azure File Copy**<br>[AzureFileCopy@1](azure-file-copy-v1.md) | Copy files to Azure blob or VM(s). |
| **Azure Key Vault**<br>[AzureKeyVault@1](azure-key-vault-v1.md) | Download Azure Key Vault Secrets. |
| **Azure Monitor Alerts**<br>[AzureMonitorAlerts@0](azure-monitor-alerts-v0.md) | Configure alerts on available metrics for an Azure resource. |
| **Azure PowerShell**<br>[AzurePowerShell@2](azure-powershell-v2.md)<br>[AzurePowerShell@1](azure-powershell-v1.md) | Run a PowerShell script within an Azure environment. |
| **Azure Resource Group Deployment**<br>[AzureResourceGroupDeployment@2](azure-resource-group-deployment-v2.md)<br>[AzureResourceGroupDeployment@1](azure-resource-group-deployment-v1.md) | Deploy, start, stop, delete Azure Resource Groups. |
| **Azure SQL Database Deployment**<br>[SqlAzureDacpacDeployment@1](sql-azure-dacpac-deployment-v1.md) | Deploy Azure SQL DB using DACPAC or run scripts using SQLCMD. |
| **Azure VM scale set Deployment**<br>[AzureVmssDeployment@0](azure-vmss-deployment-v0.md) | Deploy Virtual Machine scale set image. |
| **Build Machine Image**<br>[PackerBuild@0](packer-build-v0.md) | Build machine image using Packer. This image can be used for Azure Virtual machine scale set deployment. |
| **Chef**<br>[Chef@1](chef-v1.md) | Deploy to Chef environments by editing environment attributes. |
| **Chef Knife**<br>[ChefKnife@1](chef-knife-v1.md) | Run Scripts with knife commands on your chef workstation. |
| **Copy Files Over SSH**<br>[CopyFilesOverSSH@0](copy-files-over-ssh-v0.md) | Copy files or build artifacts to a remote machine over SSH. |
| **Deploy to Kubernetes**<br>[Kubernetes@0](kubernetes-v0.md) | Deploy, configure, update your Kubernetes cluster in Azure Container Service by running kubectl commands. |
| **IIS Web App Deploy**<br>[IISWebAppDeploymentOnMachineGroup@0](iisweb-app-deployment-on-machine-group-v0.md) | Deploy a Website or Web Application using WebDeploy. |
| **IIS Web App deployment (Deprecated)**<br>[IISWebAppDeployment@1](iisweb-app-deployment-v1.md) | Deploy by MSDeploy, create/update website & app pools. |
| **IIS Web App Manage**<br>[IISWebAppManagementOnMachineGroup@0](iisweb-app-management-on-machine-group-v0.md) | Create or update a Website, Web App, Virtual Directories, and Application Pool. |
| **Invoke REST API**<br>[InvokeRESTAPI@1](invoke-rest-api-v1.md)<br>[InvokeRESTAPI@0](invoke-rest-api-v0.md) | Invoke REST API as a part of your process. |
| **Manual Intervention**<br>[ManualIntervention@8](manual-intervention-v8.md) | Pause deployment and wait for intervention. |
| **PowerShell on Target Machines**<br>[PowerShellOnTargetMachines@2](powershell-on-target-machines-v2.md)<br>[PowerShellOnTargetMachines@1](powershell-on-target-machines-v1.md) | Execute PowerShell scripts on remote machine(s). |
| **Service Fabric Application Deployment**<br>[ServiceFabricDeploy@1](service-fabric-deploy-v1.md) | Deploy a Service Fabric application to a cluster. |
| **Service Fabric Compose Deploy**<br>[ServiceFabricComposeDeploy@0](service-fabric-compose-deploy-v0.md) | Deploy a docker-compose application to a Service Fabric cluster. |
| **SQL Server Database Deploy**<br>[SqlDacpacDeploymentOnMachineGroup@0](sql-dacpac-deployment-on-machine-group-v0.md) | Deploy to SQL Server Database using DACPAC or SQL scripts. |
| **SQL Server database deploy (Deprecated)**<br>[SqlServerDacpacDeployment@1](sql-server-dacpac-deployment-v1.md) | Deploy SQL Server Database using DACPAC. |
| **SSH**<br>[SSH@0](ssh-v0.md) | Run shell commands or a script on a remote machine using SSH. |
| **Windows Machine File Copy**<br>[WindowsMachineFileCopy@2](windows-machine-file-copy-v2.md)<br>[WindowsMachineFileCopy@1](windows-machine-file-copy-v1.md) | Copy files to remote machine(s). |
## Package tasks

| Task | Description |
|---|---|
| **CocoaPods**<br>[CocoaPods@0](cocoa-pods-v0.md) | CocoaPods is a dependency manager for Swift and Objective-C Cocoa projects. This task runs 'pod install'. |
| **npm**<br>[Npm@1](npm-v1.md)<br>[Npm@0](npm-v0.md) | Install and publish npm packages, or run an npm command. Supports npmjs.com and authenticated registries like Package Management. |
| **npm Authenticate (for task runners)**<br>[npmAuthenticate@0](npm-authenticate-v0.md) | Don't use this task if you're also using the npm task. Provides npm credentials to an .npmrc file in your repository for the scope of the build. This enables npm task runners like Gulp and Grunt to authenticate with private registries. |
| **NuGet**<br>[NuGetCommand@2](nuget-command-v2.md) | Restore, pack, or push NuGet packages, or run a NuGet command. Supports NuGet.org and authenticated feeds like Package Management and MyGet. Uses NuGet.exe and works with .NET Framework apps. For .NET Core and .NET Standard apps, use the .NET Core task. |
| **NuGet Command**<br>[NuGet@0](nuget-v0.md) | Deprecated: use the “NuGet” task instead. It works with the new Tool Installer framework so you can easily use new versions of NuGet without waiting for a task update, provides better support for authenticated feeds outside this account/collection, and uses NuGet 4 by default. |
| **NuGet Installer**<br>[NuGetInstaller@0](nuget-installer-v0.md) | Installs or restores missing NuGet packages. |
| **NuGet Packager**<br>[NuGetPackager@0](nuget-packager-v0.md) | Deprecated: use the “NuGet” task instead. It works with the new Tool Installer framework so you can easily use new versions of NuGet without waiting for a task update, provides better support for authenticated feeds outside this account/collection, and uses NuGet 4 by default. |
| **NuGet Publisher**<br>[NuGetPublisher@0](nuget-publisher-v0.md) | Deprecated: use the “NuGet” task instead. It works with the new Tool Installer framework so you can easily use new versions of NuGet without waiting for a task update, provides better support for authenticated feeds outside this account/collection, and uses NuGet 4 by default. |
| **NuGet Restore**<br>[NuGetRestore@1](nuget-restore-v1.md) | Restores NuGet packages in preparation for a Visual Studio Build step. |
| **Xamarin Component Restore**<br>[XamarinComponentRestore@0](xamarin-component-restore-v0.md) | Restores Xamarin components for the specified solution. |
## Test tasks

| Task | Description |
|---|---|
| **App Center Test**<br>[AppCenterTest@1](app-center-test-v1.md) | Test app packages with Visual Studio App Center. |
| **Mobile Center Test**<br>[VSMobileCenterTest@0](vsmobile-center-test-v0.md) | Test mobile app packages with Visual Studio Mobile Center. |
| **Publish Code Coverage Results**<br>[PublishCodeCoverageResults@1](publish-code-coverage-results-v1.md) | Publish Cobertura or JaCoCo code coverage results from a build. |
| **Publish Test Results**<br>[PublishTestResults@2](publish-test-results-v2.md)<br>[PublishTestResults@1](publish-test-results-v1.md) | Publish Test Results to VSTS/TFS. |
| **Run Functional Tests**<br>[RunVisualStudioTestsusingTestAgent@1](run-visual-studio-testsusing-test-agent-v1.md) | Deprecated: This task and it’s companion task (Visual Studio Test Agent Deployment) are deprecated. Use the 'Visual Studio Test' task instead. The VSTest task can run unit as well as functional tests. Run tests on one or more agents using the multi-agent phase setting. Use the 'Visual Studio Test Platform' task to run tests without needing Visual Studio on the agent. VSTest task also brings new capabilities such as automatically rerunning failed tests. |
| **Visual Studio Test**<br>[VSTest@2](vstest-v2.md)<br>[VSTest@1](vstest-v1.md) | Run unit and functional tests (Selenium, Appium, Coded UI test, etc.) using the Visual Studio Test runner. Test frameworks that have a Visual Studio test adapter such as xUnit, NUnit, Chutzpah, etc. can also be run. Tests can be distributed on multiple agents using this task (version 2). |
| **Visual Studio Test Agent Deployment**<br>[DeployVisualStudioTestAgent@2](deploy-visual-studio-test-agent-v2.md)<br>[DeployVisualStudioTestAgent@1](deploy-visual-studio-test-agent-v1.md) | DeployVisualStudioTestAgent@2 is deprecated. Use the Visual Studio Test task to run unit and functional tests. |
| **Xamarin Test Cloud**<br>[XamarinTestCloud@1](xamarin-test-cloud-v1.md) | [Depreciated] Testing mobile apps with Xamarin Test Cloud using Xamarin.UITest - recommended task is now AppCenterTest. |
## Tool tasks

| Task | Description |
|---|---|
| **.NET Core SDK/runtime installer**<br>[DotNetCoreInstaller@0](dotnet-core-installer-v0.md) | Acquire a specific version of the .NET Core SDK from the internet or local cache and add it to the PATH. |
| **Java Tool Installer**<br>[JavaToolInstaller@0](java-tool-installer-v0.md) | Acquires a specific version of Java from a user supplied Azure blob or the tools cache and sets JAVA_HOME. Use this task to change the version of Java used in Java tasks. |
| **Node Tool Installer**<br>[NodeTool@0](node-tool-v0.md) | Finds or Downloads and caches specified version spec of Node and adds it to the PATH. |
| **NuGet Tool Installer**<br>[NuGetToolInstaller@0](nuget-tool-installer-v0.md) | Acquires a specific version of NuGet from the internet or the tools cache and adds it to the PATH. Use this step to change the version of NuGet used in the NuGet steps. |
| **Visual Studio Test Platform Installer**<br>[VisualStudioTestPlatformInstaller@1](visual-studio-test-platform-installer-v1.md) | Acquires the test platform from nuget.org or the tools cache. Satisfies the ‘vstest’ demand and can be used for running tests and collecting diagnostic data using the Visual Studio Test task. |
## Utility tasks

| Task | Description |
|---|---|
| **Archive Files**<br>[ArchiveFiles@2](archive-files-v2.md)<br>[ArchiveFiles@1](archive-files-v1.md) | Archive files using compression formats such as .7z, .rar, .tar.gz, and .zip. |
| **Azure Network Load Balancer**<br>[AzureNLBManagement@1](azure-nlb-management-v1.md) | Connect/Disconnect an Azure virtual machine's network interface to a Load Balancer's backend address pool. |
| **Bash**<br>[Bash@3](bash-v3.md) | This is an early preview. Run a Bash script on macOS, Linux, or Windows. |
| **Batch Script**<br>[BatchScript@1](batch-script-v1.md) | Run a windows cmd or bat script and optionally allow it to change the environment. |
| **Command Line**<br>[CmdLine@2](cmd-line-v2.md)<br>[CmdLine@1](cmd-line-v1.md) | Run a command line script using Bash on Linux and macOS and cmd.exe on Windows. |
| **Copy and Publish Build Artifacts**<br>[CopyPublishBuildArtifacts@1](copy-publish-build-artifacts-v1.md) | CopyPublishBuildArtifacts@1 is deprecated. Use the Copy Files task and the Publish Build Artifacts task instead. |
| **Copy Files**<br>[CopyFiles@2](copy-files-v2.md)<br>[CopyFiles@1](copy-files-v1.md) | Copy files from source folder to target folder using match patterns (The match patterns will only match file paths, not folder paths). |
| **cURL Upload Files**<br>[cURLUploader@2](curl-uploader-v2.md)<br>[cURLUploader@1](curl-uploader-v1.md) | Use cURL to upload files with FTP, FTPS, SFTP, HTTP, and more. |
| **Decrypt File (OpenSSL)**<br>[DecryptFile@1](decrypt-file-v1.md) | A thin utility task for file decryption using OpenSSL. |
| **Delay**<br>[Delay@1](delay-v1.md) | Delay further execution of the workflow by a fixed time. |
| **Delete Files**<br>[DeleteFiles@1](delete-files-v1.md) | Delete files or folders. (The minimatch patterns will only match file paths, not folder paths). |
| **Download Build Artifacts**<br>[DownloadBuildArtifacts@0](download-build-artifacts-v0.md) | Download Build Artifacts. |
| **Download Package**<br>[DownloadPackage@0](download-package-v0.md) | Download a package from a Package Management feed in VSTS or TFS. 
 Requires the Package Management extension. |
| **Download Secure File**<br>[DownloadSecureFile@1](download-secure-file-v1.md) | Download a secure file to a temporary location on the build or release agent. |
| **Extract Files**<br>[ExtractFiles@1](extract-files-v1.md) | Extract a variety of archive and compression files such as .7z, .rar, .tar.gz, and .zip. |
| **FTP Upload**<br>[FtpUpload@1](ftp-upload-v1.md) | FTP Upload. |
| **Install Apple Certificate**<br>[InstallAppleCertificate@1](install-apple-certificate-v1.md)<br>[InstallAppleCertificate@0](install-apple-certificate-v0.md) | Install an Apple certificate required to build on a macOS agent. |
| **Install Apple Provisioning Profile**<br>[InstallAppleProvisioningProfile@1](install-apple-provisioning-profile-v1.md)<br>[InstallAppleProvisioningProfile@0](install-apple-provisioning-profile-v0.md) | Install an Apple provisioning profile required to build on a macOS agent. |
| **Install SSH Key**<br>[InstallSSHKey@0](install-ssh-key-v0.md) | Install an SSH key prior to a build or release. |
| **Invoke Azure Function**<br>[AzureFunction@1](azure-function-v1.md)<br>[AzureFunction@0](azure-function-v0.md) | Invoke Azure function as a part of your process. |
| **Jenkins Download Artifacts**<br>[JenkinsDownloadArtifacts@1](jenkins-download-artifacts-v1.md) | Download artifacts produced by a Jenkins job. |
| **PowerShell**<br>[PowerShell@2](powershell-v2.md)<br>[PowerShell@1](powershell-v1.md) | This is an early preview. Run a PowerShell script on Windows, macOS, or Linux. |
| **Publish Build Artifacts**<br>[PublishBuildArtifacts@1](publish-build-artifacts-v1.md) | Publish build artifacts to Visual Studio Team Services/TFS or a file share. |
| **Publish To Azure Service Bus**<br>[PublishToAzureServiceBus@1](publish-to-azure-service-bus-v1.md)<br>[PublishToAzureServiceBus@0](publish-to-azure-service-bus-v0.md) | Sends a message to azure service bus using a service connection (no agent required). |
| **PyPI Publisher**<br>[PyPIPublisher@0](py-pi-publisher-v0.md) | Publish Python packages to PyPI. |
| **Query Azure Monitor Alerts**<br>[AzureMonitor@0](azure-monitor-v0.md) | Observe the configured Azure monitor rules for active alerts. |
| **Query Work Items**<br>[queryWorkItems@0](query-work-items-v0.md) | Executes a work item query and checks for the number of items returned. |
| **Service Fabric PowerShell**<br>[ServiceFabricPowerShell@1](service-fabric-powershell-v1.md) | Run a PowerShell script within the context of an Azure Service Fabric cluster connection. |
| **Shell Script**<br>[ShellScript@2](shell-script-v2.md) | Run a shell script using bash. |
| **Update Service Fabric App Versions**<br>[ServiceFabricUpdateAppVersions@1](service-fabric-update-app-versions-v1.md) | Automatically updates the versions of a packaged Service Fabric application. |
| **Update Service Fabric Manifests**<br>[ServiceFabricUpdateManifests@2](service-fabric-update-manifests-v2.md) | Automatically updates portions of the application and service manifests within a packaged Service Fabric application. |
| **Xamarin License**<br>[XamarinLicense@1](xamarin-license-v1.md) | [Deprecated] Upgrade to free version of Xamarin: https://store.xamarin.com. |

:::moniker-end
<!-- :::taskIndex-end::: -->

## Open source

These tasks are open source [on GitHub](https://github.com/Microsoft/azure-pipelines-tasks). Feedback and contributions are welcome. See [Pipeline task changelog](https://github.com/microsoft/azure-pipelines-tasks/releases) for a list of task changes, including a historical record of task updates.

## FAQ

### What are task input aliases?

Inputs to a task are identified by a `label`, `name`, and may include one or more optional `aliases`. The following example is an excerpt from the [source code](https://github.com/microsoft/azure-pipelines-tasks/blob/5cf07afe033fe76df9d011b1e71ee2b7057f3969/Tasks/InstallSSHKeyV0/task.json#L35) for the **Known Hosts Entry** input of the [InstallSSHKey@0](./install-ssh-key-v0.md) task.

```json
{
    "name": "hostName",
    "aliases": [
        "knownHostsEntry"
    ],
    "label": "Known Hosts Entry"
    ...
}
```

Before YAML pipelines were introduced in 2019, pipelines were created and edited using a UI based pipeline editor, and only the `label` was used by pipeline authors to reference a task input.

:::image type="content" source="./media/task-assistant.png" alt-text="Screenshot of the task assistant in the YAML pipeline editor.":::

When YAML pipelines were introduced in 2019, pipeline authors using YAML started using the task input `name` to refer to a task input. In some cases, the task input names weren't descriptive, so `aliases` were added to provide additional descriptive names for task inputs.

For example, the `InstallSSHKey@0` task has a **Known Hosts Entry** input named `hostName` that expects an entry from a **known_hosts** file. The **Known Hosts Entry** label in the classic pipeline designer makes this clear, but it isn't as clear when using the `hostName` name in a YAML pipeline. Task input aliases were introduced to allow task authors to provide decriptive names for their previously authored tasks, and for the `InstallSSHKey@0` task, a `knownHostsEntry` [alias was added](https://github.com/microsoft/azure-pipelines-tasks/pull/9973/), while keeping the original `hostName` name for compatibility with existing pipelines using that name.

Any items in a task input's `aliases` are interchangeable with the `name` in a YAML pipeline. The following two YAML snippets are functionally identical, with the first example using the `knownHostsEntry` alias and the second example using `hostName`.

```yml
- task: InstallSSHKey@0
  inputs:
    # Using knownHostsEntry alias
    knownHostsEntry: 'sample known hosts entry line'
    # Remainder of task inputs omitted

- task: InstallSSHKey@0
  inputs:
    # Using hostName name
    hostName: 'sample known hosts entry line'
    # Remainder of task inputs omitted
```

Starting with Azure DevOps Server 2019.1, the [YAML pipeline editor was introduced](/azure/devops/pipelines/get-started/yaml-pipeline-editor), which provides an intellisense type functionality. 

The YAML pipeline editor uses the [Yamlschema - Get](/rest/api/azure/devops/distributedtask/yamlschema/get) REST API to retrieve the schema used for validation in the editor. If a task input has an alias, the schema promotes the alias to the primary YAML name for the task input, and the alias is suggested by the intellisense.

:::image type="content" source="./media/yaml-editor-intellisense.png" alt-text="Screenshot of intellisense in the YAML pipeline editor.":::

The following example is the **Known Hosts Entry** task input for the `InstallSSHKey@0` task from the YAML schema, with `knownHostsEntry` listed in the name position and `hostName` in the `aliases` collection.

```json
"properties": {
  "knownHostsEntry": {
    "type": "string",
    "description": "Known Hosts Entry",
    "ignoreCase": "key",
    "aliases": [
      "hostName"
    ]
  },
```

Because the intellisense in the YAML pipeline editor displays `knownHostsEntry`, and the YAML generated by the task assistant uses `knownHostsEntry` in the generated YAML, the task reference displays the `alias` from the task source code as the YAML name for a task input. If a task has more than one alias (there are a few that have two aliases), the first alias is used as the name.

### Why did the task reference change?

The Azure Pipelines tasks reference documentation moved to its current location to support the following improvements.

 * Task articles are generated using the task source code from the [Azure Pipelines tasks open source repository](https://github.com/microsoft/azure-pipelines-tasks).
 * Task input names and aliases are generated from the task source so they are always up to date.
 * YAML syntax blocks are generated from the task source so they are up to date.
 * Supports community contributions with integrated user content such as enhanced task input descriptions, remarks and examples.
 * Provides task coverage for all supported Azure DevOps versions.
 * Updated every sprint to cover the latest updates.

To contribute, see [Contributing to the tasks content](https://github.com/MicrosoftDocs/azure-devops-yaml-schema#contributing-to-the-tasks-content).

### Where can I learn step-by-step how to build my app?

[Build your app](/previous-versions/azure/devops/pipelines/apps/)

### Can I add my own build tasks?

Yes: [Add a build task](/azure/devops/extend/develop/add-build-task)

### What are installer tasks?

To learn more about tool installer tasks, see [Tool installers](/azure/devops/pipelines/process/tasks#tool-installers).
