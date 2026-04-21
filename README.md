<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>craftedbysahil — Web Designer & Developer</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=Outfit:wght@300;400;500;600;700;800;900&display=swap" rel="stylesheet">
<style>
:root {
  --red: #c0152a;
  --red2: #e01a32;
  --red-glow: rgba(192,21,42,0.35);
  --red-soft: rgba(192,21,42,0.12);
  --bg: #0a0205;
  --bg2: #0f0308;
  --bg3: #150509;
  --card: rgba(255,255,255,0.03);
  --border: rgba(192,21,42,0.2);
  --border2: rgba(192,21,42,0.08);
  --text: #f5e8ea;
  --muted: #9a7e82;
  --white: #ffffff;
}
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
html{scroll-behavior:smooth}
body{
  font-family:'Space Grotesk',sans-serif;
  background:var(--bg);
  color:var(--text);
  overflow-x:hidden;
  cursor:none;
}

/* CUSTOM CURSOR */
.cursor{
  position:fixed;width:10px;height:10px;
  background:var(--red2);border-radius:50%;
  pointer-events:none;z-index:9999;
  transform:translate(-50%,-50%);
  transition:transform 0.1s,width 0.2s,height 0.2s;
  box-shadow:0 0 10px var(--red-glow),0 0 20px var(--red-glow);
}
.cursor-ring{
  position:fixed;width:32px;height:32px;
  border:1px solid rgba(192,21,42,0.5);
  border-radius:50%;pointer-events:none;z-index:9998;
  transform:translate(-50%,-50%);
  transition:transform 0.15s ease,width 0.3s,height 0.3s;
}

/* NOISE OVERLAY */
body::before{
  content:'';position:fixed;inset:0;
  background-image:url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.75' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.04'/%3E%3C/svg%3E");
  pointer-events:none;z-index:0;opacity:0.4;
}

/* NAV */
nav{
  position:fixed;top:0;left:0;right:0;z-index:100;
  display:flex;align-items:center;justify-content:space-between;
  padding:1.2rem 4rem;
  background:rgba(10,2,5,0.8);
  backdrop-filter:blur(20px);
  border-bottom:1px solid var(--border2);
}
.logo{
  font-family:'Outfit',sans-serif;
  font-weight:800;font-size:1.1rem;
  color:var(--text);text-decoration:none;
  letter-spacing:-0.02em;
}
.logo span{color:var(--red2);}
.nav-links{display:flex;gap:0.5rem;list-style:none;
  background:rgba(192,21,42,0.08);
  border:1px solid var(--border);
  border-radius:40px;padding:0.3rem;
}
.nav-links a{
  font-size:0.8rem;font-weight:500;
  color:var(--muted);text-decoration:none;
  padding:0.4rem 1rem;border-radius:30px;
  transition:all 0.2s;display:flex;align-items:center;gap:0.4rem;
}
.nav-links a:hover,.nav-links a.active{
  color:var(--text);background:var(--red);
}
.nav-status{
  display:flex;align-items:center;gap:0.5rem;
  font-size:0.75rem;color:var(--muted);
}
.status-dot{
  width:7px;height:7px;border-radius:50%;
  background:#22c55e;
  box-shadow:0 0 6px #22c55e;
  animation:pulse-green 2s infinite;
}
@keyframes pulse-green{0%,100%{opacity:1}50%{opacity:0.4}}

