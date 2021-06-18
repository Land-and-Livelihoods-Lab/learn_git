# Tips and Tricks

If you are just getting started with `git`, begin with [README.md](README.md)

[General Workflow][#General workflow]

[Quick commit - Main branch][#Quick commit - Main branch]

[Quick commit - Other branch][#Quick commit - Other branch]

[When all else fails][#When all else fails]

## General workflow

When contributing to an existing remote repository hosted on Github, you should first clone the repository to your local computer. To do so, see the example at the top of the page.

Once a repository has been cloned to your system, consider how you want to contribute to the repository. Two approaches are possible: 

(1) Work directly on the main branch. 

(2) Work on a temporary branch that eventually gets merged to the main branch.

In an industry setting, approach (1) is generally discouraged to allow for quality control (only changes that don't break existing code are allowed to be added to the main branch) and to avoid merge conflicts arising from many people working on the same code. These reasons are less relevant in an academic research context where groups tend to be smaller, quality control happens differently, and it is less common for multiple people to be working simultaneously on the same file. Thus, while approach (2) is recommend, either approach is acceptable.

### Working directly on the main branch

Here it is assumed that you have produced new work that does not conflict with existing work on the repository.

#### Synchronize your repository with Github

Before doing new work, it is usually a good idea to synchronize your repository with the shared repository on Github. To do so:

##### 1. Check status with `git status`

This will tell you what branch is currently checked out on your computer and whether you have made any changes that have not yet been committed. If you have just cloned the repository or have been diligent about committing and pushing changes appropriately, you should see the phrase:

    nothing to commit, working tree clean

If you see something else, for example an untracked file that you have previously added or modified, you should either remove/revert the file (if it is not important) or `git add` the file and make a new commit. Note that making a new commit at this stage may require a special `git merge`, especially if others have contributed to the repository since the last time you committed (see below for details).

##### 2. Fetch changes with  `git fetch remotename`

This will pull changes *from* Github to your computer, without overwriting your local copy of the repository. Replace `remotename` with the name assigned to the Github repository. By default, `git clone` chooses a name for you. 

If you do not know the name, type `git remote -v` to view it (name will be in the first column). You should see output like:

    github  git@github.com:temporalecologylab/learn_git.git (fetch)
    github  git@github.com:temporalecologylab/learn_git.git (push)

This indicates that `github` is the only `remotename` available and that it is currently set as the default *fetch* and *push* location. In other words, you could type `git fetch` and git would interpret this as `git fetch github`. 

##### 3. View changes with `git diff branch remotename/branch --stat`

This compares the local `branch` with the remote `branch`. Replace `branch` with whatever branch you are working on (usually `master` or a `development` branch). The argument `--stat` shortens the output, displaying only the file names that have been changed. Remove it to see a more detailed comparison.

If the changes are acceptable, then:

##### 4. Pull changes with `git pull remotename branch`

Remove the warning message by setting pulls to be "fast-forward" only, with `git config pull.ff only`.

##### 5. 


#### Summary

    git status   # Check status
	
	git fetch remotename   # Fetch changes
	
	git diff branch remotename/branch --stat   # View changes
		
	git pull remotename branch   # Pull changes
	
## When all else fails

Despite best efforts, things can and will go wrong. If you are facing a `git` problem with no clear solution (e.g., multiple merge conflicts), it may not be worth your time to solve it in the "correct", "`git`-approved" way. If you think this applies to you, the following steps will work in the sense that `git` will stop asking you to solve a problem and your work will be added to commit log. Note that since most `git` problems arise from people working on the same file at the same time, committing your changes in this way may end up "overwriting" changes made by someone else.

### 1. Save your new work outside the repository (i.e. outside the Github folder).

### 2. Delete the repository from your computer.

### 3. Clone the repository again from Github.

### 4. Copy your new work into the newly cloned folder.

### 5. Commit changes and push.


