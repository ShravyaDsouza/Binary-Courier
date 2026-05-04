---
layout: default
title: Home
---

<div class="bento-grid">
  {% for post in site.posts limit: 10 %}
    <div class="bento-item {% if forloop.first %}featured{% endif %}">
      <div class="tag-container">
        {% if forloop.first %}<span class="bento-tag">LATEST</span>{% endif %}
        {% for tag in post.tags %}<span class="bento-tag">{{ tag | upcase }}</span>{% endfor %}
      </div>
      <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
      <p>{{ post.date | date: "%b %d, %Y" }}</p>
    </div>
  {% endfor %}
</div>