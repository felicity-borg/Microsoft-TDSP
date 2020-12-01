# Documentation to help you learn data science tools and help you execute a data science project in a systematic, version controlled, and collaborative way.

The sections **Roles and Tasks** and **Development** detail how to use the Team Data Science Process (TDSP), an agile iterative data science methodology for predictive analytics solutions and intelligent applications. This approach is recommended if you would like to set up the tools and frameworks for a larger project where a number of people will be contributing. For examples of organizations using TDSP see [New Signature](https://newsignature.com/services/), for a more detailed example see [Blue Granite](https://www.blue-granite.com/blog/getting-more-from-your-data-science-teams-organization-and-process-considerations).

If you would like instructions on how to get started on a small project such as a Proof of Concept or you would like to develop some experience using Azure DevOps, Azure ML and an IDE or text editor refer to pages in **Getting Started**.

**Getting Started** contains two options for code development: 
 * **Visual Studio Code**: VS Code is a fully featured text editor which includes debugging tools and other advanced features and extensions that improve code quality and      productivity when programming.
 * **Jupyter Notebooks**: Jupyter Notebooks are useful for setting global variables and displaying outputs in the same place as code e.g. when writing reports and when code is not to be re-used. 

Both can be used together to their strengths, e.g. complex code is written as a module (e.g. Python file containing class and function definitions) in VS code, and called from the jupyter notebook to set variables and display results.

	
# Documentation Contents

* [Overview](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/README.md)
* [Roles and Tasks](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/team-lead-tasks.md)
  * [Group manager](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/group-manager-tasks.md)
  * [Team lead](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/team-lead-tasks.md)
  * [Project lead](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/project-lead-tasks.md)
  * [Individual contributor](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/project-ic-tasks.md)
* Development
  * [Agile development](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/agile-development.md)
  * [Git repositories](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/createRepo.md)
  * [Integrating AzureML notebooks with Git](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/gitIntegration.md)
  * [Collaborative coding with git](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/collaboartive-Coding.md)
* Getting Started
  * [Azure ML Service Best Practices](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/azure-ml-best-practices.md)
  * [Option 1—Get Started with Visual Studio Code](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/get-started-with-vs-code.md)
  * [Option 2:1—Create a Machine Learning Workspace](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/azure-ml-workspace.md)
  * [Option 2:2—Get Started with Jupyter](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/GetStartedWithJupyter.md)
  * [Connect to data with the Azure Machine Learning studio](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/datastore-and-dataset.md)

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

This process has a lot of overlap with the Cross-industry Standard process for Data Mining (CRISP-DM) used by Peak Indicators, making the TDSP's components applicable to projects following the CRISP_DM lifecycle. As confirmed by [Microsft](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/overview); at a high level, these different methodologies have a lot in common.

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

Microsoft templates are provided in this GitHub repo to help provide folder structure and required documents in standard locations. This folder structure organizes the files that contain code for data exploration and feature extraction, and that record model iterations. These templates make it easier for team members to understand work done by others and to add new members to teams. It is easy to view and update document templates in markdown format. Use templates to provide checklists with key questions for each project to insure that the problem is well defined and that deliverables meet the quality expected. Examples include:

* a project charter to document the business problem and scope of the project
* data reports to document the structure and statistics of the raw data
* model reports to document the derived features
* model performance metrics such as ROC curves or MSE

![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/overview/tdsp-dir-structure.png)

The directory structure can be cloned from [GitHub](https://github.com/Azure/Azure-TDSP-ProjectTemplate).

## Infrastructure and resources for data science projects

TDSP provides recommendations for managing shared analytics and storage infrastructure such as:

* cloud file systems for storing datasets
* databases
* big data (SQL or Spark) clusters
* machine learning service

he analytics and storage infrastructure, where raw and processed datasets are stored, may be in the cloud or on-premises. This infrastructure enables reproducible analysis. It also avoids duplication, which may lead to inconsistencies and unnecessary infrastructure costs. Tools are provided to provision the shared resources, track them, and allow each team member to connect to those resources securely. It is also a good practice to have project members create a consistent compute environment. Different team members can then replicate and validate experiments.

Here is an example of a team working on multiple projects and sharing various cloud analytics infrastructure components.

![](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/media/overview/tdsp-analytics-infra.png)

## Tools and utilities for project execution

Introducing processes in most organizations is challenging. Tools provided to implement the data science process and lifecycle help lower the barriers to and increase the consistency of their adoption. TDSP provides an initial set of tools and scripts to jump-start adoption of TDSP within a team. It also helps automate some of the common tasks in the data science lifecycle such as data exploration and baseline modeling. There is a well-defined structure provided for individuals to contribute shared tools and utilities into their team's shared code repository. These resources can then be leveraged by other projects within the team or the organization. Microsoft provides extensive tooling inside Azure Machine Learning supporting both open-source (Python, R, ONNX, and common deep-learning frameworks) and also Microsoft's own tooling (AutoML).

### Next steps 
[Team Data Science Process: Roles and tasks](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/roles-tasks.md) outlines the key personnel roles and their associated tasks for a data science team that standardizes on this process.


