---
layout: post
title: Installing USB WiFi Adapter on the BeagleBone Black
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

![placeholder](/public/images/beaglebone/unw100-and-unw200-usb-wifi-adapters.jpg "UNW100 and UNW200 USB WiFi adapters")

* [UWN100](http://www.logicsupply.com/components/networking/wireless/uwn100/) - $9.95
* [UWN200](http://www.logicsupply.com/components/networking/wireless/uwn200/) - $12.95

### Setting up

The manufacturer has a nice [installation guide and troubleshooting](http://inspire.logicsupply.com/p/installing-wifi.html) on their website.

To connect to WiFi automatically you will first need to determine the device name. For that SSH to your BeagleBone
and use the following command:

{% highlight bash %}
iwlist scan
{% endhighlight %}

{% highlight bash %}
nano /etc/network/interfaces
{% endhighlight %}


{% highlight bash %}
auto ra0
iface ra0 inet dhcp
wpa-ssid "SSID"
wpa-psk "YOUR-WIFI-PASSWORD"
{% endhighlight %}
