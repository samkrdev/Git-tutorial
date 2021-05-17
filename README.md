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
