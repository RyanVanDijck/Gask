# Fileutils

This folder contains tools to help deal with file locations, directories and paths. 

This is important as the program needs to run on multiple operating systems, and needs to install using pip. This adds more complexity due to varying file location and systems. 

This justified separating them, as these functions are used thoughout the codebase, and can become quite complicated. 

- [Fileutils](#fileutils)
  - [Directory](#directory)
    - [get_top_directory](#get_top_directory)
    - [get_repos_path](#get_repos_path)
    - [get_user_folder](#get_user_folder)
  - [Folder_open](#folder_open)
    - [choose_folder](#choose_folder)
    - [create_menu_items](#create_menu_items)
    - [make_folder](#make_folder)
    - [change_win_drive](#change_win_drive)


## Directory
The [directory.py](directory.py) file contains functions to get important file and folder paths. 

### get_top_directory
This function gets the directory where the main file is run. I have decided to store the 
core repos.json file in this location to provide a consistent location across platforms. 

### get_repos_path
This gives a file path to the repos.json file. This file is accessed or altered by many parts of the program and is the only save file used the program stored outside of taskspaces. 

### get_user_folder
This function returns the file path to a directory selected by the user. 

The user is first asked if they want to use the current directory.

If they do, then the current directory is returned. Otherwise, the program returns the filepath 
given by the [choose_folder](#choose_folder) function in the [folderopen.py](folderopen.py) file. 

## Folder_open
The [folderopen.py](folderopen.py) file contains code designed 
to allow the user to choose a folder. 

### choose_folder
This function returns a filepath of a folder chosen by the user. 

If curses can be loaded, it uses a curses based interface made 
using the pick library. 

If curses can't be loaded, it simply asks the user to enter a filepath. 

### create_menu_items
This function returns a list of strings which 
represent the possible options to the user when using 
the pick/curses folder select dialog. 

If the platform is windows, an extra option is given to change to a different drive. 

### make_folder
The make folder function allows the user to create a directory 
in the directory that the user is currently in when using the pick/curses
folder dialog. 

### change_win_drive
In windows, this will allow the user to change drive when using the folder
dialog. 