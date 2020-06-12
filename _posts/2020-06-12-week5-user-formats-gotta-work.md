---
title: "Week 5: User Formats - Gotta work!"
categories: gsoc
---

Hi everyone,

Past week, I worked on porting `pretty_print_commit()` to `ref_pretty_print_commit()`[prints using ref-filter's logic]. 
Lets take a glance at what's working and what's not.

#### What's working
- `git log` without any formating option. 
- Commit format options: `medium`, `oneline`, `short`, `full`, `fuller`
- User formats: `%h`, `%H`, `%T`

#### What's not working
- Other then above mentioned user formats, rest are not added yet. (e.g. `raw`, `%an`, `%t` etc)
- Only one user format is working at a time. 

    for eg: If we run `git log --pretty="%h %H"`
    
    It will only print first one i.e `%h`
    
## What's next?

Most probably this week I will add support for multiple user formats options. 

I got 2 approaches for that:

1. modify [`strbuf_expand()`](https://github.com/git/git/blob/master/strbuf.c#L407-L432)
2. Convert input string to ref-format's understandable form.

    e.g. If user enters "%h %an", convert it to "%(objectname) %(authorname)". And then pass it to printing funtion.
    
I'm not sure what I'll do. Maybe 1st or 2nd or some new 3rd one.