/* HERO */
.hero{
  min-height:100vh;
  display:flex;align-items:center;
  padding:7rem 4rem 4rem;
  position:relative;overflow:hidden;
}
.hero-bg-glow{
  position:absolute;top:-100px;right:-50px;
  width:600px;height:600px;
  background:radial-gradient(circle,rgba(192,21,42,0.18) 0%,transparent 65%);
  pointer-events:none;
}
.hero-bg-glow2{
  position:absolute;bottom:-200px;left:-100px;
  width:500px;height:500px;
  background:radial-gradient(circle,rgba(192,21,42,0.08) 0%,transparent 65%);
  pointer-events:none;
}
.hero-grid{
  display:grid;grid-template-columns:1fr 1fr;
  gap:4rem;align-items:center;
  width:100%;max-width:1100px;margin:0 auto;
  position:relative;z-index:1;
}
.hero-tag{
  display:inline-flex;align-items:center;gap:0.5rem;
  font-size:0.72rem;font-weight:500;letter-spacing:0.12em;
  text-transform:uppercase;
  color:#22c55e;
  background:rgba(34,197,94,0.08);
  border:1px solid rgba(34,197,94,0.2);
  padding:0.35rem 1rem;border-radius:30px;
  margin-bottom:1.5rem;
  animation:fadeUp 0.6s ease both;
}
.hero-tag::before{content:'●';font-size:0.45rem;}
.hero h1{
  font-family:'Outfit',sans-serif;
  font-size:clamp(2.4rem,5vw,4rem);
  font-weight:900;line-height:1.05;
  letter-spacing:-0.03em;
  margin-bottom:0.5rem;
  animation:fadeUp 0.6s 0.1s ease both;
}
.hero h1 .name{
  color:var(--red2);
  text-shadow:0 0 30px var(--red-glow),0 0 60px rgba(192,21,42,0.2);
}
.hero-role{
  font-family:'Outfit',sans-serif;
  font-size:1.3rem;font-weight:600;
  color:var(--muted);margin-bottom:1.5rem;
  animation:fadeUp 0.6s 0.15s ease both;
}
.hero p{
  font-size:0.9rem;color:var(--muted);
  line-height:1.8;max-width:480px;
  margin-bottom:2rem;
  animation:fadeUp 0.6s 0.2s ease both;
}
.hero-meta{
  display:flex;gap:1.5rem;margin-bottom:2rem;
  animation:fadeUp 0.6s 0.25s ease both;
}
.hero-meta span{
  font-size:0.75rem;color:var(--muted);
  display:flex;align-items:center;gap:0.4rem;
}
.hero-meta span::before{font-size:0.8rem;}
.meta-loc::before{content:'📍';}
.meta-avail::before{content:'⚡';}
.hero-btns{
  display:flex;gap:1rem;flex-wrap:wrap;
  animation:fadeUp 0.6s 0.3s ease both;
}
.btn-hire{
  display:inline-flex;align-items:center;gap:0.5rem;
  background:var(--red);color:#fff;
  padding:0.8rem 1.8rem;border-radius:8px;
  font-weight:600;font-size:0.875rem;
  text-decoration:none;
  border:1px solid var(--red2);
  transition:all 0.25s;
  box-shadow:0 0 20px var(--red-glow);
}
.btn-hire:hover{
  background:var(--red2);
  box-shadow:0 0 35px var(--red-glow),0 0 60px rgba(192,21,42,0.2);
  transform:translateY(-2px);
}
.btn-work{
  display:inline-flex;align-items:center;gap:0.5rem;
  background:transparent;color:var(--text);
  padding:0.8rem 1.8rem;border-radius:8px;
  font-weight:500;font-size:0.875rem;
  text-decoration:none;
  border:1px solid var(--border);
  transition:all 0.25s;
}
.btn-work:hover{border-color:var(--red);color:var(--red2);}
.hero-socials{
  display:flex;gap:1rem;margin-top:2rem;
  animation:fadeUp 0.6s 0.35s ease both;
}
.social-link{
  width:36px;height:36px;border-radius:8px;
  border:1px solid var(--border);
  display:flex;align-items:center;justify-content:center;
  font-size:0.85rem;text-decoration:none;
  color:var(--muted);transition:all 0.2s;
}
.social-link:hover{
  border-color:var(--red);color:var(--red2);
  box-shadow:0 0 12px var(--red-glow);
}

