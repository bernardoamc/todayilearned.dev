---
author: "Bernardo"
title: "roaring bitmap"
date: 2019-04-13T19:50:10-04:00
tags: ["data-structure"]
---

TIL about [roaring bitmap](http://roaringbitmap.org), a hybrid data structure.

It's a data structure that is especially suited to compute the intersection,
union and the difference between sets. It uses different approaches depending on
how your data is distributed like uncompressed bitmaps or sorted arrays.

The way this is done is by dividing the data into chunks of 2^16 integers and
using a different strategy for each chunk depending on the data distribution.

An interesting detail is that by having these small chunks we can fit some of
them into the L1 CPU cache of most processors, granting extra performance to our
operations.
