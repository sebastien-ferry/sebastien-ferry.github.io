---
layout: post
title:  "Firefox configuration"
date:   2022-05-01 12:00:00 +0800
categories: [firefox]
tags: [firefox, about:config]
excerpt_separator: <!--more-->
---

Big reminder about Firefox setup, including addons and settings.

<!--more-->

# addons
ctrl-shift-a

## Top Tier

 * Bypass Paywalls Clean
 * I don't care about cookies
 * Panorama View
 * Single File
 * Snooze Tabs
 * SortTabs
<br><br>
 * Tree Style Tab
 * TST Bookmarks Subpanel
 * uBlock Origin
 * Unpaywall
 * Zhongwen: Chinese-English dictionary
<br><br>
 * Tab Stash
 * Temporary Containers
 * What Hacker News Says

## Keep it?
* Container Tabs Sidebar
* URL to QR code
* Redirector / Privacy Redirect

## No more...

* Vimium (only using f and F, always blocking natural input, including Alt-1-9)

## Dubious
* Privacy Pass?


# about:config

## ...
Source: https://wiki.archlinux.org/title/Firefox

  * browser.quitShortcut.disabled : no ctrl-q
  * browser.uidensity = 1 : compact mode
  * toolkit.legacyUserProfileCustomizations.stylesheets = true : enable userChrome.css and userContent.css
  * pdfjs.spreadModeOnLoad = 1 : open PDF with 2 pages

## Let the URL bar be just a URL bar
2022-05-03 Firefox 99.0.1 OK!
* keyword.enabled : false
* browser.fixup.alternate.enabled : false

Ctrl-K to search otherwise
^<space> (history), *<space> (bookmarks)

# Pocket (to remove)

  * https://support.mozilla.org/en-US/kb/disable-or-re-enable-pocket-for-firefox
> Disable or re-enable Pocket for Firefox
> Pocket is a feature that's built into Firefox. You need to have a Pocket account in order to save articles with the Pocket Fx89PocketButton button, which is found in the Firefox toolbar. 

  * https://support.mozilla.org/en-US/questions/1065182
> How do I completely remove Pocket (not just disable) ?

  * https://fawove.com/how-to-remove-pocket-from-mozilla-firefox/
> How to remove Pocket from Mozilla Firefox
> about:config
> “extensions.pocket.enabled”






# Privacy? WebRTC

* media.peerconnection.enabled


https://webrtchacks.com/an-intro-to-webrtcs-natfirewall-problem/


### [mullvad - webrtc](https://mullvad.net/en/help/webrtc/)
<details>
<summary>https://mullvad.net/en/help/webrtc/ </summary>
<p>Firefox – easy method
</p>
<p>Desktop and Android users can use the [Disable WebRTC plugin](https://addons.mozilla.org/en-US/firefox/addon/happy-bonobo-disable-webrtc/) for Firefox. Click on the "Add to Firefox" button and follow the instructions to install the plugin.
</p><p>
Once installed, it will disable WebRTC by default. You can check by looking for the plugin's 'W' icon in the Firefox toolbar. The plugin is working if the icon is green. Click it and it will turn red, meaning that WebRTC is enabled again.
</p>
<p>Firefox – advanced method</p>
<p>Use these instructions if you wish to manually disable WebRTC:</p>
<ol>
<li> Type "about:config" into the address bar and hit Enter.
    Click the button "I accept the risk!".
    Type media.peerconnection.enabled in the search bar. Only one entry should appear.
    Right-click on the entry and choose "Toggle" to change the Value column to "false".
</li>
<li> To enable WebRTC again, follow the instructions until the Value column changes back to "true".
</li>
</ol>
</details>


### https://browserleaks.com/webrtc#howto-disable-webrtc

<details>
<summary>
https://browserleaks.com/webrtc#howto-disable-webrtc
</summary>
<a href="https://browserleaks.com/webrtc#howto-disable-webrtc">https://browserleaks.com/webrtc#howto-disable-webrtc</a>
<p>
WebRTC in Mozilla Firefox is supported since Firefox 22, and it's enabled by default.

<p>To disable RTCPeerConnection and protect IP addresses leakage, go to about:config and toggle media.peerconnection.enabled to false.

<>p>To disable Media Devices, toggle media.navigator.enabled as well as media.peerconnection.enabled both to false.
</details>

# Some sources

<details>
<summary> support.mozilla.org: [I want to disable search in the address bar and browser.urlbar.unifiedcomplete is not an option anymore](https://support.mozilla.org/en-US/questions/1213978) </summary>

<ol>
<li>In a new tab, type or paste about:config in the address bar and press Enter/Return. Click the button promising to be careful or accepting the risk.
</li>
<li>Search: In the search box above the list, type or paste keyw and pause while the list is filtered
</li>
<li>Double-click the keyword.enabled preference to switch the value from true to false
</li>
<li>Fixup: In the search box above the list, type or paste fix and pause while the list is filtered
</li>
<li>Double-click the browser.fixup.alternate.enabled preference to switch the value from true to false 
</li>
</ol>
</details>
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
