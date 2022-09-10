---
layout: post
title:  "ArchLinux: pacman hook (to see the description)"
date:   2020-11-08 12:35:28 +0800
categories: [linux]
tags: [arch, pacman, hook]
excerpt_separator: <!--more-->
---
**BTW, I use arch.** Here are 2 small snippets to hook pacman to provide the description of packages updated/removed (installed too).

It helps me check the description of packages updated.

<!--more-->

# Update or delete

/etc/pacman.d/hooks/ description-install.hook
```bash
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
```


# Update or delete

/etc/pacman.d/hooks/ description-update-remove.hook

```bash
# Display description of packages installed / upgraded / removed
[Trigger]
Operation = Upgrade
Operation = Remove

Type = Package
Target = *

[Action]
# for xargs:
Depends = findutils
Depends = expac
Description = HOOK : Display full description of packages (update/remove)
When = PreTransaction
# provide target name on stdin:
NeedsTargets
Exec = /usr/bin/xargs expac -Q "      | %-10n:  %d"
```
