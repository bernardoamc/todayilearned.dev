---
author: "Bernardo"
title: "from-str"
date: 2019-10-19T22:20:45-04:00
tags: ["rust"]
---

TIL about the [FromStr](https://doc.rust-lang.org/std/str/trait.FromStr.html) trait in Rust
that is implicitly used through `str`'s `parse` method.

We could have a `struct` called `Period` that parses a string like: "10 days"
into `Period { value: 10, timeframe: "days" }`. The way to use it would be:

{{< highlight rust >}}
let period = "10 days".parse::<Period>();
{{< /highlight >}}
