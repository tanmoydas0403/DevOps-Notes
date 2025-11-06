# Linux (Basic)

1. How to know Present Working Directory

```jsx
[ec2-user@ip-172-31-4-103 ~]$ pwd
/home/ec2-user
```

1. Creating directory

```jsx
[ec2-user@ip-172-31-4-103 ~]$ mkdir c
```

1. Show the creating folder

```jsx
[ec2-user@ip-172-31-4-103 ~]$ ls
c

```

1. Show the creating folder by detailed structure and also alphabetically sorted and cannot worries about when folder created or not

```jsx
[ec2-user@ip-172-31-4-103 ~]$ ls -l
total 0
drwxr-xr-x. 2 ec2-user ec2-user 6 Oct 30 05:45 a
drwxr-xr-x. 2 ec2-user ec2-user 6 Oct 30 05:42 c

```

1. Show the creating folder by detailed structure and also alphabetically desc sorted

```jsx
[ec2-user@ip-172-31-4-103 ~]$ ls -r
c  a
[ec2-user@ip-172-31-4-103 ~]$ ls -lr
total 0
drwxr-xr-x. 2 ec2-user ec2-user 6 Oct 30 05:42 c
drwxr-xr-x. 2 ec2-user ec2-user 6 Oct 30 05:45 a

```

1. Delete empty folder

```jsx
[ec2-user@ip-172-31-4-103 ~]$ mkdir b
[ec2-user@ip-172-31-4-103 ~]$ ls -l
total 0
drwxr-xr-x. 2 ec2-user ec2-user 6 Oct 30 05:45 a
drwxr-xr-x. 2 ec2-user ec2-user 6 Oct 30 05:54 b
drwxr-xr-x. 2 ec2-user ec2-user 6 Oct 30 05:42 c
[ec2-user@ip-172-31-4-103 ~]$ rmdir b
[ec2-user@ip-172-31-4-103 ~]$ ls -l
total 0
drwxr-xr-x. 2 ec2-user ec2-user 6 Oct 30 05:45 a
drwxr-xr-x. 2 ec2-user ec2-user 6 Oct 30 05:42 c

```

1. Show hidden folders

```jsx
[ec2-user@ip-172-31-4-103 ~]$ ls -la
total 12
drwx------. 5 ec2-user ec2-user  92 Oct 30 05:55 .
drwxr-xr-x. 3 root     root      22 Oct 30 05:33 ..
-rw-r--r--. 1 ec2-user ec2-user  18 Jan 28  2023 .bash_logout
-rw-r--r--. 1 ec2-user ec2-user 141 Jan 28  2023 .bash_profile
-rw-r--r--. 1 ec2-user ec2-user 492 Jan 28  2023 .bashrc
drwx------. 2 ec2-user ec2-user  29 Oct 30 05:33 .ssh
drwxr-xr-x. 2 ec2-user ec2-user   6 Oct 30 05:45 a
drwxr-xr-x. 2 ec2-user ec2-user   6 Oct 30 05:42 c

```

1. Go one folder to another folder

```jsx
[ec2-user@ip-172-31-4-103 ~]$ ls
a  c
[ec2-user@ip-172-31-4-103 ~]$ pwd
/home/ec2-user
[ec2-user@ip-172-31-4-103 ~]$ cd /home/ec2-user/a
[ec2-user@ip-172-31-4-103 a]$ pwd
/home/ec2-user/a
```

1. How to go back to the root folder 

```jsx
[ec2-user@ip-172-31-4-103 ~]$ ls
a  c
[ec2-user@ip-172-31-4-103 ~]$ pwd
/home/ec2-user
[ec2-user@ip-172-31-4-103 ~]$ cd /home/ec2-user/a
[ec2-user@ip-172-31-4-103 a]$ pwd
/home/ec2-user/a
[ec2-user@ip-172-31-4-103 a]$ cd ~
[ec2-user@ip-172-31-4-103 ~]$ pwd
/home/ec2-user
```

1. One Folder back

```jsx
[ec2-user@ip-172-31-4-103 ~]$ pwd
/home/ec2-user
[ec2-user@ip-172-31-4-103 ~]$ cd /home/ec2-user/a
[ec2-user@ip-172-31-4-103 a]$ pwd
/home/ec2-user/a
[ec2-user@ip-172-31-4-103 a]$ cd ..
[ec2-user@ip-172-31-4-103 ~]$ pwd
/home/ec2-user
```

1. How to create a file and show all created file

