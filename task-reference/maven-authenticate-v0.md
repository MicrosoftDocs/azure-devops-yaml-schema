---
title: MavenAuthenticate@0 - Maven Authenticate v0 task
description: Provides credentials for Azure Artifacts feeds and external maven repositories.
ms.date: 07/31/2023
monikerRange: ">=azure-pipelines-2020"
---

# MavenAuthenticate@0 - Maven Authenticate v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
Use this task to provide credentials for Azure Artifacts feeds and external Maven repositories.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020"

```yaml
# Maven Authenticate v0
# Provides credentials for Azure Artifacts feeds and external maven repositories.
- task: MavenAuthenticate@0
  inputs:
    #artifactsFeeds: # string. Feeds. 
    #mavenServiceConnections: # string. Credentials for repositories outside this organization/collection.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="artifactsFeeds"::: -->
:::moniker range=">=azure-pipelines-2020"

**`artifactsFeeds`** - **Feeds**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a comma-separated list of Azure Artifacts feed names to authenticate with Maven. If you only need authentication for external Maven repositories, leave this field blank.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="mavenServiceConnections"::: -->
:::moniker range=">=azure-pipelines-2020"

**`mavenServiceConnections`** - **Credentials for repositories outside this organization/collection**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a comma-separated list of [Maven service connection](/azure/devops/pipelines/library/service-endpoints) names from external organizations to authenticate with Maven. If you only need authentication for Azure Artifacts feeds, leave this field blank.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2020"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

Specifies the credentials for Azure Artifacts feeds and external Maven repositories in the current user's `settings.xml` file.

* [Where is the `settings.xml` file containing the authenticated repositories located?](#where-is-the-settingsxml-file-containing-the-authenticated-repositories-located)
* [We use the `mvn -s` switch to specify our own `settings.xml` file. How do we authenticate Azure Artifacts feeds there?](#we-use-the-mvn--s-switch-to-specify-our-own-settingsxml-file-how-do-we-authenticate-azure-artifacts-feeds-there)
* [My Pipeline needs to access a feed in a different project](#my-pipeline-needs-to-access-a-feed-in-a-different-project)

### Where is the `settings.xml` file containing the authenticated repositories located?

The Maven Authenticate task searches for the `settings.xml` file in the current user's home directory. For Linux and Mac, the path is `$HOME/.m2/settings.xml`. For Windows, the path is `%USERPROFILE%\.m2\settings.xml`. If the `settings.xml` file doesn't exist, a new one will be created at that path.

### We use the `mvn -s` switch to specify our own `settings.xml` file. How do we authenticate Azure Artifacts feeds there?

The Maven Authenticate task doesn't have access to the custom `settings.xml` file that's specified by using an `-s` switch. To add Azure Artifacts authentication to your custom `settings.xml`, add a server element inside your `settings.xml` file:

```XML
<server>
  <id>feedName</id> <!-- Set this to the id of the <repository> element inside your pom.xml file. -->
  <username>AzureDevOps</username>
  <password>${env.SYSTEM_ACCESSTOKEN}</password>
</server>
```

The access token variable can be set in your pipelines using these [instructions](/azure/devops/pipelines/build/variables#systemaccesstoken).

### My Pipeline needs to access a feed in a different project

If the pipeline is running in a different project than the project hosting the feed, you must set up the other project to grant read/write access to the build service. See [Package permissions in Azure Pipelines](/azure/devops/artifacts/feeds/feed-permissions#pipelines-permissions) for more details.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

* [Authenticate Maven feeds inside your organization](#authenticate-maven-feeds-inside-your-organization)
* [Authenticate Maven feeds outside your organization](#authenticate-maven-feeds-outside-your-organization)

### Authenticate Maven feeds inside your organization

In this example, we authenticate two Azure Artifacts feeds within our organization.

#### Task definition

```YAML
- task: MavenAuthenticate@0
  displayName: 'Maven Authenticate'
  inputs:
    artifactsFeeds: MyFeedInOrg1,MyFeedInOrg2
```

The `MavenAuthenticate` task updates the `settings.xml` file present in the agent user's .m2 directory located at `{user.home}/.m2/settings.xml` to add two entries inside the `<servers>` element.

#### settings.xml

```XML
<servers>
  <server>
    <id>MyFeedInOrg1</id>
    <username>AzureDevOps</username>
    <password>****</password>
  </server>
  <server>
    <id>MyFeedInOrg2</id>
    <username>AzureDevOps</username>
    <password>****</password>
  </server>
</servers>
```

To correctly authenticate the task, set the repositories in your project's `pom.xml` to the same `<id>` as the name specified in the task for Maven.

#### pom.xml

Project scoped feed
```XML
 <repository>
   <id>MyFeedInOrg1</id>
   <url>https://pkgs.dev.azure.com/OrganzationName/ProjectName/_packaging/MyProjectScopedFeed1/Maven/v1</url>
   <releases>
     <enabled>true</enabled>
   </releases>
   <snapshots>
     <enabled>true</enabled>
   </snapshots>
 </repository>
```

Organization scoped feed
```XML
 <repository>
   <id>MyFeedInOrg1</id>
   <url>https://pkgs.dev.azure.com/OrganzationName/_packaging/MyOrgScopedFeed1/Maven/v1</url>
   <releases>
     <enabled>true</enabled>
   </releases>
   <snapshots>
     <enabled>true</enabled>
   </snapshots>
 </repository>
```

The Artifacts feed URL may or may not contain the project. A URL for a project-scoped feed must contain the project, and a URL for an organization-scoped feed must not contain the project. Learn more about [project-scoped feeds](/azure/devops/artifacts/feeds/project-scoped-feeds).

### Authenticate Maven feeds outside your organization

In this example, we authenticate two external Maven repositories.

#### Task definition

```YAML
- task: MavenAuthenticate@0
  displayName: 'Maven Authenticate'
  inputs:
    MavenServiceConnections: central,MavenOrg
```

The `MavenAuthenticate` task updates the `settings.xml` file present in the agent users' .m2 directory located at `{user.home}/.m2/settings.xml` to add two entries inside the `<servers>` element.

#### settings.xml

```XML
<servers>
  <server>
    <id>central</id>
    <username>centralUsername</username>
    <password>****</password>
  </server>
  <server>
    <id>MavenOrg</id>
    <username>mavenOrgUsername</username>
    <password>****</password>
  </server>
</servers>
```

To correctly authenticate the task, set the repositories in your project's `pom.xml` to the same `<id>` as the name specified in the task for Maven.

#### pom.xml

```XML
<repository>
  <id>central</id>
  <url>https://repo1.maven.org/maven2/</url>
  <releases>
    <enabled>true</enabled>
  </releases>
  <snapshots>
    <enabled>true</enabled>
  </snapshots>
</repository>
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range="=azure-pipelines"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.144.0 or greater |
| Task category | Package |

:::moniker-end

:::moniker range=">=azure-pipelines-2020 <=azure-pipelines-2022"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.120.0 or greater |
| Task category | Package |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
