---
author: "Bernardo"
title: "amdahl's law"
date: 2019-05-09T18:45:10-04:00
tags: ["computer-architecture"]
---

TIL about [Amdahl's Law](https://en.wikipedia.org/wiki/Amdahl%27s_law) as a way
to measure the result of a given optimization. It's especially useful to
compare different optimizations and see the maximum performance each
optimization provides for your system. Another cool thing is that
Amdahl's Law works for parallel or serial programs.

It has a few implications:

- Make the common case fast
- Optimizations wil have less and less effects (Law of diminishing returns)

Here's [an interesting video](https://www.youtube.com/watch?v=QutASUpGzbc) about it.
