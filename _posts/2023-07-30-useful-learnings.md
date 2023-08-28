---
title: Useful Learnings
author: mbeals
date: 2023-07-30 13:00:00 -0700
categories: [Blogging, First]
tags: [helloworld]
pin: true
math: true
mermaid: true
---

This post is a running list of useful commands, tips, and tricks I've learnt as I've been progressing through the [Practical Deep Learning for Coders](https://course.fast.ai/) course by fastai. This is good practice for me as I learn:
- Markdown syntax rendering from cotes' Chirpy Docs page [**Text and Typography**](https://chirpy.cotes.page/posts/text-and-typography/).
- Python commands from reading [**Python For Data Analysis**](https://wesmckinney.com/book/).

## Bash Commands

**To launch a local server to test the Jekyll website** 

Navigate to the website root folder and type in ubuntu temrinal:
```bash
bundle exec jekyll s
```

- `sudo` (super user do) gives you root privileges to excecute restricted commands
- `cat` (concatenate) prints the outputs of a file to the terminal
  - `cat /etc/passwd` lists out all users in the system
- `bin` (binary) contains all the basic linux functions one may want to use
  - 2 bins exist: `/bin` and `/usr/bin`
- `sbin` (super binary) contains superuser commands
- `which` tells you the source file location of the command you're trying to use
- `apt` (advanced package tool) helps you install packages to debian-based linux environment
- `pip` is package installer specifically for python packages
- `mamba install` is the preferred method for installation when using mamba (do not use `conda`)

## Jupyter Notebooks Commands

- `?` before or after any function/variable gives the docstring
- `?` after a statement including wildcards `*` will show all names matching the expression
- `??` in front of any function gives the source code
- `doc()` provides link to documentation for that function (maybe wrong)
- when inside the parentheses of a function, click `SHIFT` + `TAB` to get the docstring (press more times for more info)
- `%` magic symbol runs terminal commands
- `%debug` runs the python debugger
- `%run` does something (not sure what yet)
- `TAB` after any function/object will display the methods available. To see magic and internal private methods, type `_` then `T
- EVERYTHING in python is an object with a specific type

## General Notes

### Encoding

There are several ways to encode characters into bits. [ASCII](https://en.wikipedia.org/wiki/ASCII) was a 7-bit encoding devleoped in the 1960's that encoded 128 different characters
- Numbers 0-31 were reserved for control functions for things like printers and meta information (think carriage return, escape, etc)
- Numbers 32-127 were resevered for the printable characters (think what's on your keyboard that you type with)
- Number 128 was reserved for the non-printable DEL character

The problem with ASCII was that it had no support for other languages or symbols; it fully maxed out its 128 combinations. But it was very space efficient by fitting in just 7 bits. UTF-32 came along in the early 2000's and used 32 bits to encode over 4 million different graphemes (the smallest meaningful unit in a writing language), but it is very space inefficient since every grapheme now requires 4 bytes. UTF-8 addresses this by using variable sizing for different graphemes. The more commonly used graphemes (e.g. ASCII) use less bytes than less commonly used ones, which if great for space efficiency, but the downside is that there is no longer a uniform relationship between the length of a string and the number of bytes. For more details, see [this great video](https://www.youtube.com/watch?v=ut74oHojxqo) by Studying With Alex.
