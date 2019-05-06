 

a Linux Academy

Contents

 

Essential Commands

Create and Edit Text Files

Search for Files

Use Input/Output Redirection, Compare Text Files, Compare
Binary Files .................................................................................................................................................

Archive, Compress, Unpack and Decompress Files ........................................
List, Set and Change Standard File Permissions .................................................

Transfer Files Securely Via SFTP/SCP. .........................................................................

Operation of Running Systems .................................................................................................

Change the Priority of a Process/Identify Resource Utilization by
Process

Manage the Startup Processes and Services

Managing User Processes ............................................................................................................
Set File Permissions and Ownership ................................................................................
Installing Software Packages (DebiamUbuntU) ....................................................
Installing Software Packages (Red Hat/RPM) ......................................................

User and Group Management. ...................................................................................................

Create, Delete and Modify Local User Accounts ...............................................
Create, Delete and Modify Local Groups ...................................................................

Networking ...................................................................................................................................................

Conﬁgure Network Services to Start on Boot — systemd ___________________________
Implement Packet Filtering ........................................................................................................
Monitor Network Performance ..............................................................................................

Conﬁgure the Firewall ....................................................................................................................

Service Conﬁguration ........................................................................................................................

Provide/Conﬁgure Network Shares Via NFS/CIFS ..........................................

10
11

12

12

14

14

Related Courses

Linux F ozmdan'on

Certiﬁed S_slem

Administrator

Need Help?

Linux Academ
C0117mmzil_

and you can
always send in a
supporl Iickel on
our website 10 talk
10 an instruclor!

 

Conﬁgure an SMTP Service ..................................................................................................... 20

Conﬁgure SSH—Based Remote Access Using Public/Private Key

 

Pairs .................................................................................................................................................................... 22
Conﬁgure an HTTP Server ......................................................................................................... 23
Conﬁgure HTTP Server Logs .................................................................................................. 23
Conﬁgure SSL With Apache Server _____ 25
Set Up Name—Based Virtual Web Hosts ....................................................................... 26
Set Up Name Based Virtual Web Hosts With SSL. ............................................ 26
Storage Management. ......................................................................................................................... 27
Virtualization. .............................................................................................................................................. 29
Conﬁgure a Hypervisor to Host Virtual Guests .................................................... 29

Related Courses

Linux F oundan'on

C erli '65] SS [em

Administrator

Need Help?

Linux Academ
C onmmni y

and you can
always send in a
supporl Iickel on
our websile to talk
10 an instruclor!

 

LFCSA Study Guide

UnuxAcademy

 

 

Create and Edit Text Files

- vi/vim

))

Full screen editors; v1' is always available since it is a POSIX requirement, v1' m may need to be
installed)

v1 filename

Multiple modes:

— The ESC key always returns to command mode

Command mode allows for navigation and the entering of commands using combinations of

one or more letters; these can be preﬁxed With numeric values for repetition

Ex mode allow ﬁle manipulation; to enter this mode, type a colon (:) followed by the

command desired

Insert mode to edit text; enter this post by pressing 'i

v1' command examples:

h — Move one character left

5 — Move down line

k — Move up line

l — Move one character right
H — Move to top of screen

L — Move to bottom of screen
G — Move to end of ﬁle

0 — Move to beginning of line
$ — Move to end of line

'i — Insert at current position
I — Insert at beginning of line
x — Delete character

dd — Delete line

0 — Create a blank line after current line

_1_

LFCSASmdyGuMk UnuxAcademy

 

— 0 — Create a blank line before current line

— Additional commands can be found in the v1' /v1' m man pages
Text ﬁles can be created by various methods outside of v1' , v1' m or other editors:
» touch testfile.txt

— Creates a blank ﬁle called t est“ 1' [e .t Xt owned by the current user in the current directory
» echo “Some value” > testfile.txt

— Creates a ﬁle called t est“ 1' [e .t Xt, owned by the current user in the current directory,
containing the text following the echo command (in this instance, “Some value”)

— Redirection of almost any command Will take the output and place it into a ﬁle

Search for Files

vi/vim
» Moves cursor to a certain location, based on a search

» In command mode, press 1‘ and then a character; this moves to the next occurrence of value in
the current line

» To search for a value in the entire ﬁle, in command mode, use / and then type the value
» Similar to sed, you can use v1' / v1' m to replace values:
—- :%s/oldvalue/newvalues/g
H n d
» Commonly used to ﬁnd ﬁles by name, by user and/ or by type
» find /Start/d1r —name “value“
— Finds ﬁles in /start/dir With the name value
» —maxdepth
— The number of subdirectories to search
» —type
— f — Regular ﬁle
» —size
— +#[MGT] — number and type of storage value (mega, giga, terabytes)

» —perm

LFCSA Study Guide Linux Academy

 

 

— Numeric designation of permissions to look for
» -EXEC
— rm ‘{}’ +
. Execute the command I'm on the values/ﬁles Within the results of the H nd command

0 Many more values and examples in the ma n pages

Use Input/Output Redirection, Compare Text Files, Compare
Binary Files

0 Redirection is used to direct the output of a command or task into a ﬁle, or direct the contents of a
ﬁle to a command

