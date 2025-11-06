# Linux(User & Group)

1. create a user

```jsx
[ec2-user@ip-172-31-4-103 ~]$ sudo useradd mike
[ec2-user@ip-172-31-4-103 ~]$ sudo passwd mike
Changing password for user mike.
New password://test
BAD PASSWORD: The password is shorter than 8 characters
Retype new password://test
passwd: all authentication tokens updated successfully.

```

1. show where user is created

```jsx
[ec2-user@ip-172-31-4-103 ~]$ grep mike /etc/passwd
mike:x:1001:1001::/home/mike:/bin/bash
[ec2-user@ip-172-31-4-103 ~]$ grep mike /etc/passwd
mike:x:1001:1001::/home/mike:/bin/bash

// show all
[ec2-user@ip-172-31-4-103 ~]$ cat /etc/passwd
```

1. switch user

```jsx
[ec2-user@ip-172-31-4-103 ~]$ su mike
Password:
[mike@ip-172-31-4-103 ec2-user]$ ls
ls: cannot open directory '.': Permission denied
[mike@ip-172-31-4-103 ec2-user]$ pwd
/home/ec2-user
[mike@ip-172-31-4-103 ec2-user]$ cd ~
[mike@ip-172-31-4-103 ~]$ ls
[mike@ip-172-31-4-103 ~]$ pwd
/home/mike
[mike@ip-172-31-4-103 ~]$ touch f1.txt
[mike@ip-172-31-4-103 ~]$ ls
f1.txt
[mike@ip-172-31-4-103 ~]$ exit
exit
[ec2-user@ip-172-31-4-103 ~]$ pwd
/home/ec2-user
[ec2-user@ip-172-31-4-103 ~]$ cd ..
[ec2-user@ip-172-31-4-103 home]$ ls
ec2-user  mike  stallin
[ec2-user@ip-172-31-4-103 home]$ cd mike
-bash: cd: mike: Permission denied

```

1. delete the user

```jsx
[ec2-user@ip-172-31-4-103 ~]$ sudo userdel mike
[ec2-user@ip-172-31-4-103 ~]$ cd ..
[ec2-user@ip-172-31-4-103 home]$ ls
ec2-user  mike  stallin
// in avobe case delete the user but not delete the folder
```

1. delete user and folder also

```jsx
[ec2-user@ip-172-31-4-103 ~]$ sudo userdel stallin --remove
[ec2-user@ip-172-31-4-103 ~]$ cd ..
[ec2-user@ip-172-31-4-103 home]$ ls
ec2-user  mike
sudo rm -rf /home/mike
```

1. Change the user password

```jsx
[ec2-user@ip-172-31-4-103 ~]$ sudo useradd alice
[ec2-user@ip-172-31-4-103 ~]$ sudo passwd alice
Changing password for user alice.
New password: //test
BAD PASSWORD: The password is shorter than 8 characters
Retype new password: //test
passwd: all authentication tokens updated successfully.
[ec2-user@ip-172-31-4-103 ~]$ sudo passwd alice
Changing password for user alice.
New password: //testing
BAD PASSWORD: The password is shorter than 8 characters
Retype new password: //testing
passwd: all authentication tokens updated successfully.
```

1. Show all the groups

```jsx
[ec2-user@ip-172-31-4-103 ~]$ cat /etc/group
```

1. For open sudo file

```jsx
[ec2-user@ip-172-31-4-103 ~]$ sudo visudo
```

1. for mike user enable permission all

```jsx
## Allow root to run any commands anywhere
root    ALL=(ALL)       ALL
mike ALL=(ALL:ALL) ALL
// after that save and exit is ctrl + x then ctrl + y then enter 
```

1. After the enable permissions then enable password authentication

```jsx
[ec2-user@ip-172-31-4-103 ~]$ sudo vi /etc/ssh/sshd_config
```

1. After that restart ssh service

```jsx
[ec2-user@ip-172-31-4-103 ~]$ sudo systemctl restart sshd
```

1. now login to user

