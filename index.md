---
layout: default
title: FX1 Sports — Interactive Roadmap
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;800&display=swap" rel="stylesheet">

<style>
  /* --- REWRITING THEME HACKER STYLES FOR FX1 BRAND --- */
  
  /* Background & Global Typography */
  body {
    background-color: #050811 !important;
    color: #94A3B8 !important;
    font-family: 'Inter', system-ui, -apple-system, sans-serif !important;
    margin: 0;
    padding: 0;
  }

  /* Header FX1 Style */
  header {
    background: linear-gradient(180deg, #0b0f19 0%, #050811 100%) !important;
    border-bottom: 1px solid rgba(0, 229, 255, 0.15) !important;
    padding: 30px 20px !important;
    text-align: center;
  }

  /* FX1 Main Title */
  header h1, .fx1-title {
    color: #FFFFFF !important;
    font-weight: 800 !important;
    font-size: 2.2rem !important;
    letter-spacing: -0.02em !important;
    text-transform: uppercase;
    text-shadow: 0 0 20px rgba(0, 229, 255, 0.3);
    margin-bottom: 8px !important;
  }

  /* FX1 Tagline / Subtitle */
  header h2, .fx1-subtitle {
    color: #00E5FF !important;
    font-weight: 600 !important;
    font-size: 0.95rem !important;
    letter-spacing: 0.1em !important;
    text-transform: uppercase !important;
    opacity: 0.9;
  }

  /* Hide default theme header links / downloads */
  header section, header .button, header a.buttons, header a[href*="github.com"], .downloads {
    display: none !important;
  }

  /* Main Container */
  #content_wrapper, .container, section {
    max-width: 1200px !important;
    margin: 0 auto !important;
    padding: 20px !important;
  }

  /* Card Container for SVG */
  .fx1-card {
    background: #0b0f19;
    border: 1px solid rgba(0, 229, 255, 0.2);
    border-radius: 12px;
    box-shadow: 0 10px 30px -10px rgba(0, 229, 255, 0.1);
    overflow: hidden;
    margin-top: 20px;
    margin-bottom: 30px;
  }

  /* Text & Paragraphs */
  p {
    color: #94A3B8 !important;
    font-size: 1rem;
    line-height: 1.6;
  }

  /* Accent Highlight */
  .highlight-green {
    color: #4ADE80;
    font-weight: 600;
  }

  /* Footer */
  footer {
    border-top: 1px solid rgba(255, 255, 255, 0.05) !important;
    text-align: center;
    padding: 20px !important;
    color: #64748B !important;
    font-size: 0.85rem !important;
  }
</style>

<div class="fx1-card">
  <object data="./FX1roadmap.svg" type="image/svg+xml" width="100%" height="1020px" style="width:100%; border:none; display:block;">
    <p style="padding:20px; text-align:center;">
      Votre navigateur ne charge pas le SVG. 
      <a href="./FX1roadmap.svg" style="color:#00E5FF;">Cliquez ici pour l'ouvrir directement</a>.
    </p>
  </object>
</div>

---

*FX1 — AI-Powered Decentralized Sports Data Platform*
