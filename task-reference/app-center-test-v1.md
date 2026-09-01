---
title: AppCenterTest@1 - App Center test v1 task
description: Test app packages with Visual Studio App Center.
ms.date: 09/01/2026
monikerRange: "=azure-pipelines || =azure-pipelines-server || =azure-pipelines-2022.2 || =azure-pipelines-2022.1 || =azure-pipelines-2022"
author: ramiMSFT
ms.author: rabououn
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

:::moniker range="<=azure-pipelines"

```yaml
# App Center test v1
# Test app packages with Visual Studio App Center.
- task: AppCenterTest@1
  inputs:
    appFile: # string. Alias: app. Required. Binary application file path. 
    artifactsDirectory: '$(Build.ArtifactStagingDirectory)/AppCenterTest' # string. Alias: artifactsDir. Required. Artifacts directory. Default: $(Build.ArtifactStagingDirectory)/AppCenterTest.
  # Prepare Tests
    #prepareTests: true # boolean. Alias: enablePrepare. Prepare tests. Default: true.
    frameworkOption: 'appium' # 'appium' | 'espresso' | 'calabash' | 'uitest' | 'xcuitest'. Alias: framework. Required when prepareTests = true. Test framework. Default: appium.
    #appiumBuildDirectory: # string. Alias: appiumBuildDir. Required when prepareTests = true && frameworkOption = appium. Build directory. 
    #espressoBuildDirectory: # string. Alias: espressoBuildDir. Optional. Use when prepareTests = true && frameworkOption = espresso. Build directory. 
    #espressoTestApkFile: # string. Alias: espressoTestApkPath. Optional. Use when prepareTests = true && frameworkOption = espresso. Test APK path. 
    #calabashProjectDirectory: # string. Alias: calabashProjectDir. Required when prepareTests = true && frameworkOption = calabash. Project directory. 
    #calabashConfigFile: # string. Optional. Use when prepareTests = true && frameworkOption = calabash. Cucumber config file. 
    #calabashProfile: # string. Optional. Use when prepareTests = true && frameworkOption = calabash. Profile to run. 
    #calabashSkipConfigCheck: false # boolean. Optional. Use when prepareTests = true && frameworkOption = calabash. Skip Configuration Check. Default: false.
    #uiTestBuildDirectory: # string. Alias: uitestBuildDir. Required when prepareTests = true && frameworkOption = uitest. Build directory. 
    #uitestStorePath: # string. Optional. Use when prepareTests = true && frameworkOption = uitest. Store file. 
    #uiTestStorePassword: # string. Alias: uitestStorePass. Optional. Use when prepareTests = true && frameworkOption = uitest. Store password. 
    #uitestKeyAlias: # string. Optional. Use when prepareTests = true && frameworkOption = uitest. Key alias. 
    #uiTestKeyPassword: # string. Alias: uitestKeyPass. Optional. Use when prepareTests = true && frameworkOption = uitest. Key password. 
    #uiTestToolsDirectory: # string. Alias: uitestToolsDir. Optional. Use when prepareTests = true && frameworkOption = uitest. Test tools directory. 
    #signInfo: # string. Optional. Use when frameworkOption = calabash || frameworkOption = uitest. Signing information. 
    #xcUITestBuildDirectory: # string. Alias: xcuitestBuildDir. Optional. Use when prepareTests = true && frameworkOption = xcuitest. Build directory. 
    #xcUITestIpaFile: # string. Alias: xcuitestTestIpaPath. Optional. Use when prepareTests = true && frameworkOption = xcuitest. Test IPA path. 
    #prepareOptions: # string. Alias: prepareOpts. Optional. Use when prepareTests = true. Additional options. 
  # Run Tests
    #runTests: true # boolean. Alias: enableRun. Run tests. Default: true.
    credentialsOption: 'serviceEndpoint' # 'serviceEndpoint' | 'inputs'. Alias: credsType. Required when runTests = true. Authentication method. Default: serviceEndpoint.
    #serverEndpoint: # string. Required when runTests = true && credentialsOption = serviceEndpoint. App Center service connection. 
    #username: # string. Required when runTests = true && credentialsOption = inputs. App Center username. 
    #password: # string. Required when runTests = true && credentialsOption = inputs. App Center password. 
    appSlug: # string. Required when runTests = true. App slug. 
    devices: # string. Required when runTests = true. Devices. 
    #series: 'master' # string. Optional. Use when runTests = true. Test series. Default: master.
    #dsymDirectory: # string. Alias: dsymDir. Optional. Use when runTests = true. dSYM directory. 
    localeOption: 'en_US' # 'da_DK' | 'nl_NL' | 'en_GB' | 'en_US' | 'fr_FR' | 'de_DE' | 'ja_JP' | 'ru_RU' | 'es_MX' | 'es_ES' | 'user'. Alias: locale. Required when runTests = true. System language. Default: en_US.
    #userDefinedLocale: # string. Optional. Use when runTests = true && localeOption = user. Other locale. 
    #loginOptions: # string. Alias: loginOpts. Optional. Use when runTests = true && credentialsOption = inputs. Additional options for login. 
    #runOptions: # string. Alias: runOpts. Optional. Use when runTests = true. Additional options for run. 
    #skipWaitingForResults: false # boolean. Alias: async. Optional. Use when runTests = true. Do not wait for test result. Default: false.
  # Advanced
    #cliFile: # string. Alias: cliLocationOverride. App Center CLI location. 
    #showDebugOutput: false # boolean. Alias: debug. Enable debug output. Default: false.
```