```jsx
dtanm@Tanmoy MINGW64 /e/Devops/Linux/key_pair
$ ssh mike@13.203.214.65 // after @ ip i getting for ec2 details 
The authenticity of host '13.203.214.65 (13.203.214.65)' can't be established.
ED25519 key fingerprint is SHA256:cWdHCKZiBMNi/F6FD2jUGQrhGmzaTfVzz0V/9qTBVps.
This host key is known by the following other names/addresses:
    ~/.ssh/known_hosts:36: ec2-13-204-46-227.ap-south-1.compute.amazonaws.com
    ~/.ssh/known_hosts:38: ec2-3-108-64-128.ap-south-1.compute.amazonaws.com
    ~/.ssh/known_hosts:39: ec2-3-110-108-90.ap-south-1.compute.amazonaws.com
    ~/.ssh/known_hosts:40: ec2-13-203-214-65.ap-south-1.compute.amazonaws.com
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '13.203.214.65' (ED25519) to the list of known hosts.
mike@13.203.214.65's password:
   ,     #_
   ~\_  ####_        Amazon Linux 2023
  ~~  \_#####\
  ~~     \###|
  ~~       \#/ ___   https://aws.amazon.com/linux/amazon-linux-2023
   ~~       V~' '->
    ~~~         /
      ~~._.   _/
         _/ _/
       _/m/'
Last login: Sat Nov  1 05:57:32 2025
[mike@ip-172-31-4-103 ~]$ pwd
/home/mike
[mike@ip-172-31-4-103 ~]$

```

1. For knowing user in which group, and also when user is created one private group is created for this user

```jsx
[ec2-user@ip-172-31-4-103 ~]$ id mike
uid=1003(mike) gid=1003(mike) groups=1003(mike)
```

1. Create Group

```jsx
sudo groupadd developers
```

1. Add a user from a group

```jsx
sudo usermod -aG team1 alice
```

1. Display Users in a Group

```jsx
sudo lid -g team1
```

1. Remove a User from a Group

```jsx
[mike@ip-172-31-4-103 ~]$ sudo lid -g team1
 mike(uid=1003)
 stallin(uid=1004)
 alex(uid=1005)
[mike@ip-172-31-4-103 ~]$ sudo gpasswd -d alex team1
Removing user alex from group team1
[mike@ip-172-31-4-103 ~]$ sudo lid -g team1
 mike(uid=1003)
 stallin(uid=1004)
```

1. Delete Group

```jsx
[mike@ip-172-31-4-103 ~]$ sudo groupdel team
```

1. Rename Group

```jsx
[mike@ip-172-31-4-103 ~]$ sudo groupmod -n team team1
[mike@ip-172-31-4-103 ~]$ sudo lid -g team1
team1 does not exist
[mike@ip-172-31-4-103 ~]$ sudo lid -g team
 mike(uid=1003)
 stallin(uid=1004)
```

1. Give execute permission to the user

```jsx
[mike@ip-172-31-4-103 ~]$ ls -l
total 0
-rw-r--r--. 1 mike mike 0 Nov  3 05:22 file1.txt
drwxr-xr-x. 2 mike mike 6 Nov  3 05:26 folder
[mike@ip-172-31-4-103 ~]$ chmod u+x file1.txt
[mike@ip-172-31-4-103 ~]$ ls -l
total 0
-rwxr--r--. 1 mike mike 0 Nov  3 05:22 file1.txt
drwxr-xr-x. 2 mike mike 6 Nov  3 05:26 folder
```

1. Give execute permission to the group

```jsx
[mike@ip-172-31-4-103 ~]$ chmod g+x file1.txt
[mike@ip-172-31-4-103 ~]$ ls -l
total 0
-rwxr-xr--. 1 mike mike 0 Nov  3 05:22 file1.txt
drwxr-xr-x. 2 mike mike 6 Nov  3 05:26 folder
[mike@ip-172-31-4-103 ~]$ chmod g+w file1.txt
[mike@ip-172-31-4-103 ~]$ ls -l
total 0
-rwxrwxr--. 1 mike mike 0 Nov  3 05:22 file1.txt
drwxr-xr-x. 2 mike mike 6 Nov  3 05:26 folder
```

1. Remove the permission from group

```jsx
[mike@ip-172-31-4-103 ~]$ ls -l
total 0
-rwxrwxr--. 1 mike mike 0 Nov  3 05:22 file1.txt
drwxr-xr-x. 2 mike mike 6 Nov  3 05:26 folder
[mike@ip-172-31-4-103 ~]$ chmod g-w file1.txt
[mike@ip-172-31-4-103 ~]$ ls -l
total 0
-rwxr-xr--. 1 mike mike 0 Nov  3 05:22 file1.txt
drwxr-xr-x. 2 mike mike 6 Nov  3 05:26 folder
```

