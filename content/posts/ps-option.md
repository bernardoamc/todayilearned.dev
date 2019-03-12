---
author: "Bernardo"
title: "The ps -o flag"
date: 2019-03-12T07:50:10-04:00
tags: ["bash"]
---

The `ps` command is well known for displaying process information, but
it was only recently that I found out about the useful `-o` flag. What
this flag does is display the informatin about one or more selected
headers.

Let's see an example where we display the `rss` (Resident Set Size) for the
process with `pid` 5380:

{{< highlight bash >}}
$ ps -o rss -p 5380
   RSS
  1784
{{< /highlight >}}

* rss represents the `real memory`, that is, the process's memory that is
held in RAM.

We can also display more headers separating them with commas:

{{< highlight bash >}}
$ ps -o rss,%cpu,%mem -p 348
   RSS  %CPU %MEM
179468   5.8  2.1
{{< /highlight >}}

And we can also add a new label for a header:

{{< highlight bash >}}
$ ps -o rss=RealMemory -p 348
RealMemory
    179572
{{< /highlight >}}
