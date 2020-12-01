
# Tasks for the team lead on a Team Data Science Process team

This article describes the tasks that a team lead completes for their data science team. The team lead's objective is to establish a collaborative team environment that standardizes on the Team Data Science Process (TDSP). The TDSP is designed to help improve collaboration and team learning.

The TDSP is an agile, iterative data science methodology to efficiently deliver predictive analytics solutions and intelligent applications. The process details the best practices and structures from Microsoft and the industry. The goal is successful implementation of data science initiatives and fully realizing the benefits of their analytics programs.

A team lead manages a team consisting of several data scientists in the data science unit of an enterprise. Depending on the data science unit's size and structure, the group manager and the team lead might be the same person, or they could delegate their tasks to surrogates. But the tasks themselves do not change.

The following diagram shows the workflow for the tasks the team lead completes to set up a team environment:

![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/team-lead-tasks/team-leads-1-creating-teams.png)

1. Create a **team project** in the group's organization in Azure DevOps.

2. Rename the default team repository to **TeamUtilities**.

3. Create a new **TeamTemplate** repository in the team project.

4 Import the contents of the group's **GroupUtilities** and **GroupProjectTemplate** repositories into the **TeamUtilities** and **TeamTemplate** repositories.

5. Set up **security control** by adding team members and configuring their permissions.

6. If required, create team data and analytics resources:

* Add team-specific utilities to the **TeamUtilities** repository.
* Create **Azure file storage** to store data assets that can be useful for the entire team.

These steps are covered in more detail below

# Prerequisites
It is assumed that the following resources and permissions have been set up by your group manager:

* The Azure DevOps **organization** for your data unit

* **GroupProjectTemplate** and **GroupUtilities** repositories, populated with the contents of the Microsoft TDSP team's **ProjectTemplate** and **Utilities** repositories
Permissions on your organization account for you to create projects and repositories for your team

To be able to clone repositories and modify their content on your local machine or Azure ML notebooks you need the following:

* An Azure subscription.

* A Git installed on your machine will be useful if you want to also run code on an IDE on your local machine. 

## Create a team project and repositories
In this section, you create the following resources in your group's Azure DevOps organization:

* The **MyTeam** project in Azure DevOps

* The **TeamTemplate** repository

* The **TeamUtilities** repository

The names specified for the repositories and directories in this tutorial assume that you want to establish a separate project for your own team within your larger data science organization. However, the entire group can choose to work under a single project created by the group manager or organization administrator. Then, all the data science teams create repositories under this single project. This scenario might be valid for:

* A small data science group that doesn't have multiple data science teams.

* A larger data science group with multiple data science teams that nevertheless wants to optimize inter-team collaboration with activities such as group-level sprint planning.

If teams choose to have their team-specific repositories under a single group project, the team leads should create the repositories with names like *<TeamName>Template and <TeamName>Utilities*. For instance: *TeamATemplate* and *TeamAUtilities*.

In any case, team leads need to let their team members know which template and utilities repositories to set up and clone. Project leads should follow the project lead tasks for a data science team to create project repositories, whether under separate projects or a single project.

## Create the MyTeam project
To create a separate project for your team:

1. In your web browser, go to your group's Azure DevOps organization home page whoch would be URL containing the following details "https:///organization name", and select **New project**.

![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/team-lead-tasks/team-leads-2-create-new-team.png)

2. In the **Create project** dialog, enter your team name, such as *MyTeam*, under **Project name**, and then select **Advanced**.

3. Under **Version control**, select **Git**, and under **Work item process**, select **Agile**. Then select **Create**.

![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/team-lead-tasks/team-leads-3-create-new-team-2.png)

The team project **Summary** page opens, with page URL containing the following information "https://server name/organization name/team name".
	
## Rename the MyTeam default repository to TeamUtilities

1. On the **MyTeam** project **Summary** page, under **What service would you like to start with?**, select **Repos**.

![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/team-lead-tasks/team-leads-6-rename-team-project-repo.png)

2. On the **MyTeam** repo page, select the **MyTeam** repository at the top of the page, and then select **Manage repositories** from the dropdown.

![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/team-lead-tasks/team-leads-7-rename-team-project-repo-2.png)

3. On the **Project Settings** page, select the ... next to the **MyTeam** repository, and then select **Rename repository**.

![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/team-lead-tasks/team-leads-8-rename-team-project-repo-3.png)

4. In the **Rename the MyTeam repository** popup, enter *TeamUtilities*, and then select **Rename**.

## Create the TeamTemplate repository

1. On the **Project Settings** page, select **New repository**. 

![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/team-lead-tasks/team-leads-9-create-team-utilities.png)

Or, select **Repos** from the left navigation of the **MyTeam** project **Summary** page, select a repository at the top of the page, and then select **New repository** from the dropdown.

2. In the **Create a new repository** dialog, make sure **Git** is selected under **Type**. Enter *TeamTemplate* under **Repository name**, and then select **Create**.

3. Confirm that you can see the two repositories **TeamUtilities** and **TeamTemplate** on your project settings page.

![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/team-lead-tasks/team-leads-11-two-repo-in-team.png)

## Import the contents of the group common repositories
To populate your team repositories with the contents of the group common repositories set up by your group manager:

1. From your **MyTeam** project home page, select **Repos** in the left navigation. If you get a message that the **MyTeam** template is not found, select the link in **Otherwise, navigate to your default TeamTemplate repository**.

The default **TeamTemplate** repository opens.

2. On the **TeamTemplate is empty page**, select **Import**.

![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/team-lead-tasks/import-repo.png)

