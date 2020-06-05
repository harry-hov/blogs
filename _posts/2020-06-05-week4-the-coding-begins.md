---
title: "Week 4: The Coding Begins"
categories: gsoc
---

Hi everyone,

After many weeks spent on understanding the formatting logic. Now, it's time to get my hands dirty with code. 

I intend to re-write `pretty_print_commit()` using ref-filters logic (as suggested by my mentors). 

## What it does?
`pretty_print_commit()` is mainly responsible for formatting and printing commit messages (not commit hash) in predefined commit formats. 
Also, it is taking care of the user format options like %h, %an, etc.

## My Approach (might change later)

`git log` currently has 50+ placeholders for format options. 
I'm going to pick simpler ones, to begin with. 

Thinking of doing something like this:
```
static int get_format_option(const char *placeholder,
				struct ref_format format) 
{
	switch (placeholder[0]) {	
        case 'H':
            format.format = "%(objectname)";
            return 0;
        case 'h':		/* abbreviated commit hash */
            format.format = "%(objectname:short)";
            return 0;
        }
        return 0;
}
```

Will use this to set value of `format.format` and will later pass it into `verify_ref_format()`.

If everything goes right, will try to do this with more options.


 

 

