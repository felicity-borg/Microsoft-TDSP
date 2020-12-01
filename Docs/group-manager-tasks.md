
# Team Data Science Process group manager tasks

This page outlines the tasks that a *group manager* is expected to complete for a dtaa science organization. The group manager manages the entire data scinece unit in an enterprise. A data science unit may have several teams, each of which is working on many data science projects in distinct business verticals. The group manager's objective is to establish a collaborative group environment that standardizes on the Team Data Science Process (TDSP). For an outline of all the personnel roles and associated tasks handled by a data science team standardizing on the TDSP, see [Team Data Science Process: roles and tasks](roles-tasks.md).

The following diagram shows the six main group manager setup tasks. Group managers may delegate their tasks to surrogates, but the tasks associated with the role don't change.

![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/group-manager-tasks/tdsp-group-manager.png)


1. Set up an **Azure DevOps organization** for the group.

2. Create the default **GroupCommon project** in the Azure DevOps organization.

3. Create the **GroupProjectTemplate** repository in Azure Repos.

4. Create the **GroupUtilities** repository in Azure Repos.

5. Import the contents of the Microsoft TDSP team's 
**ProjectTemplate** and **Utilities** repositories into the group common repositories. 

6. Set up **membership** and **permissions** for team members to access the group.

Each of the above steps are described in further detail below.


## Create an organization and project in Azure DevOps

