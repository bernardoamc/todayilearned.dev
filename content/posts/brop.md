---
author: "Bernardo"
title: "blind rop"
date: 2020-10-25T17:50:10-04:00
tags: ["buffer-overflow"]
---

TIL about [blind rop](http://www.scs.stanford.edu/brop/bittau-brop.pdf), a technique
to write buffer overflows against targets that restart after a crash. As
example, targets that fork and recovers when the child crashes.  Since the child
has the same memory layout as the parent the stack canary will be the same.

The idea here is that we can perform an operation similar to a blind SQLI with
our binary, overring one byte at each time until we find all the bytes that form
our canary. So suppose we have a layout like the one below with our canary being
`11 22 33 44`:

{{< highlight text >}}
+------------------------------+------------+
| A A A A A A A A A A A A A A A| 11 22 33 44|
+------------------------------+------------+
<-------- buffer -------------><---canary--->
{{< /highlight >}}

In order to figure out the right canary in a blind attack we would overflow up
to the first byte and start our investigation:

{{< highlight text >}}
+------------------------------+------------+
| A A A A A A A A A A A A A A A| 00 22 33 44| -> CRASH
+------------------------------+------------+
<-------- buffer -------------><---canary--->

+------------------------------+------------+
| A A A A A A A A A A A A A A A| 01 22 33 44| -> CRASH
+------------------------------+------------+
<-------- buffer -------------><---canary--->

+------------------------------+------------+
| A A A A A A A A A A A A A A A| 02 22 33 44| -> CRASH
+------------------------------+------------+
<-------- buffer -------------><---canary--->

...

+------------------------------+------------+
| A A A A A A A A A A A A A A A| 11 22 33 44| -> SUCCESS
+------------------------------+------------+
<-------- buffer -------------><---canary--->
{{< /highlight >}}

So we found that the first byte is `11`, after that we will move to the second
byte and repeat the algorithm until we find all the required bytes.

A small python scrip representing the algorithm on a 32 bit binary:

{{< highlight python >}}
def leak_canary_byte(canary_prefix):
    for i in range(256):
        p = 'A'* buffer_size_until_canary + canary_prefix + chr(i)
        # Send p to the binary and see if we get a crash or not
        # Return if a crash didn't happen
    return None


def leak_canary():
    canary = ""
    for i in range(4):
        b = leak_canary_byte(canary)
        if b is None:
            err("bail")
            exit(1)
        ok("Found canary[%d]=%.2x"%(i, ord(b)))
        canary += b
    return canary
{{< /highlight >}}
