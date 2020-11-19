<properties
	pageTitle="Agile development of data science projects"
	description="How a data scientist can execute a data science project in a systematic, version controlled, and collaborative way within a project team."  
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
	ms.date="09/21/2016"
	ms.author="bradsev;hangzh;"/>


# Agile development of data science projects

This document describes how a data scientist can execute a data science project in a systematic, version controlled, and collaborative way within a project team by using the [Team Data Science Process](README.md) (TDSP). The TDSP is a framework developed by Microsoft that provides a structured sequence of activities to execute cloud-based, predictive analytics solutions efficiently. For an outline of the personnel roles, and their associated tasks that are handled by a data science team standardizing on this process, see [Team Data Science Process: roles and tasks](roles-tasks.md). 

This topic includes instructions on how to: 

1. So *sprint planning* for work items involved in a project. 
2. *Add work items* to sprints.
3. Create and use an *agile-derived work item template* that specifically aligns with TDSP lifecycle stages.


The following instructions outline the steps needed to set up a TDSP team environment using Azure Boards and Azure Repos in Azure DevOps.
If your group uses a different code hosting platform, the team lead tasks generally don't change, but the way to complete the tasks is different. For example, linking a work item with a Git branch might not be the same with GitHub as it is with Azure Repos.

The following figure illustrates a typical sprint planning, coding and source-control workflow involved in implementing a data science project:

![1](./media/project-execution/project-execution-1-project-execute.png)