» > — Redirect output to a ﬁle, overwriting the contents if any exist
» >> — Redirect output to a ﬁle, appending to the contents if any exist

» I — “Pipe” the output to another command and/ or ﬁle

Archive, Compress, Unpack and Decompress Files

0 t a r
» Can be used to archive, unarchive, compress and decompress ﬁles

» Archives values in the /etC directory in a ﬁle called etc .t ar:

— tar cvf etc.tar /etc

» Decompresses archive:

— tar xvf etc.tar

» Archives values in the /etC directory in a ﬁle called etc .t ar, and also compress that ﬁle With
g 21' p:

— tar cvzf etc.tar /etc

» List contents of archived ﬁle:

— tar tvf etc .t ar
» C —Archive
» v — Verbose
» f — Write to a ﬁle
» X — Extract

» z — gz1' p compression

LFCSASmdyGuMk UnuxAcademy

 

 

» j — bz1' p compression
» A — Append ﬁles to existing archive

» t — List contents

List, Set and Change Standard File Permissions

chmod

» Used to change the read, write and execute privileges of a ﬁle or directory for the owner, the
group(s) they belong to, and all others (often called everyone)

chmod 777 somefile.txt

» This would change the ﬁle someﬁ [e .t Xt to read/write/execute for the owner, the group
belonged to, and everyone else (universal permissions)

Numeric and character values for the permissions are as follows:
» r — 4 — Read permissions
» w — 2 — Write permissions
» X — 1 — Execute permissions
— Adding these values together determines the privilege number
Exanqﬂezchmod 755 somefile.txt
» User: read (4) + write (2) + execute (1) = 7
» Group: read (4) + execute (1) = 5
» Everyone: read (4) + execute (1) = 5
Permissions can also be changed by single category using character representation
Exanqﬂezchmod g+rw somefile.txt
» Adds group permissions of read and write to the ﬁle called someﬁ [e .t Xt
— Character values as follows:
I u — User
I g — Group
I a — Everyone
I r — Read

I w — Write

LFCSASmdyGuMk UnuxAcademy

 

I X — Execute

I + — Add the values indicated

I - — Remove the values indicated
- chown

» Change ownership to a speciﬁc user and/ or group

0 chgrp

» Change group ownership to a speciﬁc group

Transfer Files Securely Via SFTP/SCP

. SC p
» Based on the SSH secure protocol for transfer of ﬁles

» Transfer ﬁles to/from a server:

—- scp user@Rem0teIP:/rem0te/d1r/myfi[e.txt /h0me/user

» Copy the remote ﬁle called myﬁ [e .t Xt to the local /h0me/user directory:
—- scp myfile.txt user@Rem0teIP:/rem0te/d1r

» Copies the local ﬁle called myﬁ [e .t Xt to the remote directory /rem0te/d1' r:
0 sftp
» SSH—based ﬁle transfer program Whose behavior is based on the less—secure program, FTP
» Same format as the scp in terms of individual ﬁles or directories
» Add batch processing capabilities:
—- sftp —b batch.file

» Similar to expect scripts, using FTP commands to run through many transactions in one listing

99.9mm,9f...B.unnin.g..SY§Igm§ .................................................................

Change the Priority of a Process/Identify Resource Utilization
by Process
0 jobs
» Displays minimal information about processes associated With the current session

0 p5

LFCSASmdyGuMk UnuxAcademy

 

 

v

> By default, pS only displays process that were run from its own terminal
» —A \ —e — Displays all processes on a system
» —U — Displays processes given by a speciﬁed user

» —H — Groups processes and use indentation to show the hierarchy of relationships between
processes

» —w — Tells pS not to truncate to system
0 uptime
» Find uptime and display load average
. bg
» Restores a job to running status, but in the background
. {g
» Use CTRL+Z to pause a program and, then f g to send the program to f ore ground
. k1 l l
» Can be used to stop executing processes, uses PID

0 nohup

» Run a command immune to hangups, With output to console or non—tty

. killall

» Can be used to kill all processes of a certain name

0 free
» Show free memory and swap

. Common kill signals:
» SIGHUP 1 HANGUP
» SIGINT Z INTERRUPT FROM KEYBOARD
» SIGKILL 9 KILL SIGNAL

— This signal is not blockable and causes the program to terminate abruptly; only use if you
can’t terminate With 15
» SIGTERM 15 TERMINATION SIGNAL
— Asks the program to ﬁnish What it is doing, then exits; clean exist; the preferred way of

killing processes

» SIGSTOP 17,19,23 STOP THE PROCESS

— When a child process exits from a parent process it sends signal 1
_ 6 _

LFCSA Study Guide

UnuxAcademy

 

 

Signals in the man page man —k 51' g nal

Manage the Startup Processes and Services

Reboot the system:

» reboot

» systemctl reboot

» shutdown —r now

—I' — reboot

n 0w — Reboot immediately

+5 — Wait 5 minutes and then reboot
+0 — Same as now

01:01 — 1:01AM shutdown

-C — Cancel a scheduled shutdown

» init 6

— The inil system in Red Hat 7 is depreciated. However, runlevels are still compatible for this

current version for backwards compatibility

Shutdown the system (no reboot/power off):

» systemctl halt

» ha 1’:

» shutdown —h n0w(—h1neans1uﬂ0

» initﬂ

Physically power off the system:

» systemctl poweroff

» poweroff

» shutdown —P

Managing User Processes

nice

» Run a program With modiﬁed scheduling priority

renice

» Alter priority of running processes

LFCSASmdyGuMk UnuxAcademy

 

t 0 p
» Display Linux processes
» While running:
— K — Kills processes
— Q — Quits processes
— r — Change process priority
— s — Change update rate
— P — Sort by CPU usage
— In — Sort by memory usage; can also show uptime, memory info, and load average
» From the command line:
— —d — Speciﬁes delay between updates
— —p — Lists up to 20 speciﬁc PIDs
— —n — Display certain number of updates then quit

— —b — Batch mode

Set File Permissions and Ownership

chmod

» Used to change the read, write and execute privileges of a ﬁle or directory for the owner, the
group(s) they belong to, and then all others (often called everyone)

chmod 777 somefile.txt

» This would change the ﬁle s0meﬁle.lxl to read/write/execute for the owner, the group belonged
to, and everyone else (universal permissions)

Numeric and character values for the permissions are as follows:
» r = 4 — read permissions
» w = 2 — write permissions
» X = 1 — execute permissions
— Adding these values together determines the privilege number
Exanqﬂezchmod 755 somefile.txt

» User: read (4) + write (2) + execute (1) = 7

—8—

LFCSASmdyGuMk UnuxAcademy

 

 

» Group: read (4) + execute (1) = 5

» Everyone: read (4) + execute (1) = 5
I Permissions can also be changed by single category using character representation
I Exanqﬂezchmod g+rw somefile.txt

» Adds group permissions of read and write to the ﬁle called someﬁlelxl
I Character values as follows:

» u — user

» g — group

» a — everyone

» r — read

» w — write

» x — execute

» + — add the values indicated

» - — remove the values indicated

I chown

» Changes ownership to a speciﬁc user and/ or group

I chgrp

» Changes group ownership to a speciﬁc group

Installing Software Packages (Debian/Ubuntu)

I /etC/apt/sources . list

» Stores the repository locations that apt uses to search for packages speciﬁc to your system

I a pt —g et
» Package handling and installation utility for Debian—based distributions

» Installs packages by name and includes dependent packages during install
I d p k g

» Installs .deb package ﬁles on Debian—based systems
» —1' — Install as well as conﬁgure package

» —r — Remove package

LFCSASmdyGuMk UnuxAcademy

 

 

» -C omci 9 U r e — Conﬁgures a package
» -C — List contents of a package

» -S — List status of package (installed or not)

apt—cache
» Allows searching of named package or shows installed packages
—- apt—cache pkgnames-—Showin$aﬂed

— apt—cache search — Search for named package

dpkg—reconfigure

» Reconﬁgure an already—installed package
aptitude

» High level package management interface for Debian—based distributions

Installing Software Packages (Red Hat/RPM)

r p m
» Package installation utility for Red Hat—based distributions
» —n 0 d e p S — Install the package without worrying about installed dependencies
» —1' — Install
» —K — Check package signature
» —V — Verify
» —a — All packages
— —Va — Verify all packages
» —U — Upgrades or installs a new package
» —F — Upgrade an already—installed package
» —q — Query a package to determine if already installed
» —e —Erase or uninstall
» —f — Query package—owning ﬁle
» —p — package
» —l — List ﬁles in a package

» —rebu1' [d — Rebuilds a source package

-10-

LFCSASmdyGuMk UnuxAcademy

 

 

» —r ebu 1' lddb — Rebuilds the rpm database
» —q a — Print all install packages
» —q l — List ﬁles in an installed package
» —qf — Determine which installed packaged a ﬁle belongs to
» —q p l — List all ﬁles in an RPM package
» —Checks1'g—Same as —K
I /etc/yum.repos.d
» Directory containing yum source repository ﬁles
I Cp1' 0 — Create cpio archive
» —d — Create leading directories where needed
» —1' — Extract
» —U — Replace all ﬁles without asking
» —m — Retain previous modiﬁcation times when creating ﬁles
I rmecpio
» Converts RPM packages to CPIO compressed ﬁles

» Used primarily to extract ﬁles from a RPM package without installing the RPM package

—- rmecpio file.rpm | cpio —d1um

Shell

I ec h 0 — 35$ — Displays current shell process

I 35? — Prints the exit value of the command to the screen

I Exit code 0 — Means command completed successfully
I 35! — PID of last job run in background

I 35* — Expands all parameters passed

I 3535 — Contains current process ID

I $@ — Each passed parameter expands to a different word
I 350 — Show the name of the shell or script

I $_ — Set at shell startup and contains the absolute ﬁle name of the shell/script being execute;
expands last argument to the previous command

-]]-

LFCSASmdyGuMk UnuxAcademy

 

 

Create, Delete and Modify Local User Accounts

I /etC/passwd — This ﬁle contains the list of users on the system.

I Format:

» username:passw0rd:UID:PrimaryGUID:c0nment:homedir:defaultshell

» Exaﬁqﬂe linuxacademy:x:539:1@@:linUX academy act:/h0me/linuxacademy:/b1n/
as

I User IDs under 100 are reserved for system users
I Normal user accounts have IDs between 500—1000
I Can directly edit the pa sswd ﬁle to add, remove or modify users

I Changing the shell section of the format to /b1' H/‘F a [5e will prevent the user shell login access to
the system

I /et C/ p a sswd permissions must be readable by all, but /et C/S h a d 0w only should be readable by
superusers

I pwc k — Veriﬁes the integrity of the users and authentication information. Checks entries for /et C/
passwd and /etC/Shad0w for proper format

I /et C/Ske l — Skeleton ﬁle used when creating new users; allows you to set what ﬁles and settings
need to be conﬁgured as default for every user added

I U S e r a d d/a d d U 5 er — Creates a user on the system. Some distributions such as Slackware use
a d d U SE r instead of U S e r a d d. Note: Both username and password are case—sensitive.

» -C — Comment; can be used as a comment, but is currently used for user’s full name
» —d — Sets the user home directory; by default it is /home/user, but can be set to anything

» —e — Expire—date; sets the user’s expiration date; on this date the account password will “expire”
and the user will no longer have access; format: YYYY—MlVI—DD

» —p — Sets an encrypted password; the pre—encrypted password is added as—is to your /etc/passwd
and /etc/shadow ﬁles; this is not the adVised method of setting the password

» —M — Does not create the home directory, even if the /etc/login.defs has the default set to yes

» —m — Creates a home directory at /home/username if it does not exist; ﬁles contained in the /etc/
skel directory will be copied into the new user’s home directory; useradd creates a user’s home
directory by default

» —G — Deﬁnes all the other groups that the member belongs to; separate each group by a comma

-]2-

LFCSASmdyGuMk UnuxAcademy

 

—g — Sets the default group for the user; this is the user’s group when the user ﬁrst logs in

—f — Deﬁnes the number of days after a password expires before an account is permanently
disabled; a value of 0 immediately disables the account after password expiration, whereas —1
disables the entire feature

—k — Deﬁnes which directory skeleton to use when creating a user; allows you to have different
default settings for different users; if the option is not set, it uses the /etc/skel format by default

I /et C/d e1“ a U lt/U S e r a dd — Location of default settings for the useradd command

I /et C/Shadow — Contains the encrypted passwords for the user accounts on the system; this and
the /etc/passwd ﬁle can be directly modiﬁed; the useradd and userInod commands are an interface to
automatically modify these ﬁles.

I Format:

))

username:password:days_unt1l_change_a[lowed:days_bef0re_change_requ1red:days_
0f_warn1ng_bef0re_exp1rat10n:days_between_exp1rat10n_act1vat10n:expirat10n_
date:spec1al_flag

Flag names are self—explanatory; however, a value of —1 or 99999 will indicate that the feature is
disabled for that user

I Cha 9 e — Changes and manages user expiry information; changes the number of days between
required password change, and forces password changes for users after X number days

—E — Sets the date that the user’s password will expire
—I — Sets the number of days of inactivity after a password has expired before locking account
—m — Sets minimum number of days between password changes

—M — Sets maximum number of days which a password is valid

I user d e l — Deletes a user account and associated ﬁles.

))

—f — Forces the removal of the user account even if the user is still logged in; also deletes the
user’s home directory and mail; not typically recommended — you can use k1 l l to boot a user
from your system and then remove the user account

—I' — Removes the user’s home directory, ﬁles located in the user’s home directory and the
user’s mail; does not remove ﬁles owned by the user outside of their home directory — use the
H n d command to ﬁnd ﬁles based off owner.

I usermod — Modiﬁes a user account

))

))

))

