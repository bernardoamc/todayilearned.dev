---
author: "Bernardo"
title: "prefers-color-scheme"
date: 2019-04-05T10:30:00-04:00
tags: ["css"]
---

TIL about the [prefers-color-scheme](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-color-scheme) CSS media feature.
It is used to detect if the user has requested the system use a light or dark color theme.

{{< highlight css >}}
@media (prefers-color-scheme: dark) {

}
{{< /highlight >}}

Right now it's a feature that is just supported by `Firefox` and `Safari`.
