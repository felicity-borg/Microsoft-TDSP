 <properties
	pageTitle="Data Science Process: components, roles and tasks"
	description="An outline of the key components, personel roles, and associated tasks for a data science team."  
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

# Data Science Process: Roles and tasks

The Team Data Science Process (TDSP) is a framework developed by Microsoft that provides a structured methodology to efficiently build predictive analytics solutions and intelligent applications. This page outlines the key personnel roles and associated tasks for a data science team standardizing on this process.

This page links to other pages detailing how to set up your project environment. The pages provided detail how to use Azure DevOps Projects, Azure Repos repositories, and Azure Boards. The motivating goal is moving from concept through modeling and into deployment.

Azure DevOps facilitates collaboration by integrating role-based security, work item management and tracking, and code hosting, sharing, and source control. 

## Structures of data science groups and teams
Data science functions in enterprises are often organized in the following hierarchy:

* Data science group
	* Data science team/s within the group
	
In such a structure, there are group leads and team leads. Typically, a data science project is done by a data science team. Data science teams have project leads for project management and governance tasks, and individual data scientists and engineers to perform the data science and data engineering parts of the project. The initial project setup and governance is done by the group, team, or project leads.

## Definition and tasks for the four roles in the Data Science Group
With the assumption that the data science group unit consists of teams, there are four distinct roles within the group :

**Group Manager**: Manages the entire data science unit in an enterprise. A data science unit might have multiple teams, each of which is working on multiple data science projects in distinct business verticals. A Group Manager might delegate their tasks to a surrogate, but the tasks associated with the role do not change.

**Team Lead**: Manages a team in the data science unit of an enterprise. A team consists of multiple data scientists. For a small data science unit, the Group Manager and the Team Lead might be the same person.

**Project Lead**: Manages the daily activities of individual data scientists on a specific data science project.

**Project Individual Contributors**: Data Scientists, Business Analysts, Data Engineers, Architects, and others who execute a data science project.


**[AZURE.NOTE]**: Depending on the structure and size of an enterprise, a single person may play more than one role, or more than one person may fill a role.

## Tasks to be completed by four roles

The following diagram shows the top-level tasks for each Team Data Science Process role. This schema and the following, more detailed outline of tasks for each role can help direct you to the page relevant to your role and associated repsonsibilities.

![PROJECT_EXECUTE](./media/overview-components-roles-tasks/overview-tdsp-top-level.png)

## Group Manager tasks

The following tasks are completed by the Group Manager (or a designated TDSP system administrator) to adopt the TDSP:

* Creates an Azure DevOps **organization** and a group project within the organization.
* Creates a **project template repository** in the Azure DevOps group project, and seeds it from the project template repository developed by the Microsoft TDSP team. The Microsoft TDSP project template repository provides:
	* A **standardized directory structure**, including directories for data, code, and documents.
	* A set of **standardized document templates** to guide an efficient data science process.
* Creates a **utility repository**, and seeds it from the utility repository developed by the Microsoft TDSP team. The TDSP utility repository from Microsoft provides a set of useful utilities to make the work of a data scientist more efficient. The Microsoft utility repository includes utilities for interactive data exploration, analysis, reporting, and baseline modeling and reporting.
* Sets up the **security control policy** for the organization account.

For detailed step-by-step instructions, see [Group Manager tasks for a data science team](group-manager-tasks.md). 


## Team Lead tasks

The Team Lead or a designated project administrator completes the following tasks to adopt the TDSP:

* Creates a team **project** in the group's Azure DevOps organization.
* Creates the **project template repository** in the project, and seeds it from the group project template repository set up by the Group Manager or delegate.
* Creates the **team utility repository**, seeds it from the group utility repository, and adds team-specific utilities to the repository.
* Optionally creates Azure file storage to store useful data assets for the team. Other team members can mount this shared cloud file store on their analytics desktops.
* Sets up **security control** by adding team members and configuring their permissions. 

For detailed step-by-step instructions, see [Team Lead tasks for a data science team](team-lead-tasks.md).  


## Project Lead tasks

The Project Lead completes the following tasks to adopt the TDSP:

* Creates a **project repository** in the team project, and seeds it from the project template repository.
* Optionally creates Azure file storage to store the project's data assets.
* Sets up **security control** by adding project members and configuring their permissions.

For detailed step-by-step instructions, see [Project Lead tasks for a data science team](project-lead-tasks.md). 

## Project Individual Contributor tasks

The Project Individual Contributor, usually a Data Scientist, conducts the following tasks using the TDSP:

* Clones the project repository set up by the project lead.
* Executes the project. 

For detailed step-by-step instructions for onboarding onto a project, see [Project Individual Contributors for a data science team](project-ic-tasks.md). 


## Data science project execution
 
By following the relevant set of instructions, data scientists, project leads, and team leads can create work items to track all tasks and stages for project from beginning to end. Using Azure Repos promotes collaboration among data scientists and ensures that the artifacts generated during project execution are version controlled and shared by all project members. Azure DevOps lets you link your Azure Boards work items with your Azure Repos repository branches and easily track what has been done for a work item.

The following figure outlines the TDSP workflow for project execution:

![Typical Data Science Project Execution](./media/overview-components-roles-tasks/overview-project-execute.png)

The workflow steps can be grouped into three activities:

* Project Leads conduct sprint planning
* Data Scientists develop artifacts on `git` branches to address work items
* Project Leads or other team members do code reviews and merge working branches to the primary branch

For detailed step-by-step instructions on project execution workflow, see [Execution of data science projects](agile-development.md).
