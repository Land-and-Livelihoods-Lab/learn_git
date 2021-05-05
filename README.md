# Learning git

1. Read the following documents and install git:

About version control
http://git-scm.com/book/en/v2/Getting-Started-About-Version-Control

Installing git
http://git-scm.com/book/en/v2/Getting-Started-Installing-Git
https://github.com/git-guides/install-git

All of Chapter 2 - Git basics
http://git-scm.com/book/en/v2

Basic branching and merging
http://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging

2. Generate an SSH key and add it to Github. Start here: 
https://docs.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent

3. Create a new directory for git projects (e.g., "git_projects").

3. In the terminal / command line, go to the new directory.

For Linux:

$ cd /home/user/git_projects

For macOS:

$ cd /Users/user/git_projects

For Windows:

$ cd C:/Users/user/git_projects

4. Clone the "learn_git" repository.

$ git clone git@github.com:temporalecologylab/learn_git.git

You will not be able to clone this repository until you have uploaded your SSH key to Github.

5. In the terminal or your OS's file explorer, confirm that git has cloned this repository to your computer.

6. In the terminal, switch to the learn_git folder using "cd" as above (see step 3).
 
7. Create a branch "development_<yourname>".

$ git branch development_<yourname>

8. Switch to the branch you just created so that any changes you make to learn_git repository are restricted to the new branch.

$ git checkout development_<yourname>

9. Check the status of the repository on your computer. This will tell you what branch is currently checked out, whether that branch is up to date, and whether there are any new files to pull from Github.

$ git status

10. Now that the new branch is checked out, create a new text file titled "<yourname>.txt" containing a few lines of text (anything you like). Save the file to the learn_git folder.

11. Tell git to add the file to the repository.

$ git add <yourname>.txt

12. Check the status of the repository. You could see something indicating that a new changes is to be committed, specifically the addition of a new file.

$ git status

13. View the text of the file that is being added. Later, you can use this to view any modifications (additions or subtractions) to existing files.

$ git diff --cached

13. Commit the changes to the new branch.

$ git commit

You will see an editor pop with a message like this:

$ # Please enter the commit message for your changes. Lines starting
$ # with '#' will be ignored, and an empty message aborts the commit.
$ # On branch master
$ # Your branch is up-to-date with 'origin/master'.
$ #
$ # Changes to be committed:
$ #	new file:   README
$ #	modified:   CONTRIBUTING.md

Assuming the editor that pops up is Vim:
i. Type "i" to begin writing out a description commit message (e.g., "added file with random text")
ii. Press `Esc`
iii. Type ":wq" then press `Enter`

14. Confirm that your changes have been committed.

$ git status

15. Now, checkout the main branch. This will cause your file to disappear. Don't worry, git will restore it once you checkout the branch you were working on.

$ git checkout master

16. Confirm that the text file you added previously has disappeared.

17. Restore the text file by checking out the development branch again.

$ git checkout development_<yourname>

18. Finally, create a "pull request". This will ask the maintainer of the learn_git repository to merge your new branch with the main branch on Github.

$ git push origin development_<yourname>
