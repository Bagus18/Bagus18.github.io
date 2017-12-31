---
layout: gawan
title: Note's
permalink: /note/
img: https://openclipart.org/image/2400px/svg_to_png/182517/paper-notes.png
---
<div class="home w3-animate-zoom">
	<h1 class="page-heading w3-text-indigo w3-animate-top">Entry <a class="w3-right-align rss-subscribe" href="{{ "/feed.xml" | prepend: site.baseurl }}" title="subscribe via RSS"><i class="fa fa-rss w3-text-orange w3-right-align w3-animate-fading" aria-hidden="true"></i></a></h1>
      {% for post in site.posts %}
        {% unless post.next %}
		<ul>
          <h3 class="w3-text-deep-purple">{{ post.date | date: '%Y' }}</h3>
        {% else %}
          {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
          {% capture nyear %}{{ post.next.date | date: '%Y' }}{% endcapture %}
          {% if year != nyear %}
            <h3 class="w3-text-purple">{{ post.date | date: '%Y' }}</h3>
          {% endif %}
        {% endunless %}
        <li class="w3-text-red fa fa-angle-double-right"><a href="{{ site.baseurl }}{{ post.url }}" class="w3-text-blue"> {{ post.title }}</a></li>
      {% endfor %}
    </ul>
</div>