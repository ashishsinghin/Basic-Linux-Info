** Finding Yourself with pwd ** :- The present working directory command, pwd, returns your location within 
the directory structure.
```
ashishsingh@nuc7i7bnh:~$ pwd
/home/ashishsingh
```

**Checking Your Login with whoami** :- If you’ve forgotten whether you’re logged in as root or another user, 
you can use the `whoami` command to see which user you’re logged in as:
```
ashishsingh@nuc7i7bnh:~$ whoami
ashishsingh
ashishsingh@nuc7i7bnh:~$ sudo su
[sudo] password for ashishsingh:
root@nuc7i7bnh:/home/ashishsingh# whoami
root
```

**Changing Directories with cd** :- To change directories from the terminal, use the change directory command, cd.
```
ashishsingh@nuc7i7bnh:~$ cd /etc
ashishsingh@nuc7i7bnh:/etc$ pwd
/etc
```
To move up one level in the file structure (toward the root of the file structure, or /), we
use cdfollowed by double dots (..), as shown here:
```
ashishsingh@nuc7i7bnh:/etc$ cd ..
ashishsingh@nuc7i7bnh:/$
```

**Listing the Contents of a Directory with ls** :- To see the contents of a directory (the files and subdirectories),
we can use the ls(list)
command. This is very similar to the `dir` command in Windows.
```
ashishsingh@nuc7i7bnh:/$ ls
bin                home               mnt   sbin.usr-is-merged  usr
bin.usr-is-merged  lib                opt   snap                var
boot               lib64              proc  srv
cdrom              lib.usr-is-merged  root  swap.img
dev                lost+found         run   sys
etc                media              sbin  tmp
```

To get more information about the files and directories, such as their permissions,
owner, size, and when they were last modified, you can add the -lswitch after ls(the l
stands for long). This is often referred to as long listing. Let’s try it here:
```
ashishsingh@nuc7i7bnh:/$ ls -l
total 4194396
lrwxrwxrwx   1 root root          7 Apr 22 18:38 bin -> usr/bin
drwxr-xr-x   2 root root       4096 Feb 26 18:28 bin.usr-is-merged
drwxr-xr-x   4 root root       4096 Jun  7 10:08 boot
dr-xr-xr-x   2 root root       4096 Apr 24 16:58 cdrom
drwxr-xr-x  21 root root       4580 Jun 28 09:00 dev
drwxr-xr-x 152 root root      12288 Jun 28 09:00 etc
drwxr-xr-x   4 root root       4096 May 14 16:27 home
lrwxrwxrwx   1 root root          7 Apr 22 18:38 lib -> usr/lib
lrwxrwxrwx   1 root root          9 Apr 22 18:38 lib64 -> usr/lib64
drwxr-xr-x   2 root root       4096 Apr  8 20:07 lib.usr-is-merged
drwx------   2 root root      16384 May 14 12:37 lost+found
drwxr-xr-x   4 root root       4096 May 30 11:20 media
drwxr-xr-x   2 root root       4096 Apr 24 16:17 mnt
drwx--x--x   4 root root       4096 May 28 15:20 opt
dr-xr-xr-x 306 root root          0 Jan  1  2009 proc
drwx------   6 root root       4096 Jun 28 09:40 root
drwxr-xr-x  41 root root       1060 Jun 28 09:29 run
lrwxrwxrwx   1 root root          8 Apr 22 18:38 sbin -> usr/sbin
drwxr-xr-x   2 root root       4096 Mar 31 14:30 sbin.usr-is-merged
drwxr-xr-x  16 root root       4096 May 21 11:45 snap
drwxr-xr-x   2 root root       4096 Apr 24 16:17 srv
-rw-------   1 root root 4294967296 May 14 12:41 swap.img
dr-xr-xr-x  13 root root          0 Jun 28 09:39 sys
drwxrwxrwt  19 root root       4096 Jun 28 10:47 tmp
drwxr-xr-x  12 root root       4096 Apr 24 16:17 usr
drwxr-xr-x  15 root root       4096 May 15 11:50 var
```

Some files in Linux are hidden and won’t be revealed by a simple lsor ls-lcommand.
To show hidden files, add a lowercase –aswitch, like so:
```
ashishsingh@nuc7i7bnh:/$ ls -a
.                  cdrom  lib64              opt   sbin.usr-is-merged  tmp
..                 dev    lib.usr-is-merged  proc  snap                usr
bin                etc    lost+found         root  srv                 var
bin.usr-is-merged  home   media              run   swap.img
boot               lib    mnt                sbin  sys
```

**Getting Help** :- Nearly every command, application, or utility has a dedicated help file in Linux that
provides guidance for its use.
```
ashishsingh@nuc7i7bnh:/$ ls --help
Usage: ls [OPTION]... [FILE]...
List information about the FILEs (the current directory by default).
Sort entries alphabetically if none of -cftuvSUX nor --sort is specified.

Mandatory arguments to long options are mandatory for short options too.
  -a, --all                  do not ignore entries starting with .
  -A, --almost-all           do not list implied . and ..
```
`Note the double dash here. The convention in Linux is to use a double dash (--) before
word options, such as help, and a single dash (-) before single­letter options, such as –h.`

