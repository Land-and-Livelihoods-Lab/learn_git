# Tips and Tricks

If you are just getting started with `git`, begin with [README.md](README.md)

[General workflow](#general-workflow)

[Working on main branch - short version](#working-on-main-branch---short-version)

[Quick commit - Other branch][#Quick-commit-Other branch]

[When all else fails](#when-all-else-fails)

#

# General workflow

When contributing to an existing remote repository hosted on Github, you should first clone the repository to your local computer. To do so, see the example at the top of the page.

Once a repository has been cloned to your system, consider how you want to contribute to the repository. Two approaches are possible: 

**(A) Work directly on the main branch.**

**(B) Work on a temporary branch that eventually gets merged to the main branch.**

In an industry setting, approach **(A)** is usually discouraged to allow for quality control and to avoid excessive merge conflicts arising from many people working on the same code. These reasons are less relevant in an academic research context where groups tend to be smaller, quality control happens differently, and it is less common for multiple people to be working simultaneously on the same file. Thus, while approach **(B)** is recommend, either approach is acceptable.

### (A) Working directly on the main branch

Here it is assumed that you have produced new work that does not conflict with existing work on the repository. In other words, only you have made changes to the relevant file set. If other people have worked on the *same file set* since you last committed to the main branch, there will be a merge conflict and this approach will fail.

#### 1. Check the status of the local repository.

In the terminal type:

    git status

This will tell you what branch is currently checked out on your computer and whether you have made any changes that have not yet been committed. If you have just cloned the repository or have been diligent about committing and pushing changes appropriately, you should see the phrase:

    nothing to commit, working tree clean

#### 2. Fetch changes made to Github repository.

In the terminal type:

    git fetch remotename

This will pull changes *from* Github to your computer, without overwriting your local copy of the repository. Replace `remotename` with the name assigned to the Github repository. By default, `git clone` chooses a name for you (e.g., `github`).

If you do not know the name, type `git remote -v` to view it (name will be in the first column). You should see output like:

    github  git@github.com:temporalecologylab/learn_git.git (fetch)
    github  git@github.com:temporalecologylab/learn_git.git (push)

This indicates that `github` is the only `remotename` available and that it is currently set as the default *fetch* and *push* location. In other words, you could type `git fetch` and git would interpret this as `git fetch github`. 

#### 3. Optional: View differences between local and remote files.

In the terminal type:

`git diff branch remotename/branch --stat`

This compares the local `branch` with the remote `branch`. Replace `branch` with whatever branch you are working on (usually `master` or a `development` branch). The argument `--stat` shortens the output, displaying only the file names that have been changed. Remove it to see a more detailed comparison.

If the changes are acceptable, then:

#### 4. Pull changes from `remotename`.

In the terminal type:

    git pull remotename branch`

Remove the warning message by setting pulls to be "fast-forward" only, with `git config pull.ff only`.

#### 5. Stage your changes.

In the terminal type:

    git add filename.txt

Do this for all the new or edited files you have produced.

#### 6. Commit the changes.

In the terminal type:

    git commit -m "your message here"

#### 8. Push your changes to `remotename`.

In the terminal type:

    git push remotename master


### Working on main branch - short version

    git status   # Check status	
    
    git fetch remotename   # Fetch from remotename
    
    git diff master remotename/master --stat   # View changes
    
    git pull remotename master   # Pull changes from remotename
    
    git add filename.txt   # Stage changes
    
    git commit -m "your message here"   # Commit changes
    
    git push remotename master   # Push changes to remotename
	
#
#

## When all else fails

Despite best efforts, things can and will go wrong. If you are facing a `git` problem with no clear solution (e.g., multiple merge conflicts), it may not be worth your time to solve it in the "correct", "`git`-approved" way. If you think this applies to you, the following steps will work in the sense that `git` will stop asking you to solve a problem and your work will be added to commit log. Note that since most `git` problems arise from people working on the same file at the same time, committing your changes in this way may end up "overwriting" changes made by someone else.

### 1. Save your new work outside the repository (i.e. outside the Github folder).

### 2. Delete the repository from your computer.

### 3. Clone the repository again from Github.

### 4. Copy your new work into the newly cloned folder.

### 5. Commit changes and push.


