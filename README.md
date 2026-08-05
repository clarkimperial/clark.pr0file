<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Clark Anthony I. Llemos | Portfolio</title>

<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
<style>
/* ============================================
   CLARK ANTHONY I. LLEMOS — PORTFOLIO STYLES
   Dark theme, blue/purple gradients, glassmorphism
   ============================================ */

:root {
  --bg: #07070f;
  --bg-alt: #0c0c1a;
  --surface: rgba(255, 255, 255, 0.05);
  --surface-border: rgba(255, 255, 255, 0.1);
  --blue: #4f8bff;
  --purple: #9b5cff;
  --pink: #ff5ca8;
  --text: #eef0ff;
  --text-dim: #a4a8c4;
  --text-dimmer: #6b6f92;
  --gradient: linear-gradient(135deg, var(--blue), var(--purple));
  --gradient-soft: linear-gradient(135deg, rgba(79,139,255,0.18), rgba(155,92,255,0.18));
  --radius: 20px;
  --shadow: 0 20px 50px rgba(0,0,0,0.45);
  --ease: cubic-bezier(0.16, 1, 0.3, 1);
}

* { margin: 0; padding: 0; box-sizing: border-box; }

html { scroll-behavior: smooth; }

body {
  background: var(--bg);
  color: var(--text);
  font-family: 'Poppins', sans-serif;
  font-weight: 300;
  overflow-x: hidden;
  line-height: 1.6;
}

img { max-width: 100%; display: block; }

a { text-decoration: none; color: inherit; }

ul { list-style: none; }

::selection { background: var(--purple); color: #fff; }

/* Scrollbar */
::-webkit-scrollbar { width: 10px; }
::-webkit-scrollbar-track { background: var(--bg); }
::-webkit-scrollbar-thumb { background: var(--gradient); border-radius: 10px; }

/* ============ LOADER ============ */
.loader {
  position: fixed;
  inset: 0;
  z-index: 9999;
  background: var(--bg);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 18px;
  transition: opacity 0.6s var(--ease), visibility 0.6s var(--ease);
}
.loader.hidden { opacity: 0; visibility: hidden; pointer-events: none; }
.loader-ring {
  width: 56px;
  height: 56px;
  border-radius: 50%;
  border: 3px solid rgba(255,255,255,0.08);
  border-top-color: var(--blue);
  border-right-color: var(--purple);
  animation: spin 0.9s linear infinite;
}
.loader-text {
  font-size: 0.8rem;
  letter-spacing: 0.2em;
  text-transform: uppercase;
  color: var(--text-dim);
}
@keyframes spin { to { transform: rotate(360deg); } }

/* ============ ANIMATED BACKGROUND ============ */
.bg-blobs {
  position: fixed;
  inset: 0;
  z-index: -2;
  overflow: hidden;
  pointer-events: none;
}
.blob {
  position: absolute;
  border-radius: 50%;
  filter: blur(90px);
  opacity: 0.45;
  will-change: transform;
}
.blob-1 {
  width: 480px; height: 480px;
  background: var(--blue);
  top: -120px; left: -100px;
  animation: float1 22s ease-in-out infinite;
}
.blob-2 {
  width: 520px; height: 520px;
  background: var(--purple);
  bottom: -150px; right: -120px;
  animation: float2 26s ease-in-out infinite;
}
.blob-3 {
  width: 360px; height: 360px;
  background: var(--pink);
  top: 45%; left: 55%;
  opacity: 0.28;
  animation: float3 30s ease-in-out infinite;
}
@keyframes float1 {
  0%, 100% { transform: translate(0, 0) scale(1); }
  50% { transform: translate(80px, 100px) scale(1.15); }
}
@keyframes float2 {
  0%, 100% { transform: translate(0, 0) scale(1); }
  50% { transform: translate(-90px, -70px) scale(1.1); }
}
@keyframes float3 {
  0%, 100% { transform: translate(-50%, -50%) scale(1); }
  50% { transform: translate(-30%, -60%) scale(1.2); }
}

#particles {
  position: fixed;
  inset: 0;
  z-index: -1;
  pointer-events: none;
}

