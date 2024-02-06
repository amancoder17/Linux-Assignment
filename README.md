# Linux-Assignment
Q1)  Create a directory named "MyFiles" in your home directory. Navigate into this directory and list its contents.
Ans ->  aman@aman-Mi-NoteBook-14:~$ mkdir MyFiles
aman@aman-Mi-NoteBook-14:~$ ls
asses  democss  dir1  dir3       Downloads  MyFiles   Public  SS         Videos
buddy  Desktop  dir2  Documents  Music      Pictures  snap    Templates  webdev
aman@aman-Mi-NoteBook-14:~$ cd MyFiles/
aman@aman-Mi-NoteBook-14:~/MyFiles$ ls
aman@aman-Mi-NoteBook-14:~/MyFiles$ 

Q2) Copy  a file named "document.txt" from your home directory to the "MyFiles"  directory. Move the file to a subdirectory named "Documents" within  "MyFiles."
Ans ->  aman@aman-Mi-NoteBook-14:~$ touch document.txt
aman@aman-Mi-NoteBook-14:~$ cp document.txt ./MyFiles/Documents/
aman@aman-Mi-NoteBook-14:~$ cd MyFiles/
aman@aman-Mi-NoteBook-14:~/MyFiles$ ls
Documents
aman@aman-Mi-NoteBook-14:~/MyFiles$ cd Documents/
aman@aman-Mi-NoteBook-14:~/MyFiles/Documents$ ls
document.txt
aman@aman-Mi-NoteBook-14:~/MyFiles/Documents$ 

Q3) Create an empty file named "notes.txt" in the "MyFiles" directory. Afterward, delete the file.

Ans-> aman@aman-Mi-NoteBook-14:~/MyFiles$ touch notes.txt
aman@aman-Mi-NoteBook-14:~/MyFiles$ ls
Documents  notes.txt
aman@aman-Mi-NoteBook-14:~/MyFiles$ rm notes.txt 
aman@aman-Mi-NoteBook-14:~/MyFiles$ ls
Documents

Q4) Create a hard link named "hardlink.txt" for the file "document.txt" within the "Documents" subdirectory. Also, create a symbolic link named "symlink.txt" in the same location.
Ans->  aman@aman-Mi-NoteBook-14:~/MyFiles/Documents$ ls
document.txt
aman@aman-Mi-NoteBook-14:~/MyFiles/Documents$ ln document.txt hardlink.txt
aman@aman-Mi-NoteBook-14:~/MyFiles/Documents$ ls
document.txt  hardlink.txt

aman@aman-Mi-NoteBook-14:~/MyFiles/Documents$ ln -s document.txt symlink.txt
aman@aman-Mi-NoteBook-14:~/MyFiles/Documents$ ls
document.txt  hardlink.txt  symlink.txt

Q5) In the "MyFiles" directory, use a single command to list all files that start with the letter "a" and have a ".txt" extension.
Ans -> aman@aman-Mi-NoteBook-14:~/MyFiles$ tree -P 'a*'
.
└── Documents

1 directory, 0 files
aman@aman-Mi-NoteBook-14:~/MyFiles$ 


Q6) Rename all files in the "Documents" subdirectory of "MyFiles" with a ".bak" extension. Ensure the original file names are preserved.
Ans-> aman@aman-Mi-NoteBook-14:~/MyFiles/Documents$ for f in *.txt; do mv -- "$f" "${f%.js}.bak"; done
aman@aman-Mi-NoteBook-14:~/MyFiles/Documents$ ls
document.txt.bak  hardlink.txt.bak  symlink.txt.bak
aman@aman-Mi-NoteBook-14:~/MyFiles/Documents$ 

