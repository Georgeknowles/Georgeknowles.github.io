# Georgeknowles.github.io<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>George Knowles — Industrial Design</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;500;600;700&family=IBM+Plex+Sans:wght@400;500;600&family=IBM+Plex+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
  :root{
    --paper:#FAFAF8;
    --ink:#16181A;
    --ink-soft:#6B6F72;
    --line:#DEDEDA;
    --accent:#1F4E8C;
  }
  *{box-sizing:border-box; margin:0; padding:0;}
  html{scroll-behavior:smooth;}
  body{
    background:var(--paper);
    color:var(--ink);
    font-family:'IBM Plex Sans', sans-serif;
    line-height:1.6;
    -webkit-font-smoothing:antialiased;
  }
  h1,h2,h3{ font-family:'Space Grotesk', sans-serif; letter-spacing:-0.01em; font-weight:600;}
  .mono{ font-family:'IBM Plex Mono', monospace; letter-spacing:0.03em;}
  a{color:inherit; text-decoration:none;}

  nav{
    position:sticky; top:0; z-index:50;
    display:flex; align-items:center; justify-content:space-between;
    padding:26px 48px;
    background:rgba(250,250,248,0.88);
    backdrop-filter:blur(6px);
  }
  .logo{font-size:14px; font-weight:600;}
  .navlinks{display:flex; gap:36px; font-size:13px; color:var(--ink-soft);}
  .navlinks a{ transition:color .2s;}
  .navlinks a:hover{ color:var(--ink);}

  .hero{ max-width:760px; margin:0 auto; padding:140px 24px 110px;}
  .avail{
    font-size:12px; color:var(--accent);
    letter-spacing:0.04em; margin-bottom:22px;
    display:flex; align-items:center; gap:8px;
  }
  .avail::before{ content:""; width:6px; height:6px; border-radius:50%; background:var(--accent); display:inline-block;}
  .hero h1{ font-size:clamp(38px, 6vw, 60px); line-height:1.08;}
  .hero p{ margin-top:22px; font-size:18px; color:var(--ink-soft); max-width:520px;}

  .section-label{
    max-width:1080px; margin:0 auto; padding:0 24px;
    font-size:12px; color:var(--ink-soft); text-transform:uppercase; letter-spacing:0.1em;
    margin-top:130px; margin-bottom:36px;
  }

  .project{ max-width:1080px; margin:0 auto; padding:0 24px 96px;}

  .slideshow{
    position:relative;
    width:100%; height:480px;
    background:var(--line);
    overflow:hidden;
  }
  .slideshow .slide{
    position:absolute; inset:0;
    opacity:0; transition:opacity .5s ease;
    pointer-events:none;
  }
  .slideshow .slide.active{ opacity:1; pointer-events:auto;}
  .slideshow img{
    width:100%; height:100%; object-fit:cover;
    filter:grayscale(70%) contrast(1.01);
    transition:filter .6s ease;
    display:block;
  }
  .slideshow:hover img{ filter:grayscale(0%);}
  .slideshow img{ cursor:zoom-in;}
  .ss-btn{
    position:absolute; top:50%; transform:translateY(-50%);
    width:40px; height:40px; border-radius:50%;
    background:rgba(250,250,248,0.85);
    border:1px solid var(--line);
    display:flex; align-items:center; justify-content:center;
    cursor:pointer; font-size:16px; color:var(--ink);
    z-index:5; transition:background .2s;
  }
  .ss-btn:hover{ background:#fff;}
  .ss-prev{ left:16px;}
  .ss-next{ right:16px;}
  .ss-dots{
    position:absolute; bottom:16px; left:0; right:0;
    display:flex; justify-content:center; gap:7px; z-index:5;
  }
  .ss-dot{
    width:6px; height:6px; border-radius:50%;
    background:rgba(250,250,248,0.6);
    border:1px solid rgba(22,24,26,0.35);
    cursor:pointer;
  }
  .ss-dot.active{ background:var(--ink); border-color:var(--ink);}
  .ss-count{
    position:absolute; top:16px; right:16px;
    font-family:'IBM Plex Mono',monospace; font-size:11px;
    background:rgba(250,250,248,0.85); padding:4px 8px; z-index:5;
  }

  .project-body{
    display:grid; grid-template-columns:1fr 1.6fr; gap:48px;
    margin-top:28px;
  }
  .project-body h3{ font-size:24px;}
  .project-body .year{ display:block; font-size:13px; color:var(--ink-soft); margin-top:4px; font-family:'IBM Plex Mono',monospace;}
  .project-body .brief{ color:var(--ink-soft); font-size:15.5px; max-width:560px;}
  .meta{ margin-top:16px; font-size:12.5px; color:var(--ink-soft); font-family:'IBM Plex Mono',monospace;}
  .placeholder{color:#B8763F; font-style:italic;}
  .divider{ max-width:1080px; margin:0 auto; height:1px; background:var(--line);}

  @media (max-width:760px){
    .project-body{ grid-template-columns:1fr; gap:12px;}
    .slideshow{ height:340px;}
    nav{padding:20px 24px;}
    .navlinks{gap:20px;}
  }

  .about{ max-width:760px; margin:0 auto; padding:0 24px 100px;}
  .about p{ color:var(--ink-soft); font-size:16px; max-width:560px; margin-bottom:16px;}
  .tools{ display:flex; flex-wrap:wrap; gap:8px; margin-top:20px;}
  .tools span{ font-family:'IBM Plex Mono',monospace; font-size:11.5px; border:1px solid var(--line); padding:6px 12px; border-radius:2px;}
  .btn{ display:inline-block; margin-top:28px; border-bottom:1px solid var(--ink); padding-bottom:3px; font-size:14px; font-weight:500;}

  .contact{ max-width:760px; margin:0 auto; padding:60px 24px 140px;}
  .contact h2{ font-size:34px; max-width:420px;}
  .contact-links{ display:flex; gap:28px; margin-top:28px; font-size:15px;}
  .contact-links a{ border-bottom:1px solid var(--ink); padding-bottom:2px;}

  footer{ text-align:center; padding:28px; font-size:11.5px; color:var(--ink-soft); font-family:'IBM Plex Mono',monospace; border-top:1px solid var(--line);}

  /* ---------- lightbox ---------- */
  .lightbox{
    position:fixed; inset:0; z-index:1000;
    background:rgba(12,13,14,0.94);
    display:none;
    align-items:center; justify-content:center;
    padding:40px;
  }
  .lightbox.active{ display:flex;}
  .lightbox img{
    max-width:90vw; max-height:85vh;
    object-fit:contain;
    box-shadow:0 20px 60px rgba(0,0,0,0.4);
  }
  .lb-close{
    position:absolute; top:24px; right:28px;
    width:42px; height:42px; border-radius:50%;
    background:rgba(255,255,255,0.08);
    border:1px solid rgba(255,255,255,0.25);
    color:#fff; font-size:20px; line-height:1;
    display:flex; align-items:center; justify-content:center;
    cursor:pointer; transition:background .2s;
  }
  .lb-close:hover{ background:rgba(255,255,255,0.18);}
  .lb-btn{
    position:absolute; top:50%; transform:translateY(-50%);
    width:52px; height:52px; border-radius:50%;
    background:rgba(255,255,255,0.08);
    border:1px solid rgba(255,255,255,0.25);
    color:#fff; font-size:22px;
    display:flex; align-items:center; justify-content:center;
    cursor:pointer; transition:background .2s;
  }
  .lb-btn:hover{ background:rgba(255,255,255,0.18);}
  .lb-prev{ left:24px;}
  .lb-next{ right:24px;}
  .lb-count{
    position:absolute; bottom:24px; left:0; right:0;
    text-align:center; color:rgba(255,255,255,0.7);
    font-family:'IBM Plex Mono',monospace; font-size:12px;
  }
  @media (max-width:760px){
    .lightbox{ padding:16px;}
    .lb-btn{ width:42px; height:42px; font-size:18px;}
    .lb-prev{ left:10px;}
    .lb-next{ right:10px;}
    .lb-close{ top:14px; right:14px; width:36px; height:36px;}
  }
</style>
</head>
<body>

<nav>
  <div class="logo">George Knowles</div>
  <div class="navlinks">
    <a href="#work">Work</a>
    <a href="#about">About</a>
    <a href="#contact">Contact</a>
  </div>
</nav>

<section class="hero">
  <div class="avail">Open to Fall 2026 internships &amp; full-time roles</div>
  <h1>Industrial designer working across furniture, product systems, and mechanisms.</h1>
  <p>From early sketch to working prototype — I like problems that end up in your hands.</p>
</section>

<div class="section-label" id="work">Selected Work</div>

<section class="project">
  <div class="slideshow" data-project="huzfood"></div>
  <div class="project-body">
    <div><h3>Food Organizing System<span class="year">2024</span></h3></div>
    <div>
      <p class="brief placeholder">Shared refrigorators can get chaotic and disorganized. This project aims to fix that problem.</p>
      <div class="meta placeholder">PLA, Polypropelyn, Rubber · Designing in Context Studio · Senior</div>
    </div>
  </div>
</section>
<div class="divider"></div>

<section class="project">
  <div class="slideshow" data-project="om"></div>
  <div class="project-body">
    <div><h3>Meditation Productivity App<span class="year">2023</span></h3></div>
    <div>
      <p class="brief placeholder">A smart device for office workers.</p>
      <div class="meta placeholder">Conceptual Product · Dell User Experience · Intern</div>
    </div>
  </div>
</section>
<div class="divider"></div>

<section class="project">
  <div class="slideshow" data-project="seet"></div>
  <div class="project-body">
    <div><h3>Convertible Decoration Seating<span class="year">2023–2024</span></h3></div>
    <div>
      <p class="brief placeholder">Side chair that transforms into wall art to save space.</p>
      <div class="meta placeholder">Cedar, Poplar, Titanium, Oil Paint · Furniture Studio · Senior</div>
    </div>
  </div>
</section>
<div class="divider"></div>

<section class="project">
  <div class="slideshow" data-project="drumplus"></div>
  <div class="project-body">
    <div><h3>Hands-On Educational Music Kit<span class="year">2023</span></h3></div>
    <div>
      <p class="brief placeholder">Teaching the science of music to older elementary aged kids.</p>
      <div class="meta placeholder">Wood, Cardboard, PVC · STEAM Box Studio · Senior</div>
    </div>
  </div>
</section>
<div class="divider"></div>

<section class="project">
  <div class="slideshow" data-project="mechhand"></div>
  <div class="project-body">
    <div><h3>Analog Stylized Prosthetic<span class="year">2022</span></h3></div>
    <div>
      <p class="brief placeholder">Linkages allow passive dynamic grip for transradial amputees.</p>
      <div class="meta placeholder">Stainless Steel · Prosthetics Studio · Junior</div>
    </div>
  </div>
</section>
<div class="divider"></div>

<section class="project">
  <div class="slideshow" data-project="additional"></div>
  <div class="project-body">
    <div><h3>Additional Work<span class="year">Sketches &amp; studies</span></h3></div>
    <div>
      <p class="brief placeholder">[Quick sketches, form studies, or side projects — a line each is enough.]</p>
    </div>
  </div>
</section>

<div class="section-label" id="about">About</div>
<section class="about">
  <p class="placeholder">I like devising practical, but creative solutions to design problems. Working at a custom furniture shop taught me to be creative, but always design for the client first. </p>
  <p class="placeholder">Spring 2024 Graduate</p>
  <div class="tools">
    <span class="placeholder">Rhino</span>
    <span class="placeholder">SolidWorks</span>
    <span class="placeholder">KeyShot</span>
    <span class="placeholder">Fusion 360</span>
    <span class="placeholder">Woodshop</span>
    <span class="placeholder">3D Printing</span>
  </div>
  <a class="btn" href="#">Download Résumé (PDF)</a>
</section>

<section class="contact" id="contact">
  <h2>Let's talk about fall.</h2>
  <div class="contact-links">
    <a href="mailto:gwknowles11@gmail.com">Email</a>

  </div>
</section>

<footer>© 2026 George Knowles — Industrial Design</footer>

<div class="lightbox" id="lightbox">
  <div class="lb-close" id="lbClose">&#10005;</div>
  <div class="lb-btn lb-prev" id="lbPrev">&#8249;</div>
  <img id="lbImage" src="" alt="">
  <div class="lb-btn lb-next" id="lbNext">&#8250;</div>
  <div class="lb-count" id="lbCount"></div>
</div>

<!--
============================================================
  EDIT YOUR IMAGES HERE — no coding needed
============================================================
  Each project below has a list of image links inside square
  brackets [ ]. Each link is wrapped in quotes " " and ends
  with a comma, except the very last one in the list.

  TO ADD AN IMAGE:
    1. Get a link to the image (a URL, or a filename if you've
       uploaded the image into an "images" folder next to this
       file, e.g. "images/huzfood-05.jpg").
    2. Add a new line: "your-link-here.jpg",
    3. Make sure it still has quotes and a comma, just like
       the lines around it.

  TO REMOVE AN IMAGE:
    1. Find its line.
    2. Delete the whole line.
    3. If you deleted the LAST line in a list, remove the
       comma from what is now the new last line.

  That's it — save the file and refresh the page. Nothing
  else on the page needs to change.
============================================================
-->
<script>
  const PROJECT_IMAGES = {
    huzfood: [
      "https://static.wixstatic.com/media/81d416_e330fd7cc5bb416396a557ffdf85f6aa~mv2.jpg/v1/fit/w_960,h_1280,q_90,enc_avif,quality_auto/81d416_e330fd7cc5bb416396a557ffdf85f6aa~mv2.jpg",
      "https://static.wixstatic.com/media/81d416_6caaf227c7b84492897d01736ab161b4~mv2.webp/v1/fit/w_960,h_1280,q_90,enc_avif,quality_auto/81d416_6caaf227c7b84492897d01736ab161b4~mv2.webp",
      "https://static.wixstatic.com/media/81d416_4bc1b14644234a31881a73faf0a966c9~mv2.jpg/v1/fit/w_960,h_1280,q_90,enc_avif,quality_auto/81d416_4bc1b14644234a31881a73faf0a966c9~mv2.jpg",
      "https://static.wixstatic.com/media/81d416_2ac8da4c33054fb7af853811c06b98ad~mv2.jpg/v1/fit/w_960,h_1280,q_90,enc_avif,quality_auto/81d416_2ac8da4c33054fb7af853811c06b98ad~mv2.jpg",
      "https://static.wixstatic.com/media/81d416_1912b73fb8564662806e4e2c55852f9b~mv2.webp/v1/fit/w_960,h_1280,q_90,enc_avif,quality_auto/81d416_1912b73fb8564662806e4e2c55852f9b~mv2.webp",
      "https://static.wixstatic.com/media/81d416_d66e7b0985f242c3bb055327dede7fc8~mv2.webp/v1/fit/w_960,h_1280,q_90,enc_avif,quality_auto/81d416_d66e7b0985f242c3bb055327dede7fc8~mv2.webp",
      "https://static.wixstatic.com/media/81d416_5f922862925d4e52b122c57da94f9bf8~mv2.webp/v1/fit/w_960,h_1280,q_90,enc_avif,quality_auto/81d416_5f922862925d4e52b122c57da94f9bf8~mv2.webp",
      "https://static.wixstatic.com/media/81d416_fde4546225b6412c8cf01ff41a509242~mv2.webp/v1/fit/w_960,h_1280,q_90,enc_avif,quality_auto/81d416_fde4546225b6412c8cf01ff41a509242~mv2.webp"
    ],
    om: [
      "https://static.wixstatic.com/media/81d416_3b854f58559949ae9b25bdb19f769ad4~mv2.png/v1/fit/w_960,h_1280,q_90,enc_avif,quality_auto/81d416_3b854f58559949ae9b25bdb19f769ad4~mv2.png",
      "https://static.wixstatic.com/media/81d416_140c58bf6db0450a9c98a470ba6d8ce8~mv2.png/v1/fit/w_960,h_1280,q_90,enc_avif,quality_auto/81d416_140c58bf6db0450a9c98a470ba6d8ce8~mv2.png",
      "https://static.wixstatic.com/media/81d416_33efa443bad54e6f99a03eba1f93556e~mv2.png/v1/fit/w_960,h_1280,q_90,enc_avif,quality_auto/81d416_33efa443bad54e6f99a03eba1f93556e~mv2.png",
      "https://static.wixstatic.com/media/81d416_4f76f6c9c84a45338cb57803673a5dbc~mv2.png/v1/fit/w_960,h_1280,q_90,enc_avif,quality_auto/81d416_4f76f6c9c84a45338cb57803673a5dbc~mv2.png",
      "https://static.wixstatic.com/media/81d416_122c338c769c4e159b7be88b1972cffb~mv2.png/v1/fit/w_960,h_1280,q_90,enc_avif,quality_auto/81d416_122c338c769c4e159b7be88b1972cffb~mv2.png",
      "https://static.wixstatic.com/media/81d416_4a67dcd8d49d472a89d77cded8415427~mv2.png/v1/fit/w_960,h_1280,q_90,enc_avif,quality_auto/81d416_4a67dcd8d49d472a89d77cded8415427~mv2.png",
      "https://static.wixstatic.com/media/81d416_0fa2698a9f9440729e6b17182cc3698d~mv2.png/v1/fit/w_960,h_1280,q_90,enc_avif,quality_auto/81d416_0fa2698a9f9440729e6b17182cc3698d~mv2.png",
      "https://static.wixstatic.com/media/81d416_8716041bed32440ea6b1689b24737b31~mv2.png/v1/fit/w_960,h_1280,q_90,enc_avif,quality_auto/81d416_8716041bed32440ea6b1689b24737b31~mv2.png"
    ],
    seet: [
      "https://static.wixstatic.com/media/81d416_a1d9b573abae429d9b45e821d52dc302~mv2.jpg/v1/fit/w_960,h_1280,q_90,enc_avif,quality_auto/81d416_a1d9b573abae429d9b45e821d52dc302~mv2.jpg",
      "https://static.wixstatic.com/media/81d416_7b8cd8e95f434b419a28c0cf381a308f~mv2.jpg/v1/fit/w_960,h_1280,q_90,enc_avif,quality_auto/81d416_7b8cd8e95f434b419a28c0cf381a308f~mv2.jpg",
      "https://static.wixstatic.com/media/81d416_096258b20a894eb6ac54f93d6396f62d~mv2.jpg/v1/fit/w_960,h_1280,q_90,enc_avif,quality_auto/81d416_096258b20a894eb6ac54f93d6396f62d~mv2.jpg",
      "https://static.wixstatic.com/media/81d416_bc049eb888b44527a202f23ebae75e8e~mv2.jpg/v1/fill/w_960,h_1280,fp_0.62_0.06,q_90,enc_avif,quality_auto/81d416_bc049eb888b44527a202f23ebae75e8e~mv2.jpg",
      "https://static.wixstatic.com/media/81d416_bc38a9e7d9fc45a38cb8e7ccad46b1e4~mv2.jpg/v1/fit/w_960,h_1280,q_90,enc_avif,quality_auto/81d416_bc38a9e7d9fc45a38cb8e7ccad46b1e4~mv2.jpg",
      "https://static.wixstatic.com/media/81d416_adbdcab2469d485b8b789735d14e87c7~mv2.jpg/v1/fit/w_960,h_1280,q_90,enc_avif,quality_auto/81d416_adbdcab2469d485b8b789735d14e87c7~mv2.jpg",
      "https://static.wixstatic.com/media/81d416_144d5417087740eba8a67a53a2eb14f6~mv2.jpg/v1/fit/w_960,h_1280,q_90,enc_avif,quality_auto/81d416_144d5417087740eba8a67a53a2eb14f6~mv2.jpg",
      "https://static.wixstatic.com/media/81d416_f685dd8126f140339d530985f2559d91~mv2.jpg/v1/fit/w_960,h_1280,q_90,enc_avif,quality_auto/81d416_f685dd8126f140339d530985f2559d91~mv2.jpg",
      "https://static.wixstatic.com/media/81d416_934c2169644b4e51867ff69534a063a3~mv2.jpg/v1/fit/w_960,h_1280,q_90,enc_avif,quality_auto/81d416_934c2169644b4e51867ff69534a063a3~mv2.jpg",
      "https://static.wixstatic.com/media/81d416_a9a029399b0441ae8a9222ec093c9a5c~mv2.jpg/v1/fit/w_960,h_1280,q_90,enc_avif,quality_auto/81d416_a9a029399b0441ae8a9222ec093c9a5c~mv2.jpg"
    ],
    drumplus: [
      "https://static.wixstatic.com/media/81d416_5e4de548c85d4e74a3549758e0414e76~mv2.jpg/v1/fit/w_960,h_1280,q_90,enc_avif,quality_auto/81d416_5e4de548c85d4e74a3549758e0414e76~mv2.jpg",
      "https://static.wixstatic.com/media/81d416_ebcef097fdb64109b82f92b396a3dbec~mv2.jpg/v1/fit/w_960,h_1280,q_90,enc_avif,quality_auto/81d416_ebcef097fdb64109b82f92b396a3dbec~mv2.jpg",
      "https://static.wixstatic.com/media/81d416_71b158b77f1f4a2483201856a9f60ea7~mv2.jpg/v1/fit/w_960,h_1280,q_90,enc_avif,quality_auto/81d416_71b158b77f1f4a2483201856a9f60ea7~mv2.jpg",
      "https://static.wixstatic.com/media/81d416_b25ce608ae294ab0a4d8e3105984d24f~mv2.jpg/v1/fill/w_960,h_1280,fp_0.52_0.21,q_90,enc_avif,quality_auto/81d416_b25ce608ae294ab0a4d8e3105984d24f~mv2.jpg",
      "https://static.wixstatic.com/media/81d416_b4b0178567bc4e53ae442d43cb27593b~mv2.jpg/v1/fill/w_960,h_1280,fp_0.38_0.25,q_90,enc_avif,quality_auto/81d416_b4b0178567bc4e53ae442d43cb27593b~mv2.jpg",
      "https://static.wixstatic.com/media/81d416_8f16fcd5879b4ab1a7873458b3582cdb~mv2.jpg/v1/fit/w_960,h_1280,q_90,enc_avif,quality_auto/81d416_8f16fcd5879b4ab1a7873458b3582cdb~mv2.jpg",
      "https://static.wixstatic.com/media/81d416_de8004fafa5e416eb0de06947cfcd220~mv2.png/v1/fit/w_858,h_1178,q_90,enc_avif,quality_auto/81d416_de8004fafa5e416eb0de06947cfcd220~mv2.png",
      "https://static.wixstatic.com/media/81d416_ad2dcf9bbed14bc5917d7adf1ad2a7dd~mv2.png/v1/fit/w_960,h_1280,q_90,enc_avif,quality_auto/81d416_ad2dcf9bbed14bc5917d7adf1ad2a7dd~mv2.png"
    ],
    mechhand: [
      "https://static.wixstatic.com/media/81d416_b4deacc2aa3348cb8f9705fb9da09dbe~mv2.jpg/v1/fit/w_960,h_1280,q_90,enc_avif,quality_auto/81d416_b4deacc2aa3348cb8f9705fb9da09dbe~mv2.jpg",
      "https://static.wixstatic.com/media/81d416_74fd2c7e7c3348fc91b1b4ae11edf005~mv2.jpg/v1/fit/w_960,h_1280,q_90,enc_avif,quality_auto/81d416_74fd2c7e7c3348fc91b1b4ae11edf005~mv2.jpg",
      "https://static.wixstatic.com/media/81d416_aeac2f9fc8574dc5af87fc664141c351~mv2.jpg/v1/fill/w_960,h_1280,fp_0.26_0.23,q_90,enc_avif,quality_auto/81d416_aeac2f9fc8574dc5af87fc664141c351~mv2.jpg",
      "https://static.wixstatic.com/media/81d416_353c8f294f4f4469a447157b823d29df~mv2.jpg/v1/fit/w_960,h_1280,q_90,enc_avif,quality_auto/81d416_353c8f294f4f4469a447157b823d29df~mv2.jpg",
      "https://static.wixstatic.com/media/81d416_45692688e5b04c42b4ba887a2b156ce6~mv2.png/v1/fit/w_960,h_1280,q_90,enc_avif,quality_auto/81d416_45692688e5b04c42b4ba887a2b156ce6~mv2.png",
      "https://static.wixstatic.com/media/81d416_80ae37b574014447b928a8b754330b3b~mv2.jpg/v1/fit/w_960,h_1280,q_90,enc_avif,quality_auto/81d416_80ae37b574014447b928a8b754330b3b~mv2.jpg",
      "https://static.wixstatic.com/media/81d416_8e71952c472e45039132d6521a970433~mv2.jpeg/v1/fit/w_960,h_1250,q_90,enc_avif,quality_auto/81d416_8e71952c472e45039132d6521a970433~mv2.jpeg"
    ],
    additional: [
      "https://static.wixstatic.com/media/81d416_f6525facd20f44089af73a4babf7e0d8~mv2.jpg/v1/fit/w_960,h_1280,q_90,enc_avif,quality_auto/81d416_f6525facd20f44089af73a4babf7e0d8~mv2.jpg",
      "https://static.wixstatic.com/media/81d416_02c7c98483c642c793b12bd2d70d69c8~mv2.jpg/v1/fill/w_960,h_1280,fp_0.67_0.35,q_90,enc_avif,quality_auto/81d416_02c7c98483c642c793b12bd2d70d69c8~mv2.jpg",
      "https://static.wixstatic.com/media/81d416_f51a66186156483796ef673e22907b3e~mv2.jpg/v1/fill/w_960,h_1280,fp_0.47_0.51,q_90,enc_avif,quality_auto/81d416_f51a66186156483796ef673e22907b3e~mv2.jpg",
      "https://static.wixstatic.com/media/81d416_fdb7b76efddf43b4b6a4ba58a87d826f~mv2.jpg/v1/fit/w_960,h_1280,q_90,enc_avif,quality_auto/81d416_fdb7b76efddf43b4b6a4ba58a87d826f~mv2.jpg"
    ]
  };

  function buildSlideshow(container){
    const key = container.dataset.project;
    const images = PROJECT_IMAGES[key] || [];
    if(images.length === 0){
      container.innerHTML = '<div style="display:flex;align-items:center;justify-content:center;height:100%;color:#999;font-family:monospace;font-size:13px;">No images listed for "'+key+'"</div>';
      return;
    }
    let current = 0;
    const slidesHTML = images.map((src,i)=>
      `<div class="slide${i===0?' active':''}"><img src="${src}" alt="${key} image ${i+1}"></div>`
    ).join('');
    const dotsHTML = images.map((_,i)=>
      `<div class="ss-dot${i===0?' active':''}" data-i="${i}"></div>`
    ).join('');
    container.innerHTML = `
      ${slidesHTML}
      ${images.length > 1 ? `
        <div class="ss-btn ss-prev">&#8249;</div>
        <div class="ss-btn ss-next">&#8250;</div>
        <div class="ss-dots">${dotsHTML}</div>
        <div class="ss-count">${current+1} / ${images.length}</div>
      ` : ''}
    `;
    if(images.length <= 1) return;

    const slides = container.querySelectorAll('.slide');
    const dots = container.querySelectorAll('.ss-dot');
    const countEl = container.querySelector('.ss-count');

    function goTo(i){
      current = (i + images.length) % images.length;
      slides.forEach((s,idx)=>s.classList.toggle('active', idx===current));
      dots.forEach((d,idx)=>d.classList.toggle('active', idx===current));
      countEl.textContent = (current+1)+' / '+images.length;
    }
    container.querySelector('.ss-prev').addEventListener('click', ()=>goTo(current-1));
    container.querySelector('.ss-next').addEventListener('click', ()=>goTo(current+1));
    dots.forEach(d=>d.addEventListener('click', ()=>goTo(parseInt(d.dataset.i))));

    // clicking the visible slide image opens the lightbox at that image
    container.addEventListener('click', (e)=>{
      if(e.target.tagName === 'IMG'){
        openLightbox(key, current);
      }
    });
  }

  document.querySelectorAll('.slideshow').forEach(buildSlideshow);

  // ---------------- lightbox ----------------
  const lightbox = document.getElementById('lightbox');
  const lbImage = document.getElementById('lbImage');
  const lbCount = document.getElementById('lbCount');
  let lbKey = null;
  let lbIndex = 0;

  function openLightbox(key, index){
    lbKey = key;
    lbIndex = index;
    renderLightbox();
    lightbox.classList.add('active');
  }
  function closeLightbox(){
    lightbox.classList.remove('active');
  }
  function renderLightbox(){
    const images = PROJECT_IMAGES[lbKey] || [];
    if(images.length === 0) return;
    lbIndex = (lbIndex + images.length) % images.length;
    lbImage.src = images[lbIndex];
    lbImage.alt = lbKey + ' image ' + (lbIndex+1);
    lbCount.textContent = (lbIndex+1) + ' / ' + images.length;
  }
  function lbNext(){ lbIndex++; renderLightbox(); }
  function lbPrev(){ lbIndex--; renderLightbox(); }

  document.getElementById('lbClose').addEventListener('click', closeLightbox);
  document.getElementById('lbNext').addEventListener('click', lbNext);
  document.getElementById('lbPrev').addEventListener('click', lbPrev);

  // click on the dark backdrop (not the image or buttons) closes it
  lightbox.addEventListener('click', (e)=>{
    if(e.target === lightbox) closeLightbox();
  });

  // keyboard: Esc closes, arrow keys navigate
  document.addEventListener('keydown', (e)=>{
    if(!lightbox.classList.contains('active')) return;
    if(e.key === 'Escape') closeLightbox();
    if(e.key === 'ArrowRight') lbNext();
    if(e.key === 'ArrowLeft') lbPrev();
  });
</script>

</body>
</html>
