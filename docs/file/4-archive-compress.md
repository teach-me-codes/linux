### Archive, Compress, Unpack and Decompress Files


- ```tar``` : Can be used to archive, unarchive, compress and decompress files
- Archives values in the ```/etc``` directory in a file called ```etc.tar``` :
  - ```tar cvf etc.tar /etc```
- Decompresses archive:
  - ```tar xvf etc.tar```
- Archives values in the ```/etc``` directory in a file called ```etc.tar``` , and also compress that file with
```gzip``` :
  - ```tar cvzf etc.tar /etc```
- List contents of archived file:
  - ```tar tvf etc.tar```
- ```c``` – Archive
- ```v``` – Verbose
- ```f``` – Write to a file
- ```x``` – Extract
- ```z``` – gzip compression
- ```j ```– bzip compression
- ```A``` – Append files to existing archive
- ```t ```– List contents
