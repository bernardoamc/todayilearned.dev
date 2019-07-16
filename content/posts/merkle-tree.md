---
author: "Bernardo"
title: "merkle tree"
date: 2019-07-15T09:00:10-04:00
tags: ["data-structure", "cryptography"]
---

TIL about the [merkle tree](https://en.wikipedia.org/wiki/Merkle_tree) data
structure, a tree structure in which each leaf node is a hash of a block of
data, and each non-leaf node is a hash of its children.

{{< highlight text >}}
Label              ROOT
Value           H(H01 + H23)
                 /        \
Label       [H01]         [H23]
Value    H(H0 + H1)     H(H2 + H3)
           /     \        /     \
Label    [H0]   [H1]    [H2]   [H3]
Value    H(A)   H(B)    H(C)   H(D)
           |      |       |      |
           A      B       C      D
{{< /highlight >}}

It's mostly used in `distributed systems` for efficient `data verification` since it
only depends on hashes instead of full files. Bitcoin and Ethereum makes full
use of this data structure with variations like the [Merkle Patricia
Tree](https://github.com/ethereum/wiki/wiki/Patricia-Tree).
