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

## Git Operations and Commands

![Basic Git Commands](/assets/diagrams/basic.commands.drawio.svg)