```jsx
[ec2-user@ip-172-31-4-103 a]$ pwd
/home/ec2-user/a
[ec2-user@ip-172-31-4-103 a]$ touch f1.txt
[ec2-user@ip-172-31-4-103 a]$ touch f2.txt
[ec2-user@ip-172-31-4-103 a]$ touch f3.txt
[ec2-user@ip-172-31-4-103 a]$ ls
f1.txt  f2.txt  f3.txt
[ec2-user@ip-172-31-4-103 a]$ ls -l
total 0
-rw-r--r--. 1 ec2-user ec2-user 0 Oct 30 06:06 f1.txt
-rw-r--r--. 1 ec2-user ec2-user 0 Oct 30 06:06 f2.txt
-rw-r--r--. 1 ec2-user ec2-user 0 Oct 30 06:06 f3.txt
```

1. How to delete a folder when some content in this folder

```jsx
[ec2-user@ip-172-31-4-103 ~]$ rmdir a
rmdir: failed to remove 'a': Directory not empty
[ec2-user@ip-172-31-4-103 ~]$ rm -rf a
[ec2-user@ip-172-31-4-103 ~]$ ls
c
```

1. Rename the file name

```jsx
[ec2-user@ip-172-31-4-103 a]$ mv f4.txt f0.txt
[ec2-user@ip-172-31-4-103 a]$ ls
f0.txt  f1.txt  f2.txt  f3.txt
```

1. Move a file present location to different location

```jsx
[ec2-user@ip-172-31-4-103 a]$ pwd
/home/ec2-user/a
[ec2-user@ip-172-31-4-103 a]$ ls
a  f0.txt  f1.txt  f2.txt  f3.txt
[ec2-user@ip-172-31-4-103 a]$ mv f0.txt /home/ec2-user/a/a
[ec2-user@ip-172-31-4-103 a]$ ls
a  f1.txt  f2.txt  f3.txt
[ec2-user@ip-172-31-4-103 a]$ cd /home/ec2-user/a/a
[ec2-user@ip-172-31-4-103 a]$ pwd
/home/ec2-user/a/a
[ec2-user@ip-172-31-4-103 a]$ ls
f0.txt
```

1. Create a file , read the file and write in the file with “cat” command

```jsx
[ec2-user@ip-172-31-4-103 a]$ ls
a  f1.txt  f2.txt  f3.txt
[ec2-user@ip-172-31-4-103 a]$ cat > f4.txt
^C
[ec2-user@ip-172-31-4-103 a]$ ls
a  f1.txt  f2.txt  f3.txt  f4.txt
[ec2-user@ip-172-31-4-103 a]$ ls
a  f1.txt  f2.txt  f3.txt
[ec2-user@ip-172-31-4-103 a]$ cat > f4.txt
^C
[ec2-user@ip-172-31-4-103 a]$ ls
a  f1.txt  f2.txt  f3.txt  f4.txt
[ec2-user@ip-172-31-4-103 a]$ cat >> f1.txt
Hello
World
he
bye
see
Hello
go
^C
[ec2-user@ip-172-31-4-103 a]$ cat f1.txt
Hello
World
he
bye
see
Hello
go
```

1. Read the file with line numbers

```jsx
[ec2-user@ip-172-31-4-103 a]$ cat -n f1.txt
     1  Hello
     2  World
     3  he
     4  bye
     5  see
     6  Hello
     7  go
```

1. Touch command cannot remove or delete already created file content only change the creation time of the file

```jsx
[ec2-user@ip-172-31-4-103 a]$ cat >> f6.txt
Hello
World
^C
[ec2-user@ip-172-31-4-103 a]$ ls -l
total 8
drwxr-xr-x. 2 ec2-user ec2-user 20 Oct 30 10:35 a
-rw-r--r--. 1 ec2-user ec2-user 32 Oct 30 10:42 f1.txt
-rw-r--r--. 1 ec2-user ec2-user  0 Oct 30 10:30 f2.txt
-rw-r--r--. 1 ec2-user ec2-user  0 Oct 30 10:30 f3.txt
-rw-r--r--. 1 ec2-user ec2-user  0 Oct 30 10:40 f4.txt
-rw-r--r--. 1 ec2-user ec2-user  0 Oct 30 10:46 f5.txt
-rw-r--r--. 1 ec2-user ec2-user 12 Oct 30 10:46 f6.txt
[ec2-user@ip-172-31-4-103 a]$ touch f6.txt
[ec2-user@ip-172-31-4-103 a]$ ls -l
total 8
drwxr-xr-x. 2 ec2-user ec2-user 20 Oct 30 10:35 a
-rw-r--r--. 1 ec2-user ec2-user 32 Oct 30 10:42 f1.txt
-rw-r--r--. 1 ec2-user ec2-user  0 Oct 30 10:30 f2.txt
-rw-r--r--. 1 ec2-user ec2-user  0 Oct 30 10:30 f3.txt
-rw-r--r--. 1 ec2-user ec2-user  0 Oct 30 10:40 f4.txt
-rw-r--r--. 1 ec2-user ec2-user  0 Oct 30 10:46 f5.txt
-rw-r--r--. 1 ec2-user ec2-user 12 Oct 30 10:48 f6.txt
[ec2-user@ip-172-31-4-103 a]$ touch f6.txt
[ec2-user@ip-172-31-4-103 a]$ cat f6.txt
Hello
World
```

