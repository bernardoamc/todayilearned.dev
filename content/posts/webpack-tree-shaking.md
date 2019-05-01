---
author: "Bernardo"
title: "webpack tree shaking"
date: 2019-05-01T18:50:00-04:00
tags: ["javascript"]
---

TIL about [tree shaking](https://developers.google.com/web/fundamentals/performance/optimizing-javascript/tree-shaking/)
in [webpack](https://webpack.js.org/guides/tree-shaking/) as a way to eliminate
dead code.

The way this is accomplished is by using the `sideEffects` package.json property.

{{< highlight javascript >}}
{
  "name": "your-project",
  "sideEffects": false
}
{{< /highlight >}}

`"sideEffects": false` in this context means that our code doesn't have
special behaviour when imported other than exposing one or more exports.
If that's not the case we can whitelist these special files:

{{< highlight javascript >}}
{
  "name": "your-project",
  "sideEffects": [
    "./src/file-with-side-effect.js"
  ]
}
{{< /highlight >}}

For more options [refer to the documentation](https://webpack.js.org/guides/tree-shaking/#mark-the-file-as-side-effect-free).
