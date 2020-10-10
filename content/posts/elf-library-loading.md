---
author: "Bernardo"
title: "ELF library loading"
date: 2020-10-09T23:30:10-04:00
tags: ["linux"]
---

TIL about the algorithm an interpreter uses in order to load libraries in which
your ELF file depends on:

The interpreter locates the libraries in this order:

1. `LD_PRELOAD` environment variable, and anything in /etc/ld.so.preload
2. `LD_LIBRARY_PATH` environment variable
3. `DT_RUNPATH` or `DT_RPATH` specified in the binary file (both can be modified with patchelf)
4. system-wide configuration (/etc/ld.so.conf)
5. `/lib` and `/usr/lib`
