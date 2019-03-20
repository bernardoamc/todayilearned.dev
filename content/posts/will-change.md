---
author: "Bernardo"
title: "will change"
date: 2019-03-20T19:30:00-04:00
tags: ["css"]
---

TIL about the [will-change](https://developer.mozilla.org/en-US/docs/Web/CSS/will-change) CSS property.
It provides hints to browsers about how an element is
expected to change. Browsers may set up optimizations before an element is actually
changed.

{{< highlight css >}}
.sidebar {
  will-change: transform;
}
{{< /highlight >}}

_*This property should be used as a last resort, try to optimize before relying
on it._

For example, [avoid transitions with top/right/bottom/left
properties](https://medium.com/outsystems-experts/how-to-achieve-60-fps-animations-with-css3-db7b98610108)
as they force the browser to create layouts every time.
