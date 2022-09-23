---
title: AppCenterTest@1 - App Center test v1 task
description: Test app packages with Visual Studio App Center.
ms.date: 09/01/2022
monikerRange: "<=azure-pipelines"
---

# AppCenterTest@1 - App Center test v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Test app packages with Visual Studio App Center.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# App Center test v1
# Test app packages with Visual Studio App Center.
- task: AppCenterTest@1
  inputs:
    appFile: # string. Required. Binary application file path. 
    artifactsDirectory: '$(Build.ArtifactStagingDirectory)/AppCenterTest' # string. Required. Artifacts directory. Default: '$(Build.ArtifactStagingDirectory)/AppCenterTest'.
  # Prepare Tests
    #prepareTests: true # boolean. Prepare tests. Default: true.
    frameworkOption: 'appium' # 'appium' | 'espresso' | 'calabash' | 'uitest' | 'xcuitest'. Required when enablePrepare = true. Test framework. Default: 'appium'.
    #appiumBuildDirectory: # string. Required when enablePrepare = true && framework = appium. Build directory. 
    #espressoBuildDirectory: # string. Optional. Use when enablePrepare = true && framework = espresso. Build directory. 
    #espressoTestApkFile: # string. Optional. Use when enablePrepare = true && framework = espresso. Test APK path. 
    #calabashProjectDirectory: # string. Required when enablePrepare = true && framework = calabash. Project directory. 
    #calabashConfigFile: # string. Optional. Use when enablePrepare = true && framework = calabash. Cucumber config file. 
    #calabashProfile: # string. Optional. Use when enablePrepare = true && framework = calabash. Profile to run. 
    #calabashSkipConfigCheck: false # boolean. Optional. Use when enablePrepare = true && framework = calabash. Skip Configuration Check. Default: false.
    #uiTestBuildDirectory: # string. Required when enablePrepare = true && framework = uitest. Build directory. 
    #uitestStorePath: # string. Optional. Use when enablePrepare = true && framework = uitest. Store file. 
    #uiTestStorePassword: # string. Optional. Use when enablePrepare = true && framework = uitest. Store password. 
    #uitestKeyAlias: # string. Optional. Use when enablePrepare = true && framework = uitest. Key alias. 
    #uiTestKeyPassword: # string. Optional. Use when enablePrepare = true && framework = uitest. Key password. 
    #uiTestToolsDirectory: # string. Optional. Use when enablePrepare = true && framework = uitest. Test tools directory. 
    #signInfo: # string. Optional. Use when framework = calabash || framework = uitest. Signing information. 
    #xcUITestBuildDirectory: # string. Optional. Use when enablePrepare = true && framework = xcuitest. Build directory. 
    #xcUITestIpaFile: # string. Optional. Use when enablePrepare = true && framework = xcuitest. Test IPA path. 
    #prepareOptions: # string. Optional. Use when enablePrepare = true. Additional options. 
  # Run Tests
    #runTests: true # boolean. Run tests. Default: true.
    credentialsOption: 'serviceEndpoint' # 'serviceEndpoint' | 'inputs'. Required when enableRun = true. Authentication method. Default: 'serviceEndpoint'.
    #serverEndpoint: # string. Required when enableRun = true && credsType = serviceEndpoint. App Center service connection. 
    #username: # string. Required when enableRun = true && credsType = inputs. App Center username. 
    #password: # string. Required when enableRun = true && credsType = inputs. App Center password. 
    appSlug: # string. Required when enableRun = true. App slug. 
    devices: # string. Required when enableRun = true. Devices. 
    #series: 'master' # string. Optional. Use when enableRun = true. Test series. Default: 'master'.
    #dsymDirectory: # string. Optional. Use when enableRun = true. dSYM directory. 
    localeOption: 'en_US' # 'da_DK' | 'nl_NL' | 'en_GB' | 'en_US' | 'fr_FR' | 'de_DE' | 'ja_JP' | 'ru_RU' | 'es_MX' | 'es_ES' | 'user'. Required when enableRun = true. System language. Default: 'en_US'.
    #userDefinedLocale: # string. Optional. Use when enableRun = true && locale = user. Other locale. 
    #loginOptions: # string. Optional. Use when enableRun = true && credsType = inputs. Additional options for login. 
    #runOptions: # string. Optional. Use when enableRun = true. Additional options for run. 
    #skipWaitingForResults: false # boolean. Optional. Use when enableRun = true. Do not wait for test result. Default: false.
  # Advanced
    #cliFile: # string. App Center CLI location. 
    #showDebugOutput: false # boolean. Enable debug output. Default: false.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# App Center Test v1
