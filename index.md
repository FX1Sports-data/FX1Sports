---
layout: default
title: FX1 Sports — Portal & Interactive Roadmap
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;800&display=swap" rel="stylesheet">

<style>
  /* --- REINITIALISATION STRICTE DE LA PAGE ET DU THEME HACKER --- */
  html, body {
    height: 100vh !important;
    width: 100vw !important;
    overflow: hidden !important;
    background-color: #050811 !important;
    background-image: none !important;
    color: #94A3B8 !important;
    font-family: 'Inter', system-ui, -apple-system, sans-serif !important;
    margin: 0 !important;
    padding: 0 !important;
  }

  /* Neutralisation complète des conteneurs Jekyll Hacker */
  header, #header_background, footer, #footer_wrap, header section, .downloads, #downloads {
    display: none !important;
  }

  #main_content_wrap, #main_content, .inner, section {
    max-width: 100% !important;
    width: 100% !important;
    height: 100vh !important;
    margin: 0 !important;
    padding: 0 !important;
    position: absolute !important;
    top: 0 !important;
    left: 0 !important;
  }

  /* --- DASHBOARD LAYOUT PLEIN ÉCRAN --- */
  .fx1-dashboard {
    display: flex;
    height: 100vh;
    width: 100vw;
    box-sizing: border-box;
    position: absolute;
    top: 0;
    left: 0;
  }

  /* Sidebar gauche collée au bord */
  .fx1-sidebar {
    width: 250px;
    background: #0B0F19;
    border-right: 1px solid rgba(0, 229, 255, 0.15);
    padding: 16px 12px;
    display: flex;
    flex-direction: column;
    gap: 6px;
    flex-shrink: 0;
    box-sizing: border-box;
    overflow-y: auto;
  }

  .fx1-brand {
    font-size: 1.3rem;
    font-weight: 800;
    color: #FFFFFF;
    letter-spacing: -0.02em;
    margin-bottom: 12px;
    padding-left: 8px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .fx1-brand span {
    color: #00E5FF;
    font-size: 0.75rem;
    background: rgba(0, 229, 255, 0.1);
    border: 1px solid rgba(0, 229, 255, 0.3);
    padding: 2px 6px;
    border-radius: 4px;
  }

  /* Boutons de navigation */
  .nav-btn {
    background: transparent;
    border: 1px solid transparent;
    color: #E2E8F0;
    padding: 10px 14px;
    border-radius: 8px;
    font-weight: 600;
    font-size: 0.85rem;
    text-align: left;
    cursor: pointer;
    transition: all 0.2s ease;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .nav-btn:hover {
    background: rgba(0, 229, 255, 0.05);
    color: #FFFFFF;
    border-color: rgba(0, 229, 255, 0.2);
  }

  .nav-btn.active {
    background: linear-gradient(90deg, rgba(0, 229, 255, 0.15) 0%, rgba(0, 229, 255, 0) 100%);
    color: #00E5FF;
    border-left: 3px solid #00E5FF;
    border-radius: 4px 8px 8px 4px;
  }

  /* Zone de contenu principale */
  .fx1-content {
    flex-grow: 1;
    padding: 16px 20px;
    background: #050811;
    display: flex;
    flex-direction: column;
    height: 100vh;
    box-sizing: border-box;
    overflow: hidden;
  }

  /* En-tête de section */
  .fx1-topbar {
    margin-bottom: 10px;
  }

  .fx1-topbar h1 {
    color: #FFFFFF !important;
    font-size: 1.4rem !important;
    font-weight: 800 !important;
    margin: 0 0 2px 0 !important;
  }

  .fx1-topbar p {
    color: #CBD5E1;
    margin: 0;
    font-size: 0.85rem;
    line-height: 1.4;
  }

  /* Panneaux de vue */
  .view-panel {
    display: flex;
    flex-direction: column;
    height: 0;
    overflow: hidden;
    opacity: 0;
    visibility: hidden;
    pointer-events: none;
  }

  .view-panel.active {
    height: 100%;
    opacity: 1;
    visibility: visible;
    pointer-events: auto;
  }

  /* Conteneur de la carte SVG / Images / Landing */
  .fx1-card {
    background: #0B0F19;
    border: 1px solid rgba(0, 229, 255, 0.2);
    border-radius: 10px;
    box-shadow: 0 0 25px rgba(0, 229, 255, 0.05);
    overflow: hidden;
    flex-grow: 1;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    max-height: calc(100vh - 80px);
    overflow-y: auto;
  }

  .fx1-card object,
  .fx1-card img,
  .fx1-card iframe {
    width: 100%;
    height: 100%;
    border: none;
    display: block;
    object-fit: contain;
  }

  /* Style spécifique pour la Landing Page interne */
  .landing-container {
    padding: 30px;
    max-width: 1100px;
    width: 100%;
    box-sizing: border-box;
    text-align: left;
    display: flex;
    flex-direction: column;
    gap: 24px;
    margin: auto;
  }

  .landing-hero {
    display: grid;
    grid-template-columns: 1.2fr 0.8fr;
    gap: 30px;
    align-items: center;
  }

  /* Style du gros logo FX1 */
  .landing-logo {
    height: 52px;
    width: auto;
    margin-bottom: 16px;
    display: block;
    object-fit: contain;
  }

  .landing-text h2 {
    color: #FFFFFF;
    font-size: 2rem;
    font-weight: 800;
    margin: 0 0 12px 0;
    letter-spacing: -0.02em;
    line-height: 1.2;
  }

  .landing-text h2 span {
    color: #00E5FF;
  }

  .landing-text p {
    color: #94A3B8;
    font-size: 1rem;
    line-height: 1.6;
    margin-bottom: 20px;
  }

  .landing-cta-group {
    display: flex;
    gap: 12px;
  }

  .btn-primary {
    background: #00E5FF;
    color: #050811;
    padding: 10px 20px;
    border-radius: 6px;
    font-weight: 700;
    font-size: 0.9rem;
    border: none;
    cursor: pointer;
    text-decoration: none;
    transition: opacity 0.2s;
  }

  .btn-primary:hover {
    opacity: 0.9;
  }

  .btn-secondary {
    background: rgba(0, 229, 255, 0.1);
    color: #00E5FF;
    padding: 10px 20px;
    border-radius: 6px;
    font-weight: 700;
    font-size: 0.9rem;
    border: 1px solid rgba(0, 229, 255, 0.3);
    cursor: pointer;
    text-decoration: none;
    transition: background 0.2s;
  }

  .btn-secondary:hover {
    background: rgba(0, 229, 255, 0.2);
  }

  /* Conteneur Vidéo Natif */
  .landing-media-wrapper {
    display: flex;
    flex-direction: column;
    gap: 8px;
  }

  .landing-media {
    background: rgba(5, 8, 17, 0.9);
    border: 1px solid rgba(0, 229, 255, 0.3);
    border-radius: 12px;
    overflow: hidden;
    aspect-ratio: 16/9;
    display: flex;
    align-items: center;
    justify-content: center;
    box-shadow: 0 0 20px rgba(0, 229, 255, 0.1);
  }

  .landing-media video {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  .twitter-link-hint {
    text-align: right;
    font-size: 0.75rem;
  }

  .twitter-link-hint a {
    color: #64748B;
    text-decoration: none;
    transition: color 0.2s;
  }

  .twitter-link-hint a:hover {
    color: #00E5FF;
  }

  /* Grille des fonctionnalités clés sur la landing */
  .landing-features {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 16px;
  }

  .feature-box {
    background: rgba(11, 15, 25, 0.8);
    border: 1px solid rgba(255, 255, 255, 0.05);
    padding: 16px;
    border-radius: 8px;
    transition: border-color 0.2s;
  }

  .feature-box:hover {
    border-color: rgba(0, 229, 255, 0.4);
  }

  .feature-box h4 {
    color: #FFFFFF;
    margin: 0 0 6px 0;
    font-size: 1rem;
    display: flex;
    align-items: center;
    gap: 6px;
  }

  .feature-box p {
    color: #94A3B8;
    font-size: 0.82rem;
    margin: 0;
    line-height: 1.4;
  }

  .placeholder-box {
    padding: 40px;
    text-align: center;
    color: #E2E8F0;
  }

  /* Adaptation mobile */
  @media (max-width: 900px) {
    .landing-hero {
      grid-template-columns: 1fr;
    }
    .landing-features {
      grid-template-columns: 1fr;
    }
    html, body {
      overflow: auto !important;
      height: auto !important;
    }
    .fx1-dashboard {
      flex-direction: column;
      position: relative;
      height: auto;
    }
    .fx1-sidebar {
      width: 100%;
      border-right: none;
      border-bottom: 1px solid rgba(0, 229, 255, 0.15);
    }
    .fx1-card {
      height: auto;
      max-height: none;
    }
  }
</style>

<div class="fx1-dashboard">
  <!-- SIDEBAR GAUCHE -->
  <aside class="fx1-sidebar">
    <div class="fx1-brand">
      FX1 <span>PROT</span>
    </div>
    
    <button class="nav-btn active" onclick="switchTab('overview', this)">
      🚀 Overview
    </button>
    <button class="nav-btn" onclick="switchTab('ecosystem', this)">
      🌐 Ecosystem
    </button>
    <button class="nav-btn" onclick="switchTab('roadmap', this)">
      🗺 Interactive Roadmap
    </button>
    <button class="nav-btn" onclick="switchTab('arena', this)">
      🏟️ Arena
    </button>
    <button class="nav-btn" onclick="switchTab('token', this)">
      🪙 Token Utility
    </button>
    <button class="nav-btn" onclick="switchTab('status', this)">
      ⭐ Status & Benefits
    </button>
    <button class="nav-btn" onclick="switchTab('pulseai', this)">
      ⚡ PulseAI
    </button>
    <button class="nav-btn" onclick="switchTab('docs', this)">
      📄 Documentation
    </button>
  </aside>

  <!-- CONTENU PRINCIPAL A DROITE -->
  <main class="fx1-content">
    
    <!-- OVERVIEW / LANDING PAGE -->
    <div id="view-overview" class="view-panel active">
      <div class="fx1-topbar">
        <h1>Project Overview</h1>
        <p>Discover the core engine powering the next generation of sports engagement and AI data.</p>
      </div>
      <div class="fx1-card">
        <div class="landing-container">
          <!-- Hero Section -->
          <div class="landing-hero">
            <div class="landing-text">
              <!-- LOGO FX1 AJOUTÉ ICI -->
              <img src="{{ '/FX1logo.webp' | relative_url }}" alt="FX1 Sports Logo" class="landing-logo">
              
              <h2>Bridging <span>Fan Engagement</span> & AI Data</h2>
              <p>FX1 transforms everyday sports fandom into productive AI validation and real-world B2B revenue. Play games, make predictions, and unlock incredible real-world rewards—all with zero crypto friction.</p>
              <div class="landing-cta-group">
                <button class="btn-primary" onclick="switchTab('ecosystem', document.querySelectorAll('.nav-btn')[1])">Explore Ecosystem</button>
                <button class="btn-secondary" onclick="switchTab('roadmap', document.querySelectorAll('.nav-btn')[2])">View Roadmap</button>
              </div>
            </div>
            
            <!-- Bloc Vidéo Natif (FX1intro.mp4) -->
            <div class="landing-media-wrapper">
              <div class="landing-media">
                <video src="{{ '/FX1intro.mp4' | relative_url }}" autoplay loop muted playsinline controls></video>
              </div>
              <div class="twitter-link-hint">
                <a href="https://x.com/FX1Sports/status/2010963902679695518" target="_blank">Voir le post original sur X ↗</a>
              </div>
            </div>
          </div>

          <!-- Feature Cards / Aperçu rapide -->
          <div class="landing-features">
            <div class="feature-box" onclick="switchTab('arena', document.querySelectorAll('.nav-btn')[3])" style="cursor: pointer;">
              <h4>🏟️ FX1 Arena</h4>
              <p>Gamified predictions, trivia, and head-to-head fan battles fueled by MotionAI live data.</p>
            </div>
            <div class="feature-box" onclick="switchTab('pulseai', document.querySelectorAll('.nav-btn')[6])" style="cursor: pointer;">
              <h4>⚡ PulseAI SaaS</h4>
              <p>Automated personalized content creation for athletes, creators, and combat sports promotions.</p>
            </div>
            <div class="feature-box" onclick="switchTab('token', document.querySelectorAll('.nav-btn')[4])" style="cursor: pointer;">
              <h4>🪙 Token Utility</h4>
              <p>A self-sustaining utility loop anchored to real operating revenues, buybacks, and ecosystem rewards.</p>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- ECOSYSTEM -->
    <div id="view-ecosystem" class="view-panel">
      <div class="fx1-topbar">
        <h1>Ecosystem</h1>
        <p>The FX1 Ecosystem connects fan engagement, AI data training, and real commercial revenue lines into a single, self-sustaining network.</p>
      </div>
      <div class="fx1-card">
        <object data="{{ '/FX1ecosystem.svg' | relative_url }}?v=1" type="image/svg+xml">
          <p style="padding:20px; text-align:center; color:#E2E8F0;">
            Votre navigateur ne charge pas le SVG. 
            <a href="{{ '/FX1ecosystem.svg' | relative_url }}?v=1" style="color:#00E5FF;">Cliquez ici pour l'ouvrir directement</a>.
          </p>
        </object>
      </div>
    </div>

    <!-- ROADMAP -->
    <div id="view-roadmap" class="view-panel">
      <div class="fx1-topbar">
        <h1>Interactive Roadmap</h1>
        <p>Discover our strategic vision and the multi-phased rollout of the platform.</p>
      </div>
      <div class="fx1-card">
        <object data="{{ '/FX1roadmap.svg' | relative_url }}?v=5" type="image/svg+xml">
          <p style="padding:20px; text-align:center; color:#E2E8F0;">
            Votre navigateur ne charge pas le SVG. 
            <a href="{{ '/FX1roadmap.svg' | relative_url }}?v=5" style="color:#00E5FF;">Cliquez ici pour l'ouvrir directement</a>.
          </p>
        </object>
      </div>
    </div>

    <!-- ARENA -->
    <div id="view-arena" class="view-panel">
      <div class="fx1-topbar">
        <h1>FX1 Arena</h1>
        <p>FX1 Arena blends gamified fan experiences—predictions, battles, and trivia—with live AI data training to deliver real-world rewards.</p>
      </div>
      <div class="fx1-card">
        <object data="{{ '/FX1arena.svg' | relative_url }}?v=1" type="image/svg+xml">
          <p style="padding:20px; text-align:center; color:#E2E8F0;">
            Votre navigateur ne charge pas le SVG. 
            <a href="{{ '/FX1arena.svg' | relative_url }}?v=1" style="color:#00E5FF;">Cliquez ici pour l'ouvrir directement</a>.
          </p>
        </object>
      </div>
    </div>

    <!-- TOKEN UTILITY -->
    <div id="view-token" class="view-panel">
      <div class="fx1-topbar">
        <h1>Token Utility</h1>
        <p>The $FXI token fuels a self-sustaining utility loop—linking gameplay, AI validation, and real commercial revenues.</p>
      </div>
      <div class="fx1-card">
        <object data="{{ '/FX1utility.svg' | relative_url }}?v=1" type="image/svg+xml">
          <p style="padding:20px; text-align:center; color:#E2E8F0;">
            Votre navigateur ne charge pas le SVG. 
            <a href="{{ '/FX1utility.svg' | relative_url }}?v=1" style="color:#00E5FF;">Cliquez ici pour l'ouvrir directement</a>.
          </p>
        </object>
      </div>
    </div>

    <!-- STATUS & BENEFITS -->
    <div id="view-status" class="view-panel">
      <div class="fx1-topbar">
        <h1>Status & Benefits</h1>
        <p>Our ecosystem permanently rewards early supporters with exclusive OG benefits, while allowing new users to dynamically build their status.</p>
      </div>
      <div class="fx1-card">
        <object data="{{ '/FX1status.svg' | relative_url }}?v=1" type="image/svg+xml">
          <p style="padding:20px; text-align:center; color:#E2E8F0;">
            Votre navigateur ne charge pas le SVG. 
            <a href="{{ '/FX1status.svg' | relative_url }}?v=1" style="color:#00E5FF;">Cliquez ici pour l'ouvrir directement</a>.
          </p>
        </object>
      </div>
    </div>

    <!-- PULSE AI -->
    <div id="view-pulseai" class="view-panel">
      <div class="fx1-topbar">
        <h1>PulseAI</h1>
        <p>FX1 Pulse is an AI-powered SaaS platform engineered to automate personalized content creation for athletes and media.</p>
      </div>
      <div class="fx1-card">
        <object data="{{ '/FX1pulse.svg' | relative_url }}?v=1" type="image/svg+xml">
          <p style="padding:20px; text-align:center; color:#E2E8F0;">
            Votre navigateur ne charge pas le SVG. 
            <a href="{{ '/FX1pulse.svg' | relative_url }}?v=1" style="color:#00E5FF;">Cliquez ici pour l'ouvrir directement</a>.
          </p>
        </object>
      </div>
    </div>

    <!-- DOCUMENTATION -->
    <div id="view-docs" class="view-panel">
      <div class="fx1-topbar">
        <h1>Documentation</h1>
        <p>Whitepaper, technical guides and documentation.</p>
      </div>
      <div class="fx1-card placeholder-box">
        <h2 style="color:#00E5FF;">Docs & Whitepaper</h2>
        <p>Consult FX1's technical resources</p>
      </div>
    </div>

  </main>
</div>

<script>
  function switchTab(viewId, btnElement) {
    const views = document.querySelectorAll('.view-panel');
    views.forEach(view => view.classList.remove('active'));

    const buttons = document.querySelectorAll('.nav-btn');
    buttons.forEach(btn => btn.classList.remove('active'));

    document.getElementById('view-' + viewId).classList.add('active');
    btnElement.classList.add('active');
  }
</script>
