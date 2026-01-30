---
layout: default
title: Blog
---

{% for post in site.posts %}
<article class="post-preview">
  <h2>
    <a href="{{ post.url | relative_url }}">
      {{ post.title }}
    </a>
  </h2>

  <p class="post-excerpt">
    {{ post.excerpt }}
  </p>
</article>
{% endfor %}
