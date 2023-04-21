---
ms.topic: include
ms.date: 04/19/2023
---

#### Kubernetes Service Connection limitations when accessing AKS

You can create a Kubernetes Service Connection with any of the following options.

* KubeConfig
* Service Account
* Azure Subscription

When selecting the **Azure Subscription** option, Kubernetes needs to be accessible to Azure DevOps at Service Connection configuration time. There may be various reasons Service Connection cannot be created, for example you created a private cluster or the cluster has local accounts disabled. In these cases, Azure DevOps is unable to connect to your cluster at Service Connection configuration time and you will observe the dialog to be stuck at **Loading namespaces**.

Starting with Kubernetes 1.24, long-lived tokens are [no longer created by default](https://github.com/kubernetes/kubernetes/blob/master/CHANGELOG/CHANGELOG-1.24.md#urgent-upgrade-notes). Kubernetes recommends not to use long-lived tokens. As a result, tasks using a Kubernetes Service Connection created using the Azure Subscription option do not have access to the permanent token required to authenticate and can’t access your Kubernetes cluster. This also results in the **Loading namespaces** dialog to be frozen.

#### Use the Azure Resource Manager Service Connection to access AKS

For AKS customers, the Azure Resource Manager Service Connection type provides the best method to connect to a private cluster, or a cluster that has local accounts disabled. This method is not dependent on cluster connectivity at the time you create a Service Connection. Access to AKS is deferred to pipeline runtime, which has the following advantages:

* Access to a (private) AKS cluster can be performed from a Self-hosted or Scale set agent with line of sight to the cluster.
* A token is created for every task that uses Azure Resource Manager Service Connection. This ensures you are connecting to Kubernetes with a short-lived token, which is the [Kubernetes recommendation](https://kubernetes.io/docs/concepts/configuration/secret/#service-account-token-secrets).
* AKS can be accessed even when local accounts are disabled.

#### Service connection FAQ

##### I receive the following error message: Could not find any secret associated with the service account. What is happening?

You are using the Kubernetes Service Connection with Azure Subscription option. We are updating this method to create long-lived tokens. This is expected to be available mid-May. However, it is recommended to start using the Azure Service Connection type and don’t use long-lived tokens as per [Kubernetes guidance](https://kubernetes.io/docs/concepts/configuration/secret/#service-account-token-secrets).

##### I'm using AKS and don't want to change anything, can I continue to use tasks with the Kubernetes Service Connection as before?

We are updating this method to create long-lived tokens. This is expected to be available mid-May. However, please be aware that this approach is against [Kubernetes guidance](https://kubernetes.io/docs/concepts/configuration/secret/#service-account-token-secrets).

##### I'm using the Kubernetes tasks and Kubernetes Service Connection but not AKS. Should I be concerned?

You tasks will continue to work as before.

##### Will the Kubernetes Service Connection type be removed?

Our Kubernetes tasks work with any Kubernetes cluster, regardless where they are running. The Kubernetes Service Connection will continue to exist.

##### I’m an AKS customer and everything is running fine, should I act?

There is no need to change anything. If you are using the Kubernetes Service Connection and selected Azure Subscription during creation, you should be aware of the [Kubernetes guidance on using long-lived tokens](https://kubernetes.io/docs/concepts/configuration/secret/#service-account-token-secrets).

##### I'm creating a Kubernetes Environment, and have no option to use Service Connections

In case you can’t access AKS during environment creation time, you can use an empty environment and set the connectionType property of the above mentioned tasks to an Azure Resource Manager Service Connection.

##### I have AKS configured with Azure Active Directory RBAC, and my pipeline doesn’t work. Will these updates resolve that?

Accessing Kubernetes when AAD RBAC is enabled is unrelated to token creation. To prevent an interactive prompt, we will support [kubelogin](/azure/aks/managed-aad#non-interactive-sign-in-with-kubelogin) in a future update.
