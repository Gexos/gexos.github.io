---
layout: post
title: # OverTheWire write-up Bandit level 3 to 4
tags: [overthewire, bandit]
---

This is a write-up for the Over The Wire wargame [Bandit](https://overthewire.org/wargames/bandit/) level 3 to level 4

## Level Goal

> The password for the next level is stored in a hidden file in the inhere directory.
<!--more-->

The hostname is ```bandit.labs.overthewire.org``` 

User: ```bandit3```

password: ```UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK```

Commands used for this level:

```ls -a``` - List information about all the file's include hidden files that start with ```(.)```.

```cd``` - change directory

```cat``` - used to view contents of a file.

Step 1.
 After logging in type ```ls```
 You will see a directory named ```inhere``` (you can tell it's a directory instead of a file because it is a different color).

 Step 2.
 Change directory to inhere by typing ```cd inhere```


 Step 3.
Now in the ```/home/bandit3/inhere``` directory go ahead and type ```ls```.
Nothing will be displayed because the file we are looking for is hidden by placing a ```.``` in front of the file name. Placing a period as the first character of a file name is how you hide files in Linux.
We need to use ```ls -a``` , the dash a means display all files including hidden files.
We will now see the .hidden file.
Type ```cat .hidden``` and the password for level 4 is displayed.
> pIwrPrtPN36QITSp3EQaw936yaFoFgAB 