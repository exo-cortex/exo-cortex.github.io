---
title: "sed_basics"
date: 2021-10-30T12:09:13+02:00
draft: false
tags: [bash, linux, commandline, sed]
---

# what is sed?

sed is a "stream editor" in the commandline. It can do a lot of things and I wrote down some basics examples here (to avoid re-googling them in a few months). A great and very thorough guide can be found elsewhere [0]. I only post the most useful examples that I needed so far.

sed typically works by reading an input string, looks for patterns and does something with these patterns. See this basic example:
```bash
# replace "a " with "not a "
$ echo "this is a sentence." | sed 's/a /not a /'
```
The echo command prints "this is a sentence." and pipes the result (with the "|"-character) to sed which replaces "a " with "not a ". Usually the sed command is followed by 's/PATTERN/REPLACEMENT/'.

## typical usecases

### numbers and letters

```bash
# replace a single instance of "number" with the letter "a_":
$ echo "012345679" | sed 's/[0-9]/a_/'
a_123456789

# replace a pattern that consists of 0-n instances of "number" with the letter "a_":
$ echo "012345679" | sed 's/[0-9]*/a_/'
a_
```

the same works for letters:

```bash
$ echo "abcdefghijklmnopqrstuvwxyz" | sed 's/[a-z]/A_/'
A_bcdefghijklmnopqrstuvwxyz

$ echo "012345679" | sed 's/[a-z]*/A_/'
A_
```

### matching and replacing a pattern multiple times 

```bash
# replace each occurrence of "b" with "B" 
$ echo "abababa" | sed 's/b/B/g'
aBaBaBa
```

### using the matched pattern again

The character "**&**" represents the matched pattern.
```bash
# find "b" and replace it with " bb " by doubling the pattern
$ echo "abababa" | sed 's/b*/ && /'
a bb ababa

# do that for each ocurrence of "b"
$ echo "abababa" | sed 's/b*/ && /g'
a bb a bb a bb a
```

### using multiple sed-commands after each other
instead of piping one results from sed to another instance of sed (and so on) sed can match multiple patterns.
```bash
# first: replace first instance of a letter with "a_"
# then: replace first instance of a letter with "firstletter"
echo "abcdefghijklmnopqrstuvwxyz" | sed 's/[a-z]/a_/ ; s/[a-z]/firstletter/'
```

Links:

[0] [sed tutorial](https://www.grymoire.com/Unix/Sed.html)
