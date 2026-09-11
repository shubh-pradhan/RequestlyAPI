<!DOCTYPE html>

<html lang="en">
<head>
<meta charset="utf-8"/>
<meta content="width=device-width, initial-scale=1.0" name="viewport"/>
<title>Vietnam — First Anniversary</title>
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
:root{
  --navy:#0B1F2E;--navy-mid:#152D40;--gold:#C8922A;--gold-light:#E8B554;
  --linen:#F6F3EE;--paper:#FBF9F4;--paper-soft:#F3EFE7;--ink:#1A1A1A;--ink-mid:#4A4540;--ink-light:#5C564E;
  --divider:#D8D0C4
}
html{font-size:18px;scroll-behavior:smooth}
body{
  font-family:'DejaVu Sans',Helvetica,sans-serif;background:var(--linen);color:var(--ink);
  line-height:1.4;-webkit-font-smoothing:antialiased
}

/* COVER */
.hero{
  margin-left:158px;min-height:100vh;background:var(--navy);display:flex;flex-direction:column;
  justify-content:center;align-items:center;text-align:center;padding:70px 28px 58px;
  position:relative;overflow:hidden;transition:min-height .45s ease,padding .45s ease
}
.hero::before{
  content:'';position:absolute;inset:0;pointer-events:none;
  background:radial-gradient(ellipse at 60% 40%,rgba(200,146,42,.12) 0%,transparent 65%),
             radial-gradient(ellipse at 20% 80%,rgba(122,158,130,.08) 0%,transparent 55%)
}
.hero>*{position:relative}
.hero-eyebrow{font-weight:300;font-size:.68rem;letter-spacing:.24em;color:var(--gold-light);text-transform:uppercase;margin-bottom:22px}
.hero-title{font-family:'Liberation Serif',Georgia,serif;font-size:clamp(2.5rem,7vw,5rem);font-weight:400;color:#fff;line-height:1.05;margin-bottom:8px}
.hero-title em{font-style:italic;color:var(--gold-light)}
.hero-subtitle{font-family:'Liberation Serif',Georgia,serif;font-size:clamp(.9rem,2.2vw,1.25rem);font-style:italic;color:rgba(255,255,255,.55);margin-bottom:42px}
.hero-meta{display:flex;flex-wrap:wrap;justify-content:center}
.hero-meta-item{margin:7px 22px;text-align:center}
.hero-meta-label{font-size:.58rem;letter-spacing:.18em;text-transform:uppercase;color:rgba(255,255,255,.6);display:block;margin-bottom:3px}
.hero-meta-value{font-size:.78rem;color:rgba(255,255,255,.82)}
.hero-divider{width:38px;height:1px;background:var(--gold);opacity:.55;margin:30px auto 0}

/* MAIN NAV */
.main-nav{
  position:fixed;left:0;top:0;bottom:0;width:158px;z-index:60;background:var(--navy-mid);
  border-right:1px solid rgba(255,255,255,.08);display:flex;flex-direction:column;
  justify-content:center;padding:24px 10px;gap:3px
}
.main-nav button{
  appearance:none;border:0;border-left:2px solid transparent;background:transparent;
  color:rgba(255,255,255,.68);font:inherit;cursor:pointer;padding:13px 10px 12px;
  display:flex;flex-direction:column;justify-content:center;align-items:flex-start;gap:4px;
  text-align:left;border-radius:0 5px 5px 0;transition:background .2s,color .2s,border-color .2s
}
.main-nav button:hover{background:rgba(255,255,255,.045);color:#fff}
.main-nav button.active{background:rgba(200,146,42,.12);color:var(--gold-light);border-left-color:var(--gold-light)}
.nav-name{font-family:'Liberation Serif',Georgia,serif;font-size:.95rem;letter-spacing:.02em;line-height:1.05;white-space:nowrap}
.nav-date{font-size:.52rem;letter-spacing:.1em;text-transform:uppercase;color:rgba(255,255,255,.38);white-space:nowrap}
.main-nav button.active .nav-date{color:rgba(232,181,84,.72)}

/* COMPACT COVER AFTER FIRST SELECTION */
body.has-selection .hero{
  min-height:150px;padding:25px 20px 22px;justify-content:center
}
body.has-selection .hero-eyebrow{font-size:.54rem;margin-bottom:7px}
body.has-selection .hero-title{font-size:clamp(1.75rem,4vw,2.55rem);margin-bottom:2px}
body.has-selection .hero-subtitle{font-size:.72rem;margin-bottom:8px}
body.has-selection .hero-meta{display:none}
body.has-selection .hero-divider{margin-top:8px;width:25px}

/* CONTENT SHELL */
@media(min-width:761px){
  .hero,.content-shell{margin-left:158px;}
  .content-shell{max-width:calc(1120px + 56px);}
}
.content-shell{max-width:1120px;margin:0 auto;padding:38px 28px 64px}
.location-panel{display:none!important}
.location-panel.active{display:block!important}
.summary-panel{display:none!important}
.summary-panel.active{display:block!important}

/* SUMMARY */
.summary-intro{text-align:center;margin:4px auto 24px;max-width:760px}
.summary-intro h2{
  font-family:'Liberation Serif',Georgia,serif;font-size:1.7rem;font-weight:400;color:var(--ink);margin-bottom:5px
}
.summary-intro p{font-size:.76rem;color:var(--ink-light)}
.summary-overview{
  display:grid;grid-template-columns:repeat(2,minmax(0,1fr));gap:18px
}
.summary-location{
  background:linear-gradient(145deg,var(--paper) 0%,#F8F4EC 100%);border:1px solid var(--divider);border-radius:10px;padding:22px 23px;min-width:0
}
.summary-location h3{
  font-family:'Liberation Serif',Georgia,serif;font-size:1.18rem;font-weight:500;color:var(--ink);
  margin-bottom:3px
}
.summary-dates{font-size:.62rem;letter-spacing:.1em;text-transform:uppercase;color:var(--gold);margin-bottom:9px}
.summary-hotel{
  font-family:'Liberation Serif',Georgia,serif;font-size:.92rem;font-style:italic;color:var(--ink-mid);
  padding-bottom:11px;margin-bottom:7px;border-bottom:1px solid var(--divider)
}
.summary-items{display:grid;gap:4px}
.summary-items div{display:flex;justify-content:space-between;gap:12px;font-size:.71rem;color:var(--ink-mid);padding:2px 0}
.summary-items div span:first-child{color:var(--ink);font-weight:500}
.summary-items div span:last-child{font-size:.62rem;color:var(--ink-light);white-space:nowrap}

/* LOCATION TITLE + SECONDARY DAY NAV */
.location-heading{text-align:center;margin:2px auto 18px}
.location-heading h2{
  font-family:'Liberation Serif',Georgia,serif;font-size:1.75rem;font-weight:400;color:var(--ink)
}
.location-heading p{font-size:.68rem;color:var(--ink-light);margin-top:2px}
.day-tabs{
  width:100%;display:flex;border:1px solid var(--divider);border-radius:8px;overflow:hidden;
  background:var(--paper);margin:0 0 26px
}
.day-tabs button{
  flex:1;min-height:54px;appearance:none;border:0;border-right:1px solid var(--divider);
  background:var(--paper);color:var(--ink-mid);font:inherit;font-size:.69rem;cursor:pointer;padding:9px 12px;
  transition:background .2s,color .2s
}
.day-tabs button:last-child{border-right:0}
.day-tabs button:hover{background:#f4f0e8;color:var(--ink)}
.day-tabs button.active{background:var(--navy);color:#fff}
.day-panel{display:none!important}
.day-panel.active{display:block!important}

/* DAILY ITINERARY */
.day{margin:0 auto;display:grid;grid-template-columns:155px 1fr;gap:0 32px;max-width:900px}
.day-sidebar{padding-top:4px;align-self:start}
.day-label{font-family:'Liberation Serif',Georgia,serif;font-size:1rem;font-weight:500;color:var(--ink);line-height:1.2;margin-bottom:7px}
.day-date{font-size:.9rem;color:var(--gold);font-weight:700;line-height:1.25}
.day-line{width:22px;height:1px;background:var(--gold);margin-top:13px;opacity:.6}
.day.anniversary .day-sidebar{background:var(--navy);border-radius:8px;padding:17px 13px}
.day.anniversary .day-label{color:#fff}
.day.anniversary .day-date{color:var(--gold-light)}
.day.anniversary .day-line{background:var(--gold);opacity:1}
.anniversary-badge{
  display:inline-block;margin-top:9px;font-size:.54rem;letter-spacing:.13em;text-transform:uppercase;
  color:var(--gold-light);border:1px solid rgba(200,146,42,.4);padding:3px 6px;border-radius:2px
}
.stop{
  padding:8px 0;border-bottom:1px solid var(--divider);display:grid;grid-template-columns:82px 1fr;
  gap:0 18px;align-items:start
}
.stop:last-child{border-bottom:none}
.stop-time{font-size:.65rem;font-weight:500;color:var(--ink-mid);padding-top:3px;white-space:nowrap}
.stop-name{font-family:'Liberation Serif',Georgia,serif;font-size:.94rem;font-weight:500;color:var(--ink);margin-bottom:4px;line-height:1.3}
.stop-desc{font-size:.73rem;color:var(--ink-mid);line-height:1.45;font-weight:300}
.stop-tag{
  display:inline-block;margin-top:8px;font-size:.52rem;letter-spacing:.12em;text-transform:uppercase;
  padding:2px 6px;border-radius:20px;font-weight:500
}
.tag-food{background:#FEF3E2;color:#A0620A}.tag-culture{background:#EDF0FE;color:#3D5AE8}
.tag-nature{background:#EEF6EE;color:#3A7A3A}.tag-travel{background:#F2F2F2;color:#555}
.tag-stay{background:#FDE8F5;color:#8B2E7A}.tag-key{background:var(--navy);color:var(--gold-light)}
.stop.highlight{background:var(--navy);margin:0 -20px;padding:18px 20px;border-radius:8px;border-bottom:none}
.stop.highlight .stop-time{color:rgba(255,255,255,.55)}
.stop.highlight .stop-name{color:var(--gold-light);font-size:1rem}
.stop.highlight .stop-desc{color:rgba(255,255,255,.72)}
.stop.free{background:#EFEAE0;margin:0 -20px;padding:15px 20px;border-radius:8px;border-bottom:none}
.stop.free .stop-name{font-style:italic}

@media(max-width:760px){
  .main-nav{position:sticky;top:0;left:auto;bottom:auto;width:100%;height:66px;z-index:50;display:flex;flex-direction:row;justify-content:flex-start;overflow-x:auto;overflow-y:hidden;padding:0;background:var(--navy-mid);border-right:0;border-bottom:1px solid rgba(255,255,255,.08);gap:0}
  .main-nav button{flex:0 0 auto;min-height:66px;min-width:112px;align-items:center;text-align:center;border-left:0;border-right:1px solid rgba(255,255,255,.08);border-radius:0;padding:9px 12px}
  .main-nav button.active{border-left:0;border-bottom:2px solid var(--gold-light)}
  .content-shell{margin-left:0;padding:28px 16px 48px}
  .summary-overview{grid-template-columns:1fr}
  .day{grid-template-columns:1fr;gap:0}
  .day-sidebar{position:static;margin-bottom:16px}
  .day.anniversary .day-sidebar{padding:14px}
  .stop{grid-template-columns:68px 1fr;gap:0 12px}
  .stop.highlight,.stop.free{margin:0 -8px;padding-left:8px;padding-right:8px}
  .day-tabs{overflow-x:auto}
  .day-tabs button{white-space:nowrap;min-width:125px}
}
@media(max-width:430px){
  .hero{margin-left:0;padding-left:16px;padding-right:16px}
  .hero-meta-item{margin:6px 10px}
  .nav-name{font-size:.82rem}
  .nav-date{font-size:.5rem}
}

/* Stronger, clearer day navigation */
.day-tabs{
  position:relative;
  margin:8px 0 34px;
  padding:5px;
  gap:5px;
  border:2px solid var(--gold);
  border-radius:10px;
  background:var(--paper);
  box-shadow:0 3px 12px rgba(11,31,46,.08);
}
.day-tabs::before{
  content:'SELECT A DAY';
  position:absolute;
  left:16px;
  top:-11px;
  background:var(--linen);
  padding:0 8px;
  font-size:.52rem;
  font-weight:700;
  letter-spacing:.16em;
  color:var(--gold);
}
.day-tabs button{
  min-height:62px;
  border:1px solid transparent;
  border-radius:6px;
  background:var(--paper-soft);
  color:var(--ink);
  font-weight:600;
  font-size:.74rem;
  position:relative;
}
.day-tabs button::after{
  content:'›';
  display:inline-block;
  margin-left:8px;
  color:var(--gold);
  font-size:1rem;
  vertical-align:-1px;
}
.day-tabs button:hover{
  background:#eee8dd;
  border-color:rgba(200,146,42,.35);
}
.day-tabs button.active{
  background:var(--navy);
  color:#fff;
  border-color:var(--navy);
}
.day-tabs button.active::after{color:var(--gold-light)}

/* Prevent itinerary content from visually running into adjacent elements */
.location-panel{
  overflow:visible;
}
.location-heading{
  margin-bottom:24px;
}
.day-panel{
  width:100%;
  overflow:hidden;
  padding-top:2px;
}
.day{
  width:100%;
  padding:0 0 8px;
}
.day-sidebar{
  min-width:0;
}
.stops{
  min-width:0;
  width:100%;
}
.stop{
  min-width:0;
  width:100%;
}
.stop-content{
  min-width:0;
  overflow-wrap:anywhere;
}
.stop-name,.stop-desc{
  overflow-wrap:anywhere;
}
.stop.highlight,.stop.free{
  width:calc(100% + 0px);
  margin-left:0;
  margin-right:0;
}

@media(min-width:761px){
  .day{
    grid-template-columns:175px minmax(0,1fr);
    gap:0 38px;
  }
  .day-sidebar{
    padding-right:8px;
  }
}

/* Location day selector: vertical rail using the otherwise-empty sidebar */
.location-panel.active:not(.summary-panel):not(.logistics-panel):not(#location-return){
  display:grid!important;
  grid-template-columns:210px minmax(0,1fr);
  column-gap:42px;
  align-items:start;
}
.location-panel.active:not(.summary-panel):not(.logistics-panel):not(#location-return) .location-heading{
  grid-column:1 / -1;
  width:100%;
}
.location-panel.active:not(.summary-panel):not(.logistics-panel):not(#location-return) .day-tabs{
  grid-column:1;
  grid-row:2;
  display:flex;
  flex-direction:column;
  align-self:start;
  width:100%;
  margin:0;
  padding:8px;
  gap:7px;
  border:2px solid var(--gold);
  border-radius:10px;
  background:var(--paper);
  box-shadow:0 3px 12px rgba(11,31,46,.08);
  overflow:visible;
}
.location-panel.active:not(.summary-panel):not(.logistics-panel):not(#location-return) .day-tabs::before{
  position:static;
  display:block;
  background:transparent;
  padding:2px 8px 7px;
  font-size:.5rem;
  letter-spacing:.16em;
  text-align:left;
}
.location-panel.active:not(.summary-panel):not(.logistics-panel):not(#location-return) .day-tabs button{
  flex:none;
  width:100%;
  min-height:66px;
  text-align:left;
  padding:11px 13px;
  border:1px solid var(--divider);
  border-radius:7px;
  background:var(--paper-soft);
  color:var(--ink);
  display:flex;
  align-items:center;
  justify-content:space-between;
  gap:8px;
  line-height:1.25;
}
.location-panel.active:not(.summary-panel):not(.logistics-panel):not(#location-return) .day-tabs button::after{
  content:'→';
  margin-left:auto;
  color:var(--gold);
  font-size:1rem;
}
.location-panel.active:not(.summary-panel):not(.logistics-panel):not(#location-return) .day-tabs button.active{
  background:var(--navy);
  border-color:var(--navy);
  color:#fff;
  box-shadow:0 2px 7px rgba(11,31,46,.16);
}
.location-panel.active:not(.summary-panel):not(.logistics-panel):not(#location-return) .day-panel{
  grid-column:2;
  grid-row:2;
  width:100%;
  min-width:0;
}
.location-panel.active:not(.summary-panel):not(.logistics-panel):not(#location-return) .day-panel.active{
  display:block!important;
}

/* Logistics */
.logistics-grid{
  display:grid;
  grid-template-columns:1.15fr .85fr;
  gap:20px;
}
.logistics-card{
  background:linear-gradient(145deg,var(--paper) 0%,#F8F4EC 100%);
  border:1px solid var(--divider);
  border-radius:10px;
  padding:23px 24px;
  min-width:0;
}
.logistics-card h3{
  font-family:'Liberation Serif',Georgia,serif;
  font-size:1.28rem;
  font-weight:500;
  color:var(--ink);
}
.logistics-sub{
  font-size:.65rem;
  color:var(--ink-light);
  margin:3px 0 14px;
}
.logistics-row{
  display:grid;
  grid-template-columns:130px 1fr;
  gap:3px 16px;
  padding:12px 0;
  border-bottom:1px solid var(--divider);
}
.logistics-row:last-child{border-bottom:0}
.logistics-date{
  font-size:.6rem;
  color:var(--gold);
  font-weight:700;
  letter-spacing:.02em;
}
.logistics-route{
  font-family:'Liberation Serif',Georgia,serif;
  font-size:.91rem;
  color:var(--ink);
  font-weight:500;
}
.logistics-detail{
  grid-column:2;
  font-size:.63rem;
  color:var(--ink-light);
}
.hotel-logistics-row{
  padding:13px 0;
  border-bottom:1px solid var(--divider);
}
.hotel-logistics-row:last-child{border-bottom:0}
.hotel-logistics-top{
  display:flex;
  justify-content:space-between;
  gap:12px;
  margin-bottom:3px;
}
.hotel-place{
  font-size:.62rem;
  font-weight:700;
  color:var(--gold);
  text-transform:uppercase;
  letter-spacing:.08em;
}
.hotel-dates{
  font-size:.6rem;
  color:var(--ink-light);
}
.hotel-logistics-name{
  font-family:'Liberation Serif',Georgia,serif;
  font-size:.93rem;
  color:var(--ink);
  font-style:italic;
}
.hotel-logistics-duration{
  font-size:.61rem;
  color:var(--ink-light);
  margin-top:2px;
}
.logistics-note{
  margin-top:14px;
  text-align:center;
  font-size:.62rem;
  font-style:italic;
  color:var(--ink-light);
}
.logistics-artifact{
  margin-top:10px;
  padding:8px 10px;
  border:1px dashed #CFC5B7;
  border-radius:7px;
  background:rgba(243,239,231,.58);
  display:flex;
  align-items:center;
  justify-content:space-between;
  gap:10px;
  font-size:.6rem;
}
.logistics-artifact .artifact-label{color:var(--ink-light)}
.logistics-artifact .artifact-action{
  color:var(--navy);
  font-weight:700;
  letter-spacing:.04em;
}
.logistics-doc-card{
  background:linear-gradient(145deg,var(--paper) 0%,#F7F2E9 100%);
  border:1px solid var(--divider);
  border-radius:10px;
  padding:21px 24px;
}
.logistics-doc-card h3{
  font-family:'Liberation Serif',Georgia,serif;
  font-size:1.18rem;
  font-weight:500;
  color:var(--ink);
}
.logistics-doc-grid{
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:0 24px;
  margin-top:7px;
}
.logistics-doc-item{
  padding:10px 0;
  border-top:1px solid var(--divider);
}
.logistics-doc-item .doc-key{
  font-size:.58rem;
  text-transform:uppercase;
  letter-spacing:.08em;
  color:var(--gold);
  font-weight:700;
}
.logistics-doc-item .doc-value{
  margin-top:3px;
  font-size:.68rem;
  color:var(--ink);
}
@media (max-width:700px){
  .logistics-doc-grid{grid-template-columns:1fr}
  .logistics-artifact{font-size:.58rem}
}

@media(max-width:760px){
  .location-panel.active:not(.summary-panel):not(.logistics-panel):not(#location-return){
    display:block!important;
  }
  .location-panel.active:not(.summary-panel):not(.logistics-panel):not(#location-return) .day-tabs{
    margin:0 0 24px;
    display:flex;
    flex-direction:row;
    overflow-x:auto;
    padding:5px;
  }
  .location-panel.active:not(.summary-panel):not(.logistics-panel):not(#location-return) .day-tabs::before{
    display:none;
  }
  .location-panel.active:not(.summary-panel):not(.logistics-panel):not(#location-return) .day-tabs button{
    min-width:145px;
    min-height:58px;
    white-space:normal;
  }
  .location-panel.active:not(.summary-panel):not(.logistics-panel):not(#location-return) .day-panel{
    display:none!important;
  }
  .location-panel.active:not(.summary-panel):not(.logistics-panel):not(#location-return) .day-panel.active{
    display:block!important;
  }
  .logistics-grid{grid-template-columns:1fr}
  .logistics-row{grid-template-columns:112px 1fr}
}
</style>
</head>
<body><section class="hero">
<p class="hero-eyebrow">First Wedding Anniversary  ·  Nov – Dec 2026</p>
<h1 class="hero-title">Vietnam <em>Anniversary</em></h1>
<p class="hero-subtitle">Phong Nha  ·  Ninh Binh  ·  Hanoi  ·  Lan Ha Bay</p>
<div class="hero-meta">
<div class="hero-meta-item"><span class="hero-meta-label">Start</span><span class="hero-meta-value">Friday, 20 November 2026</span></div>
<div class="hero-meta-item"><span class="hero-meta-label">End</span><span class="hero-meta-value">Tuesday, 1 December 2026</span></div>
<div class="hero-meta-item"><span class="hero-meta-label">Duration</span><span class="hero-meta-value">11 nights · 12 days</span></div>
<div class="hero-meta-item"><span class="hero-meta-label">Anniversary</span><span class="hero-meta-value">Monday, 30 November</span></div>
</div>
<div class="hero-divider"></div>
</section><nav aria-label="Main itinerary navigation" class="main-nav"><button data-target="summary"><span class="nav-name">Summary</span><span class="nav-date"> </span></button><button data-target="logistics"><span class="nav-name">Logistics</span><span class="nav-date">Flights · Hotels</span></button><button data-target="phong-nha"><span class="nav-name">Phong Nha</span><span class="nav-date">21–22 Nov</span></button><button data-target="ninh-binh"><span class="nav-name">Ninh Binh</span><span class="nav-date">23–25 Nov</span></button><button data-target="hanoi"><span class="nav-name">Hanoi</span><span class="nav-date">26–28 Nov</span></button><button data-target="lan-ha-bay"><span class="nav-name">Lan Ha Bay</span><span class="nav-date">29–30 Nov</span></button><button data-target="return"><span class="nav-name">Return</span><span class="nav-date">1 Dec</span></button></nav><main class="content-shell"><section class="location-panel summary-panel" data-location="Summary" id="location-summary">
<div class="summary-intro">
<h2>Vietnam Anniversary</h2>
<p>11 nights · 12 days · 20 Nov – 1 Dec 2026</p>
</div>
<div class="summary-overview"><article class="summary-location"><h3>PHONG NHA</h3><div class="summary-dates">21–22 Nov</div><div class="summary-hotel">Victory Road Villas (21 Nov) · Central Backpackers (22 Nov)</div><div class="summary-items"><div><span>Phong Nha Cave</span><span>Guided tour</span></div><div><span>Paradise Cave</span><span>Guided tour</span></div></div></article><article class="summary-location"><h3>NINH BINH</h3><div class="summary-dates">23–25 Nov</div><div class="summary-hotel">An's Eco Garden Resort</div><div class="summary-items"><div><span>Trang An</span><span>~7 km / 8–10 min</span></div><div><span>Hoa Lu Ancient Capital</span><span>~5 km / ~5 min</span></div><div><span>Mua Cave</span><span>~15 min</span></div><div><span>Bich Dong Pagoda</span><span>12.3 km / 23 min</span></div><div><span>Bai Dinh Pagoda</span><span>~19 km / 12 mi</span></div><div><span>Van Long Nature Reserve</span><span>~20–23 km, calc.</span></div></div></article><article class="summary-location"><h3>HANOI</h3><div class="summary-dates">26–28 Nov</div><div class="summary-hotel">La Siesta Premium Hang Be (Old Quarter)</div><div class="summary-items"><div><span>Mausoleum / Presidential Grounds / One Pillar Pagoda</span><span>~10 min</span></div><div><span>Temple of Literature</span><span>~10 min</span></div><div><span>Bun Cha Huong Lien</span><span>Walk</span></div><div><span>Train Street</span><span>Walk</span></div><div><span>Water Puppet Theatre</span><span>Walk</span></div><div><span>Home Hanoi Restaurant</span><span>Walk</span></div><div><span>West Lake / Tran Quoc Pagoda</span><span>~4 km / 10–20 min</span></div></div></article><article class="summary-location"><h3>LAN HA BAY</h3><div class="summary-dates">29–30 Nov</div><div class="summary-hotel">Heritage Binh Chuan / Paradise Elegance Cruise</div></article></div></section><section class="location-panel" data-location="Phong Nha" id="location-phong-nha"><div class="location-heading"><h2>Phong Nha</h2><p>21–22 Nov</p></div><nav aria-label="Phong Nha days" class="day-tabs"><button data-day="phong-nha-21">Saturday, 21 Nov</button><button data-day="phong-nha-22">Sunday, 22 Nov</button></nav><div class="day-panel" id="phong-nha-21"><div class="day">
<div class="day-sidebar">
<div class="day-label">Transit &amp; arrival</div>
<div class="day-date">Saturday, 21 Nov</div>
<div class="day-line"></div>
</div>
<div class="stops">
<div class="stop">
<div class="stop-time">11:15 AM</div>
<div class="stop-content"><div class="stop-name">Fly Ho Chi Minh City → Dong Hoi</div><div class="stop-desc">VN 1406, arrives 12:50 PM. ~5h15m ground time at HCMC beforehand — confirm if this is one through-ticket or a self-transfer needing baggage reclaim.</div><span class="stop-tag tag-travel">Flight</span></div>
</div>
<div class="stop">
<div class="stop-time">2:50 PM</div>
<div class="stop-content"><div class="stop-name">Cab: Dong Hoi → Phong Nha</div><div class="stop-desc">Via 12Go, arrives 4:00 PM.</div><span class="stop-tag tag-travel">Transfer</span></div>
</div>
<div class="stop">
<div class="stop-time">Evening</div>
<div class="stop-content"><div class="stop-name">Check in, easy evening</div><div class="stop-desc">Long travel stretch — settle in, dinner nearby, rest before tomorrow's full cave day.</div><span class="stop-tag tag-stay">Stay</span></div>
</div>
</div>
</div></div><div class="day-panel" id="phong-nha-22"><div class="day page-break">
<div class="day-sidebar">
<div class="day-label">Caving day</div>
<div class="day-date">Sunday, 22 Nov</div>
<div class="day-line"></div>
</div>
<div class="stops">
<div class="stop">
<div class="stop-time">7:30 AM</div>
<div class="stop-content"><div class="stop-name">Breakfast at the homestay</div><div class="stop-desc"></div></div>
</div>
<div class="stop">
<div class="stop-time">8:45 AM</div>
<div class="stop-content"><div class="stop-name">Phong Nha Cave + Paradise Cave — Guided Tour</div><div class="stop-desc">The standard combined-day format most operators run — dragon boat into Phong Nha Cave's underground river, then a scenic walk through Paradise Cave's dry chambers. Lunch included. Returns by ~4:30–5:30 PM.</div><span class="stop-tag tag-nature">Nature</span></div>
</div>
<div class="stop">
<div class="stop-time">5:30 PM</div>
<div class="stop-content"><div class="stop-name">Checkout Victory Road Villas, transfer to Central Backpackers</div><div class="stop-desc">Central Backpackers is also the overnight bus departure point — checking in here removes the late-night transfer risk entirely, and costs under half of Victory Road's rate.</div><span class="stop-tag tag-stay">Stay</span></div>
</div>
<div class="stop free">
<div class="stop-time">6:00 PM</div>
<div class="stop-content"><div class="stop-name">Shower, rest in a private room</div><div class="stop-desc">A full cave day is more tiring than it looks — this is real recovery time, not just a layover.</div></div>
</div>
<div class="stop">
<div class="stop-time">7:30 PM</div>
<div class="stop-content"><div class="stop-name">Early dinner in the village</div><div class="stop-desc">Casual, unhurried.</div><span class="stop-tag tag-food">Food</span></div>
</div>
<div class="stop highlight">
<div class="stop-time">9:00 PM – 11:30 PM</div>
<div class="stop-content"><div class="stop-name">Rest at Central Backpackers until boarding</div><div class="stop-desc">You're already at the departure point — no transfer, no risk of missing it, and a private room to fall back on if the bus runs late.</div><span class="stop-tag tag-key">Bus Pickup</span></div>
</div>
<div class="stop">
<div class="stop-time">11:30 PM</div>
<div class="stop-content"><div class="stop-name">Overnight Sleeper Bus: Phong Nha → Ninh Binh</div><div class="stop-desc">Via 12Go, ~8 hrs, arrives 7:30 AM. Confirm operator is a known reliable one (Hung Thanh, Queen Cafe, Full Moon) — quality varies a lot on this route.</div><span class="stop-tag tag-travel">Bus</span></div>
</div>
</div>
</div></div></section><section class="location-panel" data-location="Ninh Binh" id="location-ninh-binh"><div class="location-heading"><h2>Ninh Binh</h2><p>23–25 Nov</p></div><nav aria-label="Ninh Binh days" class="day-tabs"><button data-day="ninh-binh-23">Monday, 23 Nov</button><button data-day="ninh-binh-24">Tuesday, 24 Nov</button><button data-day="ninh-binh-25">Wednesday, 25 Nov</button></nav><div class="day-panel" id="ninh-binh-23"><div class="day">
<div class="day-sidebar">
<div class="day-label">Arrival, light day</div>
<div class="day-date">Monday, 23 Nov</div>
<div class="day-line"></div>
</div>
<div class="stops">
<div class="stop">
<div class="stop-time">7:30 AM</div>
<div class="stop-content"><div class="stop-name">Arrive Ninh Binh, check in</div><div class="stop-desc">Off an overnight bus — room may not be ready this early; ask about early check-in or a luggage drop.</div><span class="stop-tag tag-stay">Stay</span></div>
</div>
<div class="stop free">
<div class="stop-time">8:00 AM</div>
<div class="stop-content"><div class="stop-name">Breakfast, rest, shower</div><div class="stop-desc">Genuine recovery time before doing anything — deliberately kept light after a night on the bus.</div></div>
</div>
<div class="stop">
<div class="stop-time">1:00 PM</div>
<div class="stop-content"><div class="stop-name">Trang An Boat Tour — UNESCO World Heritage</div><div class="stop-desc">Private wooden boat through river caves past cliffside temples. 2.5 hours. Only one activity today, deliberately — not paired with Hoa Lu like the caving-heavy days.</div><span class="stop-tag tag-nature">Nature</span></div>
</div>
<div class="stop">
<div class="stop-time">7:00 PM</div>
<div class="stop-content"><div class="stop-name">Goat Meat Dinner</div><div class="stop-desc">Ninh Binh's signature.</div><span class="stop-tag tag-food">Food</span></div>
</div>
</div>
</div></div><div class="day-panel" id="ninh-binh-24"><div class="day">
<div class="day-sidebar">
<div class="day-label">Hoa Lu &amp; Van Long</div>
<div class="day-date">Tuesday, 24 Nov</div>
<div class="day-line"></div>
</div>
<div class="stops">
<div class="stop">
<div class="stop-time">8:00 AM</div>
<div class="stop-content"><div class="stop-name">Breakfast at the resort</div><div class="stop-desc"></div></div>
</div>
<div class="stop">
<div class="stop-time">9:00 AM</div>
<div class="stop-content"><div class="stop-name">Hoa Lu Ancient Capital</div><div class="stop-desc">~5–10 min from the resort. Vietnam's 10th–11th century capital, temples against limestone peaks. ~1.5 hours.</div><span class="stop-tag tag-culture">Culture</span></div>
</div>
<div class="stop">
<div class="stop-time">12:30 PM</div>
<div class="stop-content"><div class="stop-name">Lunch</div><div class="stop-desc"></div><span class="stop-tag tag-food">Food</span></div>
</div>
<div class="stop">
<div class="stop-time">2:00 PM</div>
<div class="stop-content"><div class="stop-name">Van Long Nature Reserve</div><div class="stop-desc">~16 km, 25–30 min. Wetland boat, best chance of spotting the Delacour's langurs.</div><span class="stop-tag tag-nature">Nature</span></div>
</div>
<div class="stop">
<div class="stop-time">7:00 PM</div>
<div class="stop-content"><div class="stop-name">Dinner</div><div class="stop-desc"></div><span class="stop-tag tag-food">Food</span></div>
</div>
</div>
</div></div><div class="day-panel" id="ninh-binh-25"><div class="day">
<div class="day-sidebar">
<div class="day-label">Mua Cave &amp; Bich Dong</div>
<div class="day-date">Wednesday, 25 Nov</div>
<div class="day-line"></div>
</div>
<div class="stops">
<div class="stop">
<div class="stop-time">7:00 AM</div>
<div class="stop-content"><div class="stop-name">Mua Cave Peak Hike</div><div class="stop-desc">500 stone steps to the dragon shrine, ~30 min up. View of the Ngo Dong River winding through the valley.</div><span class="stop-tag tag-nature">Nature</span></div>
</div>
<div class="stop">
<div class="stop-time">9:00 AM</div>
<div class="stop-content"><div class="stop-name">Breakfast</div><div class="stop-desc"></div><span class="stop-tag tag-food">Food</span></div>
</div>
<div class="stop">
<div class="stop-time">10:30 AM</div>
<div class="stop-content"><div class="stop-name">Bich Dong Pagoda</div><div class="stop-desc">12.3 km, ~23 min from An's Eco Garden Resort. An ancient pagoda carved into limestone cliffs, near Tam Coc.</div><span class="stop-tag tag-culture">Culture</span></div>
</div>
<div class="stop">
<div class="stop-time">1:00 PM</div>
<div class="stop-content"><div class="stop-name">Lunch</div><div class="stop-desc"></div><span class="stop-tag tag-food">Food</span></div>
</div>
<div class="stop">
<div class="stop-time">2:30 PM</div>
<div class="stop-content"><div class="stop-name">Bai Dinh Pagoda</div><div class="stop-desc">~5–7 km from the Trang An corridor — the largest Buddhist complex in Southeast Asia. Worth it for scale and architecture, not scenic beauty like Trang An — a different register, not a highlight-reel stop. Takes longer to walk through than it looks given its size.</div><span class="stop-tag tag-culture">Culture</span></div>
</div>
<div class="stop free">
<div class="stop-time">5:30 PM</div>
<div class="stop-content"><div class="stop-name">Rest before dinner</div><div class="stop-desc"></div></div>
</div>
<div class="stop">
<div class="stop-time">7:00 PM</div>
<div class="stop-content"><div class="stop-name">Dinner</div><div class="stop-desc"></div><span class="stop-tag tag-food">Food</span></div>
</div>
</div>
</div></div></section><section class="location-panel" data-location="Hanoi" id="location-hanoi"><div class="location-heading"><h2>Hanoi</h2><p>26–28 Nov</p></div><nav aria-label="Hanoi days" class="day-tabs"><button data-day="hanoi-26">Thursday, 26 Nov</button><button data-day="hanoi-27">Friday, 27 Nov</button><button data-day="hanoi-28">Saturday, 28 Nov</button></nav><div class="day-panel" id="hanoi-26"><div class="day">
<div class="day-sidebar">
<div class="day-label">On to Hanoi</div>
<div class="day-date">Thursday, 26 Nov</div>
<div class="day-line"></div>
</div>
<div class="stops">
<div class="stop free">
<div class="stop-time">Morning</div>
<div class="stop-content"><div class="stop-name">Breakfast, checkout</div><div class="stop-desc"></div></div>
</div>
<div class="stop">
<div class="stop-time">9:00 AM</div>
<div class="stop-content"><div class="stop-name">Bus: Ninh Binh → Hanoi</div><div class="stop-desc">Via 12Go, ~2.5 hrs, arrives 11:30 AM. High-frequency, well-established route.</div><span class="stop-tag tag-travel">Bus</span></div>
</div>
<div class="stop">
<div class="stop-time">12:30 PM</div>
<div class="stop-content"><div class="stop-name">Check in, light lunch</div><div class="stop-desc"></div><span class="stop-tag tag-food">Food</span></div>
</div>
<div class="stop">
<div class="stop-time">3:00 PM</div>
<div class="stop-content"><div class="stop-name">West Lake &amp; Tran Quoc Pagoda</div><div class="stop-desc">~4 km / 10–20 min by Grab from the Old Quarter — not walkable despite feeling close on a map. Hanoi's oldest pagoda, set on the lake, especially good at golden hour.</div><span class="stop-tag tag-culture">Culture</span></div>
</div>
<div class="stop">
<div class="stop-time">6:30 PM</div>
<div class="stop-content"><div class="stop-name">Bia Hoi Corner</div><div class="stop-desc">Ta Hien street corner.</div><span class="stop-tag tag-food">Food</span></div>
</div>
</div>
</div></div><div class="day-panel" id="hanoi-27"><div class="day page-break">
<div class="day-sidebar">
<div class="day-label">Old Quarter &amp; signature dinner</div>
<div class="day-date">Friday, 27 Nov</div>
<div class="day-line"></div>
</div>
<div class="stops">
<div class="stop">
<div class="stop-time">8:00 AM</div>
<div class="stop-content"><div class="stop-name">Breakfast</div><div class="stop-desc"></div></div>
</div>
<div class="stop">
<div class="stop-time">9:00 AM</div>
<div class="stop-content"><div class="stop-name">Temple of Literature</div><div class="stop-desc">Vietnam's first university, 1070 AD. Open daily — no closure conflict.</div><span class="stop-tag tag-culture">Culture</span></div>
</div>
<div class="stop">
<div class="stop-time">12:30 PM</div>
<div class="stop-content"><div class="stop-name">Bun Cha Huong Lien — Lunch</div><div class="stop-desc">The Obama-Bourdain spot.</div><span class="stop-tag tag-food">Food</span></div>
</div>
<div class="stop">
<div class="stop-time">2:00 PM</div>
<div class="stop-content"><div class="stop-name">Hanoi Train Street</div><div class="stop-desc">Attempt via a licensed café — access inconsistent since 2025. Hoan Kiem Lake as backup.</div><span class="stop-tag tag-culture">Attempt Only</span></div>
</div>
<div class="stop">
<div class="stop-time">6:00 PM</div>
<div class="stop-content"><div class="stop-name">Thang Long Water Puppet Show</div><div class="stop-desc">Book ahead. 1 hour.</div><span class="stop-tag tag-culture">Culture</span></div>
</div>
<div class="stop">
<div class="stop-time">7:15 PM</div>
<div class="stop-content"><div class="stop-name">Egg Coffee — Giang Café</div><div class="stop-desc">The original, since 1946.</div><span class="stop-tag tag-food">Food</span></div>
</div>
<div class="stop highlight">
<div class="stop-time">9:00 PM</div>
<div class="stop-content">
<div class="stop-name">Dinner — Home Hanoi Restaurant</div>
<div class="stop-desc">Reserve months ahead. French colonial villa, candlelight, refined Vietnamese classics.</div>
<span class="stop-tag tag-key">Signature Dinner</span>
</div>
</div>
</div>
</div></div><div class="day-panel" id="hanoi-28"><div class="day page-break">
<div class="day-sidebar">
<div class="day-label">Ba Dinh &amp; the Presidential Grounds</div>
<div class="day-date">Saturday, 28 Nov</div>
<div class="day-line"></div>
</div>
<div class="stops">
<div class="stop">
<div class="stop-time">8:00 AM</div>
<div class="stop-content"><div class="stop-name">Breakfast</div><div class="stop-desc"></div></div>
</div>
<div class="stop">
<div class="stop-time">8:30 AM</div>
<div class="stop-content">
<div class="stop-name">Ho Chi Minh Mausoleum + Presidential Grounds + One Pillar Pagoda</div>
<div class="stop-desc">Open Tue/Wed/Thu/Sat/Sun mornings only, closed Mon &amp; Fri — Saturday is valid. Ba Dinh Square, the House-on-Stilts, the mango-lined fishpond, and One Pillar Pagoda. ~2 hours.</div>
<span class="stop-tag tag-culture">Culture</span>
</div>
</div>
<div class="stop free">
<div class="stop-time">11:00 AM</div>
<div class="stop-content"><div class="stop-name">Free late morning</div><div class="stop-desc">Vietnam Museum of Ethnology is ~15 min away if you want it — optional.</div></div>
</div>
<div class="stop">
<div class="stop-time">1:00 PM</div>
<div class="stop-content"><div class="stop-name">Lunch</div><div class="stop-desc"></div><span class="stop-tag tag-food">Food</span></div>
</div>
<div class="stop free">
<div class="stop-time">3:00 PM</div>
<div class="stop-content"><div class="stop-name">Free afternoon, early night</div><div class="stop-desc">8:30 AM cruise pickup tomorrow.</div></div>
</div>
<div class="stop">
<div class="stop-time">7:00 PM</div>
<div class="stop-content"><div class="stop-name">Light Dinner</div><div class="stop-desc"></div><span class="stop-tag tag-food">Food</span></div>
</div>
</div>
</div></div></section><section class="location-panel" data-location="Lan Ha Bay" id="location-lan-ha-bay"><div class="location-heading"><h2>Lan Ha Bay</h2><p>29–30 Nov</p></div><nav aria-label="Lan Ha Bay days" class="day-tabs"><button data-day="lan-ha-bay-29">Sunday, 29 Nov</button><button data-day="lan-ha-bay-30">Monday, 30 Nov</button></nav><div class="day-panel" id="lan-ha-bay-29"><div class="day">
<div class="day-sidebar">
<div class="day-label">Boarding the cruise</div>
<div class="day-date">Sunday, 29 Nov</div>
<div class="day-line"></div>
</div>
<div class="stops">
<div class="stop">
<div class="stop-time">7:30 AM</div>
<div class="stop-content"><div class="stop-name">Breakfast</div><div class="stop-desc"></div></div>
</div>
<div class="stop">
<div class="stop-time">8:30 AM</div>
<div class="stop-content"><div class="stop-name">Shared Cab: Hanoi → Cat Ba Archipelago</div><div class="stop-desc">Provided by the cruise, arrives 11:30 AM per your latest cost sheet.</div><span class="stop-tag tag-travel">Transfer</span></div>
</div>
<div class="stop">
<div class="stop-time">12:00 PM</div>
<div class="stop-content"><div class="stop-name">Board — Welcome Drink, Cabin Check-in</div><div class="stop-desc">Heritage Binh Chuan or Paradise Elegance. Mention the anniversary in advance.</div><span class="stop-tag tag-stay">Stay</span></div>
</div>
<div class="stop">
<div class="stop-time">1:15 PM</div>
<div class="stop-content"><div class="stop-name">Buffet Lunch Onboard</div><div class="stop-desc"></div><span class="stop-tag tag-food">Food</span></div>
</div>
<div class="stop">
<div class="stop-time">3:00 PM</div>
<div class="stop-content"><div class="stop-name">Kayaking / Ba Trai Dao Beach</div><div class="stop-desc">Emerald water, limestone cliffs on three sides.</div><span class="stop-tag tag-nature">Beach</span></div>
</div>
<div class="stop">
<div class="stop-time">5:30 PM</div>
<div class="stop-content"><div class="stop-name">Sunset Cocktails</div><div class="stop-desc"></div><span class="stop-tag tag-nature">View</span></div>
</div>
<div class="stop">
<div class="stop-time">6:00 PM</div>
<div class="stop-content"><div class="stop-name">Vietnamese Cooking Class</div><div class="stop-desc"></div><span class="stop-tag tag-food">Food</span></div>
</div>
<div class="stop">
<div class="stop-time">7:30 PM</div>
<div class="stop-content"><div class="stop-name">Dinner Onboard</div><div class="stop-desc"></div><span class="stop-tag tag-food">Food</span></div>
</div>
</div>
</div></div><div class="day-panel" id="lan-ha-bay-30"><div class="day anniversary">
<div class="day-sidebar">
<div class="day-label">First Anniversary</div>
<div class="day-date">Monday, 30 Nov</div>
<div class="day-line"></div>
<span class="anniversary-badge">★ Anniversary</span>
</div>
<div class="stops">
<div class="stop">
<div class="stop-time">6:00 AM</div>
<div class="stop-content"><div class="stop-name">Sunrise on Deck</div><div class="stop-desc"></div><span class="stop-tag tag-nature">Nature</span></div>
</div>
<div class="stop">
<div class="stop-time">6:50 AM</div>
<div class="stop-content"><div class="stop-name">Bright &amp; Dark Cave — Bamboo Boat</div><div class="stop-desc"></div><span class="stop-tag tag-nature">Nature</span></div>
</div>
<div class="stop">
<div class="stop-time">8:00 AM</div>
<div class="stop-content"><div class="stop-name">Breakfast Onboard</div><div class="stop-desc"></div><span class="stop-tag tag-food">Food</span></div>
</div>
<div class="stop">
<div class="stop-time">Day</div>
<div class="stop-content"><div class="stop-name">Viet Hai Village / Second Beach Session</div><div class="stop-desc">Follows the cruise's fixed day-2 program — confirm exact sequence with the operator.</div><span class="stop-tag tag-culture">Culture</span></div>
</div>
<div class="stop highlight">
<div class="stop-time">7:30 PM</div>
<div class="stop-content">
<div class="stop-name">Candlelit Anniversary Dinner — Open Deck</div>
<div class="stop-desc">Multi-course dinner under the stars, karst silhouettes all around. Arrange the private setup with the crew in advance.</div>
<span class="stop-tag tag-key">The Night</span>
</div>
</div>
</div>
</div></div></section><section class="location-panel logistics-panel" data-location="Logistics" id="location-logistics"><div class="location-heading">
<h2>Logistics</h2>
<p>Flights · Buses · Hotels · Visa · Insurance</p>
</div><div class="logistics-grid"><article class="logistics-card"><h3>Flights &amp; Buses</h3><p class="logistics-sub">All major intercity transport</p><div class="logistics-row"><div class="logistics-date">20 Nov · 11:35 PM</div><div class="logistics-route">Bangalore → Ho Chi Minh City</div><div class="logistics-detail">VJ 1802 · Flight</div></div><div class="logistics-row"><div class="logistics-date">21 Nov · 11:15 AM</div><div class="logistics-route">Ho Chi Minh City → Dong Hoi</div><div class="logistics-detail">VN 1406 · Flight</div></div><div class="logistics-row"><div class="logistics-date">21 Nov · 2:50 PM</div><div class="logistics-route">Dong Hoi → Phong Nha</div><div class="logistics-detail">12Go · Cab · Transfer</div></div><div class="logistics-row"><div class="logistics-date">22 Nov · 11:30 PM</div><div class="logistics-route">Phong Nha → Ninh Binh</div><div class="logistics-detail">12Go · Overnight sleeper · Bus</div></div><div class="logistics-row"><div class="logistics-date">26 Nov · 9:00 AM</div><div class="logistics-route">Ninh Binh → Hanoi</div><div class="logistics-detail">12Go · Bus · Bus</div></div><div class="logistics-row"><div class="logistics-date">29 Nov · 8:30 AM</div><div class="logistics-route">Hanoi → Cat Ba Archipelago</div><div class="logistics-detail">Cruise-provided shared cab · Transfer</div></div><div class="logistics-row"><div class="logistics-date">1 Dec · 11:15 AM</div><div class="logistics-route">Cruise → Noi Bai Airport</div><div class="logistics-detail">Cruise-provided private cab · Transfer</div></div><div class="logistics-row"><div class="logistics-date">1 Dec · 6:50 PM</div><div class="logistics-route">Hanoi → Bangalore</div><div class="logistics-detail">VN 983 · Flight</div></div></article><article class="logistics-card"><h3>Hotels</h3><p class="logistics-sub">Accommodation by destination</p><div class="hotel-logistics-row"><div class="hotel-logistics-top"><span class="hotel-place">Phong Nha</span><span class="hotel-dates">21 Nov</span></div><div class="hotel-logistics-name">Victory Road Villas</div><div class="hotel-logistics-duration">1 night</div></div><div class="hotel-logistics-row"><div class="hotel-logistics-top"><span class="hotel-place">Phong Nha</span><span class="hotel-dates">22 Nov</span></div><div class="hotel-logistics-name">Central Backpackers</div><div class="hotel-logistics-duration">1 night · private room</div></div><div class="hotel-logistics-row"><div class="hotel-logistics-top"><span class="hotel-place">Ninh Binh</span><span class="hotel-dates">23–25 Nov</span></div><div class="hotel-logistics-name">An's Eco Garden Resort</div><div class="hotel-logistics-duration">3 nights</div></div><div class="hotel-logistics-row"><div class="hotel-logistics-top"><span class="hotel-place">Hanoi</span><span class="hotel-dates">26–28 Nov</span></div><div class="hotel-logistics-name">La Siesta Premium Hang Be</div><div class="hotel-logistics-duration">3 nights</div></div><div class="hotel-logistics-row"><div class="hotel-logistics-top"><span class="hotel-place">Lan Ha Bay</span><span class="hotel-dates">29 Nov–1 Dec</span></div><div class="hotel-logistics-name">Heritage Binh Chuan / Paradise Elegance Cruise</div><div class="hotel-logistics-duration">2 nights</div></div></article><article class="logistics-doc-card"><h3>Visa &amp; Entry</h3><p class="logistics-sub">Travel authorization and entry documents</p><div class="logistics-doc-grid"><div class="logistics-doc-item"><div class="doc-key">Visa</div><div class="doc-value">Vietnam e-visa / entry authorization</div></div><div class="logistics-doc-item"><div class="doc-key">Passport</div><div class="doc-value">Passport details to be added</div></div><div class="logistics-doc-item"><div class="doc-key">Validity</div><div class="doc-value">Visa validity / permitted stay to be added</div></div><div class="logistics-doc-item"><div class="doc-key">Artefact</div><div class="doc-value">Visa PDF / approval letter</div><div class="logistics-artifact"><span class="artifact-label">📎 No document attached yet</span><span class="artifact-action">ADD</span></div></div></div></article><article class="logistics-doc-card"><h3>Travel Insurance</h3><p class="logistics-sub">Policy and emergency information</p><div class="logistics-doc-grid"><div class="logistics-doc-item"><div class="doc-key">Provider</div><div class="doc-value">Insurance provider to be added</div></div><div class="logistics-doc-item"><div class="doc-key">Policy</div><div class="doc-value">Policy number to be added</div></div><div class="logistics-doc-item"><div class="doc-key">Coverage</div><div class="doc-value">20–30 Nov / 1 Dec coverage dates to be confirmed</div></div><div class="logistics-doc-item"><div class="doc-key">Artefact</div><div class="doc-value">Insurance policy / certificate</div><div class="logistics-artifact"><span class="artifact-label">📎 No document attached yet</span><span class="artifact-action">ADD</span></div></div></div></article></div><div class="logistics-note">Logistics is your document hub: flights, buses, hotels, visa and insurance can each carry their supporting artefacts.</div></section><section class="location-panel" data-location="Return" id="location-return"><div class="location-heading"><h2>Return</h2><p>Tuesday, 1 Dec</p></div><div class="day-panel" id="return-1" style="display:block"><div class="day">
<div class="day-sidebar">
<div class="day-label">Heading home</div>
<div class="day-date">Tuesday, 1 Dec</div>
<div class="day-line"></div>
</div>
<div class="stops">
<div class="stop">
<div class="stop-time">Morning</div>
<div class="stop-content"><div class="stop-name">Final Breakfast, Disembark</div><div class="stop-desc"></div><span class="stop-tag tag-nature">Nature</span></div>
</div>
<div class="stop">
<div class="stop-time">11:15 AM</div>
<div class="stop-content"><div class="stop-name">Private Cab: Cruise → Noi Bai Airport</div><div class="stop-desc">Provided by the cruise, arrives 2:00 PM.</div><span class="stop-tag tag-travel">Transfer</span></div>
</div>
<div class="stop">
<div class="stop-time">6:50 PM</div>
<div class="stop-content"><div class="stop-name">Fly Hanoi → Bangalore</div><div class="stop-desc">VN 983, arrives 10:15 PM. Comfortable ~4h50m buffer after landing from the cruise.</div><span class="stop-tag tag-travel">Flight</span></div>
</div>
</div>
</div></div></section></main><script>
(() => {
  const body = document.body;
  const navButtons = [...document.querySelectorAll('.main-nav button')];
  const locationPanels = [...document.querySelectorAll('.location-panel')];
  const summaryPanel = document.getElementById('location-summary');

  function clearDaySelection(panel) {
    panel.querySelectorAll('.day-tabs button').forEach(b => b.classList.remove('active'));
    panel.querySelectorAll('.day-panel').forEach(p => p.classList.remove('active'));
  }

  function clearLocations() {
    locationPanels.forEach(p => {
      p.classList.remove('active');
      clearDaySelection(p);
    });
  }

  function activateMain(target) {
    navButtons.forEach(b => b.classList.toggle('active', b.dataset.target === target));
  }

  function showLocation(target) {
    const panel = document.getElementById(`location-${target}`);
    if (!panel) return;
    clearLocations();
    activateMain(target);
    body.classList.add('has-selection');
    panel.classList.add('active');
    // Deliberately no date selected.
  }

  function showSummary() {
    clearLocations();
    activateMain('summary');
    body.classList.add('has-selection');
    summaryPanel.classList.add('active');
  }

  function showReturn() {
    clearLocations();
    activateMain('return');
    body.classList.add('has-selection');
    const panel = document.getElementById('location-return');
    panel.classList.add('active');
    const day = panel.querySelector('.day-panel');
    if (day) day.classList.add('active');
  }

  function showLogistics() {
    clearLocations();
    activateMain('logistics');
    body.classList.add('has-selection');
    document.getElementById('location-logistics').classList.add('active');
  }

  function showDay(locationTarget, dayId) {
    const panel = document.getElementById(`location-${locationTarget}`);
    if (!panel) return;
    clearLocations();
    activateMain(locationTarget);
    body.classList.add('has-selection');
    panel.classList.add('active');
    panel.querySelectorAll('.day-tabs button').forEach(b => {
      b.classList.toggle('active', b.dataset.day === dayId);
    });
    panel.querySelectorAll('.day-panel').forEach(p => {
      p.classList.toggle('active', p.id === dayId);
    });
  }

  navButtons.forEach(button => {
    button.addEventListener('click', () => {
      const target = button.dataset.target;

      // Clicking the currently selected primary tab returns to the original
      // cover state: large hero, no active content, no active tab.
      if (button.classList.contains('active')) {
        clearLocations();
        navButtons.forEach(b => b.classList.remove('active'));
        body.classList.remove('has-selection');
        window.scrollTo({ top: 0, behavior: 'smooth' });
        return;
      }

      if (target === 'summary') showSummary();
      else if (target === 'return') showReturn();
      else if (target === 'logistics') showLogistics();
      else showLocation(target);
    });
  });

  document.querySelectorAll('.day-tabs button').forEach(button => {
    button.addEventListener('click', () => {
      const panel = button.closest('.location-panel');
      const target = panel.id.replace('location-', '');
      showDay(target, button.dataset.day);
    });
  });

  // Initial state: cover + primary navigation only.
  clearLocations();
  navButtons.forEach(b => b.classList.remove('active'));
  body.classList.remove('has-selection');
})();
</script></body>
</html>
