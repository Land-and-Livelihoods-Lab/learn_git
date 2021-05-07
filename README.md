# Learning git

### 1. Read the documents below and install git on your computer.

[About version control](http://git-scm.com/book/en/v2/Getting-Started-About-Version-Control)

[Installing git](http://git-scm.com/book/en/v2/Getting-Started-Installing-Git)

[Installing git (Github's guide)](https://github.com/git-guides/install-git)

Git basics, Chapter 2 of [this guide](http://git-scm.com/book/en/v2)

Basic branching and merging from the [same guide](http://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging)

#### Optional

[Command line reference](https://files.fosswire.com/2007/08/fwunixref.pdf)


### 2. Generate SSH key and add it to Github.

See [Github's guide for creating an SSH key](https://docs.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)


See [Github's guide for adding an SSH key to your account](https://docs.github.com/en/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account)

### 3. Open the terminal (Mac, Linux) or command prompt (Windows).

For Mac, search for the "Terminal" app.


For Windows, search for "Command prompt".


### 4. Create a directory for git projects (e.g., "git_projects") and visit in the terminal.

For Mac, type:

    cd /Users/user/git_projects


For Windows, type:

    cd C:/Users/user/git_projects


### 5. Clone the `learn_git` repository.

In the terminal type:

    git clone git@github.com:temporalecologylab/learn_git.git

You will not be able to clone this repository until you have uploaded your SSH key to Github.

In the terminal or your OS's file explorer, confirm that git has cloned this repository to your computer.


### 6. In the terminal, switch to `learn_git` folder (see step 4).

For example:

    cd learn_git
 
Note: Depending on your operating system, you may need to add `/` before after the directory name.

### 7. Create branch "development_yourname".

In the terminal type:

    git branch development_yourname


### 8. Switch to the new branch.

In the terminal type:

    git checkout development_yourname

This ensures that any changes you make to the `learn_git` repository are restricted to the new branch.


### 9. Check the status of the repository on your computer. 

In the terminal type:

    git status

This will tell you what branch is currently checked out, if that branch is up to date, and whether there are any new files to pull from Github.

You should see a message like:

    On branch development_yourname
    nothing to commit, working tree clean


### 10. Create a new text file titled "yourname.txt".
 
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


### 11. Add the file to the branch.

In the terminal type:

    git add yourname.txt


### 12. Check the status of the repository.

In the terminal type:

    git status

You should see a message like:

    On branch development_yourname
    Changes to be committed:

    (use "git restore --staged <file>..." to unstage)
    new file:   yourname.txt

This means the new file is ready to be committed to the new branch.


### 13. View the text of the file that is being added. 

In the terminal type:

    git diff --cached

You should see several different kinds of outputs (not covered here), including the text of the file you added.

Later, you can use `git diff` to view any modifications (additions or subtractions) to existing files.


### 14. Commit the changes to the new branch.

In the terminal type:

    git commit -m "your message here"

This commits your changes to the `development_yourname` branch (in this case, adding a new file) and the `-m` option adds a brief message describing the change (e.g. "added a file containing random text"). Such messages are essential for keeping track of changes in a repository.


### 15. Confirm that your changes have been committed.

In the terminal type:

    git status

You should see a message like:

    On branch development_yourname
    nothing to commit, working tree clean


### 16. Checkout the main branch.

In the terminal type:

    git checkout master

This will cause your file to disappear from your folder (go ahead and confirm this). 

Don't worry, git will restore it once you checkout the branch you were working on.


### 17. Restore the text file by checking out the development branch again.

In the terminal type:

    git checkout development_yourname


### 18. Finally, create a "pull request". 

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

Visit the web address above (starting with https) to find a pop up where you can write out a title and description of the commit and submit a pull request. 

This will ask the maintainer of the `learn_git` repository to merge your new branch with the main branch on Github.

