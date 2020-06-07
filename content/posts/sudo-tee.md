---
author: "Bernardo"
title: "sudo tee"
date: 2020-06-07T13:00:00-04:00
tags: ["bash"]
---

When we don't want to run a shell with sudo but still want to redirect output
to a location we don't have permission to access we can use the `sudo tee`
trick.

{{< highlight bash >}}
$ sudo cat /root/file | sudo tee /whatever/test.out > /dev/null
{{< /highlight >}}

The redirect to `/dev/null` is there to stop tee from outputting to the screen.

We have to use `sudo` with `tee` because a normal redirection performed by the
shell is running with our users permissions.

This could be further simplified with:


{{< highlight bash >}}
$ sudo cat /root/file | sudo dd of=/whatever/test.out
{{< /highlight >}}

`dd` is great to write large files (usually images to disks), but also works equally well with small ones.
