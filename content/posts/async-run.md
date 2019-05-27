---
author: "Bernardo"
title: "async run"
date: 2019-05-27T19:00:10-04:00
tags: ["vim"]
---

TIL about [async run](https://github.com/skywind3000/asyncrun.vim) to run shell
commands asynchronously in Vim 8 or NeoVim. The output of the shell command can
be read in real time using the `quickfix` window. Let's see an example:

{{< highlight vim >}}
" Running the command asynchronously
:AsyncRun git push origin master

" Opening the quickfix window
:copen
{{< /highlight >}}

An interesting option is to set `g:asyncrun_open` with a value like `8` to open
the `quickfix` window automatically with a certain height when an asynchronous
command is running.
