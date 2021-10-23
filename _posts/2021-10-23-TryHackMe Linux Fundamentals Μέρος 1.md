---
layout: post
title: # TryHackMe Linux Fundamentals Μέρος 1 
tags: [tryhackme]
---

Πρόσφατα συνάντησα το [TryHackMe](https://tryhackme.com), μια νέα πλατφόρμα για εκμάθηση και διδασκαλία της ασφάλειας στον κυβερνοχώρο. Διαφέρει από τις περισσότερες άλλες πλατφόρμες στο ότι ενώ άλλες πλατφόρμες επικεντρώνονται κυρίως στην αυτομάθηση δημιουργώντας περιεχόμενο για τους χρήστες τους, το TryHackMe χρησιμοποιεί διάφορες τεχνικές για να διευκολύνει τους χρήστες να μάθουν για τα διαφορετικά και μερικές φορές βαθιά πολύπλοκα επίπεδα που υπάρχουν στον κόσμο της κυβερνοασφάλειας. 
<!--more-->
Σε αυτο το άρθρο κάνουμε μια φιλική περιήγηση του δωματίου [Linux Fundamentals part 1](https://tryhackme.com/room/linuxfundamentalspart1).

Τα περιεχόμενα του δωματίου: 
- Task 1: Introduction
- Task 2: A Bit of Background on Linux
- Task 3: Interacting With Your First Linux Machine (In-Browser)
- Task 4: Running Your First few Commands
- Task 5: Interacting With the Filesystem!
- Task 6: Searching for Files
- Task 7: An Introduction to Shell Operators
- Task 8: Conclusions & Summaries
- Task 9: Linux Fundamentals Part 2

## Task 1: Introduction
Απάντηση: Δεν απαιτείται απάντηση 

## Task 2: A Bit of Background on Linux
Ερώτηση: What year was the first release of a Linux operating system?
Απάντηση: 1991

## Task 3: Interacting With Your First Linux Machine (In-Browser)
Ερώτηση: I’ve deployed my first Linux machine!
Απάντηση: Δεν χρειάζεται απάντηση 

## Task 4: Running Your First few Commands
Ερώτηση: If we wanted to output the text “TryHackMe”, what would our command be?
Χρησιμοποιούμε την εντολή echo, η οποία τυπώνει κείμενο στην οθόνη
Απάντηση: echo TryHackMe

Ερώτηση: What is the username of who you’re logged in as on your deployed Linux machine?
Απλώς χρησιμοποιήστε την εντολή whoami
Απάντηση: TryHackMe

## Task 5: Interacting With the Filesystem!
Ερώτηση: On the Linux machine that you deploy, how many folders are there?
Χρησιμοποιήστε την εντολή ls για να δείτε όλους τους φακέλους 
Απάντηση: 4

Ερώτηση: Which directory contains a file?
Χρησιμοποιήστε την εντολή cd και την εντολή ls για να ελέγξετε κάθε φάκελο και να δείτε ποιος περιέχει το αρχείο 
Απάντηση: folder4

Ερώτηση: What are the contents of this file?
Χρησιμοποιήστε την εντολή cat για να εξάγετε το περιεχόμενο του αρχείου 
Απάντηση: Hello World

Χρησιμοποιήστε την εντολή cd για να μεταβείτε στο αρχείο και την εντολή pwd για να εξάγετε τον τρέχοντα κατάλογο εργασίας. 

## Task 6: Searching for Files
Ερώτηση: Use grep on “access.log” to find the flag that has a prefix of “THM”. What is the flag?
Απάντηση: THM{ACCESS}

## Task 7: An Introduction to Shell Operator
Ερώτηση: If we wanted to run a command in the background, what operator would we want to use?
Απάντηση: &

Ερώτηση: If I wanted to replace the contents of a file named “passwords” with the word “password123”, what would my command be?
Απάντηση: echo password 123 > passwords

Ερώτηση: Now if I wanted to add “tryhackme” to this file named “passwords” but also keep “passwords123”, what would my command be
Απάντηση: echo tryhackme >> passwords

Ερώτηση: Now use the deployed Linux machine to put these into practice
Απάντηση: Δεν χρειάζεται απάντηση 

## Task 9: Linux Fundamentals Part 2
Ερώτηση: Terminate the machine deployed in this room from task 3
Απάντηση: Δεν χρειάζεται απάντηση

Ερώτηση: Join [Linux Fundamentals Part 2](https://tryhackme.com/jr/linuxfundamentalspart2)!
Απάντηση: Δεν χρειάζεται απάντηση