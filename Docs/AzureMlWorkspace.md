# Create and manage Azure Machine Learning Workspaces

## Create a workspace

1. Sign in to the [Azure portal](https://portal.azure.com/) by using the credentials for your Azure subscription.


2. In the upper-left corner of Azure portal, select + **Create a resource**.

![](https://docs.microsoft.com/en-us/azure/machine-learning/media/how-to-manage-workspace/create-workspace.gif)

3. Use the search bar to find **Machine Learning**.

4. Select **Machine Learning**.

5. In the **Machine Learning** pane, select **Create** to begin.

6. Provide the following information to configure your new workspace:

| **Field** | **Description** |
| --------  |  ---------------|
| Workspace name | Enter a unique name that identifies your workspace. In this example, we use docs-ws. Names must be unique across the resource group. Use a name that's easy to recall and to differentiate from workspaces created by others. The workspace name is case-insensitive.|
| Subscription | Select the Azure subscription that you want to use. |
| Resource group | Use an existing resource group in your subscription or enter a name to create a new resource group. A resource group holds related resources for an Azure solution. In this example, we use **docs-aml**. You need *contributor* or *owner* role to use an existing resource group. For more information about access, see [Manage access to an Azure Machine Learning workspace](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-assign-roles). |
| Region | Select the Azure region closest to your users and the data resources to create your workspace. |
| Stroag account | The default storage account for the workspace. By default, a new one is created. |
| Key Vault | The Azure Key Vault used by the workspace. By default, a new one is created. |
| Application Insights | The application insights instance for the workspace. By default, a new one is created. |
| Container Registry | The Azure Container Registry for the workspace. By default, a new one is *not* initially created for the workspace. Instead, it is created once you need it when creating a Docker image during training or deployment. | 

![](https://docs.microsoft.com/en-us/azure/machine-learning/media/how-to-manage-workspace/create-workspace-form.png)

7. When you're finished configuring the workspace, select **Review + Create**. Optionally, use the Networking and Advanced sections to configure more settings for the workspace.

8. Review the settings and make any additional chnages or corrections. When you're satisfied with the settings, select **Create**. 

**Note**—It can take several minutes to create your workspace in the cloud

When the process is finished, a deployment succes message appears. 

9. To view the new workspace, select **Go to resource**.


## To Find a workspace
See a list of all the workspaces you can use.

1. Sign in to the [Azure portal](https://portal.azure.com/).
2. In the top search field, type **Machine Learning**.
3. Select **Machine Learning** 

![](https://docs.microsoft.com/en-us/azure/machine-learning/media/how-to-manage-workspace/find-workspaces.png)

4. Look through the list of workspaces found. You can filter based on subscription, resource groups, and locations.
5. Select a workspace to display its properties. 

## Delete a workspace
When you no longer need a workspace, delete it.

![](https://docs.microsoft.com/en-us/azure/machine-learning/media/how-to-manage-workspace/delete-workspace.png)

## Clean up resources

If you don't plan to use the resources that you created, delete them so you don't incur any charges:

1. In the Azure portal, select **Resource groups** on the far left. 
2. From the list, select the resource group that you created.
3. Select **Delete resource group**. <br>
![](https://docs.microsoft.com/en-us/azure/includes/media/aml-delete-resource-group/delete-resources.png)

4. Enter the resource group name. Then select **Delete**. 