1. Give permission to others

```jsx
[mike@ip-172-31-4-103 ~]$ ls -l
total 0
-rwxr-xr--. 1 mike mike 0 Nov  3 05:22 file1.txt
drwxr-xr-x. 2 mike mike 6 Nov  3 05:26 folder
[mike@ip-172-31-4-103 ~]$ chmod o+w file1.txt
[mike@ip-172-31-4-103 ~]$ ls -l
total 0
-rwxr-xrw-. 1 mike mike 0 Nov  3 05:22 file1.txt
drwxr-xr-x. 2 mike mike 6 Nov  3 05:26 folder
```

1. Give permissions in numeric format

```jsx
[mike@ip-172-31-4-103 ~]$ ls -l
total 0
-rwxr-xrw-. 1 mike mike 0 Nov  3 05:22 file1.txt
drwxr-xr-x. 2 mike mike 6 Nov  3 05:26 folder
[mike@ip-172-31-4-103 ~]$ chmod 111 file1.txt
[mike@ip-172-31-4-103 ~]$ ls -l
total 0
---x--x--x. 1 mike mike 0 Nov  3 05:22 file1.txt
drwxr-xr-x. 2 mike mike 6 Nov  3 05:26 folder
[mike@ip-172-31-4-103 ~]$ chmod 222 file1.txt
[mike@ip-172-31-4-103 ~]$ ls -l
total 0
--w--w--w-. 1 mike mike 0 Nov  3 05:22 file1.txt
drwxr-xr-x. 2 mike mike 6 Nov  3 05:26 folder
[mike@ip-172-31-4-103 ~]$ chmod 444 file1.txt
[mike@ip-172-31-4-103 ~]$ ls -l
total 0
-r--r--r--. 1 mike mike 0 Nov  3 05:22 file1.txt
drwxr-xr-x. 2 mike mike 6 Nov  3 05:26 folder
[mike@ip-172-31-4-103 ~]$ chmod 777 file1.txt
[mike@ip-172-31-4-103 ~]$ ls -l
total 0
-rwxrwxrwx. 1 mike mike 0 Nov  3 05:22 file1.txt
drwxr-xr-x. 2 mike mike 6 Nov  3 05:26 folder
[mike@ip-172-31-4-103 ~]$ chmod 741 file1.txt
[mike@ip-172-31-4-103 ~]$ ls -l
total 0
-rwxr----x. 1 mike mike 0 Nov  3 05:22 file1.txt
drwxr-xr-x. 2 mike mike 6 Nov  3 05:26 folder
[mike@ip-172-31-4-103 ~]$ chmod 762 file1.txt
[mike@ip-172-31-4-103 ~]$ ls -l
total 0
-rwxrw--w-. 1 mike mike 0 Nov  3 05:22 file1.txt
drwxr-xr-x. 2 mike mike 6 Nov  3 05:26 folder
[mike@ip-172-31-4-103 ~]$ chmod 000 file1.txt
[mike@ip-172-31-4-103 ~]$ ls -l
total 0
----------. 1 mike mike 0 Nov  3 05:22 file1.txt
drwxr-xr-x. 2 mike mike 6 Nov  3 05:26 folder
```

### “chown” - command

1. how change owner

```jsx
[ec2-user@ip-172-31-4-103 ~]$ touch psa.txt
[ec2-user@ip-172-31-4-103 ~]$ ls -l
total 8
drwxr-xr-x. 3 ec2-user ec2-user 99 Oct 30 10:46 a
-rw-r--r--. 1 ec2-user ec2-user 90 Nov  1 02:17 f1.txt
-rw-r--r--. 1 ec2-user ec2-user 30 Oct 31 06:37 f3.txt
-rw-r--r--. 1 ec2-user ec2-user  0 Oct 31 06:56 f5.txt
-rw-r--r--. 1 ec2-user ec2-user  0 Nov  3 06:40 psa.txt
[ec2-user@ip-172-31-4-103 ~]$ sudo chown mike psa.txt
[ec2-user@ip-172-31-4-103 ~]$ ls -l
total 8
drwxr-xr-x. 3 ec2-user ec2-user 99 Oct 30 10:46 a
-rw-r--r--. 1 ec2-user ec2-user 90 Nov  1 02:17 f1.txt
-rw-r--r--. 1 ec2-user ec2-user 30 Oct 31 06:37 f3.txt
-rw-r--r--. 1 ec2-user ec2-user  0 Oct 31 06:56 f5.txt
-rw-r--r--. 1 mike     ec2-user  0 Nov  3 06:40 psa.txt
```

