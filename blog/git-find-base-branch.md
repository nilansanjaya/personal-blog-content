---
title: "Git: find base branch of a branch"
description: "Switch to your branch and run the below ( whole line )"
pubDate: 2017-06-01
category: "Code Snippets"
tags: []
draft: false
---
<p>Switch to your branch and run the below ( whole line )</p>
<pre class="brush: bash; title: ; notranslate">
git show-branch -a \
| grep '\*' \
| grep -v `git rev-parse --abbrev-ref HEAD` \
| head -n1 \
| sed 's/.*\[\(.*\)\].*/\1/' \
| sed 's/[\^~].*//‘
</pre>
