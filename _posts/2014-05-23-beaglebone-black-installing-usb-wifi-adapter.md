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

The manufacturer has a nice [installation and troubleshooting guide](http://inspire.logicsupply.com/p/installing-wifi.html) on their website.

Before turning on your BeagleBone, connect it to the network via ethernet and plug in the USB adapter. Once the board boots up, SSH into it
and run the following command to determine the adapter's device name

{% highlight bash %}
iwlist scan
{% endhighlight %}

It will most likely be something like `ra0`. To make sure the board connects to WiFi automatically on every restart you will need to edit the `interfaces` file

{% highlight bash %}
nano /etc/network/interfaces
{% endhighlight %}

For a dynamic IP address include this

{% highlight bash %}
# The wifi network interface
auto ra0
iface ra0 inet dhcp
wpa-ssid "SSID"
wpa-psk "YOUR-WIFI-PASSWORD"
{% endhighlight %}

Alternatively, use this for a static IP

{% highlight bash %}
# The wifi network interface
auto ra0
iface ra0 inet static
address 192.168.0.2
netmask 255.255.255.0
network 192.168.0.0
broadcast 192.168.0.255
gateway 192.168.0.1
dns-nameservers 192.168.0.1, 192.168.0.2, 8.8.8.8
wpa-ssid "SSID"
wpa-psk "YOUR-WIFI-PASSWORD"
{% endhighlight %}

Make sure you unplug the ethernet cable and restart the board. Once it reboots your BeagleBone should automatically connect to
 your WiFi network.