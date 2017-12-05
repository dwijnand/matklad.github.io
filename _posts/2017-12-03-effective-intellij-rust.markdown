---
layout: post
title:  "Effective IntelliJ Rust"
date:   2017-12-04 22:06:19 +0300
---

Hi! I'd like to share some tips & tricks about using IntelliJ based IDEs and
especially the [Rust plugin] efficiently. There's a lot of great stuff in 
IntelliJ platform, and generally things work out of the box, but there are
lots of small things you don't even realize you need. In this post, I try to
document features which work for my workflow, they may or may not work for you.


[Rust plugin]: https://github.com/intellij-rust/intellij-rust


# Quick Start


## Install IDE

First, install any IntelliJ based IDE, like IDEA, CLion or PyCharm. I will be 
using IntelliJ IDEA Community Edition, you can download it from 
[JetBrains' website][IDEA], or install it via operating system's package manager. 
Alternatively, you can use [Toolbox App] to conveniently manage different IDEs.

[IDEA]: https://www.jetbrains.com/idea/
[Toolbox App]: https://www.jetbrains.com/toolbox/app/


## A note on keymaps

In the post, I will be using default Linux/Windows keymap, the one for MacOS is
quite a bit different. Consult [the reference][keymap] to find the differences.
Note that on Linux, and especially on Ubuntu with default settings, a lot of IDE
shortcuts will conflict with window manager's shortcuts, so you might want to 
tweak your config.


[keymap]: https://resources.jetbrains.com/storage/products/intellij-idea/docs/IntelliJIDEA_ReferenceCard.pdf


## Install plugin

The single most important shortcut is <kbd>Ctrl+Shift+A</kbd>, **find action**.
Using it and typing "plugins" is a convenient way to install Rust plugin:

**VIDEO**


# Open a project

We will be using [Cargo] code base as a running example. I already have a cloned
Cargo repository on my hard drive, so I use **import project** to import it into
IDEA. The next time I can open the project straight away, without importing it
again.

[Cargo]: https://github.com/rust-lang/cargo


**VIDEO**


# Navigation


Code is much more often read then written, so efficient navigation is more
important  for IDEs then code completion or refactorings support, and IntelliJ
has awesome navigation facilities.


## Navigation across project 

The two most important actions for navigation are <kbd>Ctrl+N</kbd> **Goto
class** and <kbd>Ctrl+Alt+Shift+N</kbd> **Goto symbol**, which also support 
filtering by module name.

**VIDEO**

There's also <kbd>Ctrl+Shift+N</kbd> for navigation to file. Note that you can
filter by directory. If you want to find a directory and not a file, append `/` 
to the query.


## Editor tabs

Another vehicle for navigation is editor tabs: you can open several related 
files and then use mouse to select the tab you want. However, this is horribly
inefficient, so I recommend to disable tabs altogether:

**VIDEO**

It may be unusual at first, but you'll quickly learn the power of
<kbd>Ctrl+N</kbd>. Another useful shortcut to replace tabs is <kbd>Ctrl+E</kbd> 
**Recent Files**.

**VIDEO**


## Project structure

One of the most powerful ways to convey application architecture is to use a 
reasonable directory layout. To toggle the directory tree, there is 
<kbd>Alt+1</kbd> **Project Structure** shortcut. Traditionally, the tree is on
the left, but I don't find this very convenient, because closing and opening the
tree moves the code, and I have to comprimize between tree width and the most
convenient position of the code. Luckily, this is easy to fix by moving the tree
to the right.

**VIDEO**

There's a nice option, **Autoscroll from source**, which tracks current position
in project view. If you like it, you might want to install "Autoscroll save" 
plugin to make this option persistent.

**VIDEO**

Sometimes you end up with a bunch of tool windows open, but you want to get back
to the editor. To do so, I save the state with all tool windows closed as a 
default, and then use **Shift+F12** shortcut.

**VIDEO**


## Navigation withing a file

When a file does not fit into a single screen, it is useful to be able to find
out what large blocks are defined in a file and navigate between them. The best
tool here is <kbd>Alt+7</kbd> **Structure**. Note that it, like most of tree
controls in IntelliJ, has "speed search": tying a string narrows down the search:


**VIDEO**

Some other useful shortcuts are <kbd>Alt+Up/Down</kbd> to navigate between methods,
<kbd>Ctrl+Shift+M</kbd> to navigate to matching brace <kbd>Ctrl+M</kbd> to recenter
the editor.

**VIDEO**


## Navigation from the current context

There's a whole bunch of navigation actions available depending on the 
surrounding context. The fundamental one is <kbd>Ctrl+B</kbd>, **Go to definition**
(if the caret is on a reference such as an expression or a type name) **Find references**
(if the caret is already on the definition).

**VIDEO**

Another interesting one is <kbd>Ctrl+U</kbd> **Go to super method** which in Rust
brings you to the parent module or to the method definition. 

**VIDEO**

To quickly navigate between types/traits and implementations, there's <kbd>Ctrl+Alt+B</kbd> 
**Navigate to implementation**.


Sometimes, you don't need to change position and just want to lookup docs or
implementation. For such cases, <kbd>Ctrl+Q</kbd> **Quick Documentation** or 
<kbd>Ctrl+Shift+I</kbd> **Quick Definition** are ideal.


**VIDEO**


A super feature of IntelliJ is that context-dependent actions work everywhere. 
For example, you can peek a definition while looking for symbol by name:

**VIDEO**


# Editing code

* extend selection (for navigation)

* multiple selection (more on that later)

* string manipulation

* Surround with quotes

* Join lines

* if, let x = if completions, remove parentheses 

* eprintln!

* swap quotes

* balancing hashes

# Generating code

* extract variable

* postfix template

* implement members

* add impl/derive

* fill match arm

* fill fields

* tuple struct to brace struct

* rename

# Running code

* configuratino from context

* synerghy with nav to symbol

* Run cargo command action

* CLippy


# Advanced stuff

* Ace jump

* Emacs is great

* Vim is great

* Homerow computing

* Split editor sucks