:::moniker-end

<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<a name="appfile-property"></a>
<!-- :::item name="appFile"::: -->
:::moniker range="<=azure-pipelines"

**`appFile`** - **Binary application file path**<br>
[Input alias](index.md#what-are-task-input-aliases): `app`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The relative path from the repo root to the APK or IPA file you want to test.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="artifactsdirectory-property"></a>
<!-- :::item name="artifactsDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`artifactsDirectory`** - **Artifacts directory**<br>
[Input alias](index.md#what-are-task-input-aliases): `artifactsDir`. `string`. Required. Default value: `$(Build.ArtifactStagingDirectory)/AppCenterTest`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies where to place the artifacts produced by the prepare step and used by the run step. This directory will be created if it does not already exist.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="preparetests-property"></a>
<!-- :::item name="prepareTests"::: -->
:::moniker range="<=azure-pipelines"

**`prepareTests`** - **Prepare tests**<br>
[Input alias](index.md#what-are-task-input-aliases): `enablePrepare`. `boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
When set to `true`, this input prepares the tests.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="frameworkoption-property"></a>
<!-- :::item name="frameworkOption"::: -->
:::moniker range="<=azure-pipelines"

**`frameworkOption`** - **Test framework**<br>
[Input alias](index.md#what-are-task-input-aliases): `framework`. `string`. Required when `prepareTests = true`. Allowed values: `appium`, `espresso`, `calabash`, `uitest` (Xamarin UI Test), `xcuitest`. Default value: `appium`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="appiumbuilddirectory-property"></a>
<!-- :::item name="appiumBuildDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`appiumBuildDirectory`** - **Build directory**<br>
[Input alias](index.md#what-are-task-input-aliases): `appiumBuildDir`. `string`. Required when `prepareTests = true && frameworkOption = appium`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The path to the directory with the Appium tests.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="espressobuilddirectory-property"></a>
<!-- :::item name="espressoBuildDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`espressoBuildDirectory`** - **Build directory**<br>
[Input alias](index.md#what-are-task-input-aliases): `espressoBuildDir`. `string`. Optional. Use when `prepareTests = true && frameworkOption = espresso`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The path to the Espresso output directory.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="espressotestapkfile-property"></a>
<!-- :::item name="espressoTestApkFile"::: -->
:::moniker range="<=azure-pipelines"

**`espressoTestApkFile`** - **Test APK path**<br>
[Input alias](index.md#what-are-task-input-aliases): `espressoTestApkPath`. `string`. Optional. Use when `prepareTests = true && frameworkOption = espresso`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The path to the APK file with the Espresso tests. If not set, `build-dir` is used to discover it. A wildcard is allowed.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="calabashprojectdirectory-property"></a>
<!-- :::item name="calabashProjectDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`calabashProjectDirectory`** - **Project directory**<br>
[Input alias](index.md#what-are-task-input-aliases): `calabashProjectDir`. `string`. Required when `prepareTests = true && frameworkOption = calabash`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The path to the Calabash workspace directory.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="calabashconfigfile-property"></a>
<!-- :::item name="calabashConfigFile"::: -->
:::moniker range="<=azure-pipelines"

**`calabashConfigFile`** - **Cucumber config file**<br>
`string`. Optional. Use when `prepareTests = true && frameworkOption = calabash`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The path to the Cucumber configuration file, usually cucumber.yml.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="calabashprofile-property"></a>
<!-- :::item name="calabashProfile"::: -->
:::moniker range="<=azure-pipelines"

**`calabashProfile`** - **Profile to run**<br>
`string`. Optional. Use when `prepareTests = true && frameworkOption = calabash`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The profile to run.  This value must exist in the Cucumber configuration file.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="calabashskipconfigcheck-property"></a>
<!-- :::item name="calabashSkipConfigCheck"::: -->
:::moniker range="<=azure-pipelines"

**`calabashSkipConfigCheck`** - **Skip Configuration Check**<br>
`boolean`. Optional. Use when `prepareTests = true && frameworkOption = calabash`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
When set to `true`, this input skips the configuration check specified by the Cucumber profile.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="uitestbuilddirectory-property"></a>
<!-- :::item name="uiTestBuildDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`uiTestBuildDirectory`** - **Build directory**<br>
[Input alias](index.md#what-are-task-input-aliases): `uitestBuildDir`. `string`. Required when `prepareTests = true && frameworkOption = uitest`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The path to the directory with the built test assemblies.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="uiteststorepath-property"></a>
<!-- :::item name="uitestStorePath"::: -->
:::moniker range="<=azure-pipelines"

**`uitestStorePath`** - **Store file**<br>
`string`. Optional. Use when `prepareTests = true && frameworkOption = uitest`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The path to the store file that is used to sign the app.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="uiteststorepassword-property"></a>
<!-- :::item name="uiTestStorePassword"::: -->
:::moniker range="<=azure-pipelines"

**`uiTestStorePassword`** - **Store password**<br>
[Input alias](index.md#what-are-task-input-aliases): `uitestStorePass`. `string`. Optional. Use when `prepareTests = true && frameworkOption = uitest`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The password of the store file that is used to sign the app. To encrypt this value, use a new variable with its lock enabled on the Variables tab.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="uitestkeyalias-property"></a>
<!-- :::item name="uitestKeyAlias"::: -->
:::moniker range="<=azure-pipelines"

**`uitestKeyAlias`** - **Key alias**<br>
`string`. Optional. Use when `prepareTests = true && frameworkOption = uitest`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the alias that identifies the public/private key pair that is used in the store file.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="uitestkeypassword-property"></a>
<!-- :::item name="uiTestKeyPassword"::: -->
:::moniker range="<=azure-pipelines"

**`uiTestKeyPassword`** - **Key password**<br>
[Input alias](index.md#what-are-task-input-aliases): `uitestKeyPass`. `string`. Optional. Use when `prepareTests = true && frameworkOption = uitest`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the key password for the alias and store file. To encrypt this value, use a new variable with its lock enabled on the Variables tab.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="uitesttoolsdirectory-property"></a>
<!-- :::item name="uiTestToolsDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`uiTestToolsDirectory`** - **Test tools directory**<br>
[Input alias](index.md#what-are-task-input-aliases): `uitestToolsDir`. `string`. Optional. Use when `prepareTests = true && frameworkOption = uitest`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The path to the directory with the Xamarin UI test tools that contain *test-cloud.exe*.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="signinfo-property"></a>
<!-- :::item name="signInfo"::: -->
:::moniker range="<=azure-pipelines"

**`signInfo`** - **Signing information**<br>
`string`. Optional. Use when `frameworkOption = calabash || frameworkOption = uitest`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Signs the test server.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="xcuitestbuilddirectory-property"></a>
<!-- :::item name="xcUITestBuildDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`xcUITestBuildDirectory`** - **Build directory**<br>
[Input alias](index.md#what-are-task-input-aliases): `xcuitestBuildDir`. `string`. Optional. Use when `prepareTests = true && frameworkOption = xcuitest`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The path to the build output directory (usually `$(ProjectDir)/Build/Products/Debug-iphoneos`).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="xcuitestipafile-property"></a>
<!-- :::item name="xcUITestIpaFile"::: -->
:::moniker range="<=azure-pipelines"

**`xcUITestIpaFile`** - **Test IPA path**<br>
[Input alias](index.md#what-are-task-input-aliases): `xcuitestTestIpaPath`. `string`. Optional. Use when `prepareTests = true && frameworkOption = xcuitest`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The path to the .ipa file with the XCUITest tests.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="prepareoptions-property"></a>
<!-- :::item name="prepareOptions"::: -->
:::moniker range="<=azure-pipelines"

**`prepareOptions`** - **Additional options**<br>
[Input alias](index.md#what-are-task-input-aliases): `prepareOpts`. `string`. Optional. Use when `prepareTests = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The additional arguments that are passed to the App Center test prepare step.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="runtests-property"></a>
<!-- :::item name="runTests"::: -->
:::moniker range="<=azure-pipelines"

**`runTests`** - **Run tests**<br>
[Input alias](index.md#what-are-task-input-aliases): `enableRun`. `boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Runs the tests.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="credentialsoption-property"></a>
<!-- :::item name="credentialsOption"::: -->
:::moniker range="<=azure-pipelines"

**`credentialsOption`** - **Authentication method**<br>
[Input alias](index.md#what-are-task-input-aliases): `credsType`. `string`. Required when `runTests = true`. Allowed values: `serviceEndpoint` (App Center service connection), `inputs` (Credentials). Default value: `serviceEndpoint`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Uses the App Center service connection or enters the credentials to connect to Visual Studio App Center.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="serverendpoint-property"></a>
<!-- :::item name="serverEndpoint"::: -->
:::moniker range="<=azure-pipelines"

**`serverEndpoint`** - **App Center service connection**<br>
`string`. Required when `runTests = true && credentialsOption = serviceEndpoint`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selects the service connection for Visual Studio App Center. If needed, click the Manage link to create a new service connection.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="username-property"></a>
<!-- :::item name="username"::: -->
:::moniker range="<=azure-pipelines"

**`username`** - **App Center username**<br>
`string`. Required when `runTests = true && credentialsOption = inputs`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Create your username by visiting the [App Center sign in page](https://appcenter.ms/settings/profile), and provide the value here.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="password-property"></a>
<!-- :::item name="password"::: -->
:::moniker range="<=azure-pipelines"

**`password`** - **App Center password**<br>
`string`. Required when `runTests = true && credentialsOption = inputs`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Set your password by visiting the [App Center sign in page](https://appcenter.ms/settings/profile), and provide the value here. Variables defined in build or release pipelines as `$(passwordVariable)` are accepted. You may mark the variable type as `secret` to secure it.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="appslug-property"></a>
<!-- :::item name="appSlug"::: -->
:::moniker range="<=azure-pipelines"

**`appSlug`** - **App slug**<br>
`string`. Required when `runTests = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The app slug is in the format of `<username>/<app_identifier>`.  To locate the `<username>` and `<app_identifier>` for an app, click its name from [Visual Studio App Center](https://appcenter.ms/apps). The resulting URL is in the format `https://appcenter.ms/users/<username>/apps/<app_identifier>`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="devices-property"></a>
<!-- :::item name="devices"::: -->
:::moniker range="<=azure-pipelines"

**`devices`** - **Devices**<br>
`string`. Required when `runTests = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Identifies the devices this test will run against.  Copy and paste this string when you define a new test run from the Visual Studio App Center Test beacon.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="series-property"></a>
<!-- :::item name="series"::: -->
:::moniker range="<=azure-pipelines"

**`series`** - **Test series**<br>
`string`. Optional. Use when `runTests = true`. Default value: `master`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The series name for organizing the test runs (for example: master, production, beta).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="dsymdirectory-property"></a>
<!-- :::item name="dsymDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`dsymDirectory`** - **dSYM directory**<br>
[Input alias](index.md#what-are-task-input-aliases): `dsymDir`. `string`. Optional. Use when `runTests = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The path to the iOS symbol files.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="localeoption-property"></a>
<!-- :::item name="localeOption"::: -->
:::moniker range="<=azure-pipelines"

**`localeOption`** - **System language**<br>
[Input alias](index.md#what-are-task-input-aliases): `locale`. `string`. Required when `runTests = true`. Allowed values: `da_DK` (Danish (Denmark)), `nl_NL` (Dutch (Netherlands)), `en_GB` (English (United Kingdom)), `en_US` (English (United States)), `fr_FR` (French (France)), `de_DE` (German (Germany)), `ja_JP` (Japanese (Japan)), `ru_RU` (Russian (Russia)), `es_MX` (Spanish (Mexico)), `es_ES` (Spanish (Spain)), `user` (Other). Default value: `en_US`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Utilize if your language isn't displayed. Select `Other` and enter its locale, such as `en_US`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="userdefinedlocale-property"></a>
<!-- :::item name="userDefinedLocale"::: -->
:::moniker range="<=azure-pipelines"

**`userDefinedLocale`** - **Other locale**<br>
`string`. Optional. Use when `runTests = true && localeOption = user`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enters any two-letter ISO-639 language code along with any two-letter ISO 3166 country code in the format `<language>_<country>`, such as `en_US`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="loginoptions-property"></a>
<!-- :::item name="loginOptions"::: -->
:::moniker range="<=azure-pipelines"

**`loginOptions`** - **Additional options for login**<br>
[Input alias](index.md#what-are-task-input-aliases): `loginOpts`. `string`. Optional. Use when `runTests = true && credentialsOption = inputs`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The additional arguments that are passed to the Visual Studio App Center login step.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="runoptions-property"></a>
<!-- :::item name="runOptions"::: -->
:::moniker range="<=azure-pipelines"

**`runOptions`** - **Additional options for run**<br>
[Input alias](index.md#what-are-task-input-aliases): `runOpts`. `string`. Optional. Use when `runTests = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The additional arguments that are passed to the Visual Studio App Center test run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="skipwaitingforresults-property"></a>
<!-- :::item name="skipWaitingForResults"::: -->
:::moniker range="<=azure-pipelines"

**`skipWaitingForResults`** - **Do not wait for test result**<br>
[Input alias](index.md#what-are-task-input-aliases): `async`. `boolean`. Optional. Use when `runTests = true`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Executes a command asynchronously and exits when the tests are uploaded without waiting for the test results.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="clifile-property"></a>
<!-- :::item name="cliFile"::: -->
:::moniker range="<=azure-pipelines"

**`cliFile`** - **App Center CLI location**<br>
[Input alias](index.md#what-are-task-input-aliases): `cliLocationOverride`. `string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The path to the Visual Studio App Center CLI on the build or release agent.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="showdebugoutput-property"></a>
<!-- :::item name="showDebugOutput"::: -->
:::moniker range="<=azure-pipelines"

**`showDebugOutput`** - **Enable debug output**<br>
[Input alias](index.md#what-are-task-input-aliases): `debug`. `boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Adds `--debug` to the Visual Studio App Center CLI.
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

This task lets you run test suites against an application binary (**.apk** or **.ipa** file) using App Center Test.

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

:::moniker range=">=azure-pipelines-2022.2"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.206.1 or greater |
| Task category | Test |

:::moniker-end

:::moniker range="=azure-pipelines-2022.1"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.144.0 or greater |
| Task category | Test |

:::moniker-end

:::moniker range="=azure-pipelines-2022"

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