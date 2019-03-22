---
author: "Bernardo"
title: "android memory usage"
date: 2019-03-22T16:30:10-04:00
tags: ["android"]
---

TIL Android has a tool called procrank (`/system/xbin/procrank`), which lists
out the memory usage of Linux processes in order from highest to lowest usage.
The sizes reported per process are VSS, RSS, PSS, and USS.

**VSS**

* is the total accessible address space of a process.

**RSS**

* is the total memory actually held in RAM for a process, including shared
  libraries.

**PSS**

* same as `RSS`, but reports the proportional size of its shared libraries.
  Meaning that if you have 4 processes using the same libraries each will hold
  25% of the memory.

**USS**

* is the total private memory for a process, as is, it doesn't include
  shared libraries.

For more information check [this guide](https://elinux.org/Android_Memory_Usage).
