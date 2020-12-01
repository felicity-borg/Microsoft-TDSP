
# Project lead tasks in the Team Data Science Process

This document describes tasks that a project lead completes to set up a repository for their project team in the Team Data Science Process (TDSP). 
A project lead manages the daily activities of individual data scientists on a specific data science project in the TDSP. The following diagram shows the workflow for project lead tasks:

![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/project-lead-tasks/project-leads-1-tdsp-creating-projects.png)

This document covers Step 1: Create project repository, and Step 2: Seed project repository from your team ProjectTemplate repository.

For Step 3: Create Feature work item for project, and Step 4: Add Stories for project phases, see [Agile development of data science projects](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/agile-development.md).

For Step 5: Create and customize storage/analysis assets and share, if necessary, refer to **Create team data and analytics resources** [here](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/team-lead-tasks.md).

For Step 6: Set up security control of project repository, refer to **Add team members and configure permissions** [here](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/team-lead-tasks.md).

# Prerequisites
This tutorial assumes that your group manager and team lead have set up the following resources and permissions:

* The Azure DevOps **organization** for your data unit

* A team **project** for your data science team

* Team template and utilities **repositories**

* **Permissions** on your organization account for you to create and edit repositories for your project

To clone repositories and modify content on your local machine or Azure ML notebooks, or set up Azure file storage and mount it, you also need to consider this checklist:

* An Azure subscription.

* Git installed on your machine.

## Create a project repository in your team project
To create a project repository in your team's **MyTeam** project:

1) Go to your team's project **Summary** page which would be in the format: "https://server name/organization name/team name", for example, "https://dev.azure.com/DataScienceUnit/MyTeam", and select **Repos** from the left navigation.

2. Select the repository name at the top of the page, and then select **New repository** from the dropdown.

![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/project-lead-tasks/project-leads-9-select-repos.png)

3. In the **Create a new repository** dialog, make sure **Git** is selected under **Type**. Enter *DSProject1* under **Repository name**, and then select **Create**.

![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/project-lead-tasks/project-leads-3-create-project-repo-2.png)

4. Confirm that you can see the new **DSProject1** repository on your project settings page.

![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/project-lead-tasks/project-leads-4-create-project-repo-3.png)

## Import the team template into your project repository
To populate your project repository with the contents of your team template repository:

1. From your team's project **Summary** page, select **Repos** in the left navigation.

2. Select the repository name at the top of the page, and select **DSProject1** from the dropdown.

3. On the **DSProject1** is empty page, select **Import**.

![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/project-lead-tasks/project-leads-5-create-project-repo-4.png)

4. In the **Import a Git repository** dialog, select **Git** as the **Source type**, and enter the URL for your **TeamTemplate** repository under **Clone URL**. The URL is the format:
"https://server name/organization name/team name/_git/team template repository name".
For example: "https://dev.azure.com/DataScienceUnit/MyTeam/_git/TeamTemplate".

5. Select **Import**. The contents of your team template repository are imported into your project repository.

![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/project-lead-tasks/project-leads-6-create-project-repo-5.png)

If you need to customize the contents of your project repository to meet your project's specific needs, you can add, delete, or modify repository files and folders. You can work directly in Azure Repos, or clone the repository to your local machine or DSVM, make changes, and commit and push your updates to the shared project repository. Follow the instructions at **Customize the contents of the team repositories** [here](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/team-lead-tasks.md).


## Next Steps:

Here are links to detailed descriptions of the other roles and tasks in the Team Data Science Process:

* [Group Managr tasks fr a data science team](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/group-manager-tasks.md)
* [Team Lead tasks for a data science team](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/team-lead-tasks.md)
* [Project Individual Contributor tasks for a data science team](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/project-ic-tasks.md)
