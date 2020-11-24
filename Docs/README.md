<properties
	pageTitle="What is the Team Data Science Process?"
	description="An outline of the key components of the Team Data Science Team."  
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
	ms.date="09/22/2016"
	ms.author="bradsev;hangzh;deguhath"/>

# What is the Team Data Science Process?

The Team Data Science Process (TDSP) is an agile, iterative data science methodology to deliver predictive analytics solutions and intelligent applications efficiently. TDSP helps improve team collaboration and learning by suggesting how team roles work best together. TDSP includes best practices and structures from Microsoft and other industry leaders to help toward successful implementation of data science initiatives. The goal is to help companies fully realize the benefits of their analytics program.

This document provides an overview of TDSP and its main components. A generic description of the process is provided here and can be implemented with different kinds of tools. A more detailed description of the project tasks and roles involved in the lifecycle of the process is provided in additional linked documents. Guidance on how to implement the TDSP using a specific set of Microsoft tools and infrastructure is also provided.


## Key components of the TDSP
TDSP has the following key components:

* A **data science lifecycle** definition
* A **standardized project** structure
* **Infrastructure and resources** recommended for data science projects
* **Tools and utilities** recommended for project execution

## Data science lifecycle
The Team Data Science Process (TDSP) provides a lifecycle to structure the development of your data science projects. The lifecycle outlines the full steps that successful projects follow.

This process has a lot of overlap with the Cross-industry Standard process for Data Mining (CRISP-DM) used by Peak, making the TDSP's components applicable to projects following the CRISP_DM lifecycle. As confirmed by [Microsft](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/overview); at a high level, these different methodologies have a lot in common.

This lifecycle has been designed for data science projects that ship as part of intelligent applications. These applications deploy machine learning or artificial intelligence models for predictive analytics. Exploratory data science projects or improvised analytics projects can also benefit from using this process. But in such cases some of the steps described may not be needed.

The lifecycle outlines the major stages that projects typically execute, often iteratively:

* Business Understanding
* Data Acquisition and Understanding
* Modeling
* Deployment
Here is a visual representation of the **Team Data Science Process lifecycle**.

![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/overview/tdsp-lifecycle2.png)


The goals, tasks, and documentation artifacts for each stage of the lifecycle in TDSP are described in the Team Data Science Process lifecycle topic. These tasks and artifacts are associated with project roles:

* Solution architect
* Project manager
* Data engineer
* Data scientist
* Application developer
* Project lead
The following diagram provides a grid view of the tasks (in blue) and artifacts (in green) associated with each stage of the lifecycle (on the horizontal axis) for these roles (on the vertical axis).

![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/overview/tdsp-tasks-by-roles.png)

## Standardized project structure
Having all projects share a directory structure and use templates for project documents makes it easy for the team members to find information about their projects. All code and documents are stored in a version control system (VCS) like Git, to enable team collaboration. Tracking tasks and features in an agile project tracking system like Jira, Rally, and Azure DevOps allows closer tracking of the code for individual features. Such tracking also enables teams to obtain better cost estimates. TDSP recommends creating a separate repository for each project on the VCS for versioning, information security, and collaboration. The standardized structure for all projects helps build institutional knowledge across the organization.

Microsoft templates are provided in this GitHib repo to help provide folder structure and required documents in standard locations. This folder structure organizes the files that contain code for data exploration and feature extraction, and that record model iterations. These templates make it easier for team members to understand work done by others and to add new members to teams. It is easy to view and update document templates in markdown format. Use templates to provide checklists with key questions for each project to insure that the problem is well defined and that deliverables meet the quality expected. Examples include:

* a project charter to document the business problem and scope of the project
* data reports to document the structure and statistics of the raw data
* model reports to document the derived features
* model performance metrics such as ROC curves or MSE

![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/overview/tdsp-dir-structure.png)

The directory structure can be cloned from [GitHub](https://github.com/Azure/Azure-TDSP-ProjectTemplate).
