---
author: "Bernardo"
title: "Vim recursive macros"
date: 2019-11-01T15:15:10-04:00
tags: ["vim"]
---

TIL about recursive macros in vim. As the name implies, it consists of calling
your macro within the macro your are building. Pre-requisites:

1. Having a clear register (`qa` -> `q` to clear register `a`)
2. Having a break point through `t` or `f` if we don't want to run on all lines

Suppose we have the following file:

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

In order to build our recursive macro:

Command &nbsp;&nbsp; | &nbsp;
-------------------- |------
`qa`                 | Start macro
`02cw`               | Go to beginning of line and change two words
`hash"[<esc>`&nbsp;  | Insert `hash["` characters and exit normal mode
`f,`                 | Find the next `,` character
`i"] = <esc>`        | Insert `"] = ` characters and exit normal mode
`lx`                 | Move left and delete a character (the `,` in this case)
`j`                  | Go to the line below
`@a`                 | Call your macro. This creates the recursion
`q`                  | Finish macro

After that calling `@a` will change every line.
