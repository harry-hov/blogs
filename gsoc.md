---
title: GSoC
category_filter: gsoc
permalink: "gsoc"
---

I've been selected in [GSoC 2020](https://summerofcode.withgoogle.com/projects/#4593212745842688)
contributing to Git. This page contains the [almost] weekly updates about my
project during the GSoC period. You may also want to read my
[project proposal](https://public-inbox.org/git/CA+CkUQ966swTrR7D2vxgQ2ZA3E=Le=u8yvEAopOsphoCWGgDeg@mail.gmail.com/).

<ul class="list pa0">
  {% for post in site.posts %}
  {% if post.categories contains page.category_filter %}
  <li class="mv2">
    <a href="{{ site.url }}{{ post.url }}" class="db pv1 link blue hover-mid-gray">
      <time class="fr silver ttu">{{ post.date | date_to_string }} </time>
      {{ post.title }}
    </a>
  </li>
  {% endif %}
  {% endfor %}
</ul>
