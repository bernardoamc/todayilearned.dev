---
author: "Bernardo"
title: "disable-gems"
date: 2020-02-20T15:50:45-04:00
tags: ["ruby"]
---

TIL that we can disable gems when loading a Ruby script through
`--disable=gems`.

{{< highlight bash >}}
$ ruby --disable=gems -e ''
{{< /highlight >}}
