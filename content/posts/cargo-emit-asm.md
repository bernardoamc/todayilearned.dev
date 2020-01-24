---
author: "Bernardo"
title: "cargo-rustc-emit-asm"
date: 2020-01-23T21:54:02-04:00
tags: ["rust"]
---

TIL that we can get optimized assembly output from a Cargo project by running the
following command:

{{< highlight bash >}}
cargo rustc --release -- --emit asm
{{< /highlight >}}

This will output `x86` by default, but say we wanted the `intel` syntax?

{{< highlight bash >}}
cargo rustc -- --emit asm -C "llvm-args=-x86-asm-syntax=intel"
{{< /highlight >}}
