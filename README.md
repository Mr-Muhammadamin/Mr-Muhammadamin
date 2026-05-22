<!DOCTYPE html>
<html lang="uz">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Muhammadamin Ozadov · Backend Developer & Data Analyst</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Fraunces:opsz,wght@9..144,400;9..144,500;9..144,600&family=Outfit:wght@300;400;500;600&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --cream:   #faf7f2;
    --cream-2: #f3ede2;
    --green:   #dce8d8;
    --green-d: #4a6741;
    --blue:    #e6ecf5;
    --blue-d:  #5a6b85;
    --pink:    #f5e6ec;
    --pink-d:  #85546a;
    --sand-d:  #8a7a5e;
    --ink:     #3a352e;
    --muted:   #9a8f7e;
    --soft:    #b5ab98;
    --card:    #ffffff;
    --radius:  24px;
    --display: 'Fraunces', Georgia, serif;
    --body:    'Outfit', sans-serif;
    --mono:    'JetBrains Mono', monospace;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    font-family: var(--body);
    background: var(--cream);
    color: var(--ink);
    line-height: 1.6;
    -webkit-font-smoothing: antialiased;
    overflow-x: hidden;
  }

  .wrap { max-width: 920px; margin: 0 auto; padding: 48px 24px 80px; }

  /* floating background blobs */
  .blob {
    position: fixed; border-radius: 50%; filter: blur(8px);
    opacity: 0.5; z-index: -1; animation: float 18s ease-in-out infinite;
  }
  .blob-1 { width: 320px; height: 320px; background: var(--blue);  top: -80px; right: -100px; }
  .blob-2 { width: 260px; height: 260px; background: var(--pink);  bottom: 10%; left: -120px; animation-delay: -6s; }
  .blob-3 { width: 200px; height: 200px; background: var(--green); top: 40%; right: -80px; animation-delay: -12s; }
  @keyframes float {
    0%,100% { transform: translate(0,0) scale(1); }
    50%     { transform: translate(20px,-30px) scale(1.08); }
  }

  /* entrance animation */
  .reveal { opacity: 0; transform: translateY(24px); animation: rise 0.8s cubic-bezier(.2,.7,.3,1) forwards; }
  @keyframes rise { to { opacity: 1; transform: translateY(0); } }

  /* ---------- HEADER ---------- */
  .hero {
    background: var(--card);
    border-radius: var(--radius);
    padding: 40px;
    display: flex; gap: 28px; align-items: center;
    box-shadow: 0 8px 40px rgba(120,110,90,0.08);
    position: relative; overflow: hidden;
  }
  .hero::before {
    content: ""; position: absolute; width: 180px; height: 180px;
    background: var(--green); border-radius: 50%; top: -60px; right: -40px; opacity: 0.4;
  }
  .avatar {
    width: 104px; height: 104px; border-radius: 30px; flex-shrink: 0;
    background: var(--green); color: var(--green-d);
    display: flex; align-items: center; justify-content: center;
    font-family: var(--display); font-size: 40px; font-weight: 600;
    position: relative; z-index: 1;
  }
  .hero-text { position: relative; z-index: 1; }
  .hero h1 {
    font-family: var(--display); font-size: 42px; font-weight: 600;
    letter-spacing: -1px; line-height: 1.05; margin-bottom: 6px;
  }
  .hero .role { color: var(--muted); font-size: 18px; margin-bottom: 16px; }
  .pills { display: flex; gap: 8px; flex-wrap: wrap; }
  .pill {
    font-size: 14px; font-weight: 500; padding: 6px 14px; border-radius: 14px;
    transition: transform .2s ease;
  }
  .pill:hover { transform: translateY(-3px); }
  .pill.g { background: var(--green); color: var(--green-d); }
  .pill.b { background: var(--blue);  color: var(--blue-d); }
  .pill.p { background: var(--pink);  color: var(--pink-d); }
  .pill.s { background: var(--cream-2); color: var(--sand-d); }

  /* ---------- SECTION ---------- */
  section { margin-top: 40px; }
  .sec-head {
    display: flex; align-items: center; gap: 12px; margin-bottom: 20px;
  }
  .sec-icon {
    width: 44px; height: 44px; border-radius: 14px;
    display: flex; align-items: center; justify-content: center; font-size: 20px;
  }
  .sec-head h2 {
    font-family: var(--display); font-size: 26px; font-weight: 600; letter-spacing: -0.5px;
  }
  .ic-g { background: var(--green); } .ic-b { background: var(--blue); }
  .ic-p { background: var(--pink); }  .ic-s { background: var(--cream-2); }

  /* about */
  .about-grid { display: grid; grid-template-columns: 1.4fr 1fr; gap: 20px; }
  .card {
    background: var(--card); border-radius: 20px; padding: 26px;
    box-shadow: 0 4px 24px rgba(120,110,90,0.06);
  }
  .about-list { list-style: none; margin-top: 14px; }
  .about-list li { padding: 5px 0; color: var(--ink); font-size: 15px; }
  .code-card {
    background: #2f2a24; border-radius: 20px; padding: 22px;
    font-family: var(--mono); font-size: 13.5px; line-height: 1.8; color: #e8e0d4;
  }
  .code-card .k { color: #c9a8d4; } .code-card .s { color: #a8c99a; } .code-card .f { color: #e0b88a; }

  /* stack */
  .stack-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 16px; }
  .stack-card { background: var(--card); border-radius: 20px; padding: 22px; box-shadow: 0 4px 24px rgba(120,110,90,0.06); }
  .stack-card h3 { font-size: 14px; font-weight: 600; margin-bottom: 14px; display: flex; align-items: center; gap: 8px; }
  .stack-card.g h3 { color: var(--green-d); } .stack-card.b h3 { color: var(--blue-d); } .stack-card.p h3 { color: var(--pink-d); }
  .tech { display: flex; flex-wrap: wrap; gap: 8px; }
  .tech span {
    font-size: 13px; padding: 5px 12px; border-radius: 12px;
    background: var(--cream); color: var(--ink); transition: all .2s ease;
  }
  .stack-card.g .tech span:hover { background: var(--green); }
  .stack-card.b .tech span:hover { background: var(--blue); }
  .stack-card.p .tech span:hover { background: var(--pink); }

  /* stats */
  .stats-grid { display: grid; grid-template-columns: repeat(4, 1fr); gap: 14px; margin-bottom: 18px; }
  .stat {
    background: var(--card); border-radius: 18px; padding: 20px 16px; text-align: center;
    box-shadow: 0 4px 24px rgba(120,110,90,0.06);
  }
  .stat .num { font-family: var(--display); font-size: 30px; font-weight: 600; color: var(--pink-d); }
  .stat .lbl { font-size: 12px; color: var(--muted); margin-top: 4px; }
  .langbar-card { background: var(--card); border-radius: 20px; padding: 24px; box-shadow: 0 4px 24px rgba(120,110,90,0.06); }
  .langbar-card .t { font-size: 13px; color: var(--muted); margin-bottom: 12px; font-weight: 500; }
  .langbar { display: flex; height: 14px; border-radius: 8px; overflow: hidden; margin-bottom: 14px; }
  .langbar i { display: block; height: 100%; }
  .leg { display: flex; gap: 18px; flex-wrap: wrap; font-size: 13px; }
  .leg span { display: flex; align-items: center; gap: 6px; color: var(--ink); }
  .dot { width: 10px; height: 10px; border-radius: 50%; }

  /* contact */
  .contact { display: flex; gap: 12px; flex-wrap: wrap; justify-content: center; }
  .clink {
    display: flex; align-items: center; gap: 10px; text-decoration: none;
    padding: 14px 22px; border-radius: 16px; font-weight: 500; font-size: 15px;
    transition: transform .2s ease, box-shadow .2s ease;
  }
  .clink:hover { transform: translateY(-4px); box-shadow: 0 10px 24px rgba(120,110,90,0.12); }
  .clink.g { background: var(--green); color: var(--green-d); }
  .clink.b { background: var(--blue);  color: var(--blue-d); }
  .clink.p { background: var(--pink);  color: var(--pink-d); }
  .clink.s { background: var(--cream-2); color: var(--sand-d); }
  .clink svg { width: 20px; height: 20px; }

  footer { text-align: center; margin-top: 50px; color: var(--soft); font-size: 14px; font-style: italic; }

  /* responsive */
  @media (max-width: 700px) {
    .hero { flex-direction: column; text-align: center; padding: 32px 24px; }
    .pills { justify-content: center; }
    .about-grid { grid-template-columns: 1fr; }
    .stack-grid { grid-template-columns: 1fr; }
    .stats-grid { grid-template-columns: repeat(2, 1fr); }
    .hero h1 { font-size: 34px; }
  }
