---
layout: post
title: # OverTheWire write-up Bandit level 1 to 2
tags: [overthewire, bandit]
---

This is a write-up for the Over The Wire wargame [Bandit](https://overthewire.org/wargames/bandit/) level 1 to level 2

## Level Goal

> The password for the next level is stored in a file called - located in the home directory.
<!--more-->
The hostname is ```bandit.labs.overthewire.org``` 
```User: bandit1```
```password: boJ9jbbUNNfktd78OOpsqOltutMc3MY1```

Commands used for this level:
```cat``` - used to view contents of a file.
```ls``` - List information about the FILE's (the current directory by default).

Step 1.
 After logging in type ```ls```
 You will see a file named ```-```

Step 2.
Now from the last level we might think that typing ```cat``` - would allow you to view the contents of the file, but it wont.

Usage of dash (-) in place of a filename
Using ```-``` as a filename to mean stdin/stdout is a convention that a lot of programs use. When ```cat``` sees the string ```-``` as a filename, it treats it as a synonym for stdin.
What will happen in our case is ```cat``` - echoes stdin, in this case keyboard user input, to stdout, the terminal window. Go ahead and try it to see what happens.
(if you are stuck after doing this press CTRL C to exit back to bash prompt).

The other problem is that Linux command options usually start with a dash ( - ). If you try to type that filename on a command line, the command might think you're trying to type a command option.

To get around this, you need to alter the way that ```cat``` sees the file as a regular file by "hiding" the dash from ```cat```. The best way to do this is to ```cat``` directly to the file location by prefixing the filename with ```./``` or ```/home/bandit1/. ./``` means "look in the current directory". and /home/bandit1/ means "look in directory /home/bandit1.

  Type ```cat ./-```
  The contents of the file have the password for level 2 in it.
   > CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9 