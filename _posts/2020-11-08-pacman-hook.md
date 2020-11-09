---
layout: post
title:  "archlinux: pacman nugget"
date:   2020-11-08 12:35:28 +0800
categories: [blog, linux, arch]
tags: [arch, pacman, hook]
excerpt_separator: <!--more-->
---
BTW, I use arch.

pacman, no description

<!--more-->

/etc/pacman.d/hooks/ description-install.hook

    # Display description of packages installed / upgraded / removed
    [Trigger]
    Operation = Install
    
    Type = Package
    Target = *
    
    [Action]
    # for xargs:
    Depends = findutils
    Depends = expac
    Description = HOOK : Display full description of packages (install)
    When = PreTransaction
    # provide target name on stdin:
    NeedsTargets
    Exec = /usr/bin/xargs expac -S "      | %-10n:  %d"
