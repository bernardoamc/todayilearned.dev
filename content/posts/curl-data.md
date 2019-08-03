---
author: "Bernardo"
title: "curl data"
date: 2019-08-02T22:00:00-04:00
tags: ["bash"]
---

TIL that `curl --data` and `curl --data-binary` when used with a `@filename`
outputs a different result. The most common one being that `--data` will
strip newlines from the file but `--data-binary` will not.
