---
author: "Bernardo"
title: "open-uri"
date: 2019-03-30T12:50:45-04:00
tags: ["ruby","security"]
---

TIL `open-uri` internally patches `Kernel.open` allowing remote code execution and reading local files.
If the string provided to `open-uri` starts with a pipe it will get executed as
a command:

{{< highlight ruby >}}
require "open-uri"
irb(main):001:0> require 'open-uri'
=> true
irb(main):002:0> open('|ls').to_a
=> ["content\n", "data\n", "layouts\n", "resources\n"]
{{< /highlight >}}

For more information check [this resource](https://sakurity.com/blog/2015/02/28/openuri.html).
