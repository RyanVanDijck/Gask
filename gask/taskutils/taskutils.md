# Taskutils
This folder contains code that defines and manages taskspaces.

 [Taskutils](#taskutils)
- [Taskutils](#taskutils)
  - [Taskspace](#taskspace)
  - [What is a Taskspace?](#what-is-a-taskspace)
  - [The taskspace file](#the-taskspace-file)
  - [Taskspace Class](#taskspace-class)
  - [Taskspace dictionary vs Taskspace object](#taskspace-dictionary-vs-taskspace-object)
  - [Class Members](#class-members)
  - [Methods](#methods)
    - [Create Dict](#create-dict)
    - [\_\_str__](#__str__)
    - [\_\_init__](#__init__)
  - [Functions](#functions)
    - [create_taskspace_from_dict](#create_taskspace_from_dict)
    - [read_task_spaces](#read_task_spaces)
    - [get_current_taskspace](#get_current_taskspace)
    - [get_list_of_taskspace_dicts](#get_list_of_taskspace_dicts)
    - [deset_current_taskspace](#deset_current_taskspace)
    - [write_to_repos_from_list](#write_to_repos_from_list)
- [import_taskspace](#import_taskspace)
  - [import_taskspace](#import_taskspace-1)

## Taskspace 

## What is a Taskspace?
A taskspace is the area in which the git repository and tasks are stored. 

An information file is also stored which stores the date of the last commit and the name of the
taskspace.

The intention of taskspaces are that a user is able to switch between them
to allow dedicated task management for certain purposes and various 
collaborative projects. 

## The taskspace file
The [taskspace.py](taskspace.py) file stores information regarding taskspaces, 
the folders where the git repositories and the databases are stored. 

## Taskspace Class
This class is meant to make code in other parts of the program simpler. 

## Taskspace dictionary vs Taskspace object 
While parts of the program could be made to use a taskspace dictionary,
as imported from the json file, this would create a need for an 
increased use of functions or more code, 
which can be harder to read. 

## Class Members
This class contains a name(string), filepath(string),
and a boolean variable called is current. 

* Name simply stores the name of the taskspace
    * This is also the name of the .db file 
* Filepath stores the path to the folder where the taskspace is stored 
* is_current stores whether operations should occur to this taskspace
    * This is to allow support for switching between taskspaces later

## Methods

### Create Dict
* The create dict method turns the taskspace object in to a 
  dictionary so that it can be loaded onto a json file. 

### \_\_str__
* The str method turns a taskspace into a 
  string which can be presented to the user. 

### \_\_init__
* The init method constructs a new taskspace object using 
  a given name and filepath. 

## Functions

### create_taskspace_from_dict
This function converts a taskspace dictionary into 
a taskspace object. 

### read_task_spaces
The read_task_spaces function reads taskspaces from 
the repos.json file and returns a list of taskspace objects. 

### get_current_taskspace
The get_current_taskSpace function returns a taskspace 
object from the list produced by [read_task_spaces](#read_task_spaces). 
If there is no current taskspace, the function returns 
the current taskspace as an object.

### get_list_of_taskspace_dicts 
This Function returns a list of taskspace dictionaries. 
As mentioned in the [dictionary vs object](#taskspace-dictionary-vs-taskspace-object)
section, this is rarely used outside this file. 

### deset_current_taskspace
This function will go though the repos.json file and make any taskspace set as current not current.

This does not stop when it finds one taskspace that is current just incase there has been an issue and more that one taskspace has been set as true. 

### write_to_repos_from_list
This function will take alist of taskspace objects and write it to the repos.json file. 

# import_taskspace
The [import_taskspace.py](import_taskspace.py) file contains a function to import an already existing taskspace

## import_taskspace

This function will import a taskspace. It will work whether ther is an already exiting taskspace or not. 