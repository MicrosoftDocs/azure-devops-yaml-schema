---
applyTo: '**'
---

- @azure Rule - Use Azure Best Practices: When generating code for Azure, running terminal commands for Azure, or performing operations related to Azure, invoke your `get_azure_best_practices` tool if available.

# Azure DevOps YAML Schema & Task Reference — Override Instructions

When working in this repository, apply the following overrides to any doc-kit
agent, skill, or prompt. These rules take precedence over Foundry-specific
defaults shipped with doc-kit.

---

## 1. Product Identity

| Default (Foundry)                  | Override (Azure DevOps)                                           |
|------------------------------------|-------------------------------------------------------------------|
| Product name: "Azure AI Foundry"   | **Azure Pipelines** (YAML schema), **Azure DevOps** (tasks)      |
| Docs base URL                      | `https://learn.microsoft.com/azure/devops/pipelines/yaml-schema/` (schema), `https://learn.microsoft.com/azure/devops/pipelines/tasks/reference/` (tasks) |
| REST API reference                 | `https://learn.microsoft.com/rest/api/azure/devops/`              |
| Feedback mechanism                 | Azure DevOps Developer Community (`developercommunity.visualstudio.com`) |
| Tasks source repo                  | `https://github.com/microsoft/azure-pipelines-tasks`              |
| YAML validation schema source      | `https://github.com/Microsoft/azure-pipelines-vscode`             |
| `ms.service`                       | `azure-devops-pipelines`                                          |
| `ms.topic`                         | `reference` (set globally in `docfx.json`)                        |

## 2. Repository & Content Structure

| Aspect               | Value                                                              |
|----------------------|--------------------------------------------------------------------|
| Docs repo            | `MicrosoftDocs/azure-devops-yaml-schema` (this repo)               |
| YAML schema articles | `content/` — one `.md` file per YAML schema definition             |
| Task reference articles | `task-reference/` — one `.md` file per task version             |
| TOC                  | `content/TOC.yml`                                                  |
| Breadcrumb           | `content/breadcrumb/toc.yml`                                       |
| Includes             | `content/includes/`                                                |
| docfx config         | `content/docfx.json`                                               |
| Build output dest    | `azure-devops-yaml-schema`                                         |
| Auto-publish         | `auto-publish.yml` (pipeline definition at repo root)              |

## 3. Auto-Generated vs. Editable Content

**Critical:** Most article content in this repo is auto-generated from task
metadata and YAML schema definitions. Contributions must only touch
**editable content regions**.

### Editable content tags

Editable regions are delimited by HTML comments:

```html
<!-- :::editable-content name="{section}"::: -->
Your editable text here.
<!-- :::editable-content-end::: -->
```

Valid `name` values include: `description`, `helpMarkDown`, `remarks`,
`examples`, `seeAlso`.

### Rules

- **DO** edit text inside `<!-- :::editable-content ...::: -->` … `<!-- :::editable-content-end::: -->` tags.
- **DO NOT** edit any text outside of `editable-content` tags — those sections are overwritten by the automated generation process.
- **DO NOT** create new task articles or new YAML schema definition articles manually — they are auto-generated when Azure DevOps sprints deploy.
- **DO NOT** modify auto-generated YAML syntax blocks, input tables, allowed values, defaults, or aliases.
- Monikers may appear inside `editable-content` tags for sections like remarks, examples, and see also.

### Editable sections in task articles

| Section              | Editable? | Notes                                     |
|---------------------|-----------|-------------------------------------------|
| Task description     | Yes       | Inside `editable-content` tags            |
| Input descriptions   | Yes       | Inside `editable-content` tags            |
| Output descriptions  | Yes       | Inside `editable-content` tags            |
| Remarks              | Yes       | Full section within `editable-content`    |
| Examples             | Yes       | Full section within `editable-content`    |
| See also             | Yes       | Full section within `editable-content`    |
| YAML syntax          | **No**    | Auto-generated from task source code      |
| Input metadata       | **No**    | Aliases, defaults, allowed values         |

## 4. Versioning & Moniker Rules

- YAML schema articles use moniker range `<=azure-pipelines`.
- The `docfx.json` group range is `>= azure-pipelines-2022 <= azure-pipelines`.
- Valid monikers: `azure-pipelines` (current cloud), `azure-pipelines-2022`, `azure-pipelines-2022.1`, `azure-pipelines-2022.2`, `azure-pipelines-2020`, `azure-pipelines-2020.1`, `azure-pipelines-2019`, `azure-pipelines-2019.1`.
- Every `:::moniker range="..."` must have a matching `:::moniker-end`.
- Default to `<=azure-pipelines` for new editable content unless the feature is version-specific.
- **DISCARD** content scoped only to `tfs-2018` or earlier unless explicitly requested.

