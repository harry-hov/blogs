---
title: "Week 1: The Ten Questions: All or Nothing!"
categories: gsoc
---

Hi everyone,

This week, I continued my quest to learn more about Olga's work, but I kind of struggled a little. So I approached my mentors. Christian helped me in understanding Olga's work in a better way. He put some up some questions for me. Those questions are really helpful. 
Regardless of the project, those questions will help anyone who wants to understand someone's work.
So, it's a good idea to mention those in this blog(might help someone in future).[Hope he does not mind]

[*Dont* Hold your breath] Here are those:

- What was the goal of each patch?
- Which approach did she took to achieve the goal?
- What were the goals of the patch series?
- Which approach did she took to achieve the goals?
- What was the goal of her previous patch series?
- What was the general direction her patch series were going?
- Why did she took that direction?
- Are there ways to continue in the same direction?
- Are there ways to achieve similar goals?
- How were her goals similar and different from the goals in my proposal?
- Is it possible to use the same approach?

---
---

Even after going through Olga's patches, I wasn't able to come up with the proper approach to unifying  `ref-filter` and `pretty` formatting logic. I dont think i can proceed forward Olga's way. 

`pretty` and `ref-filter` uses totally different structures. Possible way I can think of is keep using both structures and make transition table between them. I'm not sure about this.(In fact, any suggestion will be highly appreciated.)

## Whats next?

"A good approach often comes from studying things, from trials and
errors, and from discussions with other people" -  Christian
{:.info-box}

So, now I'm going to deep-diving into `pretty.c` and `ref-filter.c` formats.
Also, will add support for atoms in `pretty.c`.

Summary: This week no patches, but it's full of learning.

**Note** - I dont want my weekly blog sounds like personal notes. So, I keep it less technical as much as possible. I'm thinking about writing another blog series about my findings related to my GSoC project. Those will be more on technical side.
bye... cya!
