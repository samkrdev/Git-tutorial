# Git-tutorial

Notes for quick reference on Git

- [Git-tutorial](#git-tutorial)
  - [What is Version Control System?](#what-is-version-control-system)
  - [What can you do with a Version control system?](#what-can-you-do-with-a-version-control-system)
  - [Types of Version control systems](#types-of-version-control-systems)
  - [What is Git](#what-is-git)
  - [Version Control with Git](#version-control-with-git)
  - [Bash Shell](#bash-shell)
  - [Git Operations and Commands](#git-operations-and-commands)
    - [**On initial install:**](#on-initial-install)
    - [**For help on git commands**](#for-help-on-git-commands)
    - [**For initializing the project**](#for-initializing-the-project)
    - [Ignoring some files for Version control](#ignoring-some-files-for-version-control)
    - [The Workflow commands](#the-workflow-commands)
      - [Check Working tree](#check-working-tree)
      - [Stage files for committing](#stage-files-for-committing)
      - [Remove files from staging](#remove-files-from-staging)
      - [Committing Changes](#committing-changes)
      - [Check log](#check-log)
      - [Clone a remote repo](#clone-a-remote-repo)
      - [View info about the repo](#view-info-about-the-repo)
      - [View changes](#view-changes)
      - [Syncing Changes](#syncing-changes)
      - [Branching and Merging](#branching-and-merging)
      - [Fixing errors](#fixing-errors)

## What is Version Control System?

Version control is a system that **_records changes_** to a file or set of files over time so that you can **_recall specific versions_** later.

## What can you do with a Version control system?

1. Revert selected files back to a previous state.
2. Revert the entire project back to a previous state.
3. Compare changes over time.
4. See who last modified something that might be causing a problem, who introduced an issue and when, and more.
5. Using a VCS also generally means that if you screw things up or lose files, you can easily recover.
6. Coordinate across multiple teams and developers on a project.
7. Risk of running into a single point failure.

## Types of Version control systems

1. **Local VCS**
   - All the versions stay in user's workstation
   - Many people’s version-control method of choice is to copy files into another directory
   - It is easy to forget which directory you’re in and accidentally write to the wrong file or copy over files you don’t mean to.
   - Incredibly error prone
   - Can't collaborate with others
2. **Centralized VCS**
   - Allows to collaborate with developers on other systems
   - CVCS has single server that contains all the versioned files and multiple developers and teams can checkout files for work from this single server.
   - Everyone knows to a certain degree what everyone else on the project is doing.
   - Administrators have fine-grained control over who can do what, and it’s far easier to administer a CVCS than it is to deal with local VCS on every client.
   - Risk of running into a single point failure.

    ![CVCS system](/assets/images/cvcs.png)
3. **Distributed VCS**
   - Clients don’t just check out the latest snapshot of the files; rather, they fully mirror the repository, including its full history
   - Every clone is really a full backup of all the data
   - No risk of single point failure

   ![DVCS system](/assets/images/dvcs.png)

## What is Git

1. Git is a mature, actively maintained open source project originally developed in 2005 by Linus Torvalds, the famous creator of the Linux operating system kernel.
2. A staggering number of software projects rely on Git for version control, including commercial projects as well as open source.
3. Git is an example of a DVCS.
4. In Git, every developer's working copy of the code is also a repository that can contain the full history of all changes.

5. Git has been designed with performance, security and flexibility in mind.

## Version Control with Git

1. Git has the functionality, performance, security and flexibility that most teams and individual developers need.

2. Git is a de facto standard due to huge talent pool.

3. Git is a quality open source project. No Cost.

4. Performance, Security and Flexibility

## Bash Shell

Before we start with Git, it pays to know basics of Bash shell.

1. Printing to terminal:

   ```zsh
   echo "Hello there!"
   ```

2. Know current working directory

   ```zsh
   pwd
   ```

3. See what is there in the working directory

   ```zsh
   ls
   ```

   To see hidden files

   ```zsh
   ls -a
   ```

   To see the more details of files and folders

   ```zsh
   ls -l
   ```

4. Go to a folder with in the directory

   ```zsh
   cd assets
   ```

   Go to previous folder

   ```zsh
   cd ..
   ```

   Go to home directory

   ```zsh
   cd ~
   ```

   Create a folder called "UmbrellaCorp" in the working directory

   ```zsh
   mkdir UmbrellaCorp
   ```

   Create an empty file called "baker.txt" in the working directory

   ```zsh
   touch baker.txt 
   ```

   Delete a file called "wesker.txt" in the working directory

   ```zsh
   rm wesker.txt
   ```

   Delete a folder called "tricell" in the working directory

   ```zsh
   rmdir tricell
   ```

   Delete everything in a folder. Will prompt for a confirmation if there are more than 3 items to delete.

   ```zsh
   rmdir -r *
   ```

   Rename a file called "RacoonCity.txt" to "RockfortIsland.txt"

   ```zsh
   mv RacoonCity.txt RockfortIsland.txt
   ```

   You can use `mv` for moving too. Use `cp` to copy.

   Consider the following folder structure

   ![Before Moving](/assets/images/pre_mv.png)

   We want to move all the .py files from `My_App/static` folder to `My_App/app` folder

   Let's assume that our working directory is `My_App` folder
   We can move the .py files using below command

   ```zsh
   mv static/app.py static/manage.py static/settings.py static/urls.py static/views.py app/
   ```

   Since we are only moving .py files, we can use * wildcard to shorten the command.

   ```zsh
   mv static/*.py app/
   ```

   Using any of the above two commands will result in following folder structure.

    ![After Moving](/assets/images/post_mv.png)

   Let's assume `My_App/static` is our working directory. In this case we will have to write our command as follows

   ```zsh
   mv *.py ../app/
   ```

5. To create a file called `dumblydore.txt`

   **In the working directory**

   ```zsh
   touch dumblydore.txt
   ```

   **In sub-directory called `hogwarts`**

   ```zsh
   touch hogwarts/dumblydore.txt
   ```

6. Some more useful commands to explore:

   ```zsh
   # Create and edit a file called harry.txt
   nano harry.txt
   
   # Print to console  
   echo "Yer a wizard Harry"

   # Write directly to a file
   echo "Yer a wizard Harry" > hagrid.txt

   # Append to a file
   echo "I Should Not Have Said That." >> hagrid.txt

   # See contents of a file
   cat hagrid.txt

   # Get help on commands
   man ls
   ```

Understand file permissions notations at <https://help.ubuntu.com/community/FilePermissions>

![Output with lsd](/assets/images/lsd.png)

## Git Operations and Commands

![Basic Git Commands](/assets/diagrams/basic.commands.drawio.svg)

### **On initial install:**

- Checks the version of the installed locally git

   ```zsh
   git --version
   ```

- sets up the name of the user

   ```zsh
   git config --global user.name "Your Name"
   ```

- sets up the email of the user

   ```zsh
   git config --global user.email "yourname@somemail.com"
   ```

- Lists all the configs

   ```zsh
   git config --list
   ```

### **For help on git commands**

```zsh
git help <verb>
# or you can use the below
git <verb> --help
 ```

### **For initializing the project**

```zsh
git init
```

### Ignoring some files for Version control

Sometimes we may need to ignore few files based on the project and organization requirements.
These files may contain personal data or PII data or org's intellectual property.

We can create and make use of `.gitignore` file to specify such files.

```zsh
touch .gitignore
```

You can edit this file in any text editor to mention the files or folders that must be ignored.

```bash
# Ignore the node_modules directory
node_modules/

# Ignore Logs
logs
*.log

# Ignore the build directory
/dist

# The file containing environment variables 
.env

# Ignore IDE specific files
.idea/
.vscode/
*.sw*
```

### The Workflow commands

![Basic Git Workflow](/assets/images/git_workflow.png)

#### Check Working tree

```zsh
git status
```

#### Stage files for committing

```zsh
git add -A
```

#### Remove files from staging

```zsh
git reset somefile.js
```

#### Committing Changes

```zsh
git commit -m "This is the commit message"
```

#### Check log

```zsh
git log
```

#### Clone a remote repo

 ```zsh
 # syntax
 git clone <url> <where to clone>
 # example
 git clone https://github.com/mehdihadeli/awesome-software-architecture.git .
 ```

#### View info about the repo

```zsh
# lists info about the repo
 git remote -v
# lists all of the branches
 git branch -a
 ```

#### View changes

```zsh
# shows the difference made in the files
git diff
```

#### Syncing Changes

1. Pull changes

   ```zsh
   # pull before push ALWAYS
   git pull origin master
   ```

2. Push Changes

   ```zsh
   # <origin> name of remote repo <master> the branch that we push to
   git push origin master
   ```

3. First time push of the branch:

   ```zsh
   # This will link the local branch and remote branch
   git push -u origin <name of the branch>
   ```

#### Branching and Merging

1. Create a branch

   ```zsh
   # syntax
   git branch <name of the branch>
   # example
   git branch develop-nav
   ```

2. Checkout a branch

   ```zsh
   # syntax
   git checkout <name of the branch>
   # example
   git checkout develop-nav
   ```

3. Workflow to merge a branch in to master and push to remote:

   ```zsh
   git checkout master # Switch to Master branch
   git pull origin master # Pull Changes from Master
   git branch --merged # See which branches are merged
   git merge develop-nav # Specify the branch that needs to be merged
   git push origin master # Push changes back to master
   ```

4. Deleting branches

   ```zsh
   git branch -d <name of the branch> # This deletes it locally!!!
   git branch -a # Check the repo branches
   git push origin --delete <name of the branch> # This deletes it from the repo!
   ```

#### Fixing errors

- Restore a file before committing

   ```zsh
   git checkout <filename>
   ```

- To make changes to commit message:

   ```zsh
   git commit --amend -m "Imported pandas"
   ```

- To add a file to commit after committing

   ```zsh
   # add the file to staging area
   git add .gitignore 
   git commit --amend
   #Press esc and :wq
   ```

- Create a commit in a branch based on a commit in another branch.

   ```zsh
   git cherry-pick <hashcode>
   ```

- Reset a commit

  ```zsh
   git reset --soft <hashcode>
   git reset <hashcode>
   git reset --hard <hashcode>
  ```

- Remove any untracked files

   ```zsh
   git clean -df
   ```

- Restore commits that were reset

   ```zsh
   git reflog # fetch commit id from here, reflog is a life saver
   git checkout <hashcode> # will send you to a detached mode
   git checkout backup_branch # will send the detached head to a new branch called backup_branch
   ```

- Revert a commit but don't rewrite git log

   ```zsh
   git revert <hashcode>
   ```
