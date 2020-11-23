# Integrating AzureML notebooks with Git

To integrate code in Jupyter lab notebooks in GIT the recommended approach by Microsoft is to use a GIT command-line. 
The steps requrd to do this is shown and documented below. For more details on the Git command-line refer [here](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/createRepo.md) page. 

![](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/media/resources/git-integration.PNG)
*Process used to integrate the code in GIT*

**GIT Clone—clone the repo to your computer**
To work with a Git repo, you need to clone the repo you will be working on for this project to your computer. Cloning a repo creates a complete local copy of the repo for you to work with, and downloads all commits and branches in the repo and sets up a named relationship with the repo on the server. Use this relationship to interact with the existing repo, pushing and pulling changes to share code with your team.

1. From your web browser, open the team project for your organization in Azure DevOps and select **Repos > Files**. If you don't have a team project, create one now.
For details on how to create a Git repo for your project click [here](https://github.com/felicity-borg/Microsoft-TDSP/blob/master/Docs/createRepo.md).
![](https://docs.microsoft.com/en-us/azure/devops/repos/get-started/media/clone-repo/repos-files.png?view=azure-devops)

2. Select **Clone** in the upper-right corner of the **Files** window and copy the clone URL; if there is a password ensure you take a note of this as you will need it in the next step. 
![](https://docs.microsoft.com/en-us/azure/devops/repos/get-started/media/clone-repo/clone-repo.png?view=azure-devops)

3. Access Azure ML JupyterLab and open a terminal Session. Run `git clone` followed by the followed by the path copied from the Clone URL in the previous section, as shown in the following example.
`git clone https://dev.azure.com/fabrikam-fiber/MyFirstProject/_git/`

If it asks for a password, paste the password shown in Azure DevOps Clone Repositiory screen in the step above. Press **Enter**. 
Git downloads a copy of the code, including all commits and branches from the repo, into a new folder for you to work with.

4. Switch your directory to the repository that you cloned. For e.g. 

`cd fabrikam-fiber`

## Work with the code

An exampe of how working with Git to save work with `commit` and sharing code with `push`. 

1. Navigate to one of the Jupyter Lab notebooks containing code and make some changes 'for e.g. add a comment `#testing my first edit`in one of the cells

2. Navigate back to the terminal and ensure you are still in the directory of the repository you cloned. 

3. Commit your changes by entering the following command in the Git command window, i.e. your terminal. 

`git commit -a -m "My first commit"`

When using `git commit`, `-a` means to commit all changed files, and `-m` specifies a commit message.

4. Push your changes up to the Git repo on the server by entering the following command into the Git command window:

`git push`. 

5. Switch back to the web portal and select **History** from the **Code** view to view your new commit. The new repo should the commit you just made to your notebook.

for more details on working with Git commands click [here](https://docs.microsoft.com/en-us/azure/devops/repos/git/?view=azure-devops).
