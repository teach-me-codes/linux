## Change the Priority of a Process/Identify Resource Utilization by Process

- ```jobs``` : Displays minimal information about processes associated with the current session
- ```ps``` : By default, ```ps``` only displays process that were run from its own terminal
  - ```–A \ -e``` : Displays all processes on a system
  - ```-u ``` : Displays processes given by a specified user
  - ```-H``` : Groups processes and use indentation to show the hierarchy of relationships between processes
  - ```-w``` : Tells ps not to truncate to system 
- ```uptime```: Find uptime and display load average
- ```bg``` : Restores a job to running status, but in the background
- ```fg``` : Use ```CTRL+Z``` to pause a program and, then ```fg``` to send the program to foreground
- ```kill``` : Can be used to stop executing processes, uses PID
- ```nohup```: Run a command immune to hangups, with output to console or non-tty
- ```killall```: Can be used to kill all processes of a certain name
- ```free``` : Show free memory and swap

### Common kill signals:

```
SIGHUP 1 HANGUP
SIGINT 2 INTERRUPT FROM KEYBOARD
SIGKILL 9 KILL SIGNAL
```
- This signal is not blockable and causes the program to terminate abruptly; only use if you can’t terminate with 15

- ```SIGTERM 15 TERMINATION SIGNAL```:  Asks the program to finish what it is doing, then exits; clean exist; the preferred way of killing processes
- ```SIGSTOP 17,19,23 STOP THE PROCESS``` : When a child process exits from a parent process it sends signal 1
- Signals in the man page ```man-k signal```