1. [Work item types](#Work item types-1)
2. [Plan sprints](#Plan sprints-2)
3. [Add a Feature to the backlog](#AddFeature-3)
4. [Add a User Story to the Feature](#AddStoryunderfeature-4)
5. [Add a Task to a User Story](#AddTaskunderstory-5)
6. [Use an agile TDSP work template](#Linkaworkitemwithagitbranch-6)

##  1. <a name='Work item types-1'></a>Work item types

In the TDSP sprint planning framework, there are four frequently used types of **work items**: **Feature**, **User Story**, **Task**, and **Bug**. Each team project maintains a single backlog for all work items. There is no backlog at the git repository level under a team project. Here are their definitions:

- **Feature**: A feature corresponds to a project engagement. Different engagements with a client are considered different features. Similarly, it is best to consider different phases of a project with a client as different features. If you choose a schema such as ***ClientName-EngagementName*** to name your features, then you can easily recognize the context of the project/engagement from the names themselves.
- **Story**: Stories are different work items that are needed to complete a feature (project) end-to-end. Examples of stories include:
	- Getting Data 
	- Exploring Data 
	- Generating Features
	- Building Models
	- Operationalizing Models 
	- Retraining Models
- **Task**: Tasks are assignable code or document work items or other activities that need to be done to complete a specific story. For example, tasks in the story *Getting Data* could be:
	-  Getting Credentials of SQL Server 
	-  Uploading Data to SQL Data Warehouse. 
- **Bug**: Bugs usually refer to fixes that are needed for an existing code or document that are done when completing a task. It can escalate to being a story or a task if the bug is caused by missing stages or tasks respectively. 

>[AZURE.NOTE] We are borrowing concepts of features, stories, tasks, and bugs from software code management (SCM) to be used in data science. They might differ slightly from their conventional  SCM definitions.

##  2. <a name='Plan sprints-2'></a>Plan sprints

Sprint planning is useful for project prioritization, and resource planning and allocation. Many data scientists are engaged with multiple projects, each of which can take months to complete. Projects often proceed at different paces. On the VSTS server, you can easily create, manage, and track work items in your team project and conduct sprint planning to ensure that your projects are moving forward as expected. 

Follow [this link](https://www.visualstudio.com/en-us/docs/work/scrum/sprint-planning) for the step-by-step instructions on sprint planning in VSTS. 


##  3. <a name='AddFeature-3'></a>Add a Feature to the backlog

After your project repository is created under a team project, go to the team **Overview** page and click **Manage work**.

![2](./media/project-execution/project-execution-2-sprint-team-overview.png)

To include a feature in the backlog, click **Backlogs** --> **Features** --> **New**, type in the feature **Title** (usually your project name), and then click **Add** .

![3](./media/project-execution/project-execution-3-sprint-team-add-work.png)

Double-click the feature you just created. Fill in the descriptions, assign team members for this feature, and set planning parameters for this feature. 

You can also link this feature to the project repository. Click **Add link** under the **Development** section. After you have finished editing the feature, click **Save & Close** to exit.


##  4. <a name='AddStoryunderfeature-4'></a>Add a User Story to the Feature

Under the feature, stories can be added to describe major steps needed to finish the (feature) project. To add a new story, click the **+** sign to the left of the feature in backlog view.  

![4](./media/project-execution/project-execution-4-sprint-add-story.png)

You can edit the details of the story, such as the status, description, comments, planning, and priority In the pop-up window.

![5](./media/project-execution/project-execution-5-sprint-edit-story.png)

You can link this story to an existing repository by clicking **+ Add link** under **Development**. 

![6](./media/project-execution/project-execution-6-sprint-link-existing-branch.png)


##  5. <a name='AddTaskunderstory-5'></a>Add a Task to a User Story

Tasks are specific detailed steps that are needed to complete each story. After all tasks of a story are completed, the story should be completed too. 

To add a task to a story, click the **+** sign next to the story item, select **Task**, and then fill in the detailed information of this task in the pop-up window.

![7](./media/project-execution/project-execution-7-sprint-add-task.png)

After the features, stories, and tasks are created, you can view them in the **Backlog** or **Board** views to track their status.

![8](./media/project-execution/project-execution-8-sprint-backlog-view.png)

![9](./media/project-execution/project-execution-9-link-to-a-new-branch.png)


##  6. <a name='Linkaworkitemwithagitbranch-6'></a>Use an agile TDSP work template

VSTS provides a convenient way to connect a work item (a story or task) with a git branch. This enables you to link your story or task directly to the code associated with it. 

To connect a work item to a new branch, double-click a work item, and in the pop-up window, click **Create a new branch** under **+ Add link**.  

![10](./media/project-execution/project-execution-10-sprint-board-view.png)

Provide the information for this new branch, such as the branch name, base git repository and the branch. The git repository  chosen must be the repository under the same team project that the work item belongs to. The base branch can be the master branch or some other existing branch.

![11](./media/project-execution/project-execution-11-create-a-branch.png)

A good practice is to create a git branch for each story work item. Then, for each task work item, you create a branch based on the story branch. Organizing the branches in this hierarchical way that corresponds to the story-task relationships is helpful when you have multiple people working on different stories of the same project, or you have multiple people working on different tasks of the same story. Conflicts can be minimized when each team member works on a different branch and when each member works on different codes or other artifacts when sharing a branch. 

The following picture depicts the recommended branching strategy for TDSP. You might not need as many branches as are shown here, especially when you only have one or two people working on the same project, or only one person works on all tasks of a story. But separating the development branch from the master branch is always a good practice. This can help prevent the release branch from being interrupted by the development activities. More complete description of git branch model can be found in [A Successful Git Branching Model](http://nvie.com/posts/a-successful-git-branching-model/).

![12](./media/project-execution/project-execution-12-git-branches.png)

To switch to the branch that you want to work on, run the following command in a shell command (Windows or Linux). 

	git checkout <branch name>

Changing the *<branch name\>* to **master** switches you back to the **master** branch. After you switch to the working branch, you can start working on that work item, developing the code or documentation artifacts needed to complete the item. 

You can also link a work item to an existing branch. In the **Detail** page of a work item, instead of clicking **Create a new branch**, you click **+ Add link**. Then, select the branch you want to link the work item to. 

![13](./media/project-execution/project-execution-13-link-to-an-existing-branch.png)

You can also create a new branch in git bash commands. If <base branch name\> is missing, the <new branch name\> is based on _master_ branch. 
	
	git checkout -b <new branch name> <base branch name>

 
