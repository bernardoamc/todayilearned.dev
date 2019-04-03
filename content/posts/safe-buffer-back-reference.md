---
author: "Bernardo"
title: "safe buffer back reference"
date: 2019-04-03T11:45:45-04:00
tags: ["ruby","rails"]
---

TIL `back references` for `sub, sub!, gsub, and gsub!` are finally [fixed](https://github.com/rails/rails/pull/34405) for
`ActiveSupport::SafeBuffer` through the use of `block.binding.eval`.

The behaviour being fixed is:

{{< highlight ruby >}}
"foo123".html_safe.sub(/([a-z]+)([0-9]+)/) {
  $2 + $1 #=> NoMethodError: undefined method `+' for nil:NilClass
}
{{< /highlight >}}

If this is confusing I recommend the following resource: [Bindings in Ruby – Behind the Magic of Blocks](https://blog.rebased.pl/2017/11/30/bindings-in-ruby-behind-the-magic-of-blocks.html)
