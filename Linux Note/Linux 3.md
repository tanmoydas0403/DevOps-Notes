# Linux

## Zip and Unzip

1. Zip and unzip the files

```jsx
[ec2-user@ip-172-31-8-156 ~]$ touch t1.txt t2.txt t3.txt t4.txt
[ec2-user@ip-172-31-8-156 ~]$ ls -l
total 0
-rw-r--r--. 1 ec2-user ec2-user 0 Nov  3 13:24 t1.txt
-rw-r--r--. 1 ec2-user ec2-user 0 Nov  3 13:24 t2.txt
-rw-r--r--. 1 ec2-user ec2-user 0 Nov  3 13:24 t3.txt
-rw-r--r--. 1 ec2-user ec2-user 0 Nov  3 13:24 t4.txt
[ec2-user@ip-172-31-8-156 ~]$ zip example *.txt
  adding: t1.txt (stored 0%)
  adding: t2.txt (stored 0%)
  adding: t3.txt (stored 0%)
  adding: t4.txt (stored 0%)
[ec2-user@ip-172-31-8-156 ~]$ ls -l
total 4
-rw-r--r--. 1 ec2-user ec2-user 582 Nov  3 13:25 example.zip
-rw-r--r--. 1 ec2-user ec2-user   0 Nov  3 13:24 t1.txt
-rw-r--r--. 1 ec2-user ec2-user   0 Nov  3 13:24 t2.txt
-rw-r--r--. 1 ec2-user ec2-user   0 Nov  3 13:24 t3.txt
-rw-r--r--. 1 ec2-user ec2-user   0 Nov  3 13:24 t4.txt
[ec2-user@ip-172-31-8-156 ~]$ rm *.txt
[ec2-user@ip-172-31-8-156 ~]$ ls -l
total 4
-rw-r--r--. 1 ec2-user ec2-user 582 Nov  3 13:25 example.zip
[ec2-user@ip-172-31-8-156 ~]$ unzip example.zip
Archive:  example.zip
 extracting: t1.txt
 extracting: t2.txt
 extracting: t3.txt
 extracting: t4.txt
[ec2-user@ip-172-31-8-156 ~]$ ls -l
total 4
-rw-r--r--. 1 ec2-user ec2-user 582 Nov  3 13:25 example.zip
-rw-r--r--. 1 ec2-user ec2-user   0 Nov  3 13:24 t1.txt
-rw-r--r--. 1 ec2-user ec2-user   0 Nov  3 13:24 t2.txt
-rw-r--r--. 1 ec2-user ec2-user   0 Nov  3 13:24 t3.txt
-rw-r--r--. 1 ec2-user ec2-user   0 Nov  3 13:24 t4.txt

```

## Networking Commands in Linux

1. ping

```jsx
[ec2-user@ip-172-31-8-156 ~]$ ping www.facebook.com
PING star-mini.c10r.facebook.com (57.144.152.1) 56(84) bytes of data.
64 bytes from edge-star-mini-shv-01-sin2.facebook.com (57.144.152.1): icmp_seq=1 ttl=52 time=61.8 ms
64 bytes from edge-star-mini-shv-01-sin2.facebook.com (57.144.152.1): icmp_seq=2 ttl=52 time=61.8 ms
64 bytes from edge-star-mini-shv-01-sin2.facebook.com (57.144.152.1): icmp_seq=3 ttl=52 time=61.9 ms
64 bytes from edge-star-mini-shv-01-sin2.facebook.com (57.144.152.1): icmp_seq=4 ttl=52 time=62.3 ms
64 bytes from edge-star-mini-shv-01-sin2.facebook.com (57.144.152.1): icmp_seq=5 ttl=52 time=62.4 ms
64 bytes from edge-star-mini-shv-01-sin2.facebook.com (57.144.152.1): icmp_seq=6 ttl=52 time=61.8 ms
```

1. Want 4 time ping

