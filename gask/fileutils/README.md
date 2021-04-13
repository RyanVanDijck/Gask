# Fileutils

This folder contains tools to help deal with file locations, directories and paths. 

This is important as the program needs to run on multiple operating systems, and needs to install using pip. This adds more complexity due to varying file location and systems. 

This justified separating them, as these functions are used thoughout the codebase, and can become quite complicated. 

## Directory
The [directory.py](directory.py) file contains functions to get important file and folder paths. 

### getTopDirectory

This function gets the directory where the main file is run. 

### getReposPath

This gives a file path to the repos.json file. This file is accessed or altered by many parts of the program. 