# Test app packages with Visual Studio App Center.
- task: AppCenterTest@1
  inputs:
    appFile: # string. Required. Binary application file path. 
    artifactsDirectory: '$(Build.ArtifactStagingDirectory)/AppCenterTest' # string. Required. Artifacts directory. Default: '$(Build.ArtifactStagingDirectory)/AppCenterTest'.
  # Prepare Tests
    #prepareTests: true # boolean. Prepare tests. Default: true.
    frameworkOption: 'appium' # 'appium' | 'espresso' | 'calabash' | 'uitest' | 'xcuitest'. Required when enablePrepare = true. Test framework. Default: 'appium'.
    #appiumBuildDirectory: # string. Required when enablePrepare = true && framework = appium. Build directory. 
    #espressoBuildDirectory: # string. Optional. Use when enablePrepare = true && framework = espresso. Build directory. 
    #espressoTestApkFile: # string. Optional. Use when enablePrepare = true && framework = espresso. Test APK path. 
    #calabashProjectDirectory: # string. Required when enablePrepare = true && framework = calabash. Project directory. 
    #calabashConfigFile: # string. Optional. Use when enablePrepare = true && framework = calabash. Cucumber config file. 
    #calabashProfile: # string. Optional. Use when enablePrepare = true && framework = calabash. Profile to run. 
    #calabashSkipConfigCheck: false # boolean. Optional. Use when enablePrepare = true && framework = calabash. Skip Configuration Check. Default: false.
    #uiTestBuildDirectory: # string. Required when enablePrepare = true && framework = uitest. Build directory. 
    #uitestStoreFile: # string. Optional. Use when enablePrepare = true && framework = uitest. Store file. 
    #uiTestStorePassword: # string. Optional. Use when enablePrepare = true && framework = uitest. Store password. 
    #uitestKeyAlias: # string. Optional. Use when enablePrepare = true && framework = uitest. Key alias. 
    #uiTestKeyPassword: # string. Optional. Use when enablePrepare = true && framework = uitest. Key password. 
    #uiTestToolsDirectory: # string. Optional. Use when enablePrepare = true && framework = uitest. Test tools directory. 
    #signInfo: # string. Optional. Use when framework = calabash || framework = uitest. Signing information. 
    #xcUITestBuildDirectory: # string. Optional. Use when enablePrepare = true && framework = xcuitest. Build directory. 
    #xcUITestIpaFile: # string. Optional. Use when enablePrepare = true && framework = xcuitest. Test IPA path. 
    #prepareOptions: # string. Optional. Use when enablePrepare = true. Additional options. 
  # Run Tests
    #runTests: true # boolean. Run tests. Default: true.
    credentialsOption: 'serviceEndpoint' # 'serviceEndpoint' | 'inputs'. Required when enableRun = true. Authentication method. Default: 'serviceEndpoint'.
    #serverEndpoint: # string. Required when enableRun = true && credsType = serviceEndpoint. App Center service connection. 
    #username: # string. Required when enableRun = true && credsType = inputs. App Center username. 
    #password: # string. Required when enableRun = true && credsType = inputs. App Center password. 
    appSlug: # string. Required when enableRun = true. App slug. 
    devices: # string. Required when enableRun = true. Devices. 
    #series: 'master' # string. Optional. Use when enableRun = true. Test series. Default: 'master'.
    #dsymDirectory: # string. Optional. Use when enableRun = true. dSYM directory. 
    localeOption: 'en_US' # 'da_DK' | 'nl_NL' | 'en_GB' | 'en_US' | 'fr_FR' | 'de_DE' | 'ja_JP' | 'ru_RU' | 'es_MX' | 'es_ES' | 'user'. Required when enableRun = true. System language. Default: 'en_US'.
    #userDefinedLocale: # string. Optional. Use when enableRun = true && locale = user. Other locale. 
    #loginOptions: # string. Optional. Use when enableRun = true && credsType = inputs. Additional options for login. 
    #runOptions: # string. Optional. Use when enableRun = true. Additional options for run. 
    #skipWaitingForResults: false # boolean. Optional. Use when enableRun = true. Do not wait for test result. Default: false.
  # Advanced
    #cliFile: # string. App Center CLI location. 
    #showDebugOutput: false # boolean. Enable debug output. Default: false.
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