```jsx
[ec2-user@ip-172-31-8-156 ~]$ ping -c 4 www.facebook.com
PING star-mini.c10r.facebook.com (163.70.143.35) 56(84) bytes of data.
64 bytes from edge-star-mini-shv-01-bom2.facebook.com (163.70.143.35): icmp_seq=1 ttl=52 time=55.7 ms
64 bytes from edge-star-mini-shv-01-bom2.facebook.com (163.70.143.35): icmp_seq=2 ttl=52 time=55.7 ms
64 bytes from edge-star-mini-shv-01-bom2.facebook.com (163.70.143.35): icmp_seq=3 ttl=52 time=55.7 ms
64 bytes from edge-star-mini-shv-01-bom2.facebook.com (163.70.143.35): icmp_seq=4 ttl=52 time=55.8 ms

--- star-mini.c10r.facebook.com ping statistics ---
4 packets transmitted, 4 received, 0% packet loss, time 3004ms
rtt min/avg/max/mdev = 55.727/55.750/55.805/0.031 ms
[ec2-user@ip-172-31-8-156 ~]$ ping -c 4 www.facebook.com
PING star-mini.c10r.facebook.com (163.70.143.35) 56(84) bytes of data.
64 bytes from edge-star-mini-shv-01-bom2.facebook.com (163.70.143.35): icmp_seq=1 ttl=52 time=55.7 ms
64 bytes from edge-star-mini-shv-01-bom2.facebook.com (163.70.143.35): icmp_seq=2 ttl=52 time=55.7 ms
64 bytes from edge-star-mini-shv-01-bom2.facebook.com (163.70.143.35): icmp_seq=3 ttl=52 time=55.7 ms
64 bytes from edge-star-mini-shv-01-bom2.facebook.com (163.70.143.35): icmp_seq=4 ttl=52 time=55.8 ms

--- star-mini.c10r.facebook.com ping statistics ---
4 packets transmitted, 4 received, 0% packet loss, time 3004ms
rtt min/avg/max/mdev = 55.727/55.750/55.805/0.031 ms

```

1. Used to download files from the internet

```jsx
wget <url> //here url i give file url download link
```

1. Used to send HTTP requests to a server and fetch responses

```jsx
[ec2-user@ip-172-31-8-156 ~]$ curl https://fake-json-api.mock.beeceptor.com/users
[
  {
    "id": 1,
    "name": "Sadye Block",
    "company": "Terry, Wisozk and Wiegand",
    "username": "Marietta.Hoppe44",
    "email": "Benny.Ziemann30@gmail.com",
    "address": "31802 Margarette Square",
    "zip": "18339-3683",
    "state": "Utah",
    "country": "Democratic Republic of the Congo",
    "phone": "1-352-205-6857 x95286",
    "photo": "https://json-server.dev/ai-profiles/47.png"
  },
  {
    "id": 2,
    "name": "Evie Faker Attribute Error: person.astName is not supported",
    "company": "Steuber - Labadie",
    "username": "Erich70",
    "email": "Antonette.Veum-Dare@yahoo.com",
    "address": "568 Lon Wells",
    "zip": "99460-9893",
    "state": "Indiana",
    "country": "Chile",
    "phone": "(271) 956-5334 x99880",
    "photo": "https://json-server.dev/ai-profiles/3.png"
  }
```

## Package Managers in Linux

A package in Linux refers to a software application, tool, or utility. Package managers are tools used to install, update, and manage these software packages on Linux systems.

examples of packages: git, maven, java, python

Package Managers for Various Linux Distributions:

1. Amazon Linux / Red Hat Linux / CentOS:  yum
2. Ubuntu / Debian :  apt

1. install git

```jsx
[ec2-user@ip-172-31-8-156 ~]$ git --version
-bash: git: command not found
[ec2-user@ip-172-31-8-156 ~]$ sudo yum install git
//installing
[ec2-user@ip-172-31-8-156 ~]$ git --version
git version 2.50.1
[ec2-user@ip-172-31-8-156 ~]$ whereis git
git: /usr/bin/git /usr/share/man/man1/git.1.gz
```

1. uninstall git

```jsx
[ec2-user@ip-172-31-8-156 ~]$ git --version
git version 2.50.1
[ec2-user@ip-172-31-8-156 ~]$ sudo yum remove git
//uninstall git
[ec2-user@ip-172-31-8-156 ~]$ git --version
-bash: /usr/bin/git: No such file or directory
```

1. install java

```jsx
[ec2-user@ip-172-31-8-156 ~]$ java --version
-bash: java: command not found
[ec2-user@ip-172-31-8-156 ~]$ sudo yum install java -y
//installing java
[ec2-user@ip-172-31-8-156 ~]$ java --version
openjdk 25.0.1 2025-10-21 LTS
OpenJDK Runtime Environment Corretto-25.0.1.8.1 (build 25.0.1+8-LTS)
OpenJDK 64-Bit Server VM Corretto-25.0.1.8.1 (build 25.0.1+8-LTS, mixed mode, sharing)
```

