[index.html](https://github.com/user-attachments/files/27681032/index.html)
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>SmileRenew — Patient Call Guide | SWR Dental</title>
<link href="https://fonts.googleapis.com/css2?family=DM+Sans:ital,wght@0,300;0,400;0,500;0,600;1,400&family=DM+Serif+Display&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --teal: #0F6E56;
    --teal-mid: #1D9E75;
    --teal-light: #E1F5EE;
    --teal-dark: #085041;
    --teal-muted: #B2DADA;
    --text: #1A2E2E;
    --text-muted: #4a5e5e;
    --text-faint: #7a9090;
    --bg: #f7fafa;
    --surface: #ffffff;
    --surface-alt: #f0f7f5;
    --border: rgba(15,110,86,0.12);
    --border-strong: rgba(15,110,86,0.25);
    --radius: 10px;
    --radius-lg: 16px;
    --shadow: 0 1px 4px rgba(15,110,86,0.08), 0 4px 16px rgba(15,110,86,0.06);
  }

  body {
    font-family: 'DM Sans', sans-serif;
    background: var(--bg);
    color: var(--text);
    min-height: 100vh;
    line-height: 1.6;
  }

  /* ── HEADER ── */
  .site-header {
    background: var(--teal);
    padding: 2rem 1.5rem 1.75rem;
    text-align: center;
  }
  .site-header .practice { font-size: 12px; letter-spacing: .1em; text-transform: uppercase; color: var(--teal-muted); margin-bottom: 6px; font-weight: 500; }
  .site-header h1 { font-family: 'DM Serif Display', serif; font-size: clamp(28px, 5vw, 42px); color: #fff; font-weight: 400; line-height: 1.15; }
  .site-header h1 sup { font-family: 'DM Sans', sans-serif; font-size: 0.45em; vertical-align: super; }
  .site-header .tagline { color: var(--teal-muted); font-size: 15px; margin-top: 6px; font-style: italic; }
  .header-pill { display: inline-block; margin-top: 14px; background: rgba(255,255,255,0.12); border: 1px solid rgba(255,255,255,0.2); color: #fff; font-size: 12px; padding: 5px 14px; border-radius: 99px; }

  /* ── LAYOUT ── */
  .container { max-width: 820px; margin: 0 auto; padding: 2rem 1.25rem 4rem; }

  /* ── TABS ── */
  .tabs { display: flex; gap: 6px; flex-wrap: wrap; margin-bottom: 1.75rem; background: var(--surface); border-radius: var(--radius-lg); padding: 6px; border: 1px solid var(--border); }
  .tab { flex: 1; min-width: 120px; padding: 9px 16px; border-radius: var(--radius); border: none; background: transparent; font-family: 'DM Sans', sans-serif; font-size: 14px; font-weight: 400; color: var(--text-muted); cursor: pointer; transition: all .18s; text-align: center; }
  .tab:hover { background: var(--teal-light); color: var(--teal-dark); }
  .tab.active { background: var(--teal); color: #fff; font-weight: 500; }

  /* ── SECTIONS ── */
  .section { display: none; animation: fadeIn .2s ease; }
  .section.visible { display: block; }
  @keyframes fadeIn { from { opacity: 0; transform: translateY(4px); } to { opacity: 1; transform: translateY(0); } }

  /* ── CARDS ── */
  .card { background: var(--surface); border: 1px solid var(--border); border-radius: var(--radius-lg); padding: 1.25rem 1.5rem; margin-bottom: 1rem; box-shadow: var(--shadow); }
  .card-label { font-size: 11px; font-weight: 600; text-transform: uppercase; letter-spacing: .08em; color: var(--teal-mid); margin-bottom: 10px; }

  /* ── INTRO BANNER ── */
  .intro-banner { background: var(--teal-light); border: 1px solid var(--border-strong); border-radius: var(--radius-lg); padding: 1.25rem 1.5rem; margin-bottom: 1.25rem; }
  .intro-banner p { font-size: 15px; color: var(--text); line-height: 1.7; }
  .intro-banner strong { color: var(--teal); }

  /* ── STAGES ── */
  .stages { display: grid; grid-template-columns: repeat(5, 1fr); gap: 10px; margin-top: 14px; }
  @media (max-width: 580px) { .stages { grid-template-columns: 1fr 1fr; } }
  .stage { text-align: center; }
  .stage-num { width: 40px; height: 40px; border-radius: 50%; background: var(--teal); color: #fff; font-size: 18px; font-weight: 500; display: flex; align-items: center; justify-content: center; margin: 0 auto 8px; }
  .stage-name { font-size: 13px; font-weight: 600; color: var(--text); margin-bottom: 4px; }
  .stage-desc { font-size: 11px; color: var(--text-muted); line-height: 1.4; }

  /* ── OPTIONS ── */
  .options-row { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; margin-top: 12px; }
  @media (max-width: 520px) { .options-row { grid-template-columns: 1fr; } }
  .option-card { border: 1px solid var(--border); border-radius: var(--radius); padding: 14px; background: var(--surface-alt); }
  .option-card h4 { font-size: 13px; font-weight: 600; color: var(--teal-dark); margin-bottom: 6px; }
  .option-card p { font-size: 13px; color: var(--text-muted); line-height: 1.5; margin-bottom: 10px; }
  .tag { display: inline-block; font-size: 11px; padding: 3px 9px; border-radius: 99px; background: var(--teal-light); color: var(--teal-dark); font-weight: 500; margin: 2px 2px 0 0; border: 1px solid var(--border-strong); }

  /* ── SCENARIO GRID ── */
  .scenario-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(140px, 1fr)); gap: 8px; margin-bottom: 1.5rem; }
  .scenario-btn { background: var(--surface); border: 1px solid var(--border); border-radius: var(--radius); padding: 10px 14px; font-family: 'DM Sans', sans-serif; font-size: 13px; cursor: pointer; color: var(--text-muted); text-align: left; transition: all .15s; line-height: 1.4; }
  .scenario-btn:hover { border-color: var(--teal-mid); color: var(--teal-dark); background: var(--teal-light); }
  .scenario-btn.active { border-color: var(--teal); background: var(--teal); color: #fff; font-weight: 500; }

  /* ── SCRIPT BLOCKS ── */
  .script-block { display: none; animation: fadeIn .18s ease; }
  .script-block.visible { display: block; }

  .say { background: var(--teal-light); border-left: 3px solid var(--teal-mid); border-radius: 0 var(--radius) var(--radius) 0; padding: 14px 18px; margin: 10px 0; }
  .say-label { font-size: 10px; font-weight: 700; color: var(--teal); text-transform: uppercase; letter-spacing: .08em; margin-bottom: 6px; }
  .say p { margin: 0; color: var(--teal-dark); font-size: 14px; line-height: 1.7; font-style: italic; }

  .tip { background: #f7f7f5; border-left: 3px solid #d0d0cc; border-radius: 0 var(--radius) var(--radius) 0; padding: 12px 16px; margin: 10px 0; }
  .tip-label { font-size: 10px; font-weight: 700; color: var(--text-faint); text-transform: uppercase; letter-spacing: .08em; margin-bottom: 5px; }
  .tip p { margin: 0; color: var(--text-muted); font-size: 13px; line-height: 1.6; }

  /* ── Q&A ── */
  .qa-item { border-bottom: 1px solid var(--border); padding: 14px 0; }
  .qa-item:last-child { border-bottom: none; padding-bottom: 0; }
  .qa-q { font-size: 14px; font-weight: 600; color: var(--text); margin-bottom: 6px; }
  .qa-a { font-size: 14px; color: var(--text-muted); line-height: 1.65; }
  .qa-a strong { color: var(--text); font-weight: 600; }

  /* ── QUICK REF ── */
  .pill-row { display: flex; gap: 8px; flex-wrap: wrap; margin-top: 10px; }
  .pill { font-size: 12px; padding: 5px 12px; border-radius: 99px; background: var(--surface-alt); border: 1px solid var(--border); color: var(--text-muted); }

  .info-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; margin-top: 12px; }
  @media (max-width: 480px) { .info-grid { grid-template-columns: 1fr; } }
  .info-item { padding: 12px 14px; background: var(--surface-alt); border-radius: var(--radius); border: 1px solid var(--border); }
  .info-item .label { font-size: 10px; color: var(--text-faint); text-transform: uppercase; letter-spacing: .07em; font-weight: 600; margin-bottom: 4px; }
  .info-item .value { font-size: 14px; color: var(--text); font-weight: 500; }

  .dont-say { background: #fff8f7; border-left: 3px solid #e8a090; border-radius: 0 var(--radius) var(--radius) 0; padding: 10px 14px; margin: 8px 0; }
  .dont-say p { margin: 0; color: #7a3020; font-size: 13px; line-height: 1.5; }

  /* ── FOOTER ── */
  .site-footer { background: var(--teal); color: var(--teal-muted); text-align: center; padding: 1.5rem; font-size: 13px; margin-top: 2rem; }
  .site-footer a { color: #fff; text-decoration: none; }
  .site-footer strong { color: #fff; }
</style>
</head>
<body>

<header class="site-header">
  <div class="practice">South West Rocks Dental</div>
  <h1>SmileRenew<sup>™</sup></h1>
  <div class="tagline">Your Smile, Thoughtfully Restored</div>
  <div class="header-pill">Patient Call Guide — Internal Team Resource</div>
</header>

<div class="container">

  <div class="tabs">
    <button class="tab active" onclick="showTab('overview', this)">Overview</button>
    <button class="tab" onclick="showTab('scenarios', this)">Call scenarios</button>
    <button class="tab" onclick="showTab('questions', this)">Common questions</button>
    <button class="tab" onclick="showTab('quickref', this)">Quick reference</button>
  </div>

  <!-- ── OVERVIEW ── -->
  <div class="section visible" id="tab-overview">

    <div class="intro-banner">
      <p>For many people, dental care becomes a cycle of small fixes with no clear long-term plan. <strong>SmileRenew changes that.</strong> It's a clear, structured pathway — from patchwork dentistry to a confident, healthy, long-lasting result. The pace is always the patient's.</p>
    </div>

    <div class="card">
      <div class="card-label">The 5-stage pathway</div>
      <div class="stages">
        <div class="stage">
          <div class="stage-num">1</div>
          <div class="stage-name">Diagnose</div>
          <div class="stage-desc">Records, scans & photos — the full picture of bite, wear & needs</div>
        </div>
        <div class="stage">
          <div class="stage-num">2</div>
          <div class="stage-name">Blueprint</div>
          <div class="stage-desc">Co-design the plan — function, aesthetics & longevity</div>
        </div>
        <div class="stage">
          <div class="stage-num">3</div>
          <div class="stage-name">Try-in</div>
          <div class="stage-desc">See & feel the result before committing to anything</div>
        </div>
        <div class="stage">
          <div class="stage-num">4</div>
          <div class="stage-name">Prototype</div>
          <div class="stage-desc">Composite smile via injection moulding — live with it medium-term</div>
        </div>
        <div class="stage">
          <div class="stage-num">5</div>
          <div class="stage-name">Porcelain</div>
          <div class="stage-desc">Optional final step — handcrafted, long-lasting result</div>
        </div>
      </div>
    </div>

    <div class="card">
      <div class="card-label">Two treatment paths</div>
      <div class="options-row">
        <div class="option-card">
          <h4>Option A — Composite prototype</h4>
          <p>Custom composite smile via injection moulding. More accessible and less invasive. Many patients stay here long-term — it's clinically valid on its own.</p>
          <span class="tag">Accessible</span><span class="tag">Less invasive</span><span class="tag">Faster</span>
        </div>
        <div class="option-card">
          <h4>Option B — Porcelain (optional)</h4>
          <p>Handcrafted porcelain for longevity and a refined natural result. Taken at the patient's own pace — months or even years later if they choose.</p>
          <span class="tag">Long-lasting</span><span class="tag">Handcrafted</span><span class="tag">Refined</span>
        </div>
      </div>
    </div>

  </div>

  <!-- ── SCENARIOS ── -->
  <div class="section" id="tab-scenarios">

    <div class="scenario-grid">
      <button class="scenario-btn active" onclick="showScript('general', this)">General enquiry</button>
      <button class="scenario-btn" onclick="showScript('marketing', this)">Came from an ad</button>
      <button class="scenario-btn" onclick="showScript('cost', this)">Asking about cost</button>
      <button class="scenario-btn" onclick="showScript('nervous', this)">Nervous or hesitant</button>
      <button class="scenario-btn" onclick="showScript('existing', this)">Existing patient</button>
      <button class="scenario-btn" onclick="showScript('book', this)">Ready to book</button>
    </div>

    <div class="script-block visible" id="script-general">
      <div class="say">
        <div class="say-label">Open with</div>
        <p>"Thanks for calling about SmileRenew — great that you've reached out. SmileRenew is our signature process for adults who want to properly restore their smile, rather than just patch things up one tooth at a time. It's a clear, staged plan from start to finish. Can I ask — what's been going on with your teeth that prompted you to call today?"</p>
      </div>
      <div class="tip">
        <div class="tip-label">Why ask that?</div>
        <p>Getting them to describe their situation lets you listen and reflect their words back. You're not selling — you're understanding. Let them talk first.</p>
      </div>
      <div class="say">
        <div class="say-label">Then move toward booking</div>
        <p>"The best starting point is a private SmileRenew consultation — it's relaxed, one-to-one, and there's absolutely no treatment on the day. You'll get a full walkthrough of the process and your own personalised price guide. Would you like to get that booked in?"</p>
      </div>
    </div>

    <div class="script-block" id="script-marketing">
      <div class="say">
        <div class="say-label">Acknowledge where they came from</div>
        <p>"Wonderful — glad the ad caught your eye! SmileRenew is our signature smile restoration process. It's designed for people who are tired of one-off repairs and want a proper long-term plan for their teeth. What drew you to it — was it the process itself, or something specific about your own teeth?"</p>
      </div>
      <div class="tip">
        <div class="tip-label">Key point</div>
        <p>Marketing patients are often at the awareness stage — curious but not yet committed. Your job is to make the consultation feel easy and low-risk. Emphasise "no pressure, no treatment on day one."</p>
      </div>
      <div class="say">
        <div class="say-label">Close toward the consult</div>
        <p>"The consultation is really just a conversation — we take some records, walk you through the five stages, and give you a transparent price guide so you know exactly what's involved. A lot of people find it really clarifying. Would you like to come in and explore it?"</p>
      </div>
    </div>

    <div class="script-block" id="script-cost">
      <div class="say">
        <div class="say-label">Acknowledge honestly</div>
        <p>"That's a great question and completely understandable. We don't quote a price over the phone because every SmileRenew plan is individual — it depends on your teeth, your bite, and what you're looking to achieve. What we do is give you a full itemised price guide at your consultation, so you see every single cost laid out before committing to anything."</p>
      </div>
      <div class="tip">
        <div class="tip-label">If they push for a ballpark</div>
        <p>Acknowledge warmly without giving a number: "I completely understand wanting a rough idea. What I can say is there are two stages — a more accessible composite option and an optional porcelain step — and the consultation will give you the full picture for your specific situation."</p>
      </div>
      <div class="say">
        <div class="say-label">Mention payment options</div>
        <p>"We also have staged payment and finance options available, so many patients don't pay for everything upfront. The consultation is really the right place to talk through all of that — would that work for you?"</p>
      </div>
    </div>

    <div class="script-block" id="script-nervous">
      <div class="say">
        <div class="say-label">Validate first</div>
        <p>"That makes complete sense — a lot of the people who come to us have put this off for years, and often it's because previous dental experiences have felt rushed or overwhelming. SmileRenew is actually designed around the opposite of that."</p>
      </div>
      <div class="say">
        <div class="say-label">Reassure about the consult</div>
        <p>"The consultation is just a conversation — no treatment happens on that day at all. It's one-to-one with the dentist, completely unhurried, and there's zero obligation to proceed. Some people come in, understand their options, and decide they want to take care of some general dentistry first — that's completely fine too. It's really just about getting clarity."</p>
      </div>
      <div class="tip">
        <div class="tip-label">Tone note</div>
        <p>Slow down your own pace. A calm, warm voice does more here than any script. Let there be pauses. Don't rush to fill silence.</p>
      </div>
    </div>

    <div class="script-block" id="script-existing">
      <div class="say">
        <div class="say-label">Acknowledge the relationship</div>
        <p>"Wonderful — so glad you're thinking about this. SmileRenew is something we've developed as a way to give existing patients a proper long-term plan, rather than continuing to treat things one at a time. Your dentist will already have some context on your history which makes the consultation even more productive."</p>
      </div>
      <div class="tip">
        <div class="tip-label">Key difference for existing patients</div>
        <p>They may already have records on file. Let them know the consultation builds on what we already know — it's not starting from scratch. This is a comfort and a genuine benefit.</p>
      </div>
      <div class="say">
        <div class="say-label">Invite them in</div>
        <p>"The SmileRenew consultation is a dedicated appointment — separate from a regular check-up — where we look at the full picture and map out a plan together. Would you like me to get that scheduled for you?"</p>
      </div>
    </div>

    <div class="script-block" id="script-book">
      <div class="say">
        <div class="say-label">Make it easy</div>
        <p>"Perfect — let's get that locked in for you. The SmileRenew consultation is a private, one-to-one appointment with the dentist. I just need a few details and we'll find a time that suits. What days generally work best for you?"</p>
      </div>
      <div class="tip">
        <div class="tip-label">Before you hang up</div>
        <p>Confirm their name and contact number, the date and time, and let them know what to expect — "you don't need to bring anything, just come as you are." A brief confirmation text or email after the call is a great touch.</p>
      </div>
    </div>

  </div>

  <!-- ── COMMON QUESTIONS ── -->
  <div class="section" id="tab-questions">
    <div class="card">

      <div class="qa-item">
        <div class="qa-q">How long does the whole process take?</div>
        <div class="qa-a">From consultation to composite prototype is typically <strong>4–8 weeks</strong> over a few short visits. The porcelain step — if they choose it — is entirely on their own timeline. Could be months later, could be years. No pressure either way.</div>
      </div>

      <div class="qa-item">
        <div class="qa-q">Do I have to do the porcelain step?</div>
        <div class="qa-a">No — and this is important to convey clearly. <strong>The composite prototype is a clinically valid long-term solution on its own.</strong> Many patients stay at that stage. Whether to go to porcelain is a decision made together with the dentist, based on how things are going.</div>
      </div>

      <div class="qa-item">
        <div class="qa-q">Is it suitable if I have missing teeth?</div>
        <div class="qa-a">Yes. Missing teeth are common and often part of the plan. <strong>Implants or bridges may be needed</strong> to replace back teeth before restoring the front — the consultation will map all of that out for the individual patient.</div>
      </div>

      <div class="qa-item">
        <div class="qa-q">What actually happens at the consultation?</div>
        <div class="qa-a">It's a relaxed one-to-one session. The dentist takes records, photos and digital scans (when comfortable), walks through all five stages, and hands them a <strong>personalised itemised price guide</strong>. No treatment starts — it's purely a planning appointment.</div>
      </div>

      <div class="qa-item">
        <div class="qa-q">Is there any pressure to proceed?</div>
        <div class="qa-a"><strong>None at all.</strong> The consultation is completely without obligation. Some patients take the information away, think about it, and come back. Some address general dental health first. The pace is entirely theirs.</div>
      </div>

      <div class="qa-item">
        <div class="qa-q">What are the risks?</div>
        <div class="qa-a">Like all dental treatment, there are clinical risks — including tooth sensitivity, possible root canal on some teeth, gum irritation, and potential need for future adjustments. <strong>The dentist will discuss the specific risks at the consultation.</strong> All clinicians are AHPRA-registered.</div>
      </div>

      <div class="qa-item">
        <div class="qa-q">Can I pay in instalments?</div>
        <div class="qa-a">Yes. <strong>Finance and staged payment options are available.</strong> The consultation includes the full price guide and a conversation about what payment approach works for them.</div>
      </div>

    </div>
  </div>

  <!-- ── QUICK REFERENCE ── -->
  <div class="section" id="tab-quickref">

    <div class="card">
      <div class="card-label">Always say these things</div>
      <div class="say" style="margin-bottom: 8px;"><p>"No treatment on day one — the consultation is just a conversation."</p></div>
      <div class="say" style="margin-bottom: 8px;"><p>"You'll receive a full itemised price guide before committing to anything."</p></div>
      <div class="say" style="margin-bottom: 8px;"><p>"The pace is entirely yours — porcelain is optional, not required."</p></div>
      <div class="say"><p>"We have payment plans and finance options available."</p></div>
    </div>

    <div class="card">
      <div class="card-label">Never say these things</div>
      <div class="dont-say"><p>"It'll cost around $X..." — never quote a price over the phone. Always direct to the consultation.</p></div>
      <div class="dont-say"><p>"It fixes everything" — outcomes are individual. Keep it honest and specific.</p></div>
      <div class="dont-say"><p>"You have to do the porcelain step" — porcelain is always optional.</p></div>
      <div class="dont-say"><p>Rushing the patient — calm and patience are part of what SmileRenew stands for.</p></div>
    </div>

    <div class="card">
      <div class="card-label">Who is a good fit?</div>
      <div class="pill-row">
        <span class="pill">Tired of repeated repairs</span>
        <span class="pill">Worn or broken teeth</span>
        <span class="pill">Avoiding photos</span>
        <span class="pill">Struggling to eat comfortably</span>
        <span class="pill">Wants a long-term plan</span>
        <span class="pill">Wants clarity on cost upfront</span>
        <span class="pill">Has been putting it off for years</span>
      </div>
    </div>

    <div class="card">
      <div class="card-label">Practice details</div>
      <div class="info-grid">
        <div class="info-item">
          <div class="label">Phone</div>
          <div class="value">(02) 6566 6070</div>
        </div>
        <div class="info-item">
          <div class="label">Hours</div>
          <div class="value">Mon–Fri, 8am–6pm</div>
        </div>
        <div class="info-item">
          <div class="label">Website</div>
          <div class="value">swrdental.com.au</div>
        </div>
        <div class="info-item">
          <div class="label">Response time</div>
          <div class="value">Within 1 business day</div>
        </div>
      </div>
    </div>

  </div>

</div>

<footer class="site-footer">
  <strong>South West Rocks Dental</strong> &nbsp;·&nbsp; <a href="tel:0265666070">(02) 6566 6070</a> &nbsp;·&nbsp; <a href="https://swrdental.com.au/services/smile-renew/" target="_blank">swrdental.com.au</a>
  <br><span style="font-size: 11px; margin-top: 6px; display: block;">Internal resource — for team use only</span>
</footer>

<script>
  function showTab(name, btn) {
    document.querySelectorAll('.section').forEach(s => s.classList.remove('visible'));
    document.querySelectorAll('.tab').forEach(t => t.classList.remove('active'));
    document.getElementById('tab-' + name).classList.add('visible');
    btn.classList.add('active');
  }
  function showScript(name, btn) {
    document.querySelectorAll('.script-block').forEach(s => s.classList.remove('visible'));
    document.querySelectorAll('.scenario-btn').forEach(b => b.classList.remove('active'));
    document.getElementById('script-' + name).classList.add('visible');
    btn.classList.add('active');
  }
</script>

</body>
</html>
