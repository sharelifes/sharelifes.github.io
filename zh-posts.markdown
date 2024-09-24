---
layout: page
title: 博客
permalink: /zh/posts/
background: '/assets/images/banner.jpg'
language: "zh"
---

<ul>
    {% for post in site.posts %}
        {% if post.language == "zh" and post.item == "list" %}
            <li>
                <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
                {{ post.excerpt }}
            </li>
        {% endif %}
    {% endfor %}
</ul>