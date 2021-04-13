# Commands

This is folder is used to store the command line arguments used by the software.

- [Commands](#commands)
  - [Command Search](#command-search)
  - [Standard commands](#standard-commands)
    - [Add](#add)
    - [Complete](#complete)
    - [List](#list)
  - [Taskspace Management](#taskspace-management)
    - [Create](#create)
    - [Delete](#delete)
    - [Switch](#switch)
    - [Set](#set)
  - [Central repostitory](#central-repostitory)
    - [Setremote](#setremote)
    - [Push|Pull](#pushpull)
    - [Update](#update)
  - [Extra](#extra)
    - [Burndown](#burndown)

## Command Search 

The [commandsearch.py](commandsearch.py) file is used to process the string given by the program at startup and then use the correct command. 

## Standard commands

### Add

This command is completed in the [add.py](add.py) file.

It adds a task to the database in the current taskspace, using a given command line argument.

`gask add "Finish Work"`

The quote marks are not necessary.

`gask add Finish Work`

The program will concatenate the word arguments into a single string.


### Complete 

This command is completed in the [complete.py](complete.py) file. 

It uses a task id to complete/remove a task from the database in the current taskspace. 

`gask complete 1`

### List 

This command is completed in the [list.py](list.py) file. 

It lists the tasks currently store in the database in the current taskspace. 

It is accessed using the command:

`gask list`.

## Taskspace Management

### Create
This command is completed in the [newspace.py](newspace.py) file. 

This command allows the user to create a new taskspace. 

It will perform the same setup as is completed when 
the program is first run. 

Use the command:

`gask create`

The user will be given an option to make this the current taskspace. 

### Delete 

This command is implemented in the [delete_taskspace.py](delete_taskspace.py) file. 

It will delete an existing taskspace from the repos.json file, which is what the 
program uses to store taskspaces. 

The user will then be given the option to empty and delete the folder. 

If there are any other taskspaces found, the user will then be asked if they want to 
set a taskspace as current. 

Use the command:

`gask delete`

### Switch 

This command is located in the [switch.py](switch.py) file. 

It is used to change the current taskspace. 

Use the command:

`gask switch`

### Set

This command is stored in the [set.py](set.py) file. 

The set command is used to change information about a taskspace.

It can currently set/change the deadline or the name/description of the taskspace. 

For now, dates should be given in the format `yyyy-mm-dd`.

The general format is 

`gask set <taskspace_id> <thing_to_change> <new_value>`

e.g:

`gask set 3 name Finish Assignment`

`gask set 2 deadline 2021-4-11`


## Central repostitory 
These commands are used to interact with a taskspace located 
on a central repostitory, such as a GitHub or GitLab repository. 

### Setremote

This command is located in the [setremote.py](setremote.py) file.

This command ties a local taskspace to a central taskspace
based on the argument given. 

This could be a GitHub or GitLab clone link. 

Any interaction between the user and these services are handled
by the GitPython api and the git program.

Use the command

`git setremote <clone_link>`

### Push|Pull

These commands use git functionatily to interact with 
a central repository. 

The push command is created in the [push.py](push.py) file. 
This command is used to update the central repository with 
changes made to the local repostory.

It is identical to the `git push` command. 

`gask push`

The push command is created in the [pull.py](pull.py) file. 
This command is used to retrieve changes from the central repository. 

It is identical to the `git pull` command. 

`gask pull`

### Update

The update combines the [push and pull](#pushpull) commands to allow the user to 
retrieve and upload changes at the same time. 

This may lead to a merge conflict in some scenarios. 

`gask update`


## Extra
This section contains commands which did not easily fit in any
other category. 

### Burndown

This command produces a burndown chart based on the current day and 15 days before.

This command needs the matplotlib library to run. 

`gask burndown`