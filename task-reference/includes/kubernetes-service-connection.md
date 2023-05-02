---
ms.topic: include
ms.date: 04/19/2023
---

#### Kubernetes Service Connection considerations when accessing AKS

You can create a Kubernetes service connection with any of the following options.

* KubeConfig
* Service Account
* Azure Subscription

:::image type="content" source="../media/kubernetes-service-connection-authentication-method.png" alt-text="Screenshot of choosing a Kubernetes service connection authentication method.":::

When selecting the **Azure Subscription** option, Kubernetes needs to be accessible to Azure DevOps at service connection configuration time. There may be various reasons a service connection cannot be created, for example you created a private cluster or the cluster has local accounts disabled. In these cases, Azure DevOps is unable to connect to your cluster at service connection configuration time and you will observe the dialog to be stuck at **Loading namespaces**.

:::image type="content" source="../media/loading-namespaces.png" alt-text="Screenshot of choosing a Kubernetes service connection authentication dialog stuck at loading namespaces.":::

Starting with Kubernetes 1.24, long-lived tokens are [no longer created by default](https://github.com/kubernetes/kubernetes/blob/master/CHANGELOG/CHANGELOG-1.24.md#urgent-upgrade-notes). Kubernetes recommends not to use long-lived tokens. As a result, tasks using a Kubernetes service connection created using the Azure Subscription option do not have access to the permanent token required to authenticate and can’t access your Kubernetes cluster. This also results in the **Loading namespaces** dialog to be frozen.

#### Use the Azure Resource Manager Service Connection to access AKS

For AKS customers, the Azure Resource Manager service connection type provides the best method to connect to a private cluster, or a cluster that has local accounts disabled. This method is not dependent on cluster connectivity at the time you create a service connection. Access to AKS is deferred to pipeline runtime, which has the following advantages:

* Access to a (private) AKS cluster can be performed from a self-hosted or scale set agent with line of sight to the cluster.
* A token is created for every task that uses an Azure Resource Manager service connection. This ensures you are connecting to Kubernetes with a short-lived token, which is the [Kubernetes recommendation](https://kubernetes.io/docs/concepts/configuration/secret/#service-account-token-secrets).
* AKS can be accessed even when local accounts are disabled.

#### Service connection FAQ

##### I receive the following error message: Could not find any secret associated with the service account. What is happening?

You are using the Kubernetes service connection with Azure Subscription option. We are updating this method to create long-lived tokens. This is expected to be available mid-May. However, it is recommended to start using the Azure service connection type and not o use long-lived tokens as per [Kubernetes guidance](https://kubernetes.io/docs/concepts/configuration/secret/#service-account-token-secrets).

##### I'm using AKS and don't want to change anything, can I continue to use tasks with the Kubernetes service connection?

We are updating this method to create long-lived tokens. This is expected to be available mid-May. However, please be aware that this approach is against [Kubernetes guidance](https://kubernetes.io/docs/concepts/configuration/secret/#service-account-token-secrets).

##### I'm using the Kubernetes tasks and Kubernetes service connection but not AKS. Should I be concerned?

You tasks will continue to work as before.

##### Will the Kubernetes service connection type be removed?

Our Kubernetes tasks work with any Kubernetes cluster, regardless where they are running. The Kubernetes service connection will continue to exist.

##### I’m an AKS customer and everything is running fine, should I act?

There is no need to change anything. If you are using the Kubernetes service connection and selected Azure Subscription during creation, you should be aware of the [Kubernetes guidance on using long-lived tokens](https://kubernetes.io/docs/concepts/configuration/secret/#service-account-token-secrets).

##### I'm creating a Kubernetes Environment, and have no option to use service connections

In case you can’t access your AKS during environment creation time, you can use an empty environment and set the `connectionType` input to an Azure Resource Manager service connection.

##### I have AKS configured with Azure Active Directory RBAC, and my pipeline doesn’t work. Will these updates resolve that?

Accessing Kubernetes when AAD RBAC is enabled is unrelated to token creation. To prevent an interactive prompt, we will support [kubelogin](/azure/aks/managed-aad#non-interactive-sign-in-with-kubelogin) in a future update.
