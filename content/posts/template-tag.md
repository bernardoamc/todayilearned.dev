---
author: "Bernardo"
title: "template tag"
date: 2019-04-01T09:00:00-04:00
tags: ["html", "javascript", "security"]
---

TIL about the
[template](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/template)
tag. It's used to hold client-side content that is not to be rendered when a page
is loaded but may subsequently be instantiated during runtime using JavaScript.

Let's see some client side input without the template tag:

{{< highlight javascript >}}
  let container = document.createElement('div');

  // This will trigger the alert
  container.innerHTML = "<img src=x onerror=alert(1)>"
{{< /highlight >}}

Now let's use the `<template>` tag:

{{< highlight javascript >}}
  let container = document.createElement('template');

  // Alert NOT triggered
  container.innerHTML = "<img src=x onerror=alert(1)>"
{{< /highlight >}}

We can access the content inside a `template` with `template.content` and change the
rendered HTML before actually inserting it on the page. There's a [great
video](https://www.youtube.com/watch?v=lG7U3fuNw3A) from `LiveOverflow`
explaining how this tag is used by Google and many others in order to prevent
`XSS` client-side and how a misconfiguration allowed `XSS` on Google Search.
