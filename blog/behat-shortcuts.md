---
title: "Behat Shortcuts"
description: "Run all Run single feature Run single scenario within a feature Where 10 is the line number of the first line of the feature Run all tests with a certain tag All tests except a certain tag Run multiple tags: Run tests tagged with @tagname1 AND @tagname2 AND NOT […]"
pubDate: 2016-07-26
category: "Code Snippets"
tags:
  - "behat"
  - "shortcuts"
draft: false
---
<p>Run all</p>
<pre class="brush: bash; title: ; notranslate">
bin/behat path_to_yml
</pre>
<p>&nbsp;</p>
<p>Run single feature</p>
<pre class="brush: bash; title: ; notranslate">
bin/behat features/featureName.feature
</pre>
<p>&nbsp;</p>
<p>Run single scenario within a feature<br />
<em>Where 10 is the line number of the first line of the feature</em></p>
<pre class="brush: bash; title: ; notranslate">
bin/behat features/featureName.feature:10 
</pre>
<p>&nbsp;</p>
<p>Run all tests with a certain tag</p>
<pre class="brush: bash; title: ; notranslate">
bin/behat --tags @tagname
</pre>
<p>&nbsp;</p>
<p>All tests except a certain tag</p>
<pre class="brush: bash; title: ; notranslate">
bin/behat --tags ~tagname
</pre>
<p>&nbsp;</p>
<p>Run multiple tags:</p>
<pre class="brush: bash; title: ; notranslate">
bin/behat --tags &quot;@tagname1,@tagname2&quot;
bin/behat --tags=&quot;@tagname1&amp;&amp;@tagname2&quot;
</pre>
<p>&nbsp;</p>
<p>Run tests tagged with @tagname1 AND @tagname2 AND NOT @tagname3</p>
<pre class="brush: bash; title: ; notranslate">
bin/behat --tags &quot;@tagname1&amp;&amp;@tagname2&amp;&amp;~@tagname3&quot;
</pre>
<p>&nbsp;</p>
<p>By adding an @javascript tag above the feature (for all the scenarios) or above a single scenario, the test will use Selenium and Firefox to run the test. These defaults can be changed in the behat.yml file.</p>
