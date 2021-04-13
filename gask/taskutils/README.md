# Taskutils 

This folder houses code related to the definition and processes related to tasks and the storage of tasks. 

# Taskspace 

The [taskspace.py](taskspace.py) file stores information regarding taskspaces, the folders where the git repositories and the databases are stored. 

### Taskspace Class

This class contains a name(string), filepath(string) and a boolean varible called is current. 

* Name simply stores the name of the taskspace
    * This is also the name of the .db file 
* Filepath stores the path to the folder where the taskspace is stored 
* iscurrent stores whether operations should occur to this taskspace
    * This is to allow support for switching between taks spaces later

#### Methods

* The create dict method turns the taskspace object in to a dictionary so that it can be loaded onto a json file. 

* The str method turns a taskspace into a string which can be presented to the user. 

* The init method constructs a new taskspace object using a given name and filepath. 


### readTaskSpaces

The readTaskSpaces function reads taskspaces from the repos.json file and returns a list of taskspace objects. 

### getCurrentTaskSpace

The getCurrentTaskSpace function returns a taskspace object from the list produced by readtaskspaces. If there is no current taskspace, the function returns nothing (for now :smile: )