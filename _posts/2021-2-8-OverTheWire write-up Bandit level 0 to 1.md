---
layout: post
title: # OverTheWire write-up Bandit level 0 to 1
tags: [overthewire, bandit]
---

This is a write-up for the Over The Wire wargame [Bandit](https://overthewire.org/wargames/bandit/) level 0 to Level 1 

First, we need to connect to the Over the Wire Bandit game with SSH. You will need an SSH client. For Linux, I suggest Gnome Connection Manager and for Windows I suggest Putty.
<!--more-->
The hostname is ```bandit.labs.overthewire.org``` 
User: ```bandit0```
password: ```bandit0```

The best tool to use to read about Linux commands is the man pages. To use man pages you simply type: ```man <command name>```
Example: ```man ls```

Commands used for this level:
```ls```  - List information about the FILE's (the current directory by default).

The two most common  arguments used with ```ls``` are:
```ls -a``` - view all files including hidden files that start with.
```ls -l``` - view long list format of files.

```cat``` - used to view contents of a file.

Step 1.
 After logging in type ```ls```
 You will see a file named readme

Step 2.
  Type ```cat readme```
  The contents of the file have the password for level 1 in it.
   > boJ9jbbUNNfktd78OOpsqOltutMc3MY1