---
author: "Bernardo"
title: "power of two choices"
date: 2019-05-17T20:50:10-04:00
tags: ["algorithm"]
---

TIL about the [Power of Two Choices](https://www.eecs.harvard.edu/~michaelm/postscripts/tpds2001.pdf)
algorithm used in load balancing, queuing theory and distributed systems in
general.

The main takeaway is that it is better to pick two queues at random and
choose the one with the least amount of work than finding the best queue
and sending a workload there. Why? If we are dealing with many decision makers
(as in distributed load balancers for example) and each one choose the best
queue disregarding each other choices then all their choices will go to the
same queue, overwhelming it.

NGINX implements this algorithm for their load balancers for example, [check it
out](https://www.nginx.com/blog/nginx-power-of-two-choices-load-balancing-algorithm/)!