1. cat command overright the file existing or earlier content

```jsx
[ec2-user@ip-172-31-4-103 a]$ ls
a  f1.txt  f2.txt  f3.txt  f4.txt  f5.txt  f6.txt
[ec2-user@ip-172-31-4-103 a]$ cat f6.txt
Hello
World
[ec2-user@ip-172-31-4-103 a]$ cat > f6.txt
^C
[ec2-user@ip-172-31-4-103 a]$ cat f6.txt
[ec2-user@ip-172-31-4-103 a]$ //content deleted
```

1. Print the content of the file in reverse manner

```jsx
[ec2-user@ip-172-31-4-103 a]$ cat f1.txt
Hello
World
he
bye
see
Hello
go
[ec2-user@ip-172-31-4-103 a]$ tac f1.txt
go
Hello
see
bye
he
World
Hello
```

1. Copy the data one file to another file

```jsx
[ec2-user@ip-172-31-4-103 a]$ ls
a  f1.txt  f2.txt  f3.txt  f4.txt  f5.txt  f6.txt
[ec2-user@ip-172-31-4-103 a]$ cat f2.txt
[ec2-user@ip-172-31-4-103 a]$ cp f1.txt f2.txt
[ec2-user@ip-172-31-4-103 a]$ cat f2.txt
Hello
World
he
bye
see
Hello
go
```

1. Copy the from multiple file into a single file

```jsx
[ec2-user@ip-172-31-4-103 a]$ cat f1.txt f2.txt > f3.txt
[ec2-user@ip-172-31-4-103 a]$ cat f3.txt
Hello
World
he
bye
see
Hello
go
Hello
World
he
bye
see
Hello
go
```

1. Show first 10 line of content from head direction in a file

 

```jsx
[ec2-user@ip-172-31-4-103 a]$ head f3.txt
Hello
World
he
bye
see
Hello
go
Hello
World
he
```

1. Particular set of lines if you want to read from head of the file content

```jsx
[ec2-user@ip-172-31-4-103 a]$ head -n 5 f3.txt
Hello
World
he
bye
see
```

1. How to read last 10 line of the file content

```jsx
[ec2-user@ip-172-31-4-103 a]$ cat f3.txt
Hello
World
he
bye
see
Hello
go
Hello
World
he
bye
see
Hello
go
[ec2-user@ip-172-31-4-103 a]$ tail f3.txt
see
Hello
go
Hello
World
he
bye
see
Hello
go
```

1. Last 3 line read from the file

```jsx
[ec2-user@ip-172-31-4-103 a]$ tail -n 3 f3.txt
see
Hello
go
```

1. “grep” command using for searching text from formatting structure and this command also case-sensitive. It using for pattern search or complete keyword search

```jsx
[ec2-user@ip-172-31-4-103 a]$ cat f3.txt
Hello
World
he
bye
see
Hello
go
Hello
World
he
bye
see
Hello
go
[ec2-user@ip-172-31-4-103 a]$ grep 'Hel' f3.txt
Hello
Hello
Hello
Hello
[ec2-user@ip-172-31-4-103 a]$ grep 'hel' f3.txt
[ec2-user@ip-172-31-4-103 a]$
```

1. How to search case-insensitive using “grep” command

```jsx
[ec2-user@ip-172-31-4-103 a]$ cat f3.txt
Hello
World
he
bye
see
Hello
go
Hello
World
he
bye
see
Hello
go
hello
world
[ec2-user@ip-172-31-4-103 a]$ grep -i 'He' f3.txt
Hello
he
Hello
Hello
he
Hello
hello
```

1. How to search line with line number 

```jsx
[ec2-user@ip-172-31-4-103 a]$ grep -n 'He' f3.txt
1:Hello
6:Hello
8:Hello
13:Hello
[ec2-user@ip-172-31-4-103 a]$ grep -n -i 'He' f3.txt
1:Hello
3:he
6:Hello
8:Hello
10:he
13:Hello
15:hello
```

