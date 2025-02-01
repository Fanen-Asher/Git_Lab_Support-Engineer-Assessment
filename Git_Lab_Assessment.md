# Question 1

## The Git commit graph below shows the output of `git log --all --decorate --oneline --graph`. What sequence of Git commands would result in this commit graph when starting from an empty directory?
 

```
* 3ceaba9 (HEAD -> main) fourth commit
*   6b5b81f Merge
|\
| * 9f22672 (feature-branch) awesome feature
* | 572982b third commit
|/
* 87acf21 second commit
* 5662bb5 first commit
```

## From the above question, please find my feedback below
## Answer:

## The git log graph shows the commit history of a Git repository, including branches and merges. below is a breakdown of the graph:

## Commit details on git log
The graph starts with the oldest commit at the bottom and progresses upward to the most recent commit at the top

## Commits:

**5662bb5** is the first commit in the repository.

**87acf21** is the second commit, which was made after the first commit.

**572982b** is the third commit, made on the main branch.

**9f22672** is a commit on the feature-branch branch, labeled as "awesome feature."

**6b5b81f** is a merge commit that combines changes from feature-branch into main.

**3ceaba9** is the fourth commit, which is the most recent commit on the main branch and is also the current HEAD.

## Branches:
The main branch has the following commits: **5662bb5**, **87acf21**, **572982b**, **6b5b81f** (merge commit), and **3ceaba9**.

The feature-branch branch has one commit: **9f22672**.

## Merge:
The **6b5b81f** commit is a merge commit. It combines the changes from feature-branch **9f22672** into the main branch **572982b**.

The merge is represented by the |\ and |/ lines in the graph.

## HEAD:
HEAD points to the main branch, and the most recent commit on main is **3ceaba9**.

## Extra Note: 
This graph is a common way to visualize Git history, especially when branches and merges are involved. and the above looks more of a ***squash*** merge process that was done after the initial commit process

