---
title: "Easy way to get a list of angular modules loaded on the page"
description: "Just execute this on the browser console,"
pubDate: 2017-06-19
category: "Randoms"
tags: []
draft: false
---
<p>Just execute this on the browser console,</p>
<pre class="brush: jscript; title: ; notranslate">
angular.module('yourModule')['_invokeQueue'].forEach(function(e){ console.log(e[2][0]) });
</pre>
