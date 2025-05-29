---
layout: default
title: Теги Проектов
---

# Теги

Здесь ты можешь найти проекты, сгруппированные по тегам.

<div class="tag-list">
    {% assign all_tags = site.posts | map: 'tags' | compact | uniq %}
    {% for tag_group in all_tags %}
        {% for tag in tag_group %}
            <a href="#{{ tag | slugify }}" class="tag-button">{{ tag }}</a>
        {% endfor %}
    {% endfor %}
</div>

{% assign sorted_tags = site.tags | sort %}
{% for tag_name in sorted_tags %}
    <h2 id="{{ tag_name[0] | slugify }}">{{ tag_name[0] }}</h2>
    <ul>
        {% for post in tag_name[1] %}
            <li><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></li>
        {% endfor %}
    </ul>
{% endfor %}

<style>
    .tag-list {
        margin-bottom: 30px;
    }
    .tag-button {
        background-color: #007bff;
        color: white;
        padding: 8px 12px;
        border-radius: 5px;
        text-decoration: none;
        margin: 5px;
        display: inline-block;
        font-size: 0.9em;
    }
    .tag-button:hover {
        background-color: #0056b3;
    }
</style>
