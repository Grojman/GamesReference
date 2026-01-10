---
layout: default
title: Juegos
permalink: /juegos.html
---

<div class="container my-4">
  <div class="row" id="games-container">

    <div class="col-12 mb-4">
      <div class="p-3 bg-dark text-white d-flex align-items-center rounded shadow-sm">
        <h2 class="h4 m-0 text-uppercase font-weight-bold" style="letter-spacing: 1px;">
          <span style="color: #ffc107;">★</span><span id="games-title">FAMOSOS / DESTACADOS</span>
        </h2>
      </div>
      <div style="height: 4px; background: linear-gradient(90deg, #ffc107 0%, #343a40 100%); width: 100%;"></div>
    </div>
<!-- 
    {% assign games = site.data.metadata %}
    {%- assign items = site.data[site.metadata] | where_exp: 'item','item.objectid' -%}

    
    {% if games.size > 0 %}
      {% for item in items limit:3 %}
      <div class="col-md-4 mb-4">
        <div class="card h-100 shadow border-0 hover-effect">
          
          <div class="position-relative" style="height: 205px; overflow: hidden; background-color: #212529;">
            <a href="{{ '/game-displayer.html' | relative_url }}?id={{ item.objectid }}">
              <img src="{{ '/objects/' | relative_url }}{{ item.filename }}" 
                   class="card-img-top w-100 h-100" 
                   style="object-fit: cover; transition: transform 0.3s;" 
                   alt="{{ item.title }}"
                   onmouseover="this.style.transform='scale(1.1)'"
                   onmouseout="this.style.transform='scale(1)'">
            </a>
            {% if item.genero %}
            <div class="position-absolute top-0 right-0 m-2">
              <span class="badge badge-warning text-dark shadow-sm">{{ item.genero }}</span>
            </div>
            {% endif %}
          </div>

          <div class="card-body d-flex flex-column">
            <h5 class="card-title font-weight-bold text-uppercase mb-2">
              <a href="{{ '/game-displayer.html' | relative_url }}?id={{ item.objectid }}" class="text-dark text-decoration-none">
                {{ item.title }}
              </a>
            </h5>
            
            <div class="mb-3 small text-muted">
              {% if item.narrativa %}
                <div class="mb-1"><span class="mr-2">📖</span> {{ item.narrativa | truncate: 35 }}</div>
              {% endif %}
              {% if item.musica %}
                <div><span class="mr-2">🎵</span> {{ item.musica | truncate: 35 }}</div>
              {% endif %}
            </div>
            
            <div class="mt-auto pt-2 border-top">
               <a href="{{ '/game-displayer.html' | relative_url }}?id={{ item.objectid }}" class="btn btn-sm btn-outline-dark w-100">Ver Ficha</a>
            </div>
          </div>
        </div>
      </div>
      {% endfor %}
    
    {% else %}
      <div class="col-12 text-center py-5">
        <p class="text-muted">No se encontraron juegos en _data/metadata.csv</p>
      </div>
    {% endif %} -->

  </div>
</div>

<script>
    var cb_items = [
        {%- for item in items -%}
        {
        "objectid": {{ item.objectid | jsonify }},
        "filename": {{ item.filename | default: "" | jsonify }},
        "title": {{ item.title | default: "" | jsonify }},
        "format": {{ item.format | default: "" | jsonify }},
        "latitude": {{ item.latitude | default: "" | jsonify }},
        "longitude": {{ item.longitude | default: "" | jsonify }},
        "genero": {{ item.genero | default: "" | jsonify }},
        "narrativa": {{ item.narrativa | default: "" | jsonify }},
        "musica": {{ item.musica | default: "" | jsonify }},
        "innovador": {{ item.innovador | default: "" | jsonify }},
        "description": {{ item.description | default: "" | jsonify }},
        "narrative_text": {{ item.narrative_text | default: "" | jsonify }},
        "music_text": {{ item.music_text | default: "" | jsonify }},
        "graphics_text": {{ item.graphics_text | default: "" | jsonify }}
        }{% unless forloop.last %},{% endunless %}
        {%- endfor -%}
        ];

    function translate(a) {
        switch (a)
        {
            case "genero":
                return "Género";
            case "musica":
                return "Música";
            case "narrativa":
                return "Narrativa";
            case "estetica":
                return "Estética";
        }
    }

    let url = new URL(window.location);
    var itemPageId = url.searchParams.get('by');

    var records = itemPageId == null ? cb_items : cb_items.filter(item => item.innovador == itemPageId);

    document.querySelector('#games-title').textContent = itemPageId == null ? "Todos los juegos" : "Juegos por " + translate(itemPageId);

    const container = document.getElementById("games-container");

  if (records && records.length > 0) {
    records.forEach(item => {

      const col = document.createElement("div");
      col.className = "col-md-4 mb-4";

      col.innerHTML = `
        <div class="card h-100 shadow border-0 hover-effect">

          <div class="position-relative" style="height: 190px; overflow: hidden; background-color: #212529;">
            <a href="/game-displayer.html?id=${item.objectid}">
              <img src="/objects/${item.filename || ""}"
                   class="card-img-top w-100 h-100"
                   style="object-fit: cover; transition: transform 0.3s;"
                   alt="${item.title || ""}"
                   onmouseover="this.style.transform='scale(1.02)'"
                   onmouseout="this.style.transform='scale(1)'">
            </a>

            ${item.genero ? `
              <div class="position-absolute top-0 right-0 m-2">
                <span class="badge badge-warning text-dark shadow-sm">${item.genero}</span>
              </div>
            ` : ""}
          </div>

          <div class="card-body d-flex flex-column">
            <h5 class="card-title font-weight-bold text-uppercase mb-2">
              <a href="/game-displayer.html?id=${item.objectid}"
                 class="text-dark text-decoration-none">
                ${item.title || ""}
              </a>
            </h5>

            <div class="mb-3 small text-muted">
              ${item.narrativa ? `
                <div class="mb-1">
                  <span class="mr-2">📖</span>
                  ${truncate(item.narrativa, 35)}
                </div>
              ` : ""}

              ${item.musica ? `
                <div>
                  <span class="mr-2">🎵</span>
                  ${truncate(item.musica, 35)}
                </div>
              ` : ""}
            </div>

            <div class="mt-auto pt-2 border-top">
              <a href="/game-displayer.html?id=${item.objectid}"
                 class="btn btn-sm btn-outline-dark w-100">
                Ver Ficha
              </a>
            </div>
          </div>

        </div>
      `;

      container.appendChild(col);
    });

  } else {
    container.innerHTML = `
      <div class="col-12 text-center py-5">
        <p class="text-muted">No se encontraron juegos en _data/metadata.csv</p>
      </div>
    `;
  }

  // Función auxiliar equivalente a | truncate: 35
  function truncate(text, length) {
    if (!text) return "";
    return text.length > length
      ? text.substring(0, length) + "…"
      : text;
  }
</script>