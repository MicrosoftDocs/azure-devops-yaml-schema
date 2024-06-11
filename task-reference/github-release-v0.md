---
title: GitHubRelease@0 - GitHub Release v0 task
description: Create, edit, or delete a GitHub release (task version 0).
ms.date: 06/11/2024
monikerRange: ">=azure-pipelines-2019.1"
---

# GitHubRelease@0 - GitHub Release v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Use this task to create, edit, or delete a GitHub release.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020"

```yaml
# GitHub Release v0
# Create, edit, or delete a GitHub release.
- task: GitHubRelease@0
  inputs:
    gitHubConnection: # string. Required. GitHub connection (OAuth or PAT). 
    repositoryName: '$(Build.Repository.Name)' # string. Required. Repository. Default: $(Build.Repository.Name).
    action: 'create' # 'create' | 'edit' | 'delete'. Required. Action. Default: create.
    #target: '$(Build.SourceVersion)' # string. Required when action = create || action = edit. Target. Default: $(Build.SourceVersion).
    tagSource: 'auto' # 'auto' | 'manual'. Required when action = create. Tag source. Default: auto.
    #tagPattern: # string. Optional. Use when tagSource = auto. Tag Pattern. 
    #tag: # string. Required when action = edit || action = delete || tagSource = manual. Tag. 
    #title: # string. Optional. Use when action = create || action = edit. Release title. 
    #releaseNotesSource: 'file' # 'file' | 'input'. Optional. Use when action = create || action = edit. Release notes source. Default: file.
    #releaseNotesFile: # string. Optional. Use when releaseNotesSource = file. Release notes file path. 
    #releaseNotes: # string. Optional. Use when releaseNotesSource = input. Release notes. 
    #assets: '$(Build.ArtifactStagingDirectory)/*' # string. Optional. Use when action = create || action = edit. Assets. Default: $(Build.ArtifactStagingDirectory)/*.
    #assetUploadMode: 'delete' # 'delete' | 'replace'. Optional. Use when action = edit. Asset upload mode. Default: delete.
    #isDraft: false # boolean. Optional. Use when action = create || action = edit. Draft release. Default: false.
    #isPreRelease: false # boolean. Optional. Use when action = create || action = edit. Pre-release. Default: false.
    #addChangeLog: true # boolean. Optional. Use when action = create || action = edit. Add changelog. Default: true.
  # Changelog configuration
    changeLogCompareToRelease: 'lastFullRelease' # 'lastFullRelease' | 'lastNonDraftRelease' | 'lastNonDraftReleaseByTag'. Required when addChangeLog = true. Compare to. Default: lastFullRelease.
    #changeLogCompareToReleaseTag: # string. Required when changeLogCompareToRelease = lastNonDraftReleaseByTag && addChangeLog = true. Release Tag. 
    changeLogType: 'commitBased' # 'commitBased' | 'issueBased'. Required when addChangeLog = true. Changelog type. Default: commitBased.
    #changeLogLabels: '[{ "label" : "bug", "displayName" : "Bugs", "state" : "closed" }]' # string. Optional. Use when changeLogType = issueBased && addChangeLog = true. Categories. Default: [{ "label" : "bug", "displayName" : "Bugs", "state" : "closed" }].
```

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

