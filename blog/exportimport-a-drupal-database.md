---
title: "Export/Import a Drupal Database"
description: "Export Drupal 6 and 7 Drupal 8 Import"
pubDate: 2016-06-17
category: "Code Snippets"
tags:
  - "database"
  - "drupal"
  - "dump"
  - "export"
  - "import"
  - "mysql"
draft: false
---
<h2>Export</h2>
<p>Drupal 6 and 7</p>
<pre class="brush: bash; title: ; notranslate">
drush cc
drush sql-dump &amp;gt; ~/dump-file.sql
</pre>
<p>Drupal 8</p>
<pre class="brush: bash; title: ; notranslate">
drush cr
drush sql-dump &amp;gt; ~/dump-file.sql
</pre>
<h2></h2>
<h2>Import</h2>
<pre class="brush: bash; title: ; notranslate">
drush sql-drop
drush sql-cli &amp;lt; ~/my-sql-dump-file-name.sql
</pre>
