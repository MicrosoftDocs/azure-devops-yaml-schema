---
title: XamarinTestCloud@1 - Xamarin Test Cloud v1 task
description: XamarinTestCloud@1 is deprecated. Test mobile apps with Xamarin Test Cloud using Xamarin.UITest. Instead, use the 'App Center test' task.
ms.date: 10/21/2022
monikerRange: "<=azure-pipelines"
---

# XamarinTestCloud@1 - Xamarin Test Cloud v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
XamarinTestCloud@1 is deprecated. Test mobile apps with Xamarin Test Cloud using Xamarin.UITest. Instead, use the 'App Center test' task.
<!-- :::editable-content-end::: -->

This task is deprecated.

:::moniker-end

:::moniker range="<=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
[Depreciated] Testing mobile apps with Xamarin Test Cloud using Xamarin.UITest - recommended task is now AppCenterTest.
<!-- :::editable-content-end::: -->

This task is deprecated.

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# Xamarin Test Cloud v1
# [Deprecated] Test mobile apps with Xamarin Test Cloud using Xamarin.UITest. Instead, use the 'App Center test' task.
- task: XamarinTestCloud@1
  inputs:
    appFile: # string. Alias: app. Required. App file. 
    #dsymFile: # string. Alias: dsym. dSYM file (iOS only). 
    teamApiKey: # string. Required. Team API key. 
    email: # string. Alias: user. Required. User email. 
    devices: # string. Required. Devices. 
    series: 'master' # string. Required. Series. Default: master.
    testAssemblyDirectory: # string. Alias: testDir. Required. Test assembly directory. 
  # Advanced
    parallelizationOption: 'none' # 'none' | '--fixture-chunk' | '--test-chunk'. Alias: parallelization. Required. Parallelization. Default: none.
    localeOption: 'en_US' # 'da_DK' | 'nl_NL' | 'en_GB' | 'en_US' | 'fr_FR' | 'de_DE' | 'ja_JP' | 'ru_RU' | 'es_MX' | 'es_ES' | 'user'. Alias: locale. Required. System language. Default: en_US.
    #userDefinedLocale: # string. Optional. Use when locale = user. Other locale. 
    testCloudFile: '**/packages/**/tools/test-cloud.exe' # string. Alias: testCloudLocation. Required. test-cloud.exe location. Default: **/packages/**/tools/test-cloud.exe.
    #optionalArgs: # string. Optional arguments. 
    #publishNUnitResults: true # boolean. Publish results to Azure Pipelines. Default: true.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Xamarin Test Cloud v1
# [Depreciated] Testing mobile apps with Xamarin Test Cloud using Xamarin.UITest - recommended task is now AppCenterTest.
- task: XamarinTestCloud@1
  inputs:
    appFile: # string. Alias: app. Required. App file. 
    #dsymFile: # string. Alias: dsym. dSYM file (iOS only). 
    teamApiKey: # string. Required. Team API key. 
    email: # string. Alias: user. Required. User email. 
    devices: # string. Required. Devices. 
    series: 'master' # string. Required. Series. Default: master.
    testAssemblyDirectory: # string. Alias: testDir. Required. Test assembly directory. 
  # Advanced
    parallelizationOption: 'none' # 'none' | '--fixture-chunk' | '--test-chunk'. Alias: parallelization. Required. Parallelization. Default: none.
    localeOption: 'en_US' # 'da_DK' | 'nl_NL' | 'en_GB' | 'en_US' | 'fr_FR' | 'de_DE' | 'ja_JP' | 'ru_RU' | 'es_MX' | 'es_ES' | 'user'. Alias: locale. Required. System language. Default: en_US.
    #userDefinedLocale: # string. Optional. Use when locale = user. Other locale. 
    testCloudFile: '**/packages/**/tools/test-cloud.exe' # string. Alias: testCloudLocation. Required. test-cloud.exe location. Default: **/packages/**/tools/test-cloud.exe.
    #optionalArgs: # string. Optional arguments. 
    #publishNUnitResults: true # boolean. Publish results to Azure Pipelines/TFS. Default: true.
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

