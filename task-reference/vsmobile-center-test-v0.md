---
title: VSMobileCenterTest@0 - Mobile Center Test v0 task
description: Test mobile app packages with Visual Studio Mobile Center.
ms.date: 09/01/2022
monikerRange: "<=azure-pipelines"
---

# VSMobileCenterTest@0 - Mobile Center Test v0 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Test mobile app packages with Visual Studio Mobile Center.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019"

```yaml
# Mobile Center Test v0
# Test mobile app packages with Visual Studio Mobile Center.
- task: VSMobileCenterTest@0
  inputs:
    app: # string. Required. Binary Application File Path. 
    artifactsDir: '$(Build.ArtifactStagingDirectory)/MobileCenterTest' # string. Required. Artifacts Directory. Default: '$(Build.ArtifactStagingDirectory)/MobileCenterTest'.
  # Prepare Tests
    #enablePrepare: true # boolean. Prepare Tests. Default: true.
    framework: 'appium' # 'appium' | 'espresso' | 'calabash' | 'uitest' | 'xcuitest'. Required when enablePrepare = true. Test Framework. Default: 'appium'.
    #appiumBuildDir: # string. Required when enablePrepare = true && framework = appium. Build Directory. 
    #espressoBuildDir: # string. Optional. Use when enablePrepare = true && framework = espresso. Build Directory. 
    #espressoTestApkPath: # string. Optional. Use when enablePrepare = true && framework = espresso. Test APK Path. 
    #calabashProjectDir: # string. Required when enablePrepare = true && framework = calabash. Project Directory. 
    #calabashConfigFile: # string. Optional. Use when enablePrepare = true && framework = calabash. Cucumber Config File. 
    #calabashProfile: # string. Optional. Use when enablePrepare = true && framework = calabash. Profile to run. 
    #calabashSkipConfigCheck: false # boolean. Optional. Use when enablePrepare = true && framework = calabash. Skip Configuration Check. Default: false.
    #uitestBuildDir: # string. Required when enablePrepare = true && framework = uitest. Build Directory. 
    #uitestStoreFile: # string. Optional. Use when enablePrepare = true && framework = uitest. Store File. 
    #uitestStorePass: # string. Optional. Use when enablePrepare = true && framework = uitest. Store Password. 
    #uitestKeyAlias: # string. Optional. Use when enablePrepare = true && framework = uitest. Key Alias. 
    #uitestKeyPass: # string. Optional. Use when enablePrepare = true && framework = uitest. Key Password. 
    #uitestToolsDir: # string. Optional. Use when enablePrepare = true && framework = uitest. Test Tools Directory. 
    #signInfo: # string. Optional. Use when framework = calabash || framework = uitest. Signing Information. 
    #xcuitestBuildDir: # string. Optional. Use when enablePrepare = true && framework = xcuitest. Build Directory. 
    #xcuitestTestIpaPath: # string. Optional. Use when enablePrepare = true && framework = xcuitest. Test IPA Path. 
    #prepareOpts: # string. Optional. Use when enablePrepare = true. Additional Options. 
  # Run Tests
    #enableRun: true # boolean. Run Tests. Default: true.
    credsType: 'serviceEndpoint' # 'serviceEndpoint' | 'inputs'. Required when enableRun = true. Authentication Method. Default: 'serviceEndpoint'.
    #serverEndpoint: # string. Required when enableRun = true && credsType = serviceEndpoint. Mobile Center Connection. 
    #username: # string. Required when enableRun = true && credsType = inputs. Mobile Center Username. 
    #password: # string. Required when enableRun = true && credsType = inputs. Mobile Center Password. 
    appSlug: # string. Required when enableRun = true. App Slug. 
    devices: # string. Required when enableRun = true. Devices. 
    #series: 'master' # string. Optional. Use when enableRun = true. Test Series. Default: 'master'.
    #dsymDir: # string. Optional. Use when enableRun = true. dSYM Directory. 
    locale: 'en_US' # 'da_DK' | 'nl_NL' | 'en_GB' | 'en_US' | 'fr_FR' | 'de_DE' | 'ja_JP' | 'ru_RU' | 'es_MX' | 'es_ES' | 'user'. Required when enableRun = true. System Language. Default: 'en_US'.
    #userDefinedLocale: # string. Optional. Use when enableRun = true && locale = user. Other Locale. 
    #loginOpts: # string. Optional. Use when enableRun = true && credsType = inputs. Addtional Options for Login. 
    #runOpts: # string. Optional. Use when enableRun = true. Additional Options for Run. 
    #async: false # boolean. Optional. Use when enableRun = true. Do not wait for test result. Default: false.
  # Advanced
    #cliLocationOverride: # string. mobile-center CLI Location. 
    #debug: false # boolean. Enable Debug Output. Default: false.
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

<!-- :::item name="app"::: -->
:::moniker range="<=azure-pipelines"

**`app`** - **Binary Application File Path**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Relative path from the repo root to the APK or IPA file you want to test.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="artifactsDir"::: -->
:::moniker range="<=azure-pipelines"

**`artifactsDir`** - **Artifacts Directory**<br>
Type: string. Required. Default value: '$(Build.ArtifactStagingDirectory)/MobileCenterTest'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Where to place the artifacts produced by the prepare step and used by the run step. This directory will be created if it does not exist.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="enablePrepare"::: -->
:::moniker range="<=azure-pipelines"

**`enablePrepare`** - **Prepare Tests**<br>
Type: boolean. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="framework"::: -->
:::moniker range="<=azure-pipelines"

**`framework`** - **Test Framework**<br>
Type: string. Required when enablePrepare = true. Allowed values: 'appium', 'espresso', 'calabash', 'uitest', 'xcuitest'. Default value: 'appium'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="appiumBuildDir"::: -->
:::moniker range="<=azure-pipelines"

**`appiumBuildDir`** - **Build Directory**<br>
Type: string. Required when enablePrepare = true && framework = appium.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to directory with Appium tests.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="espressoBuildDir"::: -->
:::moniker range="<=azure-pipelines"

**`espressoBuildDir`** - **Build Directory**<br>
Type: string. Optional. Use when enablePrepare = true && framework = espresso.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to Espresso output directory.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="espressoTestApkPath"::: -->
:::moniker range="<=azure-pipelines"

**`espressoTestApkPath`** - **Test APK Path**<br>
Type: string. Optional. Use when enablePrepare = true && framework = espresso.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to APK file with Espresso tests. If not set, build-dir is used to discover it. Wildcard is allowed.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="calabashProjectDir"::: -->
:::moniker range="<=azure-pipelines"

**`calabashProjectDir`** - **Project Directory**<br>
Type: string. Required when enablePrepare = true && framework = calabash.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to Calabash workspace directory.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="calabashConfigFile"::: -->
:::moniker range="<=azure-pipelines"

**`calabashConfigFile`** - **Cucumber Config File**<br>
Type: string. Optional. Use when enablePrepare = true && framework = calabash.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to Cucumber configuration file, usually cucumber.yml.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="calabashProfile"::: -->
:::moniker range="<=azure-pipelines"

**`calabashProfile`** - **Profile to run**<br>
Type: string. Optional. Use when enablePrepare = true && framework = calabash.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Profile to run.  This value must exists in the Cucumber configuration file.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="calabashSkipConfigCheck"::: -->
:::moniker range="<=azure-pipelines"

**`calabashSkipConfigCheck`** - **Skip Configuration Check**<br>
Type: boolean. Optional. Use when enablePrepare = true && framework = calabash. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Force running without Cucumber profile.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="uitestBuildDir"::: -->
:::moniker range="<=azure-pipelines"

**`uitestBuildDir`** - **Build Directory**<br>
Type: string. Required when enablePrepare = true && framework = uitest.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to directory with built test assemblies.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="uitestStoreFile"::: -->
:::moniker range="<=azure-pipelines"

**`uitestStoreFile`** - **Store File**<br>
Type: string. Optional. Use when enablePrepare = true && framework = uitest.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="uitestStorePass"::: -->
:::moniker range="<=azure-pipelines"

**`uitestStorePass`** - **Store Password**<br>
Type: string. Optional. Use when enablePrepare = true && framework = uitest.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="uitestKeyAlias"::: -->
:::moniker range="<=azure-pipelines"

**`uitestKeyAlias`** - **Key Alias**<br>
Type: string. Optional. Use when enablePrepare = true && framework = uitest.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="uitestKeyPass"::: -->
:::moniker range="<=azure-pipelines"

**`uitestKeyPass`** - **Key Password**<br>
Type: string. Optional. Use when enablePrepare = true && framework = uitest.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="uitestToolsDir"::: -->
:::moniker range="<=azure-pipelines"

**`uitestToolsDir`** - **Test Tools Directory**<br>
Type: string. Optional. Use when enablePrepare = true && framework = uitest.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to directory with Xamarin UI test tools that contains test-cloud.exe.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="signInfo"::: -->
:::moniker range="<=azure-pipelines"

**`signInfo`** - **Signing Information**<br>
Type: string. Optional. Use when framework = calabash || framework = uitest.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Use Signing Infor for signing the test server.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="xcuitestBuildDir"::: -->
:::moniker range="<=azure-pipelines"

**`xcuitestBuildDir`** - **Build Directory**<br>
Type: string. Optional. Use when enablePrepare = true && framework = xcuitest.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to the build output directory (usually $(ProjectDir)/Build/Products/Debug-iphoneos).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="xcuitestTestIpaPath"::: -->
:::moniker range="<=azure-pipelines"

**`xcuitestTestIpaPath`** - **Test IPA Path**<br>
Type: string. Optional. Use when enablePrepare = true && framework = xcuitest.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to the *.ipa file with the XCUITest tests.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="prepareOpts"::: -->
:::moniker range="<=azure-pipelines"

**`prepareOpts`** - **Additional Options**<br>
Type: string. Optional. Use when enablePrepare = true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Additional arguments passed to mobile-center test prepare step.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="enableRun"::: -->
:::moniker range="<=azure-pipelines"

**`enableRun`** - **Run Tests**<br>
Type: boolean. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="credsType"::: -->
:::moniker range="<=azure-pipelines"

**`credsType`** - **Authentication Method**<br>
Type: string. Required when enableRun = true. Allowed values: 'serviceEndpoint', 'inputs'. Default value: 'serviceEndpoint'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Use Mobile Center service endpoint connection or enter credentials to connect to Visual Studio Mobile Center.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="serverEndpoint"::: -->
:::moniker range="<=azure-pipelines"

**`serverEndpoint`** - **Mobile Center Connection**<br>
Type: string. Required when enableRun = true && credsType = serviceEndpoint.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the service endpoint for your Visual Studio Mobile Center connection. To create one, click the Manage link and create a new service endpoint.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="username"::: -->
:::moniker range="<=azure-pipelines"

**`username`** - **Mobile Center Username**<br>
Type: string. Required when enableRun = true && credsType = inputs.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Visit https://mobile.azure.com/settings/profile to get your username.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="password"::: -->
:::moniker range="<=azure-pipelines"

**`password`** - **Mobile Center Password**<br>
Type: string. Required when enableRun = true && credsType = inputs.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Visit https://mobile.azure.com/settings/profile to set your password. It can accept variable defined in Build/Release definitions as '$(passwordVariable)'. You may mark variable type as 'secret' to secure it.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="appSlug"::: -->
:::moniker range="<=azure-pipelines"

**`appSlug`** - **App Slug**<br>
Type: string. Required when enableRun = true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The app slug is in the format of {username}/{app_identifier}.  To locate {username} and {app_identifier} for an app, click on its name from https://mobile.azure.com/apps, and the resulting url is in the format of https://mobile.azure.com/users/{username}/apps/{app_identifier}.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="devices"::: -->
:::moniker range="<=azure-pipelines"

**`devices`** - **Devices**<br>
Type: string. Required when enableRun = true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
String to identify what devices this test will run against.  Copy and paste this string when you define a new test run from Mobile Center Test beacon.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="series"::: -->
:::moniker range="<=azure-pipelines"

**`series`** - **Test Series**<br>
Type: string. Optional. Use when enableRun = true. Default value: 'master'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The series name for organizing test runs (e.g. master, production, beta).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="dsymDir"::: -->
:::moniker range="<=azure-pipelines"

**`dsymDir`** - **dSYM Directory**<br>
Type: string. Optional. Use when enableRun = true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to iOS symbol files.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="locale"::: -->
:::moniker range="<=azure-pipelines"

**`locale`** - **System Language**<br>
Type: string. Required when enableRun = true. Allowed values: 'da_DK', 'nl_NL', 'en_GB', 'en_US', 'fr_FR', 'de_DE', 'ja_JP', 'ru_RU', 'es_MX', 'es_ES', 'user'. Default value: 'en_US'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If your language isn't displayed, select 'Other' and enter its locale below, such as en_US.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="userDefinedLocale"::: -->
:::moniker range="<=azure-pipelines"

**`userDefinedLocale`** - **Other Locale**<br>
Type: string. Optional. Use when enableRun = true && locale = user.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter any two-letter ISO-639 language code along with any two-letter ISO 3166 country code in the format [language]_[country], such as en_US.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="loginOpts"::: -->
:::moniker range="<=azure-pipelines"

**`loginOpts`** - **Addtional Options for Login**<br>
Type: string. Optional. Use when enableRun = true && credsType = inputs.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Additional arguments passed to mobile-center login step.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="runOpts"::: -->
:::moniker range="<=azure-pipelines"

**`runOpts`** - **Additional Options for Run**<br>
Type: string. Optional. Use when enableRun = true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Additional arguments passed to mobile-center test run.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="async"::: -->
:::moniker range="<=azure-pipelines"

**`async`** - **Do not wait for test result**<br>
Type: boolean. Optional. Use when enableRun = true. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Execute command asynchronously, exit when tests are uploaded, without waiting for test results.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="cliLocationOverride"::: -->
:::moniker range="<=azure-pipelines"

**`cliLocationOverride`** - **mobile-center CLI Location**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="debug"::: -->
:::moniker range="<=azure-pipelines"

**`debug`** - **Enable Debug Output**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Add --debug to mobile-center cli.
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
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range=">=azure-pipelines-2019"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version | All supported agent versions. |
| Task category | Test |

:::moniker-end

:::moniker range="=azure-pipelines-2018"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build |
| Runs on | All |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version | All supported agent versions. |
| Task category | Test |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->