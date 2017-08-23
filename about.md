---
title: About
layout: page
---

<header class="header-home {% if site.animation %}animated{% endif %}">
	{% if site.about %}
	<a class="link" href="{{ site.url }}/about">
		<img class="selfie" alt="{{ site.name }}" src="{% if site.external-image %}{{ site.picture }}{% else %}{{ site.url }}/{{ site.picture }}{% endif %}" />
	</a>
	{% else %}
	<span class="link">
		<img class="selfie" alt="{{ site.name }}" src="{% if site.external-image %}{{ site.picture }}{% else %}{{ site.url }}/{{ site.picture }}{% endif %}" />
	</span>
	{% endif %}

	<h1 class="title">{{ site.name }}</h1>
	<h2 class="description">{{ site.bio }}</h2>

	{% include social-links.html %}
</header>


{% include nav.html %}

<hr>
<p>I am a web developer currenlty working for Giraffes in the Kitchen, a digital agency in Greece.</p>

<p>This is the place where I document and share my projects or other findings from daily issues/bugs.</p>

<p>My current stack is: PHP, MySQL, Apache and a lot of Javascript.</p>

<p>You can check some of my projects on my <a href="https://github.com/konmavrakis">github</a> profile or you can follow me on <a href="https://twitter.com/konmavrakis">twitter</a></p>


<h2>Skills</h2>

<ul class="skill-list">
	<li>HTML - Pug</li>
	<li>JavaScript (ES5,ES6, NodeJS)</li>
	<li>CSS (Sass)</li>
	<li>CSS Frameworks (Bootstrap)</li>
	<li>Gulp</li>
	<li>Git</li>
	<li>PHP</li>
	<li>MySQL - MongoDB</li>
	<li>Linux server administration</li>
</ul>