1. Go to [visualstudio.microsoft.com](https://visualstudio.microsoft.com/), select **Sign in** at upper right, and sign into your Microsoft account.

![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/group-manager-tasks/signinvs.png)

If you don't have a Microsoft account, select **Sign up now**, create a Microsoft account, and sign in using this account. If your organization has a Visual Studio subscription, sign in with the credentials for that subscription.
		
2. After you sign in, at upper right on the Azure DevOps page, select **Create new orgnaization**. 
		
![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/group-manager-tasks/create-organization.png)

3. If you're prompted to agree to the Terms of Service, Privacy Statement, and Code of Conduct, select **Continue**.

4. In the signup dialog, name your Azure DevOps organization and accept the host region assignment, or drop down and select a different region. Then select **Continue**.

5. Under **Create a project to get started**, enter *GroupCommon*, and then select **Create project**.

![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/group-manager-tasks/create-project.png)

The **GroupCommon** project **Summary** page opens. The page URL is *https://<servername>/<organization-name>/GroupCommon*.

![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/group-manager-tasks/project-summary.png)


## Set up the group common repositories.

Azure Repos hosts the following types of repositories for your group:

**Group common repositories**: General-purpose repositories that multiple teams within a data science unit can adopt for many data science projects.
**Team repositories**: Repositories for specific teams within a data science unit. These repositories are specific for a team's needs, and may be used for multiple projects within that team, but are not general enough to be used across multiple teams within a data science unit.
**Project repositories**: Repositories for specific projects. Such repositories may not be general enough for multiple projects within a team, or for other teams in a data science unit.

To set up the group common repositories in your project, you:

* Rename the default **GroupCommon** repository to **GroupProjectTemplate**.

* Create a new **GroupUtilities** repository.


### Rename the default project repository to GroupProjectTemplate
To rename the default **GroupCommon** project repository to **GroupProjectTemplate**:

1. On the **GroupCommon** project **Summary** page, select **Repos**. This action takes you to the default **GroupCommon** repository of the GroupCommon project, which is currently empty.

2. At the top of the page, drop down the arrow next to **GroupCommon** and select **Manage repositories**.

![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/group-manager-tasks/rename-groupcommon-repo-3.png)

3. On the **Project Settings** page, select the ... next to **GroupCommon**, and then select **Rename repository**.

![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/group-manager-tasks/rename-groupcommon-repo-4.png)


4. In the Rename the **GroupCommon repository** popup, enter *GroupProjectTemplate*, and then select **Rename**.

![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/group-manager-tasks/rename-groupcommon-repo-6.png)


### Create the GroupUtilities repository

To create the **GroupUtilities** repository:

1. On the **GroupCommon** project **Summary** page, select **Repos**.

2. At the top of the page, drop down the arrow next to **GroupProjectTemplate** and select **New repository**.

![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/group-manager-tasks/create-grouputilities-repo-1.png)

3. In the **Create a new repository** dialog, select **Git** as the **Type**, enter **GroupUtilities** as the Repository name, and then select **Create**.

![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/group-manager-tasks/create-grouputilities-repo-2.png)

4. On the **Project Settings** page, select **Repositories** under **Repos** in the left navigation to see the two group repositories: **GroupProjectTemplate** and **GroupUtilities**.

![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/group-manager-tasks/two-repositories.png)

## Import the Microsoft TDSP team repositories
Hereyou import the contents of the **ProjectTemplate** and **Utilities** repositories managed by the Microsoft TDSP team into your **GroupProjectTemplate** and **GroupUtilities** repositories.

To import the TDSP team repositories:

1. From the **GroupCommon** project home page, select **Repos** in the left navigation. The default **GroupProjectTemplate** repo opens.

2. On the **GroupProjectTemplate is empty** page, select **Import**.

![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/group-manager-tasks/import-repo.png)

3. In the **Import a Git repository** dialog, select **Git** as the **Source type**, and enter *https://github.com/Azure/Azure-TDSP-ProjectTemplate.git* for the **Clone URL**. Then select **Import**. The contents of the Microsoft TDSP team ProjectTemplate repository are imported into your GroupProjectTemplate repository.

![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/group-manager-tasks/import-repo-2.png)

4. At the top of the **Repos** page, drop down and select the **GroupUtilities** repository.

Each of your two group repositories now contains all the files, except those in the .git directory, from the Microsoft TDSP team's corresponding repository.	


## Customize the contents of the group repositories
If you want to customize the contents of your group repositories to meet the specific needs of your group, you can do that now. You can modify the files, change the directory structure, or add files that your group has developed or that are helpful for your group.


### Make changes in Azure Repos

To customize repository contents:

1. On the **GroupCommon** project **Summary** page, select **Repos**.

2. At the top of the page, select the repository you want to customize.

3. In the repo directory structure, navigate to the folder or file you want to change.

* To create new folders or files, select the arrow next to **New**.

![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/group-manager-tasks/new-file.png)

* To upload files, select **Upload file(s)**.

![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/group-manager-tasks/upload-files.png)

* To edit existing files, navigate to the file and then select **Edit**.

![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/group-manager-tasks/edit-file.png)


4. After adding or editing files, select **Commit**.

![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/group-manager-tasks/commit.png)


## Make changes using your local machine or Azure ML Service

If you want to make changes using your local machine or Azure Ml Service and push the changes up to the group repositories, make sure you have the prerequisites for working with Git and Azure ML:

* An Azure ubscription, if you want to create a Azure ML workspace

* Git installed on your machine—see the [Platforms and tools appendix](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/platforms-and-tools#appendix).


For more information on how to integrate your Azure ML notebooks with your Git repo click [here](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/gitIntegration.md).

## Add group members and configure permissions

To add members to the group:

1. In Azure DevOps, from the **GroupCommon** project home page, select **Project settings** from the left navigation.

2. From the **Project Settings** left navigation, select **Teams**, then on the **Teams** page, select the **GroupCommon Team**.

3. On the **Team Profile** page, select **Add**.

![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/group-manager-tasks/add-to-team.png)

4. In the **Add users and groups** dialog, search for and select members to add to the group, and then select **Save changes**.

![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/group-manager-tasks/add-users.png)

To configure permissions for members:

1. From the **Project Settings** left navigation, select **Permissions**.

2. On the **Permissions** page, select the group you want to add members to.

3. On the page for that group, select **Members**, and then select **Add**.

4. In the **Invite members** popup, search for and select members to add to the group, and then select **Save**.

![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/group-manager-tasks/grant-permissions.png)

## Next Steps:

Here are links to detailed descriptions of the other roles and tasks in the Team Data Science Process:

* [Team Lead tasks for a data science team](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/team-lead-tasks.md)
* [Project Lead tasks for a data science team](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/project-lead-tasks.md)
* [Project Individual Contributor tasks for a data science team](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/project-ic-tasks.md)



