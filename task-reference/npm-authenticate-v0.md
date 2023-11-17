---
title: npmAuthenticate@0 - npm authenticate (for task runners) v0 task
description: Don't use this task if you're also using the npm task. Provides npm credentials to an .npmrc file in your repository for the scope of the build. This enables npm task runners like gulp and Grunt to authenticate with private registries.
ms.date: 11/17/2023
monikerRange: "<=azure-pipelines"
---

# npmAuthenticate@0 - npm authenticate (for task runners) v0 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to provide `npm` credentials to an `.npmrc` file in your repository for the scope of the build. This enables `npm`, as well as `npm` task runners like gulp and Grunt, to authenticate with private registries.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020"

```yaml
# npm authenticate (for task runners) v0
# Don't use this task if you're also using the npm task. Provides npm credentials to an .npmrc file in your repository for the scope of the build. This enables npm task runners like gulp and Grunt to authenticate with private registries.
- task: npmAuthenticate@0
  inputs:
    workingFile: # string. Required. .npmrc file to authenticate. 
    #customEndpoint: # string. Credentials for registries outside this organization/collection.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2019.1"

```yaml
# npm Authenticate (for task runners) v0
# Don't use this task if you're also using the npm task. Provides npm credentials to an .npmrc file in your repository for the scope of the build. This enables npm task runners like Gulp and Grunt to authenticate with private registries.
- task: npmAuthenticate@0
  inputs:
    #workingFile: # string. .npmrc file to authenticate. 
    #customEndpoint: # string. Credentials for registries outside this account/collection.
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

<!-- :::item name="workingFile"::: -->
:::moniker range=">=azure-pipelines-2020"

**`workingFile`** - **.npmrc file to authenticate**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The path to the `.npmrc` file that specifies the registries you want to work with. Select the file, not the folder, such as `/packages/mypackage.npmrc`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="<=azure-pipelines-2019.1"

**`workingFile`** - **.npmrc file to authenticate**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The path to the `.npmrc` file that specifies the registries you want to work with. Select the file, not the folder, such as `/packages/mypackage.npmrc`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customEndpoint"::: -->
:::moniker range=">=azure-pipelines-2020"

**`customEndpoint`** - **Credentials for registries outside this organization/collection**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The comma-separated list of [npm service connection](/azure/devops/pipelines/library/service-endpoints) names for registries outside this organization or collection. The specified `.npmrc` file must contain registry entries corresponding to the service connections. If you only need registries in this organization or collection, leave this blank. The build's credentials are used automatically.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="<=azure-pipelines-2019.1"

**`customEndpoint`** - **Credentials for registries outside this account/collection**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The comma-separated list of [npm service connection](/azure/devops/pipelines/library/service-endpoints) names for registries outside this organization or collection. The specified `.npmrc` file must contain registry entries corresponding to the service connections. If you only need registries in this organization or collection, leave this blank. The build's credentials are used automatically.
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

Use this task to provide `npm` credentials to an `.npmrc` file in your repository for the scope of the build. This enables `npm`, as well as `npm` task runners like gulp and Grunt, to authenticate with private registries.

