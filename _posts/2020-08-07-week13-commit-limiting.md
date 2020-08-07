---
title: "Week 13: Log Commit Limiting"
categories: gsoc
---

Hi everyone,

This week I submitted the second version of ref-filter improvement patch series. While this patch series is in review, I plan to prepare sequel to this ref-filter improvement patch that will be focused on `trailers` atom.

Apart from that, I plan to work on some commit limiting options of `git log` using ref-filter's logic. More specifically on `--grep=<pattern>`.
`git log` supports many commit limiting options, to know more about them [click here](https://git-scm.com/docs/git-log#_commit_limiting)

## Test Status

I run some log related tests using pretty-lib.c, around 30% of tests are failing. The main reason for test failing is log options that are not yet supported by pretty-lib. I'm learning about working of all those log option too.