/* HERO RIGHT — ANIME CARD */
.hero-right{
  display:flex;justify-content:center;align-items:center;
  animation:fadeUp 0.8s 0.2s ease both;
  position:relative;
}
.anime-card{
  width:320px;
  background:rgba(192,21,42,0.06);
  border:1px solid var(--border);
  border-radius:16px;
  padding:1.5rem;
  position:relative;
  overflow:hidden;
}
.anime-card::before{
  content:'';position:absolute;inset:0;
  background:radial-gradient(ellipse at 50% 0%,rgba(192,21,42,0.15) 0%,transparent 60%);
  pointer-events:none;
}
.card-top-bar{
  display:flex;align-items:center;justify-content:space-between;
  margin-bottom:1.25rem;
  font-size:0.65rem;letter-spacing:0.1em;
  text-transform:uppercase;color:var(--muted);
}
.card-top-bar .online{
  display:flex;align-items:center;gap:0.4rem;
  color:#22c55e;
}
.card-top-bar .online::before{
  content:'';width:6px;height:6px;
  border-radius:50%;background:#22c55e;
  box-shadow:0 0 6px #22c55e;
  animation:pulse-green 2s infinite;
}
.anime-avatar{
  width:180px;height:200px;
  margin:0 auto 1.25rem;
  background:linear-gradient(160deg,rgba(192,21,42,0.15),rgba(192,21,42,0.05));
  border-radius:12px;
  border:1px solid var(--border);
  display:flex;align-items:center;justify-content:center;
  font-size:5rem;
  position:relative;overflow:hidden;
}
.anime-avatar::after{
  content:'';position:absolute;
  bottom:0;left:0;right:0;height:40%;
  background:linear-gradient(to top,rgba(10,2,5,0.8),transparent);
}
.card-name{
  font-family:'Outfit',sans-serif;
  font-size:1.3rem;font-weight:800;
  text-align:center;margin-bottom:0.25rem;
  color:var(--text);
}
.card-role{
  text-align:center;font-size:0.75rem;
  color:var(--red2);margin-bottom:1rem;
  letter-spacing:0.05em;
}
.card-stats{
  display:grid;grid-template-columns:1fr 1fr;
  gap:0.5rem;
}
.stat-box{
  background:rgba(192,21,42,0.08);
  border:1px solid var(--border2);
  border-radius:8px;padding:0.6rem;
  text-align:center;
}
.stat-box .num{
  font-family:'Outfit',sans-serif;
  font-size:1.1rem;font-weight:800;
  color:var(--red2);
}
.stat-box .lbl{font-size:0.65rem;color:var(--muted);}

/* SECTION COMMON */
section{padding:5rem 4rem;position:relative;z-index:1;}
.sec-header{margin-bottom:3rem;}
.sec-tag{
  font-size:0.7rem;font-weight:600;letter-spacing:0.15em;
  text-transform:uppercase;color:var(--red2);
  margin-bottom:0.5rem;
}
.sec-title{
  font-family:'Outfit',sans-serif;
  font-size:clamp(1.6rem,3vw,2.4rem);
  font-weight:800;line-height:1.1;
  letter-spacing:-0.02em;
}
.sec-sub{color:var(--muted);font-size:0.9rem;margin-top:0.5rem;line-height:1.7;}

/* SERVICES */
#services{background:var(--bg2);}
.services-grid{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(260px,1fr));
  gap:1rem;
}
.srv-card{
  background:var(--card);
  border:1px solid var(--border2);
  border-radius:12px;padding:1.75rem;
  transition:all 0.3s;
  position:relative;overflow:hidden;
}
.srv-card::after{
  content:'';position:absolute;
  top:0;left:0;right:0;height:1px;
  background:linear-gradient(90deg,transparent,var(--red),transparent);
  opacity:0;transition:opacity 0.3s;
}
.srv-card:hover{
  border-color:var(--border);
  transform:translateY(-3px);
  background:rgba(192,21,42,0.05);
  box-shadow:0 8px 30px rgba(192,21,42,0.1);
}
.srv-card:hover::after{opacity:1;}
.srv-icon{
  width:44px;height:44px;border-radius:10px;
  background:var(--red-soft);
  border:1px solid var(--border);
  display:flex;align-items:center;justify-content:center;
  font-size:1.2rem;margin-bottom:1.1rem;
}
.srv-card h3{
  font-family:'Outfit',sans-serif;
  font-size:1rem;font-weight:700;margin-bottom:0.5rem;
}
.srv-card p{font-size:0.8rem;color:var(--muted);line-height:1.65;margin-bottom:1rem;}
.srv-price{
  font-size:0.75rem;font-weight:600;
  color:var(--red2);
  background:var(--red-soft);
  border:1px solid var(--border);
  padding:0.25rem 0.75rem;border-radius:20px;
  display:inline-block;
}

