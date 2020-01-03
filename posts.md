---
title: "All Posts"
permalink: "/posts/index.html"
---

<ul class="list pa0">
  {% for category in site.categories %}
  <h3>{{ category[0] | upcase }}</h3>
  {% for post in category[1] %}
  <li class="mv2">
    <a href="{{ site.url }}{{ post.url }}" class="db pv1 link blue hover-mid-gray">
      <time class="fr silver ttu">{{ post.date | date_to_string }} </time>
      {{ post.title }}
    </a>
  </li>
  {% endfor %}
  {% endfor %}
</ul>
