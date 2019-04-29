---
author: "Bernardo"
title: "ulids"
date: 2019-04-29T08:30:10-04:00
tags: ["data-structure"]
---

TIL about [ULID](https://github.com/ulid/spec), which stands for "Universally
Unique Lexicographically Sortable Identifier".  Like `UUID`, `ULID` have `128` bits
but are represented as a `26` character string, as opposed to `36`.

An `ULID` is composed of a timestamp + random sequence of bits:

```md
 01AN4Z07BY      79KA1307SR9X4MV3
|----------|    |----------------|
 Timestamp          Randomness
   48bits             80bits
```

It gives the system the possibility of sorting identifiers unlike `UUIDs`,
but still makes it difficult to guess an identifier and the amount of resources our system
has, which are two potential problems of using `sequential ids`.