1. update the version

```jsx
[ec2-user@ip-172-31-8-156 ~]$ sudo yum update java
Last metadata expiration check: 0:07:55 ago on Mon Nov  3 13:53:22 2025.
Dependencies resolved.
Nothing to do.
Complete!
```

1. uninstall java

```jsx
[ec2-user@ip-172-31-8-156 ~]$ sudo yum remove java
```

## HTTPD Webserver

1. Install the HTTPD Webserver

```jsx
sudo yum install httpd -y
```

1. Check the Status of the webserver

```jsx
sudo service httpd status
```

1. Start the HTTPD Webserver

```jsx
sudo service httpd start
```

1. httpd folder and change content

```jsx
[ec2-user@ip-172-31-8-156 ~]$ cd /var/www/html
[ec2-user@ip-172-31-8-156 html]$ sudo vi index.html
```

## systemctl commands

1. Stop a Service

```jsx
sudo systemctl stop httpd // here httpd service stop
```

1. Restart the services

```jsx
sudo systemctl restart httpd
```

1. Reload the service

```jsx
sudo systemctl reload httpd
```

1. show ram memory

```jsx
top
```

## Same inode number

1. Create Same inode number and this is we backup data using hard-link

```jsx
[ec2-user@ip-172-31-8-156 ~]$ ls
[ec2-user@ip-172-31-8-156 ~]$ cat >> A.txt
Hello World
[ec2-user@ip-172-31-8-156 ~]$ cat A.txt
Hello World
[ec2-user@ip-172-31-8-156 ~]$ ls -li
total 4
8918660 -rw-r--r--. 1 ec2-user ec2-user 12 Nov  4 04:33 A.txt
[ec2-user@ip-172-31-8-156 ~]$ ln A.txt B.txt
[ec2-user@ip-172-31-8-156 ~]$ ls -li
total 8
8918660 -rw-r--r--. 2 ec2-user ec2-user 12 Nov  4 04:33 A.txt
8918660 -rw-r--r--. 2 ec2-user ec2-user 12 Nov  4 04:33 B.txt
[ec2-user@ip-172-31-8-156 ~]$ cat B.txt
Hello World
[ec2-user@ip-172-31-8-156 ~]$ rm A.txt
[ec2-user@ip-172-31-8-156 ~]$ ls -l
total 4
-rw-r--r--. 1 ec2-user ec2-user 12 Nov  4 04:33 B.txt
[ec2-user@ip-172-31-8-156 ~]$ cat B.txt
Hello World
```

1. Symbolic link

```jsx
[ec2-user@ip-172-31-8-156 ~]$ mkdir f1
[ec2-user@ip-172-31-8-156 ~]$ cd f1
[ec2-user@ip-172-31-8-156 f1]$ pwd
/home/ec2-user/f1
[ec2-user@ip-172-31-8-156 f1]$ cat >> A.txt
Hello World
[ec2-user@ip-172-31-8-156 f1]$ cd ~
[ec2-user@ip-172-31-8-156 ~]$ ln -s /home/ec2-user/f1/A.txt B.txt
[ec2-user@ip-172-31-8-156 ~]$ cat B.txt
Hello World
[ec2-user@ip-172-31-8-156 ~]$ ls -li
total 0
8918709 lrwxrwxrwx. 1 ec2-user ec2-user 23 Nov  4 04:43 B.txt -> /home/ec2-user/f1/A.txt
8918660 drwxr-xr-x. 2 ec2-user ec2-user 19 Nov  4 04:41 f1
[ec2-user@ip-172-31-8-156 ~]$ cd /home/ec2-user/f1
[ec2-user@ip-172-31-8-156 f1]$ ls -li
total 4
8918707 -rw-r--r--. 1 ec2-user ec2-user 12 Nov  4 04:41 A.txt
[ec2-user@ip-172-31-8-156 f1]$ rm A.txt
[ec2-user@ip-172-31-8-156 f1]$ cd ~
[ec2-user@ip-172-31-8-156 ~]$ cat B.txt
cat: B.txt: No such file or directory

```

## Task Manager in Linux

1. task manager

```jsx
ps aux
```

1. Kill the process

