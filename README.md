<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Totot Kitfo — Crafted Tradition. Pure Flavor.</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Fraunces:opsz,wght@9..144,300;9..144,400;9..144,500;9..144,600&family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<style>
  :root{
    --obsidian:#0A0A0B;
    --charcoal:#121215;
    --charcoal-2:#17171b;
    --off-white:#F5F5F7;
    --off-white-dim:#B8B8BD;
    --gold:#C5A059;
    --gold-bright:#DCB86E;
    --gold-dim:#7A6438;
    --line:rgba(197,160,89,0.16);
    --line-soft:rgba(245,245,247,0.08);
  }

  *{margin:0;padding:0;box-sizing:border-box;}
  html{scroll-behavior:smooth;}

  body{
    background:var(--obsidian);
    color:var(--off-white);
    font-family:'Inter',sans-serif;
    font-weight:400;
    overflow-x:hidden;
    -webkit-font-smoothing:antialiased;
  }

  ::selection{background:var(--gold-dim);color:var(--off-white);}

  h1,h2,h3,.display{
    font-family:'Fraunces',serif;
    font-weight:500;
    letter-spacing:-0.01em;
    line-height:1.05;
  }

  a{color:inherit;text-decoration:none;}
  button{font-family:inherit;cursor:pointer;border:none;background:none;color:inherit;}

  .eyebrow{
    font-size:12px;
    letter-spacing:0.22em;
    text-transform:uppercase;
    color:var(--gold);
    font-weight:600;
    display:flex;
    align-items:center;
    gap:10px;
  }
  .eyebrow::before{
    content:"";
    width:18px;
    height:1px;
    background:var(--gold);
    display:inline-block;
  }

  .container{
    max-width:1200px;
    margin:0 auto;
    padding:0 32px;
  }

  :focus-visible{
    outline:1.5px solid var(--gold);
    outline-offset:4px;
  }

  @media (prefers-reduced-motion: reduce){
    *{animation-duration:0.001ms !important; animation-iteration-count:1 !important; transition-duration:0.001ms !important; scroll-behavior:auto !important;}
  }

  /* ---------- Gold thread signature (scroll-linked lineage line) ---------- */
  .thread-wrap{
    position:fixed;
    top:0; left:0;
    width:100%; height:100%;
    pointer-events:none;
    z-index:1;
  }
  #threadSvg{
    position:absolute;
    left:50%;
    transform:translateX(-50%);
    top:0;
    height:100%;
    width:2px;
    overflow:visible;
  }
  #threadPath{
    fill:none;
    stroke:var(--gold);
    stroke-width:1;
    stroke-dasharray:1;
    stroke-dashoffset:1;
    opacity:0.55;
    vector-effect:non-scaling-stroke;
  }

  /* ---------- Nav ---------- */
  header{
    position:fixed;
    top:0; left:0; right:0;
    z-index:100;
    background:rgba(10,10,11,0.55);
    backdrop-filter:blur(18px) saturate(140%);
    -webkit-backdrop-filter:blur(18px) saturate(140%);
    border-bottom:1px solid transparent;
    transition:border-color 0.4s ease, background 0.4s ease;
  }
  header.scrolled{
    border-bottom:1px solid var(--line);
    background:rgba(10,10,11,0.78);
  }
  nav{
    max-width:1200px;
    margin:0 auto;
    padding:18px 32px;
    display:flex;
    align-items:center;
    justify-content:space-between;
  }
  .logo{
    font-family:'Fraunces',serif;
    font-size:20px;
    font-weight:600;
    letter-spacing:0.14em;
    color:var(--off-white);
  }
  .logo span{color:var(--gold);}
  .nav-links{
    display:flex;
    gap:40px;
    list-style:none;
  }
  .nav-links a{
    font-size:14px;
    font-weight:500;
    color:var(--off-white-dim);
    position:relative;
    padding-bottom:4px;
    transition:color 0.3s ease;
  }
  .nav-links a::after{
    content:"";
    position:absolute;
    left:0; bottom:0;
    width:0; height:1px;
    background:var(--gold);
    transition:width 0.35s ease;
  }
  .nav-links a:hover{color:var(--off-white);}
  .nav-links a:hover::after{width:100%;}

  .btn-pill{
    display:inline-flex;
    align-items:center;
    justify-content:center;
    padding:12px 26px;
    border-radius:100px;
    font-size:13px;
    font-weight:600;
    letter-spacing:0.02em;
    transition:transform 0.35s cubic-bezier(.2,.8,.2,1), box-shadow 0.35s ease, background 0.35s ease, color 0.35s ease;
  }
  .btn-gold{
    background:var(--gold);
    color:var(--obsidian);
  }
  .btn-gold:hover{
    transform:translateY(-2px);
    box-shadow:0 12px 30px -8px rgba(197,160,89,0.55);
    background:var(--gold-bright);
  }
  .btn-outline{
    border:1px solid var(--line-soft);
    color:var(--off-white);
  }
  .btn-outline:hover{
    border-color:var(--gold);
    color:var(--gold-bright);
    transform:translateY(-2px);
  }
  .nav-cta{padding:10px 22px;font-size:13px;}

  .nav-toggle{display:none;}

  /* ---------- Hero ---------- */
  .hero{
    position:relative;
    min-height:100vh;
    display:flex;
    flex-direction:column;
    align-items:center;
    justify-content:center;
    text-align:center;
    padding:160px 32px 100px;
    z-index:2;
    background:
      radial-gradient(ellipse 60% 45% at 50% 18%, rgba(197,160,89,0.10), transparent 70%),
      radial-gradient(ellipse 80% 60% at 50% 100%, rgba(197,160,89,0.05), transparent 70%),
      var(--obsidian);
    overflow:hidden;
  }
  .hero::before{
    content:"";
    position:absolute;
    inset:0;
    background-image:
      repeating-linear-gradient(115deg, rgba(245,245,247,0.02) 0px, rgba(245,245,247,0.02) 1px, transparent 1px, transparent 90px);
    opacity:0.5;
    pointer-events:none;
  }
  .hero-eyebrow{margin-bottom:28px; opacity:0; animation:riseIn 0.9s 0.15s ease forwards;}
  .hero h1{
    font-size:clamp(44px, 8vw, 108px);
    max-width:1150px;
    color:var(--off-white);
    opacity:0;
    animation:riseIn 1s 0.3s ease forwards;
  }
  .hero h1 em{
    font-style:normal;
    background:linear-gradient(100deg, var(--gold-dim), var(--gold-bright) 55%, var(--gold));
    -webkit-background-clip:text;
    background-clip:text;
    color:transparent;
  }
  .hero p{
    margin-top:30px;
    max-width:560px;
    font-size:18px;
    line-height:1.65;
    color:var(--off-white-dim);
    font-weight:300;
    opacity:0;
    animation:riseIn 1s 0.5s ease forwards;
  }
  .hero-ctas{
    margin-top:48px;
    display:flex;
    gap:16px;
    opacity:0;
    animation:riseIn 1s 0.7s ease forwards;
  }
  .btn-lg{padding:16px 34px;font-size:14px;}

  @keyframes riseIn{
    from{opacity:0; transform:translateY(18px);}
    to{opacity:1; transform:translateY(0);}
  }

  .scroll-cue{
    position:absolute;
    bottom:36px;
    left:50%;
    transform:translateX(-50%);
    width:1px;
    height:52px;
    background:linear-gradient(to bottom, transparent, var(--gold));
    opacity:0.6;
  }
  .scroll-cue::after{
    content:"";
    position:absolute;
    top:0; left:-2px;
    width:5px; height:5px;
    border-radius:50%;
    background:var(--gold-bright);
    animation:dropCue 2.2s ease-in-out infinite;
  }
  @keyframes dropCue{
    0%{top:0; opacity:1;}
    80%{opacity:0.2;}
    100%{top:100%; opacity:0;}
  }

  /* ---------- Generic section ---------- */
  section{
    position:relative;
    z-index:2;
    padding:140px 0;
  }
  .section-head{
    text-align:center;
    max-width:640px;
    margin:0 auto 72px;
  }
  .section-head h2{
    margin-top:20px;
    font-size:clamp(32px, 4.5vw, 52px);
    color:var(--off-white);
  }
  .section-head p{
    margin-top:18px;
    color:var(--off-white-dim);
    font-size:16px;
    line-height:1.7;
    font-weight:300;
  }
  .center{text-align:center; margin-left:auto; margin-right:auto;}

  /* ---------- Bento grid ---------- */
  .bento{
    display:grid;
    grid-template-columns:1.15fr 1fr 1fr;
    grid-template-rows:auto auto;
    gap:20px;
  }
  .bento-card{
    background:linear-gradient(160deg, var(--charcoal-2), var(--charcoal));
    border:1px solid var(--line-soft);
    border-radius:24px;
    padding:44px 38px;
    position:relative;
    overflow:hidden;
    transition:transform 0.5s cubic-bezier(.2,.8,.2,1), border-color 0.5s ease, box-shadow 0.5s ease;
  }
  .bento-card::before{
    content:"";
    position:absolute;
    top:0; left:0; right:0;
    height:1px;
    background:linear-gradient(90deg, transparent, var(--gold), transparent);
    opacity:0;
    transition:opacity 0.5s ease;
  }
  .bento-card:hover{
    transform:translateY(-6px);
    border-color:var(--line);
    box-shadow:0 30px 60px -30px rgba(0,0,0,0.6);
  }
  .bento-card:hover::before{opacity:1;}
  .bento-a{grid-row:1 / 3;}
  .card-num{
    font-family:'Fraunces',serif;
    font-size:13px;
    color:var(--gold);
    letter-spacing:0.1em;
    opacity:0.85;
  }
  .bento-card h3{
    margin-top:22px;
    font-size:26px;
    color:var(--off-white);
    font-weight:500;
  }
  .bento-a h3{font-size:32px;}
  .bento-card p{
    margin-top:14px;
    color:var(--off-white-dim);
    font-size:15px;
    line-height:1.7;
    font-weight:300;
  }
  .glyph{
    width:44px; height:44px;
    border-radius:50%;
    border:1px solid var(--line);
    display:flex;
    align-items:center;
    justify-content:center;
    margin-bottom:24px;
    color:var(--gold);
  }
  .bento-a .plate{
    margin-top:32px;
    width:100%;
    height:200px;
    border-radius:16px;
    background:
      radial-gradient(circle at 35% 30%, rgba(197,160,89,0.35), transparent 55%),
      radial-gradient(circle at 70% 70%, rgba(197,160,89,0.15), transparent 60%),
      linear-gradient(160deg, #1c1a17, #0d0c0b);
    border:1px solid var(--line);
    position:relative;
  }

  /* ---------- Menu section ---------- */
  .menu-tabs{
    display:flex;
    justify-content:center;
    gap:8px;
    margin-bottom:56px;
    flex-wrap:wrap;
  }
  .tab-btn{
    padding:12px 24px;
    border-radius:100px;
    font-size:13px;
    font-weight:600;
    letter-spacing:0.03em;
    color:var(--off-white-dim);
    border:1px solid var(--line-soft);
    transition:all 0.35s ease;
  }
  .tab-btn:hover{color:var(--off-white); border-color:var(--line);}
  .tab-btn.active{
    background:var(--gold);
    color:var(--obsidian);
    border-color:var(--gold);
  }

  .menu-grid{
    display:grid;
    grid-template-columns:repeat(2, 1fr);
    gap:1px;
    background:var(--line-soft);
    border:1px solid var(--line-soft);
    border-radius:20px;
    overflow:hidden;
  }
  .menu-item{
    background:var(--charcoal);
    padding:34px 38px;
    display:flex;
    justify-content:space-between;
    align-items:flex-start;
    gap:24px;
    opacity:0;
    transform:translateY(10px);
    animation:riseIn 0.6s ease forwards;
    transition:background 0.35s ease;
  }
  .menu-item:hover{background:var(--charcoal-2);}
  .menu-item-name{
    font-family:'Fraunces',serif;
    font-size:19px;
    color:var(--off-white);
    font-weight:500;
  }
  .menu-item-desc{
    margin-top:8px;
    font-size:14px;
    color:var(--off-white-dim);
    font-weight:300;
    line-height:1.6;
    max-width:340px;
  }
  .menu-item-price{
    font-family:'Fraunces',serif;
    font-size:17px;
    color:var(--gold);
    white-space:nowrap;
    padding-top:2px;
  }

  /* ---------- Reservation ---------- */
  .reserve-wrap{
    max-width:640px;
    margin:0 auto;
    background:linear-gradient(160deg, var(--charcoal-2), var(--charcoal));
    border:1px solid var(--line);
    border-radius:28px;
    padding:56px 48px;
  }
  .field-row{
    display:grid;
    grid-template-columns:1fr 1fr;
    gap:22px;
    margin-bottom:22px;
  }
  .field{display:flex; flex-direction:column; gap:10px;}
  .field label{
    font-size:12px;
    letter-spacing:0.08em;
    text-transform:uppercase;
    color:var(--off-white-dim);
    font-weight:600;
  }
  .field input, .field select{
    background:rgba(245,245,247,0.03);
    border:1px solid var(--line-soft);
    border-radius:12px;
    padding:14px 16px;
    color:var(--off-white);
    font-size:15px;
    font-family:'Inter',sans-serif;
    transition:border-color 0.3s ease, background 0.3s ease;
    color-scheme:dark;
  }
  .field input::placeholder{color:rgba(245,245,247,0.3);}
  .field input:focus, .field select:focus{
    outline:none;
    border-color:var(--gold);
    background:rgba(245,245,247,0.05);
  }
  .submit-btn{
    width:100%;
    margin-top:12px;
    padding:17px;
    border-radius:12px;
    background:var(--gold);
    color:var(--obsidian);
    font-weight:600;
    font-size:14px;
    letter-spacing:0.03em;
    transition:transform 0.3s ease, background 0.3s ease, box-shadow 0.3s ease;
  }
  .submit-btn:hover{
    background:var(--gold-bright);
    transform:translateY(-2px);
    box-shadow:0 14px 30px -10px rgba(197,160,89,0.5);
  }
  .submit-btn:active{transform:translateY(0);}
  .form-success{
    display:none;
    margin-top:20px;
    padding:16px 18px;
    border-radius:12px;
    border:1px solid var(--line);
    background:rgba(197,160,89,0.08);
    color:var(--gold-bright);
    font-size:14px;
    text-align:center;
  }
  .form-success.show{display:block; animation:riseIn 0.5s ease forwards;}

  /* ---------- Location ---------- */
  .location-grid{
    display:grid;
    grid-template-columns:1fr 1fr;
    gap:20px;
  }
  .loc-card{
    border:1px solid var(--line-soft);
    border-radius:24px;
    padding:40px;
    background:var(--charcoal);
  }
  .loc-map{
    border-radius:24px;
    border:1px solid var(--line-soft);
    min-height:100%;
    position:relative;
    overflow:hidden;
    background:
      radial-gradient(circle at 50% 45%, rgba(197,160,89,0.18), transparent 60%),
      repeating-linear-gradient(0deg, rgba(245,245,247,0.035) 0 1px, transparent 1px 44px),
      repeating-linear-gradient(90deg, rgba(245,245,247,0.035) 0 1px, transparent 1px 44px),
      var(--charcoal-2);
    display:flex;
    align-items:center;
    justify-content:center;
    min-height:340px;
  }
  .pin{
    width:16px; height:16px;
    border-radius:50% 50% 50% 0;
    transform:rotate(-45deg);
    background:var(--gold);
    box-shadow:0 0 0 8px rgba(197,160,89,0.15), 0 0 30px rgba(197,160,89,0.5);
    position:relative;
  }
  .pin::after{
    content:"";
    position:absolute;
    top:3px; left:3px;
    width:6px; height:6px;
    border-radius:50%;
    background:var(--obsidian);
  }
  .loc-label{
    font-size:12px;
    text-transform:uppercase;
    letter-spacing:0.14em;
    color:var(--gold);
    font-weight:600;
    margin-bottom:14px;
  }
  .loc-card h3{font-size:20px; color:var(--off-white); font-weight:500; margin-bottom:16px; font-family:'Fraunces',serif;}
  .loc-card p{color:var(--off-white-dim); font-size:15px; line-height:1.9; font-weight:300;}
  .hours-row{display:flex; justify-content:space-between; padding:10px 0; border-bottom:1px solid var(--line-soft); font-size:14px;}
  .hours-row:last-child{border-bottom:none;}
  .hours-row span:first-child{color:var(--off-white-dim); font-weight:300;}
  .hours-row span:last-child{color:var(--off-white); font-weight:500;}

  /* ---------- Footer ---------- */
  footer{
    border-top:1px solid var(--line-soft);
    padding:48px 0;
    position:relative;
    z-index:2;
  }
  .footer-inner{
    display:flex;
    justify-content:space-between;
    align-items:center;
    flex-wrap:wrap;
    gap:16px;
  }
  .footer-inner .logo{font-size:16px;}
  footer p{color:var(--off-white-dim); font-size:13px; font-weight:300;}

  /* ---------- Reveal on scroll ---------- */
  .reveal{
    opacity:0;
    transform:translateY(28px);
    transition:opacity 0.8s cubic-bezier(.2,.8,.2,1), transform 0.8s cubic-bezier(.2,.8,.2,1);
  }
  .reveal.in{opacity:1; transform:translateY(0);}

  /* ---------- Responsive ---------- */
  @media (max-width: 860px){
    .nav-links{
      position:fixed;
      top:64px; left:0; right:0;
      flex-direction:column;
      background:rgba(10,10,11,0.97);
      backdrop-filter:blur(20px);
      padding:28px 32px;
      gap:22px;
      border-bottom:1px solid var(--line);
      transform:translateY(-130%);
      transition:transform 0.4s cubic-bezier(.2,.8,.2,1);
    }
    .nav-links.open{transform:translateY(0);}
    .nav-toggle{
      display:flex;
      flex-direction:column;
      gap:5px;
      width:22px;
    }
    .nav-toggle span{width:100%; height:1px; background:var(--off-white); transition:all 0.3s ease;}
    .nav-cta{display:none;}
    .bento{grid-template-columns:1fr;}
    .bento-a{grid-row:auto;}
    .menu-grid{grid-template-columns:1fr;}
    .field-row{grid-template-columns:1fr;}
    .location-grid{grid-template-columns:1fr;}
    section{padding:100px 0;}
    .hero{padding-top:140px;}
    .hero-ctas{flex-direction:column; width:100%; max-width:280px;}
  }
</style>
</head>
<body>

<div class="thread-wrap">
  <svg id="threadSvg" preserveAspectRatio="none" viewBox="0 0 2 1000">
    <path id="threadPath" d="M1,0 L1,1000"/>
  </svg>
</div>

<header id="siteHeader">
  <nav>
    <a href="#top" class="logo">TOTO<span>T</span></a>
    <ul class="nav-links" id="navLinks">
      <li><a href="#tradition">The Tradition</a></li>
      <li><a href="#menu">Menu</a></li>
      <li><a href="#location">Location</a></li>
      <li><a href="#reserve" class="btn-pill btn-gold nav-cta">Order / Table Booking</a></li>
    </ul>
    <button class="nav-toggle" id="navToggle" aria-label="Toggle menu">
      <span></span><span></span><span></span>
    </button>
  </nav>
</header>

<main id="top">

  <!-- HERO -->
  <section class="hero">
    <p class="eyebrow hero-eyebrow">GURAGE HERITAGE · ADDIS ABABA</p>
    <h1>Crafted Tradition.<br><em>Pure Flavor.</em></h1>
    <p>Totot Kitfo brings the authentic Gurage art of kitfo to Bole — finely minced beef, warmed gently in niter kibbeh and mitmita, served the way it has been for generations.</p>
    <div class="hero-ctas">
      <a href="#menu" class="btn-pill btn-gold btn-lg">Explore Menu</a>
      <a href="#location" class="btn-pill btn-outline btn-lg">Visit Us</a>
    </div>
    <div class="scroll-cue"></div>
  </section>

  <!-- THE CRAFT / BENTO -->
  <section id="tradition">
    <div class="container">
      <div class="section-head reveal">
        <p class="eyebrow center">THE CRAFT</p>
        <h2>Three things we never rush.</h2>
        <p>Every plate at Totot follows a discipline passed down through Gurage kitchens — nothing sped up, nothing substituted.</p>
      </div>

      <div class="bento">
        <div class="bento-card bento-a reveal">
          <span class="card-num">01</span>
          <h3>The Signature Kitfo</h3>
          <p>Finely minced beef, hand-cut to order, gently warmed with authentic mitmita and clarified spiced butter — never overcooked, never rushed.</p>
          <div class="plate" aria-hidden="true"></div>
        </div>
        <div class="bento-card reveal">
          <div class="glyph">◆</div>
          <span class="card-num">02</span>
          <h3>Gomen Besiga & Ayib</h3>
          <p>Traditional cottage cheese and slow-braised collard greens, plated on banana leaves in the old style.</p>
        </div>
        <div class="bento-card reveal">
          <div class="glyph">◈</div>
          <span class="card-num">03</span>
          <h3>Cultural Atmosphere</h3>
          <p>Authentic Gurage hospitality — low tables, warm coffee ceremonies, and a room that feels like a family gathering.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- MENU -->
  <section id="menu">
    <div class="container">
      <div class="section-head reveal">
        <p class="eyebrow center">THE MENU</p>
        <h2>Made to order, priced plainly.</h2>
        <p>All prices in Ethiopian Birr (ETB). Every dish is prepared fresh once you order.</p>
      </div>

      <div class="menu-tabs reveal">
        <button class="tab-btn active" data-tab="specialties">Specialties</button>
        <button class="tab-btn" data-tab="sides">Sides</button>
        <button class="tab-btn" data-tab="drinks">Drinks & Coffee</button>
      </div>

      <div class="menu-grid" id="menuGrid"></div>
    </div>
  </section>

  <!-- RESERVATION -->
  <section id="reserve">
    <div class="container">
      <div class="section-head reveal">
        <p class="eyebrow center">RESERVE</p>
        <h2>Book your table.</h2>
        <p>Tell us when you're coming — we'll have the table warm and ready.</p>
      </div>

      <form class="reserve-wrap reveal" id="reserveForm">
        <div class="field-row">
          <div class="field">
            <label for="rName">Name</label>
            <input type="text" id="rName" placeholder="Your full name" required>
          </div>
          <div class="field">
            <label for="rGuests">Guests</label>
            <select id="rGuests" required>
              <option value="" disabled selected>Select</option>
              <option>1</option><option>2</option><option>3</option><option>4</option>
              <option>5</option><option>6</option><option>7+</option>
            </select>
          </div>
        </div>
        <div class="field-row">
          <div class="field">
            <label for="rDate">Date</label>
            <input type="date" id="rDate" required>
          </div>
          <div class="field">
            <label for="rTime">Time</label>
            <input type="time" id="rTime" required>
          </div>
        </div>
        <button type="submit" class="submit-btn">Confirm Reservation</button>
        <div class="form-success" id="formSuccess">Thank you — your table request has been received. We'll confirm shortly by phone.</div>
      </form>
    </div>
  </section>

  <!-- LOCATION -->
  <section id="location">
    <div class="container">
      <div class="section-head reveal">
        <p class="eyebrow center">FIND US</p>
        <h2>Location & hours.</h2>
      </div>

      <div class="location-grid reveal">
        <div class="loc-map">
          <div class="pin"></div>
        </div>
        <div style="display:flex; flex-direction:column; gap:20px;">
          <div class="loc-card">
            <p class="loc-label">Address</p>
            <h3>Bole Sub-City</h3>
            <p>Totot Kitfo Restaurant<br>Bole Sub-City, Addis Ababa, Ethiopia</p>
          </div>
          <div class="loc-card">
            <p class="loc-label">Contact</p>
            <h3>Call for booking</h3>
            <p>+251 11 663 4521<br>Open daily for reservations</p>
          </div>
          <div class="loc-card">
            <div class="loc-label">Hours</div>
            <div class="hours-row"><span>Monday – Friday</span><span>11:00 – 22:00</span></div>
            <div class="hours-row"><span>Saturday – Sunday</span><span>10:00 – 23:00</span></div>
          </div>
        </div>
      </div>
    </div>
  </section>

</main>

<footer>
  <div class="container footer-inner">
    <a href="#top" class="logo">TOTO<span>T</span></a>
    <p>© 2026 Totot Kitfo — Bole Sub-City, Addis Ababa.</p>
  </div>
</footer>

<script>
  // ---------- Nav scroll state ----------
  const header = document.getElementById('siteHeader');
  window.addEventListener('scroll', () => {
    header.classList.toggle('scrolled', window.scrollY > 20);
  }, { passive:true });

  // ---------- Mobile nav toggle ----------
  const navToggle = document.getElementById('navToggle');
  const navLinks = document.getElementById('navLinks');
  navToggle.addEventListener('click', () => navLinks.classList.toggle('open'));
  navLinks.querySelectorAll('a').forEach(a => a.addEventListener('click', () => navLinks.classList.remove('open')));

  // ---------- Scroll reveal ----------
  const revealEls = document.querySelectorAll('.reveal');
  const io = new IntersectionObserver((entries) => {
    entries.forEach(e => { if (e.isIntersecting) e.target.classList.add('in'); });
  }, { threshold: 0.15 });
  revealEls.forEach(el => io.observe(el));

  // ---------- Gold thread scroll draw ----------
  const threadPath = document.getElementById('threadPath');
  const threadLen = threadPath.getTotalLength ? threadPath.getTotalLength() : 1000;
  threadPath.style.strokeDasharray = threadLen;
  threadPath.style.strokeDashoffset = threadLen;

  function updateThread(){
    const scrollTop = window.scrollY;
    const docHeight = document.documentElement.scrollHeight - window.innerHeight;
    const pct = docHeight > 0 ? Math.min(scrollTop / docHeight, 1) : 0;
    threadPath.style.strokeDashoffset = threadLen * (1 - pct);
  }
  window.addEventListener('scroll', () => requestAnimationFrame(updateThread), { passive:true });
  updateThread();

  // ---------- Menu data & tabs ----------
  const menuData = {
    specialties: [
      { name:"Kitfo Leb (Rare)", desc:"Finely minced beef warmed in niter kibbeh and mitmita, served the traditional way.", price:"450 ETB" },
      { name:"Kitfo Special", desc:"Our signature kitfo plated with ayib and sautéed gomen.", price:"520 ETB" },
      { name:"Gored Gored", desc:"Cubed beef tossed in spiced clarified butter and mitmita.", price:"480 ETB" },
      { name:"Dulet", desc:"Minced tripe, liver, and beef sautéed with onion, chili, and herbs.", price:"400 ETB" }
    ],
    sides: [
      { name:"Ayib", desc:"Fresh Ethiopian cottage cheese, cool and mild.", price:"120 ETB" },
      { name:"Gomen", desc:"Slow-cooked collard greens with garlic and onion.", price:"130 ETB" },
      { name:"Injera Basket", desc:"Extra warm injera, made fresh daily.", price:"60 ETB" },
      { name:"Timatim Salad", desc:"Tomato, onion, and jalapeño with a lemon dressing.", price:"110 ETB" }
    ],
    drinks: [
      { name:"Coffee Ceremony", desc:"Traditional roast, grind, and brew, served table-side.", price:"250 ETB" },
      { name:"Macchiato", desc:"Ethiopian-style espresso macchiato.", price:"90 ETB" },
      { name:"Tej", desc:"Honey wine, house-fermented.", price:"180 ETB" },
      { name:"Ambo Water", desc:"Ethiopian natural sparkling mineral water.", price:"70 ETB" }
    ]
  };

  const menuGrid = document.getElementById('menuGrid');
  const tabBtns = document.querySelectorAll('.tab-btn');

  function renderMenu(tab){
    menuGrid.innerHTML = '';
    menuData[tab].forEach((item, i) => {
      const el = document.createElement('div');
      el.className = 'menu-item';
      el.style.animationDelay = (i * 0.08) + 's';
      el.innerHTML = `
        <div>
          <div class="menu-item-name">${item.name}</div>
          <div class="menu-item-desc">${item.desc}</div>
        </div>
        <div class="menu-item-price">${item.price}</div>
      `;
      menuGrid.appendChild(el);
    });
  }

  tabBtns.forEach(btn => {
    btn.addEventListener('click', () => {
      tabBtns.forEach(b => b.classList.remove('active'));
      btn.classList.add('active');
      renderMenu(btn.dataset.tab);
    });
  });

  renderMenu('specialties');

  // ---------- Reservation form ----------
  const reserveForm = document.getElementById('reserveForm');
  const formSuccess = document.getElementById('formSuccess');
  reserveForm.addEventListener('submit', (e) => {
    e.preventDefault();
    formSuccess.classList.add('show');
    reserveForm.querySelector('.submit-btn').textContent = 'Request Sent';
    setTimeout(() => {
      reserveForm.querySelector('.submit-btn').textContent = 'Confirm Reservation';
    }, 3000);
  });

  // ---------- Set min date on date field to today ----------
  document.getElementById('rDate').min = new Date().toISOString().split('T')[0];
</script>

</body>
</html>
