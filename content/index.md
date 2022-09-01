---
title: YAML schema reference
description: Azure Pipelines YAML schema reference
ms.date: 02/03/2022
monikerRange: ">= azure-pipelines-2019"
---

# YAML schema reference for Azure Pipelines

The YAML schema reference for Azure Pipelines is a detailed reference for YAML pipelines that lists all supported YAML syntax and their available options.

To create a YAML pipeline, start with the [pipeline](pipeline.md#remarks) definition. For more information about building YAML pipelines, see [Customize your pipeline](/azure/devops/pipelines/customize-pipeline).

The YAML schema reference does not cover tasks. For more information about tasks, see the [Azure Pipelines tasks index](/azure/devops/pipelines/tasks/reference).

## YAML schema definition index

[!INCLUDE [definition-index](includes/definition-index.md)]

## YAML schema documentation conventions

The YAML schema reference is a detailed reference guide to Azure Pipelines YAML pipelines.
It includes a catalog of all supported YAML capabilities and the available options.

Here are the syntax conventions used in the YAML schema reference.

* To the left of `:` is a literal keyword used in pipeline definitions.
* To the right of `:` is a data type.
  The data type can be a primitive type like **string** or a reference to a rich structure defined elsewhere in this reference.
* The notation `[` *datatype* `]` indicates an array of the mentioned definition type.
  For instance, `[ string ]` is an array of strings.
* The notation `{` *datatype* `:` *datatype* `}` indicates a mapping of one data type to another.
  For instance, `{ string: string }` is a mapping of strings to strings.
* The symbol `|` indicates there are multiple data types available for the keyword.
  For instance, `job | template` means either a job definition or a template reference is allowed.

## See also

This reference covers the schema of an Azure Pipelines YAML file.
To learn the basics of YAML, see [Learn YAML in Y Minutes](https://learnxinyminutes.com/docs/yaml/).
Azure Pipelines doesn't support all YAML features.
Unsupported features include anchors, complex keys, and sets.
Also, unlike standard YAML, Azure Pipelines depends on seeing `stage`, `job`, `task`, or a task shortcut like `script` as the first key in a mapping.
