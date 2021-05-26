---
layout: default
title: Home
description: Stuff
---

<ul id='posts'>
  {%- for post in site.posts -%}
  <li>
    <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
    <p>{{ post.description }}</p>
    <p class='date'>{{ post.date | date: '%B %d, %Y' }} | &nbsp;
      {%- if post.categories != empty -%}
        {%- for category in post.categories -%}
        <a href="{{site.baseurl}}/categories?q={{category|slugize}}">{{category}}</a>
        {%- unless forloop.last %},&nbsp;{% endunless -%}
        {%- endfor -%}
      {%- endif -%}
    </p>
  </li>
  {%- endfor -%}
</ul>