<!-- :::item name="appFile"::: -->
:::moniker range="<=azure-pipelines"

**`appFile`** - **Binary application file path**<br>
Input alias: `app`. Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Relative path from the repo root to the APK or IPA file you want to test.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="artifactsDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`artifactsDirectory`** - **Artifacts directory**<br>
Input alias: `artifactsDir`. Type: string. Required. Default value: '$(Build.ArtifactStagingDirectory)/AppCenterTest'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Where to place the artifacts produced by the prepare step and used by the run step. This directory will be created if it does not exist.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="prepareTests"::: -->
:::moniker range="<=azure-pipelines"

**`prepareTests`** - **Prepare tests**<br>
Input alias: `enablePrepare`. Type: boolean. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="frameworkOption"::: -->
:::moniker range="<=azure-pipelines"

**`frameworkOption`** - **Test framework**<br>
Input alias: `framework`. Type: string. Required when enablePrepare = true. Allowed values: 'appium', 'espresso', 'calabash', 'uitest', 'xcuitest'. Default value: 'appium'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="appiumBuildDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`appiumBuildDirectory`** - **Build directory**<br>
Input alias: `appiumBuildDir`. Type: string. Required when enablePrepare = true && framework = appium.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to directory with Appium tests.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="espressoBuildDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`espressoBuildDirectory`** - **Build directory**<br>
Input alias: `espressoBuildDir`. Type: string. Optional. Use when enablePrepare = true && framework = espresso.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to Espresso output directory.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="espressoTestApkFile"::: -->
:::moniker range="<=azure-pipelines"

**`espressoTestApkFile`** - **Test APK path**<br>
Input alias: `espressoTestApkPath`. Type: string. Optional. Use when enablePrepare = true && framework = espresso.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to APK file with Espresso tests. If not set, build-dir is used to discover it. Wildcard is allowed.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="calabashProjectDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`calabashProjectDirectory`** - **Project directory**<br>
Input alias: `calabashProjectDir`. Type: string. Required when enablePrepare = true && framework = calabash.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to Calabash workspace directory.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="calabashConfigFile"::: -->
:::moniker range="<=azure-pipelines"

**`calabashConfigFile`** - **Cucumber config file**<br>
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
<!-- :::item name="uiTestBuildDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`uiTestBuildDirectory`** - **Build directory**<br>
Input alias: `uitestBuildDir`. Type: string. Required when enablePrepare = true && framework = uitest.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to directory with built test assemblies.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="uitestStorePath"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`uitestStorePath`** - **Store file**<br>
Type: string. Optional. Use when enablePrepare = true && framework = uitest.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="uiTestStorePassword"::: -->
:::moniker range="<=azure-pipelines"

**`uiTestStorePassword`** - **Store password**<br>
Input alias: `uitestStorePass`. Type: string. Optional. Use when enablePrepare = true && framework = uitest.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="uitestKeyAlias"::: -->
:::moniker range="<=azure-pipelines"

