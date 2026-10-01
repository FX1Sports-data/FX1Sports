---
layout: default
title: FX1 Sports — Portal & Interactive Roadmap
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;800&display=swap" rel="stylesheet">

<style>
  /* --- LAYOUT GLOBAL & REINITIALISATION --- */
  html, body, #header_background, #main_content_wrap, #footer_wrap {
    background-color: #050811 !important;
    background-image: none !important;
    color: #94A3B8 !important;
    font-family: 'Inter', system-ui, -apple-system, sans-serif !important;
    margin: 0 !important;
    padding: 0 !important;
  }

  /* Masquer le header et footer natifs du thème pour un look App Web moderne */
  header, #header_background, footer, #footer_wrap, header section, .downloads {
    display: none !important;
  }

  #main_content, .inner {
    max-width: 100% !important;
    width: 100% !important;
    margin: 0 !important;
    padding: 0 !important;
  }

  /* --- STRUCTURE DASHBOARD (SIDEBAR + MAIN) --- */
  .fx1-dashboard {
    display: flex;
    min-height: 100vh;
  }

  /* Sidebar gauche */
  .fx1-sidebar {
    width: 260px;
    background: #0B0F19;
    border-right: 1px solid rgba(0, 229, 255, 0.15);
    padding: 24px 16px;
    display: flex;
    flex-direction: column;
    gap: 8px;
    flex-shrink: 0;
  }

  .fx1-brand {
    font-size: 1.4rem;
    font-weight: 800;
    color: #FFFFFF;
    letter-spacing: -0.02em;
    margin-bottom: 24px;
    padding-left: 12px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .fx1-brand span {
    color: #00E5FF;
    font-size: 0.8rem;
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
    padding: 12px 16px;
    border-radius: 8px;
    font-weight: 600;
    font-size: 0.9rem;
    text-align: left;
    cursor: pointer;
    transition: all 0.2s ease;
    display: flex;
    align-items: center;
    gap: 10px;
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

  /* Zone de contenu droite */
  .fx1-content {
    flex-grow: 1;
    padding: 24px 32px;
    background: #050811;
  }

  /* Topbar dans la zone de contenu */
  .fx1-topbar {
    margin-bottom: 20px;
  }

  .fx1-topbar h1 {
    color: #FFFFFF !important;
    font-size: 1.8rem !important;
    font-weight: 800 !important;
    margin: 0 0 6px 0 !important;
  }

  .fx1-topbar p {
    color: #64748B;
    margin: 0;
    font-size: 0.95rem;
  }

  /* Carte conteneur pour le SVG et les vues */
  .fx1-card {
    background: #0B0F19;
    border: 1px solid rgba(0, 229, 255, 0.2);
    border-radius: 12px;
    box-shadow: 0 0 30px rgba(0, 229, 255, 0.05);
    overflow: hidden;
  }

  /* Panneaux de contenu masqués/visibles */
  .view-panel {
    display: none;
  }

  .view-panel.active {
    display: block;
  }

  .placeholder-box {
    padding: 60px;
    text-align: center;
    color: #94A3B8;
  }

  /* Mobile responsiveness */
  @media (max-width: 768px) {
    .fx1-dashboard {
      flex-direction: column;
    }
    .fx1-sidebar {
      width: 100%;
      border-right: none;
      border-bottom: 1px solid rgba(0, 229, 255, 0.15);
    }
  }
</style>

<div class="fx1-dashboard">
  <!-- SIDEBAR GAUCHE (NAVIGATION) -->
  <aside class="fx1-sidebar">
    <div class="fx1-brand">
      FX1 <span>PROT</span>
    </div>
    
    <button class="nav-btn active" onclick="switchTab('roadmap', this)">
      🗺️️ Interactive Roadmap
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
    
    <!-- VUE 1 : ROADMAP (ACTIVE PAR DEFAUT) -->
    <div id="view-roadmap" class="view-panel active">
      <div class="fx1-topbar">
        <h1>Interactive Roadmap</h1>
        <p>Découvrez notre vision stratégique et le déploiement multi-phases de la plateforme.</p>
      </div>
      <div class="fx1-card">
        <object data="./FX1roadmap.svg?v=3" type="image/svg+xml" width="100%" height="1020px" style="width:100%; border:none; display:block;">
          <p style="padding:20px; text-align:center; color:#94A3B8;">
            Votre navigateur ne charge pas le SVG. 
            <a href="./FX1roadmap.svg?v=3" style="color:#00E5FF;">Cliquez ici pour l'ouvrir directement</a>.
          </p>
        </object>
      </div>
    </div>

    <!-- VUE 2 : PULSE AI -->
    <div id="view-pulseai" class="view-panel">
      <div class="fx1-topbar">
        <h1>PulseAI</h1>
        <p>Intelligence artificielle prédictive et analyse de données sportives en temps réel.</p>
      </div>
      <div class="fx1-card placeholder-box">
        <h2 style="color:#00E5FF;">Section PulseAI en construction</h2>
        <p>Les métriques et modules IA seront affichés ici très prochainement.</p>
      </div>
    </div>

    <!-- VUE 3 : ECOSYSTEM -->
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

    <!-- VUE 4 : ARENA -->
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

    <!-- VUE 5 : TOKEN UTILITY -->
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

    <!-- VUE 6 : STATUS & BENEFITS -->
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

    <!-- VUE 7 : LIVE DATA -->
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

    <!-- VUE 8 : DOCUMENTATION -->
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
    // 1. Masquer toutes les vues
    const views = document.querySelectorAll('.view-panel');
    views.forEach(view => view.classList.remove('active'));

    // 2. Réinitialiser l'état actif des boutons
    const buttons = document.querySelectorAll('.nav-btn');
    buttons.forEach(btn => btn.classList.remove('active'));

    // 3. Activer la vue et le bouton sélectionnés
    document.getElementById('view-' + viewId).classList.add('active');
    btnElement.classList.add('active');
  }
</script>