—d — Sets the user’s home directory to a new directory
—e — Sets date for when the user account will expire; use YYYY—MlVI—DD

—f — Number of days after a password expires until account is permanently disabled

-]3-

LFCSASmdyGuMk UnuxAcademy

 

 

» —g — Group ID/name of the user’s new default login group
» —G — List of extra groups the user is a member of
» —l — Changes the login name of the user

» —L — Locks the user’s account

Create, Delete and Modify Local Groups

gr 0U pde l — Deleted group; if any user has this group as their primary group, then the group cannot

be removed until it is removed as the primary group

9 r 0 U pmod — Modif y group name or group ID

» —g — Specify a new group ID; returns error if group already exists

» —0 — When used with —g, allows two groups to share the same group ID

» —n — Speciﬁes a new group name

/et C/g r 0U p — This ﬁle contains a list of groups and all the members associated with the groups

Exanqﬂeof/etc/group

» groupName:Passw0rd:GUID:Userlist

groupadd — Adds a group to the system

» —g — Speciﬁes a group idea; if not speciﬁed it will auto—select one for you

» —r — Instructs groupadd to pick a group ID; less than 500 used for system groups

» —f — Forces group creation even if another group already exists

Conﬁgure Network Services to Start on Boot — systemd

Sysvinit (older serVice management, CentOS/RHEL 6.x, Ubuntu/Debian prior to 1004/23)