**`uitestKeyAlias`** - **Key alias**<br>
Type: string. Optional. Use when enablePrepare = true && framework = uitest.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="uiTestKeyPassword"::: -->
:::moniker range="<=azure-pipelines"

**`uiTestKeyPassword`** - **Key password**<br>
Input alias: `uitestKeyPass`. Type: string. Optional. Use when enablePrepare = true && framework = uitest.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="uiTestToolsDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`uiTestToolsDirectory`** - **Test tools directory**<br>
Input alias: `uitestToolsDir`. Type: string. Optional. Use when enablePrepare = true && framework = uitest.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to directory with Xamarin UI test tools that contains test-cloud.exe.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="signInfo"::: -->
:::moniker range="<=azure-pipelines"

**`signInfo`** - **Signing information**<br>
Type: string. Optional. Use when framework = calabash || framework = uitest.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Use Signing Infor for signing the test server.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="xcUITestBuildDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`xcUITestBuildDirectory`** - **Build directory**<br>
Input alias: `xcuitestBuildDir`. Type: string. Optional. Use when enablePrepare = true && framework = xcuitest.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to the build output directory (usually $(ProjectDir)/Build/Products/Debug-iphoneos).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="xcUITestIpaFile"::: -->
:::moniker range="<=azure-pipelines"

**`xcUITestIpaFile`** - **Test IPA path**<br>
Input alias: `xcuitestTestIpaPath`. Type: string. Optional. Use when enablePrepare = true && framework = xcuitest.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to the *.ipa file with the XCUITest tests.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="prepareOptions"::: -->
:::moniker range="<=azure-pipelines"

**`prepareOptions`** - **Additional options**<br>
Input alias: `prepareOpts`. Type: string. Optional. Use when enablePrepare = true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Additional arguments passed to the App Center test prepare step.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="runTests"::: -->
:::moniker range="<=azure-pipelines"

**`runTests`** - **Run tests**<br>
Input alias: `enableRun`. Type: boolean. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="credentialsOption"::: -->
:::moniker range="<=azure-pipelines"

**`credentialsOption`** - **Authentication method**<br>
Input alias: `credsType`. Type: string. Required when enableRun = true. Allowed values: 'serviceEndpoint', 'inputs'. Default value: 'serviceEndpoint'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Use App Center service connection or enter credentials to connect to Visual Studio App Center.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="serverEndpoint"::: -->
:::moniker range=">=azure-pipelines-2019"

**`serverEndpoint`** - **App Center service connection**<br>
Type: string. Required when enableRun = true && credsType = serviceEndpoint.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the service connection for Visual Studio App Center. To create one, click the Manage link and create a new service connection.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`serverEndpoint`** - **App Center connection**<br>
Type: string. Required when enableRun = true && credsType = serviceEndpoint.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the service connection for Visual Studio App Center. To create one, click the Manage link and create a new service connection.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="username"::: -->
:::moniker range="<=azure-pipelines"

**`username`** - **App Center username**<br>
Type: string. Required when enableRun = true && credsType = inputs.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Visit https://appcenter.ms/settings/profile to get your username.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="password"::: -->
:::moniker range="<=azure-pipelines"

**`password`** - **App Center password**<br>
Type: string. Required when enableRun = true && credsType = inputs.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Visit https://appcenter.ms/settings/profile to set your password. It can accept a variable defined in build or release pipelines as '$(passwordVariable)'. You may mark variable type as 'secret' to secure it.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="appSlug"::: -->
:::moniker range="<=azure-pipelines"

**`appSlug`** - **App slug**<br>
Type: string. Required when enableRun = true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The app slug is in the format of {username}/{app_identifier}.  To locate {username} and {app_identifier} for an app, click on its name from https://appcenter.ms/apps, and the resulting URL is in the format of https://appcenter.ms/users/{username}/apps/{app_identifier}.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="devices"::: -->
:::moniker range="<=azure-pipelines"

