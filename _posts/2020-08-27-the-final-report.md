---
title: "The Final Report"
categories: gsoc
---

Hi everyone,

Finally, the time has come, to sum up all my work so far into a single blog post. Without wasting any time, let's get started.

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

## PROJECT

**Title:** Unify ref-filter formats with other --pretty formats 

**Aim:** To simplify the codebase by removing duplicate logic. The task is to re-use ref-filter.{c,h}'s logic in pretty.{c,h}.

**Mentors:** Christian Couder, Heba Waly

Note - For more details, you can check out my proposal [here](https://github.com/harry-hov/GSoC-Proposal-git/blob/master/%5BGSoC%5D%20Git%20Proposal.pdf).

## PROGRESS

Almost all of the pretty formats are implemented. I'm only mentioning the list of formatting options those are using ref-filter's logic. 

```
%H	:	commit hash
%h	:	abbreviated commit hash
%T	:	tree hash
%t	:	abbreviated tree hash
%P	:	parent hashes
%p	:	abbreviated parent hashes
%an	:	author name
%aN	:	author name (respecting .mailmap)
%ae	:	author email
%aE	:	author email (respecting .mailmap)
%al	:	author email local-part (the part before the @ sign)
%aL	:	author local-part (respecting .mailmap)
%ad	:	author date
%aD	:	author date, RFC2822 style
%ar	:	author date, relative
%at	:	author date, UNIX timestamp
%ai	:	author date, ISO 8601-like format
%aI	:	author date, strict ISO 8601 format
%as	:	author date, short format (YYYY-MM-DD)
%cn	:	committer name
%cN	:	committer name (respecting .mailmap)
%ce	:	committer email
%cE	:	committer email (respecting .mailmap)
%cl	:	author email local-part (the part before the @ sign)
%cL	:	committer local-part (respecting .mailmap)
%cd	:	committer date
%cD	:	committer date, RFC2822 style
%cr	:	committer date, relative
%ct	:	committer date, UNIX timestamp
%ci	:	committer date, ISO 8601-like format
%cI	:	committer date, strict ISO 8601 format
%cs	:	committer date, short format (YYYY-MM-DD)
%s	:	subject
%f	:	sanitized subject line, suitable for a filename
%b	:	body
%B	:	raw body (unwrapped subject and body)
%(trailers[:options]) : "only[=val]", "unfold[=val]", "valueonly[=val]"l, "key=<K>" and "separator=<SEP>"
```

## WHATS LEFT?

Although we have implemented all the formatting options in the new file pretty-lib.{c,h}, but its still not perfect. Some issues needs work.

1) It doesnt handle incorrect formatting options.

2) EMAIL/MBOXED commit format needs work.

3) 30-40% tests in are failing.

I plan to keep on working on this even after GSoC ends. I tend to finish What i started.

## PATCHES

**Patch series sent to mailing list:**

#### [PATCH 0/8] Improvements to ref-filter
- ref-filter: support different email formats
- ref-filter: refactor `grab_objectname()`
- ref-filter: modify error messages in `grab_objectname()`
- ref-filter: rename `objectname` related functions and fields
- ref-filter: add `short` modifier to 'tree' atom
- ref-filter: add `short` modifier to 'parent' atom
- pretty: refactor `format_sanitized_subject()`
- ref-filter: add `sanitize` option for 'subject' atom

Link to patch series on mailing list: [https://public-inbox.org/git/pull.684.v4.git.1598046110.gitgitgadget@gmail.com/](https://public-inbox.org/git/pull.684.v4.git.1598046110.gitgitgadget@gmail.com/)

Status: Seen (not yet in master)

#### [PATCH 0/2] Fix trailers atom bug and improved tests
- t6300: unify %(trailers) and %(contents:trailers) tests
- ref-filter: 'contents:trailers' show error if `:` is missing

Link to patch series on mailing list: [https://public-inbox.org/git/pull.707.git.1597841551.gitgitgadget@gmail.com/](https://public-inbox.org/git/pull.707.git.1597841551.gitgitgadget@gmail.com/)

Status: Seen (not yet in master)

#### [PATCH 0/2] Unify trailers logic for pretty.{c,h} and ref-filter.{c,h}
- [pretty.c: refactor trailer logic to `format_set_trailers_options()](https://public-inbox.org/git/712ab9aacf240a02d808af6b6837e682b929493c.1598043976.git.gitgitgadget@gmail.com/)
- [ref-filter: using pretty.c logic for trailers](https://public-inbox.org/git/d491be5d10991189f7ec6ead739c1d1500e437a1.1598043976.git.gitgitgadget@gmail.com/)

Status: Reviewed by mentors

#### [PATCH 0/30] pretty use ref-filter's logic 
- pretty-lib: add 'raw' commit format
- pretty-lib: print indented commits
- pretty: rename and make some generic support functions public
- ref_format: change `need_color_reset_at_eol` to bit field
- pretty-lib: add support for `--log-size`
- pretty-lib: add support for `--graph`
- pretty-lib: add formatting option `%<` and `%>`
- pretty: make `parse_padding_placeholder()` public
- pretty-lib: add formatting option `%w`
- pretty: move line wrapping logic to new function
- pretty-lib: add formatting option `%S`
- pretty-lib: add formatting option `%e`
- pretty-lib: add formatting option `%N`
- pretty-lib: support options that expands to string literals
- pretty-lib: add reflog related formatting options
- pretty: move reflog formatting logic to new function
- pretty-lib: add `raw body` formatting option
- pretty-lib: add different date formats
- pretty-lib: add formatting option `m`, `d`, and `D`
- pretty-lib: add color related formatting options
- pretty: make `struct format_commit_context` public
- pretty.c: move color logic to `format_commit_color()`
- pretty-lib: add formatting option `f`
- pretty-lib: add formatting option `t` and `p`
- pretty-lib: add more formatting option
- pretty-lib: print commits using ref-filters logic
- ref_format: add option to skip `\n` at eol
- pretty: introduce `get_user_format()`
- revision: add `use_ref_filter` in struct rev_info
- builtin/log: new config log.useRefFilter

Link to commits: [https://github.com/harry-hov/git/commits/pretty-lib-2.0.2?author=harry-hov](https://github.com/harry-hov/git/commits/pretty-lib-2.0.2?author=harry-hov)

Status: Partially reviewed by mentors (not sent to mailing list)
