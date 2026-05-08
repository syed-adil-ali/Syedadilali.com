<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<meta name="description" content="Syed Adil Ali - Frontend Developer & Engineering Student. Portfolio showcasing premium UI projects."/>
<meta name="keywords" content="Syed Adil Ali, Frontend Developer, UI Designer, Engineering Student, Portfolio"/>
<title>Syed Adil Ali | Frontend Developer</title>
<link rel="preconnect" href="https://fonts.googleapis.com"/>
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin/>
<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Space+Mono:ital,wght@0,400;0,700;1,400&family=Manrope:wght@300;400;500;600;700&display=swap" rel="stylesheet"/>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css"/>
<style>
/* ============================================================
   TOUCH & THEME VARIABLES
   ============================================================ */
html, body, a, button, div, span { -webkit-tap-highlight-color: transparent !important; }
* { outline: none; }

:root {
  --bg-primary: #03050f;
  --bg-secondary: #070b1a;
  --bg-glass: rgba(10,20,50,0.55);
  --neon-blue: #00d4ff;
  --neon-purple: #8b5cf6;
  --neon-pink: #ff0080;
  --accent: #00d4ff;
  --text-primary: #e8f0fe;
  --text-secondary: #7b90c4;
  --text-muted: #3d5280;
  --border: rgba(0,212,255,0.15);
  --border-strong: rgba(0,212,255,0.4);
  --glow-blue: 0 0 20px rgba(0,212,255,0.4), 0 0 60px rgba(0,212,255,0.15);
  --radius: 16px;
  --radius-sm: 10px;
  --font-display: 'Orbitron', monospace;
  --font-mono: 'Space Mono', monospace;
  --font-body: 'Manrope', sans-serif;
}

.light-mode {
  --bg-primary: #f0f4ff;
  --bg-secondary: #e2eaff;
  --bg-glass: rgba(220,230,255,0.7);
  --text-primary: #0a0f2e;
  --text-secondary: #334288;
  --text-muted: #8090c0;
}

/* ============================================================
   BASE STYLES
   ============================================================ */
*, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }
html { scroll-behavior: smooth; font-size: 16px; }
body {
  font-family: var(--font-body);
  background: var(--bg-primary);
  color: var(--text-primary);
  overflow-x: hidden;
  cursor: none;
  transition: background 0.4s, color 0.4s;
}

/* Custom Cursor */
#cursor-dot { width: 8px; height: 8px; background: var(--neon-blue); border-radius: 50%; position: fixed; top: 0; left: 0; z-index: 9999; pointer-events: none; transition: transform 0.1s; box-shadow: var(--glow-blue); }
#cursor-ring { width: 36px; height: 36px; border: 1.5px solid var(--neon-blue); border-radius: 50%; position: fixed; top: 0; left: 0; z-index: 9998; pointer-events: none; transition: all 0.15s ease; opacity: 0.6; }

/* Loader */
#loader { position: fixed; inset: 0; background: #000; display: flex; flex-direction: column; align-items: center; justify-content: center; z-index: 99999; transition: opacity 0.6s; }
#loader.hidden { opacity: 0; visibility: hidden; }
.loader-logo { font-family: var(--font-display); font-size: 2rem; background: linear-gradient(90deg, var(--neon-blue), var(--neon-purple)); -webkit-background-clip: text; -webkit-text-fill-color: transparent; animation: pulse 1s infinite; }

/* Navbar */
nav { position: fixed; top: 0; left: 0; right: 0; z-index: 1000; padding: 0 5%; height: 70px; display: flex; align-items: center; justify-content: space-between; background: var(--bg-glass); backdrop-filter: blur(20px); border-bottom: 1px solid var(--border); }
.nav-logo { font-family: var(--font-display); font-weight: 900; text-decoration: none; color: var(--neon-blue); display: flex; align-items: center; }
.nav-links { display: flex; gap: 2rem; list-style: none; }
.nav-links a { font-family: var(--font-mono); font-size: 0.75rem; color: var(--text-secondary); text-decoration: none; text-transform: uppercase; transition: 0.3s; }
.nav-links a:hover { color: var(--neon-blue); }

