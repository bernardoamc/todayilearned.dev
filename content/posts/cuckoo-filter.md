---
author: "Bernardo"
title: "cuckoo filter"
date: 2019-06-24T09:00:10-04:00
tags: ["algorithm"]
---

TIL about [cuckoo filter](https://en.wikipedia.org/wiki/Cuckoo_filter), a
similar algorithm to [bloom
filters](https://en.wikipedia.org/wiki/Bloom_filter). Both algorithms support
fast set membership testing, but `cuckoo filters` expand on this concept by
providing limited counting, deletion and a bounded false positive probability
while maintaining a similar space complexity.

`cuckoo filters` **do not** play nice with concurrency.
