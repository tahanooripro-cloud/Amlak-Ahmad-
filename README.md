<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>املاک احمد</title>
<meta name="theme-color" content="#1F3D3D">
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
<meta name="apple-mobile-web-app-title" content="املاک احمد">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Vazirmatn:wght@400;500;600;700;800&display=swap" rel="stylesheet">
<style>
  :root{
    --bg:#EFEAE0;
    --bg-alt:#F7F4EC;
    --ink:#1F2E2A;
    --ink-soft:#5B6B64;
    --primary:#1F3D3D;
    --primary-2:#2F5757;
    --accent:#B8863B;
    --accent-2:#D9AE5F;
    --card:#FFFFFF;
    --border:#E1D9C8;
    --danger:#B4483A;
    --success:#3E7A54;
    --radius:16px;
    --shadow: 0 6px 20px rgba(31,45,42,.08);
    --font: 'Vazirmatn', -apple-system, 'Segoe UI', Tahoma, sans-serif;
  }
  @media (prefers-color-scheme: dark){
    :root:not([data-theme="light"]){
      --bg:#141C1B; --bg-alt:#1A2321; --ink:#EDE8DB; --ink-soft:#AEB6AD;
      --primary:#4A7C79; --primary-2:#639191; --accent:#E0B463; --accent-2:#EDCB89;
      --card:#1E2926; --border:#31413C; --shadow: 0 6px 20px rgba(0,0,0,.35);
    }
  }
  :root[data-theme="dark"]{
    --bg:#141C1B; --bg-alt:#1A2321; --ink:#EDE8DB; --ink-soft:#AEB6AD;
    --primary:#4A7C79; --primary-2:#639191; --accent:#E0B463; --accent-2:#EDCB89;
    --card:#1E2926; --border:#31413C; --shadow: 0 6px 20px rgba(0,0,0,.35);
  }
  *{box-sizing:border-box;}
  html,body{margin:0;padding:0;}
  body{
    background:var(--bg); color:var(--ink); font-family:var(--font);
    min-height:100vh; -webkit-font-smoothing:antialiased;
    padding-bottom:78px;
  }
  .wrap{max-width:480px; margin:0 auto; min-height:100vh; background:var(--bg); position:relative; overflow-x:hidden;}
  .view{display:none; animation:fade .35s ease;}
  .view.active{display:block;}
  @keyframes fade{from{opacity:0; transform:translateY(6px);} to{opacity:1; transform:translateY(0);}}

  /* ---------- Header pattern ---------- */
  .hero{
    position:relative; padding:56px 24px 40px; text-align:center; overflow:hidden;
    background:linear-gradient(180deg, var(--primary) 0%, var(--primary-2) 100%);
    color:#F3EFE4; border-radius:0 0 28px 28px;
  }
  .hero svg.pattern{position:absolute; inset:0; width:100%; height:100%; opacity:.14;}
  .hero .mark{position:relative; width:80px; height:80px; margin:0 auto 16px; display:flex; align-items:center; justify-content:center;}
  .hero h1{position:relative; font-size:30px; font-weight:800; margin:0 0 8px; letter-spacing:.5px;}
  .hero p.tagline{position:relative; margin:0; font-size:15px; font-weight:500; color:var(--accent-2);}
  .hero-stats{position:relative; display:flex; justify-content:center; gap:10px; margin-top:22px;}
  .chip{background:rgba(243,239,228,.14); border:1px solid rgba(243,239,228,.3); border-radius:999px; padding:7px 14px; font-size:12.5px; font-weight:500;}

  .section-pad{padding:22px 20px 10px;}
  .section-title{font-size:17px; font-weight:700; margin:0 0 4px;}
  .section-sub{font-size:13px; color:var(--ink-soft); margin:0 0 16px;}

  .home-actions{display:flex; flex-direction:column; gap:12px; padding:0 20px 24px;}
  .action-card{
    display:flex; align-items:center; gap:14px; background:var(--card); border:1px solid var(--border);
    border-radius:var(--radius); padding:16px; box-shadow:var(--shadow); cursor:pointer; transition:transform .15s;
    text-align:right; width:100%;
  }
  .action-card:active{transform:scale(.98);}
  .action-icon{flex-shrink:0; width:44px; height:44px; border-radius:12px; background:var(--bg-alt); display:flex; align-items:center; justify-content:center; color:var(--primary);}
  .action-text b{display:block; font-size:14.5px; font-weight:700;}
  .action-text span{display:block; font-size:12.5px; color:var(--ink-soft); margin-top:2px;}

  /* ---------- Listings ---------- */
  .listing-header{display:flex; align-items:center; justify-content:space-between; padding:22px 20px 4px;}
  .btn{
    border:none; cursor:pointer; font-family:var(--font); font-weight:600; border-radius:12px;
    display:inline-flex; align-items:center; gap:6px; justify-content:center; transition:opacity .15s, transform .15s;
  }
  .btn:active{transform:scale(.97);}
  .btn-primary{background:var(--primary); color:#F3EFE4; padding:10px 16px; font-size:13.5px;}
  .btn-accent{background:var(--accent); color:#2A1E08; padding:10px 16px; font-size:13.5px;}
  .btn-ghost{background:var(--bg-alt); color:var(--ink); padding:10px 16px; font-size:13.5px; border:1px solid var(--border);}
  .btn-sm{padding:7px 12px; font-size:12px;}
  .btn-block{width:100%;}
  .btn-danger{background:transparent; color:var(--danger); border:1px solid var(--danger); padding:8px 12px; font-size:12.5px;}

  .filter-row{display:flex; gap:8px; padding:14px 20px 0; overflow-x:auto; scrollbar-width:none;}
  .filter-row::-webkit-scrollbar{display:none;}
  .filter-chip{flex-shrink:0; border:1px solid var(--border); background:var(--card); color:var(--ink-soft); font-family:var(--font); font-weight:600; font-size:12.5px; padding:8px 15px; border-radius:999px; cursor:pointer; white-space:nowrap; transition:background .15s,color .15s,border-color .15s;}
  .filter-chip.active{background:var(--primary); color:#F3EFE4; border-color:var(--primary);}
  .listings{padding:14px 20px 24px; display:flex; flex-direction:column; gap:16px;}
  .card{background:var(--card); border:1px solid var(--border); border-radius:var(--radius); overflow:hidden; box-shadow:var(--shadow);}
  .card-photo{position:relative; width:100%; aspect-ratio:16/10; background:linear-gradient(135deg,var(--primary),var(--primary-2)); display:flex; align-items:center; justify-content:center; overflow:hidden;}
  .card-photo img{width:100%; height:100%; object-fit:cover;}
  .card-photo .ph-icon{color:rgba(243,239,228,.55);}
  .badge{position:absolute; top:10px; right:10px; background:var(--accent); color:#2A1E08; font-size:11.5px; font-weight:700; padding:4px 10px; border-radius:999px;}
  .card-body{padding:14px 16px 16px;}
  .card-body h3{margin:0 0 6px; font-size:15.5px; font-weight:700;}
  .price{color:var(--accent); font-weight:800; font-size:14px; margin:0 0 8px;}
  .meta-row{display:flex; flex-wrap:wrap; gap:8px; margin-bottom:8px;}
  .meta-tag{font-size:11.5px; color:var(--ink-soft); background:var(--bg-alt); border-radius:8px; padding:4px 8px;}
  .desc{font-size:13px; color:var(--ink-soft); line-height:1.8; margin:0 0 10px;}
  .card-foot{display:flex; gap:8px; flex-wrap:wrap;}
  .empty{text-align:center; padding:50px 24px; color:var(--ink-soft);}
  .empty svg{opacity:.5; margin-bottom:12px;}

  /* ---------- Admin ---------- */
  .admin-bar{margin:0 20px 8px; padding:10px 14px; border-radius:12px; background:var(--bg-alt); border:1px dashed var(--border); font-size:12px; color:var(--ink-soft); display:flex; align-items:center; justify-content:space-between; gap:10px;}
  .modal-overlay{position:fixed; inset:0; background:rgba(15,20,19,.55); z-index:50; display:flex; align-items:flex-end; justify-content:center;}
  .modal-overlay.hidden{display:none;}
  .modal{width:100%; max-width:480px; background:var(--card); border-radius:22px 22px 0 0; padding:22px 20px 28px; max-height:88vh; overflow-y:auto; animation:slideUp .25s ease;}
  @keyframes slideUp{from{transform:translateY(30px); opacity:0;} to{transform:translateY(0); opacity:1;}}
  .modal h2{margin:0 0 4px; font-size:17px;}
  .modal p.hint{margin:0 0 18px; font-size:12.5px; color:var(--ink-soft);}
  .field{margin-bottom:14px;}
  .field label{display:block; font-size:12.5px; font-weight:600; margin-bottom:6px; color:var(--ink-soft);}
  .field input[type=text], .field input[type=tel], .field input[type=password], .field input[type=number], .field textarea, .field select{
    width:100%; padding:11px 13px; border-radius:10px; border:1px solid var(--border); background:var(--bg-alt); color:var(--ink);
    font-family:var(--font); font-size:14px;
  }
  .field textarea{resize:vertical; min-height:72px;}
  .row2{display:grid; grid-template-columns:1fr 1fr; gap:10px;}
  .upload-box{border:1.5px dashed var(--border); border-radius:12px; padding:14px; text-align:center; cursor:pointer; background:var(--bg-alt);}
  .upload-box input{display:none;}
  .thumbs{display:flex; gap:8px; flex-wrap:wrap; margin-top:10px;}
  .thumbs img{width:64px; height:64px; object-fit:cover; border-radius:10px; border:1px solid var(--border);}
  .modal-actions{display:flex; gap:10px; margin-top:18px;}
  .close-x{position:absolute; left:16px; top:16px; background:var(--bg-alt); border:none; width:32px; height:32px; border-radius:50%; display:flex; align-items:center; justify-content:center; cursor:pointer; color:var(--ink);}
  .modal{position:relative;}

  /* ---------- Contact ---------- */
  .contact-list{padding:14px 20px 24px; display:flex; flex-direction:column; gap:12px;}
  .contact-card{background:var(--card); border:1px solid var(--border); border-radius:var(--radius); padding:16px; box-shadow:var(--shadow); display:flex; align-items:center; gap:14px;}
  .avatar{width:48px; height:48px; border-radius:50%; background:var(--bg-alt); color:var(--primary); display:flex; align-items:center; justify-content:center; font-weight:800; font-size:16px; flex-shrink:0;}
  .contact-info{flex:1; min-width:0;}
  .contact-info b{display:block; font-size:14.5px;}
  .contact-info span{display:block; font-size:13px; color:var(--ink-soft); direction:ltr; text-align:right; margin-top:2px;}
  .contact-btns{display:flex; gap:6px; flex-shrink:0;}
  .icon-btn{width:38px; height:38px; border-radius:10px; border:1px solid var(--border); background:var(--bg-alt); display:flex; align-items:center; justify-content:center; color:var(--primary); cursor:pointer;}
  .addr-card{background:var(--card); border:1px solid var(--border); border-radius:var(--radius); padding:16px; box-shadow:var(--shadow);}
  .addr-card b{display:block; font-size:14px; margin-bottom:6px;}
  .addr-card p{margin:0 0 12px; font-size:13.5px; line-height:2; color:var(--ink-soft);}

  /* ---------- Message tab ---------- */
  .profile-card{margin:14px 20px; background:var(--card); border:1px solid var(--border); border-radius:var(--radius); padding:18px; box-shadow:var(--shadow); text-align:center;}
  .profile-photo{width:76px; height:76px; border-radius:50%; margin:0 auto 12px; background:var(--bg-alt); border:2px solid var(--border); display:flex; align-items:center; justify-content:center; overflow:hidden; color:var(--ink-soft); position:relative; cursor:pointer;}
  .profile-photo img{width:100%; height:100%; object-fit:cover;}
  .profile-photo input{display:none;}
  .form-block{padding:0 20px 24px;}
  .form-card{background:var(--card); border:1px solid var(--border); border-radius:var(--radius); padding:18px; box-shadow:var(--shadow);}
  .saved-tag{display:inline-flex; align-items:center; gap:6px; font-size:12px; color:var(--success); background:rgba(62,122,84,.1); padding:5px 10px; border-radius:999px; margin-top:6px;}
  .toast{position:fixed; bottom:96px; left:50%; transform:translateX(-50%); background:var(--ink); color:var(--bg); padding:10px 18px; border-radius:999px; font-size:13px; z-index:80; opacity:0; pointer-events:none; transition:opacity .25s, bottom .25s;}
  .toast.show{opacity:1; bottom:106px;}

  /* ---------- Bottom nav ---------- */
  .tabbar{
    position:fixed; bottom:0; left:50%; transform:translateX(-50%); width:100%; max-width:480px;
    background:var(--card); border-top:1px solid var(--border); display:flex; padding:8px 6px calc(8px + env(safe-area-inset-bottom));
    z-index:40; box-shadow:0 -6px 20px rgba(0,0,0,.06);
  }
  .tab-btn{flex:1; background:none; border:none; display:flex; flex-direction:column; align-items:center; gap:4px; padding:6px 2px; cursor:pointer; color:var(--ink-soft); font-family:var(--font);}
  .tab-btn svg{width:22px; height:22px;}
  .tab-btn span{font-size:11px; font-weight:600;}
  .tab-btn.active{color:var(--primary);}

  a{color:inherit;}
  ::selection{background:var(--accent-2); color:#2A1E08;}
</style>
</head>
<body>
<div class="wrap" id="app">

  <!-- ============ HOME ============ -->
  <section class="view active" id="view-home">
    <div class="hero">
      <svg class="pattern" viewBox="0 0 400 260" preserveAspectRatio="xMidYMid slice">
        <defs>
          <pattern id="star8" width="44" height="44" patternUnits="userSpaceOnUse" patternTransform="rotate(0)">
            <g fill="none" stroke="#F3EFE4" stroke-width="1">
              <path d="M22 2 L27 17 L42 22 L27 27 L22 42 L17 27 L2 22 L17 17 Z"/>
            </g>
          </pattern>
        </defs>
        <rect width="400" height="260" fill="url(#star8)"/>
      </svg>
      <div class="mark">
        <svg width="72" height="72" viewBox="0 0 100 100">
          <defs>
            <linearGradient id="ringGrad" x1="0" y1="0" x2="1" y2="1">
              <stop offset="0" stop-color="#E8C588"/>
              <stop offset="1" stop-color="#B8863B"/>
            </linearGradient>
          </defs>
          <circle cx="50" cy="50" r="47" fill="none" stroke="url(#ringGrad)" stroke-width="1.4" opacity=".9"/>
          <circle cx="50" cy="50" r="40" fill="rgba(243,239,228,.06)" stroke="rgba(243,239,228,.35)" stroke-width="1"/>
          <g stroke="url(#ringGrad)" fill="none">
            <circle cx="50" cy="7.5" r="2" fill="url(#ringGrad)" stroke="none"/>
            <circle cx="50" cy="92.5" r="2" fill="url(#ringGrad)" stroke="none"/>
            <circle cx="7.5" cy="50" r="2" fill="url(#ringGrad)" stroke="none"/>
            <circle cx="92.5" cy="50" r="2" fill="url(#ringGrad)" stroke="none"/>
          </g>
          <g transform="translate(50,47)">
            <path d="M-21 2 0 -16 21 2" fill="none" stroke="#F3EFE4" stroke-width="2.6" stroke-linecap="round" stroke-linejoin="round"/>
            <path d="M-14 -1 v22 a2 2 0 0 0 2 2 h8 v-13 a2 2 0 0 1 2-2 h4 a2 2 0 0 1 2 2 v13 h8 a2 2 0 0 0 2-2 v-22" fill="none" stroke="#F3EFE4" stroke-width="2.6" stroke-linecap="round" stroke-linejoin="round"/>
            <circle cx="0" cy="-2.5" r="2.4" fill="url(#ringGrad)"/>
          </g>
        </svg>
      </div>
      <h1>املاک احمد</h1>
      <p class="tagline">اعتماد شما سرمایه ماست</p>
      <div class="hero-stats">
        <span class="chip" id="homeListingCount">— ملک موجود</span>
        <span class="chip">خرمدره</span>
      </div>
    </div>

    <div class="section-pad">
      <p class="section-title">دسترسی سریع</p>
      <p class="section-sub">هر چی لازم دارید، همین‌جاست</p>
    </div>
    <div class="home-actions">
      <button class="action-card" onclick="goTo('listings')">
        <span class="action-icon">
          <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7" stroke-linecap="round" stroke-linejoin="round"><path d="M3 9.5 12 3l9 6.5V20a1 1 0 0 1-1 1h-5v-7H9v7H4a1 1 0 0 1-1-1Z"/></svg>
        </span>
        <span class="action-text"><b>موجودی‌های ما</b><span>دیدن ملک‌های ثبت‌شده با عکس و فیلم</span></span>
      </button>
      <button class="action-card" onclick="goTo('contact')">
        <span class="action-icon">
          <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7" stroke-linecap="round" stroke-linejoin="round"><path d="M4 5h3l2 5-2.5 1.5a11 11 0 0 0 5 5L13 14l5 2v3a2 2 0 0 1-2 2C9.5 21 3 14.5 3 7a2 2 0 0 1 1-2Z"/></svg>
        </span>
        <span class="action-text"><b>تماس با ما</b><span>شماره تلفن و آدرس دفتر</span></span>
      </button>
      <button class="action-card" onclick="goTo('message')">
        <span class="action-icon">
          <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7" stroke-linecap="round" stroke-linejoin="round"><path d="M4 4h16v13H7l-3 3Z"/></svg>
        </span>
        <span class="action-text"><b>پیام به ما</b><span>ساخت پروفایل و ارسال پیام</span></span>
      </button>
    </div>
  </section>

  <!-- ============ LISTINGS ============ -->
  <section class="view" id="view-listings">
    <div class="listing-header">
      <div>
        <p class="section-title" style="margin-bottom:2px;">موجودی‌های ما</p>
        <p class="section-sub" style="margin-bottom:0;" id="listingsSub">ملک‌های ثبت‌شده توسط املاک احمد</p>
      </div>
      <button class="btn btn-primary btn-sm" id="addListingBtn" onclick="onAddListingClick()">
        <svg width="15" height="15" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round"><path d="M12 5v14M5 12h14"/></svg>
        افزودن
      </button>
    </div>
    <div class="admin-bar" id="adminBar" style="display:none;">
      <span>🔓 حالت مدیریت فعال است — می‌توانید آگهی اضافه یا حذف کنید</span>
      <button class="btn btn-ghost btn-sm" onclick="lockAdmin()">خروج</button>
    </div>
    <div class="filter-row" id="filterRow"></div>
    <div class="listings" id="listingsWrap"></div>
  </section>

  <!-- ============ CONTACT ============ -->
  <section class="view" id="view-contact">
    <div class="section-pad">
      <p class="section-title">تماس با ما</p>
      <p class="section-sub">همیشه در دسترس شما هستیم</p>
    </div>
    <div class="contact-list">
      <div class="contact-card">
        <div class="avatar">ا.ن</div>
        <div class="contact-info">
          <b>احمد نوری</b>
          <span>09124417043</span>
        </div>
        <div class="contact-btns">
          <a class="icon-btn" href="tel:09124417043" aria-label="تماس">
            <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><path d="M4 5h3l2 5-2.5 1.5a11 11 0 0 0 5 5L13 14l5 2v3a2 2 0 0 1-2 2C9.5 21 3 14.5 3 7a2 2 0 0 1 1-2Z"/></svg>
          </a>
          <a class="icon-btn" href="sms:09124417043" aria-label="پیامک">
            <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><path d="M4 4h16v13H7l-3 3Z"/></svg>
          </a>
        </div>
      </div>
      <div class="contact-card">
        <div class="avatar">م.ت</div>
        <div class="contact-info">
          <b>محمد رضا تیموری</b>
          <span>09105732261</span>
        </div>
        <div class="contact-btns">
          <a class="icon-btn" href="tel:09105732261" aria-label="تماس">
            <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><path d="M4 5h3l2 5-2.5 1.5a11 11 0 0 0 5 5L13 14l5 2v3a2 2 0 0 1-2 2C9.5 21 3 14.5 3 7a2 2 0 0 1 1-2Z"/></svg>
          </a>
          <a class="icon-btn" href="sms:09105732261" aria-label="پیامک">
            <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><path d="M4 4h16v13H7l-3 3Z"/></svg>
          </a>
        </div>
      </div>
      <div class="addr-card">
        <b>📍 آدرس دفتر</b>
        <p>خرمدره، شهرک گلدشت، خیابان سعدی، روبروی فروشگاه هرمس</p>
        <a class="btn btn-accent btn-block" target="_blank" href="https://www.google.com/maps/search/?api=1&query=%D8%AE%D8%B1%D9%85%D8%AF%D8%B1%D9%87%20%D8%B4%D9%87%D8%B1%DA%A9%20%DA%AF%D9%84%D8%AF%D8%B4%D8%AA%20%D8%AE%DB%8C%D8%A7%D8%A8%D8%A7%D9%86%20%D8%B3%D8%B9%D8%AF%DB%8C">
          نمایش روی نقشه
        </a>
      </div>
    </div>
  </section>

  <!-- ============ MESSAGE ============ -->
  <section class="view" id="view-message">
    <div class="section-pad">
      <p class="section-title">پیام به ما</p>
      <p class="section-sub">پروفایلتان را بسازید تا 
