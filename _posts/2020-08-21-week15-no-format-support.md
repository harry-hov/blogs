---
title: "Week 15: NO format-support.{c,h}"
categories: gsoc
---

Hi everyone,

It's about to over... yeah, I'm talking about GSoC. Final evaluations are few days away and none of the patches I worked on during GSoC are in the master yet. But two of the ref-filter focused patch series got positive response on the mailing list. Hopefully, they will get merged soon. I'm about to send another 'trailers' focused patch series to the mailing list soon. It will unify the 'trailers' logic from pretty and ref-filter.

In the last blog I talked about `--grep`, I checked that grep and some other log options are working fine for pretty-lib.c as they don't depend on pretty.c. But tests are still failing from some unknown reason.

## What next?

From the recent [Junio's review](https://public-inbox.org/git/xmqqlfid1305.fsf@gitster.c.googlers.com/) it seems like he is not much happy with new file format-support.{c,h}. So, I plan to refactor the whole pretty-lib series and will remove format-support.{c,h}. It is indeed a hectic task.

Also, I'm thinking of merging all of my work into a single branch. And will run test script on it. It will give a more clear picture of what is working as expected and what is not.
