---
title: "Smart Home – ESP8266 module with NodeMCU"
description: "ESP8266 wifi module is going to be our endpoint where we will be controlling through our Homebridge device. For the moment, we will be simply controlling a 5V relay which will control the power of any electrical device ( ex: Lights, TV, Wall outlets etc ) NodeMCU is a firmware that allows you to program […]"
pubDate: 2017-01-10
category: "Randoms"
tags: []
draft: false
---
<p>ESP8266 wifi module is going to be our endpoint where we will be controlling through our Homebridge device. For the moment, we will be simply controlling a 5V relay which will control the power of any electrical device ( ex: Lights, TV, Wall outlets etc )</p>
<p>NodeMCU is a firmware that allows you to program the ESP8266 modules with LUA script. And you’ll find it very similar to the way you program an Arduino. With just a few lines of code you can establish a WiFi connection, control the ESP8266 GPIOs, turning your ESP8266 into a web server and a lot more. In our case, we will only be needing two URL endpoints to switch on / off the relays. Which we can call from our homebridge device.</p>
<p>First things first, unless your module is having pre installed firmware, we need to write the nodeMCU firmware to it before we start. Thanks to the open source community, this is fairly simple. you just need the right tools.</p>
<p>&nbsp;</p>
<p>I&#8217;ve bought the device with loaded firmware. you can follow these few steps to get your device up and running.</p>
<p><a href="https://github.com/nodemcu/nodemcu-devkit/wiki/Getting-Started-on-OSX" target="_blank">https://github.com/nodemcu/nodemcu-devkit/wiki/Getting-Started-on-OSX</a></p>
<p>If everything worked well, you should now be able to run lua scripts inside your module!</p>
<p>We will be using <a href="http://esp8266.ru/download/esp8266-doc/Getting%20Started%20with%20the%20ESPlorer%20IDE%20-%20Rui%20Santos.pdf" target="_blank">ESPlorer</a> for that.</p>