* [How does this task work?](#how-does-this-task-work)
* [When in my pipeline should I run this task?](#when-in-my-pipeline-should-i-run-this-task)
* [I have multiple npm projects. Do I need to run this task for each .npmrc file?](#i-have-multiple-npm-projects-do-i-need-to-run-this-task-for-each-npmrc-file)
* [My agent is behind a web proxy. Will `npmAuthenticate` set up `npm/gulp/Grunt` to use my proxy?](#my-agent-is-behind-a-web-proxy-will-npmauthenticate-set-up-npmgulpgrunt-to-use-my-proxy)
* [My Pipeline needs to access a feed in a different project](#my-pipeline-needs-to-access-a-feed-in-a-different-project)

### How does this task work?

This task searches the specified `.npmrc` file for registry entries, then appends authentication details for the discovered registries to the end of the file. For all registries in the current organization/collection, the build's credentials are used. For  registries in a different organization or hosted by a third-party, the registry URIs will be compared to the URIs of the [npm service connections](/azure/devops/pipelines/library/service-endpoints#npm-service-connection) specified by the `customEndpoint` input, and the corresponding credentials will be used. The `.npmrc` file will be reverted to its original state at the end of the pipeline execution.

### When in my pipeline should I run this task?

This task must run before you use `npm`, or an `npm` task runner, to install or push packages to an authenticated npm repository such as Azure Artifacts. There are no other ordering requirements.

### I have multiple npm projects. Do I need to run this task for each .npmrc file?

This task will only add authentication details to one `.npmrc` file at a time. If you need authentication for multiple `.npmrc` files, you can run the task multiple times, once for each `.npmrc` file. Alternately, consider creating an `.npmrc` file that specifies all registries used by your projects, running `npmAuthenticate` on this `.npmrc` file, and then setting an environment variable to designate this `.npmrc` file as the npm per-user configuration file.

```YAML
- task: npmAuthenticate@0
  inputs:
    workingFile: $(agent.tempdirectory)/.npmrc
- script: echo ##vso[task.setvariable variable=NPM_CONFIG_USERCONFIG]$(agent.tempdirectory)/.npmrc
- script: npm ci
  workingDirectory: project1
- script: npm ci
  workingDirectory: project2
```

### My agent is behind a web proxy. Will `npmAuthenticate` set up `npm/gulp/Grunt` to use my proxy?

The answer is no. While this task itself will work behind a web proxy [your agent has been configured to use](/azure/devops/pipelines/agents/proxy), it does not configure `npm` or `npm` task runners to use the proxy.

To do so, you can either:

* Set the environment variables `http_proxy`/`https_proxy` and optionally `no_proxy` to your proxy settings. See [npm config](https://docs.npmjs.com/misc/config#https-proxy) for details. Note that these are commonly used variables which other non-`npm` tools (e.g. curl) may also use.

* Add the proxy settings to the [npm configuration](https://docs.npmjs.com/misc/config), either manually, by using [npm config set](https://docs.npmjs.com/cli/config#set), or by setting [environment variables](https://docs.npmjs.com/misc/config#environment-variables) prefixed with `NPM_CONFIG_`.
  >**Caution:**  
  >`npm` task runners may not be compatible with all methods of proxy configuration supported by `npm`.

* Specify the proxy with a command line flag when calling `npm`.
  ```YAML
  - script: npm ci --https-proxy $(agent.proxyurl)
  ```

If your proxy requires authentication, you may need to add an additional build step to construct an authenticated proxy URI.

```YAML
- script: node -e "let u = url.parse(`$(agent.proxyurl)`); u.auth = `$(agent.proxyusername):$(agent.proxypassword)`; console.log(`##vso[task.setvariable variable=proxyAuthUri;issecret=true]` + url.format(u))"
- script: npm publish --https-proxy $(proxyAuthUri)
```

### My Pipeline needs to access a feed in a different project

If the pipeline is running in a different project than the project hosting the feed, you must set up the other project to grant read/write access to the build service. See [Package permissions in Azure Pipelines](/azure/devops/artifacts/feeds/feed-permissions#pipelines-permissions) for more details.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

* [Restore `npm` packages for your project from a registry within your organization](#restore-npm-packages-for-your-project-from-a-registry-within-your-organization)
* [Restore and publish `npm` packages outside your organization](#restore-and-publish-npm-packages-outside-your-organization)
* [npmrc](#npmrc)
* [npm](#npm)

### Restore `npm` packages for your project from a registry within your organization

If the only authenticated registries you use are Azure Artifacts registries in your organization, you only need to specify the path to an `.npmrc` file to the `npmAuthenticate` task.

#### `.npmrc`
```
registry=https://pkgs.dev.azure.com/{organization}/_packaging/{feed}/npm/registry/
always-auth=true
```

#### `npm`
```YAML
- task: npmAuthenticate@0
  inputs:
    workingFile: .npmrc
- script: npm ci
# ...
- script: npm publish
```

### Restore and publish `npm` packages outside your organization

If your `.npmrc` contains Azure Artifacts registries from a different organization or use a third-party authenticated package repository, you'll need to set up [npm service connections](/azure/devops/pipelines/library/service-endpoints#npm-service-connection) and specify them in the `customEndpoint` input.
Registries within your Azure Artifacts organization will also be automatically authenticated.

#### `.npmrc`

```
registry=https://pkgs.dev.azure.com/{organization}/{project}/_packaging/{feed}/npm/registry/
@{scope}:registry=https://pkgs.dev.azure.com/{otherorganization}/_packaging/{feed}/npm/registry/
@{otherscope}:registry=https://{thirdPartyRepository}/npm/registry/
always-auth=true
```

The registry URL pointing to an Azure Artifacts feed may or may not contain the project. An URL for a project scoped feed must contain the project, and the URL for an organization scoped feed must not contain the project. Learn more about [project scoped feeds](/azure/devops/artifacts/feeds/project-scoped-feeds).

#### npm
```YAML
- task: npmAuthenticate@0
  inputs:
    workingFile: .npmrc
    customEndpoint: OtherOrganizationNpmConnection, ThirdPartyRepositoryNpmConnection
- script: npm ci
# ...
- script: npm publish -registry https://pkgs.dev.azure.com/{otherorganization}/_packaging/{feed}/npm/registry/
```
`OtherOrganizationNpmConnection` and `ThirdPartyRepositoryNpmConnection` are the names of [npm service connections](/azure/devops/pipelines/library/service-endpoints#npm-service-connection) that have been configured and authorized for use in your pipeline, and have URLs that match those in the specified `.npmrc` file.
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
| Agent version |  2.115.0 or greater |
| Task category | Package |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->