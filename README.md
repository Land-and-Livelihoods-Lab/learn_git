# Learning git

## Getting started

### 1. Read the documents below and install git on your computer.

[About version control](http://git-scm.com/book/en/v2/Getting-Started-About-Version-Control)

[Installing git](http://git-scm.com/book/en/v2/Getting-Started-Installing-Git)

[Installing git (Github's guide)](https://github.com/git-guides/install-git)

Git basics, Chapter 2 of [this guide](http://git-scm.com/book/en/v2)

Basic branching and merging from the [same guide](http://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging)

#### Optional reading

[Command line reference](https://files.fosswire.com/2007/08/fwunixref.pdf)


### 2. Generate SSH key and add it to Github.

Follow [Github's guide for creating an SSH key](https://docs.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)


Follow [Github's guide for adding an SSH key to your account](https://docs.github.com/en/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account)


### 3. Open terminal and create a directory for git projects

For Mac, search and open the "Terminal" application. Once open, type:

    cd /Users/user/git_projects


For Windows, search and open the "Command prompt" program. Once open, type:

    cd C:/Users/user/git_projects


### 4. Clone the `learn_git` repository.

In the terminal type:

    git clone git@github.com:temporalecologylab/learn_git.git

You will not be able to clone this repository until you have uploaded your SSH key to Github.

In the terminal or your OS's file explorer, confirm that git has cloned this repository to your computer.


### 5. In the terminal, switch to `learn_git` folder (see step 4).

For example:

    cd learn_git
 
Note: Depending on your operating system, you may need to add `/` before or after the directory name.

### 6. Create branch "development_yourname".

In the terminal type:

    git branch development_yourname


### 7. Switch to the new branch.

In the terminal type:

    git checkout development_yourname

This ensures that any changes you make to the `learn_git` repository are restricted to the new branch.


### 8. Check the status of the repository on your computer. 

In the terminal type:

    git status

This will tell you what branch is currently checked out, if that branch is up to date, and whether there are any new files to pull from Github.

You should see a message like:

    On branch development_yourname
    nothing to commit, working tree clean


### 9. Create a new text file titled "yourname.txt".
 
The file should contain a few lines of text (anything you like). Save the file to the `learn_git` folder.

Now, if you type:

    git status

you should see a message like:

    On branch development_yourname
    Untracked files:

    (use "git add <file>..." to include in what will be committed)
    yourname.txt

    nothing added to commit but untracked files present (use "git add" to track)

As the message indicates, git knows the new file is there but it hasn't incorporated the file into the new branch yet. 


### 10. Add the file to the branch.

In the terminal type:

    git add yourname.txt


### 11. Check the status of the repository.

In the terminal type:

    git status

You should see a message like:

    On branch development_yourname
    Changes to be committed:

    (use "git restore --staged <file>..." to unstage)
    new file:   yourname.txt

This means the new file is ready to be committed to the new branch.


### 12. View the text of the file that is being added. 

In the terminal type:

    git diff --cached

You should see several different kinds of outputs (not covered here), including the text of the file you added.

Later, you can use `git diff` to view any modifications (additions or subtractions) to existing files.


### 13. Commit the changes to the new branch.

In the terminal type:

    git commit -m "your message here"

This commits your changes to the `development_yourname` branch (in this case, adding a new file) and the `-m` option adds a brief message describing the change (e.g. "added a file containing random text"). Such messages are essential for keeping track of changes in a repository.


### 14. Confirm that your changes have been committed.

In the terminal type:

    git status

You should see a message like:

    On branch development_yourname
    nothing to commit, working tree clean


### 15. Checkout the main branch.

In the terminal type:

    git checkout master

This will cause your file to disappear from your folder (go ahead and confirm this). 

Don't worry, git will restore it once you checkout the branch you were working on.


### 16. Restore the text file by checking out the development branch again.

In the terminal type:

    git checkout development_yourname


### 17. Finally, create a "pull request". 

In the terminal type:

    git push origin development_yourname

You should see a message like:

    Counting objects: 3, done.
    Delta compression using up to 8 threads.
    Compressing objects: 100% (2/2), done.
    Writing objects: 100% (3/3), 306 bytes | 306.00 KiB/s, done.
    Total 3 (delta 1), reused 0 (delta 0)
    remote: Resolving deltas: 100% (1/1), completed with 1 local object.
    remote:
    remote: Create a pull request for development_yourname> on GitHub by visiting:
    remote:
    https://github.com/temporalecologylab/learn_git/pull/new/development_yourname
    remote:
    To github.com:temporalecologylab/learn_git.git
    * [new branch]      development_yourname -> development_yourname

Visit the web address above (starting with https://github.com/temporalecologylab/learn_git/pull) to find a pop up where you can write out a title and description of the commit and submit a pull request. 

This will ask the maintainer of the `learn_git` repository to merge your new branch with the main branch on Github.

#

## Overview of general workflow

When contributing to an existing remote repository hosted on Github, you should first clone the repository to your local computer. To do so, see the example at the top of the page.

Once a repository has been cloned to your system and you are ready to contribute to it, it is recommend you follow these steps:

### Synchronize your repository with Github

Before doing new work, it is usually a good idea to synchronize your repository with the shared repository on Github. To do so:

#### 1. Check status by typing `git status`.

This will tell you what branch is currently checked out on your computer and whether you have made any changes that have not yet been committed. If you have just cloned the repository or have been diligent about committing and pushing changes appropriately, you should see the phrase:

    nothing to commit, working tree clean

If you see something else, for example an untracked file that you have previously added or modified, you should either remove/revert the file (if it is not important) or `git add` the file and make a new commit. Note that making a new commit at this stage may require a special `git merge`, especially if others have contributed to the repository since the last time you committed (see below for details).

#### 2. Fetch changes by typing `git fetch remotename`.

This will pull changes *from* Github to your computer, without overwriting your local copy of the repository. Replace `remotename` with the name assigned to the Github repository. By default, `git clone` chooses a name for you. If you do not know the name, type `git remote -v` to view it (name will be in the first column).

#### 3. View any changes by typing `git diff branch remotename/branch --stat`.

This compares the local `branch` with the remote `branch`. Replace `branch` with whatever branch you are working on (usually `master` or a `development` branch). The argument `--stat` shortens the output, displaying only the file names that have been changed. Remove it to see a more detailed comparison.

If the changes are acceptable, then:

#### 4. Update the local repository with `git pull remotename branch`.

Remove the warning message by setting pulls to be "fast forward" only, with 

    git config pull.ff only

#### Summary

    git status
	
	git fetch remotename
	
	(OPTIONAL) git diff branch remotename/branch --stat
		
	git pull remotename/branch
	
