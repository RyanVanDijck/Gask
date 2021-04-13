# Gittools

This folder is used to store code to interact with git. 
These functions have been made to simplify other parts 
of code and abstract common tasks such as making commits. 

- [Gittools](#gittools)
  - [git_commit](#git_commit)
    - [git_commit](#git_commit-1)
  - [central_repo](#central_repo)
    - [create_central_repo](#create_central_repo)
    - [update_to](#update_to)
    - [update_from](#update_from)


## git_commit 

The [git_commit.py](git_commit.py) file contains code to commit changes
to a local repository in a taskspace. 

### git_commit

The git_commit function is resposible for 
commiting changes to a git repository in a taskspace. 

It tasks an argument of a commit message which is 
determined based on function which is calling this function. 

Most changes made to a taskspace will call this function.

This includes creating and completing tasks. 

## central_repo
The [central_repo.py](central_repo.py) file contains functions 
that involve commuication related to a central repository, 
such as a GitHub or GitLab repository. 

Any need for account verification is handled by 
the git program itself. 

All communication with a central repostiory is manual, 
as the program will never recieve or send changes
to a central repository without the relevant commands 
given. 

For now, any merge conficts need to be handled by the user. 

### create_central_repo
The create_central_repo repository creates an object 
which can be used to communicate with a central repostory.

### update_to 
The update_to function stores changes made to the taskspace 
to the central repository, equivalent to the 
```git push``` command. 

### update_from 
The update_from function updates the local
taskspace with changes from the 
central repository, equivalent to the 
```git pull``` command. 