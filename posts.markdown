---
layout: page
title: Blogs
permalink: /posts/
background: '/assets/images/banner.jpg'
language: "en"
---

<ul>
    {% for post in site.posts %}
        {% if post.language == "en" and post.item == "list" %}
            <li>
                <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
                {{ post.excerpt }}
            </li>
        {% endif %}
    {% endfor %}
</ul>