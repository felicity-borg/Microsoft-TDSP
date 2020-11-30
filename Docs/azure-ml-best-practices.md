# Describe Azure ML Service best practices

**Contents**: 
1. [Manage and increase quotas for resources with Azure Machine Learning](#Quotas-1)
2. [Understand workspace administration best practices](#WSAdmin-2)
3. [Security best practices](#security-3)
3. [Tools and integration best practices](#Integ-4)


##  1. <a name='Quotas-1'></a>Manage and increase quotas for resources with Azure Machine Learning

Azure uses limits and quotas to prevent budget overruns due to fraud, and to honor Azure capacity constraints. Consider these limits as you scale for production workloads.
This section will cover:
* Default limits on Azure resources related to [Azure Machine Learning](https://docs.microsoft.com/en-gb/azure/machine-learning/overview-what-is-azure-ml).
* Creating workspace-level quotas.
* Viewing your quotas and limits.
* Requesting quota increases.
* Private endpoint and DNS quotas.

Along with managing quotas, you can learn how to [plan and manage costs for Azure Machine Learning](https://docs.microsoft.com/en-gb/azure/machine-learning/concept-plan-manage-cost).

#### Special Considerations:

* A quota is a credit limit, not a capacity guarantee. If you have large-scale capacity needs, [contact Azure support to increase your quota](https://docs.microsoft.com/en-gb/azure/machine-learning/how-to-manage-quotas#request-quota-increases).

* A quota is shared across all the services in your subscriptions, including Azure Machine Learning. Calculate usage across all services when you're evaluating capacity.

Azure Machine Learning compute is an exception. It has a separate quota from the core compute quota.

* Default limits vary by offer category type, such as free trial, pay-as-you-go, and virtual machine (VM) series (such as Dv2, F, and G).

#### Default resource quotas
In this section, you learn about the default and maximum quota limits for the following resources:

* Virtual machines
* Azure Machine Learning compute
* Azure Machine Learning pipelines
* Azure Container Instances
* Azure Storage

#### Virtual Machines

Each Azure subscription has a limit on the number of virtual machines across all services. Virtual machine cores have a regional total limit and a regional limit per size series. Both limits are separately enforced.

For example, consider a subscription with a US East total VM core limit of 30, an A series core limit of 30, and a D series core limit of 30. This subscription would be allowed to deploy 30 A1 VMs, or 30 D1 VMs, or a combination of the two that does not exceed a total of 30 cores.

You can't raise limits for virtual machines above the values shown in the following table.

| **Resource** | **Limit** |
| ------------ | ----------- |
| Subscriptions per Azure Active Directory tenant |	Unlimited |
| [Coadministrators](https://docs.microsoft.com/en-gb/azure/cost-management-billing/manage/add-change-subscription-administrator) per subscription	| Unlimited |
| [Resource groups](https://docs.microsoft.com/en-gb/azure/azure-resource-manager/management/overview) per subscription	| 980 |
| Azure Resource Manager API request size |	4,194,304 bytes |
| Tags per subscription<sup>1</sup> 50 |
| Unique tag calculations per subscription<sup>1</sup>	| 10,000 |
| [Subscription-level deployments](https://docs.microsoft.com/en-gb/azure/azure-resource-manager/templates/deploy-to-subscription) per location |	8002<sup>2</sup> |

---

<sup>1</sup>  You can apply up to 50 tags directly to a subscription. However, the subscription can contain an unlimited number of tags that are applied to resource groups and resources within the subscription. The number of tags per resource or resource group is limited to 50. Resource Manager returns a [list of unique tag name and values](https://docs.microsoft.com/en-us/rest/api/resources/tags) in the subscription only when the number of tags is 10,000 or less. You still can find a resource by tag when the number exceeds 10,000.

<sup>2</sup> If you reach the limit of 800 deployments, delete deployments that are no longer needed from the history. To delete subscription-level deployments, use [Remove-AzDeployment](https://docs.microsoft.com/en-us/powershell/module/az.resources/Remove-AzDeployment) or [az deployment sub delete](https://docs.microsoft.com/en-us/cli/azure/deployment/sub#az-deployment-sub-delete).

##### Azure Machine Learning Compute 

[Azure Machine Learning compute](https://docs.microsoft.com/en-gb/azure/machine-learning/concept-compute-target#azure-machine-learning-compute-managed) has a default quota limit on both the number of cores and the number of unique compute resources allowed per region in a subscription. This quota is separate from the VM core quota from the previous section.

[Request a quota increase](https://docs.microsoft.com/en-gb/azure/machine-learning/how-to-manage-quotas#request-quota-increases) to raise the limits in this section up to the maximum limit shown in the table.

Available resources:

* **Dedicated cores per region** have a default limit of 24 to 300, depending on your subscription offer type. You can increase the number of dedicated cores per subscription for each VM family. Specialized VM families like NCv2, NCv3, or ND series start with a default of zero cores.

* **Low-priority cores per region** have a default limit of 100 to 3,000, depending on your subscription offer type. The number of low-priority cores per subscription can be increased and is a single value across VM families.

* **Clusters per region**  have a default limit of 200. These are shared between a training cluster and a compute instance. (A compute instance is considered a single-node cluster for quota purposes.)

The following table shows additional limits that you can't exceed.

| **Resource** | **Maximum Limit** |
| ------------ | ----------------- |
| Workspaces per resource group |	800 |
| Nodes in a single Azure Machine Learning compute (AmlCompute) resource |	100 nodes |
| GPU MPI processes per node	|  1-4 |
| GPU workers per node	| 1-4 |
| Job lifetime| 	21 days <sup>1</sup> |
| Job lifetime on a low-priority node | 	7 days <sup>2</sup> |
| Parameter servers per node |	1 |

<sup>1</sup> Maximum lifetime is the duration between when a run starts and when it finishes. Completed runs persist indefinitely. Data for runs not completed within the maximum lifetime is not accessible. <sup>2</sup> Jobs on a low-priority node can be preempted whenever there's a capacity constraint. We recommend that you implement checkpoints in your job.

##### Azure Machone Learning Pipelines

[Azure Machine Learning Pipelines](https://docs.microsoft.com/en-gb/azure/machine-learning/concept-ml-pipelines) have the following limits. 

|  **Resource ** | **Limit** |
| -------------- | --------- |
| Step in a pipeline | 30,000 |
| Workspaces per resource group | 800 |

##### Container Instances
For more information, see [Container Instances limits](https://docs.microsoft.com/en-gb/azure/azure-resource-manager/management/azure-subscription-service-limits#container-instances-limits).

##### Storage
Azure Storage has a limit of 250 storage accounts per region, per subscription. This limit includes both Standard and Premium storage accounts.

To increase the limit, make a request through [Azure Support](https://ms.portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest/). 

###### Workspace-level quotas

Workspace-level quotas
Use workspace-level quotas to manage Azure Machine Learning compute target allocation between multiple [workspaces](https://docs.microsoft.com/en-gb/azure/machine-learning/concept-workspace) in the same subscription.

By default, all workspaces share the same quota as the subscription-level quota for VM families. However, you can set a maximum quota for individual VM families on workspaces in a subscription. This lets you share capacity and avoid resource contention issues.

1. Go to any workspace in your subscription.
2. In the left pane, select **Usages + quotas**.
3. Select the **Configure quotas** tab to view the quotas.
4. Expand a VM family.
5. Set a quota limit on any workspace listed under that VM family.
You can't set a negative value or a value higher than the subscription-level quota.

![](https://docs.microsoft.com/en-gb/azure/machine-learning/media/how-to-manage-quotas/azure-machine-learning-workspace-quota.png)

**Note** You need a subscription-level permissions to set a quote at the workspace level. 

###### View your usage and quotas
To view your quota for various Azure resources like virtual machines, storage, or network, use the Azure portal:

1. On the left pane, select **All services** and then select **Subscriptions** under the **General** category.

2. From the list of subscriptions, select the subscription whose quota you're looking for.

3. Select **Usage + quotas** to view your current quota limits and usage. Use the filters to select the provider and locations.

You manage the Azure Machine Learning compute quota on your subscription separately from other Azure quotas:

1. Go to your **Azure Machine Learning** workspace in the Azure portal.

2. On the left pane, in the **Support + troubleshooting** section, select *Usage + quotas** to view your current quota limits and usage.

3. Select a subscription to view the quota limits. Filter to the region you're interested in.

4. You can switch between a subscription-level view and a workspace-level view.

##### Request quota increases

To raise the limit or quota above the default limit, open an [online customer support request](https://ms.portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest/) at no charge.

You can't raise limits above the maximum values shown in the preceding tables. If there's no maximum limit, you can't adjust the limit for the resource.

When you're requesting a quota increase, select the service that you have in mind. For example, select Azure Machine Learning, Container Instances, or Storage. For Azure Machine Learning compute, you can select the **Request Quota** button while viewing the quota in the preceding steps.

##### Private endpoint and private DNS quota increases
There are limits on the number of private endpoints and private DNS zones that you can create in a subscription.

Azure Machine Learning creates resources in your (customer) subscription, but some scenarios create resources in a Microsoft-owned subscription.

In the following scenarios, you might need to request a quota allowance in the Microsoft-owned subscription:

* Azure Private Link enabled workspace with a customer-managed key (CMK)
* Azure Container Registry for the workspace behind your virtual network
* Attaching a Private Link enabled Azure Kubernetes Service cluster to your workspace

To request an allowance for these scenarios, use the following steps:

1. [Create an Azure support request](https://docs.microsoft.com/en-gb/azure/azure-portal/supportability/how-to-create-azure-support-request#create-a-support-request) and select the following options in the **Basics** section:

| **Field** | **Selection** |
| --------- | ------------- |
| Issue type | **Techical** | 
| Service | **My services**. Then select **Machine Learning** in the drop-down list. |
| Problem type | **Workspace Configuration and Security** |
| Problem subtype | **Private Endpoint and Private DNS Zone allowance request** |

2. In the **Details** section, use the **Description** field to provide the Azure region and the scenario that you plan to use. If you need to request quote increases for multiple subscriptions list the sunscriptions IDs in this field. 

3. Select **Create* to create the request. 

![](https://docs.microsoft.com/en-gb/azure/machine-learning/media/how-to-manage-quotas/quota-increase-private-endpoint.png)

### Additional considerations
* Create different workspaces by different department / business team / data tier, and per environment (development, staging, and production) - across relevant Azure subscriptions
* Define workspace level tags which propagate to initially provisioned resources in managed resource group (Tags could also propagate from parent resource group)
* Use Azure [Resource Manager templates templates](https://github.com/Azure/azure-quickstart-templates( to have a more managed way of deploying the workspaces - whether via CLI, PowerShell, or some SDK
* Create relevant groups of users - using [Group REST API](https://docs.azuredatabricks.net/api/latest/groups.html) or by using [Azure Active Directory Group Sync with SCIM](https://docs.azuredatabricks.net/administration-guide/admin-settings/scim/index.html)/

##  2. <a name='WSAdmin-2'></a>Understand workspace administration best practices

### Azure subscription limits

Key [Azure limits](https://docs.microsoft.com/en-us/azure/azure-subscription-service-limits) are:

* Storage accounts per region per subscription: **250**
* Maximum egress for general-purpose v2 and Blob storage accounts (all regions): **50 Gbps**
* Virtual Machines (VMs) per subscription per region: **25,000**
* Resource groups per subscription: **980**
* These limits are at this point in time and might change going forward. Some of them can also be increased if needed. For more help in understanding the impact of these limits or options of increasing them, please contact Microsoft or Databricks technical architects.

### Networking
When creating a workspace the default network configuration is to use a **Public endpoint**, which is accessible on the public internet. To limit access to your workspace to an Azure Virtual Network you have created, you can instead select **Private endpoint** (preview) as the **Connectivity method**, and then use **+ Add** to configure the endpoint.
![](https://docs.microsoft.com/en-us/azure/machine-learning/media/how-to-manage-workspace/select-private-endpoint.png)

On the **Create private endpoint** form, set the location, name, and virtual network to use. If you'd like to use the endpoint with a Private DNS Zone, select **Integrate with private DNS** zone and select the zone using the **Private DNS Zone field**. Select **OK** to create the endpoint.
![](https://docs.microsoft.com/en-us/azure/machine-learning/media/how-to-manage-workspace/create-private-endpoint.png)

When you are finished configuring networking, you can select **Review + Create**, or advance to the optional **Advanced** configuration.
**Important**: Using a private endpoint with Azure Machine Learning workspace is currently in public preview. This preview is provided without a service level agreement, and it's not recommended for production workloads. Certain features might not be supported or might have constrained capabilities. For more information, see Supplemental Terms of Use for Microsoft Azure Previews.

### Multiple workspaces with private endpoint
When you create a private endpoint, a new Private DNS Zone named **privatelink.api.azureml.ms** is created. This contains a link to the virtual network. If you create multiple workspaces with private endpoints in the same resource group, only the virtual network for the first private endpoint may be added to the DNS zone. To add entries for the virtual networks used by the additional workspaces/private endpoints, use the following steps:

1. In the Azure portal, select the resource group that contains the workspace. Then select the Private DNS Zone resource named **privatelink.api.azureml.ms**
2. In the **Settings**, select **Virtual network links**.
3. Select **Add**. From the **Add virtual network link** page, provide a unique **Link name**, and then select the **Virtual network** to be added. Select **OK** to add the network link.
For more information, see [Azure Private Endpoint DNS configuration](https://docs.microsoft.com/en-us/azure/private-link/private-endpoint-dns).

### Vulnerability scanning
Azure Security Center provides unified security management and advanced threat protection across hybrid cloud workloads. You should allow Azure Security Center to scan your resources and follow its recommendations. For more, see [Azure Container Registry image scanning by Security Center](https://docs.microsoft.com/en-us/azure/security-center/defender-for-container-registries-introduction) and [Azure Kubernetes Services integration with Security Center](https://docs.microsoft.com/en-us/azure/security-center/defender-for-kubernetes-introduction).

### Download a configuration file
If you will be creating a [compute instance](https://docs.microsoft.com/en-us/azure/machine-learning/tutorial-1st-experiment-sdk-setup#azure), skip this step. The compute instance has already created a copy of this file for you.
![](https://docs.microsoft.com/en-us/azure/machine-learning/media/how-to-manage-workspace/configure.png)

Place the file into the directory structure with your Python scripts or Jupyter Notebooks. It can be in the same directory, a subdirectory named *.azureml*, or in a parent directory. When you create a compute instance, this file is added to the correct directory on the VM for you.

##  3. <a name='security-3'></a>Security best practices

Security and infrastructure configuration go hand-in-hand. When you set up your Azure ML service workspace(s) and related services, you need to make sure that security considerations do not take a back seat during the architecture design. 

### Always hide secrets in a key vault
It is a significant security risk to expose sensitive data such as access credentials openly in Notebooks or other places such as job configs, initialization scripts, etc. You should always use a vault to securely store and access them. Unless you are using azure Databricks (ADB) workspace in which case you can use ADB's internal Key Vault for this purpose, use Azure's Key Vault (AKV) service.

If using Azure Key Vault, create separate AKV-backed secret scopes and corresponding AKVs to store credentials pertaining to different data stores. This will help prevent users from accessing credentials that they might not have access to. Since access controls are applicable to the entire secret scope, users with access to the scope will see all secrets for the AKV associated with that scope.

More Information can be found in the following urls:

[Create an Azure Key Vault-backed secret scope](https://docs.azuredatabricks.net/user-guide/secrets/secret-scopes.html)

[Example of using a secret in a notebook](https://docs.azuredatabricks.net/user-guide/secrets/example-secret-workflow.html)

[Best practices for creating secret scopes](https://docs.azuredatabricks.net/user-guide/secrets/secret-acl.html)

### Additional considerations
Configure encryption-at-rest for [Blob Storage](https://docs.microsoft.com/en-us/azure/storage/common/storage-service-encryption-customer-managed-keys) and [ADLS](https://docs.microsoft.com/en-us/azure/data-lake-store/data-lake-store-encryption), preferably by using customer-managed keys in Azure Key Vault.

## 4. <a name = 'Integ-4'></a>Tools and integration best practices

* Use [Azure Data Factory](https://docs.azuredatabricks.net/user-guide/dev-tools/data-pipelines.html#azure-data-factory) to orchestrate pipelines / workflows (or something like [Airflow](https://docs.azuredatabricks.net/user-guide/dev-tools/data-pipelines.html#apache-airflow)).
* Sync notebooks with [Azure DevOps](https://docs.azuredatabricks.net/user-guide/notebooks/azure-devops-services-version-control.html) for seamless version control. For detailed information refer to his [page](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/agile-development.md).
