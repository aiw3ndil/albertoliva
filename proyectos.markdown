---
layout: page
title: Proyectos
permalink: /proyectos/
---

<style>
  .project-container {
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    gap: 2rem;
    margin-bottom: 2rem;
    padding-bottom: 2rem;
    border-bottom: 1px dashed var(--terminal-dim);
  }
  .project-image {
    flex: 1 1 200px;
  }
  .project-image img {
    width: 100%;
    height: auto;
    border: 1px solid var(--terminal-dim);
    filter: grayscale(100%) brightness(0.8) contrast(1.2);
    transition: filter 0.3s ease;
  }
  .project-image img:hover {
    filter: none;
  }
  .project-details {
    flex: 2 1 300px;
  }
  .project-details h3 a {
    text-decoration: none;
    color: var(--terminal-text);
    text-shadow: none; /* Eliminar sombra para máxima nitidez */
  }
  .project-details h3 a:hover {
    color: #fff;
    text-shadow: 0 0 8px var(--terminal-text);
  }
  @media (max-width: 600px) {
    .project-container {
      flex-direction: column;
    }
  }
</style>

Estos son algunos proyectos que he empezado como hobby.

<div class="project-container">
  <div class="project-image">
    <a href="https://enkihost.com" target="_blank" rel="noopener noreferrer">
      <img src="/assets/images/enkimail-logo.png" alt="Logo de Enkihost" style="opacity: 0.5; filter: grayscale(100%)">
    </a>
  </div>
  <div class="project-details">
    <h3><a href="https://enkihost.com" target="_blank" rel="noopener noreferrer">Enkihost</a></h3>
    <p>Hosting especializado para Jekyll, Ruby on Rails y Sinatra.</p>
    <ul>
      <li>Despliegue automático desde repositorios públicos para sitios estáticos (Jekyll).</li>
      <li>Próximamente: Soporte completo para aplicaciones dinámicas en Ruby (Rails/Sinatra).</li>
      <li>Enfoque en simplicidad y control total de la infraestructura.</li>
    </ul>
  </div>
</div>

<div class="project-container">
  <div class="project-image">
    <a href="https://enkimail.com" target="_blank" rel="noopener noreferrer">
      <img src="/assets/images/enkimail-logo.png" alt="Logo de Enkimail">
    </a>
  </div>
  <div class="project-details">
    <h3><a href="https://enkimail.com" target="_blank" rel="noopener noreferrer">Enkimail</a></h3>
    <p>Procesador de colas para email marketing enfocado en la simplicidad y entregabilidad.</p>
    <ul>
      <li>Gestión de campañas automatizadas y sistemas de listas de suscriptores.</li>
      <li>Infraestructura propia con Postfix en Docker y optimización de protocolos de autenticación para máxima llegada a bandeja de entrada.</li>
    </ul>
  </div>
</div>

<div class="project-container">
  <div class="project-image">
    <a href="https://jombo.es" target="_blank" rel="noopener noreferrer">
      <img src="/assets/images/jombo-logo.png" alt="Logo de Jombo">
    </a>
  </div>
  <div class="project-details">
    <h3><a href="https://jombo.es" target="_blank" rel="noopener noreferrer">Jombo.es</a></h3>
    <p>Carpooling ético sin comisiones.</p>
    <ul>
      <li>Plataforma de viaje compartido para facilitar el transporte comunitario de forma directa.</li>
      <li>Arquitectura basada en API de Ruby y frontend en Next.js alojado en Vercel.</li>
    </ul>
  </div>
</div>

<div class="project-container">
  <div class="project-image">
    <a href="https://truek.xyz" target="_blank" rel="noopener noreferrer">
      <img src="/assets/images/truek-logo.png" alt="Logo de Truek.xyz">
    </a>
  </div>
  <div class="project-details">
    <h3><a href="https://truek.xyz" target="_blank" rel="noopener noreferrer">Truek.xyz</a></h3>
    <p>Plataforma de intercambio de objetos construida con Ruby (API) y Next.js.</p>
    <ul>
      <li>Implementación de lógica de intercambio, perfiles de usuario y sistemas de búsqueda avanzada.</li>
      <li>Desarrollo ágil mediante Vibe Coding y despliegue automatizado con Coolify.</li>
    </ul>
  </div>
</div>
