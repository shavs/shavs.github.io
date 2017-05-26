---
layout: post
title: "Why Bash is Escaping Variables"
date: 2017-05-26 11:30:27 +0100
categories: bash terminal guide
---

## Introduction and Issue

On my laptop, I've experimented with replacing [Oh My Zsh]() with [Bash](), and a heavily customised environment.

During this experimentation, I've noticed that using `$HOME`, e.g.:

```bash

$ cd $HOME/Documents/

``` 

That it would escape the variable instead, rather than expanding the variable or simply using the variable as-is.
For example:

```bash

$ cd $HOME/Documents/

<TAB>

Output of the <TAB> is shown.

$ cd \$HOME/Documents

```

Trying to use `<TAB>` again results in the directory not being found.


## Solution

In order to avoid this, using the command:

```bash

shopt -s direxpand

```

will expand the directory properly. I have never encountered this before, so I thought it was worth writing down.

More on [shopt](https://www.gnu.org/software/bash/manual/html_node/The-Shopt-Builtin.html) can be found here.