## Reference:
[Udemy DevOpsCourse](https://www.udemy.com/share/103Coy3@mQdw4r9Fl7n1-g6tG016ppTM1xucVl3vAhokOJqTG9lq1Kmk23im9eftklNezU5B/)




# Question 2

## A user is complaining that it's taking a long time to load a page on our web application. In your own words, write down and discuss the possible cause(s) of the slowness. Also describe how you would begin to troubleshoot this issue?

## Answer Response:
when a user reports that an application is loading slowly this could be from various factors in the application, server, or database. It's always good to look at the end to end system architecture stack to have a feel of where the issue could be coming from.

## Possible system layers the issue could stem from:

### Database:
depending on the RDBMs used which could be MySQL, Oracle or MSSQL the possible issues could be **indexing issues** on frequently querried tables, **unoptimized queries** which may take time to execute or in some case lead to DB locks

### Servers:
the server may be maxing out of key resources such as RAM and CPU or there could be some external network communication issues when trying to reach some third party APIs that could be slow.

### Web Application and Web server:
The web server might not have enough workers or threads to handle concurrent requests or no caching inplace for database communication of stateful request.

### External dependencies:
Third party APIs could be slow or i some cases DNS resolution problems.

### Troubleshooting Steps

Comfirm the experience: accessing the page yourself and also check is issue is consistent or intermittent as this could guide on what to check next

### Check Server performance:
can use monitoring tools such as BM truesight or AppDynamics to check server resource utilization or even log on to the server box and run commands such as **top**, **vmstats**, **df -h** to check memory, storage or CPU utilization

### Web service:
can also check web server(IIS, Apache, Nginx etc) logs to see possible trace of transactions and destinations

### database:
check long running queries and see if their are possible optimization and even kill some queries so that they can be re-initiated. eg SHOW PROCESSLIST on MySQL or other commands for different databases.

### Web Application:
possible profiling of the application using the MVC framework

### External Dependencies:
use commands such as curl or telnet to check reachability of external endpoints 

### Redesign possibility
If there is a likelihold of an increase in the request hitting the system from the usual trend then the system architecture needs to be reviewed. Load balancing the request across multipl web server and application servers to handle effiencient processing of request.

## Reference:

[System Architecting and DevOps Course](https://www.udemy.com/share/104Xxm3@RfrUg2jgtEc5s2OTligOHdF-Kt_nH4u-Ry4cC7WLhhkZ4WCH8mYlO34bwpMIMDp6/)

# Question 3
## In your own words, write a tutorial/blog explaining things in a beginner-friendly way. Make sure to address both the "why" and "how" for each Git command you use.  Assume the audience are readers of a well known blog.

### Theory about Brancing in Git:
the whole idea of using a branch is for better management of building new features before mearging to production. in other ways these features can be better tested before merging to the Mainor Master branch. before we go into the details lets try to understand the differences of Main and feature branch.

### Main or Master Branch: 
this is usually the working code of the application in production after the working directory is initialized and the code is added and commited to the working directory and any changes to the code in this directory will alter the functionality of the working aplication.

### Feature Branching or Branch concepts in Git:
This is required to build new features for a working app without making changes to the working working app code. we can have a simple review by looking at below commands and why we use them and how they work:

### Git commands before branching:

### creating and initializing a git directory:
***git init***: ussed to initialize a working directory in git. initializing helps to manages the changes to the code in the directory.

***git  add .*** : whenever there is a change or an addition to the working directory you need to add the new code change or directory to the staging the area before commiting to the main branch using below command

***git commit -m*** "what has been added or change?": this commits to the main working directory which can also be seen as the most recent code for the working application.

![checkimage](.\Images\git_describe.png)

### New feature to working Application:
if there is a new feature to be added to the working application its usually ideal to run a stage or test of the the new feature before merging to the working application code we can use below command to checkout the Feature app


***git checkout -b FeatureA*** this will check out the code from the main branch and present to the user some sort of a branch to make updates from without impacting the working code you can make update and the do a commit to ensure persistence to the branch. once you are satisfied with the changes from the FeatureA branch and now want to merge the new feature to the working Application code the you can check out the Main or Master branch using below command and then merge the featureA branch from the Main branch

***git checkout Main*** after checout to the Main or Master branch then you can merge the changes to the working application from the FeatureA branch using below command

***git merge FeatureA*** this now merges the changes from the featureA branch to the Main branch. you can run a ***git log --all*** to see all the commits

### Extra information:
The above process could also be a ***fast forward merge*** process or ***squash merge*** process depending on the changes to be made at different points in time and when they are merged to the main or master branch

# Question 4

## What is a technical book/blog/course/etc. you experienced recently or in the past that you enjoyed?  Please include:
 - A link or reference so we know what you are talking about.
 - A brief review of what you especially liked or didn’t like about it.

### The technical course was more of a DevOps & GitHub Project based course that I went through on Udemy with below link: very interesting course and one of the best project based course I have seen on DevOps based projects.

[DevOps & GitHub Projects Based Course](https://www.udemy.com/share/103WWq3@OJwpydIEYMZJL15MN18LxGLLV-Wfd6LI-cUUq7G6uCHllljr0TtrKQWT5e8Awq97/)

### What I Liked about the course:
was a one stop shop project based course from begginer to advanced level that covers different project from on premises infrastructure to cloud and managing codes using github and CI/CD pipelines as well. I had gone through the main course it self before going through the project based course  to get more handson on complex K8S deployments and other system architecting concepts. other interesting concepts from the course

`Ansible`
`Docker`
`Jenkins`
`AWS`
`Terraform` 
`linux`

### Overall I developed good systems architecting skills, troubleshooting and automation concepts as well.

# Question 5
## Write a Ruby or Bash script that will print usernames of all users on a Linux system together with their home directories. Here's some example output:

   ```
   gitlab:/home/gitlab
   nobody:/nonexistent
   .
   .
   ```
   
   Each line is a concatenation of a username, the colon
   character (`:`), and the home directory path for that username. Your script
   should output such a line for each user on the system.
   
   Next, write a second script that:

   * Takes the full output of your first script and converts it to an MD5 hash.
   * On its first run stores the MD5 checksum into the `/var/log/current_users` file.
   * On subsequent runs, if the MD5 checksum changes, the script should add a line in
     the `/var/log/user_changes` file with the message,
     `DATE TIME changes occurred`, replacing `DATE` and `TIME` with appropriate
     values, and replaces the old MD5 checksum in `/var/log/current_users`
     file with the new MD5 checksum.

   Finally, write a crontab entry that runs these scripts hourly.

   Provide both scripts and the crontab entry for the answer to be
   complete.

## Answer to above: Using Bash

### First Script 1: list_users.sh

This script lists all users and their home directories.

`#!/bin/bash`

*Loop through all users and print their username and home directory*

`getent passwd | awk -F: '{print $1 ":" $6}'`

### Second script: monitor_users.sh

*this script calculates the MD5 hash of the output from list_users.sh, compares it with the previous hash stored in /var/log/current_users, and logs changes if detected.*

![secondscript](.\Images\secondscript.png)

### Crontab Entry:
*Add the following line to your crontab to run the scripts hourly*:

`0 * * * * /path/to/list_users.sh | /path/to/monitor_users.sh`

*Replace /path/to/ with the actual paths to your scripts.*

### Steps to Set Up:

1. Save ***list_users.sh*** and ***monitor_users.sh*** to your desired directory.
   
2. Make both scripts executable:
   
   `chmod +x /path/to/list_users.sh`

   `chmod +x /path/to/monitor_users.sh`

3. Add the crontab entry using `crontab -e`.
4. Ensure the `/var/log/` directory is writable by the user running the script, or adjust the file paths as needed.

*This setup will monitor user changes hourly and log them if any changes are detected.*

## Reference:

[Linux & Bash Scripting Course](https://www.udemy.com/share/101svy3@Zj59dtefhQfF4MTevVm8RefhD4vX3vP8JJZJlVzZYoppdfNUWZrvVJftFV7Kwj90/)
















