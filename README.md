Skip to content
sumondatta
sumondatta.github.io
Repository navigation
Code
Issues
Pull requests
Agents
Actions
Projects
Wiki
Security and quality
Insights
Settings
Commit 510ca60
sumondatta
sumondatta
authored
4 minutes ago
·
·
Verified
Add files via upload
main
1 parent 
631fd14
 commit 
510ca60
1 file changed

+470
Lines changed: 470 additions & 0 deletions
File tree
Filter files…
index.html
Search within code
 
‎index.html‎
+470
Lines changed: 470 additions & 0 deletions
Original file line number	Diff line number	Diff line change
@@ -0,0 +1,470 @@
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Sumon Datta, Ph.D., E.I. — Irrigation Engineer, Oklahoma State University</title>
<meta name="description" content="Sumon Datta, Ph.D., E.I. — Assistant Professor & Irrigation Engineer and Director of the Irrigation Research Laboratory, Department of Biosystems & Agricultural Engineering, Oklahoma State University." />
<!--
  HOW TO EDIT: everything is in this one file. Find a section by its
  comment (e.g. SECTION: GRANTS) and edit the text. All colours, fonts
  and spacing live in the :root block of <style>. No build step — just
  save and re-upload to your repo.
-->
<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
<link href="https://fonts.googleapis.com/css2?family=Fraunces:opsz,wght@9..144,400;9..144,500;9..144,600&family=IBM+Plex+Mono:wght@400;500&family=IBM+Plex+Sans:wght@400;500;600&display=swap" rel="stylesheet" />
<style>
  :root{
    --ground:#f3f5f0;
    --panel:#fbfcfa;
    --ink:#103b36;
    --ink-2:#33514c;
    --muted:#728681;
    --accent:#b1742a;
    --water:#2c7a76;
    --line:#dde2d8;
    --line-2:#e9ece4;
    --serif:'Fraunces',Georgia,'Times New Roman',serif;
    --sans:'IBM Plex Sans',system-ui,-apple-system,Segoe UI,Roboto,sans-serif;
    --mono:'IBM Plex Mono',ui-monospace,SFMono-Regular,Menlo,monospace;
    --content:840px;
    --pad:clamp(22px,5vw,40px);
  }
  *{box-sizing:border-box;}
  html{scroll-behavior:smooth;}
  body{
    margin:0;background:var(--ground);color:var(--ink-2);
    font-family:var(--sans);font-size:17px;line-height:1.7;
    -webkit-font-smoothing:antialiased;text-rendering:optimizeLegibility;
  }
  @media (prefers-reduced-motion:reduce){
    html{scroll-behavior:auto;} *{animation:none!important;transition:none!important;}
  }
  a{color:var(--water);text-decoration:none;}
  a:hover{color:var(--ink);}
  a:focus-visible,button:focus-visible{outline:2px solid var(--accent);outline-offset:3px;border-radius:2px;}
  .wrap{max-width:var(--content);margin:0 auto;padding:0 var(--pad);}
  /* ---- shared label ---- */
  .eyebrow{
    font-family:var(--mono);font-size:12px;letter-spacing:.16em;text-transform:uppercase;
    color:var(--accent);margin:0 0 18px;display:flex;align-items:center;gap:12px;
  }
  .eyebrow::before{content:"";width:24px;height:1px;background:currentColor;display:inline-block;flex:none;}
  /* ---- top bar ---- */
  .bar{position:sticky;top:0;z-index:50;background:var(--ground);border-bottom:1px solid var(--line);}
  .bar-inner{max-width:var(--content);margin:0 auto;padding:13px var(--pad);display:flex;align-items:center;justify-content:space-between;gap:18px;}
  .brand{font-family:var(--mono);font-size:12.5px;letter-spacing:.1em;color:var(--ink);text-transform:uppercase;white-space:nowrap;}
  .brand b{font-weight:500;}
  nav.menu{display:flex;gap:18px;}
  nav.menu a{font-family:var(--mono);font-size:11.5px;letter-spacing:.07em;text-transform:uppercase;color:var(--muted);white-space:nowrap;}
  nav.menu a:hover{color:var(--ink);}
  @media (max-width:820px){ nav.menu{display:none;} }
  /* ---- hero ---- */
  .hero{padding:clamp(44px,8vw,92px) 0 clamp(30px,5vw,52px);}
  .hero-grid{display:grid;grid-template-columns:1fr auto;gap:clamp(24px,4vw,44px);align-items:start;}
  @media (max-width:720px){ .hero-grid{grid-template-columns:1fr;} }
  .hero h1{font-family:var(--serif);font-weight:500;font-size:clamp(42px,8vw,72px);line-height:1;letter-spacing:-.015em;color:var(--ink);margin:0;}
  .waterline{height:3px;background:linear-gradient(90deg,var(--water),var(--accent));border-radius:2px;margin:20px 0 22px;max-width:460px;width:0;animation:fill 1.05s cubic-bezier(.2,.7,.2,1) .12s forwards;}
  @keyframes fill{to{width:100%;}}
  @media (prefers-reduced-motion:reduce){ .waterline{width:100%;} }
  .lede{font-size:clamp(18px,2.3vw,21px);line-height:1.5;color:var(--ink-2);max-width:45ch;margin:0 0 24px;}
  .role-line{font-family:var(--mono);font-size:12.5px;letter-spacing:.03em;color:var(--muted);line-height:1.95;margin:0 0 24px;}
  .role-line strong{color:var(--ink);font-weight:500;}
  .chips{display:flex;flex-wrap:wrap;gap:10px;}
  .chip{font-family:var(--mono);font-size:12.5px;letter-spacing:.03em;border:1px solid var(--line);border-radius:999px;padding:9px 16px;color:var(--ink);background:var(--panel);transition:border-color .2s,color .2s,background .2s;}
  .chip:hover{border-color:var(--water);color:var(--water);}
  .chip.solid{background:var(--ink);color:#eaf2ef;border-color:var(--ink);}
  .chip.solid:hover{background:var(--water);border-color:var(--water);color:#fff;}
  .portrait{width:clamp(150px,20vw,190px);height:clamp(150px,20vw,190px);border-radius:4px;object-fit:cover;border:1px solid var(--line);box-shadow:0 18px 38px -28px rgba(16,59,54,.55);}
  /* ---- stat ledger (hairlines via 1px grid gap) ---- */
  .ledger{border-top:1px solid var(--line);border-bottom:1px solid var(--line);}
  .ledger .grid{max-width:var(--content);margin:0 auto;display:grid;grid-template-columns:repeat(3,1fr);gap:1px;background:var(--line-2);}
  @media (max-width:560px){ .ledger .grid{grid-template-columns:repeat(2,1fr);} }
  .stat{background:var(--ground);padding:24px clamp(18px,3vw,28px);}
  .stat .num{font-family:var(--serif);font-weight:500;font-size:clamp(26px,3.4vw,33px);color:var(--ink);line-height:1;}
  .stat .num span{color:var(--accent);}
  .stat .lab{font-family:var(--mono);font-size:10.5px;letter-spacing:.11em;text-transform:uppercase;color:var(--muted);margin-top:11px;line-height:1.45;}
  /* ---- sections ---- */
  section{padding:clamp(50px,7vw,88px) 0;border-bottom:1px solid var(--line);}
  .sec-title{font-family:var(--serif);font-weight:500;font-size:clamp(27px,3.6vw,36px);line-height:1.1;letter-spacing:-.01em;color:var(--ink);margin:0 0 26px;max-width:26ch;}
  .prose p{margin:0 0 18px;max-width:68ch;}
  .prose p:last-child{margin-bottom:0;}
  .note{color:var(--muted);font-size:15px;margin:-8px 0 6px;max-width:68ch;}
  /* ---- grouped lists ---- */
  .group-label{font-family:var(--mono);font-size:11.5px;letter-spacing:.13em;text-transform:uppercase;color:var(--accent);margin:34px 0 14px;padding-bottom:10px;border-bottom:1px solid var(--line);}
  .entry{display:grid;grid-template-columns:64px 1fr;gap:18px;padding:18px 0;border-bottom:1px solid var(--line-2);}
  .entry:last-child{border-bottom:0;}
  .entry .yr{font-family:var(--mono);font-size:13px;color:var(--muted);padding-top:2px;}
  .entry .ttl{font-weight:600;color:var(--ink);line-height:1.4;}
  .entry .meta{font-family:var(--mono);font-size:12px;letter-spacing:.02em;color:var(--muted);margin-top:7px;line-height:1.75;}
  .entry .meta .role{color:var(--water);}
  .entry .meta .amt{color:var(--ink-2);}
  .entry .desc{font-size:15.5px;color:var(--ink-2);margin-top:9px;max-width:70ch;}
  @media (max-width:560px){ .entry{grid-template-columns:1fr;gap:5px;} .entry .yr{padding-top:0;} }
  /* ---- publications ---- */
  ol.pubs{list-style:none;counter-reset:p;margin:0;padding:0;}
  ol.pubs li{counter-increment:p;display:grid;grid-template-columns:30px 1fr;gap:16px;padding:16px 0;border-bottom:1px solid var(--line-2);}
  ol.pubs li:last-child{border-bottom:0;}
  ol.pubs li::before{content:counter(p,decimal-leading-zero);font-family:var(--mono);font-size:12px;color:var(--accent);padding-top:3px;}
  .pub-t{color:var(--ink);font-weight:500;}
  .pub-a{font-size:15px;color:var(--ink-2);}
  .pub-v{font-family:var(--mono);font-size:12px;color:var(--muted);margin-top:5px;letter-spacing:.01em;}
  .pub-v a{color:var(--water);}
  /* ---- cards ---- */
  .cards{display:grid;grid-template-columns:repeat(2,1fr);gap:16px;}
  @media (max-width:640px){ .cards{grid-template-columns:1fr;} }
  .card{background:var(--panel);border:1px solid var(--line);border-radius:6px;padding:22px;}
  .card h4{margin:0;font-family:var(--serif);font-weight:500;font-size:20px;color:var(--ink);line-height:1.2;}
  .card .deg{font-family:var(--mono);font-size:11.5px;letter-spacing:.05em;text-transform:uppercase;color:var(--accent);margin:8px 0 13px;}
  .card p{margin:0;font-size:15px;color:var(--ink-2);}
  .card .status{margin-top:12px;font-size:13.5px;color:var(--muted);font-style:italic;}
  /* ---- timelines ---- */
  .two-col{display:grid;grid-template-columns:1fr 1fr;gap:clamp(28px,5vw,52px);}
  @media (max-width:720px){ .two-col{grid-template-columns:1fr;} }
  .tl h3{font-family:var(--mono);font-size:12px;letter-spacing:.14em;text-transform:uppercase;color:var(--accent);margin:0 0 22px;}
  .tl-item{padding:0 0 22px 22px;border-left:1px solid var(--line);position:relative;}
  .tl-item:last-child{padding-bottom:0;}
  .tl-item::before{content:"";position:absolute;left:-4.5px;top:7px;width:8px;height:8px;border-radius:50%;background:var(--water);}
  .tl-when{font-family:var(--mono);font-size:11.5px;color:var(--muted);letter-spacing:.03em;}
  .tl-what{font-weight:600;color:var(--ink);margin-top:3px;line-height:1.35;}
  .tl-where{font-size:14.5px;color:var(--ink-2);margin-top:3px;}
  .tl-note{font-size:13.5px;color:var(--muted);margin-top:5px;}
  /* ---- OASIS feature ---- */
  .feature{background:var(--ink);color:#dbe8e4;border-radius:8px;padding:clamp(28px,5vw,44px);}
  .feature .eyebrow{color:#e3ad63;}
  .feature h3{font-family:var(--serif);font-weight:500;font-size:clamp(23px,3.2vw,31px);color:#fff;margin:0 0 14px;line-height:1.12;}
  .feature p{margin:0 0 20px;max-width:64ch;color:#caded8;}
  .feature .ftmeta{font-family:var(--mono);font-size:12px;letter-spacing:.04em;color:#9cc0ba;margin:0 0 22px;line-height:1.7;}
  .feature .chip{background:transparent;border-color:#3d635e;color:#eaf2ef;}
  .feature .chip:hover{border-color:#e3ad63;color:#f3d8b3;}
  /* ---- join CTA ---- */
  .join{background:var(--panel);border:1px solid var(--line);border-radius:8px;padding:clamp(28px,5vw,44px);}
  .join h3{font-family:var(--serif);font-weight:500;font-size:clamp(23px,3.2vw,31px);color:var(--ink);margin:0 0 14px;line-height:1.12;}
  .join p{max-width:66ch;}
  /* ---- sponsors ---- */
  .sponsors{display:flex;flex-wrap:wrap;gap:10px;}
  .sponsors span{font-family:var(--mono);font-size:12.5px;letter-spacing:.03em;color:var(--ink-2);border:1px solid var(--line);border-radius:4px;padding:8px 13px;background:var(--panel);}
  /* ---- footer ---- */
  footer{padding:clamp(44px,6vw,72px) 0 64px;}
  .foot-grid{display:grid;grid-template-columns:1.4fr 1fr;gap:32px;align-items:start;}
  @media (max-width:640px){ .foot-grid{grid-template-columns:1fr;} }
  footer .fname{font-family:var(--serif);font-size:26px;color:var(--ink);font-weight:500;margin:0 0 14px;}
  footer .contact{font-family:var(--mono);font-size:13px;color:var(--muted);line-height:2;}
  footer .contact a{color:var(--water);}
  .colophon{font-family:var(--mono);font-size:11px;letter-spacing:.04em;color:var(--muted);margin-top:40px;padding-top:18px;border-top:1px solid var(--line);}
</style>
</head>
<body>
<!-- TOP BAR -->
<header class="bar">
  <div class="bar-inner">
    <div class="brand"><b>Sumon Datta</b>, Ph.D., E.I.</div>
    <nav class="menu" aria-label="Section navigation">
      <a href="#about">About</a>
      <a href="#research">Research</a>
      <a href="#grants">Grants</a>
      <a href="#publications">Publications</a>
      <a href="#lab">Lab</a>
      <a href="#cv">CV</a>
    </nav>
  </div>
</header>
<!-- HERO -->
<div class="hero">
  <div class="wrap hero-grid">
    <div>
      <p class="eyebrow">Irrigation Engineer · Oklahoma State University</p>
      <h1>Sumon&nbsp;Datta</h1>
      <div class="waterline" aria-hidden="true"></div>
      <p class="lede">Bringing in-situ sensors, soil-water modeling, and AI together to answer one deceptively simple question for growers: when to turn the water on, and when to turn it off.</p>
      <p class="role-line">
        <strong>Assistant Professor &amp; Irrigation Engineer</strong><br>
        <strong>Director</strong>, Irrigation Research Laboratory<br>
        Dept. of Biosystems &amp; Agricultural Engineering<br>
        215A Agricultural Hall, Stillwater, OK 74078
      </p>
      <div class="chips">
        <a class="chip solid" href="mailto:sumon.datta@okstate.edu">Email Dr. Datta</a>
        <a class="chip" href="#cv">Download CV</a>
        <a class="chip" href="https://irrigation.okstate.edu" target="_blank" rel="noopener">OASIS Tool ↗</a>
      </div>
    </div>
    <img class="portrait" src="https://res.cloudinary.com/allen-cld01/image/upload/f_webp,q_auto,w_300,h_300,c_fill,g_face,q_auto:best/fac-poc/qw0PCJ3FbYZMPWyddHv9sd9phmy1/ICBc1Jy-Q-hyJA9_" alt="Portrait of Sumon Datta, Ph.D., E.I." onerror="this.style.display='none'" />
  </div>
</div>
<!-- STAT LEDGER -->
<div class="ledger">
  <div class="grid">
    <div class="stat"><div class="num">$13.15<span>M</span></div><div class="lab">Research funding secured</div></div>
    <div class="stat"><div class="num">$1.85<span>M</span></div><div class="lab">Awarded to his program</div></div>
    <div class="stat"><div class="num">24</div><div class="lab">Peer-reviewed publications</div></div>
    <div class="stat"><div class="num">482</div><div class="lab">Citations · h-index 8</div></div>
    <div class="stat"><div class="num">59</div><div class="lab">Talks &amp; presentations</div></div>
    <div class="stat"><div class="num">15</div><div class="lab">Students mentored</div></div>
  </div>
</div>
<!-- SECTION: ABOUT -->
<section id="about">
  <div class="wrap">
    <p class="eyebrow">About</p>
    <h2 class="sec-title">Engineering water decisions for a drier future.</h2>
    <div class="prose">
      <p>Dr. Datta is an irrigation engineer with over ten years of post-bachelor experience in irrigation water management, specializing in both the quantity and quality of water across agricultural systems. His expertise lies in integrating smart sensors, modeling, and AI (machine and deep learning) to improve irrigation efficiency and decision-making, continuously building on prior knowledge while closing the gaps that remain through new methods and advanced data analytics.</p>
      <p>His overarching goal is to advance sustainable water management by bridging research, innovation, outreach, and education. In response to global water scarcity and a changing climate, he develops science-based, data-driven solutions that raise irrigation efficiency, conserve natural resources, and sustain long-term agricultural productivity — with an emphasis on precision irrigation scheduling through in-situ sensing, numerical modeling, and applied AI.</p>
      <p>Equally central is his commitment to teaching and mentorship. He works to equip future engineers and researchers with strong foundations in sustainable irrigation, critical thinking, and ethical responsibility, fostering an inclusive learning environment for the complex water challenges ahead.</p>
      <p>Collaboration runs through all of it. He partners with farmers, policymakers, industry, and academic peers to translate irrigation research into practice that benefits local communities and beyond — working toward a resilient agricultural future where water is managed wisely across environmental, economic, and food-security goals.</p>
    </div>
  </div>
</section>
<!-- SECTION: RESEARCH -->
<section id="research">
  <div class="wrap">
    <p class="eyebrow">Research Focus</p>
    <h2 class="sec-title">When should we turn watering on — and off?</h2>
    <div class="prose">
      <p>Dr. Datta's program monitors, studies, and models the bio-physical interactions inside cropping systems — particularly irrigated ones — to answer the central question of scientific irrigation scheduling. The work draws on in-situ sensors such as soil-moisture and canopy-temperature probes, satellite products including high-resolution imagery and OpenET, physically based models such as dual crop-coefficient soil-water balances and numerical schemes, and, increasingly, data-driven machine- and deep-learning approaches.</p>
      <p>His Extension efforts translate that science for the people who use it: agricultural producers and state agencies managing irrigation at field and regional scale, policymakers shaping water-allocation strategy, and the wider scientific community — all through application-based, stakeholder-driven projects that integrate research and Extension. Much of this work is grounded in the Southern Great Plains and the depleting Ogallala / High Plains Aquifer.</p>
    </div>
  </div>
</section>
<!-- SECTION: GRANTS -->
<section id="grants">
  <div class="wrap">
    <p class="eyebrow">Grants &amp; Contracts</p>
    <h2 class="sec-title">$13.15M secured across 22 awards.</h2>
    <p class="note">Amounts show the total award, with the portion to Dr. Datta's program in parentheses.</p>
    <p class="group-label">Oklahoma State University · 2023–present</p>
    <div class="entry"><div class="yr">2026</div><div><div class="ttl">Regional Forecasting of Evapotranspiration and Crop Water Demand Using OpenET, GraphCast Weather Predictions, and NISAR Soil Moisture Observations</div><div class="meta">NASA Water Resources Program · <span class="role">Co-PI</span> · 6/2026–5/2029 · <span class="amt">$900,000 ($234,825)</span></div></div></div>
    <div class="entry"><div class="yr">2026</div><div><div class="ttl">Scaling a Data-Driven Decision-Support Platform for Irrigation Scheduling to Improve Water Conservation in the Ogallala Aquifer Region</div><div class="meta">Ogallala Aquifer Program · <span class="role">Co-PI</span> · 1/2027–12/2028 · <span class="amt">$79,898 ($79,898)</span></div></div></div>
    <div class="entry"><div class="yr">2026</div><div><div class="ttl">Producer Attitudes Towards Groundwater Conservation Policies and Programs in the High Plains Aquifer Region</div><div class="meta">USDA NIFA AFRI Foundational &amp; Applied Sciences · <span class="role">Co-PI</span> · 5/2026–4/2029 · <span class="amt">$649,946 ($12,857)</span></div></div></div>
    <div class="entry"><div class="yr">2026</div><div><div class="ttl">Deployment and Testing of the Oklahoma Agricultural Scientific Irrigation Scheduler — OASIS Tool</div><div class="meta">Oklahoma Mesonet · <span class="role">Lead PI</span> · 10/2025–12/2027 · <span class="amt">$41,940 ($41,940)</span></div></div></div>
    <div class="entry"><div class="yr">2026</div><div><div class="ttl">Data-driven Canopy Temperature Modeling for Irrigated Cotton: Phase III — Field Testing &amp; OASIS Integration</div><div class="meta">Cotton Incorporated Core Research Program · <span class="role">Lead PI</span> · 1/2026–12/2026 · <span class="amt">$20,000 ($20,000)</span></div></div></div>
    <div class="entry"><div class="yr">2026</div><div><div class="ttl">Field-scale Sensor-informed Water Allocation for Sustainable Cotton Production in the Lugert-Altus Irrigation District</div><div class="meta">Cotton Incorporated — Oklahoma State Support Committee · <span class="role">Lead PI</span> · 1/2026–12/2026 · <span class="amt">$14,200 ($14,200)</span></div></div></div>
    <div class="entry"><div class="yr">2026</div><div><div class="ttl">Expanding the OASIS Tool to Kansas Farmers</div><div class="meta">Kansas Water Institute, Kansas State University · <span class="role">Lead PI</span> · 1/2026–12/2027 · <span class="amt">$46,094 ($46,094)</span></div></div></div>
    <div class="entry"><div class="yr">2026</div><div><div class="ttl">TxSIS: Texas Scientific Irrigation Scheduler — Expanding OASIS for West Texas Farmers</div><div class="meta">Davis College Water Center, Texas Tech University · <span class="role">Lead PI</span> · 1/2026–12/2027 · <span class="amt">$46,094 ($46,094)</span></div></div></div>
    <div class="entry"><div class="yr">2025</div><div><div class="ttl">Water Meters for Smart Savings and Conservation? Examining Water Meters as a Tool for Sustainable Irrigation in Oklahoma's Rural Communities</div><div class="meta">OSU Rural Renewal Initiative · <span class="role">Co-PI</span> · 1/2025–12/2027 · <span class="amt">$90,000 ($8,000)</span></div></div></div>
    <div class="entry"><div class="yr">2025</div><div><div class="ttl">Cost-effective Edge Sensors: Resourcing AI for Irrigation Networks (CES-RAIN)</div><div class="meta">OSU CEAT ERSF Seed Grant · <span class="role">Co-PI</span> · 8/2025–7/2026 · <span class="amt">$25,000 (in-kind)</span></div></div></div>
    <div class="entry"><div class="yr">2025</div><div><div class="ttl">Sustainable Irrigation and Climate Adaptation in the Southern High Plains: A Satellite-Enabled and Peer-Led Model</div><div class="meta">USDA NIFA AFRI Sustainable Agricultural Systems · <span class="role">Co-PI</span> · 2/2025–1/2030 · <span class="amt">$10,000,000 ($744,897)</span></div></div></div>
    <div class="entry"><div class="yr">2025</div><div><div class="ttl">Deployment of the Advanced Autonomous Oklahoma Irrigation Planner</div><div class="meta">Oklahoma Mesonet Products Development Fund · <span class="role">Lead PI</span> · 1/2025–9/2025 · <span class="amt">$18,000 ($18,000)</span></div></div></div>
    <div class="entry"><div class="yr">2025</div><div><div class="ttl">Data-driven Canopy Temperature Modeling for Irrigated Cotton: Phase II — Evaluation of Instrumentation Requirements</div><div class="meta">Cotton Incorporated Core Funding · <span class="role">Lead PI</span> · 1/2025–12/2025 · <span class="amt">$20,000 ($20,000)</span></div></div></div>
    <div class="entry"><div class="yr">2024</div><div><div class="ttl">Investigating Changes in Consumptive Water Use in Furrow and Subsurface Drip Irrigated Cotton Fields</div><div class="meta">USGS 104b · <span class="role">Lead PI</span> · 9/2024–8/2025 · <span class="amt">$24,995 ($24,995)</span></div></div></div>
    <div class="entry"><div class="yr">2024</div><div><div class="ttl">Data-driven Canopy Temperature Modeling for Irrigated Cotton: Phase I — Evaluation of State-of-the-art Approaches</div><div class="meta">Cotton Incorporated Core Funding · <span class="role">Lead PI</span> · 6/2024–12/2024 · <span class="amt">$13,998 ($13,998)</span></div></div></div>
    <div class="entry"><div class="yr">2024</div><div><div class="ttl">Building an Advanced Autonomous Oklahoma Irrigation Planner</div><div class="meta">Oklahoma Mesonet Products Development Fund · <span class="role">Lead PI</span> · 5/2024–12/2024 · <span class="amt">$18,000 ($18,000)</span></div></div></div>
    <div class="entry"><div class="yr">2024</div><div><div class="ttl">Oklahoma Master Irrigator Program and Ogallala Aquifer Study</div><div class="meta">Oklahoma Water Resources Board / Oklahoma Conservation Commission · <span class="role">Co-PI</span> · 1/2022–8/2024 · <span class="amt">$60,081 ($19,734)</span></div></div></div>
    <div class="entry"><div class="yr">2024</div><div><div class="ttl">Comparison of Consumptive Water Use of Different Irrigation Systems in the Lugert-Altus Irrigation District</div><div class="meta">2024 OSU Buchanan Undergraduate Research Fund · <span class="role">Lead PI</span> · 1/2024–5/2024 · <span class="amt">$2,000 ($2,000)</span></div></div></div>
    <div class="entry"><div class="yr">2024</div><div><div class="ttl">Annual Funding for Irrigation System Audits — Oklahoma Master Irrigator Program &amp; Mobile Irrigation Lab</div><div class="meta">Oklahoma Conservation Commission / Oklahoma Water Resources Board · <span class="role">Co-PI</span> · 1/2024–12/2024 · <span class="amt">$31,622 ($7,866)</span></div></div></div>
    <p class="group-label">University of Maine · 2022–2023</p>
    <div class="entry"><div class="yr">2023</div><div><div class="ttl">Piloting Innovation in Wild Blueberry: Team WILD — Wild Blueberry Innovations Led by Data</div><div class="meta">Maine Technology Institute · <span class="role">Lead PI</span> · 5/2023–12/2026 · <span class="amt">$1,000,000 ($473,836)</span></div></div></div>
    <div class="entry"><div class="yr">2023</div><div><div class="ttl">Socio-Economic and Environmental Analyses for Using Woody Biochar to Conserve Water and Sustain Agriculture in Maine</div><div class="meta">University of Maine Water Resources Research Institute · <span class="role">Co-PI</span> · 9/2023–8/2024 · <span class="amt">$40,000 ($2,000)</span></div></div></div>
    <p class="group-label">As a Graduate Student · Oklahoma State University</p>
    <div class="entry"><div class="yr">2018</div><div><div class="ttl">Conserving Agricultural Water Resources Using Smart Technologies</div><div class="meta">USGS 104b · <span class="role">Co-PI</span> · 9/2018–8/2019 · <span class="amt">$5,000 ($5,000)</span></div></div></div>
  </div>
</section>
<!-- SECTION: PUBLICATIONS -->
<section id="publications">
  <div class="wrap">
    <p class="eyebrow">Publications</p>
    <h2 class="sec-title">Peer-reviewed journal articles &amp; proceedings.</h2>
    <ol class="pubs">
      <li><div><span class="pub-t">Canopy Temperature Sensor Data Optimization for Irrigation Scheduling.</span> <span class="pub-a">Meadi, S., Kalayambakam Janardhan, A. Y., Datta, S., &amp; Das, H. (2026).</span><div class="pub-v">2026 IEEE DCAS Conference, Dallas, TX · DOI forthcoming</div></div></li>
      <li><div><span class="pub-t">Data-driven Modeling of Soil Moisture at Irrigated Fields.</span> <span class="pub-a">Kalayambakam Janardhan, A. Y., Datta, S., Crick, C., Taghvaeian, S., &amp; Kundu, P. K. (2026).</span><div class="pub-v">2026 IEEE DCAS Conference, Dallas, TX · DOI forthcoming</div></div></li>
      <li><div><span class="pub-t">Evapotranspiration Terminology and Definitions.</span> <span class="pub-a">DeJonge, K. C., Allen, R. G., Kilic, A., … Datta, S., … et al. (2025).</span><div class="pub-v">ASCE Journal of Irrigation &amp; Drainage Engineering, 151(5) · <a href="https://doi.org/10.1061/jidedh.ireng-10491" target="_blank" rel="noopener">doi:10.1061/jidedh.ireng-10491</a></div></div></li>
      <li><div><span class="pub-t">Irrigation and Water Conservation Practices of Surface-Irrigated Croplands in West and South Regions of the U.S.</span> <span class="pub-a">Datta, S., Taghvaeian, S., Sibley, M., Gholson, D. M., Yost, M., Long, M. A., Bali, K. M., Zaccaria, D., Davis-Conger, S. L., &amp; Ritchie, L. A. (2025).</span><div class="pub-v">Journal of the ASABE, 68(3), 503–511 · <a href="https://doi.org/10.13031/ja.16257" target="_blank" rel="noopener">doi:10.13031/ja.16257</a></div></div></li>
      <li><div><span class="pub-t">Multi-model Ensemble Mapping of Irrigated Areas Using Remote Sensing, Machine Learning, and Ground Truth Data.</span> <span class="pub-a">Akbar, M. U., Mirchi, A., Arshad, A., Alian, S., Mehata, M., Taghvaeian, S., Khodkar, K., Kettner, J., Datta, S., &amp; Wagner, K. (2025).</span><div class="pub-v">Agricultural Water Management, 312, 109416 · <a href="https://doi.org/10.1016/j.agwat.2025.109416" target="_blank" rel="noopener">doi:10.1016/j.agwat.2025.109416</a></div></div></li>
      <li><div><span class="pub-t">Water Dynamics of Variably Irrigated Pecan Trees in Oklahoma.</span> <span class="pub-a">Kettner, J., Taghvaeian, S., Pokhrel, N., Mirchi, A., Zhang, L., Mehata, M., &amp; Datta, S. (2025).</span><div class="pub-v">Journal of the American Pomological Society, 78(2), 85–99 · <a href="https://doi.org/10.71318/tak32v50" target="_blank" rel="noopener">doi:10.71318/tak32v50</a></div></div></li>
      <li><div><span class="pub-t">Rice Cultivation Under Raised Bed Conserving Irrigation Technique: Effects of Bed Width on Soil Wetness and Yield.</span> <span class="pub-a">Munmun, T. H., Islam, M. T., Rahman, M. M., Islam, M. A., Datta, S., Das, N., Akter, J., &amp; Adham, A. K. M. (2024).</span><div class="pub-v">Paddy and Water Environment · <a href="https://doi.org/10.1007/s10333-023-00957-3" target="_blank" rel="noopener">doi:10.1007/s10333-023-00957-3</a></div></div></li>
      <li><div><span class="pub-t">Soil Water Sensors for Irrigation Scheduling in the United States: A Systematic Review of Literature.</span> <span class="pub-a">Datta, S., &amp; Taghvaeian, S. (2023).</span><div class="pub-v">Agricultural Water Management, 278, 108148 · <a href="https://doi.org/10.1016/j.agwat.2023.108148" target="_blank" rel="noopener">doi:10.1016/j.agwat.2023.108148</a></div></div></li>
      <li><div><span class="pub-t">Effects of Soil Data Accuracy on Outputs of Irrigation Scheduling Tools.</span> <span class="pub-a">Mehata, M., Datta, S., Taghvaeian, S., Mirchi, A., &amp; Moriasi, D. N. (2023).</span><div class="pub-v">Journal of the ASABE, 66(3), 677–687 · <a href="https://doi.org/10.13031/ja.15323" target="_blank" rel="noopener">doi:10.13031/ja.15323</a></div></div></li>
      <li><div><span class="pub-t">Performance of a Multi-sensor Capacitance Probe in Estimating Soil Water Content and Field Capacity.</span> <span class="pub-a">Mehata, M., Datta, S., Taghvaeian, S., Ochsner, T., Mirchi, A., &amp; Moriasi, D. N. (2023).</span><div class="pub-v">Journal of the ASABE, 66(2), 253–261 · <a href="https://doi.org/10.13031/ja.15416" target="_blank" rel="noopener">doi:10.13031/ja.15416</a></div></div></li>
      <li><div><span class="pub-t">Simulating Soil Water Content of Irrigated Fields: The Effects of Variable Soil Data and Root Water Uptake Distribution.</span> <span class="pub-a">Mehata, M., Datta, S., Taghvaeian, S., Mirchi, A., Moriasi, D., &amp; Starks, P. J. (2022).</span><div class="pub-v">Journal of the ASABE, 65(3), 587–597 · <a href="https://doi.org/10.13031/ja.14856" target="_blank" rel="noopener">doi:10.13031/ja.14856</a></div></div></li>
      <li><div><span class="pub-t">Quantifying Water Fluxes of Irrigated Fields in an Agricultural Watershed in Oklahoma.</span> <span class="pub-a">Datta, S., Mehata, M., Taghvaeian, S., Moriasi, D., &amp; Starks, P. J. (2021).</span><div class="pub-v">ASCE Journal of Irrigation &amp; Drainage Engineering, 147(7) · <a href="https://doi.org/10.1061/(ASCE)IR.1943-4774.0001570" target="_blank" rel="noopener">doi:10.1061/(ASCE)IR.1943-4774.0001570</a></div></div></li>
      <li><div><span class="pub-t">High Plains Aquifer — State of Affairs of Irrigated Agriculture and the Role of Irrigation in the Sustainability Paradigm.</span> <span class="pub-a">Ajaz, A., Datta, S., &amp; Stoodley, S. (2020).</span><div class="pub-v">Sustainability, 12(9), 3714 · <a href="https://doi.org/10.3390/su12093714" target="_blank" rel="noopener">doi:10.3390/su12093714</a></div></div></li>
      <li><div><span class="pub-t">Geospatial Data Assimilation and Mapping Groundwater Vulnerability in the High Plains Aquifer Using the DRASTIC Model.</span> <span class="pub-a">Datta, S., &amp; Ajaz, A. (2019).</span><div class="pub-v">Fundamental and Applied Agriculture, 4(3), 933–942 · <a href="https://doi.org/10.5455/faa.53506" target="_blank" rel="noopener">doi:10.5455/faa.53506</a></div></div></li>
      <li><div><span class="pub-t">Suitability of Power-plant Disposed Water for Irrigation of the Ashuganj Agro-Irrigation Project in Bangladesh.</span> <span class="pub-a">Rana, M. M., Islam, M. T., Datta, S., Rahman, M. M., &amp; Adham, A. K. M. (2019).</span><div class="pub-v">Progressive Agriculture, 30(1), 113–124 · <a href="https://doi.org/10.3329/pa.v30i1.42218" target="_blank" rel="noopener">doi:10.3329/pa.v30i1.42218</a></div></div></li>
      <li><div><span class="pub-t">Quantification and Characterization of Particulate Matter Generated from Unpaved Roads in the Oil Development Area of Western North Dakota.</span> <span class="pub-a">Datta, S., Rahman, S., Borhan, M. S., Saini-Eidukat, B., Cihacek, L., &amp; Ringwall, K. (2019).</span><div class="pub-v">Transactions of the ASABE, 62(3), 615–625 · <a href="https://doi.org/10.13031/trans.13169" target="_blank" rel="noopener">doi:10.13031/trans.13169</a></div></div></li>
      <li><div><span class="pub-t">Impacts of Irrigation Termination on Cotton Yield and Irrigation Requirement.</span> <span class="pub-a">Masasi, B., Taghvaeian, S., Boman, R., &amp; Datta, S. (2019).</span><div class="pub-v">Agriculture, 9(2), 39 · <a href="https://doi.org/10.3390/agriculture9020039" target="_blank" rel="noopener">doi:10.3390/agriculture9020039</a></div></div></li>
      <li><div><span class="pub-t">Performance Assessment of Five Different Soil Moisture Sensors under Irrigated Field Conditions in Oklahoma.</span> <span class="pub-a">Datta, S., Taghvaeian, S., Ochsner, T., Moriasi, D., Gowda, P., &amp; Steiner, J. (2018).</span><div class="pub-v">Sensors, 18(11), 3786 · <a href="https://doi.org/10.3390/s18113786" target="_blank" rel="noopener">doi:10.3390/s18113786</a></div></div></li>
      <li><div><span class="pub-t">Waste Generation and Management Practices in BSCIC, Mymensingh.</span> <span class="pub-a">Rahman, S., Datta, S., &amp; Islam, S. (2014).</span><div class="pub-v">Journal of Environmental Science and Natural Resources, 7(1), 47–51 · <a href="https://doi.org/10.3329/jesnr.v7i1.22143" target="_blank" rel="noopener">doi:10.3329/jesnr.v7i1.22143</a></div></div></li>
    </ol>
    <p class="group-label">Peer-reviewed Extension Factsheets</p>
    <ol class="pubs">
      <li><div><span class="pub-t">Using Soil Moisture Trend Values from Moisture Sensors for Irrigation Decisions.</span> <span class="pub-a">Sharma, S., Wagner, K., &amp; Datta, S. (2025).</span><div class="pub-v">Oklahoma Cooperative Extension Service · accepted, number pending</div></div></li>
      <li><div><span class="pub-t">Determining Field Capacity Using Continuous Soil Water Content Data.</span> <span class="pub-a">Krueger, E. S., Ashrafi, A., Ochsner, T., &amp; Datta, S. (2025).</span><div class="pub-v">Oklahoma Cooperative Extension Service · PSS-2403</div></div></li>
      <li><div><span class="pub-t">Irrigated Agriculture in Oklahoma.</span> <span class="pub-a">Datta, S., Kettner, J., Mehata, M., &amp; Taghvaeian, S. (2025).</span><div class="pub-v">Oklahoma Cooperative Extension Service · BAE-1530</div></div></li>
      <li><div><span class="pub-t">Understanding the Results of Master Irrigator Center Pivot Energy Efficiency Tests.</span> <span class="pub-a">Frazier, S., &amp; Datta, S. (2024).</span><div class="pub-v">Oklahoma Cooperative Extension Service · BAE-1411</div></div></li>
      <li><div><span class="pub-t">Understanding Soil Water Content and Thresholds for Irrigation Management.</span> <span class="pub-a">Datta, S., Taghvaeian, S., &amp; Stivers, J. (2017).</span><div class="pub-v">Oklahoma Cooperative Extension Service · BAE-1537</div></div></li>
    </ol>
  </div>
</section>
<!-- SECTION: LAB -->
<section id="lab">
  <div class="wrap">
    <p class="eyebrow">The Lab</p>
    <h2 class="sec-title">Irrigation Research Laboratory.</h2>
    <p class="note">Students directly advised by Dr. Datta in Biosystems &amp; Agricultural Engineering.</p>
    <p class="group-label">Current Students</p>
    <div class="cards">
      <div class="card"><h4>Jacob Kettner</h4><div class="deg">Ph.D. Candidate, BAE · GRA/GTA · Fall 2024–2028</div><p>Sensitivity analysis of model inputs — soil data, current and forecasted weather, and crop-specific parameters — on irrigation scheduling for major crops in the Southern Great Plains, using soil-water-balance models such as pyfao56.</p></div>
      <div class="card"><h4>Alok Pandit</h4><div class="deg">M.S., BAE · GRA · Spring 2024–Summer 2026</div><p>Feasibility of using satellite products such as OpenET to quantify crop water use and evapotranspiration for irrigation water management in Oklahoma and beyond.</p></div>
      <div class="card"><h4>Abinava Yeshwanth Kalayambakam Janardhan</h4><div class="deg">Ph.D., BAE · GRA · Spring 2026–Fall 2029</div><p>Application of AI to soil-moisture-based irrigation management, including machine- and deep-learning estimation of multi-depth soil moisture in irrigated fields. (Completed his M.S. in Computer Science in the group.)</p></div>
      <div class="card"><h4>Satheesh Meadi</h4><div class="deg">Ph.D., BAE · GRA · Spring 2026–Fall 2029</div><p>Development of data-driven, sensor-enhanced machine- and deep-learning algorithms to predict canopy temperature for irrigated cotton.</p></div>
    </div>
    <p class="group-label">Past Students</p>
    <div class="cards">
      <div class="card"><h4>Tatumn Kennedy</h4><div class="deg">B.S., BAE · Undergraduate RA · Spring 2024–Spring 2026</div><p>Quantifying crop water use among major irrigation systems in Southwest Oklahoma and identifying relative-humidity-limited areas for canopy-temperature-based scheduling.</p><div class="status">Graduated; now an M.S. student in OSU BAE.</div></div>
      <div class="card"><h4>Palash Kumar Kundu</h4><div class="deg">M.S., BAE · GRA · Spring 2024–Summer 2025</div><p>Data-driven modeling of canopy temperature for irrigated cotton to support an irrigation scheduling tool.</p><div class="status">Graduated; now a Ph.D. student at Michigan State University.</div></div>
      <div class="card"><h4>Gillian Quellar</h4><div class="deg">B.S., BAE · Undergraduate RA · Spring 2024</div><p>Preliminary results quantifying evapotranspiration in Southwest Oklahoma using the OpenET platform.</p></div>
    </div>
  </div>
</section>
<!-- SECTION: TEACHING -->
<section id="teaching">
  <div class="wrap">
    <p class="eyebrow">Teaching</p>
    <h2 class="sec-title">Courses developed &amp; taught.</h2>
    <div class="entry"><div class="yr">2023–25</div><div><div class="ttl">AST 4203 / 5200 — Agricultural Water Management</div><div class="meta">Oklahoma State University · Fall 2023, 2024, 2025 · Undergraduate &amp; graduate</div><div class="desc">An introduction to the theory and application of agricultural water management. Redesigned across offerings to add hands-on labs, a research-station field tour, and frequent low-stakes assessment.</div></div></div>
    <div class="entry"><div class="yr">2025</div><div><div class="ttl">BAE 5030 — Advanced Techniques in Irrigation Water Management</div><div class="meta">Oklahoma State University · Spring 2025 · Graduate · Developed by Dr. Datta</div><div class="desc">A new graduate course built from the ground up, covering soil-moisture and canopy-temperature sensors, soil-water-balance models, and crop models for advanced irrigation water management.</div></div></div>
  </div>
</section>
<!-- SECTION: BACKGROUND -->
<section id="background">
  <div class="wrap">
    <p class="eyebrow">Background</p>
    <div class="two-col">
      <div class="tl">
        <h3>Experience</h3>
        <div class="tl-item"><div class="tl-when">2023 — present</div><div class="tl-what">Assistant Professor &amp; Irrigation Engineer</div><div class="tl-where">Biosystems &amp; Agricultural Engineering, Oklahoma State University</div><div class="tl-note">75% Research · 25% Teaching</div></div>
        <div class="tl-item"><div class="tl-when">2022 — 2023</div><div class="tl-what">Assistant Extension Professor &amp; Extension Agricultural Engineer</div><div class="tl-where">Cooperative Extension, University of Maine, Orono, ME</div><div class="tl-note">100% Extension</div></div>
        <div class="tl-item"><div class="tl-when">2020 — 2022</div><div class="tl-what">Postdoctoral Fellow</div><div class="tl-where">Biosystems &amp; Agricultural Engineering, Oklahoma State University</div></div>
        <div class="tl-item"><div class="tl-when">2017 — 2020</div><div class="tl-what">Graduate Research Assistant</div><div class="tl-where">Biosystems &amp; Agricultural Engineering, Oklahoma State University</div></div>
        <div class="tl-item"><div class="tl-when">2015 — 2016</div><div class="tl-what">Graduate Research Assistant</div><div class="tl-where">Agricultural &amp; Biosystems Engineering, North Dakota State University</div></div>
        <div class="tl-item"><div class="tl-when">2013 — 2014</div><div class="tl-what">Undergraduate Research Assistant</div><div class="tl-where">Agricultural Engineering &amp; Technology, Bangladesh Agricultural University</div></div>
      </div>
      <div class="tl">
        <h3>Education</h3>
        <div class="tl-item"><div class="tl-when">Ph.D. · 2020</div><div class="tl-what">Biosystems &amp; Agricultural Engineering</div><div class="tl-where">Oklahoma State University · Advisor: Dr. Saleh Taghvaeian</div><div class="tl-note">Dissertation: Measurement and Modeling of Soil Moisture for Irrigation Management</div></div>
        <div class="tl-item"><div class="tl-when">M.S. · 2016</div><div class="tl-what">Agricultural &amp; Biosystems Engineering</div><div class="tl-where">North Dakota State University · Advisor: Dr. Shafiqur Rahman</div><div class="tl-note">Thesis: Quantification and Characterization of Particulate Matter from Unpaved Roads in the Oil Development Area of Western North Dakota</div></div>
        <div class="tl-item"><div class="tl-when">B.S. · 2014</div><div class="tl-what">Agricultural Engineering</div><div class="tl-where">Bangladesh Agricultural University · Advisor: Md. Siddikur Rahman</div><div class="tl-note">Project: Waste Generation and Management Practices in BSCIC, Mymensingh</div></div>
        <div class="tl-item"><div class="tl-when">Certification</div><div class="tl-what">Engineer Intern (E.I.), Maine</div><div class="tl-where">License #EI8079</div></div>
      </div>
    </div>
  </div>
</section>
<!-- SECTION: TOOL / OASIS -->
<section id="tool">
  <div class="wrap">
    <div class="feature">
      <p class="eyebrow">Tools Developed</p>
      <h3>OASIS — Oklahoma Agricultural Scientific Irrigation Scheduler</h3>
      <p class="ftmeta">Built from the ground up · Dual crop-coefficient soil-water-balance model · $1.15M in development &amp; deployment funding</p>
      <p>A new irrigation scheduling tool for Oklahoma growers — versatile enough to apply across the U.S. — that estimates crop water use (evapotranspiration) and lets users schedule irrigations from Oklahoma Mesonet weather data and in-field inputs. Growing-degree-day methods, soil-water-data infusion, and OpenET integration are on the horizon, and the tool is being expanded to Kansas and Texas. Beta release is expected in summer 2026.</p>
      <a class="chip" href="https://irrigation.okstate.edu" target="_blank" rel="noopener">Visit irrigation.okstate.edu ↗</a>
    </div>
  </div>
</section>
<!-- SECTION: JOIN -->
<section id="join">
  <div class="wrap">
    <div class="join">
      <p class="eyebrow">Interested in Joining the Group?</p>
      <h3>The lab is growing to five Ph.D. students by summer 2026.</h3>
      <p>Dr. Datta is always looking for talented, self-motivated individuals with a B.S. or M.S. (conferred or all-but-thesis) in Agricultural Engineering, Biosystems Engineering, or Computer Science — Computer Science applicants should plan to take the FE exam before applying. The group prioritizes students joining at the Ph.D. level.</p>
      <p>If you meet these requirements, email a CV and a cover letter explaining how your expertise <strong>specifically fits</strong> the group's priorities. Only shortlisted applicants will be contacted.</p>
      <div class="chips" style="margin-top:6px"><a class="chip solid" href="mailto:sumon.datta@okstate.edu?subject=Prospective%20PhD%20student%20%E2%80%94%20Irrigation%20Research%20Laboratory">Email with CV &amp; cover letter</a></div>
    </div>
  </div>
</section>
<!-- SECTION: SPONSORS -->
<section id="sponsors">
  <div class="wrap">
    <p class="eyebrow">Sponsors &amp; Funders</p>
    <h2 class="sec-title">With support from</h2>
    <div class="sponsors">
      <span>USDA NIFA</span>
      <span>Cotton Incorporated</span>
      <span>Oklahoma Mesonet</span>
      <span>USGS</span>
      <span>NASA</span>
      <span>Ogallala Aquifer Program</span>
      <span>OSU Rural Renewal Initiative</span>
      <span>Oklahoma Water Resources Board</span>
      <span>Oklahoma Conservation Commission</span>
      <span>OSU CEAT</span>
      <span>OAES</span>
      <span>OCES</span>
    </div>
  </div>
</section>
<!-- FOOTER -->
<footer id="cv">
  <div class="wrap">
    <div class="foot-grid">
      <div>
        <p class="fname">Sumon Datta, Ph.D., E.I.</p>
        <div class="chips">
          <a class="chip solid" href="mailto:sumon.datta@okstate.edu">Email</a>
          <!-- Replace the href below with your own hosted CV file once the site is live -->
          <a class="chip" href="https://firebasestorage.googleapis.com/v0/b/faculty-poc.appspot.com/o/qw0PCJ3FbYZMPWyddHv9sd9phmy1%2Fpublic%2FCV_SumonDatta_20260516.pdf?alt=media&token=1291faf9-1aba-45d7-a305-d1889d3e9205" target="_blank" rel="noopener">Curriculum Vitae (PDF)</a>
          <a class="chip" href="https://irrigation.okstate.edu" target="_blank" rel="noopener">OASIS Tool</a>
        </div>
      </div>
      <div>
        <div class="contact">
          Director, Irrigation Research Laboratory<br>
          Biosystems &amp; Agricultural Engineering<br>
          215A Agricultural Hall<br>
          Oklahoma State University<br>
          Stillwater, OK 74078<br>
          <a href="mailto:sumon.datta@okstate.edu">sumon.datta@okstate.edu</a><br>
          +1 (405) 744-5403
        </div>
      </div>
    </div>
    <div class="colophon">© 2026 Sumon Datta, Ph.D., E.I. · Irrigation Research Laboratory, Oklahoma State University</div>
  </div>
</footer>
</body>
</html>
0 commit comments
Comments
0
 (0)
Comment
You're not receiving notifications from this thread.

There are no files selected for viewing
