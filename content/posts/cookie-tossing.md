---
author: "Bernardo"
title: "Cookie Tossing"
date: 2019-10-02T12:30:00-04:00
tags: ["web"]
---

TIL about the term `cookie tossing`, an attack leverages the feature that
a subdomain can put a `key=value` pair in a cookie which can then also be read
by the domain above it. For example, `todayilearned.dev` doesn't know if this
`key` comes from it or from `cookie.todayilearned.dev`.

This becomes problematic when a website allows untrusted people to host subdomains
under its domain. They can then abuse this feature to write manipulated cookie
information.
