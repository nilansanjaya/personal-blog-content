---
title: "Smart Home – Homebridge"
description: "Homebridge is a lightweight NodeJS server you can run on your home network that emulates the iOS HomeKit API. It supports Plugins, which are community-contributed modules that provide a basic bridge from HomeKit to various 3rd-party APIs provided by manufacturers of “smart home” devices. This is going to be the brain of the whole smart […]"
pubDate: 2017-01-05
category: "Randoms"
tags: []
draft: false
---
<blockquote><p>Homebridge is a lightweight NodeJS server you can run on your home network that emulates the iOS HomeKit API. It supports Plugins, which are community-contributed modules that provide a basic bridge from HomeKit to various 3rd-party APIs provided by manufacturers of &#8220;smart home&#8221; devices.</p></blockquote>
<p>This is going to be the brain of the whole smart home thing. This directly connects with any Apple device ( iPhone, iPad etc ) and will contains all the necessary plugins and commands to control the wireless endpoints we will be making.</p>
<p>You can read more information and get it from its git repo &#8211; <a href="https://github.com/nfarina/homebridge" rel="nofollow">https://github.com/nfarina/homebridge</a></p>
<p>If you don&#8217;t have a Raspberry Pi or any other device, you can simply install it on your PC / Laptop. If you are worried about all the packages it installs, you can simply run it inside the linux vagrant box.</p>
<p>It might not work out of the box by following the simple installation mentioned there. atleast it didn&#8217;t for me, had some issues with npm versiona and permission, etc etc. after hours of research, here&#8217;s what I did. You can simply run the below commands and you should get the homebridge up and running in your device/VM in few minutes.</p>
<p><code><br />
sudo apt-get update<br />
sudo apt-get upgrade<br />
wget https://nodejs.org/dist/v5.3.0/node-v5.3.0-linux-x86.tar.gz<br />
tar -xvf node-v5.3.0-linux-x86.tar.gz<br />
cd node-v5.3.0-linux-x86<br />
sudo cp -R * /usr/local/<br />
node -v<br />
"v.5.3.0"<br />
npm -v<br />
"v.3.3.12"<br />
cd<br />
sudo apt-get install git<br />
sudo apt-get install libavahi-compat-libdnssd-dev<br />
sudo npm install -g homebridge<br />
sudo npm install -g homebridge-legacy-plugins<br />
homebridge<br />
"Couldn't find a config.json file [snip]"<br />
"Added config.json to ./homebridge folder. SUCCESS!!!"<br />
</code></p>
<p>Source: <a href="https://github.com/nfarina/homebridge/issues/347#issuecomment-165886271" rel="nofollow">https://github.com/nfarina/homebridge/issues/347#issuecomment-165886271</a></p>
<p>&nbsp;</p>
<p>If you have succesfully installed, you can simply run it using <code>homebridge</code> command and you should get something similar,</p>
<p><code><br />
---<br />
Loaded config.json with 0 accessories and 0 platforms.<br />
---<br />
Loading 0 platforms...<br />
Loading 0 plugins...<br />
Scan this code with your HomeKit App on your iOS device to pair with Homebridge:</p>
<p>    ┌────────────┐<br />
    │ 031-45-154 │<br />
    └────────────┘     </p>
<p>Homebridge is running on port 51826.</p>
<p></code></p>
<p>This means you are lucky. Go to your HomeKit App on your iPhone or iPad and it should detect your VM/Device as a Homebridge device.</p>
<p>There won&#8217;t be any accessories at the moment.</p>
