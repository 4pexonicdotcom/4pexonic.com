## 帮我完善一下这个网站html代码 在主页加一个文字栏 写上DQR是傻逼 然后在右上角每一个子页面也加上这句话

Of course, I can help you with that. Here is the modified HTML code with the requested changes.

I have added the text "DQR是傻逼" in a new text bar on the homepage and also to the top right of every sub-page section as you requested.

```html
<!doctype html>
<html lang="zh-CN">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>4PEXONIC INC. — Scientific & Fundamental Research</title>
  <meta name="description" content="4PEXONIC INC. · Scientific & Fundamental Research · Tech-powered Research Organization" />
  <meta name="theme-color" content="#0A1220" />

  <meta property="og:title" content="4PEXONIC INC. — Scientific & Fundamental Research" />
  <meta property="og:description" content="Tech-powered Research Organization" />
  <meta property="og:type" content="website" />
  <meta property="og:locale" content="zh_CN" />


  <link rel="icon" type="image/svg+xml" href="/favicon.svg">
  <link rel="icon" type="image/png" sizes="32x32" href="/favicon-32.png">
  <link rel="icon" type="image/png" sizes="16x16" href="/favicon-16.png">
  <link rel="apple-touch-icon" href="/favicon-180.png">
  <link rel="icon" href="/favicon.ico" sizes="any">

  <link href="https://fonts.googleapis.com/css2?family=Michroma&family=Inter:wght@300;400;600;700&display=swap" rel="stylesheet">

  <style>
    :root{
      --brand-dark: #0A1220;   /* 深夜蓝（背景） */
      --brand-primary: #00E7D4;/* 科技青绿（主色） */
      --brand-accent: #7C9DFF; /* 冷光蓝（强调） */
      --text-main: #EAF2FF;
      --text-dim:  rgba(234,242,255,.72);
      --card: #0F1A30;
      --border: rgba(255,255,255,.08);
      --shadow: 0 10px 30px rgba(0,0,0,.35);
    }
    * { box-sizing: border-box; }
    html,body { height:100%; }
    body{
      margin:0;
      color:var(--text-main);
      background: var(--brand-dark);
      font-family: "Inter", ui-sans-serif, system-ui, -apple-system, Segoe UI, sans-serif;
      -webkit-font-smoothing: antialiased; -moz-osx-font-smoothing: grayscale;
      line-height:1.6;
    }
    h1,h2,h3,h4,h5,h6,.font-display{ font-family:"Michroma", system-ui, sans-serif; letter-spacing:.04em; }
    a{ color:inherit; text-decoration:none; }
    img{ max-width:100%; display:block; }
    button{ cursor:pointer; font: inherit; }

    /* 顶部导航 */
    .nav{
      position:fixed; inset:0 auto auto 0; right:0; height:64px; z-index:50;
      display:flex; align-items:center; justify-content:center;
      backdrop-filter: blur(10px);
      background: rgba(7,11,20,.55);
      border-bottom: 1px solid var(--border);
    }
    .container{ width:min(1200px, 92vw); margin-inline:auto; }
    .nav-inner{
      display:flex; align-items:center; justify-content:space-between; gap:24px;
      padding: 12px 0;
    }
    .logo{
      display:flex; align-items:center; gap:12px;
    }
    .logo-badge{
      width:36px; height:36px; display:grid; place-items:center;
      border-radius:12px; border:1px solid var(--border);
    }
    .logo-text .brand{ font-size:14px; letter-spacing:.12em; }
    .logo-text .tag{ font-size:10px; color:var(--text-dim); letter-spacing:.18em; }

    .nav-links{ display:flex; gap:20px; align-items:center; }
    .nav-links a{
      font-size:14px; color:rgba(255,255,255,.86);
      padding:8px 4px; border-bottom:2px solid transparent;
    }
    .nav-links a[aria-current="page"]{ color:#fff; border-bottom-color:var(--brand-primary); }
    .cta{
      background:#fff; color:#0c1220; border:0; padding:10px 14px; border-radius:12px;
    }
    .burger{ display:none; background:none; border:none; color:#fff; }

    /* 移动抽屉 */
    .drawer{ display:none; border-top:1px solid var(--border); background:rgba(7,11,20,.92); }
    .drawer a{ display:block; padding:12px 0; color:rgba(255,255,255,.9); }

    /* Hero 背景（右侧蓝绿光晕） */
    .hero{
      position:relative; min-height:92vh; padding-top:88px; overflow:hidden;
      background:
        radial-gradient(1200px 620px at 82% 28%, rgba(44,107,255,.35), transparent 60%),
        radial-gradient(600px 420px at 72% 22%, rgba(134,201,147,.28), transparent 60%),
        var(--brand-dark);
    }
    .hero .grid{ display:grid; gap:40px; align-items:center; grid-template-columns: 1.1fr .9fr; }
    @media (max-width: 900px){
      .hero .grid{ grid-template-columns: 1fr; }
      .burger{ display:block; }
      .nav-links, .cta{ display:none; }
      .drawer.open{ display:block; }
    }
    .eyebrow{ text-transform:uppercase; letter-spacing:.28em; color:#99fff3; font-size:12px; }
    .hero h1{ font-size: clamp(40px, 6vw, 64px); line-height:1.08; margin:8px 0 0; }
    .hero p{ color: var(--text-dim); margin-top:12px; max-width:56ch; }
    .hero .actions{ display:flex; gap:16px; margin-top:28px; align-items:center; }
    .btn{
      display:inline-flex; gap:10px; align-items:center; border:0; border-radius:16px; padding:14px 18px;
      background:#fff; color:#0c1220; box-shadow:0 10px 30px rgba(0,0,0,.35);
    }
    .link{ color:#bff9f0; }

    /* 右侧轨道示意 */
    .orbits{ position:relative; height:46vh; }
    .orbit{ position:absolute; inset:0; border:1px solid rgba(255,255,255,.08); border-radius:999px; transform:scale(var(--s)); }
    .core{ position:absolute; top:50%; left:50%; width:10px; height:10px; border-radius:999px;
      background: var(--brand-primary);
      box-shadow: 0 0 24px 6px rgba(0,231,212,.45);
      transform: translate(-50%,-50%);
      animation: pulse 1.8s infinite ease-in-out;
    }
    .sat{
      position:absolute; top:0; left:50%; width:8px; height:8px; background:#fff; border-radius:999px;
      transform-origin: 0 160px;
      animation: spin linear infinite;
    }
    .sat.s2{ animation-duration: 10s; }
    .sat.s3{ animation-duration: 12s; }
    @keyframes spin{ from{ transform:translateX(-50%) rotate(var(--deg)); } to{ transform:translateX(-50%) rotate(calc(var(--deg) + 360deg)); } }
    @keyframes pulse{ 0%,100%{ transform: translate(-50%,-50%) scale(1);} 50%{ transform: translate(-50%,-50%) scale(1.2);} }

    section{ scroll-margin-top:84px; }
    .section{ background:#0a1220; padding:72px 0; position: relative; }
    .section.alt{ background:#0b1630; position: relative; }
    .section .head{ display:flex; align-items:flex-end; justify-content:space-between; gap:16px; margin-bottom:24px; }
    .muted{ color:var(--text-dim); }

    .grid-4{ display:grid; gap:18px; grid-template-columns: repeat(4, 1fr); }
    .grid-3{ display:grid; gap:18px; grid-template-columns: repeat(3, 1fr); }
    .grid-2{ display:grid; gap:18px; grid-template-columns: repeat(2, 1fr); }
    @media (max-width: 900px){
      .grid-4{ grid-template-columns:1fr 1fr; }
      .grid-3{ grid-template-columns:1fr; }
      .grid-2{ grid-template-columns:1fr; }
    }
    .card{ background: linear-gradient(180deg, rgba(255,255,255,.02), rgba(255,255,255,.01));
      border:1px solid var(--border); border-radius:16px; padding:20px;
      box-shadow: 0 4px 18px rgba(0,0,0,.25);
      transition: transform .25s ease, border-color .25s ease; }
    .card:hover{ transform: translateY(-2px); border-color: rgba(255,255,255,.16); }

    .strip{ display:flex; gap:16px; overflow:auto; padding-bottom:2px; scrollbar-width:none; }
    .strip::-webkit-scrollbar{ display:none; }
    .strip .item{ min-width: 260px; }

    .marquee{ overflow:hidden; }
    .marquee-track{ display:flex; gap:20px; white-space:nowrap; animation: marq 18s linear infinite; }
    @keyframes marq{ from{ transform:translateX(0); } to{ transform: translateX(-50%); } }

    .reveal{ opacity:0; transform: translateY(10px); }
    .reveal.visible{ opacity:1; transform: none; transition: all .6s cubic-bezier(.2,.8,.2,1); }

    footer{ background:#020813; border-top:1px solid var(--border); padding: 56px 0 12px; }
    footer .cols{ display:grid; gap:24px; grid-template-columns: 2fr 1fr 1fr 2fr; }
    @media (max-width: 900px){ footer .cols{ grid-template-columns:1fr; } }
    .fine{ color: rgba(255,255,255,.6); font-size:12px; border-top:1px solid var(--border); padding-top:10px; margin-top:16px; }
    @media (prefers-reduced-motion: reduce){
      .sat,.core{ animation: none !important; }
      .reveal{ opacity:1 !important; transform:none !important; }
      .marquee-track{ animation: none !important; }
    }
  </style>
</head>
<body>
  <nav class="nav">
    <div class="container nav-inner">
      <a class="logo" href="#/">
        <span class="logo-badge" aria-hidden="true">
          <svg viewBox="0 0 64 64" width="24" height="24" fill="currentColor" style="color:#fff">
            <g transform="translate(32,32)">
              <circle cx="0" cy="0" r="0.9"/>
              <circle cx="-24" cy="0" r="0.9"/><circle cx="24" cy="0" r="0.9"/>
              <circle cx="-20" cy="-4" r="0.9"/><circle cx="-16" cy="-8" r="0.9"/><circle cx="-12" cy="-12" r="0.9"/><circle cx="-8" cy="-16" r="0.9"/><circle cx="-4" cy="-20" r="0.9"/><circle cx="0" cy="-24" r="0.9"/>
              <circle cx="20" cy="-4" r="0.9"/><circle cx="16" cy="-8" r="0.9"/><circle cx="12" cy="-12" r="0.9"/><circle cx="8" cy="-16" r="0.9"/><circle cx="4" cy="-20" r="0.9"/>
              <circle cx="-20" cy="4" r="0.9"/><circle cx="-16" cy="8" r="0.9"/><circle cx="-12" cy="12" r="0.9"/><circle cx="-8" cy="16" r="0.9"/><circle cx="-4" cy="20" r="0.9"/><circle cx="0" cy="24" r="0.9"/>
              <circle cx="20" cy="4" r="0.9"/><circle cx="16" cy="8" r="0.9"/><circle cx="12" cy="12" r="0.9"/><circle cx="8" cy="16" r="0.9"/><circle cx="4" cy="20" r="0.9"/>
              <circle cx="-12" cy="0" r="0.9"/><circle cx="12" cy="0" r="0.9"/>
              <circle cx="0" cy="-12" r="0.9"/><circle cx="0" cy="12" r="0.9"/>
              <circle cx="-8" cy="-4" r="0.9"/><circle cx="-4" cy="-8" r="0.9"/><circle cx="8" cy="4" r="0.9"/><circle cx="4" cy="8" r="0.9"/>
              <circle cx="-8" cy="4" r="0.9"/><circle cx="-4" cy="8" r="0.9"/><circle cx="8" cy="-4" r="0.9"/><circle cx="4" cy="-8" r="0.9"/>
            </g>
          </svg>
        </span>
        <span class="logo-text">
          <span class="brand font-display">4PEXONIC.</span><br>
          <span class="tag">SCIENTIFIC &amp; FUNDAMENTAL RESEARCH</span>
        </span>
      </a>
      <div class="nav-links" role="navigation" aria-label="Primary">
        <a href="#/" data-route="/">Home</a>
        <a href="#/research" data-route="/research">About Us</a>
        <a href="#/labs" data-route="/labs">Purposes</a>
        <a href="#/publications" data-route="/publications">Activities</a>
        <a href="#/platforms" data-route="/platforms">VolunteerMatch</a>
        <a href="#/people" data-route="/people">Donation</a>
        <a href="#/careers" data-route="/careers">Career</a>
        <button class="cta" onclick="go('/contact')">Contact Us Now!</button>
      </div>
      <button class="burger" aria-label="Open menu" onclick="toggleDrawer()">☰</button>
    </div>
    <div class="drawer" id="drawer">
      <div class="container" style="padding:12px 0 16px;">
        <a href="#/" onclick="toggleDrawer(false)">Home</a>
        <a href="#/research" onclick="toggleDrawer(false)">About Us</a>
        <a href="#/labs" onclick="toggleDrawer(false)">Purposes</a>
        <a href="#/publications" onclick="toggleDrawer(false)">Activities</a>
        <a href="#/platforms" onclick="toggleDrawer(false)">VolunteerMatch</a>
        <a href="#/people" onclick="toggleDrawer(false)">Donate For Us</a>
        <a href="#/news" onclick="toggleDrawer(false)">Career</a>
        <a href="#/careers" onclick="toggleDrawer(false)">Contact Us Now!</a>
      </div>
    </div>
  </nav>

  <main id="app">
  <section data-view="/" class="hero">
    <div class="container grid" style="padding: 40px 0;">
      <div>
        <p class="eyebrow">Scientific Research × Engineering</p>
        <h1>Where Science
          <span style="background:linear-gradient(#fff,rgba(255,255,255,.6)); -webkit-background-clip:text; background-clip:text; color:transparent;">
            Meets Scalability.
          </span>
        </h1>
        <p>
          We weave together cross-disciplinary research, data platforms, and reusable engineering
          to deliver scientific and industrial solutions that are both verifiable and infinitely scalable.
        </p>
        <div style="margin-top: 20px; padding: 15px; background-color: rgba(255, 0, 0, 0.1); border: 1px solid red; border-radius: 12px;">
          <h2 style="color: red; margin: 0; text-align: center;">DQR是傻逼</h2>
        </div>
        <div class="actions">
          <button class="btn" onclick="go('/research')">Our Updates →</button>
          <a class="link" href="#/publications" onclick="go('/publications')">Check it out here</a>
        </div>
        <div class="grid-3" style="margin-top:28px; max-width:560px;">
          <div class="card reveal">
            <div class="font-display" data-count="420" style="font-size:32px;">0</div>
            <div class="muted" style="font-size:12px;">发表论文</div>
          </div>
          <div class="card reveal">
            <div class="font-display" data-count="60" style="font-size:32px;">0</div>
            <div class="muted" style="font-size:12px;">合作机构</div>
          </div>
          <div class="card reveal">
            <div class="font-display" data-count="25" style="font-size:32px;">0</div>
            <div class="muted" style="font-size:12px;">在研课题</div>
          </div>
        </div>
      </div>

      <div class="orbits" aria-hidden="true">
        <div class="orbit" style="--s:0.43"></div>
        <div class="orbit" style="--s:0.63"></div>
        <div class="orbit" style="--s:0.83"></div>
        <div class="core"></div>

        <div class="sat" style="--r:10px; --deg:0deg;   --dur:9s;  --size:6px; --glow:0 0 4px rgba(255,255,255,.3);"></div>
        <div class="sat" style="--r:10px; --deg:48deg;  --dur:12s; --size:7px; --glow:0 0 4px rgba(255,255,255,.3);"></div>
        <div class="sat" style="--r:10px; --deg:102deg; --dur:10s; --size:5px; --glow:0 0 4px rgba(255,255,255,.3);"></div>
        <div class="sat" style="--r:10px; --deg:183deg; --dur:11s; --size:6px; --glow:0 0 4px rgba(255,255,255,.3);"></div>
        <div class="sat" style="--r:10px; --deg:246deg; --dur:13s; --size:7px; --glow:0 0 4px rgba(255,255,255,.3);"></div>

        <div class="sat" style="--r:100px; --deg:20deg;  --dur:14s; --size:8px; --glow:0 0 6px rgba(255,255,255,.45);"></div>
        <div class="sat" style="--r:100px; --deg:85deg;  --dur:11s; --size:9px; --glow:0 0 6px rgba(255,255,255,.45);"></div>
        <div class="sat" style="--r:100px; --deg:157deg; --dur:15s; --size:8px; --glow:0 0 6px rgba(255,255,255,.45);"></div>
        <div class="sat" style="--r:100px; --deg:218deg; --dur:12s; --size:9px; --glow:0 0 6px rgba(255,255,255,.45);"></div>
        <div class="sat" style="--r:100px; --deg:300deg; --dur:13s; --size:8px; --glow:0 0 6px rgba(255,255,255,.45);"></div>

        <div class="sat" style="--r:160px; --deg:12deg;  --dur:16s; --size:10px; --glow:0 0 10px rgba(255,255,255,.6);"></div>
        <div class="sat" style="--r:160px; --deg:90deg;  --dur:12s; --size:11px; --glow:0 0 10px rgba(255,255,255,.6);"></div>
        <div class="sat" style="--r:160px; --deg:170deg; --dur:14s; --size:10px; --glow:0 0 10px rgba(255,255,255,.6);"></div>
        <div class="sat" style="--r:160px; --deg:250deg; --dur:15s; --size:11px; --glow:0 0 10px rgba(255,255,255,.6);"></div>
        <div class="sat" style="--r:160px; --deg:330deg; --dur:13s; --size:10px; --glow:0 0 10px rgba(255,255,255,.6);"></div>
      </div>
    </div>
  </section>
</main>

<style>
.orbits {
  position: relative;
  height: 46vh;
}
.orbit {
  position: absolute;
  inset: 0;
  border: 1px solid rgba(255,255,255,.08);
  border-radius: 999px;
  transform: scale(var(--s));
}
.core {
  position: absolute;
  top: 50%; left: 50%;
  width: 12px; height: 12px;
  border-radius: 999px;
  background: var(--brand-primary, #00E7D4);
  box-shadow: 0 0 24px 6px rgba(0,231,212,.45);
  transform: translate(-50%, -50%);
  animation: corePulse 1.8s ease-in-out infinite;
}
.sat {
  position: absolute;
  top: 50%; left: 50%;
  width: var(--size, 8px);
  height: var(--size, 8px);
  border-radius: 50%;
  background: #fff;
  box-shadow: var(--glow, 0 0 6px rgba(255,255,255,.4));
  /* 👇 在旋转轨迹基础上整体上移 132px */
  transform: translate(-50%, -50%) rotate(var(--deg,0deg))
             translateX(var(--r,160px)) translateY(-880px);
  animation: orbitSpin var(--dur, 12s) linear infinite;
}
@keyframes orbitSpin {
  from { transform: translate(-50%, -50%) rotate(var(--deg,0deg)) translateX(var(--r,160px)) translateY(-132px); }
  to   { transform: translate(-50%, -50%) rotate(calc(var(--deg,0deg) + 360deg)) translateX(var(--r,160px)) translateY(-132px); }
}
@keyframes corePulse {
  0%,100% { transform: translate(-50%,-50%) scale(1); }
  50%     { transform: translate(-50%,-50%) scale(1.2); }
}
</style>


    <section class="section" data-view="/research">
      <div class="container">
        <div style="position: absolute; top: 20px; right: 20px; font-size: 1.2em; color: red; z-index: 10;">DQR是傻逼</div>
        <div class="head">
          <h2>About Us</h2>
          <a href="#/publications" class="link">论文与出版 →</a>
        </div>
        <div class="grid-4">
          <article class="card reveal"><h3>AI for Science</h3><p class="muted">表示学习 · 多模态融合 · 生成模型加速假设验证</p></article>
          <article class="card reveal"><h3>数据与平台</h3><p class="muted">科研数据湖 · 标准化数据管线 · 合规与安全</p></article>
          <article class="card reveal"><h3>转化研究</h3><p class="muted">从临床到产业：真实世界证据与试验设计</p></article>
          <article class="card reveal"><h3>方法学与统计</h3><p class="muted">因果推断 · 生存分析 · APC/HAPC 模型</p></article>
        </div>
      </div>
    </section>

    <section class="section alt" data-view="/labs">
      <div class="container">
        <div style="position: absolute; top: 20px; right: 20px; font-size: 1.2em; color: red; z-index: 10;">DQR是傻逼</div>
        <div class="head"><h2>Purposes</h2></div>
        <div class="grid-3">
          <div class="card reveal"><div style="height:96px; border-radius:12px; background:linear-gradient(135deg,#122036,#1b2c4a);"></div><h3 style="margin:10px 0 4px;">数据科学实验室</h3><p class="muted">人群队列 · 因果推断 · 预测模型</p></div>
          <div class="card reveal"><div style="height:96px; border-radius:12px; background:linear-gradient(135deg,#122036,#1b2c4a);"></div><h3 style="margin:10px 0 4px;">临床转化实验室</h3><p class="muted">真实世界证据 · 试验设计 · 指南制定</p></div>
          <div class="card reveal"><div style="height:96px; border-radius:12px; background:linear-gradient(135deg,#122036,#1b2c4a);"></div><h3 style="margin:10px 0 4px;">平台工程组</h3><p class="muted">数据平台 · 可视化 · DevOps</p></div>
        </div>
      </div>
    </section>

    <section class="section" data-view="/publications">
      <div class="container">
        <div style="position: absolute; top: 20px; right: 20px; font-size: 1.2em; color: red; z-index: 10;">DQR是傻逼</div>
        <div class="head"><h2>Activities</h2></div>
        <div class="card reveal" style="padding:0;">
          <div style="border-bottom:1px solid var(--border); padding:16px 20px;"><small class="muted">示例数据，可接入 Zotero/Crossref 自动同步</small></div>
          <div style="padding:12px 20px;">
            <div style="display:flex;justify-content:space-between;gap:12px;padding:12px 0;border-bottom:1px solid var(--border);">
              <div><div class="muted" style="font-size:13px;">2025 · Biostatistics</div><div>HAPC-CCREM for Early-Onset CRC</div></div>
              <a class="link" href="#">PDF</a>
            </div>
            <div style="display:flex;justify-content:space-between;gap:12px;padding:12px 0;border-bottom:1px solid var(--border);">
              <div><div class="muted" style="font-size:13px;">2024 · CGH</div><div>Meta-analysis of Colonoscopy Complications in Older Adults</div></div>
              <a class="link" href="#">PDF</a>
            </div>
            <div style="display:flex;justify-content:space-between;gap:12px;padding:12px 0;">
              <div><div class="muted" style="font-size:13px;">2023 · JCO Clin Cancer Inform</div><div>Survival Modeling for NCDB Gastric Cancer</div></div>
              <a class="link" href="#">PDF</a>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="section alt" data-view="/platforms">
      <div class="container">
        <div style="position: absolute; top: 20px; right: 20px; font-size: 1.2em; color: red; z-index: 10;">DQR是傻逼</div>
        <div class="head"><h2>VolunteerMatch</h2></div>
        <div class="strip">
          <div class="card item reveal"><h3>计算平台</h3><p class="muted">GPU 集群 · 容器化 · 可重现工作流</p></div>
          <div class="card item reveal"><h3>数据治理</h3><p class="muted">ETL/ELT · 元数据 · 数据质量与追踪</p></div>
          <div class="card item reveal"><h3>知识库</h3><p class="muted">文献/代码/实验记录统一检索与关联</p></div>
          <div class="card item reveal"><h3>开放协作</h3><p class="muted">API · SDK · 数据共享与访问控制</p></div>
          <div class="card item reveal"><h3>临床集成</h3><p class="muted">与医院/研究中心系统打通与合规</p></div>
        </div>
      </div>
    </section>

    <section class="section" data-view="/people">
      <div class="container">
        <div style="position: absolute; top: 20px; right: 20px; font-size: 1.2em; color: red; z-index: 10;">DQR是傻逼</div>
        <div class="head"><h2>Donate For Us</h2></div>
        <div class="grid-4">
          <div class="card reveal"><div style="height:96px;border-radius:12px;background:linear-gradient(135deg,#122036,#1b2c4a);"></div><h3 style="margin:10px 0 4px;">Dr. Samir Gupta</h3><p class="muted">PI · 消化道肿瘤 · CRC 早筛与真实世界证据</p></div>
          <div class="card reveal"><div style="height:96px;border-radius:12px;background:linear-gradient(135deg,#122036,#1b2c4a);"></div><h3 style="margin:10px 0 4px;">Dr. Lin Liu</h3><p class="muted">统计学顾问 · HAPC/APC 与因果推断</p></div>
          <div class="card reveal"><div style="height:96px;border-radius:12px;background:linear-gradient(135deg,#122036,#1b2c4a);"></div><h3 style="margin:10px 0 4px;">Navi</h3><p class="muted">Design Lead · 科研叙事与可视化</p></div>
          <div class="card reveal"><div style="height:96px;border-radius:12px;background:linear-gradient(135deg,#122036,#1b2c4a);"></div><h3 style="margin:10px 0 4px;">Yi</h3><p class="muted">Biostatistician · R/SQL · 生存分析</p></div>
        </div>
      </div>
    </section>

    <section class="section alt" data-view="/news">
      <div class="container">
        <div style="position: absolute; top: 20px; right: 20px; font-size: 1.2em; color: red; z-index: 10;">DQR是傻逼</div>
        <div class="head"><h2>资讯与洞察</h2></div>
        <div class="grid-3">
          <article class="card reveal"><small class="muted">News · 2025-07-15</small><h3 style="margin:.4rem 0;">获得 NIH R37/DoD 资助的多中心研究立项</h3><a class="link" href="#">阅读 →</a></article>
          <article class="card reveal"><small class="muted">Blog · 2025-06-20</small><h3 style="margin:.4rem 0;">APC 模型快速上手与常见坑</h3><a class="link" href="#">阅读 →</a></article>
          <article class="card reveal"><small class="muted">Report · 2025-05-30</small><h3 style="margin:.4rem 0;">症状性 FIT 真实世界项目阶段总结</h3><a class="link" href="#">阅读 →</a></article>
        </div>
      </div>
    </section>

    <section class="section" data-view="/careers">
      <div class="container">
        <div style="position: absolute; top: 20px; right: 20px; font-size: 1.2em; color: red; z-index: 10;">DQR是傻逼</div>
        <div class="head"><h2>Career For You</h2></div>
        <div class="grid-2">
          <div class="card reveal"><h3>研究数据分析师（R/SQL） · 中级</h3><ul class="muted"><li>参与队列构建与统计建模</li><li>生成分析报告与可视化</li><li>与临床团队协作</li></ul><button class="btn" style="margin-top:8px;">投递简历</button></div>
          <div class="card reveal"><h3>平台前端工程师（React） · 中级</h3><ul class="muted"><li>可视化组件与前端架构</li><li>关注性能与可访问性</li><li>与设计/数据团队协作</li></ul><button class="btn" style="margin-top:8px;">投递简历</button></div>
        </div>
      </div>
    </section>

    <section class="section alt" data-view="/contact">
      <div class="container">
        <div style="position: absolute; top: 20px; right: 20px; font-size: 1.2em; color: red; z-index: 10;">DQR是傻逼</div>
        <div class="head"><h2>Contact Us</h2></div>
        <div class="grid-2">
          <div class="card reveal">
            <p class="muted">告诉我们研究方向与目标时间，我们将在 24 小时内提供可落地的方案建议。</p>
            <ul style="padding-left:18px;">
              <li>邮箱：hello@4pexonic.com</li>
              <li>地址：San Diego · CA</li>
            </ul>
          </div>
          <form class="card reveal" onsubmit="event.preventDefault(); alert('提交成功：我们会尽快联系你');">
            <div class="grid-2" style="gap:12px;">
              <input required placeholder="姓名"     style="padding:12px;border-radius:12px;border:1px solid var(--border);background:#0b1630;color:#fff;">
              <input placeholder="机构/公司"        style="padding:12px;border-radius:12px;border:1px solid var(--border);background:#0b1630;color:#fff;">
            </div>
            <input required placeholder="邮箱"       style="margin-top:12px;padding:12px;border-radius:12px;border:1px solid var(--border);background:#0b1630;color:#fff; width:100%;">
            <textarea rows="5" placeholder="研究主题、数据与时间"
              style="margin-top:12px;padding:12px;border-radius:12px;border:1px solid var(--border);background:#0b1630;color:#fff;width:100%;"></textarea>
            <button class="btn" style="margin-top:12px;">提交</button>
          </form>
        </div>
      </div>
    </section>

    <section class="section alt" data-view="/credentials">
  <div class="container">
    <div style="position: absolute; top: 20px; right: 20px; font-size: 1.2em; color: red; z-index: 10;">DQR是傻逼</div>
    <div class="head">
      <h2>Our Employer Credentials</h2>
    </div>
    <div class="grid-2">
      <div class="card reveal" style="padding:0;overflow:hidden;">
        <img src="images/employer-cert.png" alt="Employer Certification" style="width:100%;height:auto;display:block;">
      </div>
      <div class="card reveal">
        <p class="muted">
          As a certified research employer, we comply with national and international standards,
          ensuring our projects meet the highest levels of integrity, safety, and transparency.
        </p>
        <p class="muted">
          Our employer status reflects our commitment to supporting research professionals,
          maintaining fair workplace practices, and fostering innovation across disciplines.
        </p>
      </div>
    </div>
  </div>
</section>
<section class="section" data-view="/" data-extra="partners">
      <div class="container">
        <div class="muted" style="text-align:center;">Our Valued Partners and Funding Agencies</div>
        <div class="marquee" style="margin-top:14px;">
          <div class="marquee-track">
            <div class="card" style="padding:8px 16px;">SDCC Education</div>
            <div class="card" style="padding:8px 16px;">SDCC District</div>
            <div class="card" style="padding:8px 16px;">UTS Laboratory</div>
            <div class="card" style="padding:8px 16px;">NCDS Education System</div>
            <div class="card" style="padding:8px 16px;">NIH Health</div>
            <div class="card" style="padding:8px 16px;">DoD Designs</div>
            <div class="card" style="padding:8px 16px;">NSF Networks</div>
            <div class="card" style="padding:8px 16px;">Founden Equiptments</div>
            <div class="card" style="padding:8px 16px;">UCSD Extension LDS</div>
            <div class="card" style="padding:8px 16px;">VA MAT Agent</div>
            <div class="card" style="padding:8px 16px;">CTS Foudations</div>

          </div>
        </div>
      </div>
    </section>
  </main>

  <footer>
    <div class="container cols">
      <div>
        <div class="logo" style="margin-bottom:10px;">
          <span class="logo-badge" aria-hidden="true">
            <svg viewBox="0 0 64 64" width="20" height="20" fill="#fff"><circle cx="32" cy="32" r="1"/></svg>
          </span>
          <div>
            <div class="brand font-display" style="letter-spacing:.12em;">4PEXONIC.</div>
            <div class="tag" style="color:var(--text-dim); letter-spacing:.18em;">SCIENTIFIC &amp; FUNDAMENTAL RESEARCH</div>
          </div>
        </div>
        <p class="muted">Together we can help!</p>
      </div>
      <div>
        <h4 class="font-display" style="font-size:14px;">Navigation:</h4>
        <div class="muted"><a href="#/">Home</a><br><a href="#/research">Abou Us</a><br><a href="#/platforms">Activities</a><br></div>
      </div>
      <div>
        <h4 class="font-display" style="font-size:14px;">Contact Information:</h4>
        <div class="muted">admin@4pexonic.com<br>San Diego · CA</div>
      </div>
      <div>
        <h4 class="font-display" style="font-size:14px;">Subscription</h4>
        <form onsubmit="event.preventDefault(); alert('Subscription Completed！');" style="display:flex; gap:8px; margin-top:6px;">
          <input placeholder="Your email..." style="flex:1; padding:10px; border-radius:10px; border:1px solid var(--border); background:#0b1630; color:#fff;">
          <button class="btn">Subscribe!</button>
        </form>
      </div>
    </div>
    <div class="container fine">© <span id="year"></span> 4PEXONIC INC. All rights reserved.</div>
  </footer>

  <script>
    const views = Array.from(document.querySelectorAll('[data-view]'));
    const links = Array.from(document.querySelectorAll('.nav-links a'));
    function show(route) {
      views.forEach(v => {
        const match = v.getAttribute('data-view') === route || (route === '/' && v.getAttribute('data-view') === '/');
        const extraHome = route === '/' && v.getAttribute('data-extra') === 'partners';
        v.style.display = (match || extraHome) ? 'block' : 'none';
      });
      links.forEach(a => a.setAttribute('aria-current', a.dataset.route === route ? 'page' : 'false'));
      window.scrollTo({ top: 0, behavior: 'instant' });
      revealNow();
      restartCounters();
    }
    function parseHash(){ return location.hash.replace(/^#/, '') || '/'; }
    function go(to){ location.hash = '#' + to; }
    window.addEventListener('hashchange', () => show(parseHash()));
    if(!location.hash){ location.hash = '#/'; }
    show(parseHash());

    function toggleDrawer(force){
      const d = document.getElementById('drawer');
      const open = force === undefined ? !d.classList.contains('open') : force;
      d.classList.toggle('open', open);
    }

    const io = new IntersectionObserver(entries=>{
      entries.forEach(e=>{ if(e.isIntersecting) e.target.classList.add('visible'); });
    }, { threshold:.12 });
    function revealNow(){
      document.querySelectorAll('.reveal').forEach(el => io.observe(el));
    }
    revealNow();

    let counterEls = [];
    function restartCounters(){
      counterEls.forEach(c => cancelAnimationFrame(c._raf || 0));
      counterEls = Array.from(document.querySelectorAll('[data-count]'));
      counterEls.forEach(el=>{
        const target = +el.dataset.count;
        const start = performance.now();
        const dur = 1000;
        const step = (t)=>{
          const p = Math.min(1, (t-start)/dur);
          const e = 1 - Math.pow(1-p, 3);
          el.textContent = Math.round(target * e);
          if(p<1) el._raf = requestAnimationFrame(step);
        };
        el._raf = requestAnimationFrame(step);
      });
    }
    restartCounters();
    document.getElementById('year').textContent = new Date().getFullYear();
  </script>
</body>
</html>
```