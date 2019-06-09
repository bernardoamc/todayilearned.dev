---
author: "Bernardo"
title: "async run"
date: 2019-06-08T22:45:10-04:00
tags: ["vim"]
---

TIL about [quickfix-reflector](https://github.com/stefandtw/quickfix-reflector.vim) to
make the quickfix window modifiable. I've been using it in conjunction with plugins
like `fzf.vim` and `async-run` that writes to the quickfix window, after that the
plugin makes commands like `:w` and `:x` reflect the action to every file listed
in the quickfix window. It's a great plugin to enable search and replace,
allowing things like replacing words through regular expressions across files
in a very convenient way.
