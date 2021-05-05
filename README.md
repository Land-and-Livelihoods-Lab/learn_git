# Learning git

## 1. Read the documents below and install git on your computer.

About version control:

http://git-scm.com/book/en/v2/Getting-Started-About-Version-Control

Installing git:

http://git-scm.com/book/en/v2/Getting-Started-Installing-Git
https://github.com/git-guides/install-git

All of Chapter 2 - Git basics:

http://git-scm.com/book/en/v2

Basic branching and merging:

http://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging

## 2. Generate SSH key and add it to Github.

Start here:

https://docs.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent

## 3. Create a directory for git projects (e.g., "git_projects") and visit in the terminal.

For Linux:

> cd /home/user/git_projects

For macOS:

> cd /Users/user/git_projects

For Windows:

> cd C:/Users/user/git_projects

## 4. Clone the `learn_git` repository.

In the terminal type:

> git clone git@github.com:temporalecologylab/learn_git.git

You will not be able to clone this repository until you have uploaded your SSH key to Github.

In the terminal or your OS's file explorer, confirm that git has cloned this repository to your computer.

## 5. In the terminal, switch to `learn_git` folder using "cd" (see step 3).

For example:

> cd learn_git
 
 
## 6. Create branch "development_yourname".

In the terminal type:

> git branch development_yourname

## 7. Switch to the new branch 

In the terminal type:

> git checkout development_yourname

This ensures that any changes you make to the `learn_git` repository are restricted to the new branch.

## 8. Check the status of the repository on your computer. 

In the terminal type:

> git status

This will tell you what branch is currently checked out, whether that branch is up to date, and whether there are any new files to pull from Github.

## 9. Create a new text file titled "yourname.txt".
 
 The file should contain a few lines of text (anything you like). Save the file to the `learn_git` folder.

## 10. Add the file to the repository.

In the terminal type:

> git add <yourname>.txt

## 11. Check the status of the repository.

In the terminal type:

> git status

You should see something indicating that a new change is to be committed, specifically the addition of a new file.

## 12. View the text of the file that is being added. 

In the terminal type:

> git diff --cached

Later, you can use `git diff` to view any modifications (additions or subtractions) to existing files.

## 13. Commit the changes to the new branch.

In the terminal type:

> git commit

You will see an editor pop with a message like this:

> Please enter the commit message for your changes. Lines starting
> with '#' will be ignored, and an empty message aborts the commit.
> On branch master
> Your branch is up-to-date with 'origin/master'.
> 
> Changes to be committed:
> new file:  yourname.txt

Assuming the editor that pops up is Vim:

i. Type "i" to begin writing out a description commit message (e.g., "added file with random text")

ii. Press `Esc`

iii. Type ":wq" then press `Enter`

## 14. Confirm that your changes have been committed.

In the terminal type:

> git status

## 15. Checkout the main branch.

In the terminal type:

> git checkout master

This will cause your file to disappear from your folder (go ahead and confirm this). 

Don't worry, git will restore it once you checkout the branch you were working on.

## 16. Restore the text file by checking out the development branch again.

In the terminal type:

> git checkout development_yourname

## 17. Finally, create a "pull request". 

In the terminal type:

> git push origin development_yourname

This will ask the maintainer of the `learn_git` repository to merge your new branch with the main branch on Github.
