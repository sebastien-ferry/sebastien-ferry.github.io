---
layout: post
title:  "github pages: ruby memo"
date:   2021-06-30 12:00:00 +0800
categories: [blog, linux, arch]
tags: [arch, ruby, github-pages]
excerpt_separator: <!--more-->
---

Because I forgot how to update this space...

<!--more-->

BTW, I use arch...

# Install Ruby + Jekyll

ArchLinux Forum » Newbie Corner » [Solved "bundle exec jekyll serve" crashes](https://bbs.archlinux.org/viewtopic.php?id=265534)

> Install ruby **2.7**
>
> **`sudo pacman -S ruby2.7`**

`cd /PATH/TO/YOUR/JEKYLL/PROJECT`

> Install **Jekyll**
>
> **`bundle-2.7 install`**

> Launch **Jekyll**:
>
> **`bundle-2.7 exec jekyll serve`**

# Also github


[Generating a new SSH key and adding it to the ssh-agent](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)

> Start the ssh-agent in the background.
> 
> `eval "$(ssh-agent -s)"`
>
> `Agent pid 59566`


> Add your SSH private key to the ssh-agent.
>
> `ssh-add ~/.ssh/id_ed25519`

## ssh-agent output
> SSH_AUTH_SOCK=/tmp/ssh-XXXXXXOJAapU/agent.27281; export SSH_AUTH_SOCK;
> SSH_AGENT_PID=27282; export SSH_AGENT_PID;
> echo Agent pid 27282;

## fish
`eval (ssh-agent -c)`
> set SSH_AUTH_SOCK /tmp/ssh-XXXXXXOJAapU/agent.27281
>
>set SSH_AGENT_PID 27282

<!--
https://alpaca0984.github.io/2018/01/14/Using-ssh-agent-in-fish-shell/
-->
## Xonsh
...

# GitHub Flavored Markdown Spec

[https://github.github.com/gfm](https://github.github.com/gfm)

GitHub Flavored Markdown, often shortened as GFM, is the dialect of Markdown that is currently supported for user content 
