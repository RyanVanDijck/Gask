# Start 

This folder contains code used that is run when the program
is first run 

## createTaskspace

The [createTaskspace](create_repo.py) file is used to create
a taskspace if none exists when the program is run. 

It creates a database and initializes a new git repository. 

It contains one function called createRepo. 

The [create.sql](create.sql) file contiains code to start the
database. 

## start

The [start](start_prog.py) file handles the program when the 
command is first issued. 

If there is at least one repository, then the program
processes the command. 

Otherwise, the program prompts the user to 
create a new taskspace. 
