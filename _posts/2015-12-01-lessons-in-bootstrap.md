---
title : Lessons in Bootstrap - The Polka
meta : Dec 1, 2015
tags : [dev,blogdev]
post-id: d
---
<p><b><i>This release can be found <a href="https://github.com/tmlewallen/tmlewallen.github.io/releases/tag/v1.0">here - v1.0</a></i></b></p>
<p>Whenever I start a project with Bootstrap, I always think it'll pretty straight forward. Nothing finicky to deal with, just simple, intuitive design.</p>

<p><i>It never really turns out that way though.</i></p>

<p>Bootstrap feels like it's 1 part intuitive grid system and 2 parts sorcery.</p>

<p>I'm pretty pleased with how simple my markup is in this version of the blog, but it honestly took me a good number of hours of trial and error to get here.</p> 

<p>And the real challenge was... <i>Accordions.</i></p>

<p>I knew I wanted posts to expand/accordion-open to show content. Seemed simple enough. Bootstrap has that, no problem.</p>

<p>Except I never know what the deal is with these things. Sometimes they don't animate smoothly. Sometimes they don't animate at all. I messed around with using Bootstrap accordions on another project, but they wouldn't animate smoothly over a background image. So I wasn't surprised when I had trouble getting them to work for the blog. I was having some issues with the close animation for a while but all of a sudden it started working. Whatever.</p>

<p>Here's what eventually worked:</p>

<pre class="prettyprint">
{% raw %}
&lt;a data-toggle="collapse" data-parent="#accordion" href="#{{post.post-id}}-post-id" aria-expanded="false"&gt;
	&lt;div class="post-container col-lg-offset-2 col-lg-8 col-md-12 col-sm-12 col-xs-12"&gt;
		&lt;h2 class="post-title"&gt;{{post.title}}&lt;/h2&gt;
		&lt;h4 class="post-subtitle"&gt;{{post.meta}}&lt;/h4&gt;
		&lt;div class="collapse" id="{{post.post-id}}-post-id"&gt;
			&lt;div class="post-content"&gt;
				{{post.content}}
			&lt;/div&gt;
		&lt;/div&gt;
	&lt;/div&gt;
&lt;/a&gt;
{% endraw %}
</pre>
<p class="img-desc"><i>From <a href="https://github.com/tmlewallen/tmlewallen.github.io/blob/master/index.html">index.html</a></i></p>
<p><i>The 'data-parent' attribute isn't actually important, just left over from experimenting.</i></p>
<p>Still haven't been able to get things to function where only one accordion can be open at a time. I'll figure that out eventually...</p>