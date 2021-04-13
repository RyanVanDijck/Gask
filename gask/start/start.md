# Start 

This folder contains code used that is run when the program
is first run 

- [Start](#start)
  - [start_prog](#start_prog)
    - [first_check](#first_check)
    - [create_taskspace](#create_taskspace)
  - [create_repo](#create_repo)
    - [create_repo](#create_repo-1)
  - [Sql queries](#sql-queries)
    - [get_create_tasks_query](#get_create_tasks_query)
    - [get_completed_tasks_query](#get_completed_tasks_query)


## start_prog
The [start_prog.py](start_prog.py) file handles the program when the 
command is first issued. 

If there is at least one repository, then the program
processes the command. 

Otherwise, the program prompts the user to 
create a new taskspace. 

### first_check 
The first_check function checks if there is a taskspace and
if there is runs the program normally or otherwise invites the user 
to create a taskspace. 

If the import command is used, this 
is executed rather than the rest of the program, even if there 
is not taskspace. 



### create_taskspace
The create taskspace function creates a taskspace. 

It takes an argument of a filepath where the taskspace is created. 

## create_repo
The [create_repo.py](create_repo.py) file is used to create
a taskspace through the [create_repo](#create_repo-1) function.  

### create_repo
This function contains the main code to create a taskspace. 
It takes the name, path as arguments as well as whether it should be
made the current taskspace or not. 

This function is placed in the start folder as it will 
mainly be used when the program is first run. However, 
it can still be used after a taskspace is already 
created/imported. 

## Sql queries
There are two queries used to initalise the database. 

They are accessed using functions in the 
[create_repo.py](create_repo.py) file. 

This was done because:

- It is easier to deploy a python package
  without extra files(in this case .sql files). 
- It reduces the risk of an error related to reading a file. 
### get_create_tasks_query
This function returns the sqlite query used to create the 
"tasks" table which stores the tasks yet to be completed. 

### get_completed_tasks_query
This function returns the sqlite query used to create the 
"completed_tasks" table where tasks are stored
after they have been marked as complete. 