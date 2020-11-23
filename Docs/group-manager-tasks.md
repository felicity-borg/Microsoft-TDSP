<properties
	pageTitle="Team Data Science Process group manager tasks"
	description="Outlines the tasks that a group manager is expected to complete for the data science team."  
	services="machine-learning"
	documentationCenter=""
	authors="bradsev"
	manager="jhubbard"
	editor="cgronlun" />

<tags
	ms.service="machine-learning"
	ms.workload="data-services"
	ms.tgt_pltfrm="na"
	ms.devlang="na"
	ms.topic="article"
	ms.date="09/20/2016"
	ms.author="bradsev;hangzh;"/>


# Team Data Science Process group manager tasks

This page outlines the tasks that a *group manager* is expected to complete for a dtaa science organization. The group manager manages the entire dtaa scinece unit in an enterprise. A data science unit may have several teams, each of which is working on many data science projects in distinct business verticals. The group manager's objective is to establish a collaborative group environment that standardizes on the Team Data Science Process (TDSP). For an outline of all the personnel roles and associated tasks handled by a data science team standardizing on the TDSP, see [Team Data Science Process: roles and tasks](roles-tasks.md).

The following diagram shows the six main group manager setup tasks. Group managers may delegate their tasks to surrogates, but the tasks associated with the role don't change.
![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/group-manager-tasks/tdsp-group-manager.png)


1. Set up an **Azure DevOps organization** for the group.
2. Create the default **GroupCommon project** in the Azure DevOps organization.
3. Create the **GroupProjectTemplate** repository in Azure Repos.
4. Create the **GroupUtilities** repository in Azure Repos.
5. Import the contents of the Microsoft TDSP team's **ProjectTemplate** and **Utilities** repositories into the group common repositories.
6 .Set up **membership** and **permissions** for team members to access the group.

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









		
After you sign in, click **Create New Account** in the upper right corner as shown in the following image:
		
![3](./media/group-manager-tasks/create-account-1.PNG)
		
Fill in the information for the VSTS server that you want to create in the **Create your account** wizard with the following values: 

- **Server URL**: Replace *mysamplegroup* with your own *server name*. The URL of your server is going to be: *https://\<servername\>.visualstudio.com*. 
- **Manage code using:** Select **_Git_**.
- **Project name:** Enter *GroupCommon*. 
- **Organize work using:** Choose *Agile*.
- **Host your projects in:** Choose a geo location. In this example, we choose *South Central US*. 
		
![4](./media/group-manager-tasks/fill-in-account-information.png)

>[AZURE.NOTE] If you see the following pop-up window after you click **Create new account**, then you need to click **Change details** to display all the fields itemized.

![5](./media/group-manager-tasks/create-account-2.png)


Click **Continue**. 

## 2. GroupCommon Team Project

