---
author: "Bernardo"
title: "at command"
date: 2019-03-15T12:15:10-04:00
tags: ["bash"]
---

TIL about the `at` command. It allows us to schedule commands to be executed
at a later time.

{{< highlight bash >}}
$ echo "bla" | at now + 5 minutes
{{< /highlight >}}

or if you want to execute commands from a file later on:

{{< highlight bash >}}
$ at -f path/to/file 9:30 PM Tue
{{< /highlight >}}

We can type `atq` to see existing jobs. For more information
check `man` or `tldr`, it's a really interesting suite of commands.
