---
layout: page
title: Articles
permalink: /articles/
---
  <ul class="post-list">
      {% for post in site.posts %}
      <li>
        <div>
        {%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
          <span class="post-meta">{{ post.date | date: date_format }}</span> <!---|
       {% for tag in post.tags %}
      <a class="post" href="/tag/{{ tag | downcase | url_encode }}"><small>{{ tag }}</small></a>{% unless forloop.last %}, {% endunless %}
      {% endfor %} --->
          <h3>
            <a class="post-link" href="{{ post.url | relative_url }}">
            {{ post.title | escape }}
            </a>
          </h3>
       {%- if post.image -%}
          <figure class="post-cover" style="float: left">
            <a href="{{ post.url | relative_url }}"><img src="{{ post.image | prepend: site.baseurl }}" alt="{{ post.title }}" title="{{ post.title }}"></a>
          </figure>
          {{ post.excerpt | strip_html | truncatewords: 100 }}
          <a href="{{ post.url | relative_url }}">Lire la suite</a>
        </div>
      {%- endif -%}     
      </li>
  {% endfor %}
    </ul>