Q7) Use a wildcard character to copy all files from the "Documents" subdirectory of "MyFiles" to another directory named "Backup."
Ans -> aman@aman-Mi-NoteBook-14:~/MyFiles$ mv Documents/* Backup/
aman@aman-Mi-NoteBook-14:~/MyFiles$ ls
Backup  Documents
aman@aman-Mi-NoteBook-14:~/MyFiles$ cd Backup/
aman@aman-Mi-NoteBook-14:~/MyFiles/Backup$ ls
document.txt.bak  hardlink.txt.bak  symlink.txt.bak
aman@aman-Mi-NoteBook-14:~/MyFiles/Backup$ 

Q8) Execute the ls command to list files in the current directory. Save the output to a file named "file_list.txt." Then, use a pipe to filter the output through grep to display only files with a ".txt" extension.
Ans-> aman@aman-Mi-NoteBook-14:~/MyFiles/Backup$ ls > file_list.txt
aman@aman-Mi-NoteBook-14:~/MyFiles/Backup$ ls
document.txt.bak  file_list.txt  hardlink.txt.bak  symlink.txt.bak
aman@aman-Mi-NoteBook-14:~/MyFiles/Backup$ grep '.txt' file_list.txt
document.txt.bak
file_list.txt
hardlink.txt.bak
symlink.txt.bak

Q9) Create a new text file named "my_notes.txt" using the touch command. Open the file in the Vim editor, add some text, and save the changes.
Ans-> 
aman@aman-Mi-NoteBook-14:~/MyFiles/Backup$ touch my_notes.txt
aman@aman-Mi-NoteBook-14:~/MyFiles/Backup$ vim my_notes.txt
![Screenshot from 2024-02-06 13-17-04](https://github.com/amancoder17/Linux-Assignment/assets/97497884/de5f11c6-b414-4d56-b478-ae55c186e475)



 Q10) Run the date command and store the output in a variable named "current_date." Display the value of the variable and append it to the "my_notes.txt" file.
Ans -> aman@aman-Mi-NoteBook-14:~/MyFiles/Backup$ now="`date`"
aman@aman-Mi-NoteBook-14:~/MyFiles/Backup$ echo "$now"
Tuesday 06 February 2024 01:51:04 PM IST
aman@aman-Mi-NoteBook-14:~/MyFiles/Backup$ echo "$now" >>my_notes.txt
aman@aman-Mi-NoteBook-14:~/MyFiles/Backup$ ls
document.txt.bak  file_list.txt  hardlink.txt.bak  my_notes.txt  symlink.txt.bak
aman@aman-Mi-NoteBook-14:~/MyFiles/Backup$ vim my_notes.txt 

Q11) Edit the Bash startup script (e.g., .bashrc) to set an environment variable named "CUSTOM_PATH" to a specific directory path. Ensure the variable is available in new shell sessions.
Ans-> aman@aman-Mi-NoteBook-14:~/MyFiles/Backup$ nano /.bashrc
aman@aman-Mi-NoteBook-14:~/MyFiles/Backup$ source ~/.bashrc

Q12) Use the echo command to add a new line of text to the "my_notes.txt" file without overwriting existing content. Verify that the new text is appended.
Ans-> aman@aman-Mi-NoteBook-14:~/MyFiles/Backup$ echo "Hello Interns" >> my_notes.txt
aman@aman-Mi-NoteBook-14:~/MyFiles/Backup$ cat my_notes.txt
i my name is aman
Tuesday 06 February 2024 01:51:04 PM IST
Hello Interns

Q13) List all files in the "/etc" directory, filter the output to include only those containing the word "conf," and save the result to a file named "conf_files.txt."
Ans-> aman@aman-Mi-NoteBook-14:~$ ls /etc | grep "conf" >conf_files.txt
aman@aman-Mi-NoteBook-14:~$ cat conf_files.txt
adduser.conf
apg.conf
appstream.conf
brltty.conf
ca-certificates.conf
ca-certificates.conf.dpkg-old
dconf
debconf.conf
deluser.conf
e2scrub.conf
fprintd.conf
fuse.conf
gai.conf
hdparm.conf
host.conf
insserv.conf.d
kernel-img.conf
kerneloops.conf
ld.so.conf
ld.so.conf.d
libao.conf
libaudit.conf
logrotate.conf
manpath.config
mke2fs.conf
mongod.conf
netconfig
nftables.conf
nsswitch.conf
pam.conf
pnm2ppa.conf
resolv.conf
rsyslog.conf
rygel.conf
sensors3.conf
sudo.conf
sudo_logsrvd.conf
sysctl.conf
ucf.conf
usb_modeswitch.conf
xattr.conf

Q14) Open the "my_notes.txt" file in Vim. Use Vim's search and replace functionality to replace all occurrences of the word "important" with "critical." Save the changes.
Ans)-> aman@aman-Mi-NoteBook-14:~/MyFiles/Backup$ vim my_notes.txt
:%s/important/critical/g

Q15) Create a new user account named "john_doe." Set the user's home directory to "/home/john_doe" and assign the user to the "users" group.
Ans-> aman@aman-Mi-NoteBook-14:~/MyFiles/Backup$ sudo adduser --home /home/john_doe --ingroup users john_doe
[sudo] password for aman: 
Adding user `john_doe' ...
Adding new user `john_doe' (1001) with group `users' ...
Creating home directory `/home/john_doe' ...
Copying files from `/etc/skel' ...
New password: 
BAD PASSWORD: The password is shorter than 8 characters
Retype new password: 
passwd: password updated successfully
Changing the user information for john_doe
Enter the new value, or press ENTER for the default
	Full Name []: John_doe
	Room Number []: 1
	Work Phone []: 1
	Home Phone []: 1
	Other []: 
Is the information correct? [Y/n] y
Q16) Add the user "john_doe" to the sudoers file, allowing them superuser privileges. Confirm that "john_doe" can execute commands with sudo.
Ans-> aman@aman-Mi-NoteBook-14:~/MyFiles/Backup$ sudo visudo
aman@aman-Mi-NoteBook-14:~/MyFiles/Backup$ sudo ls/root
sudo: ls/root: command not found
aman@aman-Mi-NoteBook-14:~/MyFiles/Backup$ sudo ls /root
snap
Q17) Modify  the user account "john_doe" to change the default shell to "/bin/bash"  and set the account's expiration date to one month from today.
aman@aman-Mi-NoteBook-14:~/MyFiles/Backup$ sudo usermod --shell /bin/bash --expiredate $(date -d "+1 month" +%Y-%m-%d) john_doe

Q18) Create a new group named "development_team." Add "john_doe" to this group and verify the group's existence.
Ans-> aman@aman-Mi-NoteBook-14:~/MyFiles/Backup$ sudo groupadd development_team
aman@aman-Mi-NoteBook-14:~/MyFiles/Backup$ sudo usermod -aG development_team john_doe
aman@aman-Mi-NoteBook-14:~/MyFiles/Backup$ getent group development_team
development_team:x:1001:john_doe
aman@aman-Mi-NoteBook-14:~/MyFiles/Backup$ groups john_doe
john_doe : users development_team
aman@aman-Mi-NoteBook-14:~/MyFiles/Backup$ 

Q19) Remove "john_doe" from the "users" group and add them to the "development_team" group. Confirm the changes.
Ans-> aman@aman-Mi-NoteBook-14:~$ sudo usermod -G development_team -a john_doe
aman@aman-Mi-NoteBook-14:~$ sudo deluser john_doe users

Q20) Delete the user account "john_doe" and ensure that their home directory is also removed.
Ans-> aman@aman-Mi-NoteBook-14:~/MyFiles/Backup$ sudo userdel -r john_doe

 Q21) Delete the group "development_team" and ensure that all users previously belonging to the group are appropriately handled.
Ans-> aman@aman-Mi-NoteBook-14:~/MyFiles/Backup$ grep development_team /etc/passwd
aman@aman-Mi-NoteBook-14:~/MyFiles/Backup$ sudo usermod -g users john_doe
aman@aman-Mi-NoteBook-14:~/MyFiles/Backup$ sudo groupdel development_team

Q22) Implement a password policy that requires users to change their passwords every 90 days. Apply this policy to all existing and new user accounts.
Ans-> aman@aman-Mi-NoteBook-14:~/MyFiles/Backup$ sudo chage -M 90 -I 10 -m 7 -W 7 aman
aman@aman-Mi-NoteBook-14:~/MyFiles/Backup$ sudo nano /etc/login.defs


Q23) Manually lock the user account "john_doe." Attempt to log in as "john_doe" to confirm that the account is locked. Then, unlock the account.
Ans-> aman@aman-Mi-NoteBook-14:~/MyFiles/Backup$ sudo passwd -l john_doe
aman@aman-Mi-NoteBook-14:~/MyFiles/Backup$ sudo passwd -u john_doe

Q24) Use the id command to display detailed information about the "john_doe" user, including user ID, group ID, and supplementary groups.
Ans-> aman@aman-Mi-NoteBook-14:~/MyFiles/Backup$ id john_doe
aman@aman-Mi-NoteBook-14:~/MyFiles/Backup$ uid=1001(john_doe) gid=1001(john_doe) groups=1001(john_doe),1002(development_team),1003(users)

Q25) Configure  the password aging for the user "john_doe" to enforce a maximum  password age of 60 days. Confirm that the changes take effect.
Ans-> aman@aman-Mi-NoteBook-14:~/MyFiles/Backup$ sudo chage -M 60 john_doe
aman@aman-Mi-NoteBook-14:~/MyFiles/Backup$ sudo chage -l john_doe






