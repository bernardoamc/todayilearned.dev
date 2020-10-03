---
author: "Bernardo"
title: "ruby-one-liners"
date: 2020-10-03T15:20:00-04:00
tags: ["ruby"]
---

TIL about the [Ruby one-liners cookbook](https://learnbyexample.github.io/learn_ruby_oneliners/preface.html).

It has tons of interesting examples about how to achieve things in Ruby that we
would previously rely on `awk` or `sed` to tackle.

A small example of what you will find there:

{{< highlight bash >}}
$ ruby -rset -ane 'BEGIN{s=Set.new}; (s.add($F[0]); next) if ARGV.size==1;
                   print if s.include?($F[0])' dept.txt marks.txt
{{< /highlight >}}
