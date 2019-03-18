---
author: "Bernardo"
title: "tldr pages"
date: 2019-03-18T07:50:10-04:00
tags: ["bash"]
---

TIL about [tldr pages](https://github.com/tldr-pages/tldr), a collection of
simplified and community-driven man pages.

It's especially useful when we already know that we need a certain tool but
forgot exactly which way to use it. Going through `man mytool` can be a slow process
sometimes.

Let's see a `tldr lsof` example:

{{< highlight bash >}}
$ tldr lsof

lsof

Lists open files and the corresponding processes.
Note: Root privileges (or sudo) is required to list files opened by others.

  - Find the processes that have a given file open:
    lsof path/to/file

  - Find the process that opened a local internet port:
    lsof -i :port

  - ...
{{< /highlight >}}

Tldr pages is an active open source project that keeps being improved, give it a
try!
