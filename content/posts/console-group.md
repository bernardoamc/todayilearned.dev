---
author: "Bernardo"
title: "Console Group"
date: 2019-06-29T09:15:00-04:00
tags: ["javascript"]
---

TIL about the `console.group` command used to create a new inline group in the
[Web Console](https://developer.mozilla.org/en-US/docs/Tools/Web_Console) log.
It is used in order to create nesting in your console logs.

Let's see an example:

{{< highlight javascript >}}
console.log("This is the outer level");
console.group();
console.log("Level 2");
console.group();
console.log("Level 3");
console.warn("More of level 3");
console.groupEnd();
console.log("Back to level 2");
console.groupEnd();
console.log("Back to the outer level");
{{< /highlight >}}

The generated log will be the following:

{{< highlight javascript >}}
"This is the outer level"
  "Level 2"
    "Level 3"
    "More of level 3"
  "Back to level 2"
"Back to the outer level"
{{< /highlight >}}
