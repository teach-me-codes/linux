
### Configure Network Services to Start on Boot – systemd

- ```Sysvinit``` (older service management, CentOS/RHEL 6.x, Ubuntu/Debian prior to 10.04/8)
  - Install an example server service:
    - ```yum install openssh-server```
  - Enable the service to start on reboot:
    -```chkconfig openssh-server```
  - Start the service in current session:
    -```service openssh-server start```

- ```Systemd``` (modern service management, all recent distributions)
  - Install an example server service:
    - ```yum install openssh-server```
  - Enable the service to start on reboot:
    - ```systemctl enable openssh-server```
  - Start the service in current session:
    - ```systemctl start openssh-server```
  - Query the status of a service (running or otherwise):
    - ```systemctl status openssh-server```
    
    
    