1. Find the lines where ‘He’ not present with line number

```jsx
//case sensitive
[ec2-user@ip-172-31-4-103 a]$ grep -v -n 'He' f3.txt
2:World
3:he
4:bye
5:see
7:go
9:World
10:he
11:bye
12:see
14:go
15:hello
16:world

//case-insensitive
[ec2-user@ip-172-31-4-103 a]$ grep -v -n -i 'He' f3.txt
2:World
4:bye
5:see
7:go
9:World
11:bye
12:see
14:go
16:world

```

1. Pattern search for all the files

```jsx
[ec2-user@ip-172-31-4-103 a]$ grep 'He' *
grep: a: Is a directory
f1.txt:Hello
f1.txt:Hello
f2.txt:Hello
f2.txt:Hello
f3.txt:Hello
f3.txt:Hello
f3.txt:Hello
f3.txt:Hello
//not case-sensitive
[ec2-user@ip-172-31-4-103 a]$ grep -i 'He' *
grep: a: Is a directory
f1.txt:Hello
f1.txt:he
f1.txt:Hello
f2.txt:Hello
f2.txt:he
f2.txt:Hello
f3.txt:Hello
f3.txt:he
f3.txt:Hello
f3.txt:Hello
f3.txt:he
f3.txt:Hello
f3.txt:hello

```

1. ‘He’ this pattern search not match for all the files

```jsx
[ec2-user@ip-172-31-4-103 a]$ grep -i -v 'He' *
grep: a: Is a directory
f1.txt:World
f1.txt:bye
f1.txt:see
f1.txt:go
f2.txt:World
f2.txt:bye
f2.txt:see
f2.txt:go
f3.txt:World
f3.txt:bye
f3.txt:see
f3.txt:go
f3.txt:World
f3.txt:bye
f3.txt:see
f3.txt:go
f3.txt:world

```

1. Pattern matching with line number not case-sensitive

```jsx
[ec2-user@ip-172-31-4-103 a]$ grep -i -n 'He' *
grep: a: Is a directory
f1.txt:1:Hello
f1.txt:3:he
f1.txt:6:Hello
f2.txt:1:Hello
f2.txt:3:he
f2.txt:6:Hello
f3.txt:1:Hello
f3.txt:3:he
f3.txt:6:Hello
f3.txt:8:Hello
f3.txt:10:he
f3.txt:13:Hello
f3.txt:15:hello

```

1. Pattern matching last 10 lines in a file with line numbers

```jsx
//case sensitive
[ec2-user@ip-172-31-4-103 a]$ tail f3.txt | grep -n 'he'
4:he
9:hello

//not case sensitive
[ec2-user@ip-172-31-4-103 a]$ tail f3.txt | grep -n -i 'he'
2:Hello
4:he
7:Hello
9:hello

```

1. lines, words and number of character count 

```jsx
[ec2-user@ip-172-31-4-103 a]$ wc f3.txt
16 16 76 f3.txt
[ec2-user@ip-172-31-4-103 a]$ cat -n f3.txt
     1  Hello
     2  World
     3  he
     4  bye
     5  see
     6  Hello
     7  go
     8  Hello
     9  World
    10  he
    11  bye
    12  see
    13  Hello
    14  go
    15  hello
    16  world

```

1. Only want line numbers

```jsx
[ec2-user@ip-172-31-4-103 a]$ wc -l f3.txt
16 f3.txt
```

1. Only count words

```jsx
[ec2-user@ip-172-31-4-103 a]$ wc -w f3.txt
16 f3.txt
```

1. Only count characters

```jsx
[ec2-user@ip-172-31-4-103 a]$ wc -c f3.txt
76 f3.txt
[ec2-user@ip-172-31-4-103 a]$ wc -m f3.txt
76 f3.txt
//both commands are right
```

1. Visual Editor (vi) : It create a file when file doesn’t exists. But if file is exists then file open then press ‘i’ for entire insert mode then whatever you want to write you can write then exist from insert mode press esc button then ‘:wq’ write then press enter - your file is save and quite. ‘:q!’ is command is for without save quite. ‘:w’ this mode for only save not quite.

```jsx
[ec2-user@ip-172-31-4-103 ~]$ ls
a
[ec2-user@ip-172-31-4-103 ~]$ vi f3.txt
[ec2-user@ip-172-31-4-103 ~]$ ls
a  f3.txt
[ec2-user@ip-172-31-4-103 ~]$ cat f3.txt
Tanmoy Das
Tarun Das
```

1. Stream Editor (SED):

i. It is primarily used for text processing (substitution, deletion, printing, and insertion)

