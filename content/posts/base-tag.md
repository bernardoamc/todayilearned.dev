---
author: "Bernardo"
title: "base tag"
date: 2019-04-08T12:45:00-04:00
tags: ["html"]
---

TIL about the [base](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/base) HTML tag.
It specifies the base URL to be used for all relative URLs within a document.

{{< highlight html >}}
<base href="http://www.example.com/">

<!-- Refers to: http://www.example.com/#relative -->
<a href="#relative">Relative</a>
{{< /highlight >}}

It is supported by all major browsers.
