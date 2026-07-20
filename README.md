[main.js](https://github.com/user-attachments/files/30205455/main.js)[styles.css](https://github.com/user-attachments/files/30205447/styles.css)[Uploading styles./* ============================================
   IMPORTA FÁCIL — Sistema de diseño
   Concepto: manifiesto de aduanas / etiqueta de envío
   ============================================ */

@import url('https://fonts.googleapis.com/css2?family=Big+Shoulders+Display:wght@700;800;900&family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500;700&display=swap');

:root {
  /* Paleta */
  --navy: #14213D;
  --navy-light: #1E2F52;
  --paper: #F0EEE6;
  --paper-dim: #E4E1D6;
  --stamp: #C15A2E;
  --stamp-dark: #9A4623;
  --cargo-yellow: #E8B84B;
  --steel: #7A8699;
  --ink: #1C1C1A;
  --ok-green: #4A7C59;

  /* Tipografía */
  --font-display: 'Big Shoulders Display', sans-serif;
  --font-body: 'Inter', sans-serif;
  --font-mono: 'JetBrains Mono', monospace;

  /* Espaciado */
  --space-1: 0.5rem;
  --space-2: 1rem;
  --space-3: 1.5rem;
  --space-4: 2.5rem;
  --space-5: 4rem;
  --space-6: 6rem;

  --radius: 4px;
  --border: 2px solid var(--ink);
}

* { box-sizing: border-box; margin: 0; padding: 0; }

html { scroll-behavior: smooth; }

body {
  background: var(--paper);
  color: var(--ink);
  font-family: var(--font-body);
  line-height: 1.6;
  -webkit-font-smoothing: antialiased;
}

a { color: inherit; }

img { max-width: 100%; display: block; }

.container {
  max-width: 1100px;
  margin: 0 auto;
  padding: 0 var(--space-3);
}

/* ============ Franja de carga (motivo firma) ============ */
.cargo-stripe {
  height: 10px;
  background: repeating-linear-gradient(
    -45deg,
    var(--cargo-yellow),
    var(--cargo-yellow) 14px,
    var(--navy) 14px,
    var(--navy) 28px
  );
}

/* ============ Header ============ */
.site-header {
  background: var(--navy);
  color: var(--paper);
  padding: var(--space-2) 0;
}

.site-header .container {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.logo {
  font-family: var(--font-display);
  font-weight: 900;
  font-size: 1.6rem;
  letter-spacing: 0.02em;
  text-decoration: none;
  color: var(--paper);
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.logo .box-icon {
  width: 28px;
  height: 28px;
  border: 2px solid var(--cargo-yellow);
  position: relative;
  transform: rotate(-3deg);
}
.logo .box-icon::before,
.logo .box-icon::after {
  content: "";
  position: absolute;
  background: var(--cargo-yellow);
}
.logo .box-icon::before { top: 0; left: 0; right: 0; height: 2px; top: 50%; }
.logo .box-icon::after { left: 0; top: 0; bottom: 0; width: 2px; left: 50%; }

nav.main-nav ul {
  list-style: none;
  display: flex;
  gap: var(--space-4);
}

nav.main-nav a {
  text-decoration: none;
  font-weight: 500;
  font-size: 0.95rem;
  text-transform: uppercase;
  letter-spacing: 0.05em;
  color: var(--paper-dim);
  transition: color 0.2s;
}
nav.main-nav a:hover { color: var(--cargo-yellow); }

.nav-toggle {
  display: none;
  background: none;
  border: none;
  color: var(--paper);
  font-size: 1.5rem;
  cursor: pointer;
}

/* ============ Hero: manifiesto de aduanas ============ */
.hero {
  padding: var(--space-6) 0 var(--space-5);
  background: var(--navy);
  color: var(--paper);
  position: relative;
  overflow: hidden;
}

.manifest-card {
  background: var(--paper);
  color: var(--ink);
  border-radius: 2px;
  padding: var(--space-4);
  box-shadow: 8px 8px 0 rgba(0,0,0,0.25);
  position: relative;
  max-width: 720px;
}

.manifest-label {
  font-family: var(--font-mono);
  font-size: 0.75rem;
  text-transform: uppercase;
  letter-spacing: 0.15em;
  color: var(--steel);
  border-bottom: 1px dashed var(--steel);
  padding-bottom: var(--space-1);
  margin-bottom: var(--space-2);
  display: flex;
  justify-content: space-between;
}

.hero h1 {
  font-family: var(--font-display);
  font-weight: 800;
  font-size: clamp(2.4rem, 5vw, 4rem);
  line-height: 0.98;
  letter-spacing: -0.01em;
  margin-bottom: var(--space-3);
}

.hero h1 em {
  font-style: normal;
  color: var(--stamp);
}

.hero p.subtitle {
  font-size: 1.1rem;
  color: var(--ink);
  max-width: 55ch;
  margin-bottom: var(--space-3);
}

.hero-meta {
  display: flex;
  gap: var(--space-4);
  font-family: var(--font-mono);
  font-size: 0.8rem;
  color: var(--steel);
  margin-top: var(--space-3);
  border-top: 1px dashed var(--steel);
  padding-top: var(--space-2);
}

/* Stamp — elemento firma reutilizable */
.stamp {
  position: absolute;
  top: -18px;
  right: -18px;
  width: 110px;
  height: 110px;
  border: 3px solid var(--stamp);
  border-radius: 50%;
  transform: rotate(-10deg);
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  color: var(--stamp);
  font-family: var(--font-mono);
  font-weight: 700;
  font-size: 0.7rem;
  text-transform: uppercase;
  letter-spacing: 0.05em;
  background: rgba(240,238,230,0.9);
}
.stamp::before {
  content: "";
  position: absolute;
  inset: 6px;
  border: 1px solid var(--stamp);
  border-radius: 50%;
}

/* ============ Botones ============ */
.btn {
  display: inline-block;
  font-family: var(--font-body);
  font-weight: 700;
  font-size: 0.95rem;
  text-decoration: none;
  padding: 0.85rem 1.8rem;
  border-radius: var(--radius);
  border: 2px solid var(--ink);
  transition: transform 0.15s, box-shadow 0.15s;
}
.btn-primary {
  background: var(--stamp);
  color: var(--paper);
  border-color: var(--stamp-dark);
  box-shadow: 4px 4px 0 var(--ink);
}
.btn-primary:hover { transform: translate(-2px,-2px); box-shadow: 6px 6px 0 var(--ink); }
.btn-secondary {
  background: transparent;
  color: var(--ink);
  box-shadow: 4px 4px 0 var(--stamp);
}
.btn-secondary:hover { transform: translate(-2px,-2px); box-shadow: 6px 6px 0 var(--stamp); }

/* ============ Secciones generales ============ */
section { padding: var(--space-5) 0; }

.section-eyebrow {
  font-family: var(--font-mono);
  font-size: 0.75rem;
  text-transform: uppercase;
  letter-spacing: 0.15em;
  color: var(--stamp);
  margin-bottom: var(--space-1);
}

.section-title {
  font-family: var(--font-display);
  font-weight: 800;
  font-size: clamp(1.8rem, 3.5vw, 2.6rem);
  margin-bottom: var(--space-4);
  max-width: 20ch;
}

/* Cards de rutas / artículos */
.grid-3 {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: var(--space-3);
}

.route-card {
  background: white;
  border: var(--border);
  border-radius: 2px;
  padding: var(--space-3);
  position: relative;
}

.route-card .route-tag {
  font-family: var(--font-mono);
  font-size: 0.7rem;
  text-transform: uppercase;
  letter-spacing: 0.1em;
  background: var(--navy);
  color: var(--cargo-yellow);
  display: inline-block;
  padding: 0.2rem 0.6rem;
  margin-bottom: var(--space-2);
}

.route-card h3 {
  font-family: var(--font-display);
  font-size: 1.4rem;
  font-weight: 700;
  margin-bottom: var(--space-1);
}

.route-card p { color: var(--steel); font-size: 0.95rem; margin-bottom: var(--space-2); }

.route-card a {
  font-weight: 700;
  text-decoration: none;
  color: var(--stamp);
  font-size: 0.9rem;
}
.route-card a::after { content: " →"; }

/* Franja "quién escribe esto" — autoridad real */
.credential-band {
  background: var(--navy-light);
  color: var(--paper);
  border-top: 4px solid var(--cargo-yellow);
  border-bottom: 4px solid var(--cargo-yellow);
}

.credential-band .container {
  display: grid;
  grid-template-columns: 140px 1fr;
  gap: var(--space-4);
  align-items: center;
}

.credential-seal {
  width: 110px;
  height: 110px;
  border: 3px dashed var(--cargo-yellow);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: var(--font-mono);
  font-size: 2.2rem;
  color: var(--cargo-yellow);
}

.credential-band h3 {
  font-family: var(--font-display);
  font-weight: 700;
  font-size: 1.5rem;
  margin-bottom: var(--space-1);
}
.credential-band p { color: var(--paper-dim); max-width: 60ch; }

/* Newsletter / CTA final */
.cta-block {
  background: var(--stamp);
  color: var(--paper);
  text-align: center;
}
.cta-block .section-title { color: var(--paper); max-width: none; }
.cta-block .section-eyebrow { color: var(--navy); }

/* ============ Footer ============ */
footer {
  background: var(--ink);
  color: var(--paper-dim);
  padding: var(--space-4) 0 var(--space-2);
  font-size: 0.9rem;
}
footer .footer-grid {
  display: grid;
  grid-template-columns: 2fr 1fr 1fr;
  gap: var(--space-3);
  margin-bottom: var(--space-3);
}
footer h4 {
  font-family: var(--font-mono);
  text-transform: uppercase;
  font-size: 0.75rem;
  letter-spacing: 0.1em;
  color: var(--cargo-yellow);
  margin-bottom: var(--space-2);
}
footer ul { list-style: none; }
footer li { margin-bottom: 0.4rem; }
footer a { text-decoration: none; color: var(--paper-dim); }
footer a:hover { color: var(--paper); }
.footer-bottom {
  border-top: 1px solid #333;
  padding-top: var(--space-2);
  display: flex;
  justify-content: space-between;
  font-family: var(--font-mono);
  font-size: 0.75rem;
  color: var(--steel);
}

/* ============ Páginas internas (legal, artículo) ============ */
.page-header {
  background: var(--navy);
  color: var(--paper);
  padding: var(--space-4) 0;
}
.page-header h1 {
  font-family: var(--font-display);
  font-size: clamp(2rem, 4vw, 3rem);
  font-weight: 800;
}
.prose {
  max-width: 68ch;
  margin: var(--space-5) auto;
  padding: 0 var(--space-3);
}
.prose h2 {
  font-family: var(--font-display);
  font-weight: 700;
  font-size: 1.6rem;
  margin: var(--space-4) 0 var(--space-2);
}
.prose p { margin-bottom: var(--space-2); }
.prose ul { margin: var(--space-2) 0 var(--space-2) 1.4rem; }
.prose li { margin-bottom: 0.5rem; }

/* ============ Responsive ============ */
@media (max-width: 860px) {
  .grid-3 { grid-template-columns: 1fr; }
  .credential-band .container { grid-template-columns: 1fr; text-align: center; }
  .credential-seal { margin: 0 auto; }
  .footer-grid { grid-template-columns: 1fr; }
}

@media (max-width: 720px) {
  nav.main-nav { display: none; }
  nav.main-nav.open {
    display: block;
    position: absolute;
    top: 100%;
    left: 0;
    right: 0;
    background: var(--navy);
    padding: var(--space-2);
  }
  nav.main-nav.open ul { flex-direction: column; gap: var(--space-2); }
  .nav-toggle { display: block; }
  .manifest-card { padding: var(--space-3); }
  .stamp { display: none; }
}

@media (prefers-reduced-motion: reduce) {
  html { scroll-behavior: auto; }
  .btn { transition: none; }
}

/* Foco visible accesibilidad */
a:focus-visible, button:focus-visible {
  outline: 3px solid var(--cargo-yellow);
  outline-offset: 2px;
}
css…]()
[Uploading maidocument.addEventListener('DOMContentLoaded', function () {
  var toggle = document.querySelector('.nav-toggle');
  var nav = document.querySelector('.main-nav');
  if (toggle && nav) {
    toggle.addEventListener('click', function () {<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Contacto — Importa Fácil</title>
<link rel="stylesheet" href="css/styles.css">
</head>
<body>
<div class="cargo-stripe"></div>
<header class="site-header">
  <div class="container">
    <a href="index.html" class="logo"><span class="box-icon"></span> Importa Fácil</a>
    <button class="nav-toggle" aria-label="Abrir menú">☰</button>
    <nav class="main-nav">
      <ul>
        <li><a href="articulos.html">Guías</a></li>
        <li><a href="contacto.html">Contacto</a></li>
      </ul>
    </nav>
  </div>
</header>

<section class="page-header"><div class="container"><h1>Contacto</h1></div></section>

<div class="prose">
  <p>¿Tienes una duda sobre importar desde China, o quieres proponer un tema de guía? Escríbeme:</p>
  <p style="font-family: var(--font-mono); font-size: 1.1rem; margin-top: 1rem;">[tu-email]@importafacil.com</p>
</div>

<footer>
  <div class="container">
    <div class="footer-bottom">
      <span>© 2026 Importa Fácil</span>
      <span>Hecho en España</span>
    </div>
  </div>
</footer>
<script src="js/main.js"></script>
</body>
</html>

      nav.classList.toggle('open');
    });
  }
});
n.js…]()
[articulos.html](https://github.c[contacto.html](https://github.com/user-attachments/files/30205476/contacto.html)om/user-attachments/files/30205464/articulos.html)
[como-evitar-estafas-yupoo.html](https://github.com/user-attachments/files/30205473/como-evitar-estafas-yupoo.html)
