---
title: "Forgot your Mac OS Password?"
description: "Forgot your Mac OS Password? There are few ways to reset. The easiest way is to reset the password through another admin account. or else you can reset it through an Apple ID. you can just google and find many common ways to reset an administrator password. but what if you only have one admin […]"
pubDate: 2014-08-03
category: "Tech Support"
tags:
  - "administrator password"
  - "Apple"
  - "Mac OS"
draft: false
---
<p>Forgot your Mac OS Password?  There are few ways to reset. The easiest way is to reset the password through another admin account. or else you can reset it through an Apple ID. you can just google and find many common ways to reset an administrator password. but what if you only have one admin user for the device? and what to do when all those methods does not work?</p>
<p>You can either Go to a Repair which most of the people will charge you a higher amount or they will fail to do it.</p>
<p>Its simple! you just have to delete the initial setup files of the Mac Os. and here&#8217;s how to do it.</p>
<p>1) Shutdown<br />
2) Hold the Apple key + S and switch on the Mac while holding the keys.<br />
3) you should get the terminal now. ones its idle, enter the below commands.</p>
<p><code>mount -uw /<br />
rm /var/db/.AppleSetupDone<br />
reboot</code></p>
<p>After rebooting you will go through the steps of a brand new OS where you can create a new admin account. which you can use to change or delete the existing one!</p>
