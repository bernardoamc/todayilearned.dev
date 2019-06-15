---
author: "Bernardo"
title: "uuencode"
date: 2019-06-14T20:35:10-04:00
tags: ["bash"]
---

TIL about the `uuencode` and `uudecode` command utilities. It allows us to
decode and encode binary files respectively.

{{< highlight bash >}}
$ echo 'foo' | uuencode -o my_binary my_binary
$ file my_binary
my_binary: uuencoded or xxencoded text, ASCII text
$ cat my_binary
begin 644 my_binary
$9F]O"@``
`
end

$ uudecode my_binary
$ cat my_binary
foo
{{< /highlight >}}