» Install an example server serVice:

—- yum install openssh—server

» Enable the serVice to start on reboot:

—- chkconfig openssh—server

» Start the serVice in current session:

—- service openssh—server start

_]4_

LFCSASmdyGuMk UnuxAcademy

 

I Systemd (modern serVice management, all recent distributions)

» Install an example server serVice:

—- yum install openssh—server

» Enable the serVice to start on reboot:

—- systemctl enable openssh—server

» Start the serVice in current session:

—- systemctl start openssh—server

» Query the status of a serVice (running or otherwise):

—- systemctl status openssh—server

Implement Packet Filtering
I iptables ﬁrewall

I List the existing rules:

» sudo iptables —L
I Policies generally available:
» ACCEPT — Lets the packet through
» DROP — Drops the packet quietly
» REJECT — Rejects the packet and returns a message to the requestor

I General format for iptables rules:

» iptables —A name_0f_cha1n criter1a_t0_meet —j target_0f_rule
— —A — Append the rule to the end of the chain
— name_0f_cha1' n — One of INPUT, OUTPUT or FORWARD

— C r 1' t eri a_t0_meet — The conditions against which all packets are inspected against to
determine whether the rule applies

— t a r get_0f_r U [e — The action or policy to apply (ACCEPT, REJECT, or DROP)

I Example: Drop ICMP ping requests between servers:
» iptables —A INPUT —pr0t0col 1cmp —1n—1nterface enpUsB —j DROP

— This causes ping commands to drop with no returned response
I Example: Reject ICMP ping requests between servers:

» iptables —A INPUT —pr0t0col 1cmp —1n—1nterface enpUsB —j REJECT

-]5-

