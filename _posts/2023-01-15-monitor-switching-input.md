---
layout: post
title:  "Switching monitor input from command line"
date:   2023-01-15 12:00:00 +0800
categories: [it, windows, linux]
tags: [WIP, it]
excerpt_separator: <!--more-->
---

DDC/IC

<!--more-->


# Linux

ddcutil --bus=1 setvcp 60 18

https://blog.tcharles.fr/ddc-ci-screen-control-on-linux/

https://moverest.xyz/blog/control-display-with-ddc-ci/



# Windows

Nirsoft
ControlMyMonitor

## Command line!

https://www.nirsoft.net/articles/set_monitor_input_source_command_line.html

`ControlMyMonitor.exe /SetValue "\\.\DISPLAY2\Monitor0" 60 3 `

# Keep going
https://moverest.xyz/blog/control-display-with-ddc-ci/

https://github.com/ChalkElec/write-edid
