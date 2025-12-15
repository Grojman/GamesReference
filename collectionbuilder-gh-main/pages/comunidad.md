---
layout: page-full-width
title: Comunidad Gamer
permalink: /comunidad/
---

<div class="gamer-community-wrapper">
    <div class="community-header mb-5 text-center">
        <h1 class="neon-text">ZONA DE DISCUSIÓN</h1>
        <p class="text-muted">Únete a la conversación. Sin registros. Pura pasión.</p>
        <button class="btn btn-neon mt-3">
            <i class="fas fa-plus-circle"></i> NUEVA DISCUSIÓN
        </button>
    </div>
    <div class="container main-feed mb-5">
        <h3 class="section-title"><i class="fas fa-fire"></i> TENDENCIAS RECIENTES</h3>
        {% assign posts = site.data.comunidad | sort: 'fecha' | reverse %}
        {% for post in posts limit:3 %}
        <div class="gamer-card mb-4 animate-up">
            <div class="card-header-gamer">
                <span class="game-tag">{{ post.juego }}</span>
                <span class="date-tag">{{ post.fecha | date: "%d %b" }}</span>
            </div>
            <div class="card-body-gamer">
                <div class="user-info">
                    <div class="avatar" style="background-color: {{ post.avatar_color }}">{{ post.usuario | slice: 0 }}</div>
                    <div class="username">{{ post.usuario }}</div>
                </div>
                <h4 class="post-title">{{ post.titulo }}</h4>
                <p class="post-content">{{ post.mensaje }}</p>
            </div>
            <div class="card-footer-gamer">
                <span><i class="fas fa-heart"></i> {{ post.likes }}</span>
                <span><i class="fas fa-comment-alt"></i> {{ post.respuestas }}</span>
            </div>
        </div>
        {% endfor %}
    </div>
    <div class="slider-section mt-5">
        <h3 class="section-title ml-4"><i class="fas fa-history"></i> DISCUSIONES ANTERIORES</h3>
        <div class="horizontal-scroll-wrapper">
            {% for post in posts offset:3 %}
            <div class="gamer-card-mini">
                <div class="mini-header">
                    <span class="game-tag-mini">{{ post.juego }}</span>
                </div>
                <h5 class="mt-2 text-white">{{ post.titulo | truncate: 25 }}</h5>
                <small class="text-muted">por {{ post.usuario }}</small>
            </div>
            {% endfor %}
        </div>
    </div>

</div>
