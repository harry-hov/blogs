---
title: "Week 11: Working on Comments!"
categories: gsoc
---

Hi everyone,

Past week I worked on mailmap, signature atom, trailers and two log options i.e `--graph` and `--log-size`.

Lets take a look at status of each of these:

#### signature atom

Partially working. After some discussion with my mentors I'm still working on this.

#### trailers

Completed. Need to rebase and split some commits. 

I used `die()` in case of wrong trailer option. As my mentors said `die()`ing is more powerful then printing error. I might need to get rid of `die()`. 

#### `--graph` and `--log-size`

Completed and reviewed by mentors.

#### mailmap

Needs change. As suggested by my mentors I'm giving a thought to use `split_ident_line()` in ref-filter.c for getting [author/committers]name and email.

## What's Next?

I'll continue my work on these options and will continue sending branches for review to my mentors.

And I'll also make sure that by the time of writing my next blog they all gets completed.
