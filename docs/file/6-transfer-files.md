### Transfer Files Securely via SFTP/SCP


- ```scp``` : Based on the SSH secure protocol for transfer of files
  - Transfer files to/from a server:
  
     ```scp user@RemoteIP:/remote/dir/myfile.txt /home/user```
  
  - Copy the remote file called ```myfile.txt``` to the local ```/home/user directory```:
  
     ```scp myfile.txt user@RemoteIP:/remote/dir```
  
  - Copies the local file called ```myfile.txt``` to the remote directory ```/remote/dir``` :

- ```sftp```: SSH-based file transfer program whose behavior is based on the less-secure program, FTP
  - Same format as the scp in terms of individual files or directories
  - Add batch processing capabilities: ```sftp -b batch.file```
  - Similar to expect scripts, using FTP commands to run through many transactions in one listing.