/* PROJECTS */
.proj-grid{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(300px,1fr));
  gap:1rem;
}
.proj-card{
  border-radius:12px;overflow:hidden;
  border:1px solid var(--border2);
  background:var(--bg3);
  transition:all 0.3s;
}
.proj-card:hover{
  border-color:var(--border);
  transform:translateY(-3px);
  box-shadow:0 10px 40px rgba(192,21,42,0.12);
}
.proj-thumb{
  height:190px;
  display:flex;align-items:center;justify-content:center;
  font-size:2.5rem;
  position:relative;overflow:hidden;
}
.pt1{background:linear-gradient(135deg,#1a0209,#3d0515);}
.pt2{background:linear-gradient(135deg,#0d1a08,#1a3d10);}
.pt3{background:linear-gradient(135deg,#0d0d1a,#15103d);}
.proj-thumb::after{
  content:'';position:absolute;inset:0;
  background:linear-gradient(to top,var(--bg3) 0%,transparent 50%);
}
.proj-info{padding:1.1rem;}
.proj-info h3{
  font-family:'Outfit',sans-serif;
  font-size:0.95rem;font-weight:700;margin-bottom:0.3rem;
}
.proj-info p{font-size:0.78rem;color:var(--muted);margin-bottom:0.75rem;line-height:1.6;}
.proj-tags{display:flex;gap:0.3rem;flex-wrap:wrap;margin-bottom:0.75rem;}
.ptag{
  font-size:0.65rem;padding:0.2rem 0.6rem;
  background:var(--red-soft);color:var(--red2);
  border:1px solid var(--border);border-radius:4px;
}
.proj-links{display:flex;gap:0.5rem;}
.proj-btn{
  font-size:0.72rem;font-weight:500;
  padding:0.3rem 0.8rem;border-radius:6px;
  text-decoration:none;transition:all 0.2s;
  border:1px solid var(--border);color:var(--muted);
  display:inline-flex;align-items:center;gap:0.3rem;
}
.proj-btn:hover{border-color:var(--red);color:var(--red2);}
.proj-btn.live{
  background:var(--red-soft);color:var(--red2);
}

/* ABOUT */
#about{background:var(--bg2);}
.about-grid{
  display:grid;grid-template-columns:1fr 1.5fr;
  gap:4rem;align-items:center;
}
.about-card{
  background:var(--card);
  border:1px solid var(--border);
  border-radius:16px;padding:2rem;
  text-align:center;
}
.about-avatar{
  width:120px;height:120px;
  border-radius:50%;
  background:linear-gradient(135deg,var(--red-soft),rgba(192,21,42,0.15));
  border:2px solid var(--border);
  display:flex;align-items:center;justify-content:center;
  font-size:3rem;margin:0 auto 1rem;
  box-shadow:0 0 30px var(--red-glow);
}
.about-card h3{
  font-family:'Outfit',sans-serif;
  font-size:1.3rem;font-weight:800;margin-bottom:0.25rem;
}
.about-card .role{font-size:0.8rem;color:var(--red2);margin-bottom:1.25rem;}
.about-skills{display:flex;flex-wrap:wrap;gap:0.4rem;justify-content:center;}
.skill-tag{
  font-size:0.7rem;padding:0.25rem 0.7rem;
  background:var(--red-soft);color:var(--red2);
  border:1px solid var(--border);border-radius:4px;
}
.about-text h2{
  font-family:'Outfit',sans-serif;
  font-size:1.8rem;font-weight:800;
  margin-bottom:1rem;line-height:1.2;
}
.about-text p{
  font-size:0.875rem;color:var(--muted);
  line-height:1.8;margin-bottom:1rem;
}
.about-list{list-style:none;margin-bottom:1.5rem;}
.about-list li{
  font-size:0.85rem;color:var(--muted);
  padding:0.5rem 0;
  border-bottom:1px solid var(--border2);
  display:flex;align-items:center;gap:0.75rem;
}
.about-list li::before{
  content:'→';color:var(--red2);font-weight:700;
}

/* CONTACT */
#contact{
  background:var(--bg);
  text-align:center;
}
.contact-inner{max-width:600px;margin:0 auto;}
.contact-glow{
  font-family:'Outfit',sans-serif;
  font-size:clamp(2rem,5vw,3.5rem);
  font-weight:900;margin-bottom:1rem;
  color:var(--text);
}
.contact-glow span{
  color:var(--red2);
  text-shadow:0 0 30px var(--red-glow);
}
.contact-sub{color:var(--muted);font-size:0.9rem;margin-bottom:2.5rem;line-height:1.7;}
.contact-form{
  background:var(--card);
  border:1px solid var(--border);
  border-radius:16px;padding:2rem;
  text-align:left;
}
.form-row{display:grid;grid-template-columns:1fr 1fr;gap:1rem;margin-bottom:1rem;}
.fg{display:flex;flex-direction:column;gap:0.35rem;margin-bottom:1rem;}
.fg label{font-size:0.72rem;font-weight:500;color:var(--muted);letter-spacing:0.05em;text-transform:uppercase;}
.fg input,.fg textarea,.fg select{
  background:rgba(192,21,42,0.04);
  border:1px solid var(--border);
  border-radius:8px;padding:0.7rem 1rem;
  color:var(--text);font-family:inherit;font-size:0.875rem;
  outline:none;transition:border-color 0.2s;
}
.fg input:focus,.fg textarea:focus{border-color:var(--red);}
.fg textarea{resize:vertical;min-height:110px;}
.fg select option{background:#150509;}
.btn-send{
  width:100%;background:var(--red);color:#fff;
  border:none;padding:0.9rem;border-radius:8px;
  font-size:0.95rem;font-weight:600;
  cursor:pointer;transition:all 0.25s;
  font-family:inherit;
  box-shadow:0 0 20px var(--red-glow);
  letter-spacing:0.02em;
}
.btn-send:hover{
  background:var(--red2);
  box-shadow:0 0 35px var(--red-glow);
  transform:translateY(-2px);
}

/* FOOTER */
footer{
  background:var(--bg2);
  border-top:1px solid var(--border2);
  padding:2rem 4rem;
  display:flex;align-items:center;justify-content:space-between;
  flex-wrap:wrap;gap:1rem;
}
footer p{font-size:0.75rem;color:var(--muted);}
.footer-logo{
  font-family:'Outfit',sans-serif;
  font-weight:800;font-size:0.95rem;
  color:var(--text);
}
.footer-logo span{color:var(--red2);}

/* ANIMATIONS */
@keyframes fadeUp{
  from{opacity:0;transform:translateY(24px)}
  to{opacity:1;transform:translateY(0)}
}
@keyframes float{
  0%,100%{transform:translateY(0)}
  50%{transform:translateY(-10px)}
}
.float{animation:float 4s ease-in-out infinite;}
.fade-in{opacity:0;transform:translateY(20px);transition:opacity 0.7s ease,transform 0.7s ease;}
.fade-in.visible{opacity:1;transform:translateY(0);}

/* SCROLLBAR */
::-webkit-scrollbar{width:4px;}
::-webkit-scrollbar-track{background:var(--bg);}
::-webkit-scrollbar-thumb{background:var(--red);border-radius:2px;}

@media(max-width:900px){
  nav{padding:1rem 1.5rem;}
  .nav-links{display:none;}
  section{padding:4rem 1.5rem;}
  .hero{padding:6rem 1.5rem 3rem;}
  .hero-grid{grid-template-columns:1fr;gap:2rem;}
  .hero-right{display:none;}
  .about-grid{grid-template-columns:1fr;}
  .form-row{grid-template-columns:1fr;}
  footer{padding:2rem 1.5rem;flex-direction:column;text-align:center;}
}
</style>
</head>
<body>

<div class="cursor" id="cursor"></div>
<div class="cursor-ring" id="cursorRing"></div>

<!-- NAV -->
<nav>
  <a href="#" class="logo">craftedbysahil<span>.</span></a>
  <ul class="nav-links">
    <li><a href="#" class="active">🏠 Home</a></li>
    <li><a href="#about">👤 About</a></li>
    <li><a href="#projects">💼 Projects</a></li>
    <li><a href="#services">⚡ Services</a></li>
    <li><a href="#contact">✉ Contact</a></li>
  </ul>
  <div class="nav-status">
    <span class="status-dot"></span>
    Available for work
  </div>
</nav>

<!-- HERO -->
<section class="hero" id="home">
  <div class="hero-bg-glow"></div>
  <div class="hero-bg-glow2"></div>
  <div class="hero-grid">
    <div class="hero-left">
      <div class="hero-tag">Available for freelance work</div>
      <h1>Hi, I'm <span class="name">Sahil</span><br>More</h1>
      <div class="hero-role">Web Designer & Developer</div>
      <p>I create beautiful, fast, and modern websites for small businesses in the US, UK, and Australia. I turn your ideas into digital experiences that actually bring customers.</p>
      <div class="hero-meta">
        <span class="meta-loc">Based in India</span>
        <span class="meta-avail">Available Now</span>
      </div>
      <div class="hero-btns">
        <a href="#contact" class="btn-hire">→ Hire Me</a>
        <a href="#projects" class="btn-work">View Work</a>
      </div>
      <div class="hero-socials">
        <a href="#" class="social-link" title="GitHub">⌨</a>
        <a href="#" class="social-link" title="LinkedIn">in</a>
        <a href="#" class="social-link" title="Fiverr">f</a>
        <a href="#" class="social-link" title="Instagram">◎</a>
      </div>
    </div>
    <div class="hero-right">
      <div class="anime-card float">
        <div class="card-top-bar">
          <span>craftedbysahil.dev</span>
          <span class="online">Online</span>
        </div>
        <div class="anime-avatar">🧑‍💻</div>
        <div class="card-name">Sahil More</div>
        <div class="card-role">Web Designer & Developer</div>
        <div class="card-stats">
          <div class="stat-box">
            <div class="num">15+</div>
            <div class="lbl">Projects</div>
          </div>
          <div class="stat-box">
            <div class="num">5★</div>
            <div class="lbl">Rating</div>
          </div>
          <div class="stat-box">
            <div class="num">48h</div>
            <div class="lbl">Delivery</div>
          </div>
          <div class="stat-box">
            <div class="num">100%</div>
            <div class="lbl">Satisfaction</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- SERVICES -->
<section id="services">
  <div class="sec-header fade-in">
    <div class="sec-tag">// what i offer</div>
    <h2 class="sec-title">Services</h2>
    <p class="sec-sub">Everything your business needs to get online and grow.</p>
  </div>
  <div class="services-grid">
    <div class="srv-card fade-in">
      <div class="srv-icon">🌐</div>
      <h3>Business Website</h3>
      <p>Clean, fast, mobile-friendly websites for restaurants, clinics, and local businesses built to convert visitors into customers.</p>
      <span class="srv-price">From $299</span>
    </div>
    <div class="srv-card fade-in">
      <div class="srv-icon">🛒</div>
      <h3>E-commerce Store</h3>
      <p>Full online store with product pages, cart, and payment integration. Start selling online within days.</p>
      <span class="srv-price">From $499</span>
    </div>
    <div class="srv-card fade-in">
      <div class="srv-icon">📱</div>
      <h3>Landing Page</h3>
      <p>High-converting single pages for product launches, lead generation, and marketing campaigns.</p>
      <span class="srv-price">From $149</span>
    </div>
    <div class="srv-card fade-in">
      <div class="srv-icon">🎨</div>
      <h3>Website Redesign</h3>
      <p>Transform your outdated website into a modern, fast-loading site that impresses visitors instantly.</p>
      <span class="srv-price">From $249</span>
    </div>
    <div class="srv-card fade-in">
      <div class="srv-icon">⚡</div>
      <h3>Speed Optimization</h3>
      <p>Make your website load faster, rank higher on Google, and stop losing customers to slow speed.</p>
      <span class="srv-price">From $99</span>
    </div>
    <div class="srv-card fade-in">
      <div class="srv-icon">🔄</div>
      <h3>Monthly Maintenance</h3>
      <p>Regular updates, backups, security, and content changes so your site always runs perfectly.</p>
      <span class="srv-price">From $79/mo</span>
    </div>
  </div>
</section>

<!-- PROJECTS -->
<section id="projects">
  <div class="sec-header fade-in">
    <div class="sec-tag">// my work</div>
    <h2 class="sec-title">Recent Projects</h2>
    <p class="sec-sub">Websites I've built for businesses in the US, UK, and Australia.</p>
  </div>
  <div class="proj-grid">
    <div class="proj-card fade-in">
      <div class="proj-thumb pt1">🍕</div>
      <div class="proj-info">
        <h3>Marco's Italian Kitchen</h3>
        <p>Restaurant website with online menu, reservations, and Google Maps — New York, USA</p>
        <div class="proj-tags">
          <span class="ptag">WordPress</span>
          <span class="ptag">WooCommerce</span>
          <span class="ptag">SEO</span>
        </div>
        <div class="proj-links">
          <a href="#" class="proj-btn">GitHub</a>
          <a href="#" class="proj-btn live">Live Demo →</a>
        </div>
      </div>
    </div>
    <div class="proj-card fade-in">
      <div class="proj-thumb pt2">🦷</div>
      <div class="proj-info">
        <h3>Bright Smile Dental</h3>
        <p>Dental clinic site with online booking and patient portal — London, UK</p>
        <div class="proj-tags">
          <span class="ptag">HTML/CSS</span>
          <span class="ptag">JavaScript</span>
          <span class="ptag">Booking</span>
        </div>
        <div class="proj-links">
          <a href="#" class="proj-btn">GitHub</a>
          <a href="#" class="proj-btn live">Live Demo →</a>
        </div>
      </div>
    </div>
    <div class="proj-card fade-in">
      <div class="proj-thumb pt3">🏠</div>
      <div class="proj-info">
        <h3>Sunrise Realty Group</h3>
        <p>Real estate site with property listings and search filters — Sydney, Australia</p>
        <div class="proj-tags">
          <span class="ptag">WordPress</span>
          <span class="ptag">Listings</span>
          <span class="ptag">Maps API</span>
        </div>
        <div class="proj-links">
          <a href="#" class="proj-btn">GitHub</a>
          <a href="#" class="proj-btn live">Live Demo →</a>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ABOUT -->
<section id="about">
  <div class="about-grid">
    <div class="about-card fade-in">
      <div class="about-avatar">🧑‍🎨</div>
      <h3>Sahil More</h3>
      <div class="role">Web Designer & Developer</div>
      <div class="about-skills">
        <span class="skill-tag">WordPress</span>
        <span class="skill-tag">HTML/CSS</span>
        <span class="skill-tag">JavaScript</span>
        <span class="skill-tag">Figma</span>
        <span class="skill-tag">Elementor</span>
        <span class="skill-tag">WooCommerce</span>
        <span class="skill-tag">SEO</span>
        <span class="skill-tag">UI Design</span>
      </div>
    </div>
    <div class="about-text fade-in">
      <div class="sec-tag">// about me</div>
      <h2>Tech student.<br>Designer at heart.</h2>
      <p>Hey! I'm Sahil — a tech student and web designer who turns ideas into clean, modern websites. I started coding because I love creating things that look great and actually work.</p>
      <p>I also sketch — a lot. That design eye shows in every website I build. Clean layouts, thoughtful spacing, pixel-perfect details. Now I help businesses in the US, UK, and Australia get online with websites that bring real results.</p>
      <ul class="about-list">
        <li>Fast delivery — always on time</li>
        <li>Clear communication throughout the project</li>
        <li>Revisions until you're 100% happy</li>
        <li>Post-launch support included</li>
      </ul>
      <a href="#contact" class="btn-hire" style="display:inline-flex;">Let's Work Together →</a>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="contact-inner">
    <div class="sec-tag fade-in">// get in touch</div>
    <h2 class="contact-glow fade-in">Let's build something <span>great</span></h2>
    <p class="contact-sub fade-in">Tell me about your project and I'll reply within 24 hours with a free quote.</p>
    <div class="contact-form fade-in">
      <div class="form-row">
        <div class="fg">
          <label>Your Name</label>
          <input type="text" placeholder="John Smith">
        </div>
        <div class="fg">
          <label>Email</label>
          <input type="email" placeholder="john@business.com">
        </div>
      </div>
      <div class="form-row">
        <div class="fg">
          <label>Country</label>
          <select>
            <option>United States</option>
            <option>United Kingdom</option>
            <option>Australia</option>
            <option>Canada</option>
            <option>Other</option>
          </select>
        </div>
        <div class="fg">
          <label>Budget</label>
          <select>
            <option>$150 – $300</option>
            <option>$300 – $600</option>
            <option>$600 – $1,000</option>
            <option>$1,000+</option>
          </select>
        </div>
      </div>
      <div class="fg">
        <label>Tell me about your project</label>
        <textarea placeholder="What type of website do you need? What does your business do?"></textarea>
      </div>
      <button class="btn-send">Send Message — Get Free Quote →</button>
    </div>
  </div>
</section>

<footer>
  <div class="footer-logo">craftedbysahil<span>.</span></div>
  <p>© 2025 Sahil More — Web Designer & Developer</p>
  <p style="font-size:0.7rem;">Built with ❤ & lots of coffee</p>
</footer>

<script>
const cursor = document.getElementById('cursor');
const ring = document.getElementById('cursorRing');
let mx=0,my=0,rx=0,ry=0;
document.addEventListener('mousemove',e=>{
  mx=e.clientX;my=e.clientY;
  cursor.style.left=mx+'px';cursor.style.top=my+'px';
});
function animRing(){
  rx+=(mx-rx)*0.12;ry+=(my-ry)*0.12;
  ring.style.left=rx+'px';ring.style.top=ry+'px';
  requestAnimationFrame(animRing);
}
animRing();
document.querySelectorAll('a,button').forEach(el=>{
  el.addEventListener('mouseenter',()=>{
    cursor.style.width='6px';cursor.style.height='6px';
    ring.style.width='44px';ring.style.height='44px';
    ring.style.borderColor='rgba(192,21,42,0.8)';
  });
  el.addEventListener('mouseleave',()=>{
    cursor.style.width='10px';cursor.style.height='10px';
    ring.style.width='32px';ring.style.height='32px';
    ring.style.borderColor='rgba(192,21,42,0.5)';
  });
});
const obs=new IntersectionObserver(entries=>{
  entries.forEach((e,i)=>{
    if(e.isIntersecting) setTimeout(()=>e.target.classList.add('visible'),i*80);
  });
},{threshold:0.1});
document.querySelectorAll('.fade-in').forEach(el=>obs.observe(el));
document.querySelectorAll('.nav-links a').forEach(a=>{
  a.addEventListener('click',function(){
    document.querySelectorAll('.nav-links a').forEach(x=>x.classList.remove('active'));
    this.classList.add('active');
  });
});
</script>
</body>
</html>