</style>
</head>
<body>

<div class="blob blob-1"></div>
<div class="blob blob-2"></div>
<div class="blob blob-3"></div>

<div class="wrap">

  <!-- HERO -->
  <div class="hero reveal" style="animation-delay:.05s">
    <div class="avatar">MO</div>
    <div class="hero-text">
      <h1>Muhammadamin Ozadov</h1>
      <p class="role">Backend Developer · Data Analyst · Toshkent 🇺🇿</p>
      <div class="pills">
        <span class="pill g">Python</span>
        <span class="pill b">T-SQL</span>
        <span class="pill p">Power BI</span>
        <span class="pill s">FastAPI</span>
      </div>
    </div>
  </div>

  <!-- ABOUT -->
  <section class="reveal" style="animation-delay:.15s">
    <div class="sec-head">
      <div class="sec-icon ic-g">👋</div>
      <h2>Men haqimda</h2>
    </div>
    <div class="about-grid">
      <div class="card">
        <p>Salom! Men <b>Muhammadamin</b> — Python backend dasturchisi va ma'lumot tahlilchisiman. Backend tizimlarini quraman, SQL so'rovlarini optimallashtiraman va Power BI orqali raqamlardan biznes uchun ma'no chiqaraman.</p>
        <ul class="about-list">
          <li>🔭 Backend API va ma'lumotlar tahlili ustida ishlayapman</li>
          <li>🌱 Data Engineering va system design'ni o'rganyapman</li>
          <li>💬 Python, SQL va BI bo'yicha murojaat qiling</li>
          <li>📊 Raqamlardan hikoya yaratishni yaxshi ko'raman</li>
        </ul>
      </div>
      <div class="code-card">
