---
ms.topic: include
ms.date: 06/02/2023
---

> [!NOTE]
> Azure Pipelines [enforces time limits based on your project type and parralel job settings](/azure/devops/pipelines/licensing/concurrent-jobs#how-much-do-parallel-jobs-cost), and timeouts can also be specified at the [job level](../jobs-job.md). If either of these timeout intervals elapses before your step completes, the running job (including your step) is terminated, even if the step is configured with a longer timeout interval.
