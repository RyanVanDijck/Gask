# Commands

This is folder is used to store the command line arguments used by the software.

## Command Search 

The [commandsearch.py](commandsearch.py) file is used to process the string given by the program at startup and then use the correct command. 

## Add

This command is completed in the [add.py](add.py) file.

It adds a task to the database in the current taskspace, using a given command line argument.

`gask add "Finish Work"`

The quote marks are not necessary.

`gask add Finish Work`

The program will concatenate the word arguments into a single string.


## Complete 

This command is completed in the [complete.py](complete.py) file. 

It uses a task id to complete/remove a task from the database in the current taskspace. 

`gask complete 1` 

## List 

This command is completed in the [list.py](list.py) file. 

It lists the tasks currently store in the database in the current taskspace. 