LFCSASmdyGuMk UnuxAcademy

— This returns a message to the requestor: “Destination Port Unreachable”

— This can inadvertently expose that your IP address is valid; this setting should be used only
internally when you want the client systems to know the port is ﬁltered

Monitor Network Performance

I Socket connections
» Use the utility 55 (replacement for net St at)
— “socket statistics”

» Show all TCP ports open on a server:
— 55 —t —a
I —t — All TCP ports
I —a —All connections
» Show established connections with their timers:
— 55 —t —0
I —t —All TCP ports
I —0 —Time established
» Filter by socket:
—- ss —tn sport : :22
I Sport : : 22 — Source port of the established connection
I Identify open ports and active hosts
» Use the nma p utility (defensive scanning of your own network)

» Scan ports on the system or remote host

—- nmap —A —sS [IP/Hostname]
I —A — Deep scan for all discoverable ports and serVices

I —55 — Use TCP SYN (prevents leaving a logged footprint on the remove system)

I Monitor all IP Trafﬁc
» iptraf

— Ncurses—based, shows all packets across all interfaces (local, physical, Virtual)

» dStat

-]6-

LFCSASmdyGuMk UnuxAcademy

 

 

— Shows second—by—second monitoring statistics on your system by process, including read/
write, PIDs and system usage

Conﬁgure the Firewall
I Firewalld is the default ﬁrewall daemon
» Manage at the command line with ﬁrewall—cmd
I Allows working with serVices, zones and rules, as well as import custom rules from XlVIL ﬁles