```yaml
# GitHub Release v0
# Create, edit, or delete a GitHub release.
- task: GitHubRelease@0
  inputs:
    gitHubConnection: # string. Required. GitHub connection (OAuth or PAT). 
    repositoryName: '$(Build.Repository.Name)' # string. Required. Repository. Default: $(Build.Repository.Name).
    action: 'create' # 'create' | 'edit' | 'delete'. Required. Action. Default: create.
    #target: '$(Build.SourceVersion)' # string. Required when action = create || action = edit. Target. Default: $(Build.SourceVersion).
    tagSource: 'auto' # 'auto' | 'manual'. Required when action = create. Tag source. Default: auto.
    #tag: # string. Required when action = edit || action = delete || tagSource = manual. Tag. 
    #title: # string. Optional. Use when action = create || action = edit. Release title. 
    #releaseNotesSource: 'file' # 'file' | 'input'. Optional. Use when action = create || action = edit. Release notes source. Default: file.
    #releaseNotesFile: # string. Optional. Use when releaseNotesSource = file. Release notes file path. 
    #releaseNotes: # string. Optional. Use when releaseNotesSource = input. Release notes. 
    #assets: '$(Build.ArtifactStagingDirectory)/*' # string. Optional. Use when action = create || action = edit. Assets. Default: $(Build.ArtifactStagingDirectory)/*.
    #assetUploadMode: 'delete' # 'delete' | 'replace'. Optional. Use when action = edit. Asset upload mode. Default: delete.
    #isDraft: false # boolean. Optional. Use when action = create || action = edit. Draft release. Default: false.
    #isPreRelease: false # boolean. Optional. Use when action = create || action = edit. Pre-release. Default: false.
    #addChangeLog: true # boolean. Optional. Use when action = create || action = edit. Add changelog. Default: true.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="gitHubConnection"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`gitHubConnection`** - **GitHub connection (OAuth or PAT)**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of the GitHub service connection to use to connect to the GitHub repository. The connection must be based on a GitHub user's OAuth or a GitHub personal access token. For more information about service connections, see [Manage service connections](/azure/devops/pipelines/library/service-endpoints#github-service-connection).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="repositoryName"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`repositoryName`** - **Repository**<br>
`string`. Required. Default value: `$(Build.Repository.Name)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of the GitHub repository where you will create, edit, or delete the GitHub release.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="action"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`action`** - **Action**<br>
`string`. Required. Allowed values: `create`, `edit`, `delete`. Default value: `create`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the type of release operation to perform. This task can create, edit, or delete a GitHub release.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="target"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`target`** - **Target**<br>
`string`. Required when `action = create || action = edit`. Default value: `$(Build.SourceVersion)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the commit SHA you want to use to create the GitHub release, for example `48b11d8d6e92a22e3e9563a3f643699c16fd6e27`. You can also use a variable, like `$(myCommitSHA)`, in this field.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="tagSource"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`tagSource`** - **Tag source**<br>
`string`. Required when `action = create`. Allowed values: `auto` (Git tag), `manual` (User specified tag). Default value: `auto`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the tag you want to use for release creation. The `auto` (Git tag) option automatically uses the tag that is associated with the Git commit. Use the `manual` (User specified tag) option to manually provide a tag.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="tagPattern"::: -->
:::moniker range=">=azure-pipelines-2020"

**`tagPattern`** - **Tag Pattern**<br>
`string`. Optional. Use when `tagSource = auto`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the Git tag pattern by using regex, for example `release-v1.*`. GitHub release will be created only for commits that have matching Git tag.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="tag"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`tag`** - **Tag**<br>
`string`. Required when `action = edit || action = delete || tagSource = manual`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the tag you want to use when you create, edit, or delete a release. You can also use a variable, like `$(myTagName)`, in this field.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="title"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`title`** - **Release title**<br>
`string`. Optional. Use when `action = create || action = edit`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the title of the GitHub release. If left empty, the tag will be used as the release title.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="releaseNotesSource"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`releaseNotesSource`** - **Release notes source**<br>
`string`. Optional. Use when `action = create || action = edit`. Allowed values: `file` (Release notes file), `input` (Inline release notes). Default value: `file`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the description of the GitHub release. Use the `file` (Release notes file) option to use file contents as release notes. Use the `input` (Inline release notes) option to manually enter release notes.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="releaseNotesFile"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`releaseNotesFile`** - **Release notes file path**<br>
`string`. Optional. Use when `releaseNotesSource = file`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the file that contains the release notes.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="releaseNotes"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`releaseNotes`** - **Release notes**<br>
`string`. Optional. Use when `releaseNotesSource = input`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the release notes. Markdown is supported.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="assets"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`assets`** - **Assets**<br>
`string`. Optional. Use when `action = create || action = edit`. Default value: `$(Build.ArtifactStagingDirectory)/*`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the files you want to upload as assets of the release. You can use wildcard characters to specify multiple files. For example, use `$(Build.ArtifactStagingDirectory)/*.zip` for build pipelines or use `$(System.DefaultWorkingDirectory)/*.zip` for release pipelines. 

You can also specify multiple patterns, one per line. By default, all files in the `$(Build.ArtifactStagingDirectory)` directory will be uploaded. For more information about the list of pre-defined variables that are available, see [build variables](https://aka.ms/AA4449z) and [release variables](https://aka.ms/AA43wws).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="assetUploadMode"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`assetUploadMode`** - **Asset upload mode**<br>
`string`. Optional. Use when `action = edit`. Allowed values: `delete` (Delete exisiting assets), `replace` (Replace existing assets). Default value: `delete`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the asset upload mode you want to use. Use the `delete` (Delete existing assets) option to first delete any existing assets in the release and then upload all assets. Use the `replace` (Replace existing assets) option to replace any assets that have the same name.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="isDraft"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`isDraft`** - **Draft release**<br>
`boolean`. Optional. Use when `action = create || action = edit`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Indicates whether you want to save the release as a draft (unpublished). If `false`, the release will be published.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="isPreRelease"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`isPreRelease`** - **Pre-release**<br>
`boolean`. Optional. Use when `action = create || action = edit`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Indicates whether you want to mark the release as a pre-release.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="addChangeLog"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`addChangeLog`** - **Add changelog**<br>
`boolean`. Optional. Use when `action = create || action = edit`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies if you want to include a changelog. If set to `true`, a list of changes (commits and issues) between the current release and the last published release will be generated and appended to the release notes.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="changeLogCompareToRelease"::: -->
:::moniker range=">=azure-pipelines-2020"

**`changeLogCompareToRelease`** - **Compare to**<br>
`string`. Required when `addChangeLog = true`. Allowed values: `lastFullRelease` (Last full release), `lastNonDraftRelease` (Last non-draft release), `lastNonDraftReleaseByTag` (Last non-draft release by tag). Default value: `lastFullRelease`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Indicates which release to compare with to generate the changelog: 

* `lastFullRelease` (Last full release): Compares the current release with the most recent non-draft release that is not marked as pre-release.
* `lastNonDraftRelease` (Last non-draft release): Compares the current release with the most recent non-draft release.
* `lastNonDraftReleaseByTag` (Last non-draft release by tag): Compares the current release with the last non-draft release matching the specified tag. You can also specify a regex instead of an exact tag.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="changeLogCompareToReleaseTag"::: -->
:::moniker range=">=azure-pipelines-2020"

**`changeLogCompareToReleaseTag`** - **Release Tag**<br>
`string`. Required when `changeLogCompareToRelease = lastNonDraftReleaseByTag && addChangeLog = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the regex for the release tag. A release matching this tag will be used as the base for changelog computation.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="changeLogType"::: -->
:::moniker range=">=azure-pipelines-2020"

**`changeLogType`** - **Changelog type**<br>
`string`. Required when `addChangeLog = true`. Allowed values: `commitBased` (Commit based), `issueBased` (Issue based). Default value: `commitBased`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the changelog type. A changelog can be commit-based or issue-based. A commit-based changelog lists all commits included in a release. An issue-based changelog lists all the issues or pull requests (PRs) included in the release.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="changeLogLabels"::: -->
:::moniker range=">=azure-pipelines-2020"

**`changeLogLabels`** - **Categories**<br>
`string`. Optional. Use when `changeLogType = issueBased && addChangeLog = true`. Default value: `[{ "label" : "bug", "displayName" : "Bugs", "state" : "closed" }]`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Categorizes changes based on the label associated with the issue or PR. For a label, you can mention the display name for the category and the state of issue. Examples of labels include: `"[{ "label" : "bug", "displayName" : "Bugs", "state" : "closed" }]"`. In cases where a change has multiple labels on it, the first specified label takes priority. Leave this field empty to see a flat list of issues or PRs.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2019.1"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
:::moniker range=">=azure-pipelines-2020"

## Remarks

There is a newer version of this task available at [GitHubRelease@1](./github-release-v1.md).

:::moniker-end
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range=">=azure-pipelines-2019.1"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.0.0 or greater |
| Task category | Utility |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