3. In the **Import a Git repository** dialog, select **Git** as the **Source type**, and enter the URL for your group common template repository under **Clone URL**. The URL will contain the details: "https://server name/organization name/_git/repository name". For example: "https://dev.azure.com/DataScienceUnit/GroupCommon/_git/GroupProjectTemplate".
	
4. Select **Import**. The contents of your group template repository are imported into your team template repository.

![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/team-lead-tasks/import-repo-2.png)

5. At the top of your project's **Repos** page, drop down and select the **TeamUtilities** repository.

6. Repeat the import process to import the contents of your group common utilities repository, for example *GroupUtilities*, into your **TeamUtilities** repository.

Each of your two team repositories now contains the files from the corresponding group common repository.

## Customize the contents of the team repositories
If you want to customize the contents of your team repositories to meet your team's specific needs, you can do that now. You can modify files, change the directory structure, or add files and folders.

To modify, upload, or create files or folders directly in Azure DevOps:

1. On the **MyTeam** project **Summary** page, select **Repos**.

2. At the top of the page, select the repository you want to customize.

3. In the repo directory structure, navigate to the folder or file you want to change.

* To create new folders or files, select the arrow next to **New**.

![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/team-lead-tasks/new-file.png)

* To upload files, select **Upload file(s)**.

![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/team-lead-tasks/upload-files.png)

* To edit existing files, navigate to the file and then select **Edit**.

![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/team-lead-tasks/edit-file.png)

4. After adding or editing files, select **Commit**.

![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/team-lead-tasks/commit.png)

To work with repositories on your local machine or Azure ML notebooks, you first copy or clone the repositories to your local machine or Azure ML notebook environment, and then commit and push your changes up to the shared team repositories,
 
For more infomtion on how to work with Git repos on Azure ML notebooks click [here](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/gitIntegration.md), for more information on how to work with Git repos on your local machine click [here](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/createRepo.md).


## Add team members and configure permissions
To add members to the team:

1. In Azure DevOps, from the MyTeam project home page, select **Project settings** from the left navigation.

2. From the **Project Settings** left navigation, select **Teams**, then on the **Teams** page, select the **MyTeam Team**.

![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/team-lead-tasks/teams.png)

3.On the **Team Profile** page, select **Add**.

![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/team-lead-tasks/add-to-team.png)

4. In the **Add users and groups** dialog, search for and select members to add to the group, and then select **Save changes**.

![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/team-lead-tasks/add-users.png)

To configure permissions for team members:

1. From the **Project Settings** left navigation, select **Permissions**.

2. On the **Permissions** page, select the group you want to add members to.

3. On the page for that group, select **Members**, and then select **Add**.

4. In the **Invite members** popup, search for and select members to add to the group, and then select **Save**.

![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/team-lead-tasks/grant-permissions.png)

## Create team data and analytics resources
This step is optional, but sharing data and analytics resources with your entire team has performance and cost benefits. Team members can execute their projects on the shared resources, save on budgets, and collaborate more efficiently. You can create Azure file storage and mount it on your Azure ML noteooks to share with team members.


### Create Azure file storage 
First ensure that you have Azure CLI insitalled. For instructions on installing the Azure CLI click [here](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli)

1. Run the following script to create Azure file storage for data assets that are useful for your entire team. The script prompts you for your Azure subscription information, so have that ready to enter.

* On a Windows machine, run the script from the PowerShell command prompt:
`wget "https://raw.githubusercontent.com/Azure/`
`Azure-MachineLearning-DataScience/master/Misc/TDSP/`
`CreateFileShare.ps1" -outfile "CreateFileShare.ps1"`
`.\CreateFileShare.ps1`

2. Log in to your Microsoft Azure account when prompted, and select the subscription you want to use.

3. Select the storage account to use, or create a new one under your selected subscription. You can use lowercase characters, numbers, and hyphens for the Azure file storage name.

4. To facilitate mounting and sharing the storage, press Enter or enter `Y` to save the Azure file storage information into a text file in your current directory. You can check in this text file to your **TeamTemplate** repository, ideally under **Docs/DataDictionaries**, so all projects in your team can access it. You also need the file information to mount your Azure file storage in the next section.

## Mount Azure file storage on your local machine

 1. To mount your Azure file storage to your local machine when using Windows, use the following script.
  `wget "https://raw.githubusercontent.com/Azure/`
`Azure-MachineLearning-DataScience/master/Misc/TDSP/`
`AttachFileShare.ps1" -outfile "AttachFileShare.ps1"`
`.\AttachFileShare.ps1`

* On a Linux machine, run the script from the Linux shell:
`wget "https://raw.githubusercontent.com/Azure/`
`Azure-MachineLearning-DataScience/master/Misc/`
`TDSP/AttachFileShare.sh"`
`bash AttachFileShare.sh`

2. Press Enter or enter `Y` to continue, if you saved an Azure file storage information file in the previous step. Enter the complete path and name of the file you created.

If you don't have an Azure file storage information file, enter `n`, and follow the instructions to enter your subscription, Azure storage account, and Azure file storage information.

3. Enter the name of a local or TDSP drive to mount the file share on. The screen displays a list of existing drive names. Provide a drive name that doesn't already exist.

4.Confirm that the new drive and storage is successfully mounted on your machine.

 To connect to storage services on Azure via Azure Machine Learning datastores see [here](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-access-data).

## Next Steps:

Here are links to detailed descriptions of the other roles and tasks in the Team Data Science Process:

* [Group Managr tasks for a data science team](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/group-manager-tasks.md)
* [Project Lead tasks for a data science team](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/project-lead-tasks.md)
* [Project Individual Contributor tasks for a data science team](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/project-ic-tasks.md)