/* Hero Section */
#hero { min-height: 100vh; display: flex; align-items: center; padding: 100px 8%; position: relative; overflow: hidden; }
#particles-canvas { position: absolute; inset: 0; z-index: 0; }
.hero-content { position: relative; z-index: 1; max-width: 700px; }
.hero-name { font-family: var(--font-display); font-size: clamp(2.5rem, 6vw, 5rem); font-weight: 900; background: linear-gradient(135deg, #fff, var(--neon-blue)); -webkit-background-clip: text; -webkit-text-fill-color: transparent; margin: 10px 0; }
.typed-text { color: var(--neon-blue); font-family: var(--font-mono); }

/* Buttons */
.btn-primary { padding: 12px 28px; background: linear-gradient(135deg, var(--neon-blue), var(--neon-purple)); color: #fff; border: none; border-radius: 8px; font-family: var(--font-display); font-size: 0.8rem; text-decoration: none; display: inline-flex; align-items: center; gap: 8px; transition: 0.3s; box-shadow: 0 4px 15px rgba(0,212,255,0.3); }
.btn-primary:hover { transform: translateY(-3px); box-shadow: 0 8px 25px rgba(0,212,255,0.5); }

/* Glass Cards */
.glass { background: var(--bg-glass); backdrop-filter: blur(20px); border: 1px solid var(--border); border-radius: var(--radius); }

/* Sections */
section { padding: 80px 8%; }
.section-title { font-family: var(--font-display); font-size: 2.5rem; margin-bottom: 20px; background: linear-gradient(90deg, #fff, var(--neon-blue)); -webkit-background-clip: text; -webkit-text-fill-color: transparent; }

/* Responsive */
@media (max-width: 768px) {
  body { cursor: auto; }
  #cursor-dot, #cursor-ring { display: none; }
  .nav-links { display: none; }
}
</style>
</head>
<body>

<div id="cursor-dot"></div>
<div id="cursor-ring"></div>

<div id="loader">
  <div class="loader-logo">ADI.DEV</div>
</div>

<nav id="navbar">
  <a href="#hero" class="nav-logo">ADI</a>
  <ul class="nav-links">
    <li><a href="#about">About</a></li>
    <li><a href="#skills">Skills</a></li>
    <li><a href="#projects">Projects</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
  <button id="themeToggle" style="background:none; border:none; color:var(--neon-blue); cursor:pointer;"><i class="fas fa-moon"></i></button>
</nav>

<section id="hero">
  <canvas id="particles-canvas"></canvas>
  <div class="hero-content">
    <div style="color:var(--neon-blue); font-family:var(--font-mono);">👋 Hey, I'm Adi</div>
    <h1 class="hero-name">Syed Adil Ali</h1>
    <div style="font-size: 1.5rem; margin-bottom: 20px;">
      <span class="typed-text"></span>
    </div>
    <p style="color:var(--text-secondary); line-height:1.6; margin-bottom:30px;">I build modern, interactive web experiences. Engineering student from Punjab, India — building the future one line of code at a time.</p>
    <a href="#projects" class="btn-primary">Explore Projects</a>
  </div>
</section>

<section id="about">
  <h2 class="section-title">About Me</h2>
  <div class="glass" style="padding:30px; line-height:1.8;">
    I'm a passionate frontend developer and engineering student. I love creating smooth animations and futuristic UI designs. My goal is to build digital products that are both functional and visually stunning.
  </div>
</section>

<script>
/* Typing Animation */
const roles = ['Frontend Developer', 'UI Designer', 'Engineering Student'];
let roleIdx = 0, charIdx = 0, deleting = false;
const typedEl = document.querySelector('.typed-text');

function type() {
  const current = roles[roleIdx];
  typedEl.textContent = deleting ? current.slice(0, charIdx--) : current.slice(0, charIdx++);
  if (!deleting && charIdx > current.length) { deleting = true; setTimeout(type, 1500); return; }
  if (deleting && charIdx < 0) { deleting = false; roleIdx = (roleIdx + 1) % roles.length; }
  setTimeout(type, deleting ? 50 : 100);
}
type();

/* Cursor & Loader */
window.addEventListener('load', () => setTimeout(() => document.getElementById('loader').classList.add('hidden'), 1000));
const dot = document.getElementById('cursor-dot');
const ring = document.getElementById('cursor-ring');
document.addEventListener('mousemove', e => {
  dot.style.transform = `translate(${e.clientX}px, ${e.clientY}px)`;
  ring.style.transform = `translate(${e.clientX - 14}px, ${e.clientY - 14}px)`;
});

/* Theme Toggle */
document.getElementById('themeToggle').addEventListener('click', () => {
  document.body.classList.toggle('light-mode');
});
</script>
</body>
</html>
