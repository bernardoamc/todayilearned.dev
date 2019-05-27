---
author: "Bernardo"
title: "rum index"
date: 2019-05-22T21:30:10-04:00
tags: ["databases", "postgres"]
---

TIL about the [RUM index](https://github.com/postgrespro/rum) extension in PostgreSQL.
It is a variant of the [GIN index](https://www.postgresql.org/docs/devel/gin-intro.html)
that stores additional information in the posting tree like lexemes position and
timestamps. This solves known `GIN` problems like slow ranking and phrase
searching.

The drawback of course is that this additional information incurs extra build
and insert time, making it not ideal for tables that change often.
