---
author: "Bernardo"
title: "bsearch"
date: 2019-05-15T08:00:45-04:00
tags: ["ruby"]
---

TIL that we have a builtin `bsearch` in the `Array` class. It's common for
Rubyists to default to `find`, but as we know `bsearch` performs
much better when we have a sorted `Array`.

Let's see an example:

{{< highlight ruby >}}
ary = [0, 4, 7, 10, 12]
ary.bsearch {|x| x >= 4 } #=> 4
ary.bsearch {|x| x >=  -1 } #=> 0
{{< /highlight >}}

We can also use it to search `String` objects, but in this case we need
to use the `<=>` operator in order to return `-1`, `0` or `1`.
[Here](https://stackoverflow.com/questions/827649/what-is-the-ruby-spaceship-operator) is an explanation
of the specifics of this operator.

{{< highlight ruby >}}
options = ['Deleted', 'Draft', 'In Review', 'Published', 'Unpublished']
options.bsearch { |option| 'Draft' <=> option }  #=> 'Draft'
options.bsearch { |option| 'Random' <=> option } #=> nil
{{< /highlight >}}

Notice that the term being compared must be on the left side.
