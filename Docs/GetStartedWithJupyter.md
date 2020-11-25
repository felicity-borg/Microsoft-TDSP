# Getting a project started using Azure DevOps, Git and Jupyter Lab

This document will help guide you on how to get a project started using Azure DevOps to manage your project, a Git repository to manage your code and a Jupyter Lab as your selected Integrated Deveopment Environment (IDE).

This guide is ideal if you want to get a small project started such as for a proof of concept or you would like to develop a better idea on how to use and integrate these tools. 
If you would like to use these tools for a substantial project within a larger team please refer to [Roles and taks](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/team-lead-tasks.md) for an overiew of the different roles and repsonsibilities. 

This page will give you further links for detailed instructions on your role and how to get started with your project. Details covered include how to [get started with Azure DevOps](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/agile-development.md), [creating a project repository](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/group-manager-tasks.md) and [setting up security control—adding project members and configuring permissions](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/project-lead-tasks.md). 


![](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/media/resources/DevGitJup.PNG) <br>
*An overview of the tools used for this solution*



## 1. Create a project in Azure DevOps

### Prerequisites
* You need an organization before you can create a project. <br>
If you haven't created an organization yet, create one by following the instructions in [Sign up, sign in to Azure DevOps, which also creates a project](https://docs.microsoft.com/en-us/azure/devops/user-guide/sign-up-invite-teammates?view=azure-devops). <br>
Or see [Create an organization or project collection](https://docs.microsoft.com/en-us/azure/devops/organizations/accounts/create-organization?view=azure-devops). 
If you have a Microsoft account follow the instructions fot the heading **Sign up with a personal Microsoft account** [here](https://docs.microsoft.com/en-us/azure/devops/user-guide/sign-up-invite-teammates?view=azure-devops) and then refer back to this documentation. <br>
If you are going to sign up with a newly created Microsoft account (MWS), your project is automatically created and named based on your sign-in. <br>
* To create a new project you must be a member of the Project Collection Administrators group or have the **Create new projects** permission set to **Allow**. If you're the Organization Owner, you're automatically added to the Project Collection Administrators group. If you aren't a member, get added before following this documentation. For more information, see [Set permissions at the project- or collection-level](https://docs.microsoft.com/en-us/azure/devops/organizations/security/set-project-collection-level-permissions?view=azure-devops).


>[Important] To create a public project, or to make a private project public, see [Create a public project in your organization](https://docs.microsoft.com/en-us/azure/devops/organizations/public/create-public-project?view=azure-devops) or [Change the project visibility, public or private](https://docs.microsoft.com/en-us/azure/devops/organizations/public/make-project-public?view=azure-devops). Additional policy settings must be enabled to work with public projects.

## Create a project

1. Navigate to your organization page `https://dev.azure.com/{yourorganization}`.
2. Select **Azure DevOps** to open the **Projects page**. 
3. Choose the organization, and then select **New Project**. 

![](https://docs.microsoft.com/en-us/azure/devops/organizations/projects/media/create-project/projects-hub-select-new-project.png?view=azure-devops)

4. Enter information into the form provided. Provide a name for your project. Your project name can't contain special characters, such as `/ : \ ~ & % ; @ ' " ? < > | # $ * } { , + = [ ]`, can't begin with an underscore, can't begin or end with a period, and must be 64 or fewer characters. Enter an optional description. Choose the visibility, **Git** as the source control type, and **Agile** as the work item process. For more information, see [Choosing the right version control for your project and Choose a process](https://docs.microsoft.com/en-us/azure/devops/boards/work-items/guidance/choose-process?view=azure-devops&tabs=basic-process).

![](https://docs.microsoft.com/en-us/azure/devops/organizations/projects/media/create-project/create-new-project-form-new-nav.png?view=azure-devops)

Select visibility of either public or private. When you choose public visibility, anyone on the internet can view your project. With private visibility, only people who you give access to can view your project. For more information about public projects, see [Create a public project in your organization](https://docs.microsoft.com/en-us/azure/devops/organizations/public/create-public-project?view=azure-devops). If the **Public** option isn't available, you need to change the policy

5. Select **Create**. The welcome page appears. 

![](https://docs.microsoft.com/en-us/azure/devops/organizations/projects/media/create-project/project-creation-complete-preview.png?view=azure-devops)

* **Invite**: on the top right if you want to add others to your project. See [Add users to a project or team](https://docs.microsoft.com/en-us/azure/devops/organizations/security/add-users-team-project?view=azure-devops). You can only invite users who are already in your organization.


## 2. Add a Git repo to your project

1. Navigate to the **Repos** page in your project, hover your mouse over the name of your project and select the **Repos** icon. 
![](https://docs.microsoft.com/en-us/azure/devops/repos/git/media/repo-mgmt/select-project-repos.png?view=azure-devops)
2. From the repo drow-down, select **New repository**.
![](https://docs.microsoft.com/en-us/azure/devops/repos/git/media/repo-mgmt/new-repository.png?view=azure-devops)
3. In the **Create a new repository** dialog, verify that Git is the repo type and enter a name for your new repo. You can also choose to add a README and create a .gitignore for the type of code you plan to manage in the repo. A README contains information about the code in your repo, and a .gitignore file tells Git which types of files to ignore, such as temporary build files from your development environment.
![](https://docs.microsoft.com/en-us/azure/devops/repos/git/media/repo-mgmt/create-a-new-repository.png?view=azure-devops)
4. When you're happy with the repo name and choices, select **Create**.

A new empty Git repo is now created in your project.

## 3. 
