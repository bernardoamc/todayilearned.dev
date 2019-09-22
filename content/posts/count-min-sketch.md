---
author: "Bernardo"
title: "count min sketch"
date: 2019-09-22T09:12:35-04:00
tags: ["algorithm"]
---

TIL about [Count-Min Sketch](https://en.wikipedia.org/wiki/Count%E2%80%93min_sketch), an algorithm used to answer questions like:

* What’s the frequency of our samples?
* What’s our most frequent samples?

Similar to [bloom filters](https://en.wikipedia.org/wiki/Bloom_filter), it uses `k` distinct hash functions. Every observed
value serves as an input for these functions and the output for each function
is a number corresponding to a bucket.After finding the buckets we just need
to increment a counter in each of these buckets.

In order to retrieve the frequency of an observed value we find the buckets for
this value and return the minimum counter among all the buckets: `min(bucket_x, bucket_y, bucket_z)`

A short version the paper can be found
[here](http://dimacs.rutgers.edu/~graham/pubs/papers/cmsoft.pdf).