**`appFile`** - **App file**<br>
Input alias: `app`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Relative path from repo root of the app(s) to test.  Wildcards can be used ([more information](https://go.microsoft.com/fwlink/?linkid=856077)).  For example, `**/*.apk` for all APK files in all subfolders.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="dsymFile"::: -->
:::moniker range="<=azure-pipelines"

**`dsymFile`** - **dSYM file (iOS only)**<br>
Input alias: `dsym`. `string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
To make crash logs easier to read, you can upload a dSYM file that is associated with your app. This field only applies to iOS apps. Provide path relative to the .ipa file. Wildcards can be used ([more information](https://go.microsoft.com/fwlink/?linkid=856077)). For example: *.dSYM.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="teamApiKey"::: -->
:::moniker range="<=azure-pipelines"

**`teamApiKey`** - **Team API key**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Your Xamarin Test Cloud Team API key can be found under "Teams & Apps" at https://testcloud.xamarin.com/account.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="email"::: -->
:::moniker range="<=azure-pipelines"

**`email`** - **User email**<br>
Input alias: `user`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
User name this test will run under.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="devices"::: -->
:::moniker range="<=azure-pipelines"

**`devices`** - **Devices**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The devices string is generated by Xamarin Test Cloud. It can be found as the value of the --devices command line argument of a Test Cloud test run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="series"::: -->
:::moniker range="<=azure-pipelines"

**`series`** - **Series**<br>
`string`. Required. Default value: `master`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The series name for organizing test runs (e.g. master, production, beta).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testAssemblyDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`testAssemblyDirectory`** - **Test assembly directory**<br>
Input alias: `testDir`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Relative path to the folder containing the test assemblies, such as: SolutionName/TestsProjectName/bin/Release.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="parallelizationOption"::: -->
:::moniker range="<=azure-pipelines"

**`parallelizationOption`** - **Parallelization**<br>
Input alias: `parallelization`. `string`. Required. Allowed values: `none`, `--fixture-chunk` (By test fixture), `--test-chunk` (By test method). Default value: `none`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="localeOption"::: -->
:::moniker range="<=azure-pipelines"

**`localeOption`** - **System language**<br>
Input alias: `locale`. `string`. Required. Allowed values: `da_DK` (Danish (Denmark)), `nl_NL` (Dutch (Netherlands)), `en_GB` (English (United Kingdom)), `en_US` (English (United States)), `fr_FR` (French (France)), `de_DE` (German (Germany)), `ja_JP` (Japanese (Japan)), `ru_RU` (Russian (Russia)), `es_MX` (Spanish (Mexico)), `es_ES` (Spanish (Spain)), `user` (Other). Default value: `en_US`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If your language isn't displayed, select 'Other' and enter its locale below, such as en_US.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="userDefinedLocale"::: -->
:::moniker range="<=azure-pipelines"

**`userDefinedLocale`** - **Other locale**<br>
`string`. Optional. Use when `locale = user`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter any two-letter ISO-639 language code along with any two-letter ISO 3166 country code in the format [language]_[country], such as en_US.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testCloudFile"::: -->
:::moniker range="<=azure-pipelines"

**`testCloudFile`** - **test-cloud.exe location**<br>
Input alias: `testCloudLocation`. `string`. Required. Default value: `**/packages/**/tools/test-cloud.exe`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The path to test-cloud.exe.  Wildcards can be used, in which case the first occurrence of test-cloud.exe is used ([more information](https://go.microsoft.com/fwlink/?linkid=856077)).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="optionalArgs"::: -->
:::moniker range="<=azure-pipelines"

**`optionalArgs`** - **Optional arguments**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Additional arguments passed to test-cloud.exe.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishNUnitResults"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`publishNUnitResults`** - **Publish results to Azure Pipelines**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
When selected, --nunit-xml option will be passed to test-cloud.exe. Results from the NUnit xml file will be published to Azure Pipelines.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2019"

**`publishNUnitResults`** - **Publish results to Azure Pipelines/TFS**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
When selected, --nunit-xml option will be passed to test-cloud.exe. Results from the NUnit xml file will be published to Azure Pipelines/TFS.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`publishNUnitResults`** - **Publish results to TFS/Team Services**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
When selected, --nunit-xml option will be passed to test-cloud.exe. Results from the NUnit xml file will be published to TFS/Team Services.
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
| Agent version |  1.83.0 or greater |
| Task category | Test |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->