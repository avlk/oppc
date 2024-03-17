---
layout: default
title: Blog
---

# Latest Posts

{% for post in site.posts %}
- [{{post.title}}](/oppc/{{post.url}})
    > {{ post.excerpt }}

{% endfor %}