The **GroupCommon** page (*https://\<servername\>.visualstudio.com/GroupCommon*) opens after your VSTS server is created.
							
![6](./media/group-manager-tasks/server-created-2.PNG)

## 3. Create the GroupUtilities (R2) repository

To create the **GroupUtilities** (R2) repository under VSTS server:

- Click **New repository** on the **Version Control** tab of your team project to open the **Create a new repository** wizard. 

![13](./media/group-manager-tasks/create-grouputilities-repo-1.png) 

- Select *Git* as the **Type**, and enter *GroupUtilities* as the **Name**, and then click **Create**. 

![14](./media/group-manager-tasks/create-grouputilities-repo-2.png)
				
Now you should see two Git repositories **GroupProjectTemplate** and **GroupUtilities** in the left column of the **Version Control** page: 

![15](./media/group-manager-tasks/two-repo-under-groupCommon.PNG)


## 4. Create the GroupProjectTemplate (R1) repository

The setup of the repositories for the VSTS group server consists of two tasks:

- Rename the default **GroupCommon** repository***GroupProjectTemplate***.
- Create the **GroupUtilities** repository on the VSTS server under team project **GroupCommon**. 

Instructions for the first task are contained in this section after remarks on naming conventions or our repositories and directories. The instructions for the second task are contained in the followning section for step 4.

### Rename the default GroupCommon repository

To rename the default **GroupCommon** repository as *GroupProjectTemplate* (referred as **R1** in this tutorial):
	
- Click **Collaborate on code** on the **GroupCommon** team project page. This takes you to the default Git repository page of the team project **GroupCommon**. Currently, this Git repository is empty. 

![9](./media/group-manager-tasks/rename-groupcommon-repo-3.png)
		
- Click **GroupCommon** on the top left corner (highlighted with a red box in the following figure) on the Git repository page of **GroupCommon** and select **Manage repositories** (highlighted with a green box in the following figure). This brings up the **CONTROL PANEL**. 
- Select the **Version Control** tab of your team project. 

![10](./media/group-manager-tasks/rename-groupcommon-repo-4.png)

- Click the **...** to the right of the **GroupCommon** repository on the left panel, and select **Rename repository**. 

![11](./media/group-manager-tasks/rename-groupcommon-repo-5.png)
		
- In the **Rename the GroupCommon repository** wizard that pops up, enter *GroupProjectTemplate* in the **Repository name** box, and then click **Rename**. 

![12](./media/group-manager-tasks/rename-groupcommon-repo-6.png)



## 5. Seed the R1 & R2 repositories on the VSTS server

In this stage of the procedure, you seed the *GroupProjectTemplate* (R1) and *GroupUtilities* (R2) repositories that you set up in the previous section. These repositories are seeded with the ***ProjectTemplate*** (**G1**) and ***Utilities*** (**G2**) repositories that are managed by Microsoft for the Team Data Science Process. When this seeding is completed:

- your R1 repository is going to have the same set of directories and document templates that the G1 does
- your R2 repository is going to contain the set of data science utilities developed by Microsoft.

The seeding procedure uses the directories on your local DSVM as intermediate staging sites. Here are the steps followed in this section:

- G1 & G2 - cloned to -> LG1 & LG2
- R1 & R2 - cloned to -> LR1 & LR2
- LG1 & LG2 - files copied into -> LR1 & LR2
- (Optional) customization of LR1 & LR2
- LR1 & LR2 - contents add to -> R1 & R2


### Clone G1 & G2 repositories to your local DSVM

In this step, you clone the Team Data Science Process (TDSP) ProjectTemplate repository (G1) and Utilities (G2) from the TDSP github repositories to folders in your local DSVM as LG1 and LG2:

- Create a directory to serve as the root directory to host all your clones of the repositories. 
	-  In the Windows DSVM, create a directory *C:\GitRepos\TDSPCommon*. 
	-  In the Linux DSVM, create a directory *GitRepos\TDSPCommon* in your home directory. 

- Run the following set of commands from the *GitRepos\TDSPCommon* directory.

	`git clone https://github.com/Azure/Azure-TDSP-ProjectTemplate`<br>
	`git clone https://github.com/Azure/Azure-TDSP-Utilities`
        
![16](./media/group-manager-tasks/two-folder-cloned-from-TDSP-windows.PNG)

- Using our abbreviated repository names, this is what these scripts have achieved: 
	- G1 - cloned into -> LG1
	- G2 - cloned into -> LG2
- After the cloning is completed, you should be able to see two directories, _ProjectTemplate_ and _Utilities_, under **GitRepos\TDSPCommon** directory. 

### Clone R1 & R2 repositories to your local DSVM

In this step, you clone the GroupProjectTemplate repository (R1) and GroupUtilities repository (R2) on local directories (referred as LR1 and LR2, respectively) under **GitRepos\GroupCommon** on your DSVM.

- To get the URLs of the R1 and R2 repositories, go to your **GroupCommon** home page on VSTS. This usually has the URL *https://\<Your VSTS Server Name\>.visualstudio.com/GroupCommon*. 
- Click **CODE**. 
- Choose the **GroupProjectTemplate** and **GroupUtilities** repositories, copy and save each of the URLs (HTTPS for Windows; SSH for Linux) from the **Clone URL** element, in turn, for use in the following scripts:  

![18](./media/group-manager-tasks/find_https_ssh_2.PNG)

- Change into the **GitRepos\GroupCommon** directory on your Windows or Linux DSVM and run one of the following sets of commands to clone R1 and R2 into that directory.
		
Here are the Windows and Linux scripts:

	# Windows DSVM

	git clone <the HTTPS URL of the GroupProjectTemplate repository>
	git clone <the HTTPS URL of the GroupUtilities repository>

![19](./media/group-manager-tasks/clone-two-empty-group-reo-windows-2.PNG)

	# Linux DSVM

	git clone <the SSH URL of the GroupProjectTemplate repository>
	git clone <the SSH URL of the GroupUtilities repository>

![20](./media/group-manager-tasks/clone-two-empty-group-reo-linux-2.PNG)

>[AZURE.NOTE] Expect to receive warning messages that LR1 and LR2 are empty. 	

- Using our abbreviated repository names, this is what these scripts have achieved: 
	- R1 - cloned into -> LR1
	- R2 - cloned into -> LR2	


### Seed your GroupProjectTemplate (LR1) and GroupUtilities (LR2)

Next, in your local machine, we need to copy the content of ProjectTemplate and Utilities directories (except the metadata in the .git directories) under GitRepos\TDSPCommon to your GroupProjectTemplate and GroupUtilities directories under **GitRepos\GroupCommon**. Here are the two tasks to complete in this step:

- Copy the files in GitRepos\TDSPCommon\ProjectTemplate (**LG1**) to GitRepos\GroupCommon\GroupProjectTemplate (**LR1**) 
- Copy the files in GitRepos\TDSPCommon\Utilities (**LG2** to GitRepos\GroupCommon\Utilities (**LR2**). 

To achieve these two tasks, run the following scripts in PowerShell console (Windows) or Shell script console (Linux). You are prompted to input the complete paths to LG1, LR1, LG2, and LR2. The paths that you input are validated. If you input a directory that does not exist, you are asked to input it again. 

	# Windows DSVM		
	
    wget "https://raw.githubusercontent.com/Azure/Azure-MachineLearning-DataScience/master/Misc/TDSP/tdsp_local_copy_win.ps1" -outfile "tdsp_local_copy_win.ps1"
    .\tdsp_local_copy_win.ps1 1

![21](./media/group-manager-tasks/copy-two-folder-to-group-folder-windows-2.PNG)

Now you can see that files in directories LG1 and LG1 (except files in the .git directory) have been copied to LR1 and LR2, respectively.

![22](./media/group-manager-tasks/copy-two-folder-to-group-folder-windows.PNG)

	# Linux DSVM

    wget "https://raw.githubusercontent.com/Azure/Azure-MachineLearning-DataScience/master/Misc/TDSP/tdsp_local_copy_linux.sh"
    bash tdsp_local_copy_linux.sh 1

![23](./media/group-manager-tasks/copy-two-folder-to-group-folder-linux-2.PNG)
		
Now you see that the files in the two folders (except files in the .git directory) are copied to GroupProjectTemplate and GroupUtilities respectively.
	
![24](./media/group-manager-tasks/copy-two-folder-to-group-folder-linux.PNG)

- Using our abbreviated repository names, this is what these scripts have achieved:
	- LG1 - files copied into -> LR1
	- LG2 - files copied into -> LR2

### Option to customize the contents of LR1 & LR2
	
If you want to customize the contents of LR1 and LR2 to meet the specific needs of your group, this is the stage of the procedure where that is appropriate. You can modify the template documents, change the directory structure, and add existing utilities that your group has developed or that are helpful for your entire group. 

### Add the contents in LR1 & LR2 to R1 & R2 on group server

Now, you need to add the contents in LR1 and LR2 to repositories R1 and R2. Here are the git bash commands you can run in either Windows PowerShell or Linux. 

Run the following commands from the GitRepos\GroupCommon\GroupProjectTemplate directory:

	git status
	git add .
	git commit -m"push from DSVM"
	git push

The -m option lets you set a message for your git commit.

![25](./media/group-manager-tasks/push-to-group-server-2.PNG)

You can see that in your group's VSTS server, in the GroupProjectTemplate repository, the files are synced instantly.

![26](./media/group-manager-tasks/push-to-group-server-showed-up-2.PNG)

Finally, change to the **GitRepos\GroupCommon\GroupUtilities** directory and run the same set of git bash commands:

	git status
	git add .
	git commit -m"push from DSVM"
	git push

>[AZURE.NOTE] If this is the first time you commit to a Git repository, you need to configure global parameters *user.name* and *user.email* before you run the `git commit` command. Run the following two commands:
		
	git config --global user.name <your name>
	git config --global user.email <your email address>
 
>If you are committing to multiple Git repositories, use the same name and email address when you commit to each of them. Using the same name and email address proves convenient later on when you build PowerBI dashboards to track your Git activities on multiple repositories.


- Using our abbreviated repository names, this is what these scripts have achieved:
	- LR1 - contents add to -> R1
	- LR2 - contents add to -> R2

## 6. Add group members to the group server

From your group VSTS server's homepage, click the **gear icon** next to your user name in the upper right corner, then select the **Security** tab. You can add members to your group here with various permissions. For more information, see the **Security Control** section in [Data science resources](resources.md) topic.

![27](./media/group-manager-tasks/add_member_to_group.PNG) 