When you enter this command, you should see a short description of the tool and
guidance on how to use it. In some cases, you can use either -hor -?to get to the help
file.

```
ashishsingh@nuc7i7bnh:/$ docker -h
Flag shorthand -h has been deprecated, please use --help

Usage:  docker [OPTIONS] COMMAND

A self-sufficient runtime for containers

Common Commands:
  run         Create and run a new container from an image
  exec        Execute a command in a running container
  ps          List containers


ashishsingh@nuc7i7bnh:/$ docker -?
unknown shorthand flag: '?' in -?
See 'docker --help'.

Usage:  docker [OPTIONS] COMMAND

A self-sufficient runtime for containers

Common Commands:
  run         Create and run a new container from an image
  exec        Execute a command in a running container
  ps          List containers
  build       Build an image from a Do
```

**Referencing Manual Pages with man** :- In addition to the help switch, most commands and applications have a manual (man)
page with more information, such as a description and synopsis of the command or
application. You can view a man page by simply typing manbefore the command, utility,
or application.

```
ashishsingh@nuc7i7bnh:/$ man ls


LS(1)                            User Commands                           LS(1)

NAME
       ls - list directory contents

SYNOPSIS
       ls [OPTION]... [FILE]...

DESCRIPTION
       List  information  about  the FILEs (the current directory by default).
       Sort entries alphabetically if none of -cftuvSUX nor --sort  is  speci‐
       fied.

       Mandatory  arguments  to  long  options are mandatory for short options
       too.

       -a, --all
              do not ignore entries starting with .

       -A, --almost-all
              do not list implied . and ..
```
You can scroll through this manual file using the ENTER key, or
you can page up and down using the PG DN and PG UP keys, respectively. To exit, simply
enter q(for quit), and you’ll return to the command prompt.

**Finding Binaries with whereis** :- If you’re looking for a binary file, you can use the whereiscommand to locate it. This
command returns not only the location of the binary but also its source and man page if
they are available. Here’s an example:
```
ashishsingh@nuc7i7bnh:/$ whereis ls
ls: /usr/bin/ls /usr/share/man/man1/ls.1.gz
```

**Finding Binaries in the PATH Variable with which** :- The whichcommand is even more specific: it only returns the location of the binaries in
the PATHvariable in Linux.
```
ashishsingh@nuc7i7bnh:/$ which ls
/usr/bin/ls
```
Here, whichwas able to find a single binary file in the directories listed in the PATH
variable. At minimum, these directories usually include /usr/bin, but may include
/usr/sbin and maybe a few others

**Performing More Powerful Searches with find** :- The findcommand is the most powerful and flexible of the searching utilities. It is
capable of beginning your search in any designated directory and looking for a number
of different parameters, including, of course, the filename but also the date of creation
or modification, the owner, the group, permissions, and the size.

Here’s the basic syntax for find:
```
find directory options expression
```

**Filtering with grep** :- Very often when using the command line, you’ll want to search for a particular
keyword. For this, you can use the grepcommand as a filter to search for keywords.
The grepcommand is often used when output is piped from one command to another.
```
ashishsingh@nuc7i7bnh:/$ ps aux | grep init
root           1  0.1  0.0  23644  8292 ?        Ss   08:18   0:14 /sbin/init splash
ashishs+    3956  0.3  0.2 667348 32672 ?        Sl   08:21   0:40 /usr/bin/Xwayland :0 -rootless -noreset -accessx -core -auth /run/user/1001/.mutter-Xwaylandauth.BPFTP2 -listenfd 4 -listenfd 5 -displayfd 6 -initfd 7 -byteswappedclients
ashishs+    6313  0.0  0.0 33578032 1152 ?       Sl   08:37   0:00 /snap/brave/418/opt/brave.com/brave/chrome_crashpad_handler --monitor-self --monitor-self-annotation=ptype=crashpad-handler --database=/home/ashishsingh/snap/brave/418/.config/BraveSoftware/Brave-Browser/Crash Reports --metrics-dir=/home/ashishsingh/snap/brave/418/.config/BraveSoftware/Brave-Browser --url=https://cr.brave.com --annotation=lsb-release=Ubuntu Core 22 --annotation=plat=Linux --annotation=prod=Chrome_Linux --annotation=ver=126.1.67.119 --initial-client-fd=5 --shared-client-connection
ashishs+    6315  0.0  0.0 33568796 256 ?        Sl   08:37   0:00 /snap/brave/418/opt/brave.com/brave/chrome_crashpad_handler --no-periodic-tasks --monitor-self-annotation=ptype=crashpad-handler --database=/home/ashishsingh/snap/brave/418/.config/BraveSoftware/Brave-Browser/Crash Reports --url=https://cr.brave.com --annotation=lsb-release=Ubuntu Core 22 --annotation=plat=Linux --annotation=prod=Chrome_Linux --annotation=ver=126.1.67.119 --initial-client-fd=4 --shared-client-connection
ashishs+   39108  0.0  0.0   9144  2176 pts/0    S+   11:21   0:00 grep --color=auto init
```
***Concatenation with cat** :- The catcommand followed by a filename will display the contents of that file, but to
create a file, we follow the catcommand with a redirect, denoted with the > symbol, and
a name for the file we want to create. Here’s an example:
```
ashishsingh@nuc7i7bnh:~$ cat > codingskill
coding is the most valuable skill
```
When you press ENTER, Linux will go into interactive mode and wait for you to start
entering content for the file.
To exit and return to the prompt, I press CTRL­D. Then, when I want to see what’s in
the file codingskill, I enter the following:
```
ashishsingh@nuc7i7bnh:~$ cat codingskill 
coding is the most valuable skill
```
If you don’t use the redirect symbol, Linux will spit back the contents of your file.

