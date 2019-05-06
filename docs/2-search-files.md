
## Search for Files

- ```vi/vim``` : Moves cursor to a certain location, based on a search
  - In command mode, press f and then a character; this moves to the next occurrence of value in the current line
  - To search for a value in the entire file, in command mode, use ```/``` and then type the value
  - Similar to sed, you can use ```vi/vim``` to replace values:
    - ```— :%s/oldvalue/newvalues/g```
- ```find``` : Commonly used to find files by name, by user and/or by type
  - ``` find /start/dir -name "value"``` — Finds files in /start/dir with the name value
  - ```-maxdepth```— The number of subdirectories to search
  - ```-type``` —  ``` f ``` Regular file
  - ```-size``` — ``` +#[MGT] ```—  number and type of storage value (mega, giga, terabytes)
  - ```-perm```— Numeric designation of permissions to look for
  - ```-exec — rm ‘{}’ + ``` — Execute the command ```rm``` on the values/files within the results of the ```find``` command
- Many more values and examples in the man pages

