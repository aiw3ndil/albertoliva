---
layout: page
title: Projects
permalink: /projects/
---

<style>
  .project-container {
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    gap: 2rem;
    margin-bottom: 2rem;
    padding-bottom: 2rem;
    border-bottom: 1px dashed var(--border-color);
  }
  .project-image {
    flex: 1 1 200px;
  }
  .project-image img {
    width: 100%;
    height: auto;
    border: 1px solid var(--border-color);
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
    color: var(--text-primary);
  }
  .project-details h3 a:hover {
    color: var(--accent-color);
    text-decoration: underline;
  }
  @media (max-width: 600px) {
    .project-container {
      flex-direction: column;
    }
  }
</style>

These are some projects I have started as a hobby.

<div class="project-container">
  <div class="project-image">
    <a href="https://enkihost.com" target="_blank" rel="noopener noreferrer">
      <img src="/assets/images/enkihost.png" alt="Enkihost Screenshot">
    </a>
  </div>
  <div class="project-details">
    <h3><a href="https://enkihost.com" target="_blank" rel="noopener noreferrer">Enkihost</a></h3>
    <p>Specialized hosting for Jekyll, Ruby on Rails, and Sinatra.</p>
    <ul>
      <li>Automatic deployment from public repositories for static sites (Jekyll).</li>
      <li>Coming soon: Full support for dynamic Ruby applications (Rails/Sinatra).</li>
      <li>Focused on simplicity and complete infrastructure control.</li>
    </ul>
  </div>
</div>

<div class="project-container">
  <div class="project-image">
    <a href="https://enkimail.com" target="_blank" rel="noopener noreferrer">
      <img src="/assets/images/enkimail.png" alt="Enkimail Screenshot">
    </a>
  </div>
  <div class="project-details">
    <h3><a href="https://enkimail.com" target="_blank" rel="noopener noreferrer">Enkimail</a></h3>
    <p>Queue processor for email marketing focused on simplicity and deliverability.</p>
    <ul>
      <li>Automated campaign management and subscriber list systems.</li>
      <li>Self-hosted infrastructure with Postfix on Docker and authentication protocol optimization for maximum inbox deliverability.</li>
    </ul>
  </div>
</div>

<div class="project-container">
  <div class="project-image">
    <a href="https://jombo.es" target="_blank" rel="noopener noreferrer">
      <img src="/assets/images/jombo.png" alt="Jombo.es Screenshot">
    </a>
  </div>
  <div class="project-details">
    <h3><a href="https://jombo.es" target="_blank" rel="noopener noreferrer">Jombo.es</a></h3>
    <p>Ethical carpooling without commission fees.</p>
    <ul>
      <li>Ridesharing platform designed to facilitate direct, community-driven transportation.</li>
      <li>Architecture built on a Ruby API and a Next.js frontend hosted on Vercel.</li>
    </ul>
  </div>
</div>

<div class="project-container">
  <div class="project-image">
    <a href="https://truek.xyz" target="_blank" rel="noopener noreferrer">
      <img src="/assets/images/truek.png" alt="Truek.xyz Screenshot">
    </a>
  </div>
  <div class="project-details">
    <h3><a href="https://truek.xyz" target="_blank" rel="noopener noreferrer">Truek.xyz</a></h3>
    <p>Item exchange and bartering platform built with Ruby (API) and Next.js.</p>
    <ul>
      <li>Implementation of trade mechanics, user profiles, and advanced search systems.</li>
      <li>Agile development via Vibe Coding and automated deployment with Coolify.</li>
    </ul>
  </div>
</div>
