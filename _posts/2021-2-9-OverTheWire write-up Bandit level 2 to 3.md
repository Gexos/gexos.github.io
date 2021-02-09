---
layout: post
title: # OverTheWire write-up Bandit level 2 to 3
tags: [overthewire, bandit]
---

This is a write-up for the Over The Wire wargame [Bandit](https://overthewire.org/wargames/bandit/) level 2 to level 3

## Level Goal

> The password for the next level is stored in a file called spaces in this filename located in the home directory


The hostname is ```bandit.labs.overthewire.org``` 
User: ```bandit2```
password: ```CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9```
<!--more-->
Commands used for this level:
```cat``` - used to view contents of a file.
```ls``` - List information about the FILE's (the current directory by default).

## Step 1.
 After logging in type ```ls```
 You will see a file named spaces in this filename

## Step 2.
Linux does not handle spaces in filenames well so if you do type
```cat``` spaces in this filename, ```cat``` will think you are trying to view the contents of file spaces, file ```in```, file ```this```, and file ```filename``` and those separate files do not exist.

One of the reasons Linux does not handle spaces in filenames is that bash scripting uses spaces as a NULL terminator to break a script at a certain point. It is considered a best practice to not use spaces in filenames in Linux, underscores (_) are generally used in place of spaces. spaces_in_this_filename would be a better way to name this file if you were to create it.

To get around this we need to "hide" the spaces from ```cat```, just like in Level 1. To do this we simply type a backslash (\) in the filename before each space.

Type ```cat spaces\ in\ this\ filename```.
The contents of the file have the password for level 3 in it.
> UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK