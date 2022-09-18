---
layout: post
title:  "Linux tools for 2022"
date:   2022-01-15 12:00:00 +0800
categories: [linux]
tags: [tooling, shell, utilities]
excerpt_separator: <!--more-->
---

Some cools tools found here and there...

<!--more-->

# Terminal!
* **kitty** :  A modern, hackable, featureful, OpenGL-based terminal emulator
    * **icat** : *alias of* `kitty +kitten icat`
* **chafa** : Image-to-text converter supporting a wide range of symbols and palettes, transparency, animations, etc.

# screens
## Better top
* **bpytop** : Resource monitor that shows usage and stats for processor, memory, disks, network and processes
* **btop** : Resource monitor that shows usage and stats for processor, memory, disks, network and processes

Also: glances, btm *?*

## Cool navigation:
* **lf** : A terminal file manager inspred by ranger written in Go
* **broot** : Fuzzy Search + tree + cd
* **ranger** : Simple, vim-like file manager
* **nnn** : The fastest terminal file manager ever written.

# Shell
## [Xonsh](/xonsh)

# Superseding standard commands:
## ls
* **lsd** Modern ls with a lot of pretty colors and awesome icons
 * **bat** Cat clone with syntax highlighting and git integration

## find
* **fd** : Simple, fast and user-friendly alternative to find
* **rg (ripgrep)** : A search tool that combines the usability of ag with the raw speed of grep
* **rga (ripgrep-all)** ripgrep, but also PDF, zip, ebooks, etc.

## du
* **ncdu** : Disk usage analyzer with an ncurses interface
   * Can navigate, delete, refresh, ...
 * **dust** : A more intuitive version of du in rust
   * "ncurse" synthetic display

## Git related

* **lazygit** : Simple terminal UI for git commands
* **tig** : Text-mode interface for Git.
* **gitui** : Blazing fast terminal-ui for git written in Rust
* **magit** : needs Emacs

## [Lazy Docker](/lazy-docker)
* **lazydocker** : A simple terminal UI for docker and docker-compose, written in Go with the gocui library.


# Other
Logs etc...:
* **lnav** : A curses-based tool for viewing and analyzing log files
* **jq** : Command-line JSON processor
* **croc** : file sharing (from terminal), exists also on Android

<!--
* **ff** : Simple, human-readable, fast binary file scanner
-->

# progress bar
When no progress bar is integrated in the tool:
* **pv** : like in ` cat ... | pv | ...`

```
└─> cat 'What type of Rabbit can swim.mp4' | pv -s 1500k > /dev/null    ☺
1.48MiB 0:00:00 [14.8MiB/s] [=====================================>] 101% 
```


# Some sources

* [A list of new(ish) command line tools (jvns.ca)](https://jvns.ca/blog/2022/04/12/a-list-of-new-ish--command-line-tools/)

<!--

https://news.ycombinator.com/item?id=31009313

linear-gradient(180deg, #e3e1e0, rgba(227, 225, 224, 0))

background-image: linear-gradient(rgb(227, 225, 224), rgba(227, 225, 224, 0));
box-sizing: border-box;
color: rgb(71, 48, 48);
font-family: -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial, "Noto Sans", "Liberation Sans", sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
font-size: 24px;
font-weight: 400;
line-height: 24px;
margin-bottom: 0px;
margin-left: 0px;
margin-right: 0px;
margin-top: 0px;
overflow-wrap: break-word;
padding-bottom: 24px;
padding-left: 24px;
padding-right: 24px;
padding-top: 0px;
text-align: start

-->
