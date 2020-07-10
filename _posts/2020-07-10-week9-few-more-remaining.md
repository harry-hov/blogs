---
title: "Week 9: Few more remaining!"
categories: gsoc
---

Hi everyone,

In this blog, I would like to mention all the formatting option that are implemented or yet to be implemented. 

- Formatting options implemented and pushed to Github

```
%n	:	newline
%%	:	a raw %
%Cred	:	switch color to red
%Cgreen	:	switch color to green
%Cblue	:	switch color to blue
%Creset	:	reset color
%C(...)	:	color with auto/always option
%H	:	commit hash
%h	:	abbreviated commit hash
%T	:	tree hash
%t	:	abbreviated tree hash
%P	:	parent hashes
%p	:	abbreviated parent hashes
%an	:	author name
%ae	:	author email
%al	:	author email local-part (the part before the @ sign)
%ad	:	author date
%aD	:	author date, RFC2822 style
%ar	:	author date, relative
%at	:	author date, UNIX timestamp
%ai	:	author date, ISO 8601-like format
%aI	:	author date, strict ISO 8601 format
%as	:	author date, short format (YYYY-MM-DD)
%cn	:	committer name
%ce	:	committer email
%cl	:	author email local-part (the part before the @ sign)
%cd	:	committer date
%cD	:	committer date, RFC2822 style
%cr	:	committer date, relative
%ct	:	committer date, UNIX timestamp
%ci	:	committer date, ISO 8601-like format
%cI	:	committer date, strict ISO 8601 format
%cs	:	committer date, short format (YYYY-MM-DD)
%d	:	ref names, like the --decorate option of git-log
%D	:	ref names without the " (", ")" wrapping.
%s	:	subject
%f	:	sanitized subject line, suitable for a filename
%b	:	body
%B	:	raw body (unwrapped subject and body)
```

- Formatting options implemented locally and yet to be pushed.

```
%GG	:	raw verification message from GPG for a signed commit
%GS	:	show the name of the signer for a signed commit
%GK	:	show the key used to sign a signed commit
%GP	:	show the fingerprint of the primary key whose subkey was used to sign a signed commit
%GF	:	show the fingerprint of the key used to sign a signed commit
%(trailers[:options]) : "only[=val]", "unfold[=val]" and "valueonly[=val]" are implemented.
```

- Formatting options in progress.

```
%GT	:	show the trust level for the key used to sign a signed commit
%G?	:	show quality of signature, eg 'G' for Good, 'B' for Bad
%gD	:       reflog selector, e.g., refs/stash@{1}
%gd     :       shortened reflog selector;
%gn     :	reflog identity name
%ge	:       reflog identity email
%gs	:       reflog subject
%(trailers[:options]) : "key=<K>" and "separator=<SEP>" are in progress.
```

- Formatting options, I haven't started working on.

```
%gN     :	reflog identity name (respecting .mailmap,)
%gE	:       reflog identity email (respecting .mailmap)
%cL	:       committer local-part (respecting .mailmap)
%cE	:       committer email (respecting .mailmap)
%cN	:       committer name (respecting .mailmap)
%aL	:       author local-part (respecting .mailmap)
%aE	:       author email (respecting .mailmap)
%aN	:       author name (respecting .mailmap)
%N	:       commit notes
%e	:       encoding
%x00	:       print a byte from a hex code
```

*Note: Tests are yet to be performed on all the formatting options.

If everything goes fine, by the end of next week all formatting options will get implemented.


