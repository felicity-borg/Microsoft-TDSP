# Getting a project started using Azure DevOps, Git and Jupyter Lab

This document will help guide you on how to get a project started using Azure DevOps to manage your project, a Git repository to manage your code and a Jupyter Lab as your selected Integrated Deveopment Environment (IDE).

This guide is ideal if you want to get a small project started such as for a proof of concept or you would like to develop a better idea on how to use and integrate these tools. 
If you would like to use these tools for a substantial project within a larger team please refer to [Roles and taks](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/team-lead-tasks.md) for an overiew of the different roles and repsonsibilities. 

This page will give you further links for detailed instructions on your role and how to get started with your project. Details covered include how to [get started with Azure DevOps](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/agile-development.md), [creating a project repository](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/group-manager-tasks.md) and [setting up security control—adding project members and configuring permissions](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/project-lead-tasks.md). 


![](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/media/resources/DevGitJup.PNG) <br>
*An overview of the tools used for this solution*

1. Use Azure DevOps to create and manage your project. You can use this to break down your project into smaller tasks for e.g. 
2. Create a git repo for your project to manage your code including using version control making it easy to track changes overtime and making it easier to resove conflicts in code. 
3. Clone the git repo onto your directory on Azure Maching Learning shared workspace file system and use Jupyer notebooks to write your code. With your workspace now connected to your git repo you can `commit` (save) changes back to your git repo. If files are added to the git repo you can `pull` these changes onto your workspace making collaborating with colleagues easy. 

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

## 3. Run a notebook in your workspace

For details on how to create and manage an Azure ML workspace click [here](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/azure-ml-workspace.md).

### Create notebooks

In your Azure Machine Learning workspace, create a new Jupyter notebook and start working. The newly created notebook is stored in the default workspace storage. This notebook can be shared with anyone with access to the workspace.

To create a new notebook:

1. Open your workspace in [Azure MAchine Learning studio](https://ml.azure.com/).
2. On the left side, select **Notebooks**.
3. Select the **Create new file** icon above the list **User files** in the **My files** section. <br>
![](https://docs.microsoft.com/en-us/azure/machine-learning/media/how-to-run-jupyter-notebooks/create-new-file.png)

4. Name the file.

5. For Jupyter Notebook Files, select **Notebook** as the file type.

6. It is recommended that you select your file directory so that others will not make collisions directly on your working branch when pushhing your code to `git`.

7. Select **Create**.

You can create text files as well. Select **Text** as the file type and add the extension to the name (for example, myfile.md or myfile.txt)

You can also upload folders and files, including notebooks, with the tools at the top of the Notebooks page. Notebooks and most text file types display in the preview section. No preview is available for most other file types.

### Create a compute instance
1. In your workspace in Azure Machine Learning studio, select **Compute**, then select **Compute Instance** on the top. <br>
![](hhttps://docs.microsoft.com/en-us/azure/machine-learning/media/how-to-create-attach-studio/create-compute-target.png)

2. If you see a list of compute resources, select **+New** above the list. <br>
![](https://docs.microsoft.com/en-us/azure/machine-learning/media/how-to-create-attach-studio/select-new.png)

3. Fill out the form for your compute instance <br>
![](https://docs.microsoft.com/en-us/azure/machine-learning/media/concept-compute-instance/create-compute-instance.png)

| **Field** | **Description** |
| --------- | --------------- |
| Compute name | * Name is required and must be between 3 to 24 characters long.
* Valid characters are upper and lower case letters, digits, and the - character.
* Name must start with a letter.
* Name needs to be unique across all existing computes within an Azure region. You will see an alert if the name you choose is not unique.
* If - character is used, then it needs to be followed by at least one letter later in the name. |
| Virtual machine type | Chooose CPU or GPU. thus type cannot be changed after creation. Select CPU for general use unless you know your code will use GPU (example for training deep learning models |
| Virtual machine size | Supported virtual machine sizes might be restricted in your region. Check the [availability list](https://azure.microsoft.com/global-infrastructure/services/?products=virtual-machines) |
| Enable/disable SSH access | SSH access is disabled by default. SSH access cannot be. changed after creation. Make sure to enable access if you plan to debug interactively with [VS Code Remote](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-set-up-vs-code-remote) |
| Advanced settings | Optional. Configure a virtual network. Specify the **Resource group**, **Virtual network**, and **Subnet** to create the compute instance inside an Azure Virtual Network (vnet). For more information, see these network requirements for vnet.

4. Select **Create**

5. View the status of the create operation by selecting the compute target from the list

![](https://docs.microsoft.com/en-us/azure/machine-learning/media/how-to-create-attach-studio/view-list.png)

### Clone Git repositories into your workspace file system

Azure Machine Learning provides a shared file system for all users in the workspace. To clone a Git repository into this file share:
* Follow the instructions [here](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/gitIntegration.md) to copy the details needed to clone the Git repo. 
* Go back to your Azure ML workspace
* Open a terminal. Once the terminal is opened, you have access to a full Git client and can clone and work with Git via the Git CLI experience.
* It is advised that you clone the repository into your users directory so that others will not make collisions directly on your working branch. To do this type cd <path to you user directory> e.g. `cd david`
* Run git clone followed by the followed by the path copied from the Clone URL in the previous section, as shown in the following example. git clone https://dev.azure.com/fabrikam-fiber/MyFirstProject/_git/
* Next it will ask for a password, paste the password shown when you cloned your git repo as shown [here](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/gitIntegration.md) and press Enter. <br>
Git downloads a copy of the code, including all commits and branches from the repo, into a new folder for you to work with.

Switch your directory to the repository that you cloned. For e.g.
cd fabrikam-fiber

For details on how to work with git such as using `commit` to save changes and using `push` to share code refer to the **command line** examples shown under docuemnts titles **Commits, push, fetch, pull** shown on the left [here](https://docs.microsoft.com/en-us/azure/devops/repos/git/commits?view=azure-devops&tabs=command-line)