ii. Allows performing operations on files without opening them.

iii. A Highly versatile and powerful command in Linux.

 

```jsx
[ec2-user@ip-172-31-4-103 ~]$ cat f5.txt
Hello Hello
Hello
//case sensitive
[ec2-user@ip-172-31-4-103 ~]$ sed 's\hello\welcome\' f5.txt
Hello Hello
Hello
// first occurance of the file but not save
[ec2-user@ip-172-31-4-103 ~]$ sed 's\Hello\welcome\' f5.txt
welcome Hello
welcome
[ec2-user@ip-172-31-4-103 ~]$ cat f5.txt
Hello Hello
Hello
// second occurance of the file but not save
[ec2-user@ip-172-31-4-103 ~]$ sed 's\Hello\welcome\2' f5.txt
Hello welcome
Hello
//replace all oocurance in the file but not save
[ec2-user@ip-172-31-4-103 ~]$ sed 's\Hello\welcome\g' f5.txt
welcome welcome
welcome
//replace all occurances in the file and also save modified file content
[ec2-user@ip-172-31-4-103 ~]$ cat f5.txt
Hello Hello
Hello
[ec2-user@ip-172-31-4-103 ~]$ sed -i 's\Hello\welcome\g' f5.txt
[ec2-user@ip-172-31-4-103 ~]$ cat f5.txt
welcome welcome
welcome
```

1. Delete a particular line in the file

```jsx
[ec2-user@ip-172-31-4-103 ~]$ cat f5.txt
1. welcome welcome
2. welcome
[ec2-user@ip-172-31-4-103 ~]$ sed -i '1d' f5.txt
[ec2-user@ip-172-31-4-103 ~]$ cat f5.txt
2. welcome
```

1. Delete last line

```jsx
[ec2-user@ip-172-31-4-103 ~]$ cat f5.txt
2. welcome
3. nknefknjk
4. mnfn
5. nd
6. kknkfenf
7. e, ,f emn
[ec2-user@ip-172-31-4-103 ~]$ sed -i '$d' f5.txt
[ec2-user@ip-172-31-4-103 ~]$ cat f5.txt
2. welcome
3. nknefknjk
4. mnfn
5. nd
6. kknkfenf
```

1. Delete line in a particular range

```jsx
[ec2-user@ip-172-31-4-103 ~]$ cat f5.txt
2. welcome
3. nknefknjk
4. mnfn
5. nd
6. kknkfenf
[ec2-user@ip-172-31-4-103 ~]$ sed -i '3,5d' f5.txt
[ec2-user@ip-172-31-4-103 ~]$ cat f5.txt
2. welcome
3. nknefknjk
```

1. Delete all

```jsx
[ec2-user@ip-172-31-4-103 ~]$ cat f5.txt
1. nkfenknfk
2. welcome
3. nknefknjk
4.knksnbkj
[ec2-user@ip-172-31-4-103 ~]$ sed -i '1,$d' f5.txt
[ec2-user@ip-172-31-4-103 ~]$ cat f5.txt
[ec2-user@ip-172-31-4-103 ~]$ //delete all
```

1. Print the line in given range

```jsx
[ec2-user@ip-172-31-4-103 ~]$ sed -n '1,3p' f1.txt
1. welcome
2. welcome
3. welcome
```

1. Print all lines

```jsx
[ec2-user@ip-172-31-4-103 ~]$ sed -n '1,$p' f1.txt
1. welcome
2. welcome
3. welcome
4. welcome
5. welcome
6. welcome
```

1. Inserting new line

```jsx
//the data inserted was temporary
[ec2-user@ip-172-31-4-103 ~]$ sed '2i\hello world' f1.txt
1. welcome
hello world
2. welcome
3. welcome
4. welcome
5. welcome
6. welcome
[ec2-user@ip-172-31-4-103 ~]$ cat f1.txt
1. welcome
2. welcome
3. welcome
4. welcome
5. welcome
6. welcome
//permently add data
[ec2-user@ip-172-31-4-103 ~]$ sed -i '2i\hello world' f1.txt
[ec2-user@ip-172-31-4-103 ~]$ cat f1.txt
1. welcome
hello world
2. welcome
3. welcome
4. welcome
5. welcome
6. welcome
```

1. Data add in last line

```jsx
[ec2-user@ip-172-31-4-103 ~]$ sed -i '$a\hello world' f1.txt
[ec2-user@ip-172-31-4-103 ~]$ cat f1.txt
1. welcome
hello world
2. welcome
3. welcome
4. welcome
5. welcome
6. welcome
hello world
```