/* ============ NAVBAR ============ */
.navbar {
  position: fixed;
  top: 0; left: 0; right: 0;
  z-index: 1000;
  padding: 18px 0;
  transition: background 0.4s var(--ease), padding 0.4s var(--ease), box-shadow 0.4s var(--ease);
}
.navbar.scrolled {
  padding: 10px 0;
  background: rgba(7, 7, 15, 0.75);
  backdrop-filter: blur(16px);
  -webkit-backdrop-filter: blur(16px);
  box-shadow: 0 10px 30px rgba(0,0,0,0.35);
  border-bottom: 1px solid var(--surface-border);
}
.nav-inner {
  max-width: 1180px;
  margin: 0 auto;
  padding: 0 28px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.nav-logo {
  font-weight: 700;
  font-size: 1.3rem;
  letter-spacing: 0.03em;
}
.nav-logo span { background: var(--gradient); -webkit-background-clip: text; background-clip: text; color: transparent; }
.nav-links {
  display: flex;
  gap: 34px;
}
.nav-link {
  font-size: 0.88rem;
  font-weight: 500;
  color: var(--text-dim);
  position: relative;
  padding: 6px 0;
  transition: color 0.3s;
}
.nav-link::after {
  content: '';
  position: absolute;
  bottom: 0; left: 0;
  width: 0; height: 2px;
  background: var(--gradient);
  transition: width 0.35s var(--ease);
  border-radius: 2px;
}
.nav-link:hover { color: var(--text); }
.nav-link.active { color: var(--text); }
.nav-link.active::after { width: 100%; }

.nav-toggle {
  display: none;
  flex-direction: column;
  gap: 5px;
  background: none;
  border: none;
  cursor: pointer;
  z-index: 1100;
}
.nav-toggle span {
  width: 24px; height: 2px;
  background: var(--text);
  border-radius: 2px;
  transition: transform 0.3s var(--ease), opacity 0.3s var(--ease);
}
.nav-toggle.open span:nth-child(1) { transform: translateY(7px) rotate(45deg); }
.nav-toggle.open span:nth-child(2) { opacity: 0; }
.nav-toggle.open span:nth-child(3) { transform: translateY(-7px) rotate(-45deg); }

/* ============ HERO ============ */
.hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 120px 28px 80px;
  position: relative;
}
.hero-inner {
  max-width: 1100px;
  width: 100%;
  display: grid;
  grid-template-columns: 340px 1fr;
  gap: 64px;
  align-items: center;
}
.hero-image { position: relative; justify-self: center; }
.hero-image-glow {
  position: absolute;
  inset: -30px;
  background: var(--gradient);
  border-radius: 50%;
  filter: blur(50px);
  opacity: 0.5;
  animation: pulse 4s ease-in-out infinite;
}
@keyframes pulse {
  0%, 100% { opacity: 0.4; transform: scale(1); }
  50% { opacity: 0.65; transform: scale(1.06); }
}
.hero-image-frame {
  position: relative;
  width: 300px;
  height: 300px;
  border-radius: 50%;
  padding: 6px;
  background: var(--gradient);
  box-shadow: var(--shadow);
}
.hero-image-frame img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 50%;
  border: 4px solid var(--bg);
}
.upload-btn {
  position: absolute;
  bottom: 10px;
  right: 10px;
  width: 46px;
  height: 46px;
  border-radius: 50%;
  background: var(--gradient);
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  box-shadow: 0 8px 20px rgba(79,139,255,0.4);
  transition: transform 0.3s var(--ease);
  border: 3px solid var(--bg);
}
.upload-btn:hover { transform: scale(1.1); }
.upload-btn i { color: #fff; font-size: 1rem; }

.hero-eyebrow {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  font-size: 0.78rem;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  color: var(--blue);
  margin-bottom: 14px;
  font-weight: 500;
}
.hero-name {
  font-size: clamp(2rem, 4.5vw, 3.2rem);
  font-weight: 700;
  line-height: 1.15;
  margin-bottom: 10px;
  background: linear-gradient(135deg, #fff 40%, var(--purple));
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
}
.hero-subtitle {
  font-size: 1.05rem;
  font-weight: 500;
  color: var(--text-dim);
  min-height: 1.6em;
  margin-bottom: 18px;
}
.cursor { animation: blink 0.9s step-end infinite; color: var(--purple); }
@keyframes blink { 50% { opacity: 0; } }

.hero-welcome {
  color: var(--text-dim);
  font-weight: 300;
  max-width: 480px;
  margin-bottom: 32px;
}
.hero-actions { display: flex; gap: 16px; flex-wrap: wrap; }

.btn {
  display: inline-flex;
  align-items: center;
  gap: 10px;
  padding: 14px 28px;
  border-radius: 50px;
  font-size: 0.9rem;
  font-weight: 500;
  transition: transform 0.3s var(--ease), box-shadow 0.3s var(--ease), background 0.3s;
}
.btn-primary {
  background: var(--gradient);
  color: #fff;
  box-shadow: 0 10px 30px rgba(79,139,255,0.3);
}
.btn-primary:hover { transform: translateY(-3px); box-shadow: 0 16px 40px rgba(155,92,255,0.4); }
.btn-ghost {
  background: var(--surface);
  border: 1px solid var(--surface-border);
  backdrop-filter: blur(10px);
}
.btn-ghost:hover { background: rgba(255,255,255,0.1); transform: translateY(-3px); }

.scroll-cue {
  position: absolute;
  bottom: 28px;
  left: 50%;
  transform: translateX(-50%);
  color: var(--text-dimmer);
  font-size: 1.1rem;
  animation: bounce 2s ease-in-out infinite;
}
@keyframes bounce {
  0%, 100% { transform: translate(-50%, 0); }
  50% { transform: translate(-50%, 10px); }
}

/* ============ SECTIONS ============ */
.section { padding: 100px 28px; position: relative; }
.section-inner { max-width: 1100px; margin: 0 auto; }
.section-eyebrow {
  font-size: 0.78rem;
  letter-spacing: 0.16em;
  text-transform: uppercase;
  color: var(--purple);
  font-weight: 500;
  margin-bottom: 8px;
}
.section-title {
  font-size: clamp(1.7rem, 3.5vw, 2.4rem);
  font-weight: 600;
  margin-bottom: 44px;
}

/* Glass card */
.glass-card {
  background: var(--surface);
  border: 1px solid var(--surface-border);
  border-radius: var(--radius);
  backdrop-filter: blur(18px);
  -webkit-backdrop-filter: blur(18px);
  box-shadow: var(--shadow);
  transition: transform 0.4s var(--ease), box-shadow 0.4s var(--ease), border-color 0.4s var(--ease);
}
.glass-card:hover {
  border-color: rgba(155,92,255,0.4);
  box-shadow: 0 25px 60px rgba(79,139,255,0.15);
}

/* Info card */
.info-card { padding: 40px; margin-bottom: 28px; }
.info-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 28px;
}
.info-item { display: flex; align-items: flex-start; gap: 16px; }
.info-icon {
  width: 46px; height: 46px;
  min-width: 46px;
  border-radius: 14px;
  background: var(--gradient-soft);
  display: flex; align-items: center; justify-content: center;
  color: var(--blue);
  font-size: 1.05rem;
}
.info-item div:last-child { display: flex; flex-direction: column; gap: 3px; }
.info-label { font-size: 0.72rem; text-transform: uppercase; letter-spacing: 0.08em; color: var(--text-dimmer); }
.info-value { font-size: 0.98rem; font-weight: 500; color: var(--text); word-break: break-word; }

/* About card */
.about-card { padding: 40px; }
.about-card-header { display: flex; align-items: center; gap: 14px; margin-bottom: 18px; }
.about-card-header i { font-size: 1.3rem; color: var(--purple); }
.about-card-header h3 { font-size: 1.3rem; font-weight: 600; }
.about-card p { color: var(--text-dim); font-weight: 300; }

/* Academic */
.academic-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 22px;
}
.academic-card {
  padding: 32px 24px;
  text-align: center;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 10px;
}
.academic-icon {
  width: 56px; height: 56px;
  border-radius: 16px;
  background: var(--gradient);
  display: flex; align-items: center; justify-content: center;
  font-size: 1.4rem;
  color: #fff;
  margin-bottom: 6px;
}
.academic-card:hover .academic-icon { animation: wiggle 0.5s var(--ease); }
@keyframes wiggle { 25% { transform: rotate(-8deg); } 75% { transform: rotate(8deg); } }
.academic-label { font-size: 0.72rem; text-transform: uppercase; letter-spacing: 0.08em; color: var(--text-dimmer); }
.academic-value { font-size: 1rem; font-weight: 500; }

/* Skills */
.skills-card { padding: 44px; display: flex; flex-direction: column; gap: 24px; }
.skill-row { display: flex; flex-direction: column; gap: 10px; }
.skill-name { font-size: 0.9rem; font-weight: 500; display: flex; align-items: center; gap: 10px; color: var(--text); }
.skill-name i { color: var(--blue); width: 18px; }
.skill-bar {
  height: 8px;
  border-radius: 10px;
  background: rgba(255,255,255,0.07);
  overflow: hidden;
}
.skill-fill {
  height: 100%;
  width: 0%;
  border-radius: 10px;
  background: var(--gradient);
  transition: width 1.4s var(--ease);
  position: relative;
}
.skill-fill::after {
  content: '';
  position: absolute; inset: 0;
  background: linear-gradient(90deg, transparent, rgba(255,255,255,0.4), transparent);
  animation: shimmer 2.2s linear infinite;
}
@keyframes shimmer { 0% { transform: translateX(-100%); } 100% { transform: translateX(100%); } }

/* Hobbies */
.hobby-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 22px;
}
.hobby-card {
  padding: 34px 20px;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 14px;
  text-align: center;
  cursor: default;
}
.hobby-card i {
  font-size: 1.6rem;
  background: var(--gradient);
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
}
.hobby-card span { font-size: 0.88rem; font-weight: 500; }
.hobby-card:hover { transform: translateY(-8px); }

/* Goals */
.goals-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 28px;
}
.goal-card { padding: 38px; }
.goal-head { display: flex; align-items: center; gap: 14px; margin-bottom: 22px; }
.goal-head i { font-size: 1.3rem; color: var(--blue); }
.goal-head h3 { font-size: 1.2rem; font-weight: 600; }
.goal-card ul { display: flex; flex-direction: column; gap: 14px; }
.goal-card li { display: flex; gap: 12px; color: var(--text-dim); font-weight: 300; font-size: 0.92rem; }
.goal-card li i { color: var(--purple); margin-top: 4px; min-width: 14px; }

