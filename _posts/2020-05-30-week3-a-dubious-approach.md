---
title: "Week 3: A Dubious Approach!"
categories: gsoc
---

Hi everyone,

Its almost a month since I have been selected as GSoC Student by Git. I explored and tried various stuff within git source code to think of a particular approach for my project. 

Last week, I studied the flow of data within `git log` and `git for-each-ref`. 
I think, to start (re)using `ref-filter`'s functions, `pretty.c` must need to understand `ref-filter`'s atoms...
And to understand atoms, `pretty.c` must need to support `ref-filter`'s structures.

---

Here are the few structures used by `pretty.c`


[`cmt_fmt_map`](https://github.com/git/git/blob/1aa69c73577df21f5e37e47cc40cf44fc049121e/pretty.c#L17-L25)
- Cannot stop using this, but good candidate to make transition table 


[`pretty_print_context`](https://github.com/git/git/blob/1aa69c73577df21f5e37e47cc40cf44fc049121e/pretty.h#L26-L54)
- All pp_* functions depends on this. But I guess some fields can be ditched in favour of using ref-filter's [might need to modify pp_* functions too] 


[`userformat_want`](https://github.com/git/git/blob/1aa69c73577df21f5e37e47cc40cf44fc049121e/pretty.h#L62-L65)
- No equivalance present in ref-filter (Not even play much role in formatting logic)


---

## Whats next?

I guess, I'm going to focus more on structures.

I see many part of 'git log' are using `struct rev_info *revs` and funtions are filling values in `revs`.

Its time to introduce pretty.c to `struct ref_array`.
So, we can start filling values in `array.revs` instead of `revs`. 

```
struct ref_array {
	int nr, alloc;
	struct ref_array_item **items;
	struct rev_info *revs;
} array;
```
This might be a good start point.
