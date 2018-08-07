# Git Basic Concepts
## Before You Begin
### Create a GitHub Account
If you don't already have a GitHub account, go to https://github.com and create a new account. You should only use one account for all of your projects. GitHub has other mechanisms for separating personal projects from work projects.
### Download GitHub Desktop
Go to https://desktop.github.com/ and download the appropriate version for your OS.
## 1.1 Initialize a new Repository
To begin, we will create a new repository on our GitHub account.
1. From the splash screen or the **File** menu, select **Create new repository**

2. Fill out the fields for the new repository to be created.
	
	1. Give your new repository a name. Valid Git repository names don't have spaces, so if you attempt to give it a name with spaces it will change those spaces to dashes, e.g. "GitHub Tutorial" will be changed to "GitHub-Tutorial".
	
	2. Give your new repository a meaningful description.
	
	3. Choose a local directory for your new repository.
	
	4. Most software projects require documentation, and the easiest place to do that in GitHub is in the "README.md" file. If you want to create this file when you create repository, check the box.
	
	5. The Git ignore file tells a repository what files it should not track. For LabVIEW, we probably don't want to track imported libaries, shared objects, executables, or metadata. These files can be identified as files to ignore using their file extensions in the Git ignore file. We could manually create this file later from scratch, but GitHub already provides a nice template for LabVIEW that includes all of the relevant file types to exclude.
	
	6. **You MUST provide a license for your code.** If you intend to share this code, you should select MIT License or Apache License 2.0. If you don't select a license, then your code is considered unlicensed and get us in legal hot water. **ALWAYS PROVIDE A LICENSE**.
	
	7. Select **Create Repository**.
	
	8. Navigate to the local folder on your computer and observe the files that were created. The shortcut for this from GitHub Desktop is **Repository >> Show in Explorer (CTRL+SHIFT+F)**.
	
	9. Go to your GitHub page online and observe the files that were created. A shortcut from GitHub Desktop to view the repo online in a browser is **Repository >> View on GitHub (CTRL+SHIFT+G)**.


## 1.2 Adding a File and Committing
Create a new file and commit it.
1. Create a new simple LabVIEW VI in your local repository folder called "Hello World.vi".

![](../src/images/Hello_World_BD.png "Hello World.vi")

2. In Github Desktop, see in the Changes tab that the new file has been detected, but not yet committed.

![](../src/images/New_VI.png "New VI Detected")

3. To commit the file to the repo:

	1. A summary is required. Example: Add Hello World.vi
	
	2. The description, which is optional, can be used to add more details about the commit. Example: New VI that shows a message with a one-button dialog.
	
	3. Click **Commit to master** to complete the commit.
	
	![](../src/images/New_File_Commit.png "Commit New File")
	
## 1.3 Committing Changes
A commit is change to a file or set of files, it can be thought of as a revision.
1. Make a change to the Hello World LabVIEW VI you created in 1.3. For example, change the string constant to a string control and connect the string control to the connector pane.

![](../src/images/Hello_World_Mod_FP.png "Front Panel of Hello World.vi")
![](../src/images/Hello_World_Mod_BD.png "Block Diagram of Hello World.vi")

2. GitHub Desktop will automatically detect the changes made in the LabVIEW VI. These changes will be staged in the **Changes** tab. The yellow dot icon indicates that changes have been made to the file.

![](../src/images/Change_VI.png "Changes Reflected By Yellow Dot Icon")

3. Create another new LabVIEW VI, "Simple Add.vi". From GitHub Desktop staged changes, you will be able to see that the new file is also automatically detected and will show up with a green plus icon to indicate that it is a new file.

4. Commit the changes. Multiple changes can be committed together or separately. Use the checkboxes beside each staged difference in the Changes tab to select which changes you would like to commit.

	1. Commit **only** the change to "Hello World.vi" by unchecking the checkbox next to the "Simple Add.vi". Add summary and description and click **Commit to master**.
	
	![](../src/images/Commit_Hello_World_Change.png "Commit Changes to Hello World.vi")
	
	2. Commit the remaining change, which adds "Simple Add.vi" to the repo.
	
	![](../src/images/Commit_Simple_Add.png "Commit New VI Simple Add.vi")
	
## 1.4 History
We can view information on past commits from GitHub Desktop.
1. Click the **History** tab in GitHub Desktop and click on a commit to get more details about it.

![](../src/images/History.png "History in GitHub Desktop")

1. Commit summary.
2. Commit description.
3. A unique ID is created for every commit. This is sometimes called the SHA or the hash.

## 1.5 Publishing Your Repository to GitHub.com
You have already heard of GitHub.com, where you created your GitHub account. Up until this point, what we have been doing is using the version control software Git to track changes on our computer. This makes our computer into a Git server. The files still only exist in one place: On our machine.

GitHub.com is a web-based hosting service that we can push repositories to. This explores additional benefits of using Git besides change tracking, such as:
* Create backups of our work.
* Coordinate multiple users working on one project.

1. Click **Publish repository** to publish your repository to GitHub.com. GitHub desktop offers the option to keep your code private, but uncheck this, as private repos are only available to paying users on GitHub.com. Your repo will be viewable to the public after it is uploaded to the GitHub.com servers.

![](../src/images/Current_Branch.png "Publish Repository to GitHub.com")

