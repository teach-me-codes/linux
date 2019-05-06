## Storage Management

### Standard File Systems
 
- Partitioning
  - ```fdisk/gdisk /dev/drive```
    - Allows us to create a partition from the available indicated disk
    - Can set type of partition (GPT or MBT depending on use), list the partition types in the menu
    
- Format the filesystem partition created:
  - ```mkfs -t ext4 /dev/disk1```
  - Formats the disk partition ```disk1``` as an ext4 partition
- Mount the formatted partition:
  - ```mkdir /mnt/mount```
  - ```mount -t ext4 /dev/disk1 /mnt/mount```
    - Mounts the formatted drive, as an ext4 mount on the created directory
    
- Persistently mounting the disk above
  - Obtain the UUID of the device:
    - ```ls -al /dev/disk/by-uuid```
  - Add entry to ```/etc/fstab```:
    ```UUID=UUDI_OBTAINED     /mnt/mount    ext4    defaults   0```
    
  - Mount the defined entry automatically, if not mounted in current session:
    - ```mount -a```
    - This will scan all defined mount points, and if not mounted, mount them using the definitions in ```/etc/fstab```
    
### Encrypted File Systems

- System support encrypted file system query:
  - ```grep -I config_dm_crypt /boot/config-$(uname -r)```
- Determine if module is loaded:
  - ```lsmod | grep dm_crypt```
- Load module if needed:
  - ```modprobe dm_crypt```
- Partitioning : Handled the same way as a typical disk and drive as defined above in the “Standard File Systems” section
- Install the cryptsetup utility:
  - ```yum install cryptsetup```
- Default encryption key setup
  - ```Luks``` – Linux Unified Key Setup
- Set up the partitions with passphrase:
  - ```cryptsetup -y luksformat /dev/disk1```
    - Prompts for passphrase for unencrypting drive during mount/use
    - Large drives will take a long time to encrypt 
 - Open partition for use:
   - ```cryptsetup luksOpen /dev/disk1 reference_name```
- Format the filesystem partition created, using the mapper overlay created above
  - Handled the same way as a typical disk and drive as defined above in the “Standard File Systems” section
    - Example: ```mkfs-t ext4 /dev/mapper/reference_name```
- Mount the drive:
  - ```mount /dev/mapper/reference_name /mnt/mount```
- Close the partition once used and unmounted:
  - ```cryptsetup luksClose reference_name```
  
  
  
