---
ms.topic: include
ms.date: 04/19/2023
---

### Kubernetes tasks and service connections

Azure DevOps supports Kubernetes deployments with a number of included tasks:

* [AzureFunctionOnKubernetes v1](../azure-function-on-kubernetes-v1.md)
* [HelmDeploy v0](../helm-deploy-v0.md)
* [Kubernetes v1](../kubernetes-v1.md)
* [KubernetesManifest v1](../kubernetes-manifest-v1.md)

These tasks can be configured to target a Kubernetes cluster in a number of ways, using the `connectionType` property.

| Connection type | Description |
|-----------------|-------------|
| Azure Resource Manager | Lets you select an AKS instance. Does not access Kubernetes cluster at Service Connection configuration time. |
| Kubernetes Service Connection | Allows you to provide a KubeConfig file, specify a Service Account, or import an AKS instance with the **Azure Subscription** option. The latter requires Kubernetes cluster access at Service Connection configuration time. |
| None | Use a pre-created Kubernetes configuration stored locally. |

#### Kubernetes Service Connection limitations when accessing AKS

You can create a Kubernetes Service Connection with any of the following options.

* KubeConfig
* Service Account
* Azure Subscription

When selecting the **Azure Subscription** option, Kubernetes needs to be accessible to Azure DevOps at Service Connection configuration time. There may be various reasons Service Connection cannot be created, for example you created a private cluster or the cluster has local accounts disabled. In these cases, Azure DevOps is unable to connect to your cluster at Service Connection configuration time and you will observe the dialog to be stuck at **Loading namespaces**.

Starting with Kubernetes 1.24, long-lived tokens are [no longer created by default](https://github.com/kubernetes/kubernetes/blob/master/CHANGELOG/CHANGELOG-1.24.md#urgent-upgrade-notes). Kubernetes recommends not to use long-lived tokens. As a result, tasks using a Kubernetes Service Connection created using the Azure Subscription option do not have access to the permanent token required to authenticate and can’t access your Kubernetes cluster. This also results in the **Loading namespaces** dialog to be frozen.