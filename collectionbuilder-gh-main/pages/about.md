---
title: Sobre Nosotros
layout: default
permalink: /about.html
---

<style>
  /* Custom Styles for About Us Page */
  .about-hero {
    background: linear-gradient(135deg, #212529 0%, #343a40 100%);
    color: white;
    padding: 60px 20px;
    text-align: center;
    border-radius: 0 0 20px 20px;
    margin-bottom: 40px;
  }
  
  .about-hero h1 {
    font-weight: 700;
    text-transform: uppercase;
    margin-bottom: 20px;
    letter-spacing: 2px;
  }
  
  .about-hero p {
    font-size: 1.2rem;
    max-width: 800px;
    margin: 0 auto;
    opacity: 0.9;
  }

  .mission-section {
    text-align: center;
    padding: 40px 20px;
    background-color: #f8f9fa;
    border-radius: 15px;
    margin-bottom: 50px;
    box-shadow: 0 4px 15px rgba(0,0,0,0.05);
  }

  .mission-section h2 {
    color: #343a40;
    font-weight: 700;
    margin-bottom: 20px;
    text-transform: uppercase;
  }

  .mission-quote {
    font-size: 1.5rem;
    font-style: italic;
    color: #495057;
    font-family: 'Georgia', serif;
    position: relative;
    padding: 0 40px;
  }
  
  .team-section {
    margin-bottom: 60px;
  }
  
  .team-section h2 {
    text-align: center;
    margin-bottom: 40px;
    font-weight: 700;
    text-transform: uppercase;
    color: white;
  }

  .team-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 30px;
  }

  .team-card {
    background: white;
    border-radius: 15px;
    overflow: hidden;
    box-shadow: 0 5px 15px rgba(0,0,0,0.1);
    transition: transform 0.3s ease;
    text-align: center;
    padding: 30px 20px;
  }

  .team-card:hover {
    transform: translateY(-10px);
  }

  .team-avatar {
    width: 160px;
    height: 160px;
    background-color: transparent;
    border-radius: 50%;
    margin: 0 auto 20px;
    display: flex;
    align-items: center;
    justify-content: center;
    overflow: hidden;
  }
  
  .team-avatar img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  .team-name {
    font-weight: 700;
    font-size: 1.2rem;
    margin-bottom: 5px;
    color: #212529;
  }

  .team-role {
    color: #6c757d;
    font-size: 0.9rem;
    text-transform: uppercase;
    letter-spacing: 1px;
    margin-bottom: 15px;
  }

  .context-section {
    background-color: #212529;
    color: white;
    padding: 40px;
    border-radius: 15px;
    margin-bottom: 50px;
  }
  
  .context-section h3 {
    font-weight: 700;
    margin-bottom: 15px;
    color: #ffc107;
  }

  .cta-section {
    text-align: center;
    margin-bottom: 60px;
  }

  .btn-custom-cta {
    background-color: #ffc107;
    color: #212529;
    padding: 15px 40px;
    font-size: 1.2rem;
    font-weight: 700;
    text-transform: uppercase;
    border-radius: 50px;
    text-decoration: none;
    transition: all 0.3s ease;
    display: inline-block;
    box-shadow: 0 4px 10px rgba(255, 193, 7, 0.4);
  }

  .btn-custom-cta:hover {
    background-color: #e0a800;
    transform: scale(1.05);
    color: #212529;
    text-decoration: none;
  }

</style>

<div class="about-hero">
  <h1>Games Reference</h1>
  <p>Explorando la historia, el arte y la innovación del videojuego.</p>
</div>

<div class="container">

  <!-- Mission Section -->
  <section class="mission-section">
    <h2>Nuestra Misión</h2>
    <p class="mission-quote">
      "Recopilar juegos que sirvan de inspiración para nuevos desarrolladores indie."
    </p>
  </section>

  <!-- Team Section -->
  <section class="team-section">
    <h2>El Equipo</h2>
    <div class="team-grid">
      
      <!-- Card 1 -->
      <div class="team-card">
        <div class="team-avatar">
          <img src="{{ '/assets/img/lucas.png' | relative_url }}" alt="Lucas Vera Amorós">
        </div>
        <h3 class="team-name">Lucas Vera Amorós</h3>
        <p class="team-role">Gestión y Desarrollo</p>
      </div>

      <!-- Card 2 -->
      <div class="team-card">
        <div class="team-avatar">
          <img src="{{ '/assets/img/pau.png' | relative_url }}" alt="Pau Cremades García">
        </div>
        <h3 class="team-name">Pau Cremades García</h3>
        <p class="team-role">Diseño y Desarrollo</p>
      </div>

      <!-- Card 3 -->
      <div class="team-card">
        <div class="team-avatar">
          <img src="{{ '/assets/img/jorge.png' | relative_url }}" alt="Jorge Gomis Román">
        </div>
        <h3 class="team-name">Jorge Gomis Román</h3>
        <p class="team-role">Documentación y Desarrollo</p>
      </div>

    </div>
  </section>

  <!-- Context Section -->
  <section class="context-section">
    <div class="row align-items-center">
      <div class="col-md-12 text-center">
        <h3>Contexto Académico</h3>
        <p>
          Este proyecto ha sido desarrollado por estudiantes de <strong>2º curso de Ingeniería Multimedia</strong> 
          en la Universidad de Alicante (UA), como parte de la asignatura <em>Estructuración de Contenidos</em>.
        </p>
        <p class="mb-0 small text-muted">UA - Universidad de Alicante</p>
      </div>
    </div>
  </section>

  <!-- CTA Section -->
  <section class="cta-section">
    <h2 class="h4 mb-4">¿Buscas inspiración para tu próximo proyecto?</h2>
    <a href="{{ '/browse.html' | relative_url }}" class="btn-custom-cta">Explora el Catálogo</a>
  </section>

</div>
