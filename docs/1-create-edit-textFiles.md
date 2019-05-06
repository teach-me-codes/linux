
### Create and Edit Text Files

- ```vi/vim``` : Full screen editors; ```vi``` is always available since it is a POSIX requirement, ```vim``` may need to beinstalled)
- ```vi filename```: Multiple modes:
  - ```Command mode``` allows for navigation and the entering of commands using combinations of one or more letters; these can be prefixed with numeric values for repetition
  - ```Ex mode``` allow file manipulation; to enter this mode, type a colon (```:```) followed by the command desired
  -  ```Insert mode``` to edit text; enter this post by pressing ```i```
  - The ESC key always returns to command mode

- ```vi``` command examples:
  - ``` h```: Move one character left
  - ```j```Move down line
  - ```k``` Move up line
  - ```l```Move one character right
  - ```H ```Move to top of screen
  - ```L``` Move to bottom of screen
  - ```G```Move to end of file
  - ```0```Move to beginning of line
  - ```$ ``` Move to end of line
  - ```i```Insert at current position
  - ```I```Insert at beginning of line 
  - ```x```Delete character
  - ```dd```Delete line
  - ```o```Create a blank line after current line
  - ```O``` Create a blank line before current line
  - Additional commands can be found in the vi/vim man pages

- Text files can be created by various methods outside of ```vi, vim``` or other editors:
- ```touch testfile.txt```: Creates a blank file called testfile.txt owned by the current user in the current directory
- ```echo "Some value" > testfile.txt``` : Creates a file called ```testfile.txt```, owned by the current user in the current directory, containing the text following the echo command (in this instance, “Some value”)
- Redirection of almost any command will take the output and place it into a
file

