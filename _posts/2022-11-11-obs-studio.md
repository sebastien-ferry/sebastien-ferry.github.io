---
layout: post
title:  "OBS Studio - for remote meetings like a pro"
date:   2022-09-18 12:00:00 +0800
categories: [internet]
tags: [internet, corporate]
excerpt_separator: <!--more-->
---

Free and open source software for video recording and live streaming.

<!--more-->

# What and why

OBS can suprimpose several sources on a video flow.
For example, it can add a logo, a timer, and a webcam feed over the main presentation.

And that is cool, and almost all I use.

There are plenty of plugin... to try one day!

# How
[Virtual Camera Guide (2022-08-31)](https://obsproject.com/eu/kb/virtual-camera-guide)

https://www.movavi.com/learning-portal/obs-virtual-camera.html


<hr>
# Some technical details follow... (maybe not needed)

Here are some technical notes and pointers.

I fought a lot to get the webcam working on Windows, for older version of OBS, simply getting the information that it needed a plugin!


## Windows old versions

With old versions

Virtual Cam Plugin 2.0.5


## Linux special for virtual camera
[Virtual Camera Troubleshooting](https://obsproject.com/eu/kb/virtual-camera-troubleshooting#install-or-remove-the-virtual-camera)

creating a /dev/video13 device (for virtual camera)...

install: `v4l2loopback-dkms v4l2loopback-utils` 

(as root)
``` bash
# echo "options v4l2loopback devices=1 video_nr=13 card_label='OBS Virtual Camera' exclusive_caps=1" | sudo tee /etc/modprobe.d/v4l2loopback.conf
options v4l2loopback devices=1 video_nr=13 card_label='OBS Virtual Camera' exclusive_caps=1

# echo "v4l2loopback" | sudo tee /etc/modules-load.d/v4l2loopback.conf
v4l2loopback

# sudo modprobe -r v4l2loopback

# sudo modprobe v4l2loopback devices=1 video_nr=13 card_label="OBS Virtual Camera" exclusive_caps=1
```

[Jonathan: OBS studio Linux virtual camera](https://jonathanbossenger.com/2020/12/17/obs-studio-linux-virtual-camera/)
[2021-07 OBS Linux Basics: Virtual Webcam](https://linuxgamecast.com/2021/07/obs-linux-basics-virtual-webcam/)

## Recent issues
[Windows suppor: Virtual Cam Plugin 2.0.5 not working with OBS 28](https://obsproject.com/forum/threads/virtual-cam-plugin-2-0-5-not-working-with-obs-28.159081/)
> * #1 (ramraver) The vCam Plugin is not working any longer with version 28.
>
> What about users who need more than just one virtual cam?*
>> ...
>>> #25 (dev47) FYI- there is a new alternative virtual output plugin, currently waiting for moderation/approval.
>>>
>>> Not sure why it has not been posted on the forums yet, I assume the moderators are busy due to the OBS 28 launch,
>>>
>>> but you can find the project on GitHub in the meantime
>>>
>>> [GitHub - dev47apps/droidcam-obs-virtual-output](https://github.com/dev47apps/droidcam-obs-virtual-output)


## Windows special virtual cam  ()

https://github.com/dev47apps/droidcam-obs-virtual-output

 An alternative virtual output plugin for OBS Studio

https://obsproject.com/forum/resources/droidcam-virtual-output.1580/


An alternative virtual output plugin that connects OBS Studio with the DroidCam virtual camera drivers on Windows.

## Virtual Camera troubleshooting
Not sure if still needed...

2022-08-31
https://obsproject.com/eu/kb/virtual-camera-troubleshooting

# Plugins [TBC]
...


## [Waveform](https://obsproject.com/forum/resources/waveform.1423/)

(Windows, Mac OS X, Linux)

Waveform is a plugin for showing a (cosmetic) frequency spectrum graph and other metrics of an audio source.

# Virtual background removal

https://obsproject.com/forum/resources/background-removal-portrait-segmentation.1260/

https://github.com/royshil/obs-backgroundremoval



## [OBS Virtual background plugin](https://obsproject.com/forum/resources/obs-virtual-background-plugin.1371/) Windows
> An OBS plugin for Zoom/Meet-like virtual background feature.
>
>   uses Deep Learning based segmentation / no need to use green screen
>   fast and lightweight processing / 4~5ms / frame / <5% CPU usage at AMD Ryzen 9
>
>   no need to use chroma-key / you can wear green color, any color, rainbow/full-color T-shirts!


## [StreamFX (for OBS® Studio)](https://obsproject.com/forum/resources/streamfx-for-obs%C2%AE-studio.578/)
(Windows, Mac OS X, Linux)



