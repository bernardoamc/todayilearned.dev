---
author: "Bernardo"
title: "ramdisk tests"
date: 2019-05-04T15:30:10-04:00
tags: ["databases", "testing"]
---

TIL about running tests through a spawned database instance off a RAM disk. This
has been applied for a long time, but completely flew under my radar. An early
example of this setup with Rails and MySQL can be seen [here](https://github.com/mezis/mrd).

The idea is to make your test database’s storage live in memory instead of
on-disk since it makes for faster reads and writes, even when considering the
use of SSD.
