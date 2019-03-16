---
author: "Bernardo"
title: "Intersection Observer API"
date: 2019-03-16T09:15:00-04:00
tags: ["javascript"]
---

TIL about the [Intersection Observer API](https://developer.mozilla.org/en-US/docs/Web/API/Intersection_Observer_API).
It allows us to asynchronously observe changes in the intersection of a target element with an ancestor element or with a top-level document's viewport.

Let's see a small example:

{{< highlight javascript >}}
// Create the observer and pass it a callback function.
// The callback will run whenever a threshold is crossed.
var options = {
  root: document.querySelector('#scrollArea'),
  rootMargin: '0px',
  threshold: 1.0
}

var observer = new IntersectionObserver(callback, options);

// Watch this element, please:
var target = document.querySelector('#listItem');
observer.observe(target);
{{< /highlight >}}

The linked page provides a much deeper explanation, but that's the gist of it!