To add, or append, more content to a file, you can use the catcommand with a double
redirect (>>), followed by whatever you want to add to the end of the file. Here’s an
example:
```
ashishsingh@nuc7i7bnh:~$ cat >> codingskill 
Added new line
ashishsingh@nuc7i7bnh:~$ cat codingskill 
coding is the most valuable skillAdded new line
```
If I want to overwrite the file with new information, I can simply use the catcommand
with a single redirect again, as follows:
```
ashishsingh@nuc7i7bnh:~$ cat > codingskill 
overwrite the file
ashishsingh@nuc7i7bnh:~$ cat codingskill 
overwrite the file
```

**File Creation with touch** :- The second command for file creation is touch. This command was originally developed
so a user could simply touch a file to change some of its details, such as the date it was
created or modified. However, if the file doesn’t already exist, this command creates
that file by default.
```
ashishsingh@nuc7i7bnh:~$ touch newfile
ashishsingh@nuc7i7bnh:~$ ls -l
total 1
-rw-rw-r-- 1 ashishsingh ashishsingh    0 Jun 28 11:31  newfile
```

***Creating a Directory** :- The command for creating a directory in Linux is mkdir, a contraction of make directory.
To create a directory named newdirectory, enter the following command:
```
ashishsingh@nuc7i7bnh:~$ mkdir newdirectory
ashishsingh@nuc7i7bnh:~$ cd newdirectory/
ashishsingh@nuc7i7bnh:~/newdirectory$
```

**Copying a File** :- To copy files, we use the cpcommand. This creates a duplicate of the file in the new
location and leaves the old one in place.
```
ashishsingh@nuc7i7bnh:~$ cp newfile newdirectory/
ashishsingh@nuc7i7bnh:~$ cd newdirectory/
ashishsingh@nuc7i7bnh:~/newdirectory$ ls
newfile
```

**Renaming a File**:- Unfortunately, Linux doesn’t have a command intended solely for renaming a file, as
Windows and some other operating systems do, but it does have the mv(move)
command.
The mv command can be used to move a file or directory to a new location or simply to
give an existing file a new name. To rename newfile to newfile2, you would enter the
following:
```
ashishsingh@nuc7i7bnh:~/newdirectory$ ls
newfile
ashishsingh@nuc7i7bnh:~/newdirectory$ mv newfile newfile2
ashishsingh@nuc7i7bnh:~/newdirectory$ ls
newfile2
```
Now when you list (ls) that directory, you see newfile2 but not newfile, because it has
been renamed. You can do the same with directories.

**Removing a File** :- To remove a file, you can simply use the rmcommand, like so:
```
ashishsingh@nuc7i7bnh:~/newdirectory$ ls
newfile2
ashishsingh@nuc7i7bnh:~/newdirectory$ rm newfile2 
ashishsingh@nuc7i7bnh:~/newdirectory$ ls
ashishsingh@nuc7i7bnh:~/newdirectory$
```
**Removing a Directory** :- The command for removing a directory is similar to the rmcommand for removing files
but with dir(for directory) appended, like so:
```
ashishsingh@nuc7i7bnh:~/newdirectory$ touch newfile
ashishsingh@nuc7i7bnh:~/newdirectory$ cd ..
ashishsingh@nuc7i7bnh:~$ rmdir newdirectory/
rmdir: failed to remove 'newdirectory/': Directory not empty
```
It’s important to note that rmdirwill not remove a directory that is not empty, but will
give you a warning message that the “directory is not empty,” as you can see in this

If you do want to remove a directory and its content all in one go, you can use the -r
switch after rm, like so:
```
ashishsingh@nuc7i7bnh:~$ rm -r newdirectory/
```
Just a word of caution, though: be wary of using the -roption with rm, at least at first,
because it’s very easy to remove valuable files and directories by mistake. Using rm-rin
your home directory, for instance, would delete every file and directory there—probably
not what you were intending.

### GO PLAY NOW!
Now that you have some basic skills for navigating around the filesystem, you can play
with your Linux system a bit before progressing. The best way to become comfortable
with using the terminal is to try out your newfound skills right now.
