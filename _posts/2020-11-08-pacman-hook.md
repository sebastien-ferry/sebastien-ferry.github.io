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

/etc/pacman.d/hooks/ **description-install.hook**

{% highlight linenos linenos %}
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
{% endhighlight %}


# Update or delete

/etc/pacman.d/hooks/ **description-update-remove.hook**

{% highlight linenos linenos %}
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
{% endhighlight %}

# Result!

```
Looking for conflicting packages...

Package (8)                      Old Version      New Version      Net Change  Download Size

community/gdu                    5.17.0-1         5.17.1-1           0.00 MiB       3.09 MiB
extra/libgusb                    0.3.10-2         0.4.0-1            0.05 MiB       0.08 MiB
community/libharu                2.4.1-1          2.4.2-1            0.00 MiB       0.56 MiB
community/libluv                 1.44.2_0-1       1.44.2_1-1         0.00 MiB       0.05 MiB
community/lilv                   0.24.18-1        0.24.20-1          0.00 MiB       0.08 MiB
community/python-traitlets       5.3.0-1          5.4.0-1            0.01 MiB       0.20 MiB
archlinuxcn/rstudio-desktop-bin  2022.07.1.548-1  2022.07.1.554-2    0.00 MiB     134.26 MiB
community/wallutils              5.11.1-1         5.12.2-1          18.41 MiB       7.45 MiB

Total Download Size:   145.77 MiB
...

(8/8) checking available disk space                                                                    [############################################################] 100%
:: Running pre-transaction hooks...
(1/1) HOOK : Display full description of packages (update/remove)
      | gdu       :  Fast disk usage analyzer
      | libgusb   :  GObject wrapper for libusb1
      | libharu   :  C library for generating PDF documents
      | libluv    :  Bare libuv bindings for lua
      | lilv      :  A C library interface to the LV2 plug-in standard
      | python-traitlets:  A configuration system for Python applications
      | rstudio-desktop-bin:  An integrated development environment (IDE) for R (binary from RStudio official repository)
      | wallutils :  Utilities for handling resolutions, wallpapers and timed wallpapers
:: Processing package changes...
(1/8) upgrading gdu                                                                                    [############################################################] 100%
(2/8) upgrading libgusb                                                                                [############################################################] 100%
(3/8) upgrading libharu                                                                                [############################################################] 100%
...
```