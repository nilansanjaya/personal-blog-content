---
title: "Smart Home – The Beginning"
description: "This isn’t a tutorial on how to build your own smart home. But more of how i built mine. There are lots of different tutorials out there, using different chips, platforms, different software, etc. The hardest part at the beginning was to select which platforms to go with, and which hardware and software to use. […]"
pubDate: 2017-01-05
category: "Randoms"
tags: []
draft: false
---
<p>This isn&#8217;t a tutorial on how to build your own smart home. But more of how i built mine.</p>
<p>There are lots of different tutorials out there, using different chips, platforms, different software, etc. The hardest part at the beginning was to select which platforms to go with, and which hardware and software to use. I did not wanted to buy a ready made smart home software, due to there price, restricted use of only there supported products, and most of that, its simply not my thing <img src="https://s0.wp.com/wp-content/mu-plugins/wpcom-smileys/twemoji/2/72x72/1f642.png" alt="🙂" class="wp-smiley" style="height: 1em; max-height: 1em;" /></p>
<p>So i decided to build my own system. Which can support different platforms. But i did not wanted to build something from scratch ( that would be stupid rite? sometimes ) So i spent most of my free time researching of hardware and software i can use. and finally came up with the following.</p>
<p><strong>Phase 1 Target</strong></p>
<p>My target for Phase 1 is to automate my room first. When i wake up, I want my curtains to be open automatically. Turn off any night lights if On. ( Bonus: Switch on an Audio device and Start playing some music while reading my daily calendar or other news items which i can pre program )</p>
<p>In the evening when its getting dark, close the Curtains and switch on the lights. Additionally, I should be able to control the lights and night lights anytime i want.</p>
<p><strong>Hardware and Software</strong></p>
<p>Central Controller &#8211; Homebridge ( Running on Raspberry Pi )<br />
The main reason to pick this one is its born compatibility to be used with Apple Homekit, which i think is the easiest way to control any and everything in a single app + you get the voice command features through Siri. Homebridge can simply run on an Raspberry Pi or any other similar hardware.</p>
<p><img loading="lazy" class="alignnone " src="https://encrypted-tbn3.gstatic.com/images?q=tbn:ANd9GcR4HvQ7gVyn3KeUZI4BFD67RMKLpKUEbJYmOA_PfpBBm-ri-8tDuQ" alt="" width="240" height="62" /></p>
<p>&nbsp;</p>
<p>Wireless Modules &#8211; NodeMCU ESP8266<br />
This means the end points, Lights, Switches, Sensors ( Phase 2 ) and every other outlet. I wanted them to be wireless, Less in size and less in cost.<br />
Since the homebridge can be used with any other already existing hardware endpoints, i could have simply bought them and used, but then where&#8217;s the fun in that ?<br />
The Winner of my research was this little module. It&#8217;s small in size and has built in wifi. It&#8217;s just a matter of few lines of code to get it working and few more lines of code to make it work through URL&#8217;s. just what i was looking for.</p>
<p><img loading="lazy" class="alignnone " src="https://raw.githubusercontent.com/nodemcu/nodemcu-devkit-v1.0/master/Documents/NodeMCU_DEVKIT_1.0.jpg" alt="" width="321" height="214" /></p>
<p>&nbsp;</p>
<p>So at the time of writing this, I&#8217;ve already ran a homebridge server and programmed a NodeMCU.  it seems these two can accomplish what i want to do in Phase 1.</p>
<p>&nbsp;</p>