/* Social */
.social-grid {
  display: flex;
  flex-wrap: wrap;
  gap: 18px;
}
.social-btn {
  display: flex;
  align-items: center;
  gap: 12px;
  padding: 16px 26px;
  border-radius: 50px;
  font-weight: 500;
  font-size: 0.92rem;
  border: 1px solid var(--surface-border);
  background: var(--surface);
  backdrop-filter: blur(14px);
  transition: transform 0.3s var(--ease), box-shadow 0.3s var(--ease), background 0.3s;
}
.social-btn i { font-size: 1.1rem; }
.social-btn:hover { transform: translateY(-4px) scale(1.03); }
.social-btn.fb:hover { background: #1877f2; box-shadow: 0 12px 30px rgba(24,119,242,0.4); }
.social-btn.ig:hover { background: linear-gradient(45deg,#f09433,#e6683c,#dc2743,#cc2366,#bc1888); box-shadow: 0 12px 30px rgba(220,39,67,0.4); }
.social-btn.eq:hover { background: var(--gradient); box-shadow: 0 12px 30px rgba(155,92,255,0.4); }
.social-btn.th:hover { background: #000; box-shadow: 0 12px 30px rgba(0,0,0,0.5); }
.social-btn.tk:hover { background: #000; box-shadow: 0 12px 30px rgba(0,0,0,0.5); }

/* Footer */
.footer {
  text-align: center;
  padding: 40px 28px;
  color: var(--text-dimmer);
  font-size: 0.82rem;
  border-top: 1px solid var(--surface-border);
}

/* Back to top */
.back-to-top {
  position: fixed;
  bottom: 28px;
  right: 28px;
  width: 48px; height: 48px;
  border-radius: 50%;
  background: var(--gradient);
  border: none;
  color: #fff;
  font-size: 1rem;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 10px 30px rgba(79,139,255,0.35);
  opacity: 0;
  visibility: hidden;
  transform: translateY(20px);
  transition: opacity 0.4s var(--ease), transform 0.4s var(--ease), visibility 0.4s;
  z-index: 500;
}
.back-to-top.visible { opacity: 1; visibility: visible; transform: translateY(0); }
.back-to-top:hover { transform: translateY(-4px) scale(1.08); }

/* Reveal on scroll */
.reveal {
  opacity: 0;
  transform: translateY(36px);
  transition: opacity 0.8s var(--ease), transform 0.8s var(--ease);
}
.reveal.in-view {
  opacity: 1;
  transform: translateY(0);
}

/* Reduced motion */
@media (prefers-reduced-motion: reduce) {
  * { animation-duration: 0.01ms !important; animation-iteration-count: 1 !important; transition-duration: 0.01ms !important; }
}

/* ============ RESPONSIVE ============ */
@media (max-width: 960px) {
  .hero-inner { grid-template-columns: 1fr; text-align: center; gap: 40px; }
  .hero-actions { justify-content: center; }
  .hero-welcome { margin-left: auto; margin-right: auto; }
  .info-grid { grid-template-columns: 1fr; }
  .academic-grid { grid-template-columns: repeat(2, 1fr); }
  .hobby-grid { grid-template-columns: repeat(2, 1fr); }
  .goals-grid { grid-template-columns: 1fr; }
}

@media (max-width: 720px) {
  .nav-toggle { display: flex; }
  .nav-links {
    position: fixed;
    top: 0; right: 0;
    height: 100vh;
    width: 74%;
    max-width: 300px;
    background: rgba(9, 9, 20, 0.97);
    backdrop-filter: blur(20px);
    flex-direction: column;
    justify-content: center;
    align-items: flex-start;
    gap: 28px;
    padding: 40px;
    transform: translateX(100%);
    transition: transform 0.45s var(--ease);
    border-left: 1px solid var(--surface-border);
  }
  .nav-links.open { transform: translateX(0); }
}

@media (max-width: 520px) {
  .hero { padding: 110px 20px 60px; }
  .hero-image-frame { width: 220px; height: 220px; }
  .section { padding: 70px 20px; }
  .info-card, .about-card, .skills-card, .goal-card { padding: 26px; }
  .academic-grid, .hobby-grid { grid-template-columns: 1fr 1fr; gap: 14px; }
  .social-grid { justify-content: center; }
  .social-btn { padding: 13px 20px; font-size: 0.85rem; }
}

</style>
</head>
<body>

<!-- Loading Screen -->
<div class="loader" id="loader">
  <div class="loader-ring"></div>
  <span class="loader-text">loading profile<span class="dots">...</span></span>
</div>

<!-- Animated Background -->
<div class="bg-blobs" aria-hidden="true">
  <span class="blob blob-1"></span>
  <span class="blob blob-2"></span>
  <span class="blob blob-3"></span>
</div>
<canvas id="particles" aria-hidden="true"></canvas>

<!-- Navbar -->
<nav class="navbar" id="navbar">
  <div class="nav-inner">
    <a href="#hero" class="nav-logo">C<span>.</span>A<span class="logo-dot">L</span></a>
    <button class="nav-toggle" id="navToggle" aria-label="Toggle menu">
      <span></span><span></span><span></span>
    </button>
    <ul class="nav-links" id="navLinks">
      <li><a href="#hero" class="nav-link active" data-section="hero">Home</a></li>
      <li><a href="#about" class="nav-link" data-section="about">About</a></li>
      <li><a href="#academic" class="nav-link" data-section="academic">Academic</a></li>
      <li><a href="#skills" class="nav-link" data-section="skills">Skills</a></li>
      <li><a href="#hobbies" class="nav-link" data-section="hobbies">Hobbies</a></li>
      <li><a href="#goals" class="nav-link" data-section="goals">Goals</a></li>
      <li><a href="#contact" class="nav-link" data-section="contact">Contact</a></li>
    </ul>
  </div>
</nav>

<!-- Hero Section -->
<header class="hero" id="hero">
  <div class="hero-inner">
    <div class="hero-image reveal">
      <div class="hero-image-glow"></div>
      <div class="hero-image-frame">
            </div>
      <label class="upload-btn" for="imgUpload" title="Replace profile picture">
        <i class="fa-solid fa-camera"></i>
        <input type="file" id="imgUpload" accept="image/*" hidden>
      </label>
    </div>

    <div class="hero-text reveal">
      <p class="hero-eyebrow"><i class="fa-solid fa-satellite-dish"></i> Welcome to my portfolio</p>
      <h1 class="hero-name">Clark Anthony I. Llemos</h1>
      <p class="hero-subtitle">
        <span id="typedText"></span><span class="cursor">|</span>
      </p>
      <p class="hero-welcome">
        Hey, I'm Clark — glad you stopped by. This is where I put my code, my canvases,
        and my melodies side by side. Take a look around.
      </p>
      <div class="hero-actions">
        <a href="#about" class="btn btn-primary" id="viewProfileBtn">
          <i class="fa-solid fa-user"></i> View Profile
        </a>
        <a href="#contact" class="btn btn-ghost">
          <i class="fa-solid fa-paper-plane"></i> Get in Touch
        </a>
      </div>
    </div>
  </div>
  <a href="#about" class="scroll-cue" aria-label="Scroll down">
    <i class="fa-solid fa-chevron-down"></i>
  </a>
</header>

<main>

  <!-- Basic Information -->
  <section class="section" id="about">
    <div class="section-inner">
      <p class="section-eyebrow reveal">Basic Information</p>
      <h2 class="section-title reveal">Who I Am, On Paper</h2>

      <div class="glass-card info-card reveal">
        <div class="info-grid">
          <div class="info-item">
            <div class="info-icon"><i class="fa-solid fa-id-card"></i></div>
            <div><span class="info-label">Full Name</span><span class="info-value">Clark Anthony I. Llemos</span></div>
          </div>
          <div class="info-item">
            <div class="info-icon"><i class="fa-solid fa-cake-candles"></i></div>
            <div><span class="info-label">Age</span><span class="info-value">19 Years Old</span></div>
          </div>
          <div class="info-item">
            <div class="info-icon"><i class="fa-solid fa-venus-mars"></i></div>
            <div><span class="info-label">Gender</span><span class="info-value">Male</span></div>
          </div>
          <div class="info-item">
            <div class="info-icon"><i class="fa-solid fa-calendar-day"></i></div>
            <div><span class="info-label">Date of Birth</span><span class="info-value">January 17, 2007</span></div>
          </div>
          <div class="info-item">
            <div class="info-icon"><i class="fa-solid fa-location-dot"></i></div>
            <div><span class="info-label">Address</span><span class="info-value">Osmeña, Hinabangan, Samar</span></div>
          </div>
          <div class="info-item">
            <div class="info-icon"><i class="fa-solid fa-phone"></i></div>
            <div><span class="info-label">Contact Number</span><span class="info-value">0926 490 3143</span></div>
          </div>
          <div class="info-item">
            <div class="info-icon"><i class="fa-solid fa-envelope"></i></div>
            <div><span class="info-label">Email</span><span class="info-value">clarkimperial5@gmail.com</span></div>
          </div>
        </div>
      </div>

      <!-- About Me -->
      <div class="glass-card about-card reveal">
        <div class="about-card-header">
          <i class="fa-solid fa-feather-pointer"></i>
          <h3>About Me</h3>
        </div>
        <p>
          Hello! I'm Clark Anthony I. Llemos, a second-year Bachelor of Science in Information
          Technology (BSIT) student at Samar State University. I am passionate about technology,
          web development, and continuous learning. Aside from programming, I am also an independent
          music artist and an art enthusiast who enjoys creating paintings and expressing creativity
          through visual art. I believe that technology, music, and art are powerful ways to share
          ideas and inspire others. My goal is to continuously improve my skills as a developer while
          growing as an artist and creating meaningful projects in both fields.
        </p>
      </div>
    </div>
  </section>

  <!-- Academic Information -->
  <section class="section" id="academic">
    <div class="section-inner">
      <p class="section-eyebrow reveal">Academic Information</p>
      <h2 class="section-title reveal">Currently Studying</h2>

      <div class="academic-grid">
        <div class="glass-card academic-card reveal">
          <div class="academic-icon"><i class="fa-solid fa-building-columns"></i></div>
          <span class="academic-label">University</span>
          <span class="academic-value">Samar State University</span>
        </div>
        <div class="glass-card academic-card reveal">
          <div class="academic-icon"><i class="fa-solid fa-code"></i></div>
          <span class="academic-label">Program</span>
          <span class="academic-value">BS Information Technology</span>
        </div>
        <div class="glass-card academic-card reveal">
          <div class="academic-icon"><i class="fa-solid fa-graduation-cap"></i></div>
          <span class="academic-label">Year Level</span>
          <span class="academic-value">Second Year</span>
        </div>
        <div class="glass-card academic-card reveal">
          <div class="academic-icon"><i class="fa-solid fa-people-group"></i></div>
          <span class="academic-label">Section</span>
          <span class="academic-value">2F</span>
        </div>
      </div>
    </div>
  </section>

  <!-- Skills -->
  <section class="section" id="skills">
    <div class="section-inner">
      <p class="section-eyebrow reveal">Skills</p>
      <h2 class="section-title reveal">What I Bring to the Table</h2>

      <div class="glass-card skills-card reveal">
        <div class="skill-row" data-level="88">
          <span class="skill-name"><i class="fa-brands fa-html5"></i> HTML</span>
          <div class="skill-bar"><div class="skill-fill"></div></div>
        </div>
        <div class="skill-row" data-level="82">
          <span class="skill-name"><i class="fa-brands fa-css3-alt"></i> CSS</span>
          <div class="skill-bar"><div class="skill-fill"></div></div>
        </div>
        <div class="skill-row" data-level="78">
          <span class="skill-name"><i class="fa-solid fa-laptop-code"></i> Programming</span>
          <div class="skill-bar"><div class="skill-fill"></div></div>
        </div>
        <div class="skill-row" data-level="85">
          <span class="skill-name"><i class="fa-solid fa-puzzle-piece"></i> Problem Solving</span>
          <div class="skill-bar"><div class="skill-fill"></div></div>
        </div>
        <div class="skill-row" data-level="90">
          <span class="skill-name"><i class="fa-solid fa-lightbulb"></i> Creativity</span>
          <div class="skill-bar"><div class="skill-fill"></div></div>
        </div>
        <div class="skill-row" data-level="92">
          <span class="skill-name"><i class="fa-solid fa-palette"></i> Traditional Art &amp; Painting</span>
          <div class="skill-bar"><div class="skill-fill"></div></div>
        </div>
        <div class="skill-row" data-level="87">
          <span class="skill-name"><i class="fa-solid fa-pen-nib"></i> Drawing &amp; Sketching</span>
          <div class="skill-bar"><div class="skill-fill"></div></div>
        </div>
        <div class="skill-row" data-level="80">
          <span class="skill-name"><i class="fa-solid fa-people-arrows"></i> Teamwork</span>
          <div class="skill-bar"><div class="skill-fill"></div></div>
        </div>
        <div class="skill-row" data-level="83">
          <span class="skill-name"><i class="fa-solid fa-clock"></i> Time Management</span>
          <div class="skill-bar"><div class="skill-fill"></div></div>
        </div>
      </div>
    </div>
  </section>

  <!-- Hobbies -->
  <section class="section" id="hobbies">
    <div class="section-inner">
      <p class="section-eyebrow reveal">Hobbies &amp; Interests</p>
      <h2 class="section-title reveal">Outside the Code Editor</h2>

      <div class="hobby-grid">
        <div class="glass-card hobby-card reveal"><i class="fa-solid fa-palette"></i><span>Painting &amp; Traditional Art</span></div>
        <div class="glass-card hobby-card reveal"><i class="fa-solid fa-pencil"></i><span>Drawing &amp; Sketching</span></div>
        <div class="glass-card hobby-card reveal"><i class="fa-solid fa-globe"></i><span>Web Development</span></div>
        <div class="glass-card hobby-card reveal"><i class="fa-solid fa-terminal"></i><span>Programming</span></div>
        <div class="glass-card hobby-card reveal"><i class="fa-solid fa-microphone"></i><span>Singing</span></div>
        <div class="glass-card hobby-card reveal"><i class="fa-solid fa-headphones"></i><span>Listening to Music</span></div>
        <div class="glass-card hobby-card reveal"><i class="fa-solid fa-robot"></i><span>Exploring AI Tools</span></div>
        <div class="glass-card hobby-card reveal"><i class="fa-solid fa-microchip"></i><span>Learning New Technologies</span></div>
      </div>
    </div>
  </section>

  <!-- Goals -->
  <section class="section" id="goals">
    <div class="section-inner">
      <p class="section-eyebrow reveal">Goals</p>
      <h2 class="section-title reveal">Where I'm Headed</h2>

      <div class="goals-grid">
        <div class="glass-card goal-card reveal">
          <div class="goal-head"><i class="fa-solid fa-flag"></i><h3>Short-Term Goals</h3></div>
          <ul>
            <li><i class="fa-solid fa-check"></i> Improve my programming and web development skills.</li>
            <li><i class="fa-solid fa-check"></i> Build more personal and academic projects.</li>
            <li><i class="fa-solid fa-check"></i> Maintain good academic performance.</li>
          </ul>
        </div>
        <div class="glass-card goal-card reveal">
          <div class="goal-head"><i class="fa-solid fa-mountain-sun"></i><h3>Long-Term Goals</h3></div>
          <ul>
            <li><i class="fa-solid fa-check"></i> Graduate with a Bachelor of Science in Information Technology.</li>
            <li><i class="fa-solid fa-check"></i> Become a skilled software or web developer.</li>
            <li><i class="fa-solid fa-check"></i> Build innovative applications that solve real-world problems and keep learning new technologies throughout my career.</li>
          </ul>
        </div>
      </div>
    </div>
  </section>

  <!-- Social / Contact -->
  <section class="section" id="contact">
    <div class="section-inner">
      <p class="section-eyebrow reveal">Let's Connect</p>
      <h2 class="section-title reveal">Find Me Elsewhere</h2>

      <div class="social-grid reveal">
        <a href="https://www.facebook.com/profile.php?id=61589367733816" target="_blank" rel="noopener" class="social-btn fb">
          <i class="fa-brands fa-facebook-f"></i><span>Facebook</span>
        </a>
        <a href="https://www.instagram.com/clark_imperial?igsh=MWZoZDR3NnRxZzJ5bQ==" target="_blank" rel="noopener" class="social-btn ig">
          <i class="fa-brands fa-instagram"></i><span>Instagram</span>
        </a>
        <a href="https://listen.equa.ls/DnWI/42uls5g1" target="_blank" rel="noopener" class="social-btn eq">
          <i class="fa-solid fa-music"></i><span>Equa.ls</span>
        </a>
        <a href="https://www.threads.com/@clark_imperial" target="_blank" rel="noopener" class="social-btn th">
          <i class="fa-brands fa-threads"></i><span>Threads</span>
        </a>
        <a href="https://www.tiktok.com/@clark_zyk?_r=1&_t=ZS-98c6UISqmzk" target="_blank" rel="noopener" class="social-btn tk">
          <i class="fa-brands fa-tiktok"></i><span>TikTok</span>
        </a>
      </div>
    </div>
  </section>

</main>

<footer class="footer">
  <p>&copy; 2026 Clark Anthony I. Llemos | Designed with HTML, CSS &amp; JavaScript</p>
</footer>

<button id="backToTop" class="back-to-top" aria-label="Back to top">
  <i class="fa-solid fa-arrow-up"></i>
</button>

<script>
/* ============================================
   CLARK ANTHONY I. LLEMOS — PORTFOLIO SCRIPT
   ============================================ */

document.addEventListener('DOMContentLoaded', () => {

  /* ---------- Loader ---------- */
  const loader = document.getElementById('loader');
  window.addEventListener('load', () => {
    setTimeout(() => loader.classList.add('hidden'), 500);
  });
  // Fallback in case 'load' already fired
  setTimeout(() => loader.classList.add('hidden'), 2200);

  /* ---------- Sticky Navbar + Toggle ---------- */
  const navbar = document.getElementById('navbar');
  const navToggle = document.getElementById('navToggle');
  const navLinks = document.getElementById('navLinks');

  window.addEventListener('scroll', () => {
    navbar.classList.toggle('scrolled', window.scrollY > 40);
    toggleBackToTop();
    updateActiveNav();
  });

  navToggle.addEventListener('click', () => {
    navToggle.classList.toggle('open');
    navLinks.classList.toggle('open');
  });

  navLinks.querySelectorAll('a').forEach(link => {
    link.addEventListener('click', () => {
      navToggle.classList.remove('open');
      navLinks.classList.remove('open');
    });
  });

  /* ---------- Active Nav Highlight ---------- */
  const sections = document.querySelectorAll('main .section, .hero');
  const navItems = document.querySelectorAll('.nav-link');

  function updateActiveNav() {
    let current = 'hero';
    const scrollPos = window.scrollY + window.innerHeight * 0.35;

    sections.forEach(sec => {
      if (scrollPos >= sec.offsetTop) {
        current = sec.getAttribute('id');
      }
    });

    navItems.forEach(link => {
      link.classList.toggle('active', link.dataset.section === current);
    });
  }
  updateActiveNav();

  /* ---------- Typing Animation for Subtitle ---------- */
  const typedTextEl = document.getElementById('typedText');
  const phrases = [
    'BSIT Student',
    'Web Developer',
    'Independent Music Artist',
    'Traditional Artist'
  ];
  let phraseIndex = 0, charIndex = 0, deleting = false;

  function typeLoop() {
    const current = phrases[phraseIndex];

    if (!deleting) {
      charIndex++;
      typedTextEl.textContent = current.slice(0, charIndex);
      if (charIndex === current.length) {
        deleting = true;
        setTimeout(typeLoop, 1400);
        return;
      }
    } else {
      charIndex--;
      typedTextEl.textContent = current.slice(0, charIndex);
      if (charIndex === 0) {
        deleting = false;
        phraseIndex = (phraseIndex + 1) % phrases.length;
      }
    }
    setTimeout(typeLoop, deleting ? 40 : 80);
  }
  typeLoop();

  /* ---------- Scroll Reveal ---------- */
  const revealEls = document.querySelectorAll('.reveal');
  const revealObserver = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('in-view');
        revealObserver.unobserve(entry.target);
      }
    });
  }, { threshold: 0.15 });
  revealEls.forEach(el => revealObserver.observe(el));

  /* ---------- Animated Skill Bars ---------- */
  const skillRows = document.querySelectorAll('.skill-row');
  const skillObserver = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        const fill = entry.target.querySelector('.skill-fill');
        const level = entry.target.dataset.level;
        fill.style.width = level + '%';
        skillObserver.unobserve(entry.target);
      }
    });
  }, { threshold: 0.3 });
  skillRows.forEach(row => skillObserver.observe(row));

  /* ---------- Profile Image Upload / Replace ---------- */
  const imgUpload = document.getElementById('imgUpload');
  const profileImg = document.getElementById('profileImg');

  imgUpload.addEventListener('change', (e) => {
    const file = e.target.files[0];
    if (file && file.type.startsWith('image/')) {
      const reader = new FileReader();
      reader.onload = (ev) => {
        profileImg.src = ev.target.result;
      };
      reader.readAsDataURL(file);
    }
  });

  /* ---------- Back To Top ---------- */
  const backToTop = document.getElementById('backToTop');
  function toggleBackToTop() {
    backToTop.classList.toggle('visible', window.scrollY > 500);
  }
  backToTop.addEventListener('click', () => {
    window.scrollTo({ top: 0, behavior: 'smooth' });
  });

  /* ---------- Particle Background ---------- */
  const canvas = document.getElementById('particles');
  const ctx = canvas.getContext('2d');
  let particles = [];
  const PARTICLE_COUNT = window.innerWidth < 720 ? 35 : 70;

  function resizeCanvas() {
    canvas.width = window.innerWidth;
    canvas.height = document.documentElement.scrollHeight;
  }

  function createParticles() {
    particles = [];
    for (let i = 0; i < PARTICLE_COUNT; i++) {
      particles.push({
        x: Math.random() * canvas.width,
        y: Math.random() * window.innerHeight,
        r: Math.random() * 1.8 + 0.6,
        speedY: Math.random() * 0.3 + 0.05,
        speedX: (Math.random() - 0.5) * 0.2,
        alpha: Math.random() * 0.5 + 0.15,
        hue: Math.random() > 0.5 ? '79,139,255' : '155,92,255'
      });
    }
  }

  function animateParticles() {
    ctx.clearRect(0, 0, canvas.width, canvas.height);
    particles.forEach(p => {
      p.y -= p.speedY;
      p.x += p.speedX;
      if (p.y < -10) p.y = window.scrollY + window.innerHeight + 10;
      if (p.x < 0) p.x = canvas.width;
      if (p.x > canvas.width) p.x = 0;

      ctx.beginPath();
      ctx.arc(p.x, p.y, p.r, 0, Math.PI * 2);
      ctx.fillStyle = `rgba(${p.hue}, ${p.alpha})`;
      ctx.fill();
    });
    requestAnimationFrame(animateParticles);
  }

  const prefersReducedMotion = window.matchMedia('(prefers-reduced-motion: reduce)').matches;
  if (!prefersReducedMotion) {
    resizeCanvas();
    createParticles();
    animateParticles();
    window.addEventListener('resize', () => {
      resizeCanvas();
      createParticles();
    });
  }

  /* ---------- Smooth anchor scroll offset fix ---------- */
  document.querySelectorAll('a[href^="#"]').forEach(anchor => {
    anchor.addEventListener('click', function (e) {
      const targetId = this.getAttribute('href');
      if (targetId.length > 1) {
        const target = document.querySelector(targetId);
        if (target) {
          e.preventDefault();
          const offset = 70;
          const top = target.getBoundingClientRect().top + window.scrollY - offset;
          window.scrollTo({ top, behavior: 'smooth' });
        }
      }
    });
  });

});

</script>
</body>
</html>

