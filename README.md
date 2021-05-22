# Git-tutorial

Notes for quick reference on Git

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
   * All the versions stay in user's workstation
   * Many people’s version-control method of choice is to copy files into another directory
   * It is easy to forget which directory you’re in and accidentally write to the wrong file or copy over files you don’t mean to.
   * Incredibly error prone
   * Can't collaborate with others
2. **Centralized VCS**
   * Allows to collaborate with developers on other systems
   * CVCS has single server that contains all the versioned files and multiple developers and teams can checkout files for work from this single server.
   * Everyone knows to a certain degree what everyone else on the project is doing.
   * Administrators have fine-grained control over who can do what, and it’s far easier to administer a CVCS than it is to deal with local VCS on every client.
   * Risk of running into a single point failure.

    ![CVCS system](/assets/images/cvcs.png)
3. **Distributed VCS**
   * Clients don’t just check out the latest snapshot of the files; rather, they fully mirror the repository, including its full history
   * Every clone is really a full backup of all the data
   * No risk of single point failure

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

   ```console
   echo "Hello there!"
   ```

2. Know current working directory

   ```console
   pwd
   ```

3. See what is there in the working directory

   ```console
   ls
   ```

   To see hidden files

   ```console
   ls -a
   ```

   To see the more details of files and folders

   ```console
   ls -l
   ```

4. Go to a folder with in the directory

   ```console
   cd assets
   ```

   Go to previous folder

   ```console
   cd ..
   ```

   Go to home directory

   ```console
   cd ~
   ```

   Create a folder called "UmbrellaCorp" in the working directory

   ```console
   mkdir UmbrellaCorp
   ```

   Create an empty file called "baker.txt" in the working directory

   ```console
   touch baker.txt 
   ```

   Delete a file called "wesker.txt" in the working directory

   ```console
   rm wesker.txt
   ```

   Delete a folder called "tricell" in the working directory

   ```console
   rmdir tricell
   ```

   Delete everything in a folder. Will prompt for a confirmation if there are more than 3 items to delete.

   ```console
   rmdir -r *
   ```

   Rename a file called "RacoonCity.txt" to "RockfortIsland.txt"

   ```console
   mv RacoonCity.txt RockfortIsland.txt
   ```

   You can use `mv` for moving too. Use `cp` to copy.

   Consider the following folder structure

   ![Before Moving](/assets/images/pre_mv.png)

   We want to move all the .py files from `My_App/static` folder to `My_App/app` folder

   Let's assume that our working directory is `My_App` folder
   We can move the .py files using below command

   ```console
   mv static/app.py static/manage.py static/settings.py static/urls.py static/views.py app/
   ```

   Since we are only moving .py files, we can use * wildcard to shorten the command.

   ```console
   mv static/*.py app/
   ```

   Using any of the above two commands will result in following folder structure.

    ![After Moving](/assets/images/post_mv.png)

   Let's assume `My_App/static` is our working directory. In this case we will have to write our command as follows

   ```console
   mv *.py ../app/
   ```

5. To create a file called `dumblydore.txt`

   **In the working directory**

   ```console
   touch dumblydore.txt
   ```

   **In sub-directory called `hogwarts`**

   ```console
   touch hogwarts/dumblydore.txt
   ```

6. Some more useful commands to explore:

   ```console
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