<span class="k">def</span> <span class="f">muhammadamin</span>():<br>
&nbsp;&nbsp;<span class="k">return</span> {<br>
&nbsp;&nbsp;&nbsp;&nbsp;<span class="s">"rol"</span>: <span class="s">"Backend & Analyst"</span>,<br>
&nbsp;&nbsp;&nbsp;&nbsp;<span class="s">"til"</span>: [<span class="s">"Python"</span>, <span class="s">"SQL"</span>],<br>
&nbsp;&nbsp;&nbsp;&nbsp;<span class="s">"joy"</span>: <span class="s">"Toshkent"</span>,<br>
&nbsp;&nbsp;&nbsp;&nbsp;<span class="s">"sevimli"</span>: <span class="s">"toza kod"</span>,<br>
&nbsp;&nbsp;}
      </div>
    </div>
  </section>

  <!-- STACK -->
  <section class="reveal" style="animation-delay:.25s">
    <div class="sec-head">
      <div class="sec-icon ic-b">🛠️</div>
      <h2>Texnologiyalar</h2>
    </div>
    <div class="stack-grid">
      <div class="stack-card g">
        <h3>⚙️ Backend</h3>
        <div class="tech"><span>Python</span><span>FastAPI</span><span>Django</span><span>Flask</span></div>
      </div>
      <div class="stack-card p">
        <h3>📊 Data & BI</h3>
        <div class="tech"><span>Power BI</span><span>Pandas</span><span>NumPy</span><span>Plotly</span></div>
      </div>
      <div class="stack-card b">
        <h3>🗄️ Bazalar</h3>
        <div class="tech"><span>T-SQL</span><span>PostgreSQL</span><span>MySQL</span></div>
      </div>
      <div class="stack-card b">
        <h3>🧰 Vositalar</h3>
        <div class="tech"><span>Git</span><span>Docker</span><span>Linux</span></div>
      </div>
      <div class="stack-card g">
        <h3>💻 Muhit</h3>
        <div class="tech"><span>VS Code</span><span>Jupyter</span></div>
      </div>
      <div class="stack-card p">
        <h3>📈 Analitika</h3>
        <div class="tech"><span>DAX</span><span>Excel</span></div>
      </div>
    </div>
  </section>

  <!-- STATS -->
  <section class="reveal" style="animation-delay:.35s">
    <div class="sec-head">
      <div class="sec-icon ic-p">📊</div>
      <h2>Statistika</h2>
    </div>
    <div class="stats-grid">
      <div class="stat"><div class="num" id="st-repos">—</div><div class="lbl">repolar</div></div>
      <div class="stat"><div class="num" id="st-stars">—</div><div class="lbl">yulduzlar</div></div>
      <div class="stat"><div class="num" id="st-followers">—</div><div class="lbl">followerlar</div></div>
      <div class="stat"><div class="num" id="st-following">—</div><div class="lbl">following</div></div>
    </div>
    <div class="langbar-card">
      <div class="t">Top tillar <span id="lang-status" style="color:var(--soft);font-weight:400;">(yuklanmoqda…)</span></div>
      <div class="langbar" id="langbar">
        <i style="width:100%;background:var(--cream-2)"></i>
      </div>
      <div class="leg" id="langleg"></div>
    </div>
  </section>

  <!-- CONTACT -->
  <section class="reveal" style="animation-delay:.45s">
    <div class="sec-head">
      <div class="sec-icon ic-s">✉️</div>
      <h2>Aloqa</h2>
    </div>
    <div class="contact">
      <a class="clink g" href="mailto:muhammadaminozadov@gmail.com">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 4h16v16H4z"/><path d="m4 6 8 6 8-6"/></svg> Email
      </a>
      <a class="clink b" href="https://www.linkedin.com/in/muhammadamin-ozadov" target="_blank">
        <svg viewBox="0 0 24 24" fill="currentColor"><path d="M19 3a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V5a2 2 0 0 1 2-2h14m-.5 15.5v-5.3a3.26 3.26 0 0 0-3.26-3.26c-.85 0-1.84.52-2.32 1.3v-1.11h-2.79v8.37h2.79v-4.93c0-.77.62-1.4 1.39-1.4a1.4 1.4 0 0 1 1.4 1.4v4.93h2.79M6.88 8.56a1.68 1.68 0 0 0 1.68-1.68c0-.93-.75-1.69-1.68-1.69a1.69 1.69 0 0 0-1.69 1.69c0 .93.76 1.68 1.69 1.68m1.39 9.94v-8.37H5.5v8.37h2.77z"/></svg> LinkedIn
      </a>
      <a class="clink p" href="https://t.me/Muhammadamin_Ozadov" target="_blank">
        <svg viewBox="0 0 24 24" fill="currentColor"><path d="M9.78 18.65l.28-4.23 7.68-6.92c.34-.31-.07-.46-.52-.19L7.74 13.3 3.64 12c-.88-.25-.89-.86.2-1.3l15.97-6.16c.73-.33 1.43.18 1.15 1.3l-2.72 12.81c-.19.91-.74 1.13-1.5.71L12.6 16.3l-1.99 1.93c-.23.23-.42.42-.83.42z"/></svg> Telegram
      </a>
      <a class="clink s" href="https://github.com/Mr-Muhammadamin" target="_blank">
        <svg viewBox="0 0 24 24" fill="currentColor"><path d="M12 2A10 10 0 0 0 2 12c0 4.42 2.87 8.17 6.84 9.5.5.08.66-.23.66-.5v-1.69c-2.77.6-3.36-1.34-3.36-1.34-.46-1.16-1.11-1.47-1.11-1.47-.91-.62.07-.6.07-.6 1 .07 1.53 1.03 1.53 1.03.87 1.52 2.34 1.07 2.91.83.09-.65.35-1.09.63-1.34-2.22-.25-4.55-1.11-4.55-4.92 0-1.11.38-2 1.03-2.71-.1-.25-.45-1.29.1-2.64 0 0 .84-.27 2.75 1.02.79-.22 1.65-.33 2.5-.33.85 0 1.71.11 2.5.33 1.91-1.29 2.75-1.02 2.75-1.02.55 1.35.2 2.39.1 2.64.65.71 1.03 1.6 1.03 2.71 0 3.82-2.34 4.66-4.57 4.91.36.31.69.92.69 1.85V21c0 .27.16.59.67.5C19.14 20.16 22 16.42 22 12A10 10 0 0 0 12 2z"/></svg> GitHub
      </a>
    </div>
  </section>

  <footer class="reveal" style="animation-delay:.55s">
    💚 Tashrifingiz uchun rahmat — keling, biror zo'r narsa quraylik!
  </footer>

