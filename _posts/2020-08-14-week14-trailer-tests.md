---
title: "Week 14: Trailers"
categories: gsoc
---

Hi everyone,

For me, this week is all about trailers. I worked on a patch series focus of `trailers` atom for ref-filter. Now, trailers atom support 3 new options: `valueonly`, `separator`, and `key`. I also worked on the test script for trailers i.e `t6300` and got rid of some of the duplicate code.

Also made some minor improvements to the patch series that I sent last week to the mailing list. Added test (suggested by Junio) to check if new email options i.e. `trim` and `localpart` working per email atom. Also improved the `sanitize` option to work both ways:
`%(subject:sanitize)` & `%(contents:subject:sanitize)`.

## What's Next?

I still got to work on `grep` feature for pretty-lib.c that is using ref-filters logic. Maybe I'll continue that work.
