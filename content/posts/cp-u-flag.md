---
author: "Bernardo"
title: "cp -u flag"
date: 2019-04-26T18:20:10-04:00
tags: ["bash"]
---

TIL about the `-u` flag for `cp`. It will only copy files that don't exist, or
are newer than their existing counterparts in the destination directory.

{{< highlight bash >}}
$ cp -u *.txt app_dir
{{< /highlight >}}

It's a nice replacement to the interactive flag (`-i`) if we know we want this
behaviour.
