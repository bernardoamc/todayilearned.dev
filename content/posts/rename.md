---
author: "Bernardo"
title: "rename"
date: 2019-03-24T16:25:10-04:00
tags: ["bash"]
---

TIL about the `rename` command utility. It allows us to rename files using a
Perl Common Regular Expression. Suppose we have the following files:

{{< highlight bash >}}
$ ls
temp1.txt	temp2.txt	temp3.txt
{{< /highlight >}}

Now we want to rename our files from `temp` to `final`, but are not really
sure how to craft our regular expression. In this case we can use the `-n` flag:

{{< highlight bash >}}
$ rename -n 's/temp/final/' *.txt
'temp1.txt' would be renamed to 'final1.txt'
'temp2.txt' would be renamed to 'final2.txt'
'temp3.txt' would be renamed to 'final3.txt'
{{< /highlight >}}

And when we are ready:

{{< highlight bash >}}
$ rename 's/temp/final/' *.txt
$ ls
final1.txt	final2.txt	final3.txt
{{< /highlight >}}

For MacOSX users `rename` can be installed through: `brew install rename`.
The `tldr` tool does a great job summarizing the common use cases, but as always `man
rename` explains the entire scope.
