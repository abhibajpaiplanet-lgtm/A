<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>NEXORA – Where Memes Live.</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Archivo+Black&family=Space+Mono:ital,wght@0,400;0,700;1,400&family=Nunito:wght@400;700;800;900&display=swap" rel="stylesheet">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
<style>
*,*::before,*::after{margin:0;padding:0;box-sizing:border-box;}
:root{
  --bg:#f5f0e8;
  --card-bg:#ffffff;
  --ink:#111111;
  --ink-soft:#444444;
  --border:#111111;
  --border-w:2.5px;
  --yellow:#ffe44d;
  --pink:#ff4d8d;
  --cyan:#00d4ff;
  --green:#00e676;
  --orange:#ff6b1a;
  --purple:#8c52ff;
  --red:#ff2d55;
  --radius:12px;
  --radius-lg:20px;
  --radius-xl:28px;
  --shadow:4px 4px 0px var(--ink);
  --shadow-lg:6px 6px 0px var(--ink);
  --shadow-hover:8px 8px 0px var(--ink);
  --font-display:'Archivo Black',sans-serif;
  --font-mono:'Space Mono',monospace;
  --font-body:'Nunito',sans-serif;
  --transition:all 0.2s cubic-bezier(0.4,0,0.2,1);
}
html{scroll-behavior:smooth;overflow-x:hidden;}
body{font-family:var(--font-body);background:var(--bg);color:var(--ink);overflow-x:hidden;padding-bottom:80px;
  background-image:radial-gradient(circle at 20% 20%,rgba(255,228,77,.15) 0%,transparent 40%),
  radial-gradient(circle at 80% 80%,rgba(255,77,141,.1) 0%,transparent 40%),
  radial-gradient(circle at 50% 50%,rgba(0,212,255,.05) 0%,transparent 60%);
}
body::before{content:'';position:fixed;inset:0;background-image:radial-gradient(circle,rgba(0,0,0,.08) 1px,transparent 1px);background-size:24px 24px;pointer-events:none;z-index:0;}
*::-webkit-scrollbar{width:6px;}
*::-webkit-scrollbar-track{background:var(--bg);}
*::-webkit-scrollbar-thumb{background:var(--ink);border-radius:3px;}

