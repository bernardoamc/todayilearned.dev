---
author: "Bernardo"
title: "jot command"
date: 2019-03-17T09:00:00-04:00
tags: ["bash"]
---

TIL about the `jot` command. It allows us to print sequential or random data.

The basic option has the format `jot [numbers] [start_with]`
{{< highlight bash >}}
$ jot 3 10
10
11
12
{{< /highlight >}}

or if you want to generate random data: `jot -r [numbers] [lower_limit]
[upper_limit]`

{{< highlight bash >}}
$ jot -r 3 1 20
5
12
19
{{< /highlight >}}

Not all of the flags are covered here, `man jot` does a good job explaining
them.
