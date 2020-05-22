---
title: "Week 2: What's the Difference?"
categories: gsoc
---

Hi everyone,

I started 2 weeks ago by studying Olga's work, but it didn't help me much. I dug into pretty.c and ref-filter.c, still wasn't able to find the right approach.

ref-filter is very well coded and is simple to understand. It simply uses atoms and there is parser function for almost every atom.

Here is the whole working of `git for-each-ref` in few lines:

```
filter_refs(...);
verify_ref_format(&format);
for (i = 0; i < maxcount; i++)
 show_ref_array_item(array.items[i], &format);
ref_array_clear(&array);
```
It is pretty straight.

---

On the other hand, working of `git log` is very dispersed. e.g

- initialization and other stuff is happening in log.c. [`cmd_log()`]
- correctness verification of commit format is happening in pretty.c [`get_commit_format()`]
- printing is done in log-tree.c [`show_log()`]

---

The stupidest thing I tried is re-writing cmd_log() from scratch in for-each-ref's way. I successfully implemented the "%h" using ref-filters logic.
Here is why it's bad:
- I can't implement every single functionality of `git log`
- Back-Compatibility
- Other features like `format patch` is also using pretty.c logic. So I cannot get rid of pretty formatting logic.
- Getting rid of duplicate code is the aim of my project. I cant see that happening with this approach.

---

## What's next

I'm almost familiar with `pretty.c`, `log.c`, `for-each-ref.c`, and `ref-filter.c`. I will spend time understanding log-tree.c[specially `show_log()` and `show_decoration()`] and will document `log-tree.h`.

Hopefully next week I come up with some good approach.

