# UNIX-based Command Line Basics

## Navigation

- Terminal and Package Manager Setup ([Mac](01-terminal-setup-mac.md), [Windows](01-terminal-setup-win.md))
- **UNIX-based Command Line Basics**
    - [Introduction](#introduction)
    - [Part 1: Command-Feedback Cycles](#part1)
    - [Part 2: Navigating the File Structure](#part2)
- [Python Environment Setup](03-python-setup.md)

<a name="introduction"></a>
## Introduction

This page sets you up with a UNIX or UNIX-compatible command line, from which we can begin learning command line (`bash` or `zsh`) basics.

You will need either:
- An Apple Mac computer running macOS, or
- A Windows computer with WSL installed, or
- A Linux computer with root access

NOTE: This page is similar in spirit to the Software Carpentry Unix Shell course - http://swcarpentry.github.io/shell-novice/ - however, that one is a lot more advanced and a lot more focused on helping researchers.

<a name="part1"></a>
## Part 1: Command-Feedback Cycles

A command line is a special way of "talking" to your computer. It requires you to type some command after the prompt (typically `$` or `%`), and then you see some feedback from the computer.

For example:

```bash
$ date
Wed 10 Jun 2020 16:19:57 AEST
```

Here, I issued the command `date` and `Wed 10 Jun 2020 16:19:57 AEST` was the response. The command `date` is very simple, it requests "the date", which is by default interpreted by your computer as "the current date and time". However, you can a more specific request; for example:

```bash
$ date -v+1y +"%Y-%m-%d"
2021-06-10
```

Here, I specified two additional **options**, namely `-v` and `+`. The option `-v` means "adjust" and the option `+` means "format". I set the "adjust" option to be plus one year (`+1y`) and I set the "format" option to be `"%Y-%m-%d"` which means "year-month-day".

There are many commands that one can use, all with their own options.

<a name="part2"></a>
## Part 2: Navigating the File Structure

As you hopefully already know, your computer's internal storage - typically called "C:\ drive" (Windows) or "Macintosh HD" (Mac) - is structured as a hierarchy of files and folders. Files can be stored inside folders, and folders can also be stored inside other folders.

Your command line is always operating in some folder. When you first start up, it is already operating in a folder. You can check which folder you are currently operating in using the command `pwd`, which stands for **p**resent **w**orking **d**irectory (the "proper" name for a "folder" is actually a "directory").

```bash
$ pwd
/Users/blair
```

To list the contents of your current folder, the command is "ls" (short for "list").

```bash
$ ls 
00blair         Desktop         Downloads       Library         Music           Pictures        VirtualBox VMs  places
Applications    Documents       Dropbox         Movies          OneDrive        Public          log.txt
```

The default view shows a minimalistic display of columns, which is nice, but often we need more information. We also want to show hidden files and folders, which are files and folders whose names start with a dot (.) character.

```bash
$ ls -lah
total 352
drwxr-xr-x+ 39 blair  staff   1.2K 10 Jun 16:48 .
drwxr-xr-x   5 root   admin   160B  7 Apr 05:45 ..
-rw-------   1 blair  staff     4B 25 May 15:24 .CFUserTextEncoding
-rw-r--r--@  1 blair  staff    28K 10 Jun 16:11 .DS_Store
drwx------  27 blair  staff   864B 10 Jun 16:04 .Trash
drwxr-xr-x   3 blair  staff    96B 31 May 13:50 .cache
drwxr-xr-x   3 blair  staff    96B 25 May 19:22 .config
drwx------   3 blair  staff    96B 27 May 16:54 .cups
drwxr-xr-x  14 blair  staff   448B 25 May 15:52 .dropbox
-rw-r--r--   1 blair  staff   194B 10 Jun 15:57 .gitconfig
drwxr-xr-x   3 blair  staff    96B  2 Jun 10:26 .keras
drwxr-xr-x   3 blair  staff    96B  2 Jun 11:40 .local
drwxr-xr-x   4 blair  staff   128B  2 Jun 12:05 .matplotlib
-rw-r--r--   1 blair  staff    36B 27 May 15:49 .my.cnf
drwxr-xr-x  19 blair  staff   608B 10 Jun 15:54 .oh-my-zsh
-rw-r--r--   1 blair  staff     1B  2 Jun 11:35 .profile
-rw-------   1 blair  staff   256B  2 Jun 13:10 .python_history
drwx------   3 blair  staff    96B 25 May 23:13 .ssh
-rw-------   1 blair  staff   2.3K 10 Jun 15:59 .viminfo
drwxr-xr-x   4 blair  staff   128B 25 May 17:38 .vscode-oss
-rw-------   1 blair  staff    20K 10 Jun 16:48 .zsh_history
-rw-r--r--   1 blair  staff   3.5K  2 Jun 12:19 .zshrc
drwxr-xr-x   6 blair  staff   192B  2 Jun 10:20 00blair
drwx------@  3 blair  staff    96B 10 Jun 11:13 Applications
drwx------@ 38 blair  staff   1.2K 10 Jun 15:52 Desktop
drwx------+  5 blair  staff   160B  4 Jun 11:37 Documents
drwx------+ 12 blair  staff   384B 10 Jun 15:36 Downloads
drwx------@ 19 blair  staff   608B  2 Jun 18:33 Dropbox
drwx------@ 70 blair  staff   2.2K  3 Jun 11:56 Library
drwx------+  7 blair  staff   224B  4 Jun 11:37 Movies
drwx------+  8 blair  staff   256B 27 May 10:35 Music
drwx------@ 20 blair  staff   640B 10 Jun 15:39 OneDrive
drwx------+  6 blair  staff   192B 26 May 10:18 Pictures
drwxr-xr-x+  4 blair  staff   128B 25 May 15:24 Public
drwxr-xr-x   4 blair  staff   128B  2 Jun 10:46 VirtualBox VMs
-rw-r--r--   1 blair  staff     0B 25 May 19:56 log.txt
drwxr-xr-x  14 blair  staff   448B  9 Jun 14:25 places
```

The command I issued to get this was `ls -lah`. Here, "`-lah`" is actually shorthand for `-l -a -h` (typically, for options that are a dash followed by a single letter, you can combine them like this).

Suppose now I want to go inside a folder. To do this, the command is `cd` (short for **c**hange **d**irectory), followed by the folder's name:

```bash
$ cd 00blair
$ pwd
/Users/blair/00blair
```

Note that the `cd` command does not give you any feedback that it has successfully completed. However, I used `pwd` to confirm. Usually I just trust that it worked fine!

To go back up one level, it's simply `cd ..` (in the world of command lines, `..` means "up one level", `.` means "current level").