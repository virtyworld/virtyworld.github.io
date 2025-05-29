---
layout: default
title: Мое Портфолио
---

# Привет! 👋

Добро пожаловать на мою страницу портфолио. Здесь ты найдешь мои проекты по разработке игр и приложений.

## Мои Проекты

{% for post in site.posts reversed %}
<div class="project-card">
    <h2><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></h2>
    <p><strong>Платформы:</strong> {{ post.platforms }}</p>
    <p><strong>Жанр:</strong> {{ post.genre }}</p>
    <p><strong>Роль:</strong> {{ post.role }}</p>
    <p>{{ post.description }}</p>
    <div class="tags">
        {% for tag in post.tags %}
            <a href="{{ site.baseurl }}/tags.html#{{ tag | slugify }}">{{ tag }}</a>
        {% endfor %}
    </div>
</div>
{% endfor %}