I Service conﬁgurations are stored in XlVIL ﬁles located at /USI’/ [1' b/fi rewa lld/Servi C es and /
etC/ﬁ rewa lld/Servic es (depending on user—deﬁned (in /USI’/l1'b) or system (/etC/f1'rewa 1 1d)
level deﬁnitions)

I Restart the ﬁrewall:

» systemctl restart firewalld
I Reload the persistent ﬁrewall rules:
» f1rewall—cmd ——reload

I Zone management parameters

» ——get—defaULt—zone
» ——set defaULt—zone
» ——get—aCt1ve—zones
» ——get—z0nes

» ——list—all

» ——list—all—zones

» ——new—z0ne

» ——delete—zone

» ——permanent

» ——zone

I Current vs permanent ﬁrewall rule changes

» Commands making rule changes of any kind are NOT persistent (in other words, will not persist
across reboots or serVice restarts) UNLESS the — — perma n ent option is speciﬁed

» Commands making rule changes take immediate effect UNLESS specifying the — — perma n ent
parameter, rules specifying permanent must be applied with a subsequent — — r e [0 ad

I Service management options

» ——get—serv1ces

-]7-

LFCSASmdyGuMk UnuxAcademy

 

 

» ——list—serv1ces
» ——query—service
» ——add—serv1ce

» ——rem0ve—serv1ce
» ——new—serv1ce

» ——delete—serv1ce

I Port management options

» ——list—p0rts
» ——add—p0rt

» ——rem0ve—p0rt
» ——query—p0rt

I When adding ports, the port number must specify TCP/UDP for application ranges can be added
with dashes

» ——add—p0rt 500—599/TCP for example

I Rich rule management

» ——list—r1Ch—rules
» ——add—r1Ch—rule

» ——rem0ve—r1Ch—rule
» ——query—r1Ch—rule

I Example: Rich rules to allow inbound HTTP access from a network IP range 10.0.1.0/24, logging
each one at the info log level and making the change permanent:

» f1rewall—cmd —add—r1Ch—rule rule—family:“1pv4“ source address:”1@.@.1.@/Z4“
service name=”http“ [0g pref1X:“HTTP Allow Rule” level:“1nf0” accept

——permanent

» Uppates the default zone (public by default) XlVIL rule ﬁle in /etC/f1' rewa lld/zones/pUb [1' C .
xm

I Port f orwarding
» ——list—f0rward—p0rts
» ——add—f0rward—p0rt

» ——rem0ve—f0rward—p0rt
» ——query—f0rward—p0rt

I Example: Forwarding by redirecting SSH from port 22 to port 2222 in the DMZ zone:

-]8-

LFCSA Study Guide

UnuxAcademy

 

 

» f1rewall—cmd —zone DMZ —permanent —add—f0rward—p0rt

p0rt:22:proto:tcp:t0p0rt:2222

.§_9r.y.i.99..§Qntiguratign ...............................................................................................

Provide/Conﬁgure Network Shares Via NFS/CIFS

Installing the server packages (server setup):

» yum install nfs—Utils

Create a directory for the shared or exported ﬁlesystem:

» mkdir /var/myshare

Change the permissions to be sure everyone has access:

» chmod —R 777 /var/myshare
Enable and start the appropriate serVices:
» rpcbind

» nfs—server

» nfS—lOCk

» nfs—idmap

Create/edit the /et C/export 5 ﬁle, add the ﬁlesystem with appropriate options:

» /var/myshare 192.168.1.@/24(rw,sync,n0_r00t_squash,n0_a[t_squash)

— rw — Read/write ﬁlesystem

— syn C — Keep local and remote ﬁlesystem caches in sync

— n0_r00t_squash , n O_a l t_squash — Do not attempt to do root or user level remapping

based on UIDs for security

Start the NFS Server serVice:

» systemctl restart nfs—server

Install the packages (client setup):

» yum install nfs—Utils

Create a directory to mount the share:

» mkdir /mnt/shareddr1ve

Enable and start the appropriate serVices:

» rpCbind

-]9-

LFCSASmdyGuMk UnuxAcademy

» nfs—server
» nfS—lOCk

» nfs—idmap

I Example: Command line mount

» mount —t nfs SERVERIP:/var/myshare /mnt/shareddr1ve

I Example: Persistent mounting in / et C/‘F St a b

» 3ERVERIP:/var/myshare /mnt/shareddr1ve nfs default 0

I Mount automatically on boot or on demand:

» mount —a

Conﬁgure an SMTP Service

I Packages to install:
» dovecot

» p 0 s t f 1' X
— CentOS/RHEL — yum install dovecot postﬁx
— DebiarﬂUbuntu — apt—get install dovecot postﬁx

I Add email aliases:
» /etC/postf1X/aliases

—- email_acc0unt: alias_name1, alias_name2
— More than one alias can be added for each account to alias

— Refresh the alias table:

- postalias /etC/postf1X/aliases

I Conﬁgure postﬁx:
» /etC/postf1X/ma1n.cf

—- myorigin : /etC/ma1[name(ordonuunimeh)
I The ﬁle that contains the domain name of the server
I Can contain the domain name directly, ﬁlename is older standard still in use

— mydesti n at1'0 n : List of domains the mail server will deliver messages to locally instead
of forwarding to another system/mail server

—- mydestination : myserver.d0ma1n.c0m, localhost.d0ma1n.c0m, localhost

-20-

LFCSASmdyGuMk UnuxAcademy

 

 

(examples)

—- mynetworks : subnet

I Indicates that we are serving IPs in the local subnet the server exists on

—- 1net_1nterfaces : all

I Accepts connections and messages to/from all deﬁned network interfaces (localhost,
physical, Virtual, other)

—- mailbox_size_lim1t : ##ﬁﬁﬁ

—- message_size_lim1t : ##ﬁﬁﬁ

I Self—explanatory, can be set to whatever requirements needed, in bytes

» /etC/postf1X/transport

— Contains deﬁnitions of relationships between domains and the next server that mail
messages need to be forwarded to. For example:

I example.d0ma1n.c0m local:

I .example.c0ma1n.c0m local:

» Process the transport ﬁle and create/update the values to the mail DB format:

—- Postmap /etC/postf1X/transport

Restrict access to SMTP
» /etC/postf1X/ma1n.cf

—- smtpd_helo_requ1red : yes

I Require mail client to introduce the mail transaction with standard HELO identiﬁcation

—- smtpd_helo_restsr1ct10ns : perm1t_mynetw0rks, reject_1nvalid_helo_
hostname

I Permits only deﬁned networks (see above) and hosts that identify with HELO
appropriately

—- smtpd_sender_restr1ct1ons : perm1t_mynetw0rks, reject_unkn0wn_sender_
domain

I Only accepts email to be sent from deﬁned networks and rejects all others from
unknown domains

—- smtpq_reC1p1ent_restr1ct10ns : perm1t_mynetw0rks, reject_unauth_
dest1nat10n

I Accept only locally—deﬁned user destinations (see above conﬁguration) and reject any
unauthorized

Enable and restart the postﬁx serVice:

-2]-

LFCSASmdyGuMk UnuxAcademy

 

 

» systemctl enable postfix

» systemctl restart postfix
I Conﬁgure Dovecot:

» Initial installation supports IMAP and POP3, need to add IMAPS
—— /etC/d0vecot/d0vecot.Conf
I Protocols : p0p3 imap 1map3
I Test listening on available ports:
» netstat —npltU | grep dovecot

— Should see entries for ports 110 (pop3), 143 (imap), 993 (imaps) and 995 (pop3 secure)

I Use local mai 1 subsystem to test:

» mail email_acc0unt

— This is our alias account from earlier in the conﬁguration, should go to two users, as deﬁned
inthe /etC/postf1X/aliasesfﬂe

» Enter subject, message; exit to send

» Log in as either of the aliased users, email should be available for them to read using local mai 1
command

Conﬁgure SSH-Based Remote Access Using Public/Private
Key Pairs

I Generate a public/private key pair for SSH key exchange utilization:

» ssh—keygen

» Passphrase prompt is optional, designed to add an additional security layer (i.e. both the key
AND passphrase would then be required when connecting to a server in this manner)

I Copy the public key from a user to a remote host (note that the referenced account on the remote
host must already exist)

» ssh—Copy—id user@[servername/Serverip]
— Prompts for remote user password the ﬁrst time
— Does not connect to the session on the key copy, copies the key only
I Testing:
» ssh user@[servername/Serverip]

— If done correctly, prompts for passphrase (if one was entered) or simply connects you to the
remote host as the indicated user if no passphrase was entered during key creation

-22-

LFCSASmdyGuMk UnuxAcademy

 

 

Conﬁgure an HTTP Server

httpd

Apache serVice to install:

systemctl enable httpd

systemctl start httpd

))

