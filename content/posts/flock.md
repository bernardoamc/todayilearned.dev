---
author: "Bernardo"
title: "flock"
date: 2019-10-19T23:30:10-04:00
tags: ["system-call"]
---

TIL about the `flock` system call which applies or removes an advisory lock on an open file.
The thing to pay attention is the word `advisory`, other processes can ignore
this lock if they wish to do so. This syscall will lock the entire file, which
can be pretty bad for highly concurrent systems.

For more information: `man 2 flock`

For a more fine grained locking mechanism: `man 2 fcntl`
