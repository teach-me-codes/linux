### Create, Delete and Modify Local User Accounts

- ```/etc/passwd```– This file contains the list of users on the system.
- Format:
  - ```username:password:UID:PrimaryGUID:comment:homedir:defaultshell```
  - Example: ```linuxacademy:x:539:100:linux academy act:/home/linuxacademy:/bin/bash```
- User IDs under 100 are reserved for system users
- Normal user accounts have IDs between 500-1000
- Can directly edit the passwd file to add, remove or modify users
- Changing the shell section of the format to ```/bin/false``` will prevent the user shell login access to the system
- ```/etc/passwd``` permissions must be readable by all, but ```/etc/shadow``` only should be readable by superusers
- ```pwck``` : Verifies the integrity of the users and authentication information. Checks entries for ```/etc/passwd```and ```/etc/shadow``` for proper format
- ```/etc/skel``` :  Skeleton file used when creating new users; allows you to set what files and settings need to be configured as default for every user added
- ```useradd/adduser``` : Creates a user on the system. Some distributions such as Slackware use ```adduser``` instead of ```useradd``` . Note: Both username and password are case-sensitive.
  - ``` -c``` – Comment; can be used as a comment, but is currently used for user’s full name
  - ```-d``` – Sets the user home directory; by default it is /home/user, but can be set to anything
  -```e```– Expire-date; sets the user’s expiration date; on this date the account password will “expire” and the user will no longer have access; format:YYYY-MM-DD
  - ```-p``` – Sets an encrypted password; the pre-encrypted password is added as-is to your ```/etc/passwd```and ```/etc/shadow``` files; this is not the advised method of setting the password
  - ```-M```– Does not create the home directory, even if the /etc/login.defs has the default set to yes
  -```-m```– Creates a home directory at /home/username if it does not exist; files contained in the ```/etc/``` skel directory will be copied into the new user’s home directory; useradd creates a user’s home directory by default
  - ```-G```– Defines all the other groups that the member belongs to; separate each group by a comma
  - ```-g``` – Sets the default group for the user; this is the user’s group when the user first logs in
  -```f```– Defines the number of days after a password expires before an account is permanently disabled; a value of 0 immediately disables the account after password expiration, whereas -1 disables the entire feature
  - ```-k``` – Defines which directory skeleton to use when creating a user; allows you to have different default settings for different users; if the option is not set, it uses the ```/etc/skel``` format by default
- ```/etc/default/useradd``` – Location of default settings for the useradd command
- ```/etc/shadow``` – Contains the encrypted passwords for the user accounts on the system; this and the ```/etc/passwd``` file can be directly modified; the useradd and usermod commands are an interface to automatically modify these files.

- Format:
  -```username:password:days_until_change_allowed:days_before_change_required:days_of_warning_before_expiration:days_between_expiration_activation:expiration_date:special_flag```
  
  - Flag names are self-explanatory; however, a value of -1 or 99999 will indicate that the feature is
disabled for that user

- ```chage``` – Changes and manages user expiry information; changes the number of days between
required password change, and forces password changes for users after x number days
  - ```-E``` – Sets the date that the user’s password will expire
  - ```-I ```– Sets the number of days of inactivity after a password has expired before locking account
  - ```–m``` – Sets minimum number of days between password changes
  - ```-M``` – Sets maximum number of days which a password is valid

- ```userdel```– Deletes a user account and associated files.
  - ```-f```– Forces the removal of the user account even if the user is still logged in; also deletes the user’s home directory and mail; not typically recommended — you can use kill to boot a user
from your system and then remove the user account
  - ```-r``` – Removes the user’s home directory, files located in the user’s home directory and the
user’s mail; does not remove files owned by the user outside of their home directory — use the
```find``` command to find files based off owner.

- ```usermod```– Modifies a user account
  - ```-d``` – Sets the user’s home directory to a new directory
  - ```-e ```– Sets date for when the user account will expire; use YYYY-MM-DD
  - ```-f```– Number of days after a password expires until account is permanently disabled
  - ```-g``` – Group ID/name of the user’s new default login group
  - ```-G``` – List of extra groups the user is a member of
  - ```-l``` – Changes the login name of the user
  - ```-L``` – Locks the user’s account
  
 #### Create, Delete and Modify Local Groups

- ```groupdel``` – Deleted group; if any user has this group as their primary group, then the group cannot be removed until it is removed as the primary group
- ```groupmod```– Modify group name or group ID
  -```-g``` – Specify a new group ID; returns error if group already exists
  - ```-o``` – When used with -g , allows two groups to share the same group ID
  -```-n``` – Specifies a new group name
  
- ```/etc/group``` – This file contains a list of groups and all the members associated with the groups
- Example of /etc/group :
  - ```groupName:Password:GUID:userlist```
- ```groupadd``` – Adds a group to the system
  -```-g``` – Specifies a group idea; if not specified it will auto-select one for you
  - ```-r``` – Instructs groupadd to pick a group ID; less than 500 used for system groups
  -```-f```– Forces group creation even if another group already exists
  
  