By default, listening on port 80

Key conﬁguration ﬁles and directories:

))

/etC/httpd

— Primary http conﬁguration directory, all httpd conﬁguration ﬁles and directories root here

/etC/httpd/C0nf
— magic — mime conﬁguration ﬁle for ﬁletype deﬁnitions

— httpd.conf — Primary overall Apache conﬁguration, default location for Vhosts

/etC/httpd/C0nf.d

— User and index conﬁguration ﬁle (user directory, welcome message and indexes)

/etC/httpd/C0nf.d.m0dules

— Module conﬁguration ﬁles (as referenced in httpd.con1)
/etC/httpd/logs

— Link to /Var/log/httpd by default
/etC/httpd/m0dules

— Apache modules, link to /usr/lib64/httpd/modules by default
/etC/httpd/run

— Temporary run ﬁles for httpd process, link to /run/httpd by default
/var/www/html

— Default directory for website content

Conﬁgure HTTP Server Logs

Log format contained, by default, in the httpd.conf ﬁle and looks like, for example:

))

LogFormat “%h %l %U %t \”%r\” %>s %b” conmon

Can always be overridden within a speciﬁc Vhost, using the same directive and format

Format options are:

-23-

LFCSASmdyGuMk UnuxAcademy

 

 

))

°/oa — Remote client IP

°/oA — Local client IP

°/ob — Number of bytes transmitted

°/oB — Number of bytes transmitted

°/o{ v a r } e — Value of environment variable indicated
°/of — Requested ﬁle

°/oh — Remote host name (or IP if reverse lookup fails)
°/oH — Requested protocol

°/o{var }1' — Contents of the header line name; for example: (user—agent)i
°/ol — Remote log name

°/om — Request method

°/o{var } n — Contents of the note named

°/o{ v a r } 0 — Contents of the header named

°/op — Canonical port that serViced the request

°/oP — Process ID that serViced the request

°/oq — Query string or search argument used (prefaced with “?”)
°/or — First line of the request

°/oS — Server response status (i.e. HTTP 200 OK)

°/ot — Time in common log formatting

°/oT — Time (seconds) taken to serve the content

°/oU — Named of authenticated user (if any)

°/oU — Requested URL path

°/ov — Server name servicing the request

°/oV — Server name according to UseCanonicalName setting

I Reference names are given custom logging formats (like common in the example above)

I Er r or Log and AC C essLog directives can then refer to the reference names (when conﬁgured in
htt pd . C om“) rather than overriding the LogForInat directive within a Vhost

))

Example:

_24_

LFCSASmdyGuMk UnuxAcademy

 

—- ErrorLog logS/mysite—error.log reference_name

» Would format the site error log ﬁle, using the referenCLname format as deﬁned in httpd.
conf

Conﬁgure SSL with Apache Server

Install the openssl utility
» yum install openssl

» apt—get install openssl

Generate a certiﬁcate key ﬁle (standard example):

» openssl req —X5@9 —n0des —days 365 —newkey rsa:2@48 —key0Ut /path/t0/cert/
d1r/site.key

— Generates a key for a certiﬁcate authority to generate a valid certiﬁcate expiring one year
from the date of creation with industry standard NoDES, x509 RSA 2048bit encryption

Generate a certiﬁcate key ﬁle and use it to generate a self—signed certiﬁcate for local use:

» openssl req —X5@9 —n0des —days 365 —newkey rsa:2@48 —key0Ut /path/t0/cert/
d1r/site.key —out /path/t0/cert/d1r/site.crt

— Takes the key created and immediately signs it locally with the information provided during
certiﬁcate creation

Install mod_ssl:

» yum install m0d_ssl
Activate mod_ssl:

» CentOS/RHEL — Restart Apache after mod_ssl installation:
—- systemctl restart httpd

