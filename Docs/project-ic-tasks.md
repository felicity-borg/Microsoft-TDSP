<properties
	pageTitle="Tasks for an individual contributor in the Team Data Science Process"
	description="Outlines the tasks that an individual contributor on a data science team is expected to complete."  
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


# Tasks for an individual contributor in the Team Data Science Process

This document outlines the tasks that an *individual contributor* completes to set up a project in the Team Data Science Process (TDSP). 

The following diagram shows the tasks that project individual contributors (data scientists) complete to set up their team environment. For instructions on how to execute a data science project under the TDSP, see [Execution of data science projects](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/agile-development.md).

![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/project-ic-tasks/project-ic-1-tdsp-data-scientist.png)

* **ProjectRepository** is the repository your project team maintains to share project templates and assets.
* **TeamUtilities** is the utilities repository your team maintains specifically for your team.
** *GroupUtilities* is the repository your group maintains to share useful utilities across the entire group.

## Prerequisites
This tutorial assumes that the following resources and permissions have been set up by your group manager, team lead, and project lead:

* The Azure DevOps **organization** for your data science unit
* A **project repository** set up by your project lead to share project templates and assets
* **GroupUtilities** and **TeamUtilities** repositories set up by the group manager and team lead, if applicable
* **Azure file storage** set up for shared assets for your team or project, if applicable
* **Permissions** for you to clone from and push back to your project repository

To clone repositories and modify content on your local machine or Azure ML notebooks, or mount Azure file storage, you need to consider this checklist:

* An Azure subscription.
* Git installed on your machine. 
* The Azure file storage information for any Azure file storage you need to mount or access from your Azure ML notebooks. 

## Clone repositories
To work with repositories locally and push your changes up to the shared team and project repositories, you first copy or `clone` the repositories to your local machine or Azure ML notebooks..

For instructions on how to clone the repository to your Azure ML notebooks click [here](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/gitIntegration.md).
For details on how to connect to storage services on Azue see [here](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-access-data). 
