---
title: "Week 10: The Final Rounds: User Formats!"
categories: gsoc
---

Hi everyone,

This is the 10th blog of my GSoC series and I'm happy to mention that I'm almost done with all the user formats supported by `git log`.

I can simply divide my work on user formats in 3 categories:
- Used ref-filter's logic.
- Add support for that user format in ref-filter and then used ref-filter's logic.
- keep using pretty.c logic

Lets talk about all of these one by one.

#### 1) Used ref-filter's logic

Some user formats supported by pretty are directly available in ref-filter. 

For ex: 
- `%h` can be replaced by `%(objectname:short)`
- `%P` can be replaced by `%(parent)`

Without a second thought, its better to use ref-filter's logic for such formatting options.

#### 2) Add support for that user format in ref-filter and then used ref-filter's logic.

Some user formats supported by pretty are not available in ref-filter. But some relevant formatting options are present.
(Also these type of formatting options are nice addition to ref-filter.)

For ex:
- Take a look at `%p` in pretty.c that prints abbrev parent hash.
ref-filter supports `%(parent)` that prints parent hash (not abbrev parent hash). So, in this situation its better to add support for abbrev parent hash in ref-filter and then use ref-filter's logic for `%p`

#### 3) keep using pretty.c logic

There exists some formatting options that makes no sense to ref-filter or are not useful to ref-filter. So its better to not to add them to ref-filter.
(Another reason for that is there is no duplicacy. As my main aim is to reduce duplicate logic.)

For ex: 
- reflog related formatting options.
- formatting options like `%m` and `%w([<w>[,<i1>[,<i2>]]])`.

## What's Next

I will work comments I recieved on some commits by my mentors. Also I will work more on commit messages, because good commit message make reviewing process easy.

Apart from that 2 user formats are still left (`%GT` and `%G?`). I'm having hard time making them work.

Working on `--graph` is on my list for quite a long time. Will work on this too if time permits.
