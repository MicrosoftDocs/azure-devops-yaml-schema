---
title: Npm@1 - npm v1 task
description: Install and publish npm packages, or run an npm command. Supports npmjs.com and authenticated registries like Azure Artifacts.
ms.date: 03/20/2025
monikerRange: "<=azure-pipelines"
---

# Npm@1 - npm v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to install and publish npm packages or to run an `npm` command. Supports `npmjs.com` and authenticated registries like Azure Artifacts.

>[!NOTE]
> The [npm Authenticate task](/azure/devops/pipelines/tasks/reference/npm-authenticate-v0) is the recommended way to authenticate with Azure Artifacts. This task no longer takes new features and only critical bugs are addressed.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="<=azure-pipelines"

```yaml
# npm v1
# Install and publish npm packages, or run an npm command. Supports npmjs.com and authenticated registries like Azure Artifacts.
- task: Npm@1
  inputs:
    command: 'install' # 'ci' | 'install' | 'publish' | 'custom'. Required. Command. Default: install.
    #workingDir: # string. Working folder that contains package.json. 
    #customCommand: # string. Required when command = custom. Command and arguments. 
  # Advanced
    #verbose: # boolean. Optional. Use when command = install || command = ci || command = publish. Verbose logging. 
    #publishPackageMetadata: true # boolean. Optional. Use when command = publish && publishRegistry = useFeed. Publish pipeline metadata. Default: true.
  # Custom registries and authentication
    #customRegistry: 'useNpmrc' # 'useNpmrc' | 'useFeed'. Optional. Use when command = install || command = ci || command = custom. Registries to use. Default: useNpmrc.
    #customFeed: # string. Required when (command = install || command = ci || command = custom) && customRegistry = useFeed. Use packages from this Azure Artifacts/TFS registry. 
    #customEndpoint: # string. Optional. Use when (command = install || command = ci || command = custom) && customRegistry = useNpmrc. Credentials for registries outside this organization/collection. 
  # Destination registry and authentication
    #publishRegistry: 'useExternalRegistry' # 'useExternalRegistry' | 'useFeed'. Optional. Use when command = publish. Registry location. Default: useExternalRegistry.
    #publishFeed: # string. Required when publishRegistry = useFeed && command = publish. Target registry. 
    #publishEndpoint: # string. Required when publishRegistry = useExternalRegistry && command = publish. External Registry.
```

:::moniker-end

<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="command"::: -->
:::moniker range="<=azure-pipelines"

**`command`** - **Command**<br>
`string`. Required. Allowed values: `ci`, `install`, `publish`, `custom`. Default value: `install`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the command and arguments, which are passed to `npm` for execution.

If your arguments contain double quotes (`"`), escape them with a slash (`\`), and surround the escaped string with double quotes (`"`).

By default, packages are installed locally. To install packages globally, specify `install -g` as the command. For more information, see [Downloading and installing packages globally](https://docs.npmjs.com/downloading-and-installing-packages-globally) and [Downloading and installing packages locally](https://docs.npmjs.com/downloading-and-installing-packages-locally).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="workingDir"::: -->
:::moniker range="<=azure-pipelines"

**`workingDir`** - **Working folder that contains package.json**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the path to the folder containing the target `package.json` and `.npmrc` files. Select the folder, not the file. Example: `/packages/mypackage`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="verbose"::: -->
:::moniker range="<=azure-pipelines"

**`verbose`** - **Verbose logging**<br>
`boolean`. Optional. Use when `command = install || command = ci || command = publish`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Prints more information to the console when the task runs.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customCommand"::: -->
:::moniker range="<=azure-pipelines"

**`customCommand`** - **Command and arguments**<br>
`string`. Required when `command = custom`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Runs a custom command. Example: `dist-tag ls mypackage`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customRegistry"::: -->
:::moniker range="<=azure-pipelines"

**`customRegistry`** - **Registries to use**<br>
`string`. Optional. Use when `command = install || command = ci || command = custom`. Allowed values: `useNpmrc` (Registries in my .npmrc), `useFeed` (Registry I select here). Default value: `useNpmrc`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the registries to use. Commit a `.npmrc` file to your source code repository and set its path as the value, or specify a registry from Azure Artifacts as the value.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customFeed"::: -->
:::moniker range="<=azure-pipelines"

**`customFeed`** - **Use packages from this Azure Artifacts/TFS registry**<br>
`string`. Required when `(command = install || command = ci || command = custom) && customRegistry = useFeed`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Includes the selected feed in the generated `.npmrc`. For project-scoped feeds, use `ProjectName/FeedName` or `ProjectID/FeedID`. For organization-scoped feeds, the value should be  the feed name.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customEndpoint"::: -->
:::moniker range="<=azure-pipelines"

**`customEndpoint`** - **Credentials for registries outside this organization/collection**<br>
`string`. Optional. Use when `(command = install || command = ci || command = custom) && customRegistry = useNpmrc`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Credentials to use for external registries located in the project's `.npmrc`. Leave this blank for registries in this account/collection; the task uses the build's credentials automatically.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishRegistry"::: -->
:::moniker range="<=azure-pipelines"

**`publishRegistry`** - **Registry location**<br>
`string`. Optional. Use when `command = publish`. Allowed values: `useExternalRegistry` (External npm registry (including other accounts/collections)), `useFeed` (Registry I select here). Default value: `useExternalRegistry`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the registry that the command will target.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishFeed"::: -->
:::moniker range="<=azure-pipelines"

**`publishFeed`** - **Target registry**<br>
`string`. Required when `publishRegistry = useFeed && command = publish`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a registry hosted in the account. You must have Package Management installed and licensed to select a registry here.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishPackageMetadata"::: -->
:::moniker range="<=azure-pipelines"

**`publishPackageMetadata`** - **Publish pipeline metadata**<br>
`boolean`. Optional. Use when `command = publish && publishRegistry = useFeed`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Associates the build/release pipeline's metadata (the run # and source code information) with the package.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishEndpoint"::: -->
:::moniker range="<=azure-pipelines"

**`publishEndpoint`** - **External Registry**<br>
`string`. Required when `publishRegistry = useExternalRegistry && command = publish`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the credentials to use for publishing to an external registry.
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

> [!NOTE]
> The **Project Collection Build Service** and your project's **Build Service** identity must be set to **Contributor** to publish your packages to a feed using Azure Pipelines. See [Add new users/groups](/azure/devops/artifacts/feeds/feed-permissions#configure-feed-settings) for more details.

### Where can I learn npm commands and arguments?

* [npm docs](https://docs.npmjs.com/)
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

* [Build your Node.js app with gulp](/azure/devops/pipelines/ecosystems/javascript)
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range="<=azure-pipelines"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | Self-hosted agents must have [capabilities](/azure/devops/pipelines/agents/agents#capabilities) that match the following [demands](/azure/devops/pipelines/process/demands) to run jobs that use this task: npm |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.115.0 or greater |
| Task category | Package |

:::moniker-end

<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->