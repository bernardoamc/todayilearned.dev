---
author: "Bernardo"
title: "Vim Repeat Substitute"
date: 2019-03-10T20:25:10-04:00
tags: ["vim"]
---

TIL about the `&` command in Vim and how it can be used to repeat the last search and
replace pattern.

Let's see how this works with a quick example. Suppose we have a file like the
following:

{{< highlight html >}}
rock paper scissors
rock paper scissors
rock paper scissors
{{< /highlight >}}

And you want to replace the word `rock` with `lizard` just in the lines one and
three (don't ask me why). Normally I would do something like:

`1s/rock/lizard/ | 3s/rock/lizard`

But there is a shortcut, the `&` command:

`1s/rock/lizard/ | 3&`

The `&` command only repeats the last search and replace *without* flags though.
To keep the flags you need to use the `&` command with the (guess what?) `&` flag.
If we had a flag in the last example it would become something like:

`1s/rock/lizard/i | 3&&`
