---
layout: post
title:  "Bluetooth Low Energy everywhere!"
date:   2019-09-24 12:35:28 +0800
categories: [blog, coding]
tags: [python, ble, bluetooth, rasperry pi zero w]
excerpt_separator: <!--more-->
---
It is just crazy that so many devices broadcast so much through Bluetooth Low Energy!
    Cars, Bikes (rent), what else?

Inspired by a thread on [Hacker News: Retail stores use Bluetooth beacons to track customers](<https://news.ycombinator.com/item?id=20183968> "Y").

4 millions recording later.

<!--more-->

![Raspberry pi zero W](/assets/ble_raspberry_pi_zero_w_1-5_large.png){: style="float:right; width:30%"}

## Setup: database + raspberry pi zero W
<!--
<img style="float: right;" src="whatever.jpg">
 <img width="50%" style="float: right;" src="/assets/ble_raspberry_pi_zero_w_1-5_large.png">
 -->

T4 (PostgreSQL)  --- RPI0W

## Bluepy

  * *NOTE that LE scanning must be run as root.* :warning:
  * and loop around...

References:
  * [Github: IanHarvey/bluepy](<https://github.com/IanHarvey/bluepy> "Github: IanHarvey/bluepy")
  * [Documentation bluepy scanner](<http://ianharvey.github.io/bluepy-doc/scanner.html> "Sample code")

```python
from bluepy.btle import Scanner, DefaultDelegate

class ScanDelegate(DefaultDelegate):
    def __init__(self):
        DefaultDelegate.__init__(self)

    def handleDiscovery(self, dev, isNewDev, isNewData):
        if isNewDev:
            print "Discovered device", dev.addr
        elif isNewData:
            print "Received new data from", dev.addr

scanner = Scanner().withDelegate(ScanDelegate())
devices = scanner.scan(10.0)

for dev in devices:
    print "Device %s (%s), RSSI=%d dB" % (dev.addr, dev.addrType, dev.rssi)
    for (adtype, desc, value) in dev.getScanData():
        print "  %s = %s" % (desc, value)
```

## Code on GitHub

Coming soon

  * sensor
  * database
  * flask web access

## Some result

### Name cloud
![Name Cloud](</assets/ble_name_cloud.png>)

### Manufacturer cloud
![Manufacturer Cloud](</assets/ble_manufacturer_cloud.png>)

### App screenshot
![Screenshot](</assets/ble_screenshot.png>)

## Next

 (?)

 Also, RF with TPMS
