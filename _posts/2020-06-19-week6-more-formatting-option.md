---
title: "Week 6: More on formatting options!"
categories: gsoc
---

## Previous week

- Sent a patch for review
- added few formatting options.

#### List of added formatting options till now

```
%n      :     newline
%%      :     a raw %
%H      :     commit hash
%h      :     abbreviated commit hash
%T      :     tree hash
%t      :     abbreviated tree hash
%P      :     parent hashes
%p      :     abbreviated parent hashes
%an     :     author name
%ae     :     author email
%ad     :     author date
%cn     :     committer name
%ce     :     committer email
%cd     :     committer date
%s      :     subject
%f      :     sanitized subject line
%b      :     body
```

Apart from that, I worked on adding color related formating options
e.g- `C<color>`, `C(<color>)`, including `auto` and `always`

I think its better to keep using current logic. Because both(`ref-filter` and `pretty`) are using `color.h`. They only have their own stripping logic.

e.g. ref-filter is pulling out `red` from `color:red`

pretty is pulling out `red` from `Cred` or `C(red)` or `C(auto, red)` or `C(always, red)`

I still need to discuss about that with my mentors before concluding anything.  

## Whats next?

I will work on adding more formatting option to the list(most probably signature related) alongside with color.

