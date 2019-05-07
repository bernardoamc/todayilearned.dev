---
author: "Bernardo"
title: "hash-deep-merge"
date: 2019-05-07T12:50:45-04:00
tags: ["ruby"]
---

TIL that `Hash#deep_merge` accepts a block in which you can specify how values
from the same `key` should be merged:

{{< highlight ruby >}}
h1 = { a: { b: 1 }, c: 2}
h2 = { a: { d: 3 }, c: 4}

h1.deep_merge(h2)
# => { a: { b: 1, d: 3 }, c: 4 }

h1.deep_merge(h2) { |k, v1, v2| v1 + v2 }
# => { a: { b: 1, d: 3 }, c: 6 }
{{< /highlight >}}