**`devices`** - **Devices**<br>
Type: string. Required when enableRun = true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
String to identify what devices this test will run against.  Copy and paste this string when you define a new test run from App Center Test beacon.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="series"::: -->
:::moniker range="<=azure-pipelines"

**`series`** - **Test series**<br>
Type: string. Optional. Use when enableRun = true. Default value: 'master'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The series name for organizing test runs (e.g. master, production, beta).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="dsymDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`dsymDirectory`** - **dSYM directory**<br>
Input alias: `dsymDir`. Type: string. Optional. Use when enableRun = true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to iOS symbol files.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="localeOption"::: -->
:::moniker range="<=azure-pipelines"

**`localeOption`** - **System language**<br>
Input alias: `locale`. Type: string. Required when enableRun = true. Allowed values: 'da_DK', 'nl_NL', 'en_GB', 'en_US', 'fr_FR', 'de_DE', 'ja_JP', 'ru_RU', 'es_MX', 'es_ES', 'user'. Default value: 'en_US'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If your language isn't displayed, select 'Other' and enter its locale below, such as en_US.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="userDefinedLocale"::: -->
:::moniker range="<=azure-pipelines"

**`userDefinedLocale`** - **Other locale**<br>
Type: string. Optional. Use when enableRun = true && locale = user.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter any two-letter ISO-639 language code along with any two-letter ISO 3166 country code in the format [language]_[country], such as en_US.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="loginOptions"::: -->
:::moniker range="<=azure-pipelines"

**`loginOptions`** - **Additional options for login**<br>
Input alias: `loginOpts`. Type: string. Optional. Use when enableRun = true && credsType = inputs.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Additional arguments passed to the App Center login step.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="runOptions"::: -->
:::moniker range="<=azure-pipelines"

**`runOptions`** - **Additional options for run**<br>
Input alias: `runOpts`. Type: string. Optional. Use when enableRun = true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Additional arguments passed to the App Center test run.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="skipWaitingForResults"::: -->
:::moniker range="<=azure-pipelines"

**`skipWaitingForResults`** - **Do not wait for test result**<br>
Input alias: `async`. Type: boolean. Optional. Use when enableRun = true. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Execute command asynchronously, exit when tests are uploaded, without waiting for test results.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="cliFile"::: -->
:::moniker range="<=azure-pipelines"

**`cliFile`** - **App Center CLI location**<br>
Input alias: `cliLocationOverride`. Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to the App Center CLI on the build or release agent.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="showDebugOutput"::: -->
:::moniker range="<=azure-pipelines"

**`showDebugOutput`** - **Enable debug output**<br>
Input alias: `debug`. Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Add --debug to the App Center CLI.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="uitestStoreFile"::: -->
:::moniker range="<=azure-pipelines-2019"

**`uitestStoreFile`** - **Store file**<br>
Type: string. Optional. Use when enablePrepare = true && framework = uitest.<br>
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

This task lets you run test suites against an application binary (`.apk` or `.ipa` file) using App Center Test.

* [Sign up with App Center](https://appcenter.ms/signup?utm_source=DevOps&utm_medium=Azure&utm_campaign=docs) first.
* For details about using this task, see the App Center documentation article [Using Azure DevOps for UI Testing](/appcenter/test-cloud/vsts-plugin).
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

This example runs Espresso tests on an Android app using the App Center Test task.

```yaml
steps:
- task: AppCenterTest@1
  displayName: 'Espresso Test - Synchronous'
  inputs:
    appFile: 'Espresso/espresso-app.apk'
    artifactsDirectory: '$(Build.ArtifactStagingDirectory)/AppCenterTest'
    frameworkOption: espresso
    espressoBuildDirectory: Espresso
    serverEndpoint: 'myAppCenterServiceConnection'
    appSlug: 'xplatbg1/EspressoTests'
    devices: a84c93af
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range="<=azure-pipelines"

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
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->