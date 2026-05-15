<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>SmileRenew — Internal Team Hub | SWR Dental & Wauchope Dental</title>
<link href="https://fonts.googleapis.com/css2?family=DM+Sans:ital,wght@0,300;0,400;0,500;0,600;1,400&family=DM+Serif+Display&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --teal:       #0F6E56;
    --teal-mid:   #1D9E75;
    --teal-light: #E1F5EE;
    --teal-dark:  #085041;
    --teal-muted: #B2DADA;
    --teal-pale:  #f0faf7;
    --text:       #1A2E2E;
    --muted:      #4a6060;
    --faint:      #7a9090;
    --bg:         #f5f9f8;
    --surface:    #ffffff;
    --surface2:   #f0f7f5;
    --border:     rgba(15,110,86,0.13);
    --border2:    rgba(15,110,86,0.22);
    --red-bg:     #fff5f3;
    --red-border: #e8a090;
    --red-text:   #7a3020;
    --shadow-sm:  0 1px 3px rgba(15,110,86,0.07), 0 3px 10px rgba(15,110,86,0.05);
    --radius:     10px;
    --radius-lg:  16px;
  }

  html { scroll-behavior: smooth; }
  body { font-family: 'DM Sans', sans-serif; background: var(--bg); color: var(--text); line-height: 1.6; font-size: 15px; }

  /* ── HEADER ── */
  .site-header { background: var(--teal); }
  .header-inner { max-width: 1000px; margin: 0 auto; padding: 1.75rem 1.5rem; }
  .header-top { display: grid; grid-template-columns: 1fr auto; align-items: start; gap: 2rem; margin-bottom: 1.25rem; }
  @media(max-width:600px){ .header-top { grid-template-columns: 1fr; } }
  .header-brand h1 { font-family: 'DM Serif Display', serif; font-size: clamp(30px,5vw,46px); color: #fff; font-weight: 400; line-height: 1.1; }
  .header-brand h1 sup { font-family: 'DM Sans',sans-serif; font-size:.4em; vertical-align:super; color:var(--teal-muted); }
  .header-brand .tagline { color: var(--teal-muted); font-size: 15px; margin-top: 5px; font-style: italic; }
  .header-brand .sub { color: rgba(255,255,255,.7); font-size: 13px; margin-top: 6px; }
  .badge-internal { display:inline-block; background:rgba(255,255,255,.12); border:1px solid rgba(255,255,255,.2); color:rgba(255,255,255,.85); font-size:11px; font-weight:500; padding:3px 10px; border-radius:99px; margin-top:10px; letter-spacing:.04em; }

  /* Practice cards in header */
  .practice-cards { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; }
  @media(max-width:500px){ .practice-cards { grid-template-columns: 1fr; } }
  .practice-card { background: rgba(255,255,255,0.1); border: 1px solid rgba(255,255,255,0.18); border-radius: var(--radius); padding: 12px 14px; }
  .practice-card .p-name { font-size: 13px; font-weight: 700; color: #fff; margin-bottom: 4px; }
  .practice-card .p-phone { font-size: 15px; font-weight: 700; color: #fff; margin-bottom: 3px; }
  .practice-card .p-detail { font-size: 11px; color: var(--teal-muted); }
  .practice-card a { color: var(--teal-muted); text-decoration: none; }
  .practice-card a:hover { color: #fff; }

  /* ── NAV ── */
  .site-nav { background: var(--teal-dark); position: sticky; top: 0; z-index: 100; }
  .nav-inner { max-width: 1000px; margin: 0 auto; display: flex; gap: 2px; padding: 0 1rem; overflow-x: auto; scrollbar-width: none; }
  .nav-inner::-webkit-scrollbar { display: none; }
  .nav-btn { background: none; border: none; color: rgba(255,255,255,.6); font-family: 'DM Sans',sans-serif; font-size: 13px; font-weight: 500; padding: 13px 16px; cursor: pointer; white-space: nowrap; border-bottom: 2px solid transparent; transition: all .15s; letter-spacing: .02em; }
  .nav-btn:hover { color: #fff; }
  .nav-btn.active { color: #fff; border-bottom-color: var(--teal-mid); }

  /* ── LAYOUT ── */
  .page-section { display: none; }
  .page-section.visible { display: block; animation: fadeUp .2s ease; }
  @keyframes fadeUp { from{opacity:0;transform:translateY(6px)} to{opacity:1;transform:translateY(0)} }
  .container { max-width: 1000px; margin: 0 auto; padding: 2rem 1.5rem 4rem; }

  /* ── COMMON ── */
  .intro-banner { background: var(--surface); border: 1px solid var(--border2); border-radius: var(--radius-lg); padding: 1.25rem 1.75rem; margin-bottom: 2rem; font-size: 15px; line-height: 1.75; }
  .intro-banner strong { color: var(--teal); }
  .section-head { font-size: 11px; font-weight: 700; text-transform: uppercase; letter-spacing: .1em; color: var(--teal-mid); margin-bottom: 12px; }
  .card { background: var(--surface); border: 1px solid var(--border); border-radius: var(--radius-lg); padding: 1.25rem 1.5rem; margin-bottom: 1rem; box-shadow: var(--shadow-sm); }
  .divider { border: none; border-top: 1px solid var(--border); margin: 2rem 0; }
  .spacer { height: 1.5rem; }
  .italic-note { font-size: 13px; color: var(--faint); font-style: italic; margin-bottom: 2rem; }

  /* ── STAGES ── */
  .stages { display: grid; grid-template-columns: repeat(5,1fr); gap: 10px; margin-bottom: 2rem; }
  @media(max-width:620px){ .stages { grid-template-columns: 1fr 1fr; } }
  .stage { background: var(--surface); border: 1px solid var(--border); border-radius: var(--radius-lg); overflow: hidden; box-shadow: var(--shadow-sm); }
  .stage-top { background: var(--teal); padding: 14px 10px 12px; text-align: center; }
  .stage-num { font-size: 22px; font-weight: 700; color: #fff; line-height: 1; }
  .stage-name { font-size: 12px; font-weight: 600; color: var(--teal-muted); margin-top: 4px; }
  .stage-desc { padding: 12px 10px; font-size: 12px; color: var(--muted); line-height: 1.5; text-align: center; }

  /* ── OPTIONS ── */
  .options-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 14px; margin-bottom: 1rem; }
  @media(max-width:560px){ .options-grid { grid-template-columns: 1fr; } }
  .option-card { background: var(--surface); border: 1px solid var(--border2); border-radius: var(--radius-lg); padding: 1.25rem 1.5rem; box-shadow: var(--shadow-sm); }
  .option-card.alt { background: var(--teal-pale); }
  .option-title { font-size: 14px; font-weight: 600; color: var(--teal-dark); margin-bottom: 8px; }
  .option-desc { font-size: 13px; color: var(--muted); line-height: 1.6; margin-bottom: 12px; }
  .option-price { font-size: 20px; font-weight: 700; color: var(--teal); margin-bottom: 4px; }
  .option-price span { font-size: 13px; font-weight: 400; color: var(--muted); }
  .option-sub { font-size: 13px; color: var(--muted); margin-bottom: 8px; }
  .option-note { font-size: 12px; color: var(--teal); font-style: italic; font-weight: 600; background: var(--teal-light); border-radius: 6px; padding: 6px 10px; border-left: 3px solid var(--teal-mid); }

  /* ── 3 COL ── */
  .three-col { display: grid; grid-template-columns: repeat(3,1fr); gap: 14px; margin-bottom: 2rem; }
  @media(max-width:640px){ .three-col { grid-template-columns: 1fr; } }
  .col-card { background: var(--surface); border: 1px solid var(--border); border-radius: var(--radius-lg); padding: 1.25rem; box-shadow: var(--shadow-sm); }
  .col-card.alt { background: var(--teal-pale); }
  .col-card h3 { font-size: 12px; font-weight: 700; text-transform: uppercase; letter-spacing: .07em; color: var(--teal); margin-bottom: 12px; }
  .col-card ul { list-style: none; }
  .col-card ul li { font-size: 13px; color: var(--muted); padding: 5px 0 5px 16px; position: relative; border-bottom: 1px solid var(--border); line-height: 1.5; }
  .col-card ul li:last-child { border-bottom: none; }
  .col-card ul li::before { content: "•"; color: var(--teal-mid); position: absolute; left: 0; }

  /* ── PRICING ── */
  .pricing-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 14px; margin-bottom: 2rem; }
  @media(max-width:600px){ .pricing-grid { grid-template-columns: 1fr; } }
  .pricing-card { background: var(--surface); border: 1px solid var(--border); border-radius: var(--radius-lg); padding: 1.25rem 1.5rem; box-shadow: var(--shadow-sm); }
  .pricing-card.alt { background: var(--teal-pale); }
  .pricing-card h3 { font-size: 12px; font-weight: 700; text-transform: uppercase; letter-spacing: .07em; color: var(--teal); margin-bottom: 14px; }
  .fee-item { display: flex; gap: 10px; padding: 9px 0; border-bottom: 1px solid var(--border); align-items: flex-start; }
  .fee-item:last-child { border-bottom: none; }
  .fee-info { flex: 1; min-width: 0; }
  .fee-label { font-size: 13px; font-weight: 600; color: var(--text); }
  .fee-desc { font-size: 12px; color: var(--muted); margin-top: 2px; line-height: 1.5; }
  .fee-amount { font-size: 13px; font-weight: 700; color: var(--teal); white-space: nowrap; padding-top: 1px; }
  .fee-bonus { font-size: 11px; color: var(--teal); font-style: italic; font-weight: 600; background: var(--teal-light); padding: 3px 8px; border-radius: 4px; display: inline-block; margin-top: 5px; }

  .entry-item { padding: 10px 0; border-bottom: 1px solid var(--border); }
  .entry-item:last-of-type { border-bottom: none; }
  .entry-num { display: inline-flex; align-items: center; justify-content: center; background: var(--teal); color: #fff; font-size: 11px; font-weight: 700; width: 20px; height: 20px; border-radius: 50%; margin-right: 7px; flex-shrink: 0; }
  .entry-title { font-size: 13px; font-weight: 600; color: var(--text); margin-bottom: 4px; display: flex; align-items: center; }
  .entry-desc { font-size: 13px; color: var(--muted); line-height: 1.5; padding-left: 27px; }
  .call-goal { margin-top: 14px; background: var(--teal); color: #fff; border-radius: var(--radius); padding: 12px 16px; font-size: 13px; font-weight: 600; line-height: 1.5; }

  /* ── CALL GUIDE ── */
  .scenario-tabs { display: grid; grid-template-columns: repeat(3,1fr); gap: 8px; margin-bottom: 1.25rem; }
  @media(max-width:560px){ .scenario-tabs { grid-template-columns: 1fr 1fr; } }
  .scen-btn { background: var(--surface); border: 1px solid var(--border); border-radius: var(--radius); padding: 9px 12px; font-family: 'DM Sans',sans-serif; font-size: 13px; cursor: pointer; color: var(--muted); text-align: left; transition: all .15s; line-height: 1.4; }
  .scen-btn:hover { border-color: var(--teal-mid); color: var(--teal-dark); background: var(--teal-light); }
  .scen-btn.active { background: var(--teal); border-color: var(--teal); color: #fff; font-weight: 600; }
  .script-panel { display: none; }
  .script-panel.visible { display: block; }

  .say { background: var(--teal-light); border-left: 3px solid var(--teal-mid); border-radius: 0 var(--radius) var(--radius) 0; padding: 14px 18px; margin: 10px 0; }
  .say-lbl { font-size: 10px; font-weight: 700; color: var(--teal); text-transform: uppercase; letter-spacing: .08em; margin-bottom: 6px; }
  .say p { font-size: 14px; color: var(--teal-dark); line-height: 1.75; font-style: italic; }
  .tip { background: #f7f7f5; border-left: 3px solid #d0d0cc; border-radius: 0 var(--radius) var(--radius) 0; padding: 12px 16px; margin: 10px 0; }
  .tip-lbl { font-size: 10px; font-weight: 700; color: var(--faint); text-transform: uppercase; letter-spacing: .08em; margin-bottom: 5px; }
  .tip p { font-size: 13px; color: var(--muted); line-height: 1.6; }

  /* ── Q&A ── */
  .qa-item { border-bottom: 1px solid var(--border); padding: 14px 0; }
  .qa-item:last-child { border-bottom: none; padding-bottom: 0; }
  .qa-q { font-size: 14px; font-weight: 600; color: var(--text); margin-bottom: 6px; }
  .qa-a { font-size: 14px; color: var(--muted); line-height: 1.65; }
  .qa-a strong { color: var(--text); font-weight: 600; }

  /* ── QUICK REF ── */
  .dont { background: var(--red-bg); border-left: 3px solid var(--red-border); border-radius: 0 var(--radius) var(--radius) 0; padding: 10px 14px; margin: 6px 0; }
  .dont p { font-size: 13px; color: var(--red-text); line-height: 1.5; }
  .pill-wrap { display: flex; gap: 7px; flex-wrap: wrap; margin-top: 10px; }
  .pill { font-size: 12px; padding: 5px 12px; border-radius: 99px; background: var(--surface2); border: 1px solid var(--border); color: var(--muted); }

  /* ── PRACTICE DETAILS (quick ref) ── */
  .practice-detail-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 14px; margin-top: 12px; }
  @media(max-width:560px){ .practice-detail-grid { grid-template-columns: 1fr; } }
  .pd-card { background: var(--teal-pale); border: 1px solid var(--border2); border-radius: var(--radius-lg); padding: 1rem 1.25rem; }
  .pd-card h4 { font-size: 13px; font-weight: 700; color: var(--teal); margin-bottom: 10px; border-bottom: 1px solid var(--border); padding-bottom: 8px; }
  .pd-row { display: flex; gap: 8px; padding: 5px 0; border-bottom: 1px solid var(--border); font-size: 13px; }
  .pd-row:last-child { border-bottom: none; }
  .pd-lbl { color: var(--faint); font-weight: 600; min-width: 80px; font-size: 12px; }
  .pd-val { color: var(--text); font-weight: 500; }

  /* ── AVATAR ── */
  .avatar-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 14px; }
  @media(max-width:600px){ .avatar-grid { grid-template-columns: 1fr; } }
  .avatar-card { background: var(--surface); border: 1px solid var(--border); border-radius: var(--radius-lg); padding: 1.25rem 1.5rem; box-shadow: var(--shadow-sm); }
  .avatar-card h3 { font-size: 12px; font-weight: 700; text-transform: uppercase; letter-spacing: .07em; color: var(--teal); margin-bottom: 12px; }
  .avatar-card ul { list-style: none; }
  .avatar-card ul li { font-size: 13px; color: var(--muted); padding: 5px 0 5px 16px; position: relative; border-bottom: 1px solid var(--border); line-height: 1.5; }
  .avatar-card ul li:last-child { border-bottom: none; }
  .avatar-card ul li::before { content: "•"; color: var(--teal-mid); position: absolute; left: 0; }
  .avatar-quote { background: var(--teal); color: #fff; border-radius: var(--radius-lg); padding: 1.5rem 1.5rem 1.5rem 2.5rem; font-style: italic; font-size: 14px; line-height: 1.75; margin-top: 14px; position: relative; }
  .avatar-quote::before { content: "\201C"; font-size: 52px; color: rgba(255,255,255,.2); position: absolute; top: 10px; left: 14px; line-height: 1; font-family: Georgia,serif; }

  .respond-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 14px; margin-top: 14px; }
  @media(max-width:560px){ .respond-grid { grid-template-columns: 1fr; } }
  .respond-card { background: var(--surface); border: 1px solid var(--border); border-radius: var(--radius-lg); padding: 1.25rem; box-shadow: var(--shadow-sm); }
  .respond-card.avoid { background: var(--red-bg); border-color: var(--red-border); }
  .respond-card h3 { font-size: 12px; font-weight: 700; text-transform: uppercase; letter-spacing: .07em; color: var(--teal); margin-bottom: 10px; }
  .respond-card.avoid h3 { color: var(--red-text); }
  .respond-card ul { list-style: none; }
  .respond-card ul li { font-size: 13px; padding: 5px 0 5px 18px; position: relative; border-bottom: 1px solid var(--border); line-height: 1.5; color: var(--muted); }
  .respond-card.avoid ul li { color: var(--red-text); border-color: rgba(232,160,144,.2); }
  .respond-card ul li:last-child { border-bottom: none; }
  .respond-card ul li::before { content: "✓"; color: var(--teal-mid); position: absolute; left: 0; font-size: 12px; font-weight: 700; }
  .respond-card.avoid ul li::before { content: "✗"; color: var(--red-border); }

  /* ── FOOTER ── */
  .site-footer { background: var(--teal-dark); color: var(--teal-muted); padding: 1.5rem; }
  .footer-inner { max-width: 1000px; margin: 0 auto; display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; align-items: center; }
  @media(max-width:500px){ .footer-inner { grid-template-columns: 1fr; text-align: center; } }
  .footer-practice { font-size: 13px; }
  .footer-practice strong { color: #fff; display: block; margin-bottom: 2px; }
  .footer-practice a { color: var(--teal-muted); text-decoration: none; font-size: 12px; }
  .footer-practice a:hover { color: #fff; }
  .footer-badge { text-align: right; font-size: 11px; color: rgba(255,255,255,.35); }
  @media(max-width:500px){ .footer-badge { text-align: center; } }

  /* ── TWO COL INFO ── */
  .two-col-info { display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; }
  @media(max-width:560px){ .two-col-info { grid-template-columns: 1fr; } }
  .mini-list { list-style: none; }
  .mini-list li { font-size: 13px; color: var(--muted); padding: 4px 0 4px 16px; position: relative; border-bottom: 1px solid var(--border); line-height: 1.5; }
  .mini-list li:last-child { border-bottom: none; }
  .mini-list li::before { content: "•"; color: var(--teal-mid); position: absolute; left: 0; }
  .mini-lbl { font-size: 11px; font-weight: 700; color: var(--teal); text-transform: uppercase; letter-spacing: .07em; margin-bottom: 8px; }
</style>
</head>
<body>

<!-- ── HEADER ── -->
<header class="site-header">
  <div class="header-inner">
    <div class="header-top">
      <div class="header-brand">
        <h1>SmileRenew<sup>™</sup></h1>
        <div class="tagline">Your Smile, Thoughtfully Restored</div>
        <div class="sub">Our named, trademarked signature dental rehabilitation process</div>
        <span class="badge-internal">Internal Team Resource</span>
      </div>
      <div style="text-align:right;">
        <div style="font-size:11px; font-weight:600; text-transform:uppercase; letter-spacing:.08em; color:var(--teal-muted); margin-bottom:8px;">Our Practices</div>
        <div class="practice-cards">
          <div class="practice-card">
            <div class="p-name">SWR Dental</div>
            <div class="p-phone">(02) 6566 6070</div>
            <div class="p-detail"><a href="https://swrdental.com.au" target="_blank">swrdental.com.au</a></div>
            <div class="p-detail">South West Rocks</div>
          </div>
          <div class="practice-card">
            <div class="p-name">Wauchope Dental</div>
            <div class="p-phone">(02) 6586 0007</div>
            <div class="p-detail"><a href="https://wauchopedental.net.au" target="_blank">wauchopedental.net.au</a></div>
            <div class="p-detail">65 High Street, Wauchope</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</header>

<!-- ── NAV ── -->
<nav class="site-nav">
  <div class="nav-inner">
    <button class="nav-btn active" onclick="showSection('overview',this)">Overview</button>
    <button class="nav-btn" onclick="showSection('pricing',this)">Pricing & Pathways</button>
    <button class="nav-btn" onclick="showSection('callguide',this)">Call Guide</button>
    <button class="nav-btn" onclick="showSection('questions',this)">Common Questions</button>
    <button class="nav-btn" onclick="showSection('quickref',this)">Quick Reference</button>
    <button class="nav-btn" onclick="showSection('avatar',this)">Patient Avatar</button>
  </div>
</nav>

<!-- ════════ OVERVIEW ════════ -->
<div class="page-section visible" id="sec-overview">
<div class="container">

  <div class="intro-banner">
    Too many people live with worn, broken or embarrassing teeth — patched up over time with no clear long-term plan. <strong>SmileRenew changes that.</strong> It's our named, trademarked signature process delivering a structured, phased pathway from patchwork dentistry to a confident, functional, healthy smile. <strong>Function first, aesthetics too</strong> — at a pace that suits the patient. Available at both <strong>SWR Dental</strong> and <strong>Wauchope Dental</strong>.
  </div>

  <div class="section-head">The 5-Stage Pathway</div>
  <div class="stages">
    <div class="stage"><div class="stage-top"><div class="stage-num">1</div><div class="stage-name">Understand</div></div><div class="stage-desc">Records, photos & digital scans — full assessment of bite, wear patterns & long-term needs</div></div>
    <div class="stage"><div class="stage-top"><div class="stage-num">2</div><div class="stage-name">Plan</div></div><div class="stage-desc">Your smile blueprint — digitally co-designed balancing function, aesthetics & long-term goals</div></div>
    <div class="stage"><div class="stage-top"><div class="stage-num">3</div><div class="stage-name">Preview</div></div><div class="stage-desc">Try-in your new smile — test the function, look and feel before committing to anything</div></div>
    <div class="stage"><div class="stage-top"><div class="stage-num">4</div><div class="stage-name">Provisionalise</div></div><div class="stage-desc">Custom composite smile via injection moulding — live with it for years at a fraction of porcelain cost</div></div>
    <div class="stage"><div class="stage-top"><div class="stage-num">5</div><div class="stage-name">Porcelain</div></div><div class="stage-desc">Optional upgrade — handcrafted porcelain restorations, beautiful and durable for life ahead</div></div>
  </div>

  <div class="section-head">Two Treatment Paths</div>
  <div class="options-grid">
    <div class="option-card alt">
      <div class="option-title">Option A — Composite (Provisionalise)</div>
      <div class="option-desc">Custom composite smile via injection moulding. More affordable and less invasive — live with and enjoy your restored smile for years. Clinically valid as a long-term solution on its own.</div>
      <div class="option-price">$485 <span>per tooth</span></div>
      <div class="option-sub">+ Splint $750 (if required)</div>
      <div class="option-note">Upgrade to porcelain within 2 years → 50% of composite cost applied to upgrade</div>
    </div>
    <div class="option-card">
      <div class="option-title">Option B — Porcelain (Optional Final Step)</div>
      <div class="option-desc">Handcrafted porcelain restorations for longevity and a natural, beautiful result. Taken entirely at the patient's own pace — months or years after the prototype if they choose.</div>
      <div class="option-price">$1,715 <span>per tooth</span></div>
      <div class="option-sub">+ Splint $750 (if required)</div>
      <div class="option-note">Blueprint cost ($45/tooth, capped at $500) credited toward splint fee at end of treatment</div>
    </div>
  </div>
  <p class="italic-note">Many patients stay at composite long-term — it is clinically valid on its own. The path to porcelain is always the patient's choice, taken at their own pace.</p>

  <hr class="divider">
  <div class="section-head">Who It's For &nbsp;·&nbsp; Benefits &nbsp;·&nbsp; Why Us</div>
  <div class="three-col">
    <div class="col-card alt">
      <h3>Who Is It For?</h3>
      <ul>
        <li>Living with worn, broken or heavily restored teeth</li>
        <li>Tired of patch repairs with no long-term plan</li>
        <li>Embarrassed by their smile or avoiding photos</li>
        <li>Struggling to eat comfortably — or missing teeth</li>
        <li>Ready to invest in themselves and want a plan they can trust</li>
      </ul>
    </div>
    <div class="col-card">
      <h3>How It Benefits Them</h3>
      <ul>
        <li>A clear, structured pathway — no more guessing</li>
        <li>Test-drive the result before committing to porcelain</li>
        <li>Affordable entry via composite — upgrade on their terms</li>
        <li>Natural, age-appropriate results — not "done"</li>
        <li>Guided every step, never pressured</li>
      </ul>
    </div>
    <div class="col-card alt">
      <h3>Why Choose Us</h3>
      <ul>
        <li>Named, trademarked process — proven and consistent</li>
        <li>Prototype-first — confidence before commitment</li>
        <li>Transparent pricing with itemised guide at consultation</li>
        <li>Payment plans available</li>
        <li>SmileRenew certified providers only</li>
        <li>Available locally at both SWR Dental & Wauchope Dental</li>
      </ul>
    </div>
  </div>
</div>
</div>

<!-- ════════ PRICING & PATHWAYS ════════ -->
<div class="page-section" id="sec-pricing">
<div class="container">
  <div class="intro-banner">
    All patients receive an <strong>itemised private price guide at their CDA</strong> — no surprises, no pressure. Pricing is the same across both practices. Payment plans and finance options are available. <strong>Never quote a specific total over the phone</strong> — always direct to the consultation.
  </div>

  <div class="section-head">Full Fee Schedule — Both Practices</div>
  <div class="pricing-grid">
    <div class="pricing-card alt">
      <h3>Consultation & Planning</h3>
      <div class="fee-item">
        <div class="fee-info"><div class="fee-label">Free 20-min SmileRenew Consult</div><div class="fee-desc">Brief discussion of possibilities — easiest first step for marketing enquiries. No obligation.</div></div>
        <div class="fee-amount">Free</div>
      </div>
      <div class="fee-item">
        <div class="fee-info"><div class="fee-label">CDA — Comprehensive Dental Assessment</div><div class="fee-desc">Required for all SmileRenew patients. Full records; plan defined here or at second consult.</div></div>
        <div class="fee-amount">$199</div>
      </div>
      <div class="fee-item">
        <div class="fee-info"><div class="fee-label">Blueprint (Wax-up)</div><div class="fee-desc">Most cases need design work.<div class="fee-bonus">Blueprint cost credited toward splint fee at end of treatment</div></div></div>
        <div class="fee-amount">$45<br><span style="font-size:11px;font-weight:400">/tooth<br>cap $500</span></div>
      </div>
      <div class="fee-item">
        <div class="fee-info"><div class="fee-label">Splint</div><div class="fee-desc">Part of most cases.</div></div>
        <div class="fee-amount">$750</div>
      </div>
    </div>

    <div class="pricing-card">
      <h3>Treatment Fees</h3>
      <div class="fee-item">
        <div class="fee-info"><div class="fee-label">Composite — Injection Moulding</div><div class="fee-desc">Per tooth. A great long-term option on its own.<div class="fee-bonus">Upgrade within 2 yrs → 50% of composite cost off porcelain</div></div></div>
        <div class="fee-amount">$485<br><span style="font-size:11px;font-weight:400">/tooth</span></div>
      </div>
      <div class="fee-item">
        <div class="fee-info"><div class="fee-label">Porcelain Restorations</div><div class="fee-desc">Per tooth. Handcrafted, long-lasting, the definitive result.</div></div>
        <div class="fee-amount">$1,715<br><span style="font-size:11px;font-weight:400">/tooth</span></div>
      </div>
      <div class="fee-item">
        <div class="fee-info"><div class="fee-label">Implants</div><div class="fee-desc">Per implant.</div></div>
        <div class="fee-amount">$5,500–$7,500</div>
      </div>
      <div class="fee-item">
        <div class="fee-info"><div class="fee-label">Teeth on Implants (fixed)</div></div>
        <div class="fee-amount">$28,000</div>
      </div>
      <div class="fee-item">
        <div class="fee-info"><div class="fee-label">Implant-retained Lower Denture</div><div class="fee-desc">+ Denture costs (Port Denture Clinic)</div></div>
        <div class="fee-amount">$6,500+</div>
      </div>
    </div>
  </div>

  <hr class="divider">
  <div class="section-head">How Patients Enter SmileRenew</div>
  <div class="card">
    <div class="entry-item">
      <div class="entry-title"><span class="entry-num">1</span>Internal Referral (RDM / CDA)</div>
      <div class="entry-desc">A regular patient raises concerns during a recall. Team identifies they'd benefit from comprehensive care and introduces SmileRenew. Book a CDA with a participating provider at either practice.</div>
    </div>
    <div class="entry-item">
      <div class="entry-title"><span class="entry-num">2</span>SmileRenew Requested Directly</div>
      <div class="entry-desc">Patient has heard about SmileRenew and calls requesting it. Book a CDA with a participating provider and take records.</div>
    </div>
    <div class="entry-item">
      <div class="entry-title"><span class="entry-num">3</span>Marketing Enquiry — Free 20-min Consult</div>
      <div class="entry-desc">Patient saw an ad or post and calls to find out more. Offer the free 20-min consult first — the easiest yes. If they want the full picture, book the CDA and quote $199.</div>
    </div>
    <div class="call-goal">Goal of every call: book an appointment. The free 20-min consult is always the easiest yes for a new enquiry.</div>
  </div>

  <hr class="divider">
  <div class="section-head">Treatment Planning — How We Assess</div>
  <div class="three-col">
    <div class="col-card alt"><h3>We Assess By</h3><ul><li>Health</li><li>Longevity</li><li>Aesthetics</li></ul></div>
    <div class="col-card"><h3>Options for Worn Teeth</h3><ul><li>Bare minimum — patch erosion, splint, diet & OHI</li><li>Injection moulding (composite)</li><li>Strong long-term porcelain rehabilitation</li></ul></div>
    <div class="col-card alt"><h3>Suitable Cases</h3><ul><li>Heavily restored or worn dentition</li><li>Full mouth rehabilitation</li><li>Anterior aesthetic work</li><li>Implants, All-on-X</li><li>Any case needing structure & a long-term plan</li></ul></div>
  </div>
</div>
</div>

<!-- ════════ CALL GUIDE ════════ -->
<div class="page-section" id="sec-callguide">
<div class="container">
  <div class="intro-banner">
    Use the scenarios below for real calls at either practice. <strong>Green blocks are suggested scripts</strong> you can read directly. Grey blocks are coaching notes. The goal of every call: <strong>book an appointment.</strong>
  </div>

  <div class="section-head">Choose a Scenario</div>
  <div class="scenario-tabs">
    <button class="scen-btn active" onclick="showScript('general',this)">General enquiry</button>
    <button class="scen-btn" onclick="showScript('marketing',this)">Came from an ad</button>
    <button class="scen-btn" onclick="showScript('cost',this)">Asking about cost</button>
    <button class="scen-btn" onclick="showScript('nervous',this)">Nervous or hesitant</button>
    <button class="scen-btn" onclick="showScript('existing',this)">Existing patient</button>
    <button class="scen-btn" onclick="showScript('book',this)">Ready to book</button>
  </div>

  <div class="script-panel visible card" id="sp-general">
    <div class="say"><div class="say-lbl">Open with</div><p>"Thanks for calling about SmileRenew — great that you've reached out. SmileRenew is our signature process for adults who want to properly restore their smile, rather than just patch things up one tooth at a time. It's a clear, staged plan from start to finish. Can I ask — what's been going on with your teeth that prompted you to call today?"</p></div>
    <div class="tip"><div class="tip-lbl">Why ask that?</div><p>Getting them to describe their situation lets you listen and reflect their words back. You're not selling — you're understanding. Let them talk first before you explain anything.</p></div>
    <div class="say"><div class="say-lbl">Move toward booking</div><p>"The easiest starting point is our free 20-minute SmileRenew chat — completely relaxed, no obligation. Or if you'd like the full picture with records and a personalised price guide, we can book a comprehensive assessment. Which sounds right for you?"</p></div>
  </div>

  <div class="script-panel card" id="sp-marketing">
    <div class="say"><div class="say-lbl">Acknowledge where they came from</div><p>"Wonderful — glad that caught your eye! SmileRenew is our signature smile restoration process. It's designed for people who are tired of one-off repairs and want a proper long-term plan. What drew you to it — was it the process itself, or something specific about your own situation?"</p></div>
    <div class="tip"><div class="tip-lbl">Key point for marketing calls</div><p>These patients are at the awareness stage — curious but not yet committed. Make the next step feel easy and low-risk. Lead with the free 20-min consult. Emphasise "no pressure, nothing happens on the day."</p></div>
    <div class="say"><div class="say-lbl">Offer the free consult</div><p>"The easiest place to start is our free 20-minute SmileRenew consult — it's just a relaxed conversation with the dentist to explore what's possible for you. No treatment, no obligation. Would you like to get that locked in?"</p></div>
  </div>

  <div class="script-panel card" id="sp-cost">
    <div class="say"><div class="say-lbl">Acknowledge honestly</div><p>"That's a great question and completely understandable. We don't quote a total price over the phone because every SmileRenew plan is individual. What we do is give you a full itemised price guide at your consultation, so you see every cost laid out before committing to anything."</p></div>
    <div class="tip"><div class="tip-lbl">If they push for a ballpark</div><p>Acknowledge warmly without giving a total: "I completely understand. What I can say is we have two main paths — composite starting at $485 per tooth, and an optional porcelain step at $1,715 per tooth. The consultation gives you the exact picture for your specific situation, and payment plans are also available."</p></div>
    <div class="say"><div class="say-lbl">Mention payment plans</div><p>"We also have staged payment and finance options, so many patients don't pay for everything upfront. The consultation is really the right place to map all of that out — would that work for you?"</p></div>
  </div>

  <div class="script-panel card" id="sp-nervous">
    <div class="say"><div class="say-lbl">Validate first — don't rush</div><p>"That makes complete sense. A lot of people who call us have been putting this off for years — often because past dental experiences have felt rushed or overwhelming. SmileRenew is designed around the opposite of that."</p></div>
    <div class="say"><div class="say-lbl">Reassure about what happens</div><p>"The first step is just a conversation — the dentist listens, takes some records if you're comfortable, and walks you through what's possible. Nothing is decided on the day. Some people come in and decide to get some general dentistry sorted first — that's completely fine. It's really just about getting clarity."</p></div>
    <div class="tip"><div class="tip-lbl">Tone note</div><p>Slow down your own pace on this call. A calm, warm voice does more than any script. Let there be pauses. Don't rush to fill silence. The patient needs to feel safe before they'll book.</p></div>
  </div>

  <div class="script-panel card" id="sp-existing">
    <div class="say"><div class="say-lbl">Acknowledge the relationship</div><p>"Wonderful — so glad you're thinking about this. SmileRenew is something we've developed to give existing patients a proper long-term plan, rather than continuing to treat things one at a time. Because you're already with us, your dentist will have context on your history which makes the consultation even more useful."</p></div>
    <div class="tip"><div class="tip-lbl">Key difference for existing patients</div><p>They likely have records on file — the consultation builds on what the team already knows. The SmileRenew consult is a dedicated appointment, separate from a regular check-up.</p></div>
    <div class="say"><div class="say-lbl">Invite them in</div><p>"The SmileRenew consultation is a dedicated appointment — separate from your regular check-up — where we look at the full picture and map out a proper plan together. Would you like me to get that scheduled?"</p></div>
  </div>

  <div class="script-panel card" id="sp-book">
    <div class="say"><div class="say-lbl">Make it easy</div><p>"Perfect — let's get that locked in. The SmileRenew consultation is a private, one-to-one appointment with the dentist. I just need a few details and we'll find a time that works. What days generally suit you best?"</p></div>
    <div class="tip"><div class="tip-lbl">Before you hang up — confirm these</div><p>Name and contact number · Which practice (SWR Dental or Wauchope Dental) · Date and time confirmed · Tell them: "You don't need to bring anything — just come as you are." Send a confirmation text or email after the call.</p></div>
  </div>
</div>
</div>

<!-- ════════ COMMON QUESTIONS ════════ -->
<div class="page-section" id="sec-questions">
<div class="container">
  <div class="intro-banner">
    Know these answers confidently — patients ask these on the phone, after seeing an ad, or at the free consult. These apply across both SWR Dental and Wauchope Dental.
  </div>
  <div class="card">
    <div class="qa-item"><div class="qa-q">How long does the whole process take?</div><div class="qa-a">Consultation to composite prototype is typically <strong>4–8 weeks</strong> over a few short visits. Porcelain — if chosen — is on the patient's own timeline. Could be months, could be years. No pressure.</div></div>
    <div class="qa-item"><div class="qa-q">Do I have to do the porcelain step?</div><div class="qa-a">No. <strong>The composite prototype is a clinically valid long-term solution on its own.</strong> Many patients stay at that stage. Whether to go to porcelain is a decision made together with the dentist.</div></div>
    <div class="qa-item"><div class="qa-q">What does it cost?</div><div class="qa-a">The free 20-min consult is free. The CDA is $199. Composite is <strong>$485 per tooth</strong>; porcelain is <strong>$1,715 per tooth</strong>. Blueprint is $45/tooth capped at $500 and is credited toward the splint fee. Full itemised guide provided at the CDA. Payment plans available. <strong>Pricing is the same at both practices.</strong></div></div>
    <div class="qa-item"><div class="qa-q">If I start with composite and upgrade later, do I lose that money?</div><div class="qa-a"><strong>No — upgrade within 2 years and 50% of the composite cost is applied toward the porcelain.</strong> It rewards patients who choose to progress, not penalise them for starting affordably.</div></div>
    <div class="qa-item"><div class="qa-q">Is it suitable if I have missing teeth?</div><div class="qa-a">Yes. Missing teeth are common and often part of the plan. <strong>Implants or bridges may be needed</strong> as part of the pathway — the consultation maps this out individually.</div></div>
    <div class="qa-item"><div class="qa-q">What actually happens at the consultation?</div><div class="qa-a">Relaxed one-to-one session. Records, photos, digital scans taken. Dentist walks through all five stages and provides a <strong>personalised itemised price guide</strong>. No treatment starts — it's a planning conversation only.</div></div>
    <div class="qa-item"><div class="qa-q">Is there any pressure to proceed?</div><div class="qa-a"><strong>None at all.</strong> Some patients take information away and come back later. Some sort general dentistry first. The pace is entirely theirs.</div></div>
    <div class="qa-item"><div class="qa-q">Can I pay in instalments?</div><div class="qa-a">Yes. <strong>Finance and staged payment options are available.</strong> Discussed at the CDA alongside the full price guide.</div></div>
    <div class="qa-item"><div class="qa-q">Is this just cosmetic dentistry?</div><div class="qa-a">No — <strong>function comes first.</strong> SmileRenew is for anyone with a worn, broken or heavily restored dentition who needs a proper long-term plan. Aesthetics are part of it, but the primary goal is comfortable, healthy, functional teeth.</div></div>
    <div class="qa-item"><div class="qa-q">Which practice should I go to?</div><div class="qa-a">SmileRenew is available at both <strong>SWR Dental in South West Rocks</strong> and <strong>Wauchope Dental</strong>. The patient can choose whichever is most convenient for them — the process and pricing are identical at both.</div></div>
  </div>
</div>
</div>

<!-- ════════ QUICK REFERENCE ════════ -->
<div class="page-section" id="sec-quickref">
<div class="container">
  <div class="section-head">Always Say These Things</div>
  <div class="card">
    <div class="say"><p>"No treatment on day one — the consultation is just a conversation."</p></div>
    <div class="say"><p>"You'll receive a full itemised price guide before committing to anything."</p></div>
    <div class="say"><p>"The pace is entirely yours — porcelain is always optional."</p></div>
    <div class="say"><p>"We have payment plans and finance options available."</p></div>
    <div class="say"><p>"The free 20-min consult is the easiest first step — no obligation at all."</p></div>
    <div class="say"><p>"SmileRenew is available at both our South West Rocks and Wauchope practices."</p></div>
  </div>

  <div class="spacer"></div>
  <div class="section-head">Never Say These Things</div>
  <div class="card">
    <div class="dont"><p>"It'll cost around $X total..." — never quote a total over the phone. Direct to the consultation for the full itemised guide.</p></div>
    <div class="dont"><p>"It fixes everything" or "guaranteed results" — outcomes are individual. Always be honest.</p></div>
    <div class="dont"><p>"You have to do the porcelain step" — porcelain is always optional and always the patient's choice.</p></div>
    <div class="dont"><p>Rushing the patient — calm and patience are core to SmileRenew. Let them take their time.</p></div>
    <div class="dont"><p>"Veneers", "cosmetic package" or "rebuild" — focus on renewal, guidance and phased transformation.</p></div>
  </div>

  <div class="spacer"></div>
  <div class="section-head">Key Financial Benefits to Know</div>
  <div class="options-grid">
    <div class="option-card alt">
      <div class="option-title">Composite → Porcelain Upgrade</div>
      <div class="option-desc">Patients who upgrade to porcelain within 2 years get <strong>50% of the composite cost applied toward the porcelain</strong>. Reduces the fear of "starting with composite and losing that money."</div>
    </div>
    <div class="option-card">
      <div class="option-title">Blueprint Cost Credited</div>
      <div class="option-desc">Blueprint (wax-up) cost of $45/tooth capped at $500 <strong>comes off the splint fee</strong> at end of treatment. The design work invested early counts toward their overall costs.</div>
    </div>
  </div>

  <div class="spacer"></div>
  <div class="section-head">Practice Details</div>
  <div class="practice-detail-grid">
    <div class="pd-card">
      <h4>SWR Dental — South West Rocks</h4>
      <div class="pd-row"><span class="pd-lbl">Phone</span><span class="pd-val">(02) 6566 6070</span></div>
      <div class="pd-row"><span class="pd-lbl">Website</span><span class="pd-val">swrdental.com.au</span></div>
      <div class="pd-row"><span class="pd-lbl">Hours</span><span class="pd-val">Mon–Fri, 8am–6pm</span></div>
      <div class="pd-row"><span class="pd-lbl">Free Consult</span><span class="pd-val">20 min · No obligation</span></div>
      <div class="pd-row"><span class="pd-lbl">CDA Fee</span><span class="pd-val">$199</span></div>
      <div class="pd-row"><span class="pd-lbl">Payment Plans</span><span class="pd-val">Available — discuss at CDA</span></div>
    </div>
    <div class="pd-card">
      <h4>Wauchope Dental — Wauchope</h4>
      <div class="pd-row"><span class="pd-lbl">Phone</span><span class="pd-val">(02) 6586 0007</span></div>
      <div class="pd-row"><span class="pd-lbl">Website</span><span class="pd-val">wauchopedental.net.au</span></div>
      <div class="pd-row"><span class="pd-lbl">Address</span><span class="pd-val">65 High Street, Wauchope</span></div>
      <div class="pd-row"><span class="pd-lbl">Free Consult</span><span class="pd-val">20 min · No obligation</span></div>
      <div class="pd-row"><span class="pd-lbl">CDA Fee</span><span class="pd-val">$199</span></div>
      <div class="pd-row"><span class="pd-lbl">Payment Plans</span><span class="pd-val">Available — discuss at CDA</span></div>
    </div>
  </div>

  <div class="spacer"></div>
  <div class="section-head">Who Is a Good Fit?</div>
  <div class="card">
    <div class="pill-wrap">
      <span class="pill">Worn or broken teeth</span>
      <span class="pill">Tired of repeated patch repairs</span>
      <span class="pill">Avoiding photos</span>
      <span class="pill">Struggling to eat comfortably</span>
      <span class="pill">Has missing teeth</span>
      <span class="pill">Wants a long-term plan</span>
      <span class="pill">Wants transparent upfront pricing</span>
      <span class="pill">Has been putting it off for years</span>
      <span class="pill">Values being guided, not sold to</span>
      <span class="pill">50–75 age group (primary)</span>
    </div>
  </div>
</div>
</div>

<!-- ════════ PATIENT AVATAR ════════ -->
<div class="page-section" id="sec-avatar">
<div class="container">
  <div class="intro-banner">
    Understanding our primary patient helps the whole team — at both practices — speak their language on the phone, in the chair, and in marketing.
  </div>

  <div class="section-head">Primary Avatar — "The Renewal Seeker" &nbsp;·&nbsp; Anne or Peter, ~63</div>
  <div class="card" style="margin-bottom:1rem;">
    <div class="two-col-info">
      <div>
        <div class="mini-lbl">Who They Are</div>
        <ul class="mini-list">
          <li>Retired or semi-retired — teacher, nurse, business owner</li>
          <li>Lives locally — South West Rocks, Wauchope or surrounds</li>
          <li>Owns home, modestly comfortable financially</li>
          <li>Family-oriented — possibly becoming grandparents</li>
          <li>Invests in quality — health, good food, independence</li>
          <li>Focused on aging well and maintaining independence</li>
        </ul>
      </div>
      <div>
        <div class="mini-lbl">Their Dental Situation</div>
        <ul class="mini-list">
          <li>Multiple old restorations and crowns</li>
          <li>Ongoing frustration — patch repairs, broken fillings, tooth loss</li>
          <li>Has been told "we'll just watch that" for years</li>
          <li>Overwhelmed — unsure how to finally fix it properly</li>
          <li>May have a partial denture they hate, or frequent chipping</li>
          <li>Open to looking and functioning better — finally</li>
        </ul>
      </div>
    </div>
  </div>

  <div class="avatar-grid">
    <div class="avatar-card">
      <h3>Goals & Mindset</h3>
      <ul>
        <li>Wants to feel proud of their smile — without looking "done"</li>
        <li>Wants to eat comfortably, smile freely, be proactive about aging</li>
        <li>Values being listened to — not rushed or sold to</li>
        <li>Prefers a plan they can understand and trust, with stages</li>
        <li>Would rather invest in one quality solution than more repairs</li>
      </ul>
    </div>
    <div class="avatar-card">
      <h3>Barriers & Concerns</h3>
      <ul>
        <li>Fear of cost or overcommitment</li>
        <li>Fear that cosmetic dentistry will look fake or too young</li>
        <li>Bad past dental experiences</li>
        <li>Doesn't know a structured process like this exists</li>
        <li>Worried composite is "wasted" money if they upgrade later</li>
      </ul>
    </div>
  </div>

  <div class="avatar-quote">
    "It's not just about looks — it's about feeling whole again. The process made it easy to understand what I needed, and the prototype gave me time to adjust before moving to the final result. It's the first time I've felt I'm getting a real solution."
  </div>

  <div class="spacer"></div>
  <div class="section-head">What They Respond To vs What Puts Them Off</div>
  <div class="respond-grid">
    <div class="respond-card">
      <h3>What Attracts Them</h3>
      <ul>
        <li>Words: "restore," "renew," "confidence," "function," "natural," "guided journey"</li>
        <li>Seeing people their age in real stories and content</li>
        <li>Being offered control — test-drive with prototype before porcelain</li>
        <li>Clinician confidence combined with warmth — not overselling</li>
        <li>Clear stages and transparent pricing — no surprises</li>
        <li>Payment plans that make it feel achievable</li>
      </ul>
    </div>
    <div class="respond-card avoid">
      <h3>What Puts Them Off</h3>
      <ul>
        <li>Feeling rushed or sold to — they need to feel guided</li>
        <li>Words like "veneers," "cosmetic package," "rebuild"</li>
        <li>Vague answers about cost — they want transparency</li>
        <li>Looking "too done" — they want natural, age-appropriate</li>
        <li>Cold or clinical language — warmth matters enormously</li>
        <li>No clear pathway — more patch repairs are their biggest fear</li>
      </ul>
    </div>
  </div>

  <div class="spacer"></div>
  <div class="section-head">Audience Segments</div>
  <div class="three-col">
    <div class="col-card alt">
      <h3>50–75 · Primary</h3>
      <ul><li>Worn dentitions & years of patchwork</li><li>Function + aesthetics</li><li>Investing in themselves at this stage</li><li>Core "Renewal Seeker" avatar</li></ul>
    </div>
    <div class="col-card">
      <h3>35–45 · Secondary</h3>
      <ul><li>Mild wear, early interceptive work</li><li>Conservative makeover</li><li>Starting to notice wear — not at crisis point yet</li></ul>
    </div>
    <div class="col-card alt">
      <h3>25–35 · Tertiary</h3>
      <ul><li>Aesthetic focus</li><li>Shape refinement</li><li>Smile preview and planning</li></ul>
    </div>
  </div>
</div>
</div>

<!-- ── FOOTER ── -->
<footer class="site-footer">
  <div class="footer-inner">
    <div>
      <div class="footer-practice">
        <strong>SWR Dental — South West Rocks</strong>
        <a href="tel:0265666070">(02) 6566 6070</a> &nbsp;·&nbsp;
        <a href="https://swrdental.com.au" target="_blank">swrdental.com.au</a>
      </div>
      <div class="footer-practice" style="margin-top:8px;">
        <strong>Wauchope Dental — Wauchope</strong>
        <a href="tel:0265860007">(02) 6586 0007</a> &nbsp;·&nbsp;
        <a href="https://wauchopedental.net.au" target="_blank">wauchopedental.net.au</a>
      </div>
    </div>
    <div class="footer-badge">
      SmileRenew™ Internal Team Hub<br>
      For team use only
    </div>
  </div>
</footer>

<script>
  function showSection(name, btn) {
    document.querySelectorAll('.page-section').forEach(s => s.classList.remove('visible'));
    document.querySelectorAll('.nav-btn').forEach(b => b.classList.remove('active'));
    document.getElementById('sec-' + name).classList.add('visible');
    btn.classList.add('active');
    window.scrollTo({ top: 0, behavior: 'smooth' });
  }
  function showScript(name, btn) {
    document.querySelectorAll('.script-panel').forEach(s => s.classList.remove('visible'));
    document.querySelectorAll('.scen-btn').forEach(b => b.classList.remove('active'));
    document.getElementById('sp-' + name).classList.add('visible');
    btn.classList.add('active');
  }
</script>
</body>
</html>