1. Change the group

```jsx
[ec2-user@ip-172-31-4-103 ~]$ ls -l
total 8
drwxr-xr-x. 3 ec2-user ec2-user 99 Oct 30 10:46 a
-rw-r--r--. 1 ec2-user ec2-user 90 Nov  1 02:17 f1.txt
-rw-r--r--. 1 ec2-user ec2-user 30 Oct 31 06:37 f3.txt
-rw-r--r--. 1 ec2-user ec2-user  0 Oct 31 06:56 f5.txt
-rw-r--r--. 1 mike     ec2-user  0 Nov  3 06:40 psa.txt
[ec2-user@ip-172-31-4-103 ~]$ sudo chown :mike psa.txt
[ec2-user@ip-172-31-4-103 ~]$ ls-l
-bash: ls-l: command not found
[ec2-user@ip-172-31-4-103 ~]$ ls -l
total 8
drwxr-xr-x. 3 ec2-user ec2-user 99 Oct 30 10:46 a
-rw-r--r--. 1 ec2-user ec2-user 90 Nov  1 02:17 f1.txt
-rw-r--r--. 1 ec2-user ec2-user 30 Oct 31 06:37 f3.txt
-rw-r--r--. 1 ec2-user ec2-user  0 Oct 31 06:56 f5.txt
-rw-r--r--. 1 mike     mike      0 Nov  3 06:40 psa.txt
```

1. How to change owner and group together

```jsx
[ec2-user@ip-172-31-4-103 ~]$ ls -l
total 8
drwxr-xr-x. 3 ec2-user ec2-user 99 Oct 30 10:46 a
-rw-r--r--. 1 ec2-user ec2-user 90 Nov  1 02:17 f1.txt
-rw-r--r--. 1 ec2-user ec2-user 30 Oct 31 06:37 f3.txt
-rw-r--r--. 1 ec2-user ec2-user  0 Oct 31 06:56 f5.txt
-rw-r--r--. 1 mike     mike      0 Nov  3 06:40 psa.txt
[ec2-user@ip-172-31-4-103 ~]$ sudo chown stallin:stallin psa.txt
[ec2-user@ip-172-31-4-103 ~]$ ls -l
total 8
drwxr-xr-x. 3 ec2-user ec2-user 99 Oct 30 10:46 a
-rw-r--r--. 1 ec2-user ec2-user 90 Nov  1 02:17 f1.txt
-rw-r--r--. 1 ec2-user ec2-user 30 Oct 31 06:37 f3.txt
-rw-r--r--. 1 ec2-user ec2-user  0 Oct 31 06:56 f5.txt
-rw-r--r--. 1 stallin  stallin   0 Nov  3 06:40 psa.txt
```

### Finding file in linux

1. how to find file in linux

```jsx
[ec2-user@ip-172-31-4-103 ~]$ sudo find /home -name f1.txt
/home/ec2-user/a/f1.txt
/home/ec2-user/f1.txt
```

1. Search for empty files

```jsx
[ec2-user@ip-172-31-4-103 ~]$ sudo find /home -type f -empty
/home/ec2-user/a/a/f0.txt
/home/ec2-user/a/f4.txt
/home/ec2-user/a/f5.txt
/home/ec2-user/a/f6.txt
/home/ec2-user/f5.txt
/home/ec2-user/psa.txt
/home/mike/file1.txt

```

1. Search for empty directories

```jsx
[ec2-user@ip-172-31-4-103 ~]$ sudo find /home -type d -empty
/home/mike/folder
```

1. find files modified  2 days ago

```jsx
[ec2-user@ip-172-31-4-103 ~]$ sudo find /home -mtime 2 -print
/home/ec2-user/f5.txt
/home/ec2-user/f1.txt
/home/ec2-user/.viminfo
/home/alice
```

1. Delete the files which i created 1 day back

```jsx
sudo find /home -mtime 1 -delete
```