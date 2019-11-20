---
author: "Bernardo"
title: "rust closures"
date: 2019-11-20T00:55:35-04:00
tags: ["rust"]
---

TIL that `Rust` closures creates an anonymous struct in order to represent their
environment. As an example:

{{< highlight rust >}}
let a = 42;
let b = 100;
let f = |v: i32| v + a + b;
{{< /highlight >}}

would be represented as something like:

{{< highlight rust >}}
struct __anonymous_e3b0105<'a> {
    a: &'a i32,
    b: &'a i32,
}
{{< /highlight >}}