/* ── HEADER ── */
.header{
  position:sticky;top:0;z-index:200;
  background:var(--bg);
  border-bottom:var(--border-w) solid var(--border);
  padding:10px 20px;
  display:flex;align-items:center;justify-content:space-between;gap:12px;
  box-shadow:0 4px 0 var(--ink);
}
.logo-wrap{display:flex;flex-direction:column;line-height:1;}
.logo{
  font-family:var(--font-display);
  font-size:28px;letter-spacing:-1px;color:var(--ink);
  position:relative;display:inline-block;
  text-decoration:none;
}
.logo span{
  background:var(--yellow);
  padding:0 4px;
  border:2px solid var(--ink);
  display:inline-block;
  transform:rotate(-1.5deg);
  box-shadow:3px 3px 0 var(--ink);
  margin-right:2px;
}
.logo-tag{font-size:9px;font-weight:700;letter-spacing:2px;text-transform:uppercase;color:var(--ink-soft);font-family:var(--font-mono);}
.header-center{flex:1;max-width:440px;margin:0 auto;}
.search-box{
  display:flex;align-items:center;gap:8px;
  background:#fff;
  border:var(--border-w) solid var(--border);
  border-radius:var(--radius);
  box-shadow:var(--shadow);
  padding:8px 14px;
  transition:var(--transition);
  position:relative;
}
.search-box:focus-within{box-shadow:var(--shadow-hover);transform:translate(-1px,-1px);}
.search-box i{color:var(--ink);font-size:14px;flex-shrink:0;}
.search-box input{
  flex:1;border:none;outline:none;background:transparent;
  font-family:var(--font-body);font-size:14px;font-weight:700;color:var(--ink);
}
.search-box input::placeholder{color:#aaa;font-weight:400;}
.header-actions{display:flex;gap:8px;align-items:center;}
.hbtn{
  width:42px;height:42px;
  border:var(--border-w) solid var(--border);
  border-radius:var(--radius);
  background:#fff;
  cursor:pointer;
  display:flex;align-items:center;justify-content:center;
  font-size:16px;color:var(--ink);
  box-shadow:var(--shadow);
  transition:var(--transition);
}
.hbtn:hover{transform:translate(-2px,-2px);box-shadow:var(--shadow-hover);}
.hbtn:active{transform:translate(0,0);box-shadow:none;}
.hbtn.active{background:var(--yellow);}

/* ── CATEGORY BAR ── */
.catbar{
  padding:12px 16px 8px;
  overflow-x:auto;white-space:nowrap;
  border-bottom:var(--border-w) solid var(--border);
  background:var(--bg);
  position:sticky;top:64px;z-index:100;
  scrollbar-width:none;
}
.catbar::-webkit-scrollbar{display:none;}
.cat-list{display:inline-flex;gap:8px;}
.cat-pill{
  padding:7px 16px;
  border:var(--border-w) solid var(--border);
  border-radius:999px;
  font-family:var(--font-body);font-weight:700;font-size:13px;
  cursor:pointer;background:#fff;color:var(--ink);
  box-shadow:3px 3px 0 var(--ink);
  transition:var(--transition);
  white-space:nowrap;
  display:inline-flex;align-items:center;gap:6px;
}
.cat-pill:hover{transform:translate(-2px,-2px);box-shadow:5px 5px 0 var(--ink);}
.cat-pill:active{transform:translate(0,0);box-shadow:none;}
.cat-pill.active{background:var(--yellow);font-weight:900;}
.cat-pill .emoji{font-size:14px;}

/* ── MASONRY FEED ── */
.feed-section{position:relative;z-index:1;padding:16px 12px 0;}

.masonry-grid{
  columns:2;column-gap:10px;
}
@media(min-width:500px){.masonry-grid{columns:2;column-gap:12px;}}
@media(min-width:700px){.masonry-grid{columns:3;column-gap:14px;}}
@media(min-width:900px){.masonry-grid{columns:4;column-gap:16px;}}
@media(min-width:1200px){.masonry-grid{columns:5;column-gap:16px;}}

/* ── MEME CARD ── */
.meme-card{
  break-inside:avoid;
  margin-bottom:12px;
  border:var(--border-w) solid var(--border);
  border-radius:var(--radius-lg);
  overflow:hidden;
  cursor:pointer;
  background:#fff;
  box-shadow:var(--shadow);
  transition:transform 0.2s cubic-bezier(0.34,1.56,0.64,1),box-shadow 0.2s ease;
  display:inline-block;
  width:100%;
  position:relative;
}
.meme-card:hover{transform:translate(-3px,-5px) rotate(-0.5deg);box-shadow:var(--shadow-hover);}
.meme-card:active{transform:translate(0,0);box-shadow:3px 3px 0 var(--ink);}
.meme-card img,.meme-card .meme-gif-wrap{
  width:100%;display:block;
  object-fit:cover;
}
.meme-card img{min-height:120px;}

.meme-card-hover-btns{
  position:absolute;bottom:0;left:0;right:0;
  padding:8px;
  display:flex;gap:6px;justify-content:flex-end;
  background:linear-gradient(to top,rgba(0,0,0,.6) 0%,transparent 100%);
  opacity:0;transition:opacity 0.2s;
}
.meme-card:hover .meme-card-hover-btns{opacity:1;}
.hover-btn{
  width:30px;height:30px;border-radius:8px;
  background:#fff;border:1.5px solid var(--ink);
  color:var(--ink);font-size:12px;
  display:flex;align-items:center;justify-content:center;
  cursor:pointer;transition:var(--transition);
  box-shadow:2px 2px 0 var(--ink);
}
.hover-btn:hover{background:var(--yellow);transform:scale(1.1);}

/* ── DETAIL OVERLAY ── */
.overlay{
  position:fixed;inset:0;z-index:500;
  background:var(--bg);
  overflow-y:auto;
  opacity:0;visibility:hidden;pointer-events:none;
  transition:opacity 0.25s ease,visibility 0.25s;
}
.overlay.active{opacity:1;visibility:visible;pointer-events:all;}
.overlay-inner{max-width:900px;margin:0 auto;padding:0 0 80px;}

.detail-header{
  display:flex;align-items:center;justify-content:space-between;
  padding:14px 20px;
  border-bottom:var(--border-w) solid var(--border);
  position:sticky;top:0;background:var(--bg);z-index:10;
  box-shadow:0 4px 0 var(--ink);
}
.back-btn{
  display:flex;align-items:center;gap:8px;
  background:#fff;border:var(--border-w) solid var(--border);
  border-radius:var(--radius);padding:8px 16px;
  font-weight:900;font-size:14px;font-family:var(--font-body);
  cursor:pointer;box-shadow:var(--shadow);transition:var(--transition);
}
.back-btn:hover{transform:translate(-2px,-2px);box-shadow:var(--shadow-hover);}

.detail-meme-wrap{
  padding:20px;
  display:flex;justify-content:center;
  background:var(--bg);
  position:relative;
}
.detail-meme{
  max-width:100%;max-height:70vh;
  object-fit:contain;
  border:var(--border-w) solid var(--border);
  border-radius:var(--radius-lg);
  box-shadow:var(--shadow-lg);
  display:block;
}
.detail-meme-sticker{
  max-width:260px;
  filter:drop-shadow(0 8px 24px rgba(0,0,0,.2));
}

.detail-body{padding:0 20px;}
.detail-caption{
  font-family:var(--font-display);
  font-size:20px;line-height:1.3;
  margin-bottom:12px;
  position:relative;display:inline-block;
}
.detail-caption::after{
  content:'';position:absolute;bottom:-2px;left:0;right:0;height:5px;
  background:var(--yellow);z-index:-1;
}
.detail-tags{display:flex;flex-wrap:wrap;gap:6px;margin-bottom:16px;}
.tag-chip{
  padding:5px 12px;
  background:#fff;border:var(--border-w) solid var(--border);
  border-radius:999px;font-size:12px;font-weight:700;
  font-family:var(--font-mono);cursor:pointer;
  box-shadow:2px 2px 0 var(--ink);transition:var(--transition);
  color:var(--ink);
}
.tag-chip:hover{background:var(--cyan);transform:translate(-1px,-2px);}

.format-badge{
  padding:3px 8px;border-radius:6px;
  border:1.5px solid var(--ink);
  font-family:var(--font-mono);font-size:9px;font-weight:700;
  letter-spacing:1px;text-transform:uppercase;
  box-shadow:2px 2px 0 var(--ink);
  display:inline-block;
}
.badge-gif{background:var(--cyan);color:var(--ink);}
.badge-img{background:var(--green);color:var(--ink);}
.badge-sticker{background:var(--pink);color:#fff;}

.creator-row{
  display:flex;align-items:center;gap:12px;
  padding:14px 16px;
  background:#fff;border:var(--border-w) solid var(--border);
  border-radius:var(--radius-lg);box-shadow:var(--shadow);
  margin-bottom:16px;
}
.creator-avatar{
  width:42px;height:42px;border-radius:50%;
  border:var(--border-w) solid var(--border);
  object-fit:cover;flex-shrink:0;
  background:var(--yellow);
  display:flex;align-items:center;justify-content:center;
  font-size:18px;
}
.creator-name{font-weight:900;font-size:14px;}
.creator-handle{font-size:11px;color:var(--ink-soft);font-family:var(--font-mono);}
.creator-follow{
  margin-left:auto;
  padding:6px 14px;
  background:var(--ink);color:#fff;
  border:var(--border-w) solid var(--border);
  border-radius:999px;font-weight:800;font-size:12px;
  cursor:pointer;font-family:var(--font-body);
  box-shadow:2px 2px 0 rgba(0,0,0,.3);
  transition:var(--transition);
}
.creator-follow:hover{background:var(--yellow);color:var(--ink);}

.action-btns{display:flex;flex-wrap:wrap;gap:10px;margin-bottom:20px;}
.act-btn{
  flex:1;min-width:130px;
  padding:12px 20px;
  border:var(--border-w) solid var(--border);
  border-radius:var(--radius);
  font-family:var(--font-body);font-weight:900;font-size:14px;
  cursor:pointer;display:flex;align-items:center;justify-content:center;gap:8px;
  box-shadow:var(--shadow);transition:var(--transition);
  text-decoration:none;color:var(--ink);
}
.act-btn:hover{transform:translate(-2px,-3px);box-shadow:var(--shadow-hover);}
.act-btn:active{transform:translate(0,0);box-shadow:2px 2px 0 var(--ink);}
.act-share{background:var(--cyan);}
.act-download{background:var(--green);}
.act-custom1{background:var(--pink);color:#fff;}
.act-custom2{background:var(--purple);color:#fff;}

/* RECS SECTION */
.recs-section{margin-bottom:24px;}
.recs-heading{
  font-family:var(--font-display);font-size:16px;
  display:flex;align-items:center;gap:8px;margin-bottom:12px;
}
.recs-heading span{
  background:var(--pink);color:#fff;
  padding:2px 10px;border-radius:6px;
  border:2px solid var(--ink);box-shadow:2px 2px 0 var(--ink);
  font-size:12px;
}
.recs-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(140px,1fr));gap:10px;}
.rec-card{
  background:#fff;border:var(--border-w) solid var(--border);
  border-radius:var(--radius);overflow:hidden;cursor:pointer;
  box-shadow:var(--shadow);transition:var(--transition);
  text-decoration:none;color:var(--ink);display:block;
}
.rec-card:hover{transform:translate(-2px,-3px);box-shadow:var(--shadow-hover);}
.rec-card img{width:100%;aspect-ratio:4/3;object-fit:cover;display:block;}
.rec-card-body{padding:8px 10px;}
.rec-name{font-weight:900;font-size:12px;line-height:1.3;margin-bottom:2px;}
.rec-price{font-size:13px;font-weight:700;color:var(--orange);font-family:var(--font-mono);}

/* ── EXPLORE OVERLAY ── */
#exploreOverlay{background:var(--bg);}
.explore-inner{max-width:1200px;margin:0 auto;padding:16px 16px 80px;}
.explore-filters{
  display:flex;flex-wrap:wrap;gap:8px;margin-bottom:20px;
}
.exf-pill{
  padding:8px 18px;
  border:var(--border-w) solid var(--border);
  border-radius:999px;background:#fff;
  font-weight:700;font-size:13px;
  cursor:pointer;box-shadow:3px 3px 0 var(--ink);
  transition:var(--transition);font-family:var(--font-body);
}
.exf-pill:hover{transform:translate(-2px,-2px);box-shadow:5px 5px 0 var(--ink);}
.exf-pill.active{background:var(--purple);color:#fff;}

/* ── SEARCH OVERLAY ── */
#searchOverlay{background:var(--bg);}
.search-overlay-inner{max-width:700px;margin:0 auto;padding:20px 20px 80px;}
.search-big-box{
  display:flex;align-items:center;gap:10px;
  background:#fff;border:var(--border-w) solid var(--border);
  border-radius:var(--radius-lg);box-shadow:var(--shadow-lg);
  padding:14px 20px;margin-bottom:20px;
}
.search-big-box input{
  flex:1;border:none;outline:none;font-family:var(--font-display);font-size:18px;background:transparent;
}
.search-big-box input::placeholder{color:#ccc;}
.search-cats-section label{font-family:var(--font-display);font-size:13px;letter-spacing:1px;margin-bottom:10px;display:block;}
.search-cat-chips{display:flex;flex-wrap:wrap;gap:8px;margin-bottom:20px;}
.scat-chip{
  padding:7px 14px;border:var(--border-w) solid var(--border);border-radius:999px;
  background:#fff;font-weight:700;font-size:12px;cursor:pointer;
  box-shadow:2px 2px 0 var(--ink);transition:var(--transition);
}
.scat-chip:hover{background:var(--yellow);}
.scat-chip.active{background:var(--yellow);}

.search-results-grid{columns:2;column-gap:10px;}
@media(min-width:500px){.search-results-grid{columns:3;}}
@media(min-width:768px){.search-results-grid{columns:4;}}

/* ── BOTTOM NAV ── */
.bottom-nav{
  position:fixed;bottom:0;left:0;right:0;z-index:300;
  background:var(--bg);
  border-top:var(--border-w) solid var(--border);
  display:flex;justify-content:space-around;
  padding:6px 0 8px;
  box-shadow:0 -4px 0 var(--ink);
}
.nav-item{
  display:flex;flex-direction:column;align-items:center;gap:3px;
  background:none;border:none;cursor:pointer;
  color:var(--ink-soft);font-family:var(--font-body);
  font-size:10px;font-weight:800;letter-spacing:.5px;text-transform:uppercase;
  padding:4px 14px;border-radius:var(--radius);
  transition:var(--transition);
}
.nav-item:hover,.nav-item.active{color:var(--ink);}
.nav-icon{width:36px;height:36px;border-radius:10px;display:flex;align-items:center;justify-content:center;font-size:18px;transition:var(--transition);}
.nav-item.active .nav-icon{background:var(--yellow);border:2px solid var(--ink);box-shadow:2px 2px 0 var(--ink);}
.nav-item:hover:not(.active) .nav-icon{background:rgba(255,228,77,.3);}

/* ── UPLOAD BTN ── */
.upload-fab{
  position:fixed;bottom:88px;right:20px;z-index:400;
  width:52px;height:52px;
  background:var(--pink);color:#fff;
  border:var(--border-w) solid var(--ink);
  border-radius:var(--radius);
  font-size:22px;cursor:pointer;
  display:flex;align-items:center;justify-content:center;
  box-shadow:var(--shadow-lg);
  transition:var(--transition);
  animation:fabBounce 3s ease-in-out infinite;
}
@keyframes fabBounce{0%,100%{transform:translateY(0);}50%{transform:translateY(-5px);}}
.upload-fab:hover{transform:translate(-3px,-6px) rotate(5deg);box-shadow:var(--shadow-hover);animation:none;}

/* ── TOAST ── */
.toast{
  position:fixed;bottom:90px;left:50%;transform:translateX(-50%);
  background:var(--ink);color:#fff;
  font-family:var(--font-body);font-weight:800;font-size:14px;
  padding:12px 24px;border-radius:var(--radius);
  box-shadow:4px 4px 0 var(--yellow);
  z-index:2000;animation:toastPop .3s cubic-bezier(.34,1.56,.64,1) forwards, toastFade .3s 2.6s forwards;
  pointer-events:none;white-space:nowrap;
}
@keyframes toastPop{from{opacity:0;transform:translateX(-50%) scale(.8) translateY(10px);}to{opacity:1;transform:translateX(-50%) scale(1) translateY(0);}}
@keyframes toastFade{to{opacity:0;transform:translateX(-50%) translateY(-10px);}}

/* ── SECTION LABEL (kept for explore only) ── */
.section-label{
  font-family:var(--font-display);font-size:20px;letter-spacing:-0.5px;
  margin-bottom:14px;display:flex;align-items:center;gap:10px;flex-wrap:wrap;
}
.section-label .accent{
  background:var(--ink);color:#fff;
  padding:0 8px;border-radius:6px;font-size:16px;
}
.feed-counter{
  font-family:var(--font-mono);font-size:11px;
  background:var(--ink);color:#fff;
  padding:4px 10px;border-radius:999px;
}

/* ── EMPTY STATE ── */
.empty-state{
  text-align:center;padding:60px 20px;
  font-family:var(--font-display);
  column-span:all;
}
.empty-emoji{font-size:60px;margin-bottom:16px;display:block;animation:spinEmoji 4s linear infinite;}
@keyframes spinEmoji{from{transform:rotate(0);}to{transform:rotate(360deg);}}

/* ── PAGE TRANSITIONS ── */
.page-in{animation:pageSlide .3s cubic-bezier(.4,0,.2,1);}
@keyframes pageSlide{from{opacity:0;transform:translateY(16px);}to{opacity:1;transform:translateY(0);}}

/* ── MOBILE ADJUSTMENTS ── */
@media(max-width:480px){
  .header-center{display:none;}
  .logo{font-size:24px;}
  .detail-caption{font-size:17px;}
  .action-btns .act-btn{min-width:100px;font-size:13px;padding:10px 14px;}
}
</style>
</head>
<body>

<!-- HEADER -->
<header class="header" id="mainHeader">
  <a class="logo" href="#" onclick="showHome();return false;">
    <span>N</span>EXORA
  </a>
  <div class="logo-tag">Where Memes Live.</div>
  <div class="header-center">
    <div class="search-box" id="headerSearchBox">
      <i class="fas fa-search"></i>
      <input type="text" placeholder="Search memes…" id="headerSearchInput" autocomplete="off">
    </div>
  </div>
  <div class="header-actions">
    <button class="hbtn" id="searchToggleBtn" title="Search" aria-label="Search"><i class="fas fa-search"></i></button>
    <button class="hbtn" id="filterToggleBtn" title="Filter" aria-label="Filter"><i class="fas fa-sliders-h"></i></button>
  </div>
</header>

<!-- CATEGORY BAR -->
<div class="catbar">
  <div class="cat-list" id="catList"></div>
</div>

<!-- HOME FEED -->
<div id="homeSection" class="page-in">
  <div class="feed-section">
    <div class="masonry-grid" id="mainFeed"></div>
  </div>
</div>

<!-- BOTTOM NAV -->
<nav class="bottom-nav">
  <button class="nav-item active" data-page="home">
    <div class="nav-icon"><i class="fas fa-fire"></i></div>
    Hot
  </button>
  <button class="nav-item" data-page="explore">
    <div class="nav-icon"><i class="fas fa-compass"></i></div>
    Explore
  </button>
  <button class="nav-item" data-page="search">
    <div class="nav-icon"><i class="fas fa-search"></i></div>
    Search
  </button>
  <button class="nav-item" data-page="upload">
    <div class="nav-icon"><i class="fas fa-plus"></i></div>
    Upload
  </button>
</nav>

<!-- UPLOAD FAB -->
<button class="upload-fab" id="uploadFab" title="Upload Meme">
  <i class="fas fa-plus"></i>
</button>

<!-- DETAIL OVERLAY -->
<div class="overlay" id="detailOverlay">
  <div class="overlay-inner" id="detailContent"></div>
</div>

<!-- EXPLORE OVERLAY -->
<div class="overlay" id="exploreOverlay">
  <div class="detail-header">
    <button class="back-btn" id="closeExplore"><i class="fas fa-arrow-left"></i> Back</button>
    <span style="font-family:var(--font-display);font-size:18px;">🧭 Explore Memes</span>
    <div></div>
  </div>
  <div class="explore-inner">
    <div class="explore-filters" id="exploreFilters"></div>
    <div class="section-label"><span>All Memes</span><span class="accent">Universe</span></div>
    <div class="masonry-grid" id="exploreFeed"></div>
  </div>
</div>

<!-- SEARCH OVERLAY -->
<div class="overlay" id="searchOverlay">
  <div class="detail-header">
    <button class="back-btn" id="closeSearch"><i class="fas fa-arrow-left"></i> Back</button>
    <span style="font-family:var(--font-display);font-size:18px;">🔍 Search</span>
    <div></div>
  </div>
  <div class="search-overlay-inner">
    <div class="search-big-box">
      <i class="fas fa-search" style="color:#aaa;font-size:18px;"></i>
      <input type="text" id="searchBigInput" placeholder="Crypto meme, anime, food…">
      <button onclick="document.getElementById('searchBigInput').value='';renderSearchResults('');" style="background:none;border:none;cursor:pointer;font-size:16px;color:#aaa;"><i class="fas fa-times"></i></button>
    </div>
    <div class="search-cats-section">
      <label>FILTER BY CATEGORY</label>
      <div class="search-cat-chips" id="searchCatChips"></div>
    </div>
    <div class="section-label" style="font-size:16px;"><span>Results</span><div class="feed-counter" id="searchCounter">0 memes</div></div>
    <div class="search-results-grid" id="searchResultsGrid"></div>
  </div>
</div>

<script>
/* ============================================================
   DATA
============================================================ */
const CATEGORIES = [
  {name:'All',emoji:'🔥'},
  {name:'Trending',emoji:'📈'},
  {name:'Viral',emoji:'🚀'},
  {name:'Crypto',emoji:'🪙'},
  {name:'Gaming',emoji:'🎮'},
  {name:'Anime',emoji:'⛩️'},
  {name:'Food',emoji:'🍕'},
  {name:'Relationship',emoji:'💔'},
  {name:'Dark Humor',emoji:'💀'},
  {name:'Bollywood',emoji:'🎬'},
  {name:'Sports',emoji:'⚽'},
  {name:'NFT',emoji:'🖼️'},
  {name:'Political',emoji:'🗳️'},
  {name:'Tech',emoji:'💻'},
  {name:'Wholesome',emoji:'🥹'},
  {name:'Doge',emoji:'🐕'},
];

const EXPLORE_FILTERS = [
  '🔥 All','📈 Trending','🆕 New','⬇️ Most Downloaded','💥 Viral',
  '🏷️ Brand','🖼️ NFT','🗳️ Political','🎮 Gaming',
  '🪙 Crypto','🍕 Food','💔 Relationship','💀 Dark Humor',
  '⛩️ Anime','🎬 Bollywood','🌍 Global'
];

const MEME_IMAGES = [
  {id:'m001',img:'https://media.giphy.com/media/QBd2kLB5qDmysEXre9/giphy.gif',cat:'Crypto',format:'img',tags:['crypto','moon','hodl'],caption:'Me watching BTC at 3am again',creator:{name:'CryptoKing',handle:'@cryptoking',avatar:'🪙'},actions:[{label:'Buy BTC',url:'#',cls:'act-custom1'},{label:'View NFTs',url:'#',cls:'act-custom2'}],recs:[{name:'Moon Mug',img:'https://images.unsplash.com/photo-1574482620826-a7a2cb63a7c1?w=300&q=75',price:'$12'},{name:'HODL Cap',img:'https://images.unsplash.com/photo-1556306535-0f09a537f0a3?w=300&q=75',price:'$18'},{name:'Doge Print',img:'https://images.unsplash.com/photo-1568702846914-96b305d2aaeb?w=300&q=75',price:'$25'}]},
  {id:'m002',img:'https://files.cults3d.com/uploaders/18644490/illustration-file/0fdd294f-e770-4354-a4cb-1d6e464074e2/NIKE-90.gif',cat:'Food',format:'img',tags:['pizza','foodmeme','carbs'],caption:'My personality type is pizza',creator:{name:'FoodLord',handle:'@foodlord',avatar:'🍕'},actions:[{label:'Order Pizza',url:'#',cls:'act-custom1'},{label:'View Deals',url:'#',cls:'act-custom2'}],recs:[{name:'Pizza Tee',img:'https://images.unsplash.com/photo-1581006852262-e4307cf6283a?w=300&q=75',price:'$22'},{name:'Meme Magnet',img:'https://images.unsplash.com/photo-1574482620826-a7a2cb63a7c1?w=300&q=75',price:'$6'},{name:'Food Sticker Pack',img:'https://images.unsplash.com/photo-1607082349566-187342175e2f?w=300&q=75',price:'$3'}]},
  {id:'m003',img:'https://media.giphy.com/media/OfkGZ5H2H3f8Y/giphy.gif',cat:'Wholesome',format:'img',tags:['dog','wholesome','cute'],caption:'This dog is having a better day than me',creator:{name:'WholesomeMemer',handle:'@wholesome',avatar:'🥹'},actions:[{label:'Adopt',url:'#',cls:'act-custom1'},{label:'More Dogs',url:'#',cls:'act-custom2'}],recs:[{name:'Dog Plushie',img:'https://images.unsplash.com/photo-1583511655857-d19b40a7a54e?w=300&q=75',price:'$14'},{name:'Paw Socks',img:'https://images.unsplash.com/photo-1548036328-c9fa89d128fa?w=300&q=75',price:'$8'},{name:'Pet Stickers',img:'https://images.unsplash.com/photo-1587300003388-59208cc962cb?w=300&q=75',price:'$4'}]},
  {id:'m004',img:'https://images.unsplash.com/photo-1627163439134-7a8c47e08208?w=600&q=80',cat:'Tech',format:'img',tags:['tech','coding','monday'],caption:'Me deploying to prod on Friday',creator:{name:'DevMemer',handle:'@devmemer',avatar:'💻'},actions:[{label:'GitHub',url:'#',cls:'act-custom1'},{label:'More Tech',url:'#',cls:'act-custom2'}],recs:[{name:'Dev Mug',img:'https://images.unsplash.com/photo-1522125670776-3c7abb882bc2?w=300&q=75',price:'$15'},{name:'Rubber Duck',img:'https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=300&q=75',price:'$5'},{name:'Keyboard Sticker',img:'https://images.unsplash.com/photo-1555041469-a586c61ea9bc?w=300&q=75',price:'$3'}]},
  {id:'m005',img:'https://images.unsplash.com/photo-1574482620826-a7a2cb63a7c1?w=600&q=80',cat:'Relationship',format:'img',tags:['relationship','couple','texting'],caption:'Left on read. Again.',creator:{name:'SituationshipKing',handle:'@situationship',avatar:'💔'},actions:[{label:'Therapy',url:'#',cls:'act-custom1'},{label:'More Pain',url:'#',cls:'act-custom2'}],recs:[{name:'Sad Playlist',img:'https://images.unsplash.com/photo-1493225457124-a3eb161ffa5f?w=300&q=75',price:'Free'},{name:'Comfort Hoodie',img:'https://images.unsplash.com/photo-1556306535-0f09a537f0a3?w=300&q=75',price:'$35'},{name:'Diary',img:'https://images.unsplash.com/photo-1531346878377-a5be20888e57?w=300&q=75',price:'$10'}]},
  {id:'m006',img:'https://images.unsplash.com/photo-1568702846914-96b305d2aaeb?w=600&q=80',cat:'Doge',format:'img',tags:['doge','crypto','wow'],caption:'Such meme. Much wow.',creator:{name:'DogeGod',handle:'@dogegod',avatar:'🐕'},actions:[{label:'Buy DOGE',url:'#',cls:'act-custom1'},{label:'Wow NFT',url:'#',cls:'act-custom2'}],recs:[{name:'Doge Plush',img:'https://images.unsplash.com/photo-1583511655857-d19b40a7a54e?w=300&q=75',price:'$20'},{name:'Doge Cap',img:'https://images.unsplash.com/photo-1556306535-0f09a537f0a3?w=300&q=75',price:'$16'},{name:'Doge Keychain',img:'https://images.unsplash.com/photo-1548036328-c9fa89d128fa?w=300&q=75',price:'$7'}]},
  {id:'m007',img:'https://images.unsplash.com/photo-1622979135225-d2ba269cf1ac?w=600&q=80',cat:'Gaming',format:'gif',tags:['gaming','fps','clutch'],caption:'When you clutch the 1v5',creator:{name:'GamerGod',handle:'@gamergod',avatar:'🎮'},actions:[{label:'Watch Clip',url:'#',cls:'act-custom1'},{label:'Play Now',url:'#',cls:'act-custom2'}],recs:[{name:'Gaming Mousepad',img:'https://images.unsplash.com/photo-1525547719571-a2d4ac8945e2?w=300&q=75',price:'$28'},{name:'Stream Hoodie',img:'https://images.unsplash.com/photo-1556306535-0f09a537f0a3?w=300&q=75',price:'$40'},{name:'Controller Mug',img:'https://images.unsplash.com/photo-1522125670776-3c7abb882bc2?w=300&q=75',price:'$13'}]},
  {id:'m008',img:'https://images.unsplash.com/photo-1547036967-23d11aacaee0?w=600&q=80',cat:'Dark Humor',format:'img',tags:['dark','monday','mood'],caption:'My brain at 2am: what if—',creator:{name:'DarkVibes',handle:'@darkvibes',avatar:'💀'},actions:[{label:'Therapy',url:'#',cls:'act-custom1'},{label:'Same lol',url:'#',cls:'act-custom2'}],recs:[{name:'Skull Mug',img:'https://images.unsplash.com/photo-1522125670776-3c7abb882bc2?w=300&q=75',price:'$17'},{name:'Existential Tee',img:'https://images.unsplash.com/photo-1581006852262-e4307cf6283a?w=300&q=75',price:'$24'},{name:'Dark Stickers',img:'https://images.unsplash.com/photo-1574482620826-a7a2cb63a7c1?w=300&q=75',price:'$4'}]},
  {id:'m009',img:'https://images.unsplash.com/photo-1607083206869-4c7672e72a8a?w=600&q=80',cat:'Food',format:'sticker',tags:['coffee','morning','relatable'],caption:'Coffee is a personality',creator:{name:'CaffeineGoblin',handle:'@coffeememer',avatar:'☕'},actions:[{label:'Order Coffee',url:'#',cls:'act-custom1'},{label:'Buy Beans',url:'#',cls:'act-custom2'}],recs:[{name:'Coffee Mug',img:'https://images.unsplash.com/photo-1574482620826-a7a2cb63a7c1?w=300&q=75',price:'$14'},{name:'Barista Kit',img:'https://images.unsplash.com/photo-1495474472287-4d71bcdd2085?w=300&q=75',price:'$45'},{name:'Latte Art Print',img:'https://images.unsplash.com/photo-1507226710507-2c1f2e48fe5f?w=300&q=75',price:'$12'}]},
  {id:'m010',img:'https://images.unsplash.com/photo-1611532736597-de2d4265fba3?w=600&q=80',cat:'Tech',format:'img',tags:['phone','scrolling','adhd'],caption:'Just 5 more minutes of scrolling',creator:{name:'ScreenAddicted',handle:'@screentime',avatar:'📱'},actions:[{label:'Skill Issue',url:'#',cls:'act-custom1'},{label:'More Memes',url:'#',cls:'act-custom2'}],recs:[{name:'Phone Stand',img:'https://images.unsplash.com/photo-1596558450255-7c0b7be9d56a?w=300&q=75',price:'$9'},{name:'No Screen Hat',img:'https://images.unsplash.com/photo-1556306535-0f09a537f0a3?w=300&q=75',price:'$19'},{name:'Blue Light Glasses',img:'https://images.unsplash.com/photo-1511499767150-a48a237f0083?w=300&q=75',price:'$22'}]},
  {id:'m011',img:'https://images.unsplash.com/photo-1546182990-dffeafbe841d?w=600&q=80',cat:'Wholesome',format:'img',tags:['nature','peace','vibe'],caption:'Skill: touch grass',creator:{name:'TouchGrass',handle:'@touchgrass',avatar:'🌿'},actions:[{label:'Go Outside',url:'#',cls:'act-custom1'},{label:'Trail Map',url:'#',cls:'act-custom2'}],recs:[{name:'Hammock',img:'https://images.unsplash.com/photo-1468276311594-df7cb65d8df6?w=300&q=75',price:'$35'},{name:'Nature Journal',img:'https://images.unsplash.com/photo-1531346878377-a5be20888e57?w=300&q=75',price:'$12'},{name:'Chill Sticker Pack',img:'https://images.unsplash.com/photo-1574482620826-a7a2cb63a7c1?w=300&q=75',price:'$5'}]},
  {id:'m012',img:'https://images.unsplash.com/photo-1614680376739-414d95ff43df?w=600&q=80',cat:'Crypto',format:'gif',tags:['nft','crypto','apes'],caption:'GM. NFTs are art.',creator:{name:'NFTBro',handle:'@nftbro',avatar:'🖼️'},actions:[{label:'Buy NFT',url:'#',cls:'act-custom1'},{label:'OpenSea',url:'#',cls:'act-custom2'}],recs:[{name:'NFT Print',img:'https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=300&q=75',price:'$50'},{name:'Crypto Tee',img:'https://images.unsplash.com/photo-1581006852262-e4307cf6283a?w=300&q=75',price:'$28'},{name:'Digital Wallet',img:'https://images.unsplash.com/photo-1563013544-824ae1b704d3?w=300&q=75',price:'$15'}]},
];

/* ── STATE ── */
const state = {activeCategory:'All', searchQuery:'', exploreFilter:'🔥 All'};

/* ============================================================
   INIT
============================================================ */
document.addEventListener('DOMContentLoaded', () => {
  renderCategories();
  renderFeed(MEME_IMAGES);
  renderExploreFilters();
  renderExploreFeed(MEME_IMAGES);
  renderSearchCatChips();
  setupEventListeners();
});

/* ── CATEGORIES ── */
function renderCategories() {
  const list = document.getElementById('catList');
  list.innerHTML = CATEGORIES.map(c => `
    <button class="cat-pill ${c.name===state.activeCategory?'active':''}" data-cat="${c.name}">
      <span class="emoji">${c.emoji}</span>${c.name}
    </button>
  `).join('');
  list.querySelectorAll('.cat-pill').forEach(btn => btn.addEventListener('click', () => {
    state.activeCategory = btn.dataset.cat;
    list.querySelectorAll('.cat-pill').forEach(b => b.classList.toggle('active', b.dataset.cat === state.activeCategory));
    const filtered = state.activeCategory === 'All' ? MEME_IMAGES : MEME_IMAGES.filter(m => m.cat === state.activeCategory || m.tags?.includes(state.activeCategory.toLowerCase()));
    renderFeed(filtered);
  }));
}

/* ── FEED ── */
function renderFeed(data) {
  const feed = document.getElementById('mainFeed');
  if (!data.length) {
    feed.innerHTML = `<div class="empty-state"><span class="empty-emoji">😶‍🌫️</span><br>No memes found. Universe is empty.</div>`;
    return;
  }
  feed.innerHTML = data.map(m => memeCardHTML(m)).join('');
  feed.querySelectorAll('.meme-card').forEach(card => {
    card.addEventListener('click', () => openDetail(card.dataset.id));
  });
  feed.querySelectorAll('.hover-btn[data-action="share"]').forEach(btn => btn.addEventListener('click', e => {e.stopPropagation(); doShare(btn.dataset.id);}));
  feed.querySelectorAll('.hover-btn[data-action="download"]').forEach(btn => btn.addEventListener('click', e => {e.stopPropagation(); doDownload(btn.dataset.id);}));
}

function memeCardHTML(m) {
  return `<article class="meme-card" data-id="${m.id}">
    <img src="${m.img}" alt="${escHtml(m.caption)}" loading="lazy">
    <div class="meme-card-hover-btns">
      <button class="hover-btn" data-action="share" data-id="${m.id}" title="Share"><i class="fas fa-share-alt"></i></button>
      <button class="hover-btn" data-action="download" data-id="${m.id}" title="Download"><i class="fas fa-download"></i></button>
    </div>
  </article>`;
}

/* ── DETAIL ── */
function openDetail(id) {
  const m = MEME_IMAGES.find(x => x.id === id);
  if (!m) return;
  const overlay = document.getElementById('detailOverlay');
  const content = document.getElementById('detailContent');

  const isSticker = m.format === 'sticker';
  const avatarEl = typeof m.creator.avatar === 'string' && m.creator.avatar.length <= 4
    ? `<div class="creator-avatar">${m.creator.avatar}</div>`
    : `<img class="creator-avatar" src="${m.creator.avatar}" alt="${m.creator.name}">`;

  content.innerHTML = `
    <div class="detail-header">
      <button class="back-btn" id="closeDetail"><i class="fas fa-arrow-left"></i> Back</button>
      <span style="font-family:var(--font-mono);font-size:12px;opacity:.5;">#${m.cat}</span>
      <div></div>
    </div>
    <div class="detail-meme-wrap">
      <img src="${m.img}" alt="${escHtml(m.caption)}" class="detail-meme ${isSticker?'detail-meme-sticker':''}" loading="eager">
    </div>
    <div class="detail-body">
      <h2 class="detail-caption">${escHtml(m.caption)}</h2>
      <div class="detail-tags">
        ${m.tags.map(t=>`<button class="tag-chip">#${escHtml(t)}</button>`).join('')}
        <span class="format-badge ${({gif:'badge-gif',img:'badge-img',sticker:'badge-sticker'}[m.format])||'badge-img'}" style="position:static;display:inline-block;">${m.format.toUpperCase()}</span>
      </div>
      <div class="creator-row">
        ${avatarEl}
        <div>
          <div class="creator-name">${escHtml(m.creator.name)}</div>
          <div class="creator-handle">${escHtml(m.creator.handle)}</div>
        </div>
        <button class="creator-follow">+ Follow</button>
      </div>
      <div class="action-btns">
        <button class="act-btn act-share" data-action="share" data-id="${m.id}"><i class="fas fa-share-alt"></i> Share</button>
        <button class="act-btn act-download" data-action="download" data-id="${m.id}"><i class="fas fa-download"></i> Download</button>
        ${m.actions.map(a=>`<a href="${a.url}" target="_blank" rel="noopener" class="act-btn ${a.cls}">${escHtml(a.label)} <i class="fas fa-arrow-right" style="font-size:11px;"></i></a>`).join('')}
      </div>
      <div class="recs-section">
        <div class="recs-heading">You Might Also Meme This <span>💀 Related</span></div>
        <div class="recs-grid">
          ${m.recs.map(r=>`<a href="#" class="rec-card"><img src="${r.img}" alt="${escHtml(r.name)}" loading="lazy"><div class="rec-card-body"><div class="rec-name">${escHtml(r.name)}</div><div class="rec-price">${escHtml(r.price)}</div></div></a>`).join('')}
        </div>
      </div>
    </div>`;

  content.querySelector('#closeDetail').addEventListener('click', closeDetail);
  content.querySelectorAll('[data-action="share"]').forEach(b => b.addEventListener('click', () => doShare(m.id)));
  content.querySelectorAll('[data-action="download"]').forEach(b => b.addEventListener('click', () => doDownload(m.id)));
  content.querySelectorAll('.tag-chip').forEach(chip => chip.addEventListener('click', () => {
    state.activeCategory = 'All';
    closeDetail();
    const q = chip.textContent.slice(1);
    const filtered = MEME_IMAGES.filter(x => x.tags?.includes(q) || x.cat.toLowerCase()===q);
    renderFeed(filtered.length ? filtered : MEME_IMAGES);
  }));
  content.querySelector('.creator-follow').addEventListener('click', e => { e.currentTarget.textContent = '✓ Following'; e.currentTarget.style.background='var(--green)'; });
  content.querySelectorAll('.rec-card').forEach(c => c.addEventListener('click', e => {e.preventDefault(); showToast('Opening soon! 🚀');}));

  overlay.classList.add('active');
  document.body.style.overflow='hidden';
}

function closeDetail() {
  document.getElementById('detailOverlay').classList.remove('active');
  document.body.style.overflow='';
}

/* ── EXPLORE ── */
function renderExploreFilters() {
  const el = document.getElementById('exploreFilters');
  el.innerHTML = EXPLORE_FILTERS.map(f => `<button class="exf-pill ${f===state.exploreFilter?'active':''}" data-f="${escHtml(f)}">${f}</button>`).join('');
  el.querySelectorAll('.exf-pill').forEach(btn => btn.addEventListener('click', () => {
    state.exploreFilter = btn.dataset.f;
    el.querySelectorAll('.exf-pill').forEach(b => b.classList.toggle('active', b.dataset.f === state.exploreFilter));
    renderExploreFeed(MEME_IMAGES);
  }));
}

function renderExploreFeed(data) {
  const feed = document.getElementById('exploreFeed');
  feed.innerHTML = data.map(m => memeCardHTML(m)).join('');
  feed.querySelectorAll('.meme-card').forEach(card => card.addEventListener('click', () => {
    document.getElementById('exploreOverlay').classList.remove('active');
    openDetail(card.dataset.id);
  }));
}

/* ── SEARCH ── */
function renderSearchCatChips() {
  const el = document.getElementById('searchCatChips');
  el.innerHTML = CATEGORIES.slice(0,10).map(c => `<button class="scat-chip" data-cat="${c.name}">${c.emoji} ${c.name}</button>`).join('');
  el.querySelectorAll('.scat-chip').forEach(btn => btn.addEventListener('click', () => {
    el.querySelectorAll('.scat-chip').forEach(b=>b.classList.toggle('active', b===btn));
    document.getElementById('searchBigInput').value = btn.dataset.cat;
    renderSearchResults(btn.dataset.cat.toLowerCase());
  }));
}

function renderSearchResults(q) {
  const grid = document.getElementById('searchResultsGrid');
  const counter = document.getElementById('searchCounter');
  const filtered = q ? MEME_IMAGES.filter(m =>
    m.cat.toLowerCase().includes(q) || m.tags?.some(t=>t.includes(q)) || m.caption.toLowerCase().includes(q)
  ) : MEME_IMAGES;
  counter.textContent = `${filtered.length} memes`;
  if (!filtered.length) {
    grid.innerHTML = `<div class="empty-state" style="column-span:all;"><span style="font-size:48px;">🤔</span><br>No memes for "${escHtml(q)}"</div>`;
    return;
  }
  grid.innerHTML = filtered.map(m => memeCardHTML(m)).join('');
  grid.querySelectorAll('.meme-card').forEach(card => card.addEventListener('click', () => {
    document.getElementById('searchOverlay').classList.remove('active');
    openDetail(card.dataset.id);
  }));
}

/* ── SHARE / DOWNLOAD ── */
function doShare(id) {
  const m = MEME_IMAGES.find(x=>x.id===id);
  if (navigator.share) {
    navigator.share({title: m?.caption || 'Check this meme!', url: location.href}).catch(()=>{});
  } else {
    navigator.clipboard?.writeText(location.href).then(()=>showToast('Link copied! 🔗')).catch(()=>showToast('Share: '+location.href));
  }
}

function doDownload(id) {
  const m = MEME_IMAGES.find(x=>x.id===id);
  if (!m) return;
  const a = document.createElement('a');
  a.href = m.img;
  a.download = `nexora-meme-${id}.jpg`;
  a.target = '_blank';
  document.body.appendChild(a);
  a.click();
  document.body.removeChild(a);
  showToast('Downloading meme! 💾');
}

/* ── TOAST ── */
function showToast(msg) {
  document.querySelectorAll('.toast').forEach(t=>t.remove());
  const t = document.createElement('div');
  t.className='toast';t.textContent=msg;
  document.body.appendChild(t);
  setTimeout(()=>t.remove(), 3100);
}

/* ── NAVIGATION ── */
function setNav(page) {
  document.querySelectorAll('.nav-item').forEach(n=>n.classList.toggle('active', n.dataset.page===page));
}

function showHome() {
  closeAllOverlays();
  setNav('home');
  window.scrollTo({top:0,behavior:'smooth'});
}
function closeAllOverlays() {
  ['detailOverlay','exploreOverlay','searchOverlay'].forEach(id=>{
    document.getElementById(id).classList.remove('active');
  });
  document.body.style.overflow='';
}

/* ── EVENT LISTENERS ── */
function setupEventListeners() {
  document.querySelectorAll('.nav-item').forEach(item => {
    item.addEventListener('click', () => {
      const page = item.dataset.page;
      if (page === 'home') { showHome(); return; }
      if (page === 'upload') { showToast('Upload feature coming soon! 🚀'); return; }
      setNav(page);
      closeAllOverlays();
      if (page === 'explore') {
        document.getElementById('exploreOverlay').classList.add('active');
        document.body.style.overflow='hidden';
      } else if (page === 'search') {
        document.getElementById('searchOverlay').classList.add('active');
        document.body.style.overflow='hidden';
        setTimeout(()=>document.getElementById('searchBigInput').focus(), 150);
      }
    });
  });

  document.getElementById('searchToggleBtn').addEventListener('click', () => {
    setNav('search');
    closeAllOverlays();
    document.getElementById('searchOverlay').classList.add('active');
    document.body.style.overflow='hidden';
    setTimeout(()=>document.getElementById('searchBigInput').focus(), 150);
  });
  document.getElementById('filterToggleBtn').addEventListener('click', () => {
    setNav('explore');
    closeAllOverlays();
    document.getElementById('exploreOverlay').classList.add('active');
    document.body.style.overflow='hidden';
  });

  let st;
  document.getElementById('headerSearchInput').addEventListener('input', e => {
    clearTimeout(st); st = setTimeout(() => {
      const q = e.target.value.toLowerCase();
      if (!q) { renderFeed(MEME_IMAGES); return; }
      const filtered = MEME_IMAGES.filter(m => m.cat.toLowerCase().includes(q) || m.tags?.some(t=>t.includes(q)) || m.caption.toLowerCase().includes(q));
      renderFeed(filtered);
    }, 250);
  });
  let st2;
  document.getElementById('searchBigInput').addEventListener('input', e => {
    clearTimeout(st2); st2 = setTimeout(()=>renderSearchResults(e.target.value.toLowerCase()), 250);
  });

  document.getElementById('closeExplore').addEventListener('click', () => {
    document.getElementById('exploreOverlay').classList.remove('active');
    document.body.style.overflow='';
    setNav('home');
  });
  document.getElementById('closeSearch').addEventListener('click', () => {
    document.getElementById('searchOverlay').classList.remove('active');
    document.body.style.overflow='';
    setNav('home');
  });

  document.getElementById('uploadFab').addEventListener('click', () => showToast('Upload coming soon! 🚀'));

  document.addEventListener('keydown', e => {
    if (e.key === 'Escape') closeAllOverlays();
  });

  renderSearchResults('');
}

/* ── UTILITIES ── */
function escHtml(str) {
  if (!str) return '';
  return str.replace(/[&<>"']/g, c=>({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[c]));
}
</script>
</body>
</html>
