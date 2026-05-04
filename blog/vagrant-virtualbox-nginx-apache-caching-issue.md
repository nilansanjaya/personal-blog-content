---
title: "Vagrant + Virtualbox + ( Nginx / Apache ) caching issue"
description: "This is one of the annoying errors you might get when using the above combinations. Very hard to cache, you might turn the world upside down looking why your css or js files are not getting updated on the browser unless you restart the vagrant box. The symptoms are, you do a edit on your […]"
pubDate: 2017-02-20
category: "Randoms"
tags: []
draft: false
---
<p>This is one of the annoying errors you might get when using the above combinations. Very hard to cache, you might turn the world upside down looking why your css or js files are not getting updated on the browser unless you restart the vagrant box.</p>
<p>The symptoms are, you do a edit on your css or js files, and when you check on the browser, it the css or js file either corrupted half way, or it has some unicode characters at the last line and your changes are not updated.</p>
<p>At the writing of this post, it&#8217;s a known issue when the vagrant and virtual box combined, theres an option called <code>"sendfile"</code> that&#8217;s causing the problem. Simply turning it off and giving a <code>vagrant reload</code> could fix it.</p>
<p>If you are on <strong>nginx</strong>, simply edit the nginx.conf file and add/modify <code>sendfile off</code> option</p>
<p>If you are on <strong>apache</strong>, edit your conf file ( virtual host or the httpd conf file ) and add the below option,</p>
<pre class="brush: bash; title: ; notranslate">
&lt;Directory YOUR_PROJECT_DIRECTORY&gt;
	EnableSendfile Off
&lt;/Directory&gt;
</pre>
