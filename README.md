
<!doctype html>
<html lang="es">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Mini‑web divertida</title>
  <meta name="description" content="Página web ligera y divertida para pasar el rato" />
  <style>
    :root{
      --bg:#0f1226;--text:#e8eaff;--muted:#b7baf3;--card:#191c36;--primary:#7c3aed;--accent:#22d3ee;--ring:#a78bfa;
      --shadow:0 10px 30px rgba(0,0,0,.35);
    }
    :root.light{--bg:#f7f7fb;--text:#0f1226;--muted:#4b4e72;--card:#ffffff;--primary:#7c3aed;--accent:#0ea5e9;--ring:#7c3aed;--shadow:0 10px 30px rgba(17,24,39,.12)}
    *{box-sizing:border-box}
    html,body{height:100%}
    body{margin:0;font-family:Inter,system-ui,-apple-system,Segoe UI,Roboto,Ubuntu,Cantarell,Noto Sans,sans-serif;background:var(--bg);color:var(--text);line-height:1.5}
    a{color:inherit;text-decoration:none}
    .container{max-width:1100px;margin-inline:auto;padding:24px}
    header{position:sticky;top:0;backdrop-filter:saturate(160%) blur(10px);background:color-mix(in oklab,var(--bg) 75%, transparent);border-bottom:1px solid color-mix(in oklab,var(--text) 10%, transparent);z-index:10}
    nav{display:flex;align-items:center;gap:16px;justify-content:space-between}
    .brand{display:flex;align-items:center;gap:12px;font-weight:800;letter-spacing:.2px}
    .brand .logo{width:28px;height:28px;border-radius:8px;background:conic-gradient(from 120deg at 50% 50%,var(--primary),var(--accent),var(--primary));box-shadow:inset 0 0 12px rgba(255,255,255,.35)}
    .nav-links{display:flex;gap:18px;flex-wrap:wrap}
    .btn{display:inline-flex;align-items:center;gap:8px;border:1px solid color-mix(in oklab,var(--ring) 60%, transparent);padding:10px 14px;border-radius:12px;background:linear-gradient(180deg,color-mix(in oklab,var(--card) 70%, transparent),color-mix(in oklab,var(--card) 100%, transparent));box-shadow:var(--shadow);cursor:pointer;color:var(--text)}
    .btn:hover{transform:translateY(-1px)}
    .btn-ghost{background:transparent;border-color:color-mix(in oklab,var(--ring) 35%, transparent)}
    .hero{position:relative;isolation:isolate}
    .hero .grid{display:grid;grid-template-columns:1.1fr .9fr;gap:28px;align-items:center}
    @media (max-width:900px){.hero .grid{grid-template-columns:1fr;}}
    .badge{display:inline-flex;gap:8px;align-items:center;font-size:.9rem;color:var(--muted);background:color-mix(in oklab,var(--text) 10%, transparent);padding:6px 10px;border-radius:999px;border:1px solid color-mix(in oklab,var(--ring) 25%, transparent)}
    .title{font-size:clamp(28px,5vw,46px);line-height:1.1;margin:10px 0 12px}
    .lead{color:var(--muted);font-size:clamp(14px,2.2vw,18px)}
    .cards{display:grid;grid-template-columns:repeat(3,1fr);gap:18px;margin-top:22px}
    @media (max-width:900px){.cards{grid-template-columns:1fr 1fr}}@media (max-width:640px){.cards{grid-template-columns:1fr}}
    .card{padding:18px;border:1px solid color-mix(in oklab,var(--ring) 20%, transparent);background:var(--card);border-radius:16px;box-shadow:var(--shadow)}
    .card h3{margin:0 0 6px;font-size:1.05rem}
    .pill{font-size:.75rem;color:var(--muted)}
    .section{padding:40px 0}
    .gallery{display:grid;grid-template-columns:repeat(6,1fr);gap:8px}
    @media (max-width:900px){.gallery{grid-template-columns:repeat(3,1fr)}}@media (max-width:640px){.gallery{grid-template-columns:repeat(2,1fr)}}
    .thumb{aspect-ratio:1/1;border-radius:14px;overflow:hidden;border:1px solid color-mix(in oklab,var(--ring) 18%, transparent);background:linear-gradient(120deg, color-mix(in oklab,var(--primary) 60%, transparent), color-mix(in oklab,var(--accent) 50%, transparent));position:relative}
    .thumb::after{content:"";position:absolute;inset:0;background:radial-gradient(70% 50% at 40% 0%,rgba(255,255,255,.35),transparent 70%)}
    .aside{display:grid;gap:12px}
    .game{padding:18px;border-radius:16px;background:var(--card);border:1px solid color-mix(in oklab,var(--ring) 20%, transparent);box-shadow:var(--shadow)}
    .field{display:grid;grid-template-columns:1fr auto;gap:10px}
    input,textarea{width:100%;padding:12px 14px;border-radius:12px;border:1px solid color-mix(in oklab,var(--ring) 25%, transparent);background:color-mix(in oklab,var(--bg) 60%, white);color:var(--text)}
    label{font-size:.9rem;color:var(--muted)}
    footer{padding:36px 0;color:var(--muted);border-top:1px solid color-mix(in oklab,var(--text) 10%, transparent)}
    .gradient-bg{position:absolute;inset:-80px -20px auto -20px;height:420px;z-index:-1;background:
      radial-gradient(40% 50% at 20% 20%, color-mix(in oklab,var(--primary) 35%, transparent), transparent 60%),
      radial-gradient(40% 60% at 70% 0%, color-mix(in oklab,var(--accent) 50%, transparent), transparent 70%),
      radial-gradient(60% 60% at 90% 80%, color-mix(in oklab,var(--ring) 50%, transparent), transparent 70%);
      filter:saturate(120%) blur(30px);opacity:.55;pointer-events:none}
    .visually-hidden{position:absolute;inline-size:1px;block-size:1px;clip:rect(0 0 0 0);clip-path:inset(50%);overflow:hidden;white-space:nowrap}
  </style>
</head>
<body>
  <header>
    <div class="container">
      <nav aria-label="Principal">
        <a class="brand" href="#inicio" aria-label="Ir al inicio">
          <span class="logo" aria-hidden="true"></span>
          <span>Web Divertida</span>
        </a>
        <div class="nav-links">
          <a href="#actividades">Actividades</a>
          <a href="#galeria">Galería</a>
          <a href="#contacto">Contacto</a>
          <button id="themeToggle" class="btn btn-ghost" aria-pressed="false" aria-label="Cambiar tema">🌙/☀️</button>
        </div>
      </nav>
    </div>
  </header>

  <main id="inicio" class="container hero">
    <div class="gradient-bg" aria-hidden="true"></div>
    <section class="grid section" aria-labelledby="t-hero">
      <div>
        <span class="badge">✨ Hecha para ti en un solo archivo</span>
        <h1 id="t-hero" class="title">¡Hola! Esta es una mini‑web para jugar, probar ideas y pasar el rato 🎉</h1>
        <p class="lead">Totalmente responsive, ligera y sin dependencias. Puedes cambiar colores, texto y secciones a tu gusto.
        </p>
        <div style="display:flex;gap:12px;flex-wrap:wrap;margin-top:14px">
          <a class="btn" href="#actividades">Ver actividades</a>
          <button class="btn btn-ghost" id="confettiBtn">Lluvia de confeti</button>
        </div>
      </div>
      <aside class="aside">
        <div class="card">
          <h3>¿Qué trae?</h3>
          <p class="pill">• Cambiador de tema • Galería • Mini‑juego de clics • Formulario • Diseño moderno</p>
        </div>
        <div class="card">
          <h3>Cómo editar</h3>
          <p class="pill">Abre este archivo y cambia textos/colores. Todo está en un solo HTML con CSS y JS.</p>
        </div>
      </aside>
    </section>
  </main>

  <section id="actividades" class="container section" aria-labelledby="t-acts">
    <h2 id="t-acts" class="title">Actividades rápidas</h2>
    <div class="cards">
      <article class="card">
        <h3>Mini‑juego de clics</h3>
        <p class="pill">Haz clic y trata de superar tu récord.</p>
        <div class="game">
          <p><strong>Puntuación:</strong> <span id="score">0</span> · <strong>Mejor:</strong> <span id="best">0</span></p>
          <button id="tap" class="btn" style="width:100%">¡Clic aquí!</button>
          <div style="display:flex;gap:10px;margin-top:10px">
            <button id="reset" class="btn btn-ghost" style="flex:1">Reiniciar</button>
            <button id="frenzy" class="btn" style="flex:1">Modo Frenesí (5s)</button>
          </div>
        </div>
      </article>
      <article class="card">
        <h3>Dados de decisión</h3>
        <p class="pill">¿Pizza o estudio? Lanza y decide 😅</p>
        <div class="game">
          <div style="font-size:2.2rem;text-align:center" id="dice">🎲</div>
          <button class="btn" style="width:100%" id="roll">Lanzar</button>
        </div>
      </article>
      <article class="card">
        <h3>Temporizador 25/5</h3>
        <p class="pill">Pequeño Pomodoro: 25 min foco, 5 min break.</p>
        <div class="game">
          <p><strong>Tiempo:</strong> <span id="timer">25:00</span></p>
          <div class="field">
            <button id="startPom" class="btn">Iniciar</button>
            <button id="pausePom" class="btn btn-ghost">Pausar</button>
          </div>
        </div>
      </article>
    </div>
  </section>

  <section id="galeria" class="container section" aria-labelledby="t-gal">
    <h2 id="t-gal" class="title">Galería generativa</h2>
    <p class="lead">Imágenes de muestra con gradientes. Reemplázalas por tus fotos (arrastrar y soltar también funciona).</p>
    <div class="gallery" id="gallery" aria-live="polite">
      <!-- 12 thumbs -->
      <div class="thumb" draggable="true" title="Arrástrame"></div>
      <div class="thumb" draggable="true"></div>
      <div class="thumb" draggable="true"></div>
      <div class="thumb" draggable="true"></div>
      <div class="thumb" draggable="true"></div>
      <div class="thumb" draggable="true"></div>
      <div class="thumb" draggable="true"></div>
      <div class="thumb" draggable="true"></div>
      <div class="thumb" draggable="true"></div>
      <div class="thumb" draggable="true"></div>
      <div class="thumb" draggable="true"></div>
      <div class="thumb" draggable="true"></div>
    </div>
    <p class="pill" style="margin-top:10px">Tip: suelta una imagen desde tu PC sobre un cuadro para reemplazarlo.</p>
  </section>

  <section id="contacto" class="container section" aria-labelledby="t-contact">
    <h2 id="t-contact" class="title">Contacto</h2>
    <form class="card" onsubmit="event.preventDefault(); alert('¡Gracias por tu mensaje! (demo)')">
      <div class="field">
        <div>
          <label for="nombre">Nombre</label>
          <input id="nombre" placeholder="Tu nombre" required />
        </div>
        <div>
          <label for="correo">Correo</label>
          <input id="correo" type="email" placeholder="tucorreo@email.com" required />
        </div>
      </div>
      <div style="margin-top:10px">
        <label for="mensaje">Mensaje</label>
        <textarea id="mensaje" rows="4" placeholder="Escribe algo bonito…"></textarea>
      </div>
      <div style="margin-top:12px;display:flex;gap:10px;justify-content:flex-end">
        <button class="btn btn-ghost" type="reset">Limpiar</button>
        <button class="btn" type="submit">Enviar</button>
      </div>
    </form>
  </section>

  <footer>
    <div class="container" style="display:flex;justify-content:space-between;flex-wrap:wrap;gap:10px">
      <p>Hecho con ❤️ y vanilla JS · Accesible y responsive</p>
      <p><a href="#inicio" class="pill">Volver arriba ↑</a></p>
    </div>
  </footer>

  <canvas id="confetti" class="visually-hidden" aria-hidden="true"></canvas>

  <script>
    // Tema claro/oscuro
    const root = document.documentElement;
    const toggle = document.getElementById('themeToggle');
    function setTheme(light){
      root.classList.toggle('light', light);
      toggle.setAttribute('aria-pressed', String(light));
      localStorage.setItem('themeLight', light ? '1' : '0');
    }
    setTheme(localStorage.getItem('themeLight') === '1');
    toggle.addEventListener('click', ()=> setTheme(!root.classList.contains('light')));

    // Mini‑juego de clics
    let score = 0, best = Number(localStorage.getItem('bestScore')||0), frenzy = false, frenT;
    const $ = id=>document.getElementById(id);
    $('best').textContent = best;
    $('tap').addEventListener('click', ()=>{ score += frenzy?2:1; $('score').textContent = score; if(score>best){best=score; localStorage.setItem('bestScore', best); $('best').textContent=best;} });
    $('reset').addEventListener('click', ()=>{ score = 0; $('score').textContent = 0; });
    $('frenzy').addEventListener('click', ()=>{
      if(frenT) clearTimeout(frenT);
      frenzy = true; $('frenzy').textContent='¡Aprovecha!';
      frenT = setTimeout(()=>{ frenzy=false; $('frenzy').textContent='Modo Frenesí (5s)'; },5000);
    });

    // Dado
    const faces = ['🎯','🍕','📚','🥤','🎮','💤'];
    $('roll').addEventListener('click', ()=>{ $('dice').textContent = faces[Math.floor(Math.random()*faces.length)]; });

    // Pomodoro 25/5
    let pom=25*60, iv, paused=true;
    const fmt=s=>`${String(Math.floor(s/60)).padStart(2,'0')}:${String(Math.floor(s%60)).padStart(2,'0')}`;
    const tick=()=>{ if(paused) return; if(pom>0){ pom--; $('timer').textContent=fmt(pom);} else { paused=true; alert('¡Descanso! 5 minutos'); pom=5*60; $('timer').textContent=fmt(pom);} };
    $('startPom').addEventListener('click', ()=>{ if(iv) clearInterval(iv); paused=false; iv=setInterval(tick,1000);});
    $('pausePom').addEventListener('click', ()=>{ paused=!paused; });

    // Galería: drag & drop para reemplazar imágenes
    const gallery = document.getElementById('gallery');
    gallery.addEventListener('dragover', e=>e.preventDefault());
    gallery.addEventListener('drop', e=>{
      e.preventDefault();
      const file = e.dataTransfer.files?.[0];
      if(!file) return;
      const url = URL.createObjectURL(file);
      const target = document.elementFromPoint(e.clientX, e.clientY);
      if(target && target.classList.contains('thumb')){
        target.style.background = `center/cover no-repeat url('${url}')`;
      }
    });

    // Confeti liviano en canvas
    const cvs = document.getElementById('confetti');
    const ctx = cvs.getContext('2d');
    function confetti(){
      const W = cvs.width = innerWidth, H = cvs.height = 300; cvs.classList.remove('visually-hidden');
      const N = 140; const p=[]; for(let i=0;i<N;i++){ p.push({x:Math.random()*W,y:Math.random()*-H/2,r:2+Math.random()*4,vy:2+Math.random()*3,color:`hsl(${Math.random()*360} 90% 60%)`}); }
      let t=0; const id = setInterval(()=>{
        ctx.clearRect(0,0,W,H); t++;
        p.forEach(o=>{ o.y+=o.vy; o.x+=Math.sin(t/10+o.y/30); ctx.fillStyle=o.color; ctx.beginPath(); ctx.arc(o.x,o.y,o.r,0,Math.PI*2); ctx.fill(); });
        if(t>220){ clearInterval(id); cvs.classList.add('visually-hidden'); }
      },16);
    }
    document.getElementById('confettiBtn').addEventListener('click', confetti);
  </script>
</body>
</html>