Now, a copy of your repository (your project folder) has been "pushed" to the GitHub servers and is accessible to the public via GitHub.com. Go to your GitHub page online and observe the files that were created. A shortcut from GitHub Desktop to view the repo online in a browser is **Repository >> View on GitHub (CTRL+SHIFT+G)**. Now that it is hosted on GitHub.com, additional changes can be pushed from you as well as other users of GitHub. We will next cover how to manage access and conflicting changes.

## 1.6 Fetching and Pulling
Notice the top bar now says **Fetch origin** with a time. Fetching means detecting the latest changes from an online repo, but it does not automatically merge these changes into the local repo. With the "last fetched" time, GitHub Desktop is indicating to us the time that it last connected with the GitHub.com repository. When it detects changes, it will give you the option to pull. Pulling (**Repository >> Pull**) will take changes from the remote online repo and apply them to your local repo files.

If you are working on a project with multiple users making changes, you can see how it is very crucial that you pull from the main repository that everyone is working from before starting your own changes (e.g. adding a feature or fixing a bug). Otherwise, you may not be working with the most up-to-date version of the project. We will illustrate this by making a change in the repository hosted on GitHub.com and seeing how pulling looks in the GitHub Desktop application on your computer following these changes.

1. Launch your repository page on GitHub.com in a browser. You can either navigate to this from GitHub.com, or from GitHub Desktop, use **Repository >> View on GitHub** (CTRL+SHIFT+G).

2. We will edit the "README.md" file. GitHub.com provides a built-in text editing tool. This simulates a change to the repo that may have been pushed by another user. Click on "README.md" and then click the pencil icon on the right that launches the GitHub.com text editor. The file extension ".md" stands for Markdown, a lightweight markup language.

![](../src/images/Edit_in_GitHub.png "Edit Markdown file in GitHub")

3. Add text to the "README.md" file and commit your changes with the box below the editor. Note that we are still working in the branch **Third-Sum-Edit**.

4. Go back to GitHub Desktop. You will see that the button that previously said **Fetch origin** now says **Pull origin**. Click this to apply the change to your local repo.

![](../src/images/Pull_Origin.png "Pull From Remote Repo")

5. Navigate to the "README.md" file on your computer and open it. You will see that the changes you made in GitHub.com are now reflected in this copy of the file as well. You can also see from the **History** tab that the revision has been added to the list of commits for the branch.

## 1.7 Pushing
Up until this point we have explored how to pull the most up-to-date version of the remote repo onto your computer. The next step is to make a change to your local repo and push it back to the remote repo.

1. Open "README.md" in your local repo. Add text to the file and save the changes.

2. From GitHub Desktop, commit the changes.

3. Use the **Push origin** button to push changes to the remote repo.

4. Open the repo hosted on GitHub.com (CTRL+SHIFT+G) and see that the changes you made are reflected in the "README.md" file there.

Allowing multiple users to push to a single remote repo in this manner will very quickly start to get messy. It creates the possibility of overwriting someone else's changes. Next, we introduce branches and pull requests as methods to control access to a repo and organize changes made by multiple users working on one repo.

## 1.8 Branches and Pull Requests
Creating a branch creates a parallel version of the **master** (primary or default) branch. Making changes in this new branch will not disrupt the master branch, and the changes made in the new branch can be merged back into the master branch when the developer is ready.
1. Create a new branch from GitHub Desktop with **Branch >> New branch** (CTRL+SHIFT+N). It will ask for a name, call it "Third-Sum-Edit". This will be the branch in which we add a new feature: Add a third number to the summation in Simple Add.vi.

![](../src/images/New_Branch_Third-Sum-Edit.png "Create New Branch")

2. Add a third number to the calculation in LabVIEW VI Simple Add.vi.

![](../src/images/Third_Sum_Edit_Simple_Add.png "Add Third Addend to Simple Add VI")

3. Commit the changes to the branch.
	1. Check that you are in the correct branch from the top menu that reads "**Current branch**. It is very important that we commit to the correct branch, as committing to the **master** branch will edit the primary copy, and that may affect the other users accessing it.
	2. Add a summary and description for the commit.
	
	![](../src/images/Commit_Third-Sum-Edit.png "Commit changes to Simple Add VI to the new branch Third-Sum-Edit.")
	
	3. Notice that the commit button now reads **Commit to Third-Sum-Edit**, instead of **Commit to master**. Commit to the branch.

4. From the **Current Branch** menu on the top bar, switch back to **master** branch and view the **History** tab. There, you can confirm that these changes we committed to the branch are not reflected in the **master** branch. Be sure to switch back to **Third-Sum-Edit** branch before continuing, as we want to keep working in this branch.
	
## 1.2 Checking the Status
## 1.3 Adding a File and Committing
## 1.4 Adding Changes
## 1.5 Checking for Changes
## 1.6 Committing
## 1.7 Adding All Changes
## 1.8 Committing All Changes
## 1.9 History
## 1.10 Remote Repositories
## 1.11 Pushing Remotely
## 1.12 Pulling Remotely
## 1.13 Differences
## 1.14 Staged Differences
## 1.15 Staged Differences (cont'd)
## 1.16 Resetting the Stage
## 1.17 Undo
## 1.18 Branching Out
## 1.19 Switching Branches
## 1.20 Removing All The Things
## 1.21 Committing Branch Changes
## 1.22 Switching Back to master
## 1.23 Preparing to Merge
## 1.24 Keeping Things Clean
## 1.25 The Final Push
