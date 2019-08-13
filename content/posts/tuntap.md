---
author: "Bernardo"
title: "rename"
date: 2019-08-12T20:35:10-04:00
tags: ["bash", "iterm"]
---

TIL about the `status bar` on iTerm2. It's pretty useful with a mix of builtin
components like `Current Directory` or `git state` and user defined variables or
functions. To access and configure the status bar go to `Preferences > Profiles > Session`.
Turn on `Status bar enabled` then click `Configure Status Bar`.

Again,
[scripting](https://www.iterm2.com/documentation-scripting-fundamentals.html)
plays a huge part in how useful the status bar is.

As an example:

{{< highlight bash >}}
# In ~/.bash_profile
function iterm2_print_user_vars() {
  iterm2_set_user_var rubyVersion $(ruby -v | awk '{ print $2 }')
}
{{< /highlight >}}

And the variable can be read inside a
`Custom Action > Configure Component > Configure Action` through `\(user.rubyVersion)`.