```jsx
[ec2-user@ip-172-31-8-156 ~]$ sleep 1000 &
[1] 3606
[ec2-user@ip-172-31-8-156 ~]$ ps aux | grep sleep
ec2-user    3606  0.0  0.1 221372  1012 pts/0    S    04:49   0:00 sleep 1000
ec2-user    3610  0.0  0.1 221816  1044 pts/0    R+   04:50   0:00 grep --color=auto sleep
[ec2-user@ip-172-31-8-156 ~]$ kill 3606
[ec2-user@ip-172-31-8-156 ~]$ ps aux | grep sleep
ec2-user    3612  0.0  0.2 222328  2060 pts/0    S+   04:51   0:00 grep --color=auto sleep
[1]+  Terminated              sleep 1000
```

1. Forcefully kill the process

```jsx
[ec2-user@ip-172-31-8-156 ~]$ sleep 1000 &
[1] 3662
[ec2-user@ip-172-31-8-156 ~]$ ps aux | grep sleep
ec2-user    3662  0.0  0.1 221372  1008 pts/0    S    04:52   0:00 sleep 1000
ec2-user    3664  0.0  0.2 222328  2060 pts/0    S+   04:52   0:00 grep --color=auto sleep
[ec2-user@ip-172-31-8-156 ~]$ kill -9 3662 //this is forcefully kill
[1]+  Killed                  sleep 1000
[ec2-user@ip-172-31-8-156 ~]$ ps aux | grep sleep
ec2-user    3667  0.0  0.2 222328  2080 pts/0    S+   04:52   0:00 grep --color=auto sleep

```

1. sleep the process in background

```jsx
sleep 1000 & //here & use for background process
```

1. Memory utilization show

```jsx
[ec2-user@ip-172-31-8-156 ~]$ free -m
               total        used        free      shared  buff/cache   available
Mem:             949         130         604           0         215         681
Swap:              0           0           0
[ec2-user@ip-172-31-8-156 ~]$

```

## Changing Hostname

1. change the hostname temporarily

```jsx
[ec2-user@ip-172-31-8-156 ~]$ sudo hostname dev-env-1
[ec2-user@ip-172-31-8-156 ~]$ exit
logout
Connection to ec2-13-204-67-178.ap-south-1.compute.amazonaws.com closed.

dtanm@Tanmoy MINGW64 /e/Devops/Linux/key_pair
$ ssh -i "keys_details.pem" ec2-user@ec2-13-204-67-178.ap-south-1.compute.amazonaws.com
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
Last login: Wed Nov  5 06:07:39 2025 from 223.223.155.39
[ec2-user@dev-env-1 ~]$
//But this is temporaliy when i reboot the server hostname change again
[ec2-user@dev-env-1 ~]$ sudo reboot

Broadcast message from root@ip-172-31-8-156.ap-south-1.compute.internal on pts/1 (Wed 2025-11-05 06:11:25 UTC):

The system will reboot now!

[ec2-user@dev-env-1 ~]$ Connection to ec2-13-204-67-178.ap-south-1.compute.amazonaws.com closed by remote host.
Connection to ec2-13-204-67-178.ap-south-1.compute.amazonaws.com closed.

dtanm@Tanmoy MINGW64 /e/Devops/Linux/key_pair
$ ssh -i "keys_details.pem" ec2-user@ec2-13-204-67-178.ap-south-1.compute.amazonaws.com
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
Last login: Wed Nov  5 06:10:42 2025 from 223.223.155.39
[ec2-user@ip-172-31-8-156 ~]$

```

1. Change hostname permanently

```jsx
[ec2-user@ip-172-31-8-156 ~]$ sudo vi /etc/hostname
//After that insert mode and change hostname dev-env-1
[ec2-user@ip-172-31-8-156 ~]$ sudo reboot

Broadcast message from root@ip-172-31-8-156.ap-south-1.compute.internal on pts/1 (Wed 2025-11-05 06:18:56 UTC):

The system will reboot now!

[ec2-user@ip-172-31-8-156 ~]$ Connection to ec2-13-204-67-178.ap-south-1.compute.amazonaws.com closed by remote host.
Connection to ec2-13-204-67-178.ap-south-1.compute.amazonaws.com closed.

dtanm@Tanmoy MINGW64 /e/Devops/Linux/key_pair
$ ssh -i "keys_details.pem" ec2-user@ec2-13-204-67-178.ap-south-1.compute.amazonaws.com
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
Last login: Wed Nov  5 06:11:48 2025 from 223.223.155.39
[ec2-user@dev-env-1 ~]$

```