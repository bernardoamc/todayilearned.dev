---
author: "Bernardo"
title: "Vim :normal"
date: 2019-03-11T17:00:10-04:00
tags: ["vim"]
---

Sometimes it is useful to use the `:normal` command in VIM, what it does is
accept a sequence of keys and pretend they were typed in normal mode.

Let's see how this works with a quick example. Suppose we have a file like the
following:

{{< highlight ruby >}}
 1  abc,123
 2  bcd,4
 3  cde,54321
 4  def,88
{{< /highlight >}}

And we want the end result to be:

{{< highlight ruby >}}
hash["abc"] = 123
hash["bcd"] = 4
hash["cde"] = 54321
hash["def"] = 88
{{< /highlight >}}

To solve this in one command we can select the lines we want to modify and use:

`1,4normal 02dwihash["^[f,i"] = ^[lx`

It looks complicated, but let's break this down:

Command &nbsp;&nbsp; | &nbsp;
-------------------- |------
`02dw`               | Go to beginning of line and delete two words
`ihash["`&nbsp;&nbsp;| Insert `hash["` characters
`^[`                 | Esc key generated using `ctrl+v` followed by `esc`
`f,`                 | Find the next `,` character
`i"] =`              | Insert `"] = ` characters
`^[`                 | Esc key generated using `ctrl+v` followed by `esc`
`lx`                 | Move left and delete a character (the `,` in this case)
