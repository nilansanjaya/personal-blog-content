---
title: "Postfix failed to start after upgrade"
description: "So I’ve came across this issue recently when i updated the packages on one of my VPS. Postfix service stopped working and it didn’t start back. Tried few different ways and still it didn’t start. Nothing much helpful on the logs either. The problem seems to be an existing process using the postfix pid lock […]"
pubDate: 2017-12-06
category: "Randoms"
tags: []
draft: false
---
<p>So I&#8217;ve came across this issue recently when i updated the packages on one of my VPS. Postfix service stopped working and it didn&#8217;t start back. Tried few different ways and still it didn&#8217;t start. Nothing much helpful on the logs either.</p>
<p>The problem seems to be an existing process using the postfix pid lock file which might have probably left out while killing the process for updating, and doesn&#8217;t let the postfix to start again.</p>
<p>You can try the below steps to resolve that,</p>
<p>Try to find the process that&#8217;s using the postfix service<br />
<code><br />
$htop<br />
</code></p>
<p>To make sure, run below with the process id you found. you should see something similar to<code><br />
#ps -ef | grep 7881<br />
root      7881     1  0 Sep16 ?        00:00:09 /usr/libexec/postfix/master -w<br />
</code></p>
<p>Kill the process<code><br />
$kill 7881<br />
</code></p>
<p>Start postfix <code><br />
sudo postfix start<br />
</code></p>
