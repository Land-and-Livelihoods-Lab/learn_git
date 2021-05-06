# Learning git

## Prerequisites 

Choose a text editor and make sure it is installed on your system. 

Text editors are programs that edit files with text in them. Usually they have handy markups, autocomplete, and key-bindings (or shortcuts). 

Notable editors include: [Emacs](https://www.gnu.org/software/emacs/), [Vim](https://www.vim.org/), and [Nano](https://www.nano-editor.org/).

Most computers will already have at least one of these programs installed (Windows = Vim, macOS = Vim or Emacs).


### 1. Read the documents below and install git on your computer.

[About version control](http://git-scm.com/book/en/v2/Getting-Started-About-Version-Control)

[Installing git](http://git-scm.com/book/en/v2/Getting-Started-Installing-Git)

[Installing git (Github's guide)](https://github.com/git-guides/install-git)

Git basics, Chapter 2 of [this guide](http://git-scm.com/book/en/v2)

Basic branching and merging from the [same guide](http://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging)


### 2. Generate SSH key and add it to Github.

See [Github's guide](https://docs.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)

### 3. Open the terminal (macOS, linux) or command prompt (Windows).

For macOS, type:

> `CTRL` + `c`


For Windows, search for "Command prompt"


### 4. Create a directory for git projects (e.g., "git_projects") and visit in the terminal.

For Linux:

> cd /home/user/git_projects


For macOS:

> cd /Users/user/git_projects


For Windows:

> cd C:/Users/user/git_projects


### 5. Clone the `learn_git` repository.

In the terminal type:

> git clone `git@github.com:temporalecologylab/learn_git.git`

You will not be able to clone this repository until you have uploaded your SSH key to Github.

In the terminal or your OS's file explorer, confirm that git has cloned this repository to your computer.


### 6. In the terminal, switch to `learn_git` folder using "cd" (see step 4).

For example:

> cd learn\_git
 
 
### 7. Create branch "development_yourname".

In the terminal type:

> git branch development_yourname


### 8. Switch to the new branch.

In the terminal type:

> git checkout development_yourname

This ensures that any changes you make to the `learn_git` repository are restricted to the new branch.


### 9. Check the status of the repository on your computer. 

In the terminal type:

> git status

This will tell you what branch is currently checked out, whether that branch is up to date, and whether there are any new files to pull from Github.

You should see a message like:

> On branch development_yourname

> nothing to commit, working tree clean


### 10. Create a new text file titled "yourname.txt".
 
The file should contain a few lines of text (anything you like). Save the file to the `learn_git` folder.

Now, if you type:

> git status:

you should see a message like:

> On branch development_yourname
> Untracked files:

>  (use "git add <file>..." to include in what will be committed)

>        yourname.txt

> nothing added to commit but untracked files present (use "git add" to track)

As the message indicates, git knows the new file is there but it hasn't incorporated the file into the new branch yet. 


### 11. Add the file to the branch.

In the terminal type:

> git add yourname.txt


### 12. Check the status of the repository.

In the terminal type:

> git status

You should see a message like:

> On branch development_yourname

> Changes to be committed:

>  (use "git restore --staged <file>..." to unstage)

>        new file:   yourname.txt

This means the new file is ready to be added ("committted") to the new branch.


### 13. View the text of the file that is being added. 

In the terminal type:

> git diff --cached

You should see several different kinds of outputs (not covered here), among them should be the text of the file you added.

Later, you can use `git diff` to view any modifications (additions or subtractions) to existing files.


### 14. Commit the changes to the new branch.

In the terminal type:

> git commit

You will see an editor pop with a message like this:

> Please enter the commit message for your changes. Lines starting

> with '#' will be ignored, and an empty message aborts the commit.

> On branch development_yourname

> Your branch is up-to-date with 'origin/master'.

> 

> Changes to be committed:

> new file:  yourname.txt


Assuming the editor that pops up is Vim:

i. Type "i" to begin writing out a description commit message (e.g., "added file with random text")

ii. Press `Esc`

iii. Type ":wq" then press `Enter` (note: ":wq" means write and quit)

Note: Vim has different editing modes that are activated by typing certain keys, which is nice for expert users but can be frustrating to first timers. If you get stuck, typing ":q" or ":quit" is often effective for quitting a window.


### 15. Confirm that your changes have been committed.

In the terminal type:

> git status

You should see a message like:

> On branch development_yourname

> nothing to commit, working tree clean


### 16. Checkout the main branch.

In the terminal type:

> git checkout master

This will cause your file to disappear from your folder (go ahead and confirm this). 

Don't worry, git will restore it once you checkout the branch you were working on.


### 17. Restore the text file by checking out the development branch again.

In the terminal type:

> git checkout development_yourname


### 18. Finally, create a "pull request". 

In the terminal type:

> git push origin development_yourname

You should see a message like:

> Counting objects: 3, done.

> Delta compression using up to 8 threads.

> Compressing objects: 100% (2/2), done.

> Writing objects: 100% (3/3), 306 bytes | 306.00 KiB/s, done.

> Total 3 (delta 1), reused 0 (delta 0)

> remote: Resolving deltas: 100% (1/1), completed with 1 local object.

> remote:

> remote: Create a pull request for development\_yourname> on GitHub by visiting:

> remote:

> `https://github.com/temporalecologylab/learn_git/pull/new/development_yourname`

> remote:

> To `github.com:temporalecologylab/learn_git.git`

>  * [new branch]      development_yourname -> development_yourname

Visit the web address above to find a pop where you can write out a title and description of the commit and submit a pull request. 

This will ask the maintainer of the `learn_git` repository to merge your new branch with the main branch on Github.

