---
title: "Brew Permission Denied on Mac OS X"
description: "This is a common error that might occure while you try to install a brew package or when you try to do a brew link which could say Error: Permission denied It’s too bad that unless you properly look on the log it outputs on the console, you won’t notice that the brew link has […]"
pubDate: 2016-10-07
category: "Randoms"
tags: []
draft: false
---
<p>This is a common error that might occure while you try to install a brew package or when you try to do a <code>brew link</code> which could say <code>Error: Permission denied</code></p>
<p>It&#8217;s too bad that unless you properly look on the log it outputs on the console, you won&#8217;t notice that the brew link has actually failed.</p>
<p>Anyway, what happens most of the time is, When we run an application installation with super user permissions, sometimes it actually modifies the permissions on <code>/usr/local</code> which will they be a problem for a application that&#8217;s not running with sudo permissions.</p>
<p>Luckily there&#8217;s a easy way to fix this, just run the below commands on terminal and brew should start working properly.</p>
<p><code>sudo chown -R "$USER":admin /usr/local</code></p>
<p>Also you might have to run this too in some cases</p>
<p><code>sudo chown -R "$USER":admin /Library/Caches/Homebrew</code></p>