» DebiarﬂUbuntu — Enable the module and restart Apache:
—- a2enm0d m0d_ssl

—- systemctl restart apacheZ

Vhost directives needed

» <V1rtualHost *:443>

— Enables port 443 for current Vhost
» SSLEngine 0n

— Enables SSL for the current Vhost
» SSLCertificateKeyFile /path/t0/cert/d1r/site.key

-25-

LFCSASmdyGuMk UnuxAcademy

 

 

— Whatever path that the created key ﬁle exists in
» SSLCertificateFil /path/t0/cert/d1r/site.crt

— Whatever path that the install certiﬁcate ﬁle exists in

Restart Apache once Vhosts are created to activate them on the server

Set Up Name-Based Virtual Web Hosts

Create Virtual host directory:

» mkdir /etC/httpd/vhost.d
Add the directory to /etc/httpd/conf/httpd.conf

» include vhost.d/*.C0nf

Externalizes Vhost conﬁguration; by default, Vhost conﬁgurations can be added directly to htt pd .

conf

Sample conﬁguration for domain myhost . 5a mple . C0m:

» ﬁleruune:/etC/httpd/vhost.d/myhost.sample.c0m_http.c0nf
—- <V1rtualHost *:8@>
—- ServerAdmin adm1n@myhost.sample.com
—- DocumentRoot /var/www/html/myhost.sample.C0m
—- ServerName myhost.sample.c0m
—- ServerAlias myhost
—- ErrorLog logS/myhost.sample.C0m—err0r_log
—- CustomLog logS/myhost.sample.C0m—access_log conmon

—- </V1rtualHost>

Test the conﬁguration:

» apachectl configtest

Apache must be restarted or reloaded gracefully to read the new Virtual host:
» systemctl restart httpd
» systemctl reload httpd

Show a dump of the Virtual host conﬁguration for Apache in general:

» httpd —D DUMP_VHOSTS

Set Up Name Based Virtual Web Hosts with SSL

Vhost directives needed:

-26-

LFCSASmdyGuMk UnuxAcademy

 

 

» <V1rtualHost *:443>

— Enables port 443 for current Vhost
» SSLEngine 0n

— Enables SSL for the current Vhost
» SSLCertificateKeyFile /path/t0/cert/d1r/site.key

— Whatever path that the created key ﬁle exists in
» SSLCertificateFil /path/t0/cert/d1r/site.crt

— Whatever path that the install certiﬁcate ﬁle exists in

5:9:an.M.an.a99ment ................................................................................................

I Standard File Systems
» Partitioning
—- fdisk/gdisk /dev/dr1ve

I Allows us to create a partition from the available indicated disk

I Can set type of partition (GPT or lVIBT depending on use), list the partition types in the
menu

» Format the ﬁlesystem partition created:

—- mkfs —t ext4 /dev/disk1
I Formats the disk partition d1 5 k1 as an eXt4 partition

» Mount the f orInatted partition:
—- mkdir /mnt/m0unt
—- mount —t ext4 /dev/disk1 /mnt/m0unt

I Mounts the formatted drive, as an ext4 mount on the created directory

» Persistently mounting the disk above

— Obtain the UUID of the deVice:
I [5 —al /dev/disk/by—UU1d
— Add entry to /etc/fstab:
I UUID:UUDI_OBTAINED /mnt/m0unt ext4 defaults U U

— Mount the deﬁned entry automatically, if not mounted in current session:

' mount —a
_27_

LFCSASmdyGuMk UnuxAcademy

 

 

I This will scan all deﬁned mount points, and if not mounted, mount them using the
deﬁnitions in /EtC/tstab

I Encrypted File Systems

))

System support encrypted ﬁle system query:
—- grep —I conf1g_dm_crypt /b00t/C0nfig—$(Uname —r)

Determine if module is loaded:

—- lsmod | grep dm_crypt

Load module if needed:

—— modprobe dm_crypt
Partitioning

— Handled the same way as a typical disk and drive as deﬁned above in the “Standard File
Systems” section

Install the cryptsetup utility:
—- yum install cryptsetup

Default encryption key setup
— Luks — Linux Uniﬁed Key Setup

Set up the partitions with passphrase:
—- cryptsetup —y [Uksformat /dev/disk1

I Prompts for passphrase for unencrypting drive during mount/use
I Large drives will take a long time to encrypt

Open partition for use:

—- cryptsetup [UksOpen /dev/disk1 reference_name
Format the ﬁlesystem partition created, using the mapper overlay created above

— Handled the same way as a typical disk and drive as deﬁned above in the “Standard File
Systems” section

I Exanqﬂezmkfs —t ext4 /dev/mapper/reference_name

Mount the drive:

—- mount /dev/mapper/reference_name /mnt/m0unt

Close the partition once used and unmounted:

—- cryptsetup [UksClose reference_name

-28-

LFCSASmdyGuMk UnuxAcademy

 

 

Virtualization

Conﬁgure a Hypervisor to Host Virtual Guests

I Install and conﬁgure the necessary packages:

» yum install —y qemU—kvm qemU—img

I Install and conﬁgure the Virtual manager GUI:

» yum install —y virt—manager

-29-
