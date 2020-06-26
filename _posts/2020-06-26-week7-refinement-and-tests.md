---
title: "Week 7: Refinement and Tests!"
categories: gsoc
---

## Previous week

The past week isn't that productive for me. But I still managed to work on a few things. Without wasting any time, let's take a look:

- Added color-related formatting options and `m`, `d`, `D` straight forward from pretty.c to pretty-lib.c
- Added new atom `signature` in ref-filter with `grade`, `signer`, `key`, `fingerprint`, `primarykeyfingerprint`, `trustlevel` as arguments.
- Added signature related formatting options in pretty-lib.c using ref-filter

Note: Signature realted formatting options are not yet in final shape. You can take a look at commits here: https://github.com/harry-hov/git/commits/signature?author=harry-hov

## What's next?

This week I think I can possibly divide my tasks in 3 categories:

1. Refinement: 
    - Add support for `--date` in 'author date' and 'committer date'
    - Make author and committer email respect `.mailmap`
    - Improve signature related formatting options.
    - Figure out why `--graph` in not working properly.
    - Improve/Reduce the code in pretty-lib.
  
2. Documentation
    - Add documention for newly added atoms in `ref-filter`.
  
3. Tests:
    - Make sure that tests related to existing formatting options in pretty-lib pass successfully.
    - Add tests for newly added atoms in ref-filter.

And yeah, very first evaluation of GSoC 2020 coming this week. Fingers Crossed. Hope for the best.
