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
    color: #94A3B8;
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
    color: #64748B;
    margin: 0;
    font-size: 0.85rem;
  }

  /* Panneaux de vue */
  .view-panel {
    display: none;
    height: 100%;
    flex-direction: column;
  }

  .view-panel.active {
    display: flex;
  }

  /* Conteneur de la carte SVG / Images */
  .fx1-card {
    background: #0B0F19;
    border: 1px solid rgba(0, 229, 255, 0.2);
    border-radius: 10px;
    box-shadow: 0 0 25px rgba(0, 229, 255, 0.05);
    overflow: hidden;
    flex-grow: 1;
    display: flex;
    align-items: center;
    justify-content: center;
    max-height: calc(100vh - 80px);
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

  .placeholder-box {
    padding: 40px;
    text-align: center;
    color: #94A3B8;
  }

  /* Adaptation mobile */
  @media (max-width: 768px) {
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
      height: 80vh;
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
    
    <button class="nav-btn active" onclick="switchTab('roadmap', this)">
      🗺 Interactive Roadmap
    </button>
    <button class="nav-btn" onclick="switchTab('pulseai', this)">
      ⚡ PulseAI
    </button>
    <button class="nav-btn" onclick="switchTab('ecosystem', this)">
      🌐 Ecosystem
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
    <button class="nav-btn" onclick="switchTab('data', this)">
      📊 Live Data
    </button>
    <button class="nav-btn" onclick="switchTab('docs', this)">
      📄 Documentation
    </button>
  </aside>

  <!-- CONTENU PRINCIPAL A DROITE -->
  <main class="fx1-content">
    
    <!-- ROADMAP -->
    <div id="view-roadmap" class="view-panel active">
      <div class="fx1-topbar">
        <h1>Interactive Roadmap</h1>
        <p>Discover our strategic vision and the multi-phased rollout of the platform.</p>
      </div>
      <div class="fx1-card">
        <object data="{{ '/FX1roadmap.svg' | relative_url }}?v=5" type="image/svg+xml">
          <p style="padding:20px; text-align:center; color:#94A3B8;">
            Votre navigateur ne charge pas le SVG. 
            <a href="{{ '/FX1roadmap.svg' | relative_url }}?v=5" style="color:#00E5FF;">Cliquez ici pour l'ouvrir directement</a>.
          </p>
        </object>
      </div>
    </div>

    <!-- PULSE AI -->
    <div id="view-pulseai" class="view-panel">
      <div class="fx1-topbar">
        <h1>PulseAI</h1>
        <p>Intelligence artificielle prédictive et analyse de données sportives en temps réel.</p>
      </div>
      <div class="fx1-card">
        <object data="{{ '/FX1pulseai.svg' | relative_url }}?v=1" type="image/svg+xml">
          <p style="padding:20px; text-align:center; color:#94A3B8;">
            Votre navigateur ne charge pas le SVG. 
            <a href="{{ '/FX1pulseai.svg' | relative_url }}?v=1" style="color:#00E5FF;">Cliquez ici pour l'ouvrir directement</a>.
          </p>
        </object>
      </div>
    </div>

    <!-- ECOSYSTEM -->
    <div id="view-ecosystem" class="view-panel">
      <div class="fx1-topbar">
        <h1>Ecosystem</h1>
        <p>Aperçu global du réseau de partenaires et des intégrations FX1.</p>
      </div>
      <div class="fx1-card placeholder-box">
        <h2 style="color:#00E5FF;">Écosystème FX1</h2>
        <p>Détails sur l'architecture décentralisée à venir.</p>
      </div>
    </div>

    <!-- ARENA -->
    <div id="view-arena" class="view-panel">
      <div class="fx1-topbar">
        <h1>FX1 Arena</h1>
        <p>Plateforme de compétition et d'engagement de la communauté.</p>
      </div>
      <div class="fx1-card placeholder-box">
        <h2 style="color:#00E5FF;">FX1 Arena</h2>
        <p>Inscriptions et tournois à venir.</p>
      </div>
    </div>

    <!-- TOKEN UTILITY -->
    <div id="view-token" class="view-panel">
      <div class="fx1-topbar">
        <h1>Token Utility</h1>
        <p>Utilisation, staking et gouvernance du jeton natif FX1.</p>
      </div>
      <div class="fx1-card placeholder-box">
        <h2 style="color:#00E5FF;">Tokenomics & Staking</h2>
        <p>Informations stratégiques sur le token.</p>
      </div>
    </div>

    <!-- STATUS & BENEFITS -->
    <div id="view-status" class="view-panel">
      <div class="fx1-topbar">
        <h1>Status & Benefits</h1>
        <p>Niveaux de membre, privilèges VIP et avantages pour les détenteurs.</p>
      </div>
      <div class="fx1-card placeholder-box">
        <h2 style="color:#00E5FF;">Programme VIP / Status</h2>
        <p>Grille des avantages par niveau.</p>
      </div>
    </div>

    <!-- LIVE DATA -->
    <div id="view-data" class="view-panel">
      <div class="fx1-topbar">
        <h1>Live Data</h1>
        <p>Flux de données sportives directes.</p>
      </div>
      <div class="fx1-card placeholder-box">
        <h2 style="color:#00E5FF;">Flux Sportifs</h2>
        <p>Connexions aux API directes.</p>
      </div>
    </div>

    <!-- DOCUMENTATION -->
    <div id="view-docs" class="view-panel">
      <div class="fx1-topbar">
        <h1>Documentation</h1>
        <p>Whitepaper, guides techniques et documentation de l'API.</p>
      </div>
      <div class="fx1-card placeholder-box">
        <h2 style="color:#00E5FF;">Docs & Whitepaper</h2>
        <p>Consultez les ressources techniques de FX1.</p>
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
