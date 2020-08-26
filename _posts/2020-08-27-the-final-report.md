---
title: "The Final Report"
categories: gsoc
---

Hi everyone,

Finally, the time has come, to sum up all my work so far into a single blog post. Without wasting any time, let's get started.

## PROJECT

In short, my project is to simplify the codebase by removing duplicate logic. The task is to re-use ref-filter.{c,h}'s logic in pretty.{c,h}.

**Note**: You can check out my proposal [here](https://github.com/harry-hov/GSoC-Proposal-git/blob/master/%5BGSoC%5D%20Git%20Proposal.pdf).

## WHEN I MET GIT?

I was planning to contribute in git since Aug'19. And I made my first contribution to git via [gitgitgadget](https://gitgitgadget.github.io/) in Oct'19. At that time I was mentored by dscho(aka Johannes). I continued to contribute even since then and managed to get some of my patches merged.

## PRE-GSOC

Here's the list of patches I worked on before GSoC. 

- [t2402: test worktree path when called in .git directory](https://github.com/git/git/commit/4d864895a23bbbb5403d9aa8a65d0576d2029597)

- [receive.denyCurrentBranch: respect all worktrees](https://github.com/git/git/commit/4ef346482d6d5748861c1aa9d56712e847369b40)

- [t5509: use a bare repository for test push target](https://github.com/git/git/commit/f8692114dbb1b3ffe0b71871a015c632c195b784)

- [get_main_worktree(): allow it to be called in the Git directory](https://github.com/git/git/commit/45f274fbb118cc4cb00640c30b4e3069d96755a0)

- [git-compat-util.h: drop the `PRIuMAX` and other fallback definitions](https://github.com/git/git/commit/e547e5a89e3641bae02e762bcb0062951bb698e5)

- [builtin/blame.c: constants into bit shift format](https://github.com/git/git/commit/86795774bb9ca3c63b94d3d0930405c1ba9148ec)

Note: These patches was considered as my micro-project.


