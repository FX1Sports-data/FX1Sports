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

  /* --- BANNIERE AVERTISSEMENT / DISCLAIMER --- */
  .disclaimer-banner {
    background: rgba(255, 170, 0, 0.1);
    border: 1px solid rgba(255, 170, 0, 0.3);
    border-radius: 8px;
    padding: 12px 16px;
    color: #FFD166;
    font-size: 0.85rem;
   display: flex;
    align-items: flex-start;
    gap: 12px;
    line-height: 1.5;
  }
  
  .disclaimer-banner strong {
    color: #FFB347;
  }

  .disclaimer-banner a {
    color: #00E5FF;
   text-decoration: none;
    font-weight: 600;
    transition: color 0.2s;
  }

  .disclaimer-banner a:hover {
    color: #FFFFFF;
    text-decoration: underline;
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
   padding
