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
    <div class="news-card">
        <div class="news-card-header">
            <span class="game-pill">{{ post.juego }}</span>
            <span class="user-date-info">{{ post.usuario }} - {{ post.fecha | date: "%d/%m/%Y" }}</span>
        </div>
        <div class="news-card-body">
            <p>{{ post.mensaje }}</p>
        </div>
    </div>
    {% endfor %}

</div>
