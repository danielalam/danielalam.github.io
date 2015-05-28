---
layout: post
title: Installing USB Wifi Adapter on the BeagleBone Black
date:   2014-05-23 15:51:27
categories: beaglebone
tags: electronics beaglebone
---

Unfortunately, [BeagleBone Black](http://beagleboard.org/black) doesn't have a built in WiFi module, but
there are a few USB WiFi adapters that can solve this problem.

### UWN100 and UWN200

The best part about these two adapters is that the latest release of the BeagleBone Black, with a Debian image (2013-09-04 and up), already includes the drivers
for these modules. Both are manufactured by [Logic Supply](http://inspire.logicsupply.com/). UWN200 has an SMA antenna for extra range, otherwise
it is similar to UWN100.

<----------Photo here!


* [UWN100](http://www.logicsupply.com/components/networking/wireless/uwn100/) - $9.95
* [UWN200](http://www.logicsupply.com/components/networking/wireless/uwn200/) - $12.95

### Setting up

The manufacturer has a nice [installation guide and troubleshooting](http://inspire.logicsupply.com/p/installing-wifi.html) on their website.

To connect to WiFi automatically you will first need to determine the device name

iwlist scan
* Toggleable sliding sidebar (built with only CSS) via **☰** link in top corner
* Sidebar includes support for textual modules and a dynamically generated navigation with active link support
* Two orientations for content and sidebar, default (left sidebar) and [reverse](https://github.com/poole/lanyon#reverse-layout) (right sidebar), available via `<body>` classes
* [Eight optional color schemes](https://github.com/poole/lanyon#themes), available via `<body>` classes

[Head to the readme](https://github.com/poole/lanyon#readme) to learn more.

### Browser support

Lanyon is by preference a forward-thinking project. In addition to the latest versions of Chrome, Safari (mobile and desktop), and Firefox, it is only compatible with Internet Explorer 9 and above.

### Download

Lanyon is developed on and hosted with GitHub. Head to the <a href="https://github.com/poole/lanyon">GitHub repository</a> for downloads, bug reports, and features requests.

Thanks!
