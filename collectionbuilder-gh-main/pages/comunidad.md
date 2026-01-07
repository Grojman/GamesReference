---
layout: page-full-width
title: Comunidad Gamer
permalink: /comunidad/
---

<div class="community-container">
    <div class="news-header-pill">
        NOTICIAS
    </div>

    {% assign posts = site.data.comunidad | sort: 'fecha' | reverse %}
    {% for post in posts %}
    <a href="{{ '/new-player.html' | relative_url }}?id={{ post.id }}">
    <div class="news-card">
        <div class="news-card-body">
            <p style="font-size:x-large">{{ post.titulo }}</p>
        </div>
        <div class="news-card-header">
            <span class="game-pill">{{ post.juego }}</span>
            <span class="user-date-info" style="color:{{ post.avatar_color }}">{{ post.usuario }} - {{ post.fecha | date: "%d/%m/%Y" }}</span>
        </div>
    </div>
    </a>
    {% endfor %}

</div>