</div>

<script>
  const USER = "Mr-Muhammadamin";

  // raqamni 0 dan animatsiya bilan chiqarish
  function animateCount(el, target) {
    let cur = 0;
    const step = Math.max(1, Math.round(target / 40));
    const timer = setInterval(() => {
      cur += step;
      if (cur >= target) { cur = target; clearInterval(timer); }
      el.textContent = cur;
    }, 30);
  }

  // pastel ranglar tillar uchun
  const LANG_COLORS = ["#4a6741", "#5a6b85", "#85546a", "#8a7a5e", "#7a9b6e", "#6a7ba0"];

  async function loadGitHub() {
    try {
      // 1) asosiy profil ma'lumotlari
      const u = await fetch(`https://api.github.com/users/${USER}`).then(r => {
        if (!r.ok) throw new Error("user");
        return r.json();
      });

      animateCount(document.getElementById("st-repos"), u.public_repos || 0);
      animateCount(document.getElementById("st-followers"), u.followers || 0);
      animateCount(document.getElementById("st-following"), u.following || 0);

      // 2) barcha repolar — yulduzlar yig'indisi va tillar uchun
      const repos = await fetch(`https://api.github.com/users/${USER}/repos?per_page=100&sort=updated`).then(r => r.json());

      let stars = 0;
      const langCount = {};
      if (Array.isArray(repos)) {
        repos.forEach(repo => {
          stars += repo.stargazers_count || 0;
          if (repo.language) {
            langCount[repo.language] = (langCount[repo.language] || 0) + 1;
          }
        });
      }
      animateCount(document.getElementById("st-stars"), stars);

      // 3) til taqsimotini chizish
      renderLangs(langCount);
    } catch (e) {
      document.getElementById("lang-status").textContent = "(yuklab bo'lmadi — keyinroq urinib ko'ring)";
      ["st-repos","st-stars","st-followers","st-following"].forEach(id => {
        const el = document.getElementById(id);
        if (el.textContent === "—") el.textContent = "0";
      });
    }
  }

  function renderLangs(langCount) {
    const status = document.getElementById("lang-status");
    const bar = document.getElementById("langbar");
    const leg = document.getElementById("langleg");

    const entries = Object.entries(langCount).sort((a, b) => b[1] - a[1]).slice(0, 6);
    if (entries.length === 0) {
      status.textContent = "(til topilmadi)";
      return;
    }
    const total = entries.reduce((s, [, n]) => s + n, 0);

    status.textContent = "";
    bar.innerHTML = "";
    leg.innerHTML = "";

    entries.forEach(([lang, n], i) => {
      const pct = Math.round((n / total) * 100);
      const color = LANG_COLORS[i % LANG_COLORS.length];

      const seg = document.createElement("i");
      seg.style.width = pct + "%";
      seg.style.background = color;
      bar.appendChild(seg);

      const item = document.createElement("span");
      item.innerHTML = `<i class="dot" style="background:${color}"></i> ${lang} ${pct}%`;
      leg.appendChild(item);
    });
  }

  // sahifa ko'ringanda yuklash
  const obs = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) { loadGitHub(); obs.disconnect(); }
    });
  }, { threshold: 0.3 });
  obs.observe(document.querySelector(".stats-grid"));
</script>

</body>
</html>
