---
layout: default
title: FX1 Sports — Interactive Roadmap
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;800&display=swap" rel="stylesheet">

<style>
  /* --- FORCAGE IDENTITÉ VISUELLE FX1 --- */

  /* Fond global et typographie */
  html, body, #header_background, #main_content_wrap, #footer_wrap {
    background-color: #050811 !important;
    background-image: none !important;
    color: #94A3B8 !important;
    font-family: 'Inter', system-ui, -apple-system, sans-serif !important;
  }

  /* Header FX1 */
  header, #header_background {
    background: linear-gradient(180deg, #0b0f19 0%, #050811 100%) !important;
    border-bottom: 1px solid rgba(0, 229, 255, 0.2) !important;
    padding: 25px 0 !important;
  }

  /* Titre principal */
  header h1, #header_background h1, h1 {
    color: #FFFFFF !important;
    font-weight: 800 !important;
    text-transform: uppercase !important;
    letter-spacing: -0.02em !important;
    text-shadow: 0 0 15px rgba(0, 229, 255, 0.4) !important;
  }

  /* Masquer tous les boutons GitHub du thème */
  header section, header .button, header a.buttons, header a[href*="github.com"], .downloads, #downloads {
    display: none !important;
  }

  /* Zone de contenu principal */
  #main_content, .inner {
    max-width: 1200px !important;
    margin: 0 auto !important;
    padding: 10px 20px !important;
  }

  /* Encadrement style App / Neon pour la Roadmap */
  .fx1-card {
    background: #0b0f19;
    border: 1px solid rgba(0, 229, 255, 0.25);
    border-radius: 12px;
    box-shadow: 0 0 25px rgba(0, 229, 255, 0.08);
    overflow: hidden;
    margin: 20px 0;
  }

  /* Footer */
  footer, #footer_wrap {
    border-top: 1px solid rgba(255, 255, 255, 0.05) !important;
    color: #64748B !important;
  }
</style>

<div class="fx1-card">
  <object data="./FX1roadmap.svg?v=2" type="image/svg+xml" width="100%" height="1020px" style="width:100%; border:none; display:block;">
    <p style="padding:20px; text-align:center;">
      Votre navigateur ne charge pas le SVG. 
      <a href="./FX1roadmap.svg?v=2" style="color:#00E5FF;">Cliquez ici pour l'ouvrir directement</a>.
    </p>
  </object>
</div>

---

*FX1 — AI-Powered Decentralized Sports Data Platform*