## 5. Metadata Defaults

Global metadata is set in `content/docfx.json` and does **not** need to be
repeated in every article. The globals include:

```yaml
ms.service: azure-devops-pipelines
ms.topic: reference
author: steved0x
ms.author: sdanie
feedback_product_url: https://developercommunity.visualstudio.com/spaces/21/index.html
```

Per-article front matter should include at minimum:

```yaml
---
title: "{definition name} definition"
description: "{Brief description}"
ms.date: {MM/DD/YYYY}
monikerRange: "<=azure-pipelines"
author: steved0x
ms.author: sdanie
---
```

`ms.date` should reflect the date of the last meaningful content change.

## 6. File Naming Conventions

### YAML schema definitions (`content/`)

- File names use the dot-separated definition path with dots replaced by hyphens.
- Examples: `pipeline.md`, `jobs-job.md`, `resources-pipelines-pipeline-trigger.md`, `steps-task.md`.

### Task reference (`task-reference/`)

- File names use the task name (lowercase, hyphenated) with version suffix.
- Examples: `azure-cli-v3.md`, `bash-v3.md`, `advanced-security-codeql-init-v1.md`.

## 7. Terminology & Style

| Instead of …                          | Use …                                                         |
|---------------------------------------|---------------------------------------------------------------|
| "ADO" or "AZDO"                       | "Azure DevOps" (full name in published content)               |
| "YAML pipeline schema"               | "YAML schema reference for Azure Pipelines"                   |
| "task docs"                           | "task reference" or "Azure Pipelines tasks reference"         |
| "org"                                 | "organization"                                                |
| "agent" (AI agent)                    | "agent" (pipeline agent) — clarify context if ambiguous       |

- Follow the [Microsoft Writing Style Guide](https://learn.microsoft.com/style-guide/welcome/).
- Use **sentence-case** for headings.
- Use **bold** for UI elements and YAML property names in prose.
- Capitalize service names: **Azure Pipelines**, **Azure DevOps**.
- Do NOT abbreviate "Azure DevOps" to "ADO" in published documentation.

## 8. YAML Code Examples

When writing examples in editable-content sections:

- Use fenced code blocks with `yaml` language identifier.
- Show realistic, minimal examples that demonstrate the documented property or task.
- Include comments to explain non-obvious values.
- For task examples, show the task with its most common inputs:

```yaml
steps:
- task: TaskName@Version
  displayName: 'Descriptive name'
  inputs:
    inputName: value
```

- For schema definition examples, show the property in its parent context:

```yaml
jobs:
- job: Build
  pool:
    vmImage: ubuntu-latest
  steps:
  - script: echo Hello
```

- Always validate that YAML examples are syntactically correct.
- Reference the task version that matches the article (e.g., `Bash@3` for `bash-v3.md`).

## 9. Cross-Reference Links

- Link to other schema definitions using relative paths: `[jobs](jobs.md)`, `[pool](pool.md)`.
- Link to the main Azure DevOps docs using absolute Learn paths: `[Customize your pipeline](/azure/devops/pipelines/customize-pipeline)`.
- Link to the task index: `[Azure Pipelines tasks index](/azure/devops/pipelines/tasks/reference)`.
- Link to REST APIs: `https://learn.microsoft.com/rest/api/azure/devops/`.
- For task issues, link to: `https://github.com/microsoft/azure-pipelines-tasks`.

## 10. Common Article Patterns

### Remarks section (schema definitions)

```markdown
<!-- :::editable-content name="remarks"::: -->
## Remarks

Brief explanation of the definition, when to use it, and key considerations.

### Example scenario

Description and YAML example.
<!-- :::editable-content-end::: -->
```

### See also section

```markdown
<!-- :::editable-content name="seeAlso"::: -->
## See also

- [Related definition](related-definition.md)
- [Azure Pipelines concept](/azure/devops/pipelines/concept-topic)
<!-- :::editable-content-end::: -->
```

### Task remarks

```markdown
<!-- :::editable-content name="remarks"::: -->
## Remarks

Explain what the task does, common use cases, prerequisites, and gotchas.
Include authentication requirements and agent compatibility notes.

### Open source

This task is open source on [GitHub](https://github.com/microsoft/azure-pipelines-tasks).
Feedback and contributions are welcome.
<!-- :::editable-content-end::: -->
```

## 11. Pull Request Guidelines

- PRs that edit text **outside** of `editable-content` tags will be closed.
- PRs that add **new task articles** or **new schema definition articles** will be closed (these are auto-generated).
- PRs should target editable content only: descriptions, remarks, examples, and see also sections.
- Verify `monikerRange` in front matter matches the moniker blocks in the article body.
- Run a local `docfx build` if possible to catch broken links and syntax errors.