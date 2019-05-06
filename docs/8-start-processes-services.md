### Manage the Startup Processes and Services

- Reboot the system:
  - ```reboot```
  - ```systemctl reboot```
  - ```shutdown -r now```
    - ```-r``` : reboot
    - ```now``` : Reboot immmediately  
    - ```+5``` :  Wait 5 minutes and then reboot
    - ```+0``` :  Same as now
    - ``` 01:01```:1:01 AM shutdown
    - ```-c```: Cancel a scheduled shutdown
  - ```init 6 ```: The init system in Red Hat 7 is depreciated. However, runlevels are still compatible for thiscurrent version for backwards compatibility

- Shutdown the system (no reboot/power off):
  - ```systemctl halt```
  - ```halt```
  - ```shutdown -h now``` ( ```-h``` means halt)
  - ```init 0```

- Physically power off the system:
  - ```systemctl poweroff```
  - ```poweroff```
  - ```shutdown -P```
