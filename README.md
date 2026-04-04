<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8"/>
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>AI Prompt Pack</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Nunito:wght@400;600;700;800;900&display=swap');
    *{box-sizing:border-box;margin:0;padding:0;}
    body{font-family:'Nunito',sans-serif;background:#fafafa;color:#2d2d2d;padding-bottom:80px;}

    /* HERO */
    .hero{background:linear-gradient(135deg,#7c3aed 0%,#ec4899 45%,#f59e0b 100%);padding:56px 40px 64px;text-align:center;border-radius:0 0 44px 44px;position:relative;overflow:hidden;}
    .hero::before{content:'';position:absolute;width:320px;height:320px;background:rgba(255,255,255,.07);border-radius:50%;top:-100px;right:-60px;}
    .hero::after{content:'';position:absolute;width:200px;height:200px;background:rgba(255,255,255,.05);border-radius:50%;bottom:-50px;left:20px;}
    .hero-badge{display:inline-block;background:rgba(255,255,255,.22);color:#fff;font-size:11px;font-weight:800;letter-spacing:2.5px;text-transform:uppercase;padding:7px 20px;border-radius:20px;margin-bottom:16px;}
    .hero h1{font-size:54px;font-weight:900;color:#fff;line-height:1.05;margin-bottom:12px;}
    .hero h1 span{display:block;font-size:20px;font-weight:700;opacity:.9;margin-top:10px;}
    .hero p{font-size:15px;font-weight:600;color:rgba(255,255,255,.93);max-width:600px;margin:14px auto 22px;line-height:1.7;}
    .hero-stats{display:flex;justify-content:center;gap:14px;flex-wrap:wrap;margin-bottom:10px;}
    .hero-stat{background:rgba(255,255,255,.18);color:#fff;font-size:13px;font-weight:800;padding:8px 20px;border-radius:20px;}
    .hero-rule{display:inline-block;background:rgba(255,255,255,.25);border:2px solid rgba(255,255,255,.4);color:#fff;font-size:13px;font-weight:800;padding:9px 26px;border-radius:20px;margin-top:10px;}

    /* LAYOUT */
    .content{max-width:860px;margin:0 auto;padding:0 24px;}

    /* HOW TO USE */
    .how-block{background:#fff;border-radius:20px;padding:28px 30px;margin:36px 0 30px;box-shadow:0 3px 18px rgba(0,0,0,.07);}
    .how-block h2{font-size:20px;font-weight:900;color:#1e1e2e;margin-bottom:18px;}
    .steps-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:14px;}
    .step{border-radius:14px;padding:16px 14px;text-align:center;}
    .step-num{font-size:10px;font-weight:800;letter-spacing:1px;padding:4px 12px;border-radius:20px;display:inline-block;margin-bottom:8px;}
    .step h4{font-size:14px;font-weight:900;margin-bottom:6px;}
    .step p{font-size:12.5px;color:#666;line-height:1.55;}

    /* GOLDEN RULE */
    .golden{background:#fffbeb;border:2px solid #fde68a;border-radius:14px;padding:16px 22px;text-align:center;font-size:14px;font-weight:700;color:#92400e;margin-bottom:32px;}

    /* QUICK NAV */
    .quick-nav{background:#fff;border-radius:18px;padding:22px 24px;margin-bottom:30px;box-shadow:0 2px 14px rgba(0,0,0,.06);}
    .quick-nav h3{font-size:14px;font-weight:900;color:#1e1e2e;margin-bottom:14px;}
    .nav-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:8px;}
    .nav-item{display:flex;align-items:center;gap:8px;padding:9px 12px;border-radius:10px;font-size:12px;font-weight:700;color:#555;background:#fafafa;text-decoration:none;}
    .nav-item:hover{background:#f0f0f0;}
    .nav-dot{width:10px;height:10px;border-radius:50%;flex-shrink:0;}

    /* SECTION HEADER */
    .section-hdr{border-radius:18px;padding:24px 28px 20px;margin:44px 0 6px;}
    .section-hdr .sh-top{display:flex;align-items:center;gap:14px;margin-bottom:8px;}
    .sh-badge{font-size:10px;font-weight:800;letter-spacing:1.5px;padding:5px 14px;border-radius:20px;}
    .section-hdr h2{font-size:22px;font-weight:900;}
    .section-hdr .sh-sub{font-size:13.5px;font-weight:600;opacity:.8;margin-top:4px;}
    .section-hdr .sh-desc{font-size:13.5px;line-height:1.65;margin-top:10px;opacity:.85;}
    .section-count{font-size:11px;font-weight:800;opacity:.7;margin-top:8px;}

    /* PROMPT CARD */
    .prompt-card{background:#fff;border-radius:20px;margin-bottom:20px;overflow:hidden;box-shadow:0 3px 16px rgba(0,0,0,.07);border:1.5px solid #f0f0f0;}
    .pc-header{display:flex;align-items:flex-start;justify-content:space-between;padding:18px 22px 14px;}
    .pc-left{flex:1;}
    .pc-num{font-size:10px;font-weight:800;letter-spacing:1.5px;padding:4px 12px;border-radius:20px;display:inline-block;margin-bottom:8px;}
    .pc-title{font-size:17px;font-weight:900;color:#1e1e2e;margin-bottom:3px;}
    .pc-use{font-size:12px;font-weight:700;color:#888;}
    .copy-btn{flex-shrink:0;padding:8px 16px;border-radius:20px;font-size:12px;font-weight:800;cursor:pointer;border:none;color:#fff;transition:opacity .2s;white-space:nowrap;margin-left:12px;}
    .copy-btn:hover{opacity:.85;}

    /* PROMPT TEXT BOX */
    .prompt-box{margin:0 22px 16px;border-radius:12px;padding:16px 18px;font-size:13px;line-height:1.75;color:#2d2d2d;font-family:'Nunito',sans-serif;white-space:pre-wrap;border-left:4px solid;}

    /* META ROW */
    .pc-meta{display:flex;flex-wrap:wrap;gap:8px;padding:0 22px 16px;}
    .pc-tag{font-size:11px;font-weight:700;padding:5px 12px;border-radius:20px;}
    .pro-tip{width:100%;margin-top:4px;font-size:12.5px;font-weight:600;color:#666;padding:10px 14px;border-radius:10px;background:#fafafa;line-height:1.55;}
    .pro-tip strong{font-weight:800;}

    /* COLOR THEMES */
    /* PURPLE */
    .t-purple .section-hdr{background:#f5f3ff;}
    .t-purple .sh-badge{background:#ede9fe;color:#5b21b6;}
    .t-purple .section-hdr h2{color:#5b21b6;}
    .t-purple .pc-num{background:#ede9fe;color:#5b21b6;}
    .t-purple .copy-btn{background:#7c3aed;}
    .t-purple .prompt-box{background:#f5f3ff;border-left-color:#a855f7;}
    .t-purple .pc-tag{background:#ede9fe;color:#5b21b6;}
    .t-purple .prompt-card{border-top:3px solid #a855f7;}

    /* PINK */
    .t-pink .section-hdr{background:#fdf2f8;}
    .t-pink .sh-badge{background:#fce7f3;color:#9d174d;}
    .t-pink .section-hdr h2{color:#db2777;}
    .t-pink .pc-num{background:#fce7f3;color:#9d174d;}
    .t-pink .copy-btn{background:#ec4899;}
    .t-pink .prompt-box{background:#fdf2f8;border-left-color:#ec4899;}
    .t-pink .pc-tag{background:#fce7f3;color:#9d174d;}
    .t-pink .prompt-card{border-top:3px solid #ec4899;}

    /* AMBER */
    .t-amber .section-hdr{background:#fffbeb;}
    .t-amber .sh-badge{background:#fef3c7;color:#92400e;}
    .t-amber .section-hdr h2{color:#d97706;}
    .t-amber .pc-num{background:#fef3c7;color:#92400e;}
    .t-amber .copy-btn{background:#f59e0b;}
    .t-amber .prompt-box{background:#fffbeb;border-left-color:#f59e0b;}
    .t-amber .pc-tag{background:#fef3c7;color:#92400e;}
    .t-amber .prompt-card{border-top:3px solid #f59e0b;}

    /* GREEN */
    .t-green .section-hdr{background:#f0fdf4;}
    .t-green .sh-badge{background:#dcfce7;color:#15803d;}
    .t-green .section-hdr h2{color:#16a34a;}
    .t-green .pc-num{background:#dcfce7;color:#15803d;}
    .t-green .copy-btn{background:#10b981;}
    .t-green .prompt-box{background:#f0fdf4;border-left-color:#10b981;}
    .t-green .pc-tag{background:#dcfce7;color:#15803d;}
    .t-green .prompt-card{border-top:3px solid #10b981;}

    /* SKY */
    .t-sky .section-hdr{background:#f0f9ff;}
    .t-sky .sh-badge{background:#e0f2fe;color:#0369a1;}
    .t-sky .section-hdr h2{color:#0284c7;}
    .t-sky .pc-num{background:#e0f2fe;color:#0369a1;}
    .t-sky .copy-btn{background:#0ea5e9;}
    .t-sky .prompt-box{background:#f0f9ff;border-left-color:#0ea5e9;}
    .t-sky .pc-tag{background:#e0f2fe;color:#0369a1;}
    .t-sky .prompt-card{border-top:3px solid #0ea5e9;}

    /* ROSE */
    .t-rose .section-hdr{background:#fff1f2;}
    .t-rose .sh-badge{background:#ffe4e6;color:#be123c;}
    .t-rose .section-hdr h2{color:#e11d48;}
    .t-rose .pc-num{background:#ffe4e6;color:#be123c;}
    .t-rose .copy-btn{background:#f43f5e;}
    .t-rose .prompt-box{background:#fff1f2;border-left-color:#f43f5e;}
    .t-rose .pc-tag{background:#ffe4e6;color:#be123c;}
    .t-rose .prompt-card{border-top:3px solid #f43f5e;}

    /* TEAL */
    .t-teal .section-hdr{background:#f0fdfa;}
    .t-teal .sh-badge{background:#ccfbf1;color:#0f766e;}
    .t-teal .section-hdr h2{color:#0f766e;}
    .t-teal .pc-num{background:#ccfbf1;color:#0f766e;}
    .t-teal .copy-btn{background:#14b8a6;}
    .t-teal .prompt-box{background:#f0fdfa;border-left-color:#14b8a6;}
    .t-teal .pc-tag{background:#ccfbf1;color:#0f766e;}
    .t-teal .prompt-card{border-top:3px solid #14b8a6;}

    /* ORANGE */
    .t-orange .section-hdr{background:#fff7ed;}
    .t-orange .sh-badge{background:#ffedd5;color:#c2410c;}
    .t-orange .section-hdr h2{color:#ea580c;}
    .t-orange .pc-num{background:#ffedd5;color:#c2410c;}
    .t-orange .copy-btn{background:#f97316;}
    .t-orange .prompt-box{background:#fff7ed;border-left-color:#f97316;}
    .t-orange .pc-tag{background:#ffedd5;color:#c2410c;}
    .t-orange .prompt-card{border-top:3px solid #f97316;}

    /* INDIGO */
    .t-indigo .section-hdr{background:#eef2ff;}
    .t-indigo .sh-badge{background:#e0e7ff;color:#3730a3;}
    .t-indigo .section-hdr h2{color:#4338ca;}
    .t-indigo .pc-num{background:#e0e7ff;color:#3730a3;}
    .t-indigo .copy-btn{background:#6366f1;}
    .t-indigo .prompt-box{background:#eef2ff;border-left-color:#6366f1;}
    .t-indigo .pc-tag{background:#e0e7ff;color:#3730a3;}
    .t-indigo .prompt-card{border-top:3px solid #6366f1;}

    .copied-msg{display:none;font-size:11px;font-weight:700;color:#10b981;margin-left:8px;}

    /* DIVIDER */
    .sec-divider{height:1px;background:linear-gradient(90deg,transparent,#e5e7eb,transparent);margin:8px 0 0;}

    /* FINAL */
    .final-block{background:linear-gradient(135deg,#f5f3ff,#fdf2f8,#fffbeb);border-radius:22px;padding:38px;margin-top:50px;text-align:center;}
    .final-block .fe{font-size:44px;display:block;margin-bottom:14px;}
    .final-block p{font-size:18px;font-weight:800;color:#5b21b6;line-height:1.6;}
    .final-block .fsub{font-size:13px;font-weight:600;color:#888;margin-top:10px;}

    @media(max-width:640px){
      .steps-grid,.nav-grid{grid-template-columns:1fr 1fr;}
      .hero h1{font-size:34px;}
      .nav-grid{grid-template-columns:1fr 1fr;}
    }
  
    /* Section header alternative layout (sections 9-11) */
    .section-header{border-radius:18px;padding:24px 28px 20px;margin:44px 0 6px;display:flex;align-items:center;gap:18px;}
    .section-header .sh-icon{font-size:2.4rem;flex-shrink:0;}
    .section-header .sh-label{font-size:10px;font-weight:800;letter-spacing:1.5px;opacity:.7;text-transform:uppercase;margin-bottom:4px;}
    .section-header .sh-title{font-size:22px;font-weight:900;line-height:1.2;}
    .section-header .sh-sub{font-size:13.5px;font-weight:600;opacity:.8;margin-top:4px;}
    .t-indigo.section-header{background:#eef2ff;}
    .t-indigo.section-header .sh-title{color:#3730a3;}
    .t-rose.section-header{background:#fff1f2;}
    .t-rose.section-header .sh-title{color:#e11d48;}
    .t-teal.section-header{background:#f0fdfa;}
    .t-teal.section-header .sh-title{color:#0f766e;}
</style>
</head>
<body>

<div class="hero">
  <div class="hero-badge">✨ RESOURCE 07 — AI PROMPT PACK ✨</div>
  <h1>🤖 AI Prompt Pack
    <span>Get 10x More Out of Every AI Tool You Use</span>
  </h1>
  <p>AI tools are only as powerful as the prompts you give them. A vague prompt gets a generic response. A specific, well-structured prompt gets content you can actually use — on the first try, every time. This pack is your done-for-you shortcut to great AI output across every creator use case.</p>
  <div class="hero-stats">
    <span class="hero-stat">🤖 100+ Ready-to-Use Prompts</span>
    <span class="hero-stat">📂 8 Creator Categories</span>
    <span class="hero-stat">📋 Copy &amp; Paste Instantly</span>
    <span class="hero-stat">⚡ Works with ChatGPT, Claude &amp; Gemini</span>
  </div>
  <div class="hero-rule">💜 Fill in the [brackets] · Add your voice · Never post raw AI output</div>
</div>

<div class="content">

<!-- HOW TO USE -->
<div class="how-block">
  <h2>How to Use This Prompt Pack 💡</h2>
  <div class="steps-grid">
    <div class="step" style="background:#f5f3ff;">
      <div class="step-num" style="background:#ede9fe;color:#5b21b6;">STEP 01</div>
      <h4 style="color:#5b21b6;">📋 Copy the Prompt</h4>
      <p>Click the copy button on any prompt. The full text copies to your clipboard instantly — ready to paste.</p>
    </div>
    <div class="step" style="background:#fdf2f8;">
      <div class="step-num" style="background:#fce7f3;color:#9d174d;">STEP 02</div>
      <h4 style="color:#db2777;">✏️ Fill the Brackets</h4>
      <p>Replace every [BRACKETED PLACEHOLDER] with your specific niche, topic, audience, or details. The more specific, the better.</p>
    </div>
    <div class="step" style="background:#fffbeb;">
      <div class="step-num" style="background:#fef3c7;color:#92400e;">STEP 03</div>
      <h4 style="color:#d97706;">🚀 Paste &amp; Run</h4>
      <p>Paste into ChatGPT, Claude, Gemini, or Perplexity. Hit enter. You'll get usable output in seconds.</p>
    </div>
    <div class="step" style="background:#f0fdf4;">
      <div class="step-num" style="background:#dcfce7;color:#15803d;">STEP 04</div>
      <h4 style="color:#16a34a;">🎯 Review &amp; Pick</h4>
      <p>Read the output. Pick the strongest 60–80% of it. Highlight the lines that sound most like you.</p>
    </div>
    <div class="step" style="background:#f0f9ff;">
      <div class="step-num" style="background:#e0f2fe;color:#0369a1;">STEP 05</div>
      <h4 style="color:#0284c7;">🎙️ Add Your Voice</h4>
      <p>Edit the output to sound like YOU. Add a personal story, your own opinion, or a real example. This step is non-negotiable.</p>
    </div>
    <div class="step" style="background:#fff1f2;">
      <div class="step-num" style="background:#ffe4e6;color:#be123c;">STEP 06</div>
      <h4 style="color:#e11d48;">🚫 Never Post Raw</h4>
      <p>Raw AI output is flat and obvious. Your personality is the product. Always personalize before you post.</p>
    </div>
  </div>
</div>

<div class="golden">✨ <strong>Golden Rule:</strong> A prompt you use imperfectly today is worth 1,000x more than a perfect one you never try. Start messy. Refine as you go. ✨</div>

<!-- QUICK NAV -->
<div class="quick-nav">
  <h3>🗺️ Jump to a Category</h3>
  <div class="nav-grid">
    <a class="nav-item" href="#content-ideas"><span class="nav-dot" style="background:#f59e0b;"></span>Content Ideas</a>
    <a class="nav-item" href="#hooks"><span class="nav-dot" style="background:#ec4899;"></span>Hook Writing</a>
    <a class="nav-item" href="#captions"><span class="nav-dot" style="background:#7c3aed;"></span>Captions</a>
    <a class="nav-item" href="#scripts"><span class="nav-dot" style="background:#10b981;"></span>Video Scripts</a>
    <a class="nav-item" href="#visuals"><span class="nav-dot" style="background:#0ea5e9;"></span>Visual Creation</a>
    <a class="nav-item" href="#research"><span class="nav-dot" style="background:#f43f5e;"></span>Research</a>
    <a class="nav-item" href="#offers"><span class="nav-dot" style="background:#14b8a6;"></span>Offer Creation</a>
    <a class="nav-item" href="#email"><span class="nav-dot" style="background:#f97316;"></span>Email Writing</a>
  </div>
</div>

<!-- ═══════════════════════════════════════ -->
<!-- SECTION 1: CONTENT IDEAS -->
<!-- ═══════════════════════════════════════ -->
<div class="t-amber" id="content-ideas">
  <div class="section-hdr">
    <div class="sh-top">
      <span class="sh-badge">CATEGORY 01</span>
    </div>
    <h2>💡 Content Idea Prompts</h2>
    <div class="sh-sub">Generate 30+ ideas for your niche in under 60 seconds</div>
    <div class="sh-desc">Use these when your content calendar is empty, you're creatively blocked, or you need a fresh batch of ideas fast. The more specific your niche and audience description, the better the output.</div>
    <div class="section-count">📦 12 Prompts in this category</div>
  </div>
  <div class="sec-divider"></div>

  <div class="prompt-card t-amber">
    <div class="pc-header">
      <div class="pc-left">
        <div class="pc-num">PROMPT 01</div>
        <div class="pc-title">The 30-Idea Brain Dump</div>
        <div class="pc-use">✅ Best for: Filling your entire content calendar in one session</div>
      </div>
      <button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button>
    </div>
    <div class="prompt-box">Give me 30 unique content ideas for a [YOUR NICHE] creator on [PLATFORM — TikTok / Instagram / YouTube]. My target audience is [DESCRIBE YOUR AUDIENCE IN DETAIL — e.g., "beginner online entrepreneurs aged 22–38 who want to make their first $1,000 online but feel overwhelmed by where to start"]. 

Mix the ideas across these 5 content types:
1. Educational how-tos and tutorials
2. Personal story or opinion content
3. Trending format content
4. Product or tool reviews
5. Myth-busting or controversial takes

For each idea, give me:
— The video title or hook line
— The core message in one sentence
— The content type it falls under
— A suggested CTA

Format as a numbered list. Prioritize ideas that are specific, not generic. Avoid surface-level topics that every creator in this space already covers.</div>
    <div class="pc-meta">
      <span class="pc-tag">📅 Content Planning</span>
      <span class="pc-tag">🧠 Batch Creation</span>
      <div class="pro-tip"><strong>💡 Pro tip:</strong> Run this every Sunday to fill the next 2 weeks. The more detail you give about your audience, the more targeted the ideas.</div>
    </div>
  </div>

  <div class="prompt-card t-amber">
    <div class="pc-header">
      <div class="pc-left">
        <div class="pc-num">PROMPT 02</div>
        <div class="pc-title">Pain Point Content Mining</div>
        <div class="pc-use">✅ Best for: Creating content that makes your audience feel deeply understood</div>
      </div>
      <button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button>
    </div>
    <div class="prompt-box">My audience is [DESCRIBE YOUR AUDIENCE]. They are trying to achieve [THEIR GOAL] but are struggling with [THEIR MAIN OBSTACLE].

List the 20 biggest frustrations, fears, mistakes, and unspoken questions this audience has about [YOUR NICHE TOPIC]. Be specific and use the exact language they would use — not polished marketing language, but the real words they type into Google at 11pm.

For each pain point, give me:
— The pain point written in their voice
— One content idea that directly addresses it
— The best hook for that content idea
— Whether it's better as a short-form video, carousel, or long-form content

Prioritize the pain points that feel the most urgent, embarrassing, or expensive to ignore.</div>
    <div class="pc-meta">
      <span class="pc-tag">🎯 Audience Research</span>
      <span class="pc-tag">💬 Voice of Customer</span>
      <div class="pro-tip"><strong>💡 Pro tip:</strong> Pain-point content gets the highest save rates because it makes people feel understood. Use the exact phrases from this output in your hooks and captions.</div>
    </div>
  </div>

  <div class="prompt-card t-amber">
    <div class="pc-header">
      <div class="pc-left">
        <div class="pc-num">PROMPT 03</div>
        <div class="pc-title">Competitor Gap Finder</div>
        <div class="pc-use">✅ Best for: Finding untapped angles in a crowded niche</div>
      </div>
      <button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button>
    </div>
    <div class="prompt-box">The top creators in my niche — [LIST 2–3 CREATOR TYPES OR TOPICS THEY COVER, e.g., "people posting about TikTok Shop, UGC content, and making money online"] — are consistently covering [COMMON TOPICS THEY POST ABOUT].

Identify:
1. What topics, angles, and conversations are they NOT covering that my audience still desperately needs?
2. Where does the mainstream content in this niche feel repetitive, shallow, or formulaic?
3. What would a contrarian, surprising, or counter-narrative take look like in this space?
4. What audience segments within [NICHE] are being underserved by current content?

Give me 15 content ideas that fill these gaps. For each, explain WHY this angle is differentiated and what unique perspective I could bring to it. These should be ideas that would make someone think "finally, someone is talking about this."</div>
    <div class="pc-meta">
      <span class="pc-tag">🔍 Differentiation</span>
      <span class="pc-tag">📈 Growth Strategy</span>
      <div class="pro-tip"><strong>💡 Pro tip:</strong> Spend 20 minutes manually watching the top 10 videos in your niche before running this prompt. Real observation plus AI analysis = powerful gaps.</div>
    </div>
  </div>

  <div class="prompt-card t-amber">
    <div class="pc-header">
      <div class="pc-left">
        <div class="pc-num">PROMPT 04</div>
        <div class="pc-title">The Authority Series Builder</div>
        <div class="pc-use">✅ Best for: Building a content series that positions you as the go-to expert</div>
      </div>
      <button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button>
    </div>
    <div class="prompt-box">I want to create a 10-part content series that establishes me as a go-to authority on [YOUR NICHE TOPIC] for [TARGET AUDIENCE].

Design the full series for me:
— Series name and overarching theme
— Part 1 through Part 10: title, core teaching point, hook, and CTA for each
— The logical progression: how does each part build on the previous one?
— What is the transformation someone experiences after watching all 10?
— What is the "cliffhanger" at the end of each video that makes them want the next one?
— How should I tease this series before posting Part 1?

Make the series feel like a free mini-course. Each individual video should deliver standalone value AND make someone want to binge the rest.</div>
    <div class="pc-meta">
      <span class="pc-tag">🏆 Authority Building</span>
      <span class="pc-tag">🔁 Binge-Worthy</span>
      <div class="pro-tip"><strong>💡 Pro tip:</strong> Series content drives follows because viewers need to come back for the next installment. Announce the series upfront so people know to follow.</div>
    </div>
  </div>

  <div class="prompt-card t-amber">
    <div class="pc-header">
      <div class="pc-left">
        <div class="pc-num">PROMPT 05</div>
        <div class="pc-title">Story-to-Content Converter</div>
        <div class="pc-use">✅ Best for: Turning your real experiences into compelling content</div>
      </div>
      <button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button>
    </div>
    <div class="prompt-box">Here is something that happened to me related to my niche: [DESCRIBE YOUR PERSONAL EXPERIENCE OR STORY IN 3–5 SENTENCES. Include what happened, what you felt, and what the outcome was.]

Turn this story into 8 different content ideas across multiple formats:

1. A 60-second transformation video (hook + before + turning point + after + CTA)
2. A personal essay caption for Instagram (long-form, emotional, relatable)
3. A "lesson I learned" educational video using my story as the frame
4. A controversy or hot take inspired by what I experienced
5. A "what I wish I knew" video for beginners
6. A relatable "POV" or trending format that captures the emotion
7. A carousel breaking down the 5 lessons from this experience
8. A live stream topic using this story as the opening hook

For each, give me the hook, the format, and the platform it works best on.</div>
    <div class="pc-meta">
      <span class="pc-tag">📖 Storytelling</span>
      <span class="pc-tag">🎭 Personal Brand</span>
      <div class="pro-tip"><strong>💡 Pro tip:</strong> One real story can generate 2–3 weeks of content. Never let a meaningful experience go uncaptured.</div>
    </div>
  </div>

  <div class="prompt-card t-amber">
    <div class="pc-header">
      <div class="pc-left">
        <div class="pc-num">PROMPT 06</div>
        <div class="pc-title">Comment Mining for Content</div>
        <div class="pc-use">✅ Best for: Creating content your audience has literally asked for</div>
      </div>
      <button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button>
    </div>
    <div class="prompt-box">Here are comments, questions, and DMs I've received from my audience recently:

[PASTE 10–15 COMMENTS, DMs, OR QUESTIONS YOUR AUDIENCE HAS ASKED YOU]

Analyze these and tell me:
1. What are the 5 most common underlying questions or frustrations hiding in these messages?
2. What content gaps do these reveal — things my audience needs that I haven't covered yet?
3. Rank the top 10 content ideas I should create based on this audience feedback, from most urgent to least.
4. For each idea, write the hook and suggest the best format (video, carousel, live, etc.)
5. Are there any phrases or words my audience used repeatedly that I should mirror in my own content language?

Use THEIR words, not polished marketing language.</div>
    <div class="pc-meta">
      <span class="pc-tag">💬 Community</span>
      <span class="pc-tag">🎯 Audience-Led</span>
      <div class="pro-tip"><strong>💡 Pro tip:</strong> Check your comments and DMs before planning your weekly content. Your audience is telling you what to make — you just have to listen.</div>
    </div>
  </div>

  <div class="prompt-card t-amber">
    <div class="pc-header">
      <div class="pc-left">
        <div class="pc-num">PROMPT 07</div>
        <div class="pc-title">Seasonal &amp; Trending Content Planner</div>
        <div class="pc-use">✅ Best for: Creating timely content that gets algorithmic boost</div>
      </div>
      <button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button>
    </div>
    <div class="prompt-box">I am a [NICHE] creator and I want to plan content around [MONTH / SEASON / UPCOMING HOLIDAY OR EVENT].

Create a content plan that:
1. Identifies 8 seasonal angles that connect [MY NICHE] to this time of year naturally (not forced)
2. For each angle: give me the hook, the content type, and the platform
3. Identifies 3–5 trending sounds, formats, or challenges happening right now that I can adapt to my niche
4. Gives me a 2-week posting schedule with content type variety (educational, personal, promotional, trending)
5. Flags any content that would work as a series or multi-part post

The goal is to feel timely and relevant without losing my core message and niche identity.</div>
    <div class="pc-meta">
      <span class="pc-tag">📅 Seasonal</span>
      <span class="pc-tag">🔥 Trending</span>
      <div class="pro-tip"><strong>💡 Pro tip:</strong> Seasonal content often gets extra algorithmic push. Plan it 2 weeks ahead so you're not rushing when the moment arrives.</div>
    </div>
  </div>

  <div class="prompt-card t-amber">
    <div class="pc-header">
      <div class="pc-left">
        <div class="pc-num">PROMPT 08</div>
        <div class="pc-title">The Repurposing Machine</div>
        <div class="pc-use">✅ Best for: Squeezing maximum value from every piece of content you create</div>
      </div>
      <button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button>
    </div>
    <div class="prompt-box">I have a piece of content about [DESCRIBE THE CONTENT — e.g., "a 90-second TikTok about how I made my first $500 with digital products using only free tools"].

Give me 15 ways to repurpose this into different formats:
— 3 Instagram carousel slides (give me the slide titles and key points)
— 2 Instagram Stories sequences (give me the slide-by-slide breakdown)
— 1 YouTube Shorts version (what gets cut, what stays, new hook)
— 1 Pinterest pin description and title
— 1 email newsletter section using this as the main content
— 1 Twitter/X thread (5–7 tweets)
— 2 caption variations (one short, one long-form)
— 3 new video ideas this content inspired
— 1 FAQ-style Q&amp;A video using questions this content would generate

For each repurpose, tell me the hook, the platform, and what's different about this version versus the original.</div>
    <div class="pc-meta">
      <span class="pc-tag">♻️ Repurposing</span>
      <span class="pc-tag">⚡ Efficiency</span>
      <div class="pro-tip"><strong>💡 Pro tip:</strong> One great piece of content = 15+ pieces across platforms. Stop creating new content when you haven't fully mined what you already have.</div>
    </div>
  </div>

  <div class="prompt-card t-amber">
    <div class="pc-header">
      <div class="pc-left">
        <div class="pc-num">PROMPT 09</div>
        <div class="pc-title">The "What I Wish I Knew" Generator</div>
        <div class="pc-use">✅ Best for: Beginner-focused content that performs incredibly well</div>
      </div>
      <button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button>
    </div>
    <div class="prompt-box">I have been [DOING YOUR NICHE ACTIVITY] for [TIMEFRAME]. Generate content ideas based on the gap between what I know now and what I wish someone had told me when I started.

Give me:
1. 10 "I wish someone told me this" content ideas — each framed as a beginner mistake, a shortcut discovered late, or a mindset shift that changed everything
2. 5 "Things that seem true but aren't" myth-busting ideas in my niche
3. 5 "Nobody talks about this but..." ideas that feel like insider knowledge
4. 3 "I wasted [TIME/MONEY] on this before I discovered [BETTER WAY]" story ideas

For each, give me the hook, the core lesson, and the CTA. These should feel like advice from a trusted friend who's a few steps ahead — not a lecture from an expert.</div>
    <div class="pc-meta">
      <span class="pc-tag">🌱 Beginner Content</span>
      <span class="pc-tag">💡 High-Value</span>
      <div class="pro-tip"><strong>💡 Pro tip:</strong> "What I wish I knew" content has massive save rates because beginners bookmark it for reference. It also builds enormous trust.</div>
    </div>
  </div>

  <div class="prompt-card t-amber">
    <div class="pc-header">
      <div class="pc-left">
        <div class="pc-num">PROMPT 10</div>
        <div class="pc-title">Faceless &amp; B-Roll Content Ideas</div>
        <div class="pc-use">✅ Best for: Creators who don't want to be on camera</div>
      </div>
      <button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button>
    </div>
    <div class="prompt-box">I want to create [NUMBER] pieces of content for [PLATFORM] without appearing on camera. My niche is [NICHE] and my audience is [AUDIENCE].

Generate:
1. 10 faceless video content ideas using text overlays + voiceover + B-roll footage
2. 5 screen-recording or tutorial-style content ideas where I show my screen
3. 5 aesthetic or lifestyle B-roll concepts where I show hands, objects, or environment — not my face
4. 3 AI avatar or AI voice content ideas that would work for my niche

For each idea:
— Describe exactly what footage or visuals would be shown
— Write the text overlay script or voiceover outline
— Suggest what free stock footage sources could supply the visuals (Pexels, Pixabay, etc.)
— Rate it 1–10 for estimated engagement potential in my niche</div>
    <div class="pc-meta">
      <span class="pc-tag">🎭 Faceless</span>
      <span class="pc-tag">🎬 B-Roll</span>
      <div class="pro-tip"><strong>💡 Pro tip:</strong> Faceless content can perform just as well as face-forward content when the value is high. The hook and text overlay matter more than showing your face.</div>
    </div>
  </div>

  <div class="prompt-card t-amber">
    <div class="pc-header">
      <div class="pc-left">
        <div class="pc-num">PROMPT 11</div>
        <div class="pc-title">90-Day Content Strategy Builder</div>
        <div class="pc-use">✅ Best for: Building a strategic, intentional content plan from scratch</div>
      </div>
      <button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button>
    </div>
    <div class="prompt-box">Build me a 90-day content strategy for a [NICHE] creator on [PLATFORM] starting from [APPROXIMATE FOLLOWER COUNT OR "0 followers"].

My goal is: [YOUR SPECIFIC GOAL — e.g., "reach 10,000 followers and make my first $1,000 from digital products"]
My current posting frequency: [HOW OFTEN YOU POST]
Content I'm comfortable creating: [VIDEO / CAROUSEL / STORIES / LIVE / ALL]

Give me:
— Month 1 focus: What I should post, how often, and why (foundation-building phase)
— Month 2 focus: What shifts, what content types to add, engagement goals
— Month 3 focus: Monetization content, offers, and growth acceleration

For each month:
— 3 content pillars to focus on
— Example content ideas for each pillar
— What metrics to track to know if it's working
— One "bold move" to make that month to accelerate growth

Be specific and realistic. Not a fluffy plan — an actual roadmap.</div>
    <div class="pc-meta">
      <span class="pc-tag">🗺️ Strategy</span>
      <span class="pc-tag">📈 Growth</span>
      <div class="pro-tip"><strong>💡 Pro tip:</strong> Print this plan. Put it somewhere visible. Strategy only works when you actually follow it.</div>
    </div>
  </div>

  <div class="prompt-card t-amber">
    <div class="pc-header">
      <div class="pc-left">
        <div class="pc-num">PROMPT 12</div>
        <div class="pc-title">Viral Content Reverse-Engineer</div>
        <div class="pc-use">✅ Best for: Understanding why content goes viral and replicating it</div>
      </div>
      <button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button>
    </div>
    <div class="prompt-box">Here is a description of a piece of content that performed extremely well in my niche: [DESCRIBE THE VIRAL OR HIGH-PERFORMING VIDEO — include the hook, topic, format, and approximate views/engagement].

Reverse-engineer why this worked:
1. What psychological triggers did it activate? (curiosity, fear of missing out, relatability, controversy, inspiration, etc.)
2. What made the hook impossible to scroll past?
3. What did it do in the first 3 seconds to earn the watch?
4. What content formula or structure did it follow?
5. Why did people share, save, or comment on it specifically?

Now give me:
— 5 content ideas that use the same psychological framework but applied to different topics in my niche [NICHE]
— The hook formula extracted from this video as a reusable template
— What I should NOT copy (the surface-level stuff that wouldn't work for me)</div>
    <div class="pc-meta">
      <span class="pc-tag">🔬 Analysis</span>
      <span class="pc-tag">🚀 Viral Framework</span>
      <div class="pro-tip"><strong>💡 Pro tip:</strong> Study the top 5 videos in your niche every week. Pattern recognition is the most underrated creator skill.</div>
    </div>
  </div>
</div>

<!-- SECTION 2: HOOKS -->
<div class="t-pink" id="hooks">
  <div class="section-hdr">
    <div class="sh-top"><span class="sh-badge">CATEGORY 02</span></div>
    <h2>🎣 Hook Writing Prompts</h2>
    <div class="sh-sub">Write scroll-stopping openers that earn the watch every single time</div>
    <div class="sh-desc">Your hook is the first 1–3 seconds — the entire game. These prompts generate batches of tested hook formulas for every content type and every emotion you want to trigger.</div>
    <div class="section-count">📦 12 Prompts in this category</div>
  </div>
  <div class="sec-divider"></div>

  <div class="prompt-card t-pink">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 01</div><div class="pc-title">The 10-Hook Generator</div><div class="pc-use">✅ Best for: Any video — run this before every single post</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Write 10 completely different hooks for a video about [VIDEO TOPIC]. Use one of each of these formulas:

1. Curiosity gap: "Nobody talks about this, but..."
2. Controversy: "Unpopular opinion:"
3. Story: Drop into the middle of a moment — past tense, specific, emotional
4. Result-first: Lead with the outcome before the how
5. Question: Call out a mistake or create self-identification
6. Bold claim: Make an audacious statement that demands proof
7. List: "X things you need to know about..."
8. Agitation: "Stop scrolling if you're tired of..."
9. Contrast: "Everyone told me [X]. They were wrong."
10. Direct: "Here is exactly how to [RESULT] in [TIMEFRAME]."

For each hook:
— Write it out in full (1–2 sentences max)
— Rate it 1–10 for scroll-stopping power
— Note which emotion it triggers (curiosity / fear / inspiration / relatability / controversy)

My audience: [AUDIENCE DESCRIPTION]</div>
    <div class="pc-meta"><span class="pc-tag">🎣 Hook Formulas</span><span class="pc-tag">📱 All Platforms</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Test 3 hooks on similar content over time. The one with the highest 3-second view rate wins — use that formula again and again.</div></div>
  </div>

  <div class="prompt-card t-pink">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 02</div><div class="pc-title">Curiosity Gap Hook Deep Dive</div><div class="pc-use">✅ Best for: Educational content where mystery drives watch time</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Write 12 curiosity-gap hooks for a video about [TOPIC].

A curiosity gap hook creates an information gap so uncomfortable that the viewer HAS to watch to close it. They should feel like they're about to learn something most people don't know — something that will change how they see [TOPIC].

Rules:
— Each hook must open a gap without closing it
— Use second person ("you") where possible
— Be specific, not vague
— Avoid clickbait that doesn't deliver — these should tease something real

Starter phrases to use (use each at least once):
"Nobody talks about this, but..."
"I wish someone told me this sooner..."
"What they don't tell you about..."
"The reason most people fail at [X] has nothing to do with..."
"This is the part of [TOPIC] that every expert skips..."
"What actually happens when you..."
"Most people get this completely wrong..."
"There's a reason [COMMON APPROACH] doesn't work..."
"The thing that changed everything for me was..."
"This took me [TIMEFRAME] to figure out..."

Rate each 1–10 for curiosity level.</div>
    <div class="pc-meta"><span class="pc-tag">🧠 Curiosity</span><span class="pc-tag">📚 Educational</span><div class="pro-tip"><strong>💡 Pro tip:</strong> The more specific the curiosity gap, the higher the watch time. "Something you don't know" is weak. "The one mistake that kills every creator's growth in month 3" is powerful.</div></div>
  </div>

  <div class="prompt-card t-pink">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 03</div><div class="pc-title">Story Hook Generator</div><div class="pc-use">✅ Best for: Transformation stories, journey content, personal brand videos</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Write 10 story-based hooks for a video about [MY STORY OR VIDEO TOPIC].

A story hook drops the viewer into the middle of a specific moment — not a summary of the story, but the scene itself. Use:
— Past tense and specific sensory or emotional details
— Exact numbers, dates, or amounts where possible
— A moment of tension, failure, embarrassment, or breakthrough
— First-person and present-moment language even in past tense

Examples of what GOOD looks like:
"Six months ago I was applying for a 9-to-5 I didn't even want. Last week I made $3,000 in a single afternoon."
"I almost quit on day 47. I had made exactly $0. Then something weird happened."
"The day I posted my first video I had 14 followers. Three of them were my mom."

For each hook:
— Write the full 1–3 sentence hook
— Note the emotional trigger (vulnerability / triumph / relatability / humor / transformation)
— Suggest what the first 10 seconds after the hook would show

My story context: [DESCRIBE YOUR STORY OR TRANSFORMATION IN 3–4 SENTENCES]</div>
    <div class="pc-meta"><span class="pc-tag">📖 Storytelling</span><span class="pc-tag">💜 Connection</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Specificity is everything in story hooks. "$523" beats "some money." "Day 47" beats "a while in." Real details make people believe you.</div></div>
  </div>

  <div class="prompt-card t-pink">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 04</div><div class="pc-title">Controversy &amp; Hot Take Hooks</div><div class="pc-use">✅ Best for: Opinion content, myth-busting, high-comment videos</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Write 10 controversy-style hooks for content where I share a bold opinion about [TOPIC OR COMMON BELIEF IN YOUR NICHE].

These hooks should be bold enough to stop the scroll but not dishonest or misleading. The goal is to make someone think "wait, really?" or "I have to hear this" — not to be edgy for no reason.

Use openers like:
"Unpopular opinion:"
"Hot take:"
"Nobody wants to hear this but:"
"I'm going to get hate for saying this, but:"
"Everyone is wrong about [TOPIC]."
"Stop [COMMON ADVICE EVERYONE GIVES]."
"[THING EVERYONE BELIEVES] is actually holding you back."
"The [CONVENTIONAL WISDOM] advice is destroying your [OUTCOME]."
"What the gurus won't tell you about [TOPIC]:"
"I used to believe [COMMON BELIEF]. I was completely wrong."

For each hook:
— Write it in full
— State the actual controversial claim being set up
— Rate 1–10 for controversy level (5–7 is the sweet spot — provocative but not offensive)
— Note potential objections someone might have so I can address them in the video</div>
    <div class="pc-meta"><span class="pc-tag">🔥 Controversy</span><span class="pc-tag">💬 High Comments</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Controversy drives comments. Comments drive reach. Use controversy sparingly — 1 in 5 posts max — so your account stays trustworthy.</div></div>
  </div>

  <div class="prompt-card t-pink">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 05</div><div class="pc-title">Result-First Hook Writer</div><div class="pc-use">✅ Best for: Case studies, "how I did it" videos, proof-of-concept content</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Write 12 result-first hooks for a video about [RESULT YOU ACHIEVED OR TOPIC YOU TEACH].

A result-first hook leads with the outcome BEFORE explaining the method. It makes the viewer believe the result is real and possible, then creates curiosity about how.

Formula pattern: "[Specific result] in [specific timeframe]. Here is exactly how." or "I [achieved specific result] doing only [surprising simple method]."

Rules for these hooks:
— Use SPECIFIC numbers wherever possible (not "a lot of money" — say "$847")
— Include a timeframe (not "quickly" — say "in 11 days")
— The result should feel impressive but believable — not too perfect
— The method hinted at should feel surprisingly simple or unexpected

My results to work with: [LIST 2–3 REAL RESULTS YOU'VE ACHIEVED — views, income, followers, transformations, etc.]

For each hook:
— Write the full hook (1–2 sentences)
— Rate how "believable but impressive" it feels on a 1–10 scale
— Note what makes a viewer curious to stay and watch</div>
    <div class="pc-meta"><span class="pc-tag">💰 Results</span><span class="pc-tag">📊 Proof</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Result-first hooks work best when the result is real. Exaggerating destroys trust. Use your real numbers — even small ones — because authenticity outperforms hype.</div></div>
  </div>

  <div class="prompt-card t-pink">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 06</div><div class="pc-title">Question Hook Creator</div><div class="pc-use">✅ Best for: Content where you want instant self-identification from viewers</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Write 10 question-style hooks for a video about [TOPIC]. 

The best question hooks make the viewer either:
(a) Immediately think "yes, that's me" — self-identification
(b) Realize they might be making a mistake — fear of missing out
(c) Wonder if they know the answer — curiosity trigger

Categories to write:
— 3 "Are you making this mistake?" hooks
— 3 "Do you know [surprising fact]?" hooks  
— 2 "What if I told you [unexpected truth]?" hooks
— 2 "Why does [confusing thing happen]?" hooks

Rules:
— Keep questions short — under 12 words
— Use second person ("you") — make it personal
— The question should be answerable by watching the video — don't open a gap you can't close
— Avoid vague questions like "Have you ever thought about...?" — be specific

My audience struggles with: [LIST 2–3 MAIN STRUGGLES]

For each: write the hook, identify the trigger type, and rate 1–10.</div>
    <div class="pc-meta"><span class="pc-tag">❓ Questions</span><span class="pc-tag">🎯 Self-ID</span><div class="pro-tip"><strong>💡 Pro tip:</strong> The best question hooks answer themselves with a nod. If your viewer says "yes" in their head in the first second, they're already invested.</div></div>
  </div>

  <div class="prompt-card t-pink">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 07</div><div class="pc-title">Live Stream Opening Hook Pack</div><div class="pc-use">✅ Best for: TikTok and Instagram LIVE — the first 60 seconds</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Write a complete opening script for a TikTok / Instagram LIVE about [LIVE TOPIC OR THEME].

The opening must accomplish ALL of the following in under 90 seconds:
1. Stop people from scrolling past (hook line — the very first thing I say)
2. Tell people exactly who this live is for and why they should stay
3. Create urgency to stick around right now (what will they miss if they leave?)
4. Get the first comment or emoji drop in the first 30 seconds
5. Introduce myself in one sentence for new viewers
6. Tease what's coming in the next 30 minutes

Then write 8 standalone live-opening hooks (just the first 1–2 sentences) I can use to start any live session:
— 2 curiosity-based openers
— 2 value-promise openers ("By the end of this live you'll know...")
— 2 engagement-first openers ("Drop a [emoji] if...")
— 2 urgency openers ("I'm only doing this ONCE so stick around...")

My niche: [NICHE]. My live topic today: [TOPIC].</div>
    <div class="pc-meta"><span class="pc-tag">📡 Live Stream</span><span class="pc-tag">⚡ First 60 Seconds</span><div class="pro-tip"><strong>💡 Pro tip:</strong> The first 60 seconds of a live determines your retention for the entire session. Nail it every time — never wing it.</div></div>
  </div>

  <div class="prompt-card t-pink">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 08</div><div class="pc-title">Text Overlay Hook Creator</div><div class="pc-use">✅ Best for: Silent-scroll content, aesthetic videos, B-roll with text</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">I need bold, punchy text overlay hooks for a video about [TOPIC] where the first 3 seconds have no speaking — just text on screen.

Write 12 text overlay hook options. Rules:
— Each hook must work with SOUND OFF (no reliance on audio)
— Under 8 words per line — big, readable, impactful
— Format them as 2-line overlays: [LINE 1] / [LINE 2]
— They should create instant visual curiosity or a pattern interrupt
— Avoid generic phrases — make them feel like they were written specifically for THIS topic

Also write:
— 3 versions where the text escalates over 3 frames (like a drumroll reveal)
— 2 versions that use contrast ("Before: [bad thing]. After: [good thing].")
— 2 versions that use numbers prominently ("$0 → $2,847. Here's what changed.")

Topic: [YOUR TOPIC]
Aesthetic/vibe of my content: [DESCRIBE — minimal, bold, aesthetic, dark, bright, etc.]</div>
    <div class="pc-meta"><span class="pc-tag">📝 Text Overlays</span><span class="pc-tag">🔇 Silent Scroll</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Over 60% of TikTok is watched with sound off in public. Your text overlay IS your hook for the majority of viewers. Treat it with the same care as a spoken hook.</div></div>
  </div>

  <div class="prompt-card t-pink">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 09</div><div class="pc-title">Hook A/B Test Generator</div><div class="pc-use">✅ Best for: Testing hook formulas to find what resonates with your specific audience</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">I want to A/B test hooks on [PLATFORM] for content about [TOPIC]. Generate 3 completely different hook versions for the same video — each using a fundamentally different psychological approach.

Version A — Curiosity-driven: Opens an information gap, teases something they don't know
Version B — Result-driven: Leads with the outcome, makes them want the "how"
Version C — Relatability-driven: Makes them feel seen, mirrors their exact situation

For each version, write:
— The full hook (spoken or text overlay)
— What emotion it's designed to trigger
— What type of viewer it will resonate with most
— What to put in the first 10 seconds after the hook to pay it off

Also tell me:
— Which version you'd predict performs best for my audience ([AUDIENCE]) and why
— What metric to look at after 24–48 hours to declare a winner (views, watch time, saves, etc.)
— What to do with the losing versions — can they be repurposed?</div>
    <div class="pc-meta"><span class="pc-tag">🧪 A/B Testing</span><span class="pc-tag">📊 Data-Driven</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Once you find a hook formula that consistently outperforms, reverse-engineer what made it work and apply that pattern to all future hooks.</div></div>
  </div>

  <div class="prompt-card t-pink">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 10</div><div class="pc-title">Niche-Specific Hook Library</div><div class="pc-use">✅ Best for: Building a personal swipe file of hooks that work in your exact niche</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Build me a personal hook library for a [NICHE] creator targeting [AUDIENCE].

I want 30 hooks organized into 5 categories of 6 each:

CATEGORY 1 — INCOME &amp; RESULTS hooks (for content about money, earnings, or measurable outcomes)
CATEGORY 2 — BEGINNER TRANSFORMATION hooks (for content about starting from zero)
CATEGORY 3 — MISTAKE &amp; WARNING hooks (for content about what NOT to do)
CATEGORY 4 — SECRET / INSIDER hooks (for content that reveals something most people don't know)
CATEGORY 5 — MOTIVATIONAL &amp; MINDSET hooks (for content about perspective, belief, and identity)

For each hook:
— Write it in full
— Note the ideal content format it pairs with (video, carousel, live, etc.)
— Flag which ones work best as spoken hooks vs. text overlays

These hooks should feel specific to my niche — not generic templates that could apply to any creator. They should sound like something someone in [NICHE] would actually say.</div>
    <div class="pc-meta"><span class="pc-tag">🗂️ Swipe File</span><span class="pc-tag">🎣 Hook Library</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Save this as a notes file on your phone. Next time you go to post and can't think of a hook, open the list and grab one. Done.</div></div>
  </div>

  <div class="prompt-card t-pink">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 11</div><div class="pc-title">Carousel First-Slide Hook</div><div class="pc-use">✅ Best for: Instagram and TikTok carousel posts — the cover slide</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Write 10 first-slide hooks for an Instagram or TikTok carousel about [CAROUSEL TOPIC].

The first slide of a carousel is the hook — it must be compelling enough to make someone swipe. Rules:
— Bold headline: 4–7 words that create urgency or curiosity
— Sub-line: 1 sentence that expands and deepens the hook
— Visual suggestion: what should be on the background or graphic of this slide?

Formats to write:
— 3 number-led hooks ("7 things creators don't know about...")
— 3 question hooks ("Are you making this mistake?")
— 2 bold claim hooks ("Everything you know about X is wrong")
— 2 how-to hooks ("How to [RESULT] without [PAIN POINT]")

For each: write the headline, sub-line, and visual suggestion. Also rate which 3 you'd put at the top of the list and why.

Carousel topic: [TOPIC]
Audience: [AUDIENCE]</div>
    <div class="pc-meta"><span class="pc-tag">🖼️ Carousels</span><span class="pc-tag">👉 Swipe Rate</span><div class="pro-tip"><strong>💡 Pro tip:</strong> The first slide determines swipe rate. If nobody swipes, nobody sees your content. Treat it like a video hook — it's equally important.</div></div>
  </div>

  <div class="prompt-card t-pink">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 12</div><div class="pc-title">Hook Diagnostic &amp; Rewriter</div><div class="pc-use">✅ Best for: Fixing hooks that aren't performing the way you expected</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Here is a hook I used that did not perform well: "[PASTE YOUR UNDERPERFORMING HOOK HERE]"

The video was about: [TOPIC]
It got: [VIEWS / WATCH TIME / ENGAGEMENT]
My audience is: [AUDIENCE]

Diagnose why this hook underperformed:
1. What psychological trigger (if any) was it trying to activate?
2. Where did it fail — too vague, too generic, no curiosity gap, no emotional trigger?
3. Who specifically would this hook speak to — and is that the right audience?
4. Does it make a promise the video can actually deliver on?

Now rewrite it 5 different ways — each using a different hook formula. For each rewrite:
— Write the new hook in full
— Explain what formula it uses
— Explain why it should outperform the original
— Rate your confidence it would perform better: low / medium / high

Which of the 5 rewrites would you post first and why?</div>
    <div class="pc-meta"><span class="pc-tag">🔧 Fix &amp; Improve</span><span class="pc-tag">📉 Troubleshoot</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Every underperforming video is data. Use this prompt to extract the lesson so the next version wins.</div></div>
  </div>
</div>

<!-- SECTION 3: CAPTIONS -->
<div class="t-purple" id="captions">
  <div class="section-hdr">
    <div class="sh-top"><span class="sh-badge">CATEGORY 03</span></div>
    <h2>✍️ Caption Writing Prompts</h2>
    <div class="sh-sub">Write engaging captions that drive saves, follows, and clicks on every platform</div>
    <div class="sh-desc">A great caption extends your content, deepens trust, and drives action. These prompts handle every platform and every content goal.</div>
    <div class="section-count">📦 10 Prompts in this category</div>
  </div>
  <div class="sec-divider"></div>

  <div class="prompt-card t-purple">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 01</div><div class="pc-title">TikTok Caption with CTA</div><div class="pc-use">✅ Best for: Every TikTok post</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Write 3 TikTok caption variations for a video about [VIDEO TOPIC]. 

For each variation:
— First line: punchy and curiosity-driven (this is what shows before "more")
— Body: 1–2 sentences that add context or tease the video content
— CTA line: one specific action (follow, save, comment a word, click link in bio)
— Hashtag block: 5 hashtags — 2 large (1M+), 2 medium (100K–500K), 1 niche-specific

Variation 1: Curiosity-led caption (tease something from the video)
Variation 2: Value-led caption (state the main takeaway upfront)
Variation 3: Engagement-led caption (drive comments with a question or "drop an emoji if...")

Audience: [AUDIENCE]
Video hook: [YOUR HOOK]
Tone: [casual / motivational / professional / direct]</div>
    <div class="pc-meta"><span class="pc-tag">📱 TikTok</span><span class="pc-tag">🔗 CTA</span><div class="pro-tip"><strong>💡 Pro tip:</strong> TikTok captions are read AFTER someone watches. Your CTA is the last impression — make it feel like a natural next step, not a demand.</div></div>
  </div>

  <div class="prompt-card t-purple">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 02</div><div class="pc-title">Instagram Reels Caption (Full Structure)</div><div class="pc-use">✅ Best for: Instagram Reels and feed posts</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Write a full Instagram Reels caption for a video about [VIDEO TOPIC].

Structure EXACTLY as follows:
LINE 1 (Hook — shows before "more" cutoff): Must be compelling enough on its own to make someone tap "more." Curiosity, bold claim, or strong opener. MAX 125 characters.

[LINE BREAK]

BODY (3–5 sentences): Add real value that wasn't in the video. Give context, backstory, or an extra tip. Write in a warm, conversational first-person voice. Don't summarize the video — EXPAND it.

[LINE BREAK]

LESSON or TAKEAWAY: One sentence that distills the core message.

[LINE BREAK]

CTA: One specific action. Ask a question OR direct to link in bio — not both.

[3 LINE BREAKS]

HASHTAG BLOCK (10 hashtags, separated by line breaks):
Mix: 3 large (1M+), 4 medium (100K–500K), 3 niche/micro

Video topic: [TOPIC]
My niche: [NICHE]
Audience: [AUDIENCE]
Tone: [TONE]</div>
    <div class="pc-meta"><span class="pc-tag">📸 Instagram</span><span class="pc-tag">💾 Saves</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Instagram captions have more real estate than TikTok. Use that space to add depth — a longer caption signals that you care about your audience.</div></div>
  </div>

  <div class="prompt-card t-purple">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 03</div><div class="pc-title">The Save-Bait Caption</div><div class="pc-use">✅ Best for: Educational content — the highest-value engagement signal on Instagram</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Write a caption for a [PLATFORM] post about [TOPIC] that is SPECIFICALLY engineered to drive saves.

To earn a save, the caption itself must contain value the viewer wants to refer back to. The post should feel like a mini resource — not just a description of the video.

Include in the caption body:
— A numbered or bulleted list of [3–5] specific, actionable tips, steps, or insights
— At least one piece of information that feels like insider knowledge
— Language that tells the reader to save it: "Save this for later" / "Bookmark this" / "You'll want to come back to this"

End with a CTA that reinforces saving: "Save this so you don't lose it 📌" or similar.

Keep the overall length between 150–280 words.

Topic: [YOUR TOPIC]
Key points to include: [LIST 3–5 REAL TIPS OR POINTS FROM YOUR VIDEO]</div>
    <div class="pc-meta"><span class="pc-tag">📌 Save Rate</span><span class="pc-tag">📚 Value</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Saves are the strongest signal to the Instagram algorithm that your content is valuable. Every educational post should have at least one "save this" CTA.</div></div>
  </div>

  <div class="prompt-card t-purple">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 04</div><div class="pc-title">Comment-Driving Caption</div><div class="pc-use">✅ Best for: Boosting reach through comment volume</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Write a caption for a [PLATFORM] video about [TOPIC] that is specifically engineered to drive a high comment volume.

Tactics to use (include at least 3):
— End with a simple question anyone can answer in under 5 words
— Include a "drop an emoji if..." line
— Use a "Tell me in the comments..." prompt with a specific focus
— Create a this-or-that poll question in the caption
— Use "Tag someone who needs to see this" (if appropriate)
— Ask for a 1-word answer: "Comment the first word that comes to mind"
— "Type YES if this is you" prompt

Rules:
— The question must be EASY to answer — not philosophical or open-ended
— It should feel like a natural conversation starter, not a survey
— The rest of the caption should deliver real value so commenting feels like joining a real conversation

Write 3 full caption variations using different comment-driving tactics.

Topic: [YOUR TOPIC]
Audience: [AUDIENCE]</div>
    <div class="pc-meta"><span class="pc-tag">💬 Comments</span><span class="pc-tag">📈 Reach</span><div class="pro-tip"><strong>💡 Pro tip:</strong> "Drop a 🔥 if this is you" gets more comments than "What do you think?" Simple prompts beat complex ones every single time.</div></div>
  </div>

  <div class="prompt-card t-purple">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 05</div><div class="pc-title">Story Promotion Sequence</div><div class="pc-use">✅ Best for: Selling or promoting through Instagram / TikTok Stories</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Write a 5-slide Instagram Stories sequence promoting [PRODUCT / OFFER / DIGITAL DOWNLOAD / AFFILIATE LINK].

Slide 1 — TEASE: Create curiosity without revealing the product. Make them want to tap to the next slide. Under 15 words.

Slide 2 — THE PROBLEM: Speak directly to the pain point this product solves. Make them feel understood. 2–3 sentences.

Slide 3 — THE REVEAL: Introduce the product. What it is, what it does, why it matters. Include an engagement sticker (poll: "Would you use this? Yes / Tell me more").

Slide 4 — PROOF / SOCIAL PROOF: One result, testimonial, or transformation. If you don't have one yet, use a strong benefit statement.

Slide 5 — CTA SLIDE: Clear, direct, specific. Tell them exactly what to do and where to go. Create mild urgency without being pushy.

Product: [PRODUCT NAME AND DESCRIPTION]
Price: $[PRICE]
Who it's for: [TARGET AUDIENCE]
Link: [WHERE TO SEND THEM — link in bio / direct link / DM "WORD" for link]</div>
    <div class="pc-meta"><span class="pc-tag">📲 Stories</span><span class="pc-tag">💰 Selling</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Story sequences convert better than single promo stories. Give your audience a journey — tease, problem, reveal, proof, buy.</div></div>
  </div>

  <div class="prompt-card t-purple">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 06</div><div class="pc-title">Long-Form Story Caption</div><div class="pc-use">✅ Best for: Building deep emotional connection and brand loyalty</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Write a long-form Instagram or TikTok caption (220–350 words) for a post about [TOPIC OR PERSONAL STORY].

This caption should build emotional connection and make the reader feel like they truly know me. It's not a summary — it's a story.

Structure:
OPENER (2–3 sentences): Drop into a specific moment. A real scene, a real emotion, a real detail. No "Hey guys!" No generic intros.

THE BEFORE (3–4 sentences): Where were you before? What were you struggling with? Be specific and honest — don't sanitize it.

THE TURNING POINT (2–3 sentences): What changed? What did you discover, decide, or do differently?

THE AFTER (2–3 sentences): Where are you now? Be specific — numbers, details, feelings.

THE LESSON (1–2 sentences): What's the one takeaway your audience can apply to their own life or business?

RELATABLE CLOSE (1–2 sentences): Make them feel seen. "If you're in the before right now, I need you to know..."

CTA: One question that invites them to share their own story in the comments.

My story: [DESCRIBE YOUR STORY OR TRANSFORMATION IN 3–5 SENTENCES]
Tone: [warm / vulnerable / motivational / honest]</div>
    <div class="pc-meta"><span class="pc-tag">📖 Storytelling</span><span class="pc-tag">💜 Connection</span><div class="pro-tip"><strong>💡 Pro tip:</strong> The accounts people stay loyal to for years are the ones they feel like they know personally. Long-form story captions build that bond faster than anything else.</div></div>
  </div>

  <div class="prompt-card t-purple">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 07</div><div class="pc-title">YouTube Shorts Caption &amp; Description</div><div class="pc-use">✅ Best for: YouTube Shorts — where SEO matters more than any other short-form platform</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Write a complete YouTube Shorts description for a video about [TOPIC].

YouTube descriptions are searchable — this needs to work for both humans AND search algorithms.

Section 1 — HOOK LINE (first 100 characters — visible without clicking "show more"):
A search-friendly first sentence that clearly states what the video is about AND creates curiosity.

Section 2 — VIDEO SUMMARY (2–3 sentences):
Describe what the viewer will learn or see. Use natural keyword language — how would someone search for this?

Section 3 — KEY POINTS (optional, if relevant):
Bullet list of 3–5 key takeaways. Helps with search and gives skimmers a reason to watch.

Section 4 — CTA:
Subscribe prompt + one specific next action.

Section 5 — HASHTAGS (8–10):
Mix of: #shorts, 2 topic hashtags, 3 niche hashtags, 2 audience hashtags

Topic: [YOUR TOPIC]
Main keyword I want to rank for: [KEYWORD]
Secondary keywords: [2–3 SECONDARY KEYWORDS]
Niche: [NICHE]</div>
    <div class="pc-meta"><span class="pc-tag">▶️ YouTube</span><span class="pc-tag">🔍 SEO</span><div class="pro-tip"><strong>💡 Pro tip:</strong> YouTube is a search engine. Your description is indexed. Write it like someone will find this video by searching — because they will.</div></div>
  </div>

  <div class="prompt-card t-purple">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 08</div><div class="pc-title">Caption Rewriter &amp; Upgrader</div><div class="pc-use">✅ Best for: Fixing captions that felt flat or didn't convert</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Here is a caption I wrote that didn't perform well: 

"[PASTE YOUR UNDERPERFORMING CAPTION HERE]"

Post details:
— Platform: [PLATFORM]
— Topic: [TOPIC]
— Results: [VIEWS / COMMENTS / SAVES / CLICKS — whatever you tracked]
— What I was hoping it would do: [GOAL — drive saves / get comments / sell product / gain followers]

Diagnose the problem:
1. What is missing from this caption that would make it more effective?
2. Does it have a clear hook before the "more" cutoff? If not, what should it be?
3. Is the CTA clear, specific, and single-focused?
4. Does it deliver enough value to earn a save or click?
5. Does it sound like a real person or like a marketing copy?

Rewrite it 3 ways:
Version A: Optimized for saves (add a value list or framework)
Version B: Optimized for comments (add a simple question or engagement prompt)
Version C: Optimized for follows (add a story or reason to follow for more)

For each, explain what you changed and why.</div>
    <div class="pc-meta"><span class="pc-tag">🔧 Fix</span><span class="pc-tag">📈 Optimize</span><div class="pro-tip"><strong>💡 Pro tip:</strong> You can re-post the same video with a better caption and often get significantly better results. The content isn't always the problem — sometimes it's just the caption.</div></div>
  </div>

  <div class="prompt-card t-purple">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 09</div><div class="pc-title">Product Launch Caption Pack</div><div class="pc-use">✅ Best for: Launching a new digital product or offer</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Write a 5-caption launch sequence for [PRODUCT NAME] launching on [DATE]. Each caption is for a different post in the lead-up to and during launch.

Post 1 (5 days before launch) — THE TEASE:
Don't reveal the product yet. Create curiosity. "Something I've been working on is almost ready..." Give a hint, not a reveal.

Post 2 (3 days before) — THE PROBLEM POST:
No mention of the product. Just speak to the pain point it solves. Make people feel seen and ready for a solution.

Post 3 (1 day before) — THE REVEAL:
Announce the product for the first time. Name, what it is, who it's for, price, and where to get it. Generate excitement.

Post 4 (Launch day) — THE FULL SELL:
Full sales caption. Benefits, what's inside, social proof, urgency, clear CTA with link.

Post 5 (Day 2 or last day) — LAST CHANCE:
FOMO and urgency without being pushy. Address the #1 objection. Remind them what they get and what they're missing.

Product: [PRODUCT NAME AND DESCRIPTION]
Price: $[PRICE]
Audience pain point: [MAIN PROBLEM IT SOLVES]
Platform: [PLATFORM]</div>
    <div class="pc-meta"><span class="pc-tag">🚀 Launch</span><span class="pc-tag">💰 Sales</span><div class="pro-tip"><strong>💡 Pro tip:</strong> A 5-post launch sequence outperforms a single launch post by 4–6x. Warm your audience up before you ask them to buy.</div></div>
  </div>

  <div class="prompt-card t-purple">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 10</div><div class="pc-title">Monthly Caption Pack Builder</div><div class="pc-use">✅ Best for: Batch-writing all your captions for the month in one sitting</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">I need to write captions for my [PLATFORM] content for the next 30 days. I post [X] times per week. My niche is [NICHE] and my audience is [AUDIENCE].

Here are my planned content topics for the month:
[LIST YOUR 12–20 PLANNED CONTENT TOPICS OR VIDEO IDEAS]

For each topic, write:
— A first-line hook (before the "more" cutoff)
— The caption body (2–4 sentences of value or context)
— One CTA
— 3–5 relevant hashtags

Vary the caption TYPES across the month. Distribute them as:
— 40% value/educational captions (drive saves)
— 25% story/personal captions (drive follows and connection)
— 20% engagement captions (drive comments)
— 15% promotional captions (drive clicks and sales)

Label each caption with its type so I know what role it plays in my strategy.</div>
    <div class="pc-meta"><span class="pc-tag">📅 Batch Writing</span><span class="pc-tag">🗓️ Monthly Plan</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Batch-write all your captions for the month on one day. Caption writing is a mental gear — staying in it for 2 hours beats switching in and out of creative mode all month.</div></div>
  </div>
</div>

<!-- SECTION 4: SCRIPTS -->
<div class="t-green" id="scripts">
  <div class="section-hdr">
    <div class="sh-top"><span class="sh-badge">CATEGORY 04</span></div>
    <h2>🎬 Script Writing Prompts</h2>
    <div class="sh-sub">Full video scripts for every format — educational, sales, story, UGC, and more</div>
    <div class="sh-desc">These prompts generate complete, ready-to-film scripts — not just outlines. Each one includes hook, body, and CTA so you can hit record the moment you finish reading.</div>
    <div class="section-count">📦 10 Prompts in this category</div>
  </div>
  <div class="sec-divider"></div>

  <div class="prompt-card t-green">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 01</div><div class="pc-title">60-Second Educational Script</div><div class="pc-use">✅ Best for: How-to content, tutorial shorts, tip videos</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Write a complete 60-second educational TikTok / Reels script about [TOPIC].

Write it exactly as I would SPEAK it — conversational, natural, first-person. Not how someone writes — how someone talks to a friend.

STRUCTURE:
[0–3 sec] HOOK: One sentence that stops the scroll. Use [HOOK TYPE — curiosity / result / question].
[3–8 sec] SETUP: One sentence of context or credibility. Why should they listen to me?
[8–20 sec] POINT 1: First tip, step, or insight. Be specific — give a real example or number.
[20–35 sec] POINT 2: Second tip. Build on the first.
[35–50 sec] POINT 3: Third tip. The most impactful or surprising one.
[50–60 sec] CTA: Follow for more + one specific next action. Make it feel natural — not salesy.

RULES:
— Each point is MAX 2–3 sentences
— No filler words like "so basically" or "you know what I mean"
— Read it aloud — if it takes more than 65 seconds, cut it
— End on a high note — the last thing they hear is the most memorable

Topic: [YOUR TOPIC]
Audience: [AUDIENCE]
My background/credibility on this topic: [YOUR EXPERIENCE]</div>
    <div class="pc-meta"><span class="pc-tag">📚 Educational</span><span class="pc-tag">⏱️ 60 Seconds</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Read the script out loud before filming. If you stumble anywhere, rewrite that line. Great scripts sound like effortless conversation.</div></div>
  </div>

  <div class="prompt-card t-green">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 02</div><div class="pc-title">Sales Video Script</div><div class="pc-use">✅ Best for: Promoting digital products, programs, or affiliate offers</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Write a 90-second sales video script for [PRODUCT NAME / OFFER].

This script should convert viewers into buyers without feeling like an advertisement. It should feel like an honest recommendation from someone who genuinely uses and believes in what they're selling.

STRUCTURE:
[0–5 sec] HOOK: Lead with the result, the transformation, or the pain point — not the product name.
[5–15 sec] PROBLEM: Agitate the pain your audience feels. Make them feel understood. Be specific.
[15–25 sec] TURNING POINT: "That's why I created / found / started using [PRODUCT]..."
[25–45 sec] WHAT'S INSIDE: Briefly list 3 key benefits or features. What does it DO for them?
[45–55 sec] PROOF: One real result or testimonial in one sentence. "Someone just [achieved result] using this."
[55–75 sec] THE OFFER: What they get, how much it costs, where to get it.
[75–90 sec] CTA: Specific and urgent but not pushy. "Link is in my bio — go grab it."

Product: [PRODUCT NAME]
Price: $[PRICE]
Main benefit: [THE #1 THING IT DOES FOR THEM]
Audience pain point: [WHAT THEY'RE STRUGGLING WITH]
Platform: [TIKTOK / INSTAGRAM / YOUTUBE]</div>
    <div class="pc-meta"><span class="pc-tag">💰 Sales</span><span class="pc-tag">🔗 Conversions</span><div class="pro-tip"><strong>💡 Pro tip:</strong> The best sales scripts spend 70% of the time on the problem and only 30% on the product. Make them feel the pain before you offer the solution.</div></div>
  </div>

  <div class="prompt-card t-green">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 03</div><div class="pc-title">Transformation Story Script</div><div class="pc-use">✅ Best for: Before-and-after content, personal journey videos, building deep trust</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Write a 60–90 second story-based transformation script for a video about [MY PERSONAL STORY OR TRANSFORMATION].

This is the most powerful content format because it's 100% unique to me. Nobody can copy my story.

STRUCTURE:
[0–5 sec] HOOK: Drop into the story at a peak emotional moment — not the beginning. Start mid-scene.
[5–20 sec] THE BEFORE: Where I was. Paint the picture of the struggle — specific details, not vague statements. What did it feel like? What was I doing wrong?
[20–35 sec] THE TURNING POINT: What changed? One specific thing I discovered, decided, or did. The moment everything shifted.
[35–55 sec] THE AFTER: Where I am now. Specific results, specific feelings, specific proof.
[55–70 sec] THE LESSON: What's the takeaway for the viewer? How does my story apply to them?
[70–90 sec] CTA: Invite them to follow for more content like this OR check the link in bio for [RELEVANT RESOURCE].

My story: [DESCRIBE YOUR TRANSFORMATION IN 4–6 SENTENCES — include the before, the turning point, and the after]
What I want the viewer to feel: [INSPIRED / HOPEFUL / UNDERSTOOD / MOTIVATED]</div>
    <div class="pc-meta"><span class="pc-tag">📖 Story</span><span class="pc-tag">💜 Trust</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Don't sanitize your story. The messier the before, the more powerful the after. Vulnerability is a growth strategy.</div></div>
  </div>

  <div class="prompt-card t-green">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 04</div><div class="pc-title">Day-in-the-Life Script</div><div class="pc-use">✅ Best for: Lifestyle content, parasocial connection, aspiration and relatability</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Write a day-in-the-life voiceover script for a video showing my routine as a [YOUR IDENTITY — e.g., "stay-at-home mom building an online business", "UGC creator working from home", "digital product creator"].

This should feel like a window into a real day — not a highlight reel, not a perfectly curated fantasy. Real moments, real wins, real challenges.

STRUCTURE:
[HOOK — 0–5 sec]: One line that makes someone think "I want THAT life" or "I relate to this so hard"
[MORNING — 10–20 sec]: First thing I do. Why. What it sets up for the day.
[WORK SESSION 1 — 20–35 sec]: A specific task I work on. Show the process, not just the result. Include a real challenge or imperfect moment.
[MIDDAY — 35–50 sec]: A win, a result, or an honest moment (the kid interrupted, the Wi-Fi cut out, the first sale came in).
[WORK SESSION 2 — 50–65 sec]: Another creation or business task. Something the viewer can picture doing themselves.
[CLOSE OF DAY — 65–80 sec]: One sentence reflection. What do I feel good about? What am I still working on?
[CTA — 80–90 sec]: "Follow me if you want to watch this journey in real time."

My daily reality: [DESCRIBE A TYPICAL DAY IN 3–5 SENTENCES]
What I want viewers to feel: [INSPIRED / LIKE THEY KNOW ME / THAT THIS IS ACHIEVABLE]</div>
    <div class="pc-meta"><span class="pc-tag">📅 Day-in-Life</span><span class="pc-tag">🤝 Connection</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Routine content is the single best format for building parasocial connection. People follow people, not information. Show your real life.</div></div>
  </div>

  <div class="prompt-card t-green">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 05</div><div class="pc-title">UGC Ad Script</div><div class="pc-use">✅ Best for: Brand deals, TikTok Shop, and affiliate content</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Write a 30–45 second UGC-style ad script for [PRODUCT NAME]. 

UGC ads convert when they sound like a real person talking to a friend — not a commercial. The moment it sounds scripted or "ad-like," viewers tune out.

STRUCTURE:
[0–5 sec] NATURAL HOOK: Something a real person would actually say. Not "Hey guys!" — something that sounds mid-conversation. Ex: "Okay I've been using this for two weeks and I need to tell you about it."
[5–15 sec] THE PROBLEM: The pain point this product solves, in the viewer's language. NOT: "Are you struggling with X?" YES: Casually mention how you personally dealt with this before.
[15–28 sec] THE PRODUCT: What it is, what it does. Specific. Not feature-listing — storytelling. What changed for YOU?
[28–38 sec] THE PROOF: One specific result or detail. A number, a time, a before-and-after.
[38–45 sec] SOFT CTA: Casual, not pushy. "I'll link it below" or "It's in my bio if you want to check it out." Never "BUY NOW."

Product: [PRODUCT NAME]
Key benefits: [LIST 2–3 REAL BENEFITS]
Target audience: [WHO THIS IS FOR]
What I personally love about it: [YOUR GENUINE OPINION]
Tone: [honest / excited but chill / conversational]</div>
    <div class="pc-meta"><span class="pc-tag">🎬 UGC</span><span class="pc-tag">🛒 TikTok Shop</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Read your UGC script out loud 3 times. If it still sounds like an ad on the third read, keep editing. Authentic UGC beats polished ads every time.</div></div>
  </div>

  <div class="prompt-card t-green">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 06</div><div class="pc-title">Product Review Script</div><div class="pc-use">✅ Best for: Affiliate marketing and brand partnership content</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Write a 60–90 second honest product review script for [PRODUCT NAME].

This is NOT an ad — it's a genuine review that happens to include an affiliate link. The goal is trust, not just sales. A review that acknowledges a downside converts better than a review that's all positive.

STRUCTURE:
[HOOK]: Lead with the most impressive thing about the product OR the most surprising discovery.
[FIRST IMPRESSION]: What did you think before you tried it? Set realistic expectations.
[FEATURE 1]: Most important benefit. Show it, don't just say it. "What this actually does is..."
[FEATURE 2]: Second benefit. Include a specific detail or use case.
[REAL RESULTS]: What actually happened when you used it? Be specific — numbers, timeframes, feelings.
[THE HONEST TAKE]: One thing it doesn't do perfectly. Being honest here builds enormous trust.
[WHO IT'S FOR]: Clearly state the ideal user. "If you're someone who [situation], this is for you."
[CTA]: "Link is in my bio / below" — casual, not urgent.

Product: [PRODUCT NAME AND WHAT IT DOES]
What I genuinely like about it: [YOUR REAL OPINION]
One honest limitation: [SOMETHING IT DOESN'T DO PERFECTLY]
My affiliate/store link: [LINK PLACEHOLDER]</div>
    <div class="pc-meta"><span class="pc-tag">⭐ Review</span><span class="pc-tag">🔗 Affiliate</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Mentioning one honest limitation makes the whole review MORE believable. Audiences know nothing is perfect — honesty earns clicks.</div></div>
  </div>

  <div class="prompt-card t-green">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 07</div><div class="pc-title">Live Stream Full Script</div><div class="pc-use">✅ Best for: TikTok and Instagram LIVE — never have dead air again</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Write a complete 30-minute LIVE script outline for a TikTok / Instagram Live about [LIVE TOPIC].

Include word-for-word scripts for the high-stakes moments and bullet-point outlines for the content sections.

WORD-FOR-WORD SECTIONS (write these out in full):
1. Opening Hook (first 60 seconds — see separate prompt for detail)
2. New Viewer Welcome lines (3 variations to use when someone joins)
3. Engagement Prompts (6 different "drop an emoji if..." or question prompts to scatter throughout)
4. Offer Mention Script (how to mention [YOUR PRODUCT/LINK] naturally 2–3 times — NOT salesy)
5. Dead Air Recovery lines (5 things to say when the comments go quiet)
6. Closing Script (last 2 minutes — strong CTA, reason to follow, tease for next live)

OUTLINE SECTIONS (bullet points):
— The main teaching or entertainment segment (20 minutes of what I'll actually do/say)
— 3 natural transition points to re-hook viewers who just joined
— Where to insert the offer mentions (minute marks)

Live topic: [YOUR TOPIC]
Offer I want to mention: [PRODUCT / LINK]
My goal for this live: [FOLLOWERS / SALES / COMMUNITY BUILDING]</div>
    <div class="pc-meta"><span class="pc-tag">📡 LIVE</span><span class="pc-tag">⏱️ 30 Minutes</span><div class="pro-tip"><strong>💡 Pro tip:</strong> You don't need to read the script — have it open on a second device as a safety net. The more you live, the less you'll need it.</div></div>
  </div>

  <div class="prompt-card t-green">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 08</div><div class="pc-title">Trending Format Script</div><div class="pc-use">✅ Best for: Riding trends without losing your niche message</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">I want to use the trending [DESCRIBE THE TREND OR FORMAT — e.g., "POV format", "silent acting with text overlay", "TikTok text story format", "green screen reaction", "split screen before/after"] to create content about [MY TOPIC].

Write a complete script that:
1. Fits the trend format naturally — describe exactly what I'm doing on screen
2. Still delivers my actual message about [TOPIC] — the trend is the vessel, not the message
3. Feels organic, not forced — like I genuinely participate in this trend

Include:
— What I'm doing on camera (actions, expressions, movements)
— Text overlays (if applicable) — written out word-for-word, slide by slide
— Any voiceover or spoken lines
— What audio/sound to use (if this is a trending sound format)
— How to end it in a way that drives engagement

Then tell me:
— What makes this work as trend content (the hook)
— What makes it uniquely MINE (the niche twist)
— The optimal posting time for this trend on [PLATFORM]</div>
    <div class="pc-meta"><span class="pc-tag">🔥 Trending</span><span class="pc-tag">📱 Viral Format</span><div class="pro-tip"><strong>💡 Pro tip:</strong> The best trend content takes the format and makes it specific to your niche. Trend + niche specificity = algorithm gold.</div></div>
  </div>

  <div class="prompt-card t-green">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 09</div><div class="pc-title">Carousel Script (Slide by Slide)</div><div class="pc-use">✅ Best for: Instagram and TikTok carousels — the highest-save content format</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Write a complete 8–10 slide carousel script about [CAROUSEL TOPIC] for [PLATFORM].

For EACH slide, give me:
— Slide headline (bold, under 8 words)
— Slide body copy (2–4 sentences of real value — not filler)
— Visual suggestion (what should be on screen — graphic, icon, photo, etc.)

SLIDE STRUCTURE:
Slide 1 — COVER SLIDE: Bold hook that makes someone swipe. Creates a pattern interrupt.
Slides 2–3 — THE PROBLEM: Establish why this matters. Make the reader feel the pain or gap.
Slides 4–7 — THE CONTENT: The actual tips, steps, or framework. Each slide = one idea.
Slide 8 — THE SUMMARY: "Here's the recap in 30 seconds" — reinforces the value.
Slide 9 — CTA SLIDE: One clear action. "Save this" + "Follow for more [NICHE] content."
Slide 10 (optional) — BONUS TIP: Something extra. Makes saving feel even more worth it.

RULES:
— Each slide should work as a standalone graphic
— The person reading should feel smarter after each slide
— The carousel should feel like a mini course, not a listicle

Topic: [YOUR TOPIC]
Main takeaway: [WHAT YOU WANT THEM TO WALK AWAY KNOWING]</div>
    <div class="pc-meta"><span class="pc-tag">🖼️ Carousel</span><span class="pc-tag">📌 Save-Worthy</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Carousels get shared more than any other format because people send them to friends who need the info. Write them to be shareable reference material.</div></div>
  </div>

  <div class="prompt-card t-green">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 10</div><div class="pc-title">Talking Head Script (No Teleprompter)</div><div class="pc-use">✅ Best for: Creators who want to speak naturally without memorizing lines</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Write a talking-head script for a video about [TOPIC] that I can deliver WITHOUT a teleprompter and WITHOUT memorizing. 

Instead of word-for-word lines, give me a structure I can internalize in 5 minutes and then speak naturally. This is the difference between reading a script and actually talking.

FORMAT:
For each section, give me:
— THE BULLET (the idea in 5 words or less — what I'm saying)
— THE EXAMPLE (a specific story, stat, or example to make it real)
— THE TRANSITION (one sentence to naturally move to the next point)

SECTIONS:
1. Hook (the one sentence that starts everything)
2. Why this matters (context — 30 seconds)
3. Main Point 1 + example
4. Main Point 2 + example
5. Main Point 3 + example (the most powerful one — save it for last)
6. The wrap + lesson in one sentence
7. CTA (the natural ask)

Also give me:
— 3 "if I forget what to say next" recovery lines
— The one sentence I should always come back to if I go off track
— Tips for sounding natural on camera for THIS specific topic

Topic: [YOUR TOPIC]
My comfort level on camera: [BEGINNER / COMFORTABLE / CONFIDENT]</div>
    <div class="pc-meta"><span class="pc-tag">🎥 Talking Head</span><span class="pc-tag">🗣️ Natural Delivery</span><div class="pro-tip"><strong>💡 Pro tip:</strong> The best on-camera creators aren't reading — they're remembering. Internalize the structure, not the words. Your natural voice is more engaging than a perfect read.</div></div>
  </div>
</div>

<!-- SECTION 5: VISUALS -->
<div class="t-sky" id="visuals">
  <div class="section-hdr">
    <div class="sh-top"><span class="sh-badge">CATEGORY 05</span></div>
    <h2>🖼️ Visual Creation Prompts</h2>
    <div class="sh-sub">Create on-brand AI images, graphics, and visuals without a designer</div>
    <div class="sh-desc">Use these with Midjourney, DALL-E 3, Adobe Firefly, Ideogram, Canva AI, or Leonardo. The more specific the prompt, the better the image.</div>
    <div class="section-count">📦 8 Prompts in this category</div>
  </div>
  <div class="sec-divider"></div>

  <div class="prompt-card t-sky">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 01</div><div class="pc-title">On-Brand Visual Generator</div><div class="pc-use">✅ Best for: Creating consistent branded imagery for your feed</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Create a [TYPE OF IMAGE — e.g., "digital illustration", "flat design graphic", "photo-realistic lifestyle shot"] that represents [CONCEPT OR THEME] for a content creator in the [NICHE] space.

Visual specifications:
— Color palette: [YOUR BRAND COLORS — use hex codes if possible, e.g., "deep purple #5B21B6, warm gold #F59E0B, and clean white #FFFFFF"]
— Style: [e.g., "modern minimalist", "vibrant and energetic", "warm and aspirational", "clean and professional"]
— Mood: [e.g., "empowering and motivational", "calm and focused", "excited and celebratory"]
— Composition: [e.g., "wide open space in center for text overlay", "rule of thirds", "overhead flat lay"]
— Lighting: [e.g., "golden hour warm tones", "clean studio white", "soft natural light"]
— Do NOT include any text — I will add text in Canva
— Aspect ratio: [1:1 for feed / 9:16 for Stories/Reels / 16:9 for YouTube]

Additional context: [ANY SPECIFIC ELEMENTS TO INCLUDE OR EXCLUDE]</div>
    <div class="pc-meta"><span class="pc-tag">🎨 Brand Visuals</span><span class="pc-tag">📸 Feed</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Save your brand hex codes somewhere accessible so you can paste them directly into prompts. Consistency across visuals is what makes a brand look premium.</div></div>
  </div>

  <div class="prompt-card t-sky">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 02</div><div class="pc-title">Digital Product Cover</div><div class="pc-use">✅ Best for: Ebooks, guides, checklists, workbooks, and digital downloads</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Create a professional, premium-looking digital product cover for a [PRODUCT TYPE — e.g., "ebook", "PDF guide", "digital workbook", "checklist pack"] that looks worth $[PRICE].

Visual requirements:
— Style: [e.g., "clean and minimalist", "bold and colorful", "elegant and sophisticated"]
— Primary color: [YOUR BRAND COLOR]
— Background: [solid color / gradient / subtle pattern / texture]
— Design elements: [e.g., "subtle geometric shapes in the background", "clean line accents", "abstract gradient overlay"]
— NO text overlays — I will add the title in Canva
— Format: portrait, 8.5:11 ratio (letter size)
— Quality: high-resolution, looks like a physical book or printed document
— Mood: [professional / friendly / luxurious / approachable]

The cover should look like a product someone would find on a real marketplace and immediately perceive as high value. Clean, intentional, not generic.

Optional: generate 3 variations with slightly different backgrounds/color treatments so I can choose.</div>
    <div class="pc-meta"><span class="pc-tag">📦 Products</span><span class="pc-tag">💰 Perceived Value</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Use Adobe Firefly or Canva AI for product covers — they give more control over text placement after generation. Generate the background, add your title in Canva.</div></div>
  </div>

  <div class="prompt-card t-sky">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 03</div><div class="pc-title">Ideogram Text-on-Image Prompt</div><div class="pc-use">✅ Best for: Ideogram AI — the best free tool for readable text in images</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Create a [TYPE — e.g., "motivational quote card", "social media graphic", "typographic poster", "announcement graphic"] with the following text displayed prominently:

MAIN TEXT: "[YOUR MAIN TEXT HERE]"
SUBTEXT (optional): "[YOUR SUBTEXT IF APPLICABLE]"

Design specifications:
— Font style: [e.g., "bold modern sans-serif", "elegant serif", "handwritten script", "mixed display fonts"]
— Background: [e.g., "deep purple to pink gradient", "clean white with subtle texture", "dark moody background", "bright colorful abstract"]
— Color palette: [YOUR COLORS]
— Text placement: [centered / top third / large and dominant / elegant and spaced]
— Additional elements: [e.g., "minimal geometric accents", "floral elements", "none — text only", "subtle sparkle or star elements"]
— Overall feel: [bold and punchy / soft and aesthetic / luxurious / energetic / calm]
— Aspect ratio: [1:1 / 4:5 / 9:16]

The text MUST be clearly readable, correctly spelled, and central to the design. High quality, print-ready resolution.</div>
    <div class="pc-meta"><span class="pc-tag">✏️ Text Overlay</span><span class="pc-tag">🖼️ Ideogram</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Ideogram is currently the most reliable AI tool for generating images where text needs to actually be readable. Use it specifically for quote cards, announcement graphics, and any image where words are part of the design.</div></div>
  </div>

  <div class="prompt-card t-sky">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 04</div><div class="pc-title">Midjourney Power Prompt Template</div><div class="pc-use">✅ Best for: Midjourney — highly detailed, structured prompts for premium output</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">[DETAILED SCENE DESCRIPTION — describe exactly what you want to see. Include: subject, action, setting, time of day, atmosphere. Example: "A young woman sitting at a minimal desk setup in a sunlit home office, working on a laptop, surrounded by plants and soft morning light, looking focused and peaceful"]

[ARTISTIC STYLE — e.g., "digital art illustration", "photorealistic photography", "flat vector illustration", "watercolor painting", "cinematic film still", "editorial lifestyle photography"]

Color palette: [e.g., "warm amber and cream tones", "deep purple and gold", "muted sage green and terracotta", "bright vibrant pastels"]

Mood: [e.g., "aspirational and peaceful", "energetic and bold", "luxurious and refined", "approachable and warm"]

Lighting: [e.g., "soft golden hour backlighting", "clean bright studio lighting", "moody dramatic side lighting", "diffused natural window light"]

Camera / composition: [e.g., "wide angle establishing shot", "medium portrait", "close-up detail shot", "overhead flat lay", "rule of thirds composition"]

Quality modifiers: highly detailed, 8K resolution, professional photography, sharp focus, award-winning

Aspect ratio: --ar [9:16 for vertical / 16:9 for horizontal / 1:1 for square]
Style: --style raw (for more realistic output)
Version: --v 6</div>
    <div class="pc-meta"><span class="pc-tag">🎨 Midjourney</span><span class="pc-tag">⚡ Premium</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Add '--style raw' for photorealistic results and '--v 6' for the latest model. The more specific every detail, the fewer iterations you'll need to get the shot you want.</div></div>
  </div>

  <div class="prompt-card t-sky">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 05</div><div class="pc-title">Thumbnail Generator</div><div class="pc-use">✅ Best for: YouTube thumbnails, TikTok cover frames, pinned video covers</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Create a high-contrast, scroll-stopping thumbnail image for a video about [VIDEO TOPIC].

Requirements:
— Platform: [YouTube 16:9 / TikTok 9:16 / Instagram 1:1]
— Style: Bold, high-contrast, immediately readable at small size (thumbnail size on a phone)
— Primary focal point: [e.g., "a person with an expressive reaction", "a before/after split", "a product or money visual", "bold text as the hero element"]
— Background: [COLOR OR SETTING — clean and not busy]
— Color scheme: High contrast — [PRIMARY COLOR] on [SECONDARY COLOR]
— What to include: [LIST ANY SPECIFIC ELEMENTS — phone, money, arrow, graph, product, etc.]
— What NOT to include: faces (if faceless) / text (add in Canva later)
— Mood: [surprising / exciting / urgent / aspirational / intriguing]

The image should:
— Read clearly at thumbnail size (100px wide)
— Create enough curiosity that someone clicks without knowing the full story
— Look like it was intentionally designed, not randomly generated

Generate 3 variations with slightly different compositions.</div>
    <div class="pc-meta"><span class="pc-tag">📸 Thumbnail</span><span class="pc-tag">👆 Click Rate</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Generate the base image with AI, then add your text overlay in Canva. The combination of AI-generated visuals + bold text = professional thumbnails at zero cost.</div></div>
  </div>

  <div class="prompt-card t-sky">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 06</div><div class="pc-title">Story Background Pack</div><div class="pc-use">✅ Best for: Building a branded Story template system you can reuse</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Generate a set of [NUMBER — e.g., 6] Instagram or TikTok Stories background images that work as templates I can reuse.

Requirements for ALL backgrounds:
— Aspect ratio: 9:16 vertical (Stories format)
— Consistent aesthetic that matches [DESCRIBE YOUR BRAND — e.g., "warm purple and gold with a modern feel"]
— Plenty of clean space for text overlays, polls, link stickers, and countdowns
— No text in the generated image — I'll add text in Canva
— Resolution high enough for crisp mobile display

Generate these specific variations:
1. Dark background version (for text-heavy stories)
2. Light/white background version (for bright, clean stories)
3. Gradient version (my brand colors fading from [COLOR 1] to [COLOR 2])
4. Abstract/pattern version (subtle texture that doesn't compete with text)
5. "Pop of color" version (one bold accent color against neutral)
6. Neutral tone version (cream, beige, or minimal for a softer aesthetic)

Brand colors: [YOUR COLORS]
Overall aesthetic: [DESCRIBE YOUR BRAND VIBE]</div>
    <div class="pc-meta"><span class="pc-tag">📲 Stories</span><span class="pc-tag">🎨 Templates</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Generate 10 backgrounds at once and upload them all to Canva as a collection. Then you never have to start from scratch — just grab a background and add your content.</div></div>
  </div>

  <div class="prompt-card t-sky">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 07</div><div class="pc-title">AI Image Prompt Improver</div><div class="pc-use">✅ Best for: Upgrading weak prompts that are producing mediocre images</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Here is an AI image prompt I used that produced a mediocre result: 
"[PASTE YOUR ORIGINAL PROMPT HERE]"

The problems with the output were: [DESCRIBE WHAT WAS WRONG — e.g., "too generic", "wrong style", "text was unreadable", "composition was off", "colors were wrong"]

What I was actually trying to create: [DESCRIBE YOUR IDEAL IMAGE IN DETAIL]

Rewrite this prompt 3 times — each version more specific and more likely to produce the image I want:

Version 1: More detailed description with style, mood, and lighting added
Version 2: Different approach using reference-style language ("in the style of...", "reminiscent of...")
Version 3: Simplified and punchy — sometimes less is more

For each version:
— Write the full improved prompt
— Explain what you added or changed
— Tell me which AI tool this version would work best with (Midjourney / DALL-E / Firefly / Ideogram / Canva AI)
— Give one more optional modifier I could add to push the quality further</div>
    <div class="pc-meta"><span class="pc-tag">🔧 Improve</span><span class="pc-tag">🎨 All AI Tools</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Every great AI image prompt is an iteration. Your first prompt is never your best prompt. Use this to level up your prompting skills systematically.</div></div>
  </div>

  <div class="prompt-card t-sky">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 08</div><div class="pc-title">Canva AI Smart Prompt</div><div class="pc-use">✅ Best for: Canva's built-in AI image generator — fast, free, and integrated</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Write an optimized prompt for Canva's AI image generator (Magic Media) to create [WHAT YOU NEED].

Canva AI works best with:
— Clear subject description
— Style keywords it recognizes
— Simple, direct language (not overly technical)
— Explicit mood and color direction

Write 3 Canva-optimized prompts for:

PROMPT A — For a feed post graphic about [TOPIC]:
Subject + Style + Color + Mood — under 50 words

PROMPT B — For a Stories background for [USE CASE]:
Setting + Aesthetic + Color palette + Empty space direction — under 40 words

PROMPT C — For a product cover or lead magnet image:
Product feel + Professional aesthetic + Brand colors + Format — under 40 words

For each prompt, also note:
— Which Canva style preset to select (Photo / Illustration / Abstract / Painting etc.)
— Whether to use "Generate" or "Edit image" mode
— One tweak to try if the first result isn't right

My brand aesthetic: [DESCRIBE YOUR LOOK AND FEEL]
My primary brand colors: [YOUR COLORS]</div>
    <div class="pc-meta"><span class="pc-tag">🎨 Canva AI</span><span class="pc-tag">🆓 Free Tool</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Canva AI is built right into your design workflow — no switching apps. Generate backgrounds, product visuals, and graphic elements without ever leaving Canva.</div></div>
  </div>
</div>

<!-- SECTION 6: RESEARCH -->
<div class="t-rose" id="research">
  <div class="section-hdr">
    <div class="sh-top"><span class="sh-badge">CATEGORY 06</span></div>
    <h2>🔍 Research Prompts</h2>
    <div class="sh-sub">Understand your niche, audience, and competition faster than ever before</div>
    <div class="sh-desc">Skip hours of manual research. These prompts extract deep audience insights, competitor analysis, trend intelligence, and keyword research in minutes.</div>
    <div class="section-count">📦 8 Prompts in this category</div>
  </div>
  <div class="sec-divider"></div>

  <div class="prompt-card t-rose">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 01</div><div class="pc-title">Deep Audience Research Report</div><div class="pc-use">✅ Best for: Before creating any new content series or product</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Build me a comprehensive audience research report for my ideal follower and customer.

My niche: [YOUR NICHE]
My target audience: [DESCRIBE IN DETAIL — age range, situation, goals, platform they're on]

Research and report on ALL of the following:

1. TOP 10 PAIN POINTS: The biggest frustrations, fears, and failures this audience experiences related to [YOUR NICHE]. Write each in THEIR words — not marketing language.

2. TOP 10 DESIRES & GOALS: What they're working toward. What success looks like to them. What they dream about.

3. THEIR LANGUAGE: The exact phrases, words, and expressions they use when talking about [YOUR NICHE]. Include: what they Google, what they say in comments, what they type in Reddit / forums.

4. WHAT THEY'VE ALREADY TRIED: Things they've attempted that didn't work. Why those things failed for them.

5. WHAT MAKES THEM TRUST A CREATOR: What signals authority, authenticity, and credibility to this specific audience?

6. THEIR BIGGEST MISCONCEPTIONS: What commonly-believed things in your niche are actually wrong or misleading?

7. THEIR BUYING TRIGGERS: What makes them decide to buy a digital product or program? What makes them hesitate?

Format this as a reference document I can return to regularly.</div>
    <div class="pc-meta"><span class="pc-tag">👥 Audience</span><span class="pc-tag">🔬 Deep Research</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Use Perplexity AI for this prompt — it pulls from real forums, Reddit threads, and current discussions to give you authentic audience language, not assumptions.</div></div>
  </div>

  <div class="prompt-card t-rose">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 02</div><div class="pc-title">Competitor Content Strategy Analysis</div><div class="pc-use">✅ Best for: Building a content strategy based on what already works in your niche</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Analyze the content strategy of top creators in the [NICHE] space on [PLATFORM].

Based on your knowledge of what performs well in this space, give me a detailed breakdown:

1. TOP-PERFORMING CONTENT FORMATS: What types of videos / posts consistently get the most engagement in this niche? (Rank by: educational, story, trending, promotional)

2. MOST SUCCESSFUL TOPICS: What subject areas drive the most views, saves, and follows for creators in [NICHE]?

3. HOOK PATTERNS: What hook formulas appear most often in high-performing [NICHE] content? List the top 5 patterns.

4. POSTING FREQUENCY & TIMING: What posting frequency and times seem to correlate with growth in this niche?

5. CONTENT GAPS: Where does existing content in this niche fall short? What are creators consistently NOT covering that their audiences still want?

6. AUDIENCE COMPLAINTS: Based on common comment patterns in this niche, what do viewers wish creators would do differently?

7. MONETIZATION PATTERNS: How are the most successful creators in this niche monetizing? What offers seem to convert best?

8. MY DIFFERENTIATION OPPORTUNITY: Based on all of the above, where is the biggest gap I could own?</div>
    <div class="pc-meta"><span class="pc-tag">📊 Competitor</span><span class="pc-tag">🎯 Strategy</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Combine AI analysis with 30 minutes of manual research — watch the top 5 videos in your niche this week and add real observations to what the AI gives you.</div></div>
  </div>

  <div class="prompt-card t-rose">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 03</div><div class="pc-title">Keyword &amp; Hashtag Research</div><div class="pc-use">✅ Best for: Optimizing your content for search and discovery</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">I create content about [TOPIC] for [PLATFORM] targeting [AUDIENCE]. Do comprehensive keyword and hashtag research for me.

SEARCH KEYWORDS (for TikTok, YouTube, and Google search):
1. Top 20 search phrases my audience types to find content like mine
2. 10 long-tail keywords (3–5 word phrases) with likely high intent but lower competition
3. 5 "question keywords" (how to, what is, why does, etc.) that could drive discovery
4. Keywords to avoid — terms that are too broad or dominated by larger brands

HASHTAG STRATEGY by platform:

For [PLATFORM 1]:
— 5 large hashtags (1M+ posts) — for broad reach
— 8 medium hashtags (100K–500K posts) — for targeted reach
— 5 niche/micro hashtags (under 100K posts) — for high engagement rate
— 2 branded or community hashtags — for belonging to a specific movement

For [PLATFORM 2 — if applicable]:
— Same breakdown

TRENDING OPPORTUNITIES:
— Any hashtags in my niche currently experiencing unusual growth
— Seasonal hashtags relevant to [CURRENT MONTH / UPCOMING EVENTS]

CAPTION KEYWORDS:
— 10 natural keyword phrases to weave into captions for SEO without sounding robotic</div>
    <div class="pc-meta"><span class="pc-tag">🔍 Keywords</span><span class="pc-tag">#️⃣ Hashtags</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Smaller niche hashtags (under 100K posts) consistently deliver better engagement rates than mega-hashtags where your content gets buried in 3 seconds.</div></div>
  </div>

  <div class="prompt-card t-rose">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 04</div><div class="pc-title">Digital Product Market Research</div><div class="pc-use">✅ Best for: Validating a digital product idea before you spend time building it</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">I'm considering creating a digital product for [TARGET AUDIENCE] in the [NICHE] space. Help me validate the idea BEFORE I build it.

Product idea: [DESCRIBE YOUR PRODUCT CONCEPT]

Research the following:
1. DEMAND VALIDATION: Is there clear evidence this audience is actively searching for or buying products like this? What signals suggest demand?

2. EXISTING COMPETITION: What similar products already exist? What are their strengths and weaknesses? What are customers saying in reviews?

3. PRICING BENCHMARKS: What do comparable products in this space sell for? What price points seem to convert best? Is there a premium gap I could fill?

4. CONTENT-TO-PRODUCT FIT: What types of content about [TOPIC] perform best, and does that suggest my product idea will convert?

5. LAUNCH RISK ASSESSMENT: What are the biggest reasons this product might not sell? What would I need to do to de-risk it?

6. MINIMUM VIABLE VERSION: What's the smallest, fastest version of this product I could build to test demand before investing more time?

7. GO / NO-GO RECOMMENDATION: Based on all of the above, should I build this product, modify it, or pivot to a different idea entirely?</div>
    <div class="pc-meta"><span class="pc-tag">✅ Validation</span><span class="pc-tag">💡 Market Research</span><div class="pro-tip"><strong>💡 Pro tip:</strong> The fastest validation is to post content about the topic FIRST. If it gets saves and DMs asking where to learn more — that's your green light to build the product.</div></div>
  </div>

  <div class="prompt-card t-rose">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 05</div><div class="pc-title">Trend Intelligence Report</div><div class="pc-use">✅ Best for: Staying ahead of trends before they peak</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Give me a trend intelligence report for the [NICHE] creator space on [PLATFORM] right now.

I want to know:
1. RISING TRENDS: What topics, formats, or conversations are growing quickly in [NICHE] right now — before they hit mainstream awareness?

2. PEAK TRENDS: What is currently at peak popularity in [NICHE]? How long is the window to ride this before it becomes oversaturated?

3. DECLINING TRENDS: What content formats or topics were popular 3–6 months ago but are now losing steam? What should I pivot away from?

4. EMERGING FORMAT TRENDS: What new video formats, editing styles, or content structures are creators starting to use?

5. PLATFORM ALGORITHM SHIFTS: What changes in [PLATFORM]'s algorithm or features are creators noticing and adapting to?

6. AUDIENCE BEHAVIOR SHIFTS: How is the audience in [NICHE] changing? What do they want more of? Less of?

7. EARLY MOVER OPPORTUNITIES: What trend is 3–6 months from going mainstream that I could start creating around NOW before everyone else?

Rate each trend on: Current momentum (1–10) + Shelf life estimate + Relevance to [MY NICHE]</div>
    <div class="pc-meta"><span class="pc-tag">📈 Trends</span><span class="pc-tag">⚡ Early Mover</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Use Perplexity AI for trend research — it pulls live data. The creators who win are the ones who catch trends at 20% penetration, not 80%.</div></div>
  </div>

  <div class="prompt-card t-rose">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 06</div><div class="pc-title">Niche Authority Blueprint</div><div class="pc-use">✅ Best for: Building a reputation as the go-to expert in your specific space</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">I want to become a recognized authority in the [SPECIFIC NICHE] space on [PLATFORM]. Research and build me a blueprint for establishing expertise.

KNOWLEDGE PILLARS: What are the 5–7 core topics that define genuine expertise in [NICHE]? What does someone need to know deeply to be considered an authority?

CREDIBILITY SIGNALS: What does an audience in [NICHE] look for when deciding whether to trust a creator? What proof points matter most to them?

OPINION OPPORTUNITIES: What are the 5 most debated, misunderstood, or controversial topics in [NICHE] where having a clear, informed point of view would differentiate me?

BEGINNER GAP: What are the top 10 questions beginners in [NICHE] ask that a real expert would answer definitively and clearly?

COUNTER-NARRATIVE OPPORTUNITIES: What conventional wisdom in [NICHE] is actually wrong, outdated, or more nuanced than most creators admit?

90-DAY AUTHORITY CONTENT PLAN: Give me a content progression — Week 1–4 (foundation), Week 5–8 (depth), Week 9–12 (authority positioning) — that would make someone who discovers me in Month 1 and watches consistently say "she really knows her stuff" by Month 3.</div>
    <div class="pc-meta"><span class="pc-tag">🏆 Authority</span><span class="pc-tag">📖 Expert Positioning</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Authority is built through consistency and point of view. Having an opinion — and being right about it — is the fastest way to become the creator people reference and recommend.</div></div>
  </div>

  <div class="prompt-card t-rose">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 07</div><div class="pc-title">Platform Algorithm Research</div><div class="pc-use">✅ Best for: Understanding how to work WITH the algorithm, not against it</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Research and explain how the [PLATFORM — TikTok / Instagram / YouTube] algorithm currently works for content creators in [NICHE].

I want to understand:
1. RANKING SIGNALS: What signals does the algorithm use to decide whether to push content? Rank them by importance.

2. WATCH TIME MECHANICS: At what point does a video get shown to more people? What retention benchmarks matter?

3. ENGAGEMENT WEIGHTING: How does the algorithm weight different engagement types? (Saves vs. shares vs. comments vs. likes — which drives distribution most?)

4. EARLY MOMENTUM: What happens in the first 30–60 minutes after posting? What metrics determine if a video gets pushed?

5. POSTING FREQUENCY: What frequency is optimal for [PLATFORM] in [NICHE] without diluting reach?

6. SHADOW SIGNALS: What behaviors trigger reduced distribution that creators might not know about?

7. RECOVERY STRATEGY: If my account stops getting reach, what are the most effective ways to reset or recover?

8. WHAT CHANGED RECENTLY: What algorithm updates have impacted [PLATFORM] creators in the last 3–6 months?

Give me 5 specific, actionable adjustments I should make to my current strategy based on this.</div>
    <div class="pc-meta"><span class="pc-tag">⚙️ Algorithm</span><span class="pc-tag">📊 Platform</span><div class="pro-tip"><strong>💡 Pro tip:</strong> The algorithm rewards content that keeps people on the platform. Create content that's so good people watch twice, comment, and send to a friend — and the algorithm will do the rest.</div></div>
  </div>

  <div class="prompt-card t-rose">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 08</div><div class="pc-title">Income Stream Research</div><div class="pc-use">✅ Best for: Discovering all the ways creators in your niche are making money</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Research and map every realistic income stream available to a [NICHE] creator on [PLATFORM] with [YOUR APPROXIMATE FOLLOWING SIZE] followers.

For EACH income stream, give me:
— What it is and how it works
— Realistic income range at my current size (be honest, not hype)
— How quickly I could activate it (this week / this month / 3–6 months)
— What I need in place before it's viable
— The effort vs. reward ratio (high effort/high reward, low effort/medium reward, etc.)
— One creator in [NICHE] space who does this well (general example)

Income streams to research:
1. Digital products (guides, templates, courses, workbooks)
2. TikTok Shop / affiliate marketing
3. UGC brand deals (paid content creation for brands)
4. Creator Fund / platform monetization
5. Email list monetization
6. Membership or community
7. Live stream gifting / tipping
8. Reselling or MRR (master resell rights)
9. Coaching or consulting (if applicable)
10. KDP / print-on-demand passive income

End with your recommendation: Which 2–3 income streams should I prioritize RIGHT NOW given my size and niche?</div>
    <div class="pc-meta"><span class="pc-tag">💰 Income</span><span class="pc-tag">📊 Monetization</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Don't try to activate 5 income streams at once. Pick 1–2, master them, then add more. Scattered effort = scattered income.</div></div>
  </div>
</div>

<!-- SECTION 7: OFFER CREATION -->
<div class="t-teal" id="offers">
  <div class="section-hdr">
    <div class="sh-top"><span class="sh-badge">CATEGORY 07</span></div>
    <h2>💰 Offer Creation Prompts</h2>
    <div class="sh-sub">Build irresistible digital products, nail your pricing, and write copy that converts</div>
    <div class="sh-desc">From your very first product idea all the way through to launch-day sales copy — these prompts walk you through every stage of creating and selling a digital offer that actually makes money.</div>
    <div class="section-count">📦 12 Prompts in this category</div>
  </div>
  <div class="sec-divider"></div>

  <div class="prompt-card t-teal">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 01</div><div class="pc-title">Digital Product Idea Generator</div><div class="pc-use">✅ Best for: When you're ready to monetize but don't know what to create first</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">I am a [NICHE] creator with an audience of [DESCRIBE YOUR AUDIENCE — size, platform, what they engage with most]. I want to create and sell my first (or next) digital product.

Generate 20 digital product ideas I could create and sell. For EACH idea, give me:

— PRODUCT TYPE: (guide, checklist, template pack, workbook, mini-course, swipe file, spreadsheet, script pack, challenge, etc.)
— SPECIFIC TOPIC: Not generic — what exact transformation does it deliver?
— PRICE POINT: Suggested retail price and why
— TIME TO CREATE: Realistic estimate (1 day / 1 week / 1 month)
— DIFFICULTY TO CREATE: Low / Medium / High
— SALES POTENTIAL: Conservative monthly revenue estimate at my audience size
— CONTENT I ALREADY HAVE: Could I pull this from content I've already created?
— THE PAIN IT SOLVES: The specific, urgent problem this removes for the buyer

Organize the 20 ideas into tiers:
— TIER 1 (Low-ticket $7–$27): Quick wins, fast to create, high volume
— TIER 2 (Mid-ticket $37–$97): More depth, moderate creation time
— TIER 3 (Premium $97+): Comprehensive, high transformation, slower to sell

End with your TOP 3 recommendations for what I should build FIRST and why.</div>
    <div class="pc-meta"><span class="pc-tag">💡 Product Ideas</span><span class="pc-tag">💰 Monetization</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Start with the fastest-to-create product that solves the most urgent pain. Done and selling beats perfect and invisible. You can always upgrade it later.</div></div>
  </div>

  <div class="prompt-card t-teal">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 02</div><div class="pc-title">Product Naming &amp; Positioning Workshop</div><div class="pc-use">✅ Best for: Naming your digital product so it sells itself before anyone reads the description</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">I am creating a [PRODUCT TYPE] about [TOPIC] for [TARGET AUDIENCE].

The product delivers this transformation: [DESCRIBE THE BEFORE AND AFTER — where they start vs. where they end up after using your product]

Generate 15 name options for this product. Each name should:
— Communicate the transformation or result (not just the content)
— Sound premium and specific (not generic)
— Be memorable, easy to say, and easy to remember
— Create curiosity or desire when heard for the first time
— Work as a standalone brand (not just a description)

For EACH name:
— Write the full product name
— Write a one-sentence tagline that pairs with it
— Rate it on: Clarity (1–10), Desirability (1–10), Memorability (1–10)
— Note any potential issues (too long, too generic, similar to existing products)

Then give me:
— Your TOP 3 picks with a full explanation of why each works
— The name you would personally choose if this were your product and why
— 3 names that sounded good but have a fatal flaw (and what the flaw is)
— How to test the name with my audience before committing</div>
    <div class="pc-meta"><span class="pc-tag">🏷️ Naming</span><span class="pc-tag">🎯 Positioning</span><div class="pro-tip"><strong>💡 Pro tip:</strong> The best product names speak to the transformation, not the content. "The Hook Library" beats "200 TikTok Hook Templates." Outcome beats description every time.</div></div>
  </div>

  <div class="prompt-card t-teal">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 03</div><div class="pc-title">Full Sales Page Copy Generator</div><div class="pc-use">✅ Best for: Building a sales page that converts cold traffic into buyers</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Write complete sales page copy for [PRODUCT NAME], a [PRODUCT TYPE] for [TARGET AUDIENCE].

Product details:
— What it is: [DESCRIPTION]
— What's inside: [LIST THE KEY COMPONENTS]
— The transformation: [BEFORE STATE → AFTER STATE]
— Price: $[PRICE]
— Platform: [Stan Store / Beacons / Gumroad / own website]

Write EVERY section of the sales page:

1. HEADLINE (3 variations — pick the strongest):
Result-focused, under 12 words, no fluff

2. SUB-HEADLINE:
Expands the headline, adds specificity, 1–2 sentences

3. PROBLEM SECTION (150 words):
Agitate the pain. Make them feel seen and understood. Don't introduce the solution yet.

4. SOLUTION BRIDGE (50 words):
The transition from "I feel this" to "there is a way out"

5. PRODUCT INTRODUCTION (100 words):
Introduce the product as the natural answer. Name it. What it is in one sentence.

6. WHAT'S INSIDE (bullet list):
7–10 specific deliverables with benefit-focused descriptions (not just feature names)

7. SOCIAL PROOF SECTION:
3 testimonial templates to fill in as you collect them

8. WHO THIS IS FOR / NOT FOR:
3 bullet points each — qualifies buyers and removes wrong-fit buyers

9. FAQ SECTION:
8 pre-written questions with answers that handle the most common objections

10. FINAL CTA SECTION:
Strong, direct, with price, urgency, and one clear action</div>
    <div class="pc-meta"><span class="pc-tag">📄 Sales Page</span><span class="pc-tag">✍️ Copywriting</span><div class="pro-tip"><strong>💡 Pro tip:</strong> The problem section is the most important part of any sales page. If people don't feel their pain reflected back at them, they won't buy — no matter how good the product is.</div></div>
  </div>

  <div class="prompt-card t-teal">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 04</div><div class="pc-title">Pricing Psychology Advisor</div><div class="pc-use">✅ Best for: Setting the right price — not too low to feel cheap, not too high to stop conversions</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Help me build a complete pricing strategy for [PRODUCT NAME].

Product description: [WHAT IT IS AND WHAT IT DELIVERS]
Target audience: [WHO THEY ARE AND THEIR GENERAL INCOME/SPENDING PROFILE]
My current audience size: [FOLLOWERS / EMAIL LIST SIZE]
Similar products I've seen priced at: [EXAMPLES IF YOU KNOW ANY]

Answer ALL of the following:

1. PRICE ANCHORING STRATEGY: What should my highest-priced tier be (even if it's not my main offer) so the core offer feels like value?

2. PSYCHOLOGICAL PRICE POINTS: Which specific price numbers convert best for a product like this? ($27 vs $29 vs $30 — the psychology behind each)

3. BUNDLE OPPORTUNITY: What could I add to justify a higher price point without significantly increasing my creation time?

4. LAUNCH PRICING vs. EVERGREEN PRICING: Should I launch at a lower price and raise it? Or start at full price?

5. PAYMENT PLAN THRESHOLD: At what price point should I offer a payment plan option? What split works best?

6. FREEMIUM STRATEGY: Should any part of this product be free as a lead magnet? What portion? Why?

7. COMPETITOR PRICE POSITIONING: Am I trying to be the premium option, the accessible option, or the best-value option? What does each require?

8. INCOME PROJECTION: At my current audience size, what monthly revenue could I realistically project at each price point tested?

Give me a recommended final price and the full rationale behind it.</div>
    <div class="pc-meta"><span class="pc-tag">💲 Pricing</span><span class="pc-tag">🧠 Psychology</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Pricing too low is a bigger mistake than pricing too high. Low prices attract bargain hunters who refund. Fair prices attract committed buyers who get results and leave testimonials.</div></div>
  </div>

  <div class="prompt-card t-teal">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 05</div><div class="pc-title">Product Outline &amp; Content Builder</div><div class="pc-use">✅ Best for: Structuring your digital product so it delivers real transformation</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Help me build the complete structure and content outline for [PRODUCT NAME], a [PRODUCT TYPE] for [AUDIENCE] about [TOPIC].

The buyer starts here: [DESCRIBE THEIR SITUATION BEFORE BUYING — what they know, what they struggle with, what they've tried]
The buyer ends here: [DESCRIBE THEIR SITUATION AFTER COMPLETING THE PRODUCT — what they can do, what changed]

Build me:

PRODUCT STRUCTURE:
— How many sections / modules / chapters?
— What's the logical progression from beginning to end?
— What order creates the fastest "first win" for the buyer?

SECTION-BY-SECTION OUTLINE:
For each section, give me:
— Section title (outcome-focused, not generic)
— What the reader will learn or be able to do after this section
— 3–5 key points or steps to cover
— Any exercises, worksheets, or action steps to include
— Estimated page count or word count for a guide format

QUICK WIN PLACEMENT:
Where in the product should I put the "quick win" — the one thing that makes them immediately feel they made the right purchase?

BONUS OPPORTUNITIES:
What 1–2 bonuses could I add that would increase perceived value without significantly increasing production time?

FORMAT RECOMMENDATION:
Based on the content, should this be a PDF guide / fillable workbook / template pack / video course / combination? Give me the pros and cons.</div>
    <div class="pc-meta"><span class="pc-tag">📋 Structure</span><span class="pc-tag">🗂️ Outline</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Put a quick win in the first 10% of your product. When buyers feel immediate value, they complete the product, leave testimonials, and buy again. Quick wins build buyers for life.</div></div>
  </div>

  <div class="prompt-card t-teal">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 06</div><div class="pc-title">Objection Crusher &amp; FAQ Builder</div><div class="pc-use">✅ Best for: Handling every reason someone might NOT buy before they think of it</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">I am selling [PRODUCT NAME] at $[PRICE] to [TARGET AUDIENCE].

List the 15 most common reasons someone in this audience would hesitate to buy — and then write a compelling, honest answer to each one.

OBJECTIONS TO ADDRESS:
1. "Is this for beginners or do I need experience?"
2. "I don't have time for this right now."
3. "I've bought things like this before and they didn't work."
4. "I can find this information for free online."
5. "What if it doesn't work for me?"
6. "Is this worth the price?"
7. "I'm not sure I'm ready."
8. "How long will it take to see results?"
9. "What makes this different from every other [PRODUCT TYPE] out there?"
10. "I don't have the money right now."
11. "What if I buy it and never use it?"
12. "Is this specific to my niche or is it generic?"
13. "Do I need any special tools or software?"
14. "Will I actually get support if I'm stuck?"
15. [ADD YOUR MOST COMMON SPECIFIC OBJECTION]

For each objection:
— Write the objection as the buyer would phrase it in their head
— Write a genuine, specific, non-defensive response (2–4 sentences)
— Rate how common this objection is for [YOUR AUDIENCE]: Very Common / Common / Occasional
— Note whether this should appear in your FAQ, sales video, or both

Format as a complete FAQ section ready to paste into a sales page.</div>
    <div class="pc-meta"><span class="pc-tag">🛡️ Objections</span><span class="pc-tag">❓ FAQ</span><div class="pro-tip"><strong>💡 Pro tip:</strong> The FAQ section is where hesitant buyers become buyers. Most people scroll straight to it before reading anything else. Treat it like a sales section, not an afterthought.</div></div>
  </div>

  <div class="prompt-card t-teal">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 07</div><div class="pc-title">Bundle &amp; Upsell Architecture</div><div class="pc-use">✅ Best for: Increasing average order value from products you've already built</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">I have the following digital products:
[LIST EACH PRODUCT, ITS DESCRIPTION, AND ITS PRICE]

Help me build a complete bundle and upsell architecture that maximizes revenue from every buyer.

BUNDLE STRATEGY:
— What are the 2–3 most logical bundle combinations?
— For each bundle: name, products included, bundle price, and the "savings" angle
— How to describe each bundle so the value feels greater than the sum of its parts

UPSELL SEQUENCE:
— What's my core offer (the one I lead with)?
— What's the natural upsell AFTER someone buys the core offer?
— What's the downsell if someone says no to the upsell?
— Is there an order bump I could add at checkout for an easy "yes"?

ORDER BUMP OPTIONS:
— What add-ons could I offer at checkout for $7–$27 that require zero new creation?

CROSS-SELL STRATEGY:
— After purchase, what existing product could I introduce to the buyer within 24–48 hours?

VALUE LADDER:
— Map out my complete value ladder from free → low ticket → mid ticket → premium
— What gaps exist in my ladder that I should fill?

REVENUE PROJECTION:
— If 10% of buyers take the upsell and 5% take the order bump, what does my revenue look like per 100 sales?</div>
    <div class="pc-meta"><span class="pc-tag">📦 Bundles</span><span class="pc-tag">⬆️ Upsells</span><div class="pro-tip"><strong>💡 Pro tip:</strong> An upsell immediately after purchase converts at 20–30% because buyers are in "yes mode." The easiest person to sell to is someone who just bought from you.</div></div>
  </div>

  <div class="prompt-card t-teal">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 08</div><div class="pc-title">Social Proof &amp; Testimonial System</div><div class="pc-use">✅ Best for: Collecting and using testimonials that actually move buyers to act</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">I sell [PRODUCT NAME] to [AUDIENCE] and I want to build a systematic social proof strategy from scratch.

Help me with all of the following:

1. TESTIMONIAL REQUEST MESSAGES (write 3 versions):
— A post-purchase email or DM asking for feedback
— A follow-up message for buyers who haven't responded
— A message for buyers who got great results asking for a specific success story

2. TESTIMONIAL QUESTIONS GUIDE:
— What 5 specific questions should I ask to get a testimonial that actually converts new buyers?
— (Bad testimonials: "Great product!" Good testimonials: specific problem → specific result → who it's for)

3. TESTIMONIAL FORMATS TO COLLECT:
— Written (what to ask for and how long)
— Video (what questions to give them, how to make it easy)
— Screenshot (what conversations or results to capture)
— Metric-based (specific numbers: followers gained, income made, time saved)

4. WHERE TO USE EACH TYPE:
— Which testimonials go on the sales page?
— Which work best as TikTok / Reels content?
— Which work as Story slides?
— Which go in emails?

5. BEFORE YOU HAVE TESTIMONIALS:
— What can I use instead during my first launch to build credibility?
— How do I get my first 5 testimonials before launch?</div>
    <div class="pc-meta"><span class="pc-tag">⭐ Testimonials</span><span class="pc-tag">🔒 Trust</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Give your first 5 customers the product for free or at a heavy discount in exchange for a detailed testimonial. Those 5 testimonials will make you thousands.</div></div>
  </div>

  <div class="prompt-card t-teal">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 09</div><div class="pc-title">MRR / Resell Product Setup Guide</div><div class="pc-use">✅ Best for: Setting up a Master Resell Rights or PLR product for reselling</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">I want to sell [MRR PRODUCT NAME] — a [PRODUCT DESCRIPTION] — with Master Resell Rights, meaning buyers can also resell it and keep 100% of the profit.

Help me set up everything I need to sell this successfully:

1. RESELL VALUE PROPOSITION:
— Write 3 different ways to explain the MRR/resell opportunity to a potential buyer
— What makes the resell rights more valuable than the product alone?
— How to explain MRR without making it sound like an MLM or pyramid scheme

2. SALES CONTENT PACK (write all of these):
— 5 TikTok / Reels script hooks specifically for selling this as an MRR product
— 3 caption variations for promoting it on different days
— A "what you get" breakdown carousel slide structure
— Income disclaimer language that's honest and compliant

3. TARGET AUDIENCE IDENTIFICATION:
— Who is the ideal buyer for this MRR product? (Describe 3 different buyer profiles)
— What pain points does the resell opportunity solve for them?
— What objections will they have specific to the MRR model?

4. POSITIONING STRATEGY:
— How do I stand out from the 100 other people selling the same product?
— What can I add (bonus, community, support, custom landing page) to make MY version the one people choose?

5. INCOME PROJECTION FOR BUYERS:
— Write a realistic income example I can use in my marketing without overpromising</div>
    <div class="pc-meta"><span class="pc-tag">🔁 MRR</span><span class="pc-tag">♾️ Resell Rights</span><div class="pro-tip"><strong>💡 Pro tip:</strong> When selling MRR, YOUR personality is your differentiation. Everyone has the same product — only you have your face, your story, and your audience relationship. Lead with YOU first, product second.</div></div>
  </div>

  <div class="prompt-card t-teal">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 10</div><div class="pc-title">5-Day Launch Plan Builder</div><div class="pc-use">✅ Best for: Mapping out every piece of content and copy needed for a successful launch</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Build me a complete 5-day launch plan for [PRODUCT NAME] launching on [DATE].

Product: [DESCRIPTION]
Price: $[PRICE]
Audience size: [FOLLOWERS / EMAIL LIST]
Platforms I'm active on: [LIST PLATFORMS]

For EACH of the 5 days, give me EVERYTHING I need to post and send:

DAY 1 (5 days before launch) — THE TEASE:
— TikTok/Reels video idea + hook
— Instagram caption
— Story sequence (3 slides)
— Email subject line + email outline
— What NOT to reveal yet

DAY 2 (4 days before) — THE PROBLEM:
— Content that speaks to the pain point (no product mention)
— Caption focused on the struggle
— DM or Story engagement to gauge interest

DAY 3 (3 days before) — BUILD ANTICIPATION:
— Reveal a sneak peek of something inside the product
— Waitlist or early access CTA
— Behind-the-scenes "I'm building something" content

DAY 4 (1 day before) — THE COUNTDOWN:
— Full reveal of the product, price, and where to buy
— Email announcement
— Story countdown sticker setup

DAY 5 (LAUNCH DAY) — THE SELL:
— Full sales video script (60 seconds)
— Sales caption with every detail
— Email: full sales email
— Stories: 5-slide sales sequence
— What to post every 4 hours to keep momentum

DAY 6 BONUS (Last chance):
— FOMO content, objection-busting video, final email</div>
    <div class="pc-meta"><span class="pc-tag">🚀 Launch</span><span class="pc-tag">📅 5 Days</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Most sales happen on launch day and the last day. Your middle days build the momentum that makes those peaks possible. Don't skip the warm-up — it's where the money is made.</div></div>
  </div>

  <div class="prompt-card t-teal">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 11</div><div class="pc-title">Affiliate &amp; Collab Pitch Pack</div><div class="pc-use">✅ Best for: Getting other creators to promote your products or partnering on launches</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">I want to recruit affiliate partners and collaborators to help promote [PRODUCT NAME] at $[PRICE] with [COMMISSION PERCENTAGE]% commission.

Write me a complete affiliate outreach pack:

1. COLD OUTREACH EMAIL (to creators I don't know):
— Subject line (3 options)
— Body: introduce myself, the product, the commission, why it fits their audience
— CTA: low-pressure ask to learn more
— Under 200 words — respect their time

2. WARM OUTREACH DM (to creators I've interacted with before):
— Casual, conversational version of the pitch
— Feels like a friend asking a favor, not a pitch
— Under 100 words

3. AFFILIATE INFORMATION PAGE (write the content):
— What they're promoting and why their audience will love it
— Commission structure and payment timing
— What promotional materials I'll give them (graphics, captions, links)
— How to get started in 3 steps

4. FOLLOW-UP MESSAGE (for non-responses):
— Polite, not pushy
— Add something new (updated results, new testimonial, deadline)

5. COLLAB PITCH (joint live or bundle deal):
— Pitch for co-hosting a live or creating a bundle together
— What each person brings and gets

6. THANK YOU + RESULTS MESSAGE (after launch):
— Message to send affiliates with their results to keep the relationship warm for future launches</div>
    <div class="pc-meta"><span class="pc-tag">🤝 Affiliates</span><span class="pc-tag">🔗 Collabs</span><div class="pro-tip"><strong>💡 Pro tip:</strong> One affiliate with a loyal 5,000-person audience can outsell your entire launch. Build affiliate relationships before you launch, not during.</div></div>
  </div>

  <div class="prompt-card t-teal">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 12</div><div class="pc-title">Post-Launch Analysis &amp; Optimization</div><div class="pc-use">✅ Best for: Learning from every launch so the next one is bigger</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">My launch for [PRODUCT NAME] just ended. Here are my results:

— Total revenue: $[AMOUNT]
— Units sold: [NUMBER]
— Conversion rate (visitors to buyers): [% IF KNOWN]
— Platform that drove the most sales: [PLATFORM]
— Content that performed best: [DESCRIBE YOUR BEST-PERFORMING POST]
— Content that flopped: [DESCRIBE WHAT DIDN'T WORK]
— Most common objection heard: [WHAT DID PEOPLE SAY WHEN THEY DIDN'T BUY?]
— Refund rate: [%]
— Email open rate: [% IF APPLICABLE]

Analyze my launch and tell me:

1. WHAT WORKED: What drove the most conversions and why?
2. WHAT DIDN'T WORK: Where did I lose potential buyers?
3. CONVERSION BOTTLENECK: Where in the journey did most people drop off?
4. PRICING ASSESSMENT: Did the price point help or hurt conversions?
5. CONTENT GAP: What content should I have created during the launch that I missed?
6. OBJECTION I DIDN'T HANDLE: Based on what people said, what objection was I not addressing clearly enough?
7. NEXT LAUNCH IMPROVEMENTS: Give me 10 specific, actionable changes to make for my next launch
8. EVERGREEN OPPORTUNITY: Should I keep selling this product or run it as a timed launch again? When?</div>
    <div class="pc-meta"><span class="pc-tag">📊 Analysis</span><span class="pc-tag">📈 Optimize</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Every launch teaches you something. The creators who grow fastest are the ones who debrief ruthlessly and apply every lesson to the next one.</div></div>
  </div>
</div>

<!-- SECTION 8: EMAIL WRITING -->
<div class="t-orange" id="email">
  <div class="section-hdr">
    <div class="sh-top"><span class="sh-badge">CATEGORY 08</span></div>
    <h2>📧 Email Writing Prompts</h2>
    <div class="sh-sub">Write welcome sequences, value emails, promos, and follow-ups that actually convert</div>
    <div class="sh-desc">Your email list is your most valuable asset — the one platform you own. These prompts help you write emails that build deep relationships, deliver real value, and make sales consistently without burning out your list.</div>
    <div class="section-count">📦 12 Prompts in this category</div>
  </div>
  <div class="sec-divider"></div>

  <div class="prompt-card t-orange">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 01</div><div class="pc-title">Complete Welcome Sequence (7 Emails)</div><div class="pc-use">✅ Best for: The most important email series you'll ever write — new subscribers read every word</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Write a complete 7-email welcome sequence for new subscribers who join my list in the [NICHE] space.

My lead magnet / freebie: [WHAT THEY SIGNED UP FOR]
My core offer: [PRODUCT OR PROGRAM — what I ultimately want them to buy]
My audience: [WHO THEY ARE AND WHAT THEY WANT]
My brand voice: [warm and casual / direct and no-fluff / motivational / educational]

Write ALL 7 EMAILS in full — subject line, preview text, and complete body:

EMAIL 1 — DELIVER + WELCOME (send immediately):
Deliver the lead magnet, warmly welcome them, set expectations for what's coming. Short. Make them feel they made a great choice.

EMAIL 2 — MY STORY (send Day 1):
A personal story that builds connection and credibility. Before → turning point → after. Why I do what I do. Not polished — real.

EMAIL 3 — YOUR BIGGEST VALUE EMAIL (send Day 2):
Pure value. No selling. Teach one high-quality thing. This is the email that makes them trust you forever.

EMAIL 4 — COMMON MISTAKES (send Day 3):
3 mistakes people make in [NICHE]. Positions you as someone who sees what others miss. Ends with a hint that there's a better way.

EMAIL 5 — SOCIAL PROOF + COMMUNITY (send Day 5):
A win, result, or testimonial from your audience or your own experience. Invites them to reply and share their situation.

EMAIL 6 — SOFT INTRODUCTION TO YOUR OFFER (send Day 7):
Naturally bridge from the value they've been getting to your paid offer. Soft, not pushy. "I created something for people exactly like you..."

EMAIL 7 — THE INVITATION (send Day 9):
The actual offer email. Benefits, what's inside, price, link, and one reason to act now.

Include subject line A/B variants for emails 1, 3, and 7.</div>
    <div class="pc-meta"><span class="pc-tag">📬 Welcome Series</span><span class="pc-tag">🤝 Relationship</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Welcome sequences get 4x higher open rates than any other email you'll ever send. People are most engaged in the first 10 days after subscribing. Make every email count.</div></div>
  </div>

  <div class="prompt-card t-orange">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 02</div><div class="pc-title">Weekly Newsletter Template</div><div class="pc-use">✅ Best for: Staying top-of-mind every week without spending hours writing</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Write a complete weekly newsletter email for my [NICHE] audience. 

This week's theme / main topic: [TOPIC OR INSIGHT YOU WANT TO SHARE]
Something personal happening in my life or business this week: [1–2 SENTENCES — what's on your mind, what you're working on]
A tool, resource, or piece of content I want to recommend: [YOUR RECOMMENDATION]

Write the full email using this structure:

SUBJECT LINE (3 options — one curiosity, one value, one personal):

PREVIEW TEXT (under 90 characters — expands on subject line):

OPENING (personal, conversational — 2–3 sentences):
Start mid-thought, like you're continuing a conversation with a friend. Reference the personal element above. No "Hey [name]!" openers.

MAIN SECTION — THE INSIGHT (150–200 words):
One meaty, specific, actionable insight about [TOPIC]. Not a listicle — a real thought with a real example. Something they won't find in a generic newsletter.

QUICK PICK (2–3 bullets):
— A tool or app I'm using: [DESCRIPTION + WHY]
— A piece of content I loved this week: [WHAT + WHERE]
— Something I'm thinking about: [ONE LINE]

WHAT I'M WORKING ON (1–2 sentences):
Brief personal update. Keeps it human and builds parasocial connection.

CTA (ONE action — pick one):
Reply to this email / Read this / Check this out / Grab this

Sign-off: Warm, personal, feels like the end of a letter from a real person.

Keep total length under 400 words. Reads in under 2 minutes.</div>
    <div class="pc-meta"><span class="pc-tag">📰 Newsletter</span><span class="pc-tag">🔁 Weekly</span><div class="pro-tip"><strong>💡 Pro tip:</strong> The best newsletters feel like a letter from a smart friend, not a marketing blast. Write it in 30 minutes while your thoughts are fresh — don't over-engineer it.</div></div>
  </div>

  <div class="prompt-card t-orange">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 03</div><div class="pc-title">High-Converting Sales Email</div><div class="pc-use">✅ Best for: Sending a promotional email that converts without feeling pushy or spammy</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Write a full promotional email for [PRODUCT NAME] priced at $[PRICE] to my email list of [AUDIENCE].

Give me THREE complete versions optimized for different tones:

VERSION A — STORY-DRIVEN (most conversions for warm audiences):
Opens with a personal story that connects to the product. The sale emerges naturally from the story. Feels like a recommendation, not a pitch.

VERSION B — DIRECT + BENEFIT-LED (best for action-takers who want the facts):
Hook → Problem → Solution → What's Inside (3 bullets) → Price → CTA. Clean, fast, no fluff.

VERSION C — URGENCY + SCARCITY (best for final-day or closing emails):
Opens with the deadline. Acknowledges they've seen this before. Addresses the #1 reason they haven't bought yet. Creates genuine urgency.

For ALL THREE versions include:
— 3 subject line options (curiosity / value / urgency)
— Preview text
— Full email body (200–350 words)
— Clear CTA with the link placeholder
— PS line (the most-read part of any email after the subject line — use it for your strongest point)

Product info:
— What it includes: [KEY COMPONENTS]
— Main benefit: [#1 TRANSFORMATION]
— Audience pain point: [PROBLEM IT SOLVES]
— Any deadline or urgency: [CART CLOSE / LIMITED SPOTS / PRICE INCREASE DATE]</div>
    <div class="pc-meta"><span class="pc-tag">💰 Sales Email</span><span class="pc-tag">📈 Conversions</span><div class="pro-tip"><strong>💡 Pro tip:</strong> The PS line is read by more people than the email body. Put your strongest selling point — or your most urgent deadline — in the PS. Never waste it on a generic "thanks for reading."</div></div>
  </div>

  <div class="prompt-card t-orange">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 04</div><div class="pc-title">Re-Engagement Campaign</div><div class="pc-use">✅ Best for: Waking up cold subscribers who haven't opened in 60–90 days</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Write a 4-email re-engagement sequence for subscribers who have not opened my emails in [TIMEFRAME — e.g., "60+ days"].

My niche: [NICHE]
My list size: [APPROXIMATE SIZE]
What I typically send: [TYPE OF CONTENT — weekly tips / offers / newsletters]

Write all 4 emails in full:

EMAIL 1 — THE HONEST CHECK-IN:
Subject line should acknowledge the gap without guilt. Body: casually check in, acknowledge they've been quiet, offer something new and valuable to re-spark interest. End with a soft question: "Still interested in [NICHE BENEFIT]?"

EMAIL 2 (send 3 days later) — THE FRESH VALUE DROP:
No mention of the re-engagement. Just deliver genuinely useful content about [TOPIC]. Show them what they've been missing. Make them glad they opened this one.

EMAIL 3 (send 3 days later) — THE PERSONAL ONE:
Short. Feels handwritten. "Hey — I'm doing a quick audit of my list and I want to make sure I'm sending you things that are actually helpful. What are you working on right now?" Ask one specific question that's easy to answer.

EMAIL 4 (send 3 days later) — THE BREAKUP EMAIL:
Warm, funny, or honest — never passive-aggressive. "I'm going to remove you from my list unless you want to stay." Include one final piece of value and a clear "keep me subscribed" CTA. This email often has the highest open rate of the four.

For each: subject line, preview text, full body, CTA.</div>
    <div class="pc-meta"><span class="pc-tag">🔄 Re-Engagement</span><span class="pc-tag">🧹 List Health</span><div class="pro-tip"><strong>💡 Pro tip:</strong> A re-engagement campaign every 90 days keeps your list healthy. A smaller, engaged list always outperforms a large, cold one — for deliverability AND for sales.</div></div>
  </div>

  <div class="prompt-card t-orange">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 05</div><div class="pc-title">Abandoned Cart Follow-Up Sequence</div><div class="pc-use">✅ Best for: Recovering sales from people who visited your page but didn't buy</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Write a 4-email follow-up sequence for people who visited my sales page for [PRODUCT NAME] at $[PRICE] but did not purchase.

These are warm leads — they were interested enough to click. Something stopped them. Our job is to figure out what and remove that barrier.

EMAIL 1 — SEND SAME DAY (soft reminder):
Keep it short and breezy. "Hey — noticed you checked out [PRODUCT NAME]." Re-state the #1 benefit. Link back. No pressure. Under 100 words.

EMAIL 2 — SEND DAY 2 (handle the #1 objection):
Address the most common reason this audience doesn't buy. [MOST COMMON OBJECTION — e.g., "not sure if it's the right time", "not sure if it's for beginners"]. Write a genuine, specific response. Ends with: "If that's what's been holding you back, I hope this helps."

EMAIL 3 — SEND DAY 4 (social proof focus):
One powerful testimonial or result story. Real, specific, relatable to where they are right now. "Someone exactly like you just [achieved result] using this."

EMAIL 4 — SEND DAY 6 (final invitation):
The last email in this sequence. Be direct: "This is my last email about [PRODUCT NAME]." Re-state the core value. Create mild urgency (deadline if you have one, or simply "I won't keep mentioning this"). One final, clear CTA.

For each email: subject line, preview text, complete body, link CTA.

My #1 known objection: [WHAT PEOPLE MOST COMMONLY SAY WHEN THEY DON'T BUY]</div>
    <div class="pc-meta"><span class="pc-tag">🛒 Abandoned</span><span class="pc-tag">🔁 Follow-Up</span><div class="pro-tip"><strong>💡 Pro tip:</strong> 70% of people who visit a sales page don't buy on the first visit. Follow-up sequences recover 15–20% of those lost sales. It's the highest-ROI email you can write.</div></div>
  </div>

  <div class="prompt-card t-orange">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 06</div><div class="pc-title">Subject Line Swipe File Builder</div><div class="pc-use">✅ Best for: Building a library of subject lines you can pull from for any email</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Build me a personal email subject line swipe file for a [NICHE] creator targeting [AUDIENCE].

Write 50 subject lines organized into 10 categories of 5 each:

CATEGORY 1 — CURIOSITY GAP (make them need to open to get the answer)
CATEGORY 2 — PERSONAL STORY OPENERS (feel like a message from a friend)
CATEGORY 3 — DIRECT VALUE (promise something specific and useful)
CATEGORY 4 — NUMBERS &amp; LISTS (give them a reason to expect organized value)
CATEGORY 5 — CONTROVERSY / HOT TAKE (provocative but honest)
CATEGORY 6 — SOCIAL PROOF (results, wins, and testimonials)
CATEGORY 7 — URGENCY &amp; SCARCITY (for launch and promo emails)
CATEGORY 8 — QUESTION-BASED (make them think or self-identify)
CATEGORY 9 — ONE-WORD OR VERY SHORT (pattern interrupt — under 4 words)
CATEGORY 10 — SEASONAL &amp; TIMELY (reference current events, months, or moments)

Rules for every subject line:
— Under 50 characters (shows fully on mobile)
— No clickbait — must reflect actual email content
— No ALL CAPS or excessive punctuation
— Should work for [MY NICHE] specifically — not generic

For each subject line, also write a companion preview text (under 90 characters) that expands the hook without giving away the whole email.</div>
    <div class="pc-meta"><span class="pc-tag">📬 Subject Lines</span><span class="pc-tag">📈 Open Rates</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Your subject line is the entire game. A great email with a weak subject line goes unread. Write 10 subject line options for every important email and pick the strongest one.</div></div>
  </div>

  <div class="prompt-card t-orange">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 07</div><div class="pc-title">Post-Purchase Nurture Sequence</div><div class="pc-use">✅ Best for: Turning buyers into loyal repeat customers and raving fans</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Write a 5-email post-purchase sequence for buyers of [PRODUCT NAME] at $[PRICE].

The goal: make buyers feel amazing about their purchase, guide them to their first win, and prime them to buy from me again.

EMAIL 1 — PURCHASE CONFIRMATION + WELCOME (immediately after purchase):
Confirm the purchase, deliver access or download link, make them feel they made a great decision. Include one quick tip to get started RIGHT NOW — not tomorrow.

EMAIL 2 — THE FIRST WIN EMAIL (send Day 2):
Guide them to the fastest win inside the product. What's the ONE thing they should do first? Walk them through it in 3 steps. Short, action-focused.

EMAIL 3 — CHECK-IN + COMMUNITY (send Day 5):
Ask how it's going. Invite them to share their first result. Give them a bonus tip they didn't expect. Build the relationship beyond the transaction.

EMAIL 4 — SUCCESS STORY + WHAT'S NEXT (send Day 10):
Share a success story from another buyer to re-motivate them (if they've stalled). Bridge to your next offer naturally: "If you loved [PRODUCT], you might be ready for [NEXT PRODUCT]."

EMAIL 5 — THE TESTIMONIAL ASK (send Day 14):
Ask for honest feedback. Include specific questions that help you get a useful testimonial. Make it easy — give them a template or prompts to follow.

For each email: subject line, preview text, complete body, CTA.
Product info: [WHAT THEY BOUGHT AND WHAT IT HELPS THEM DO]</div>
    <div class="pc-meta"><span class="pc-tag">🏆 Post-Purchase</span><span class="pc-tag">🔁 Retention</span><div class="pro-tip"><strong>💡 Pro tip:</strong> The money is in repeat buyers. Someone who buys once and gets a result will buy from you again and again. The post-purchase sequence is where you create lifetime customers.</div></div>
  </div>

  <div class="prompt-card t-orange">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 08</div><div class="pc-title">Broadcast Email — Pure Value Drop</div><div class="pc-use">✅ Best for: Building deep trust between promos — the emails that make your list WANT to hear from you</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Write a pure-value broadcast email for my [NICHE] audience about [TOPIC / TIP / INSIGHT].

NO selling. NO mention of any product. Just an email so good they screenshot it, share it, and immediately trust me more.

SUBJECT LINE (3 options):
One curiosity-driven, one benefit-driven, one ultra-short pattern interrupt

PREVIEW TEXT:
Under 90 characters, expands the subject without giving away everything

OPENING (2–3 sentences):
Start mid-thought. Reference something real — a mistake I made, a question I got, something I observed. Never "I hope this email finds you well."

THE CORE INSIGHT (200–250 words):
One idea, explained deeply. Not a listicle — a single, meaty insight with:
— The concept explained clearly
— A real example or story that makes it concrete
— The counterintuitive angle most people miss
— Why this matters specifically for [AUDIENCE]

THE ACTION STEP (3–5 sentences):
What should they do with this? One specific thing they can try today or this week.

THE CLOSE (2–3 sentences):
Warm, personal, conversational. A reflection or question. Signs off like a real person.

CTA: ONE soft action — reply to this, try this and let me know how it goes, share this with someone who needs it

Topic: [YOUR TOPIC]
Key insight I want to share: [YOUR MAIN POINT IN 1–2 SENTENCES]</div>
    <div class="pc-meta"><span class="pc-tag">💎 Pure Value</span><span class="pc-tag">🤝 Trust</span><div class="pro-tip"><strong>💡 Pro tip:</strong> For every 1 sales email you send, send 3–4 pure value emails. This ratio keeps your list engaged, your open rates high, and your unsubscribes low.</div></div>
  </div>

  <div class="prompt-card t-orange">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 09</div><div class="pc-title">Flash Sale Email Sequence</div><div class="pc-use">✅ Best for: Running a limited-time discount or bonus to spike revenue fast</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Write a complete 3-email flash sale sequence for [PRODUCT NAME] with a [DISCOUNT / BONUS DESCRIPTION] available for [TIMEFRAME — e.g., "48 hours only"].

Product: [NAME AND DESCRIPTION]
Regular price: $[REGULAR PRICE]
Sale price / offer: $[SALE PRICE] or [BONUS BEING ADDED]
Sale window: [START DATE/TIME to END DATE/TIME]
Reason for the sale (always give a reason — "just because" doesn't convert): [E.G., "celebrating my birthday", "end of month sale", "I hit a milestone I want to celebrate with you"]

EMAIL 1 — FLASH SALE ANNOUNCEMENT (send when sale opens):
Subject: Something fun and unexpected — don't lead with "SALE"
Body: Share the reason for the sale warmly. Introduce the offer. Make it feel like a gift to your list, not a desperation move. Clear CTA with deadline.

EMAIL 2 — MIDPOINT CHECK-IN (send halfway through — e.g., 24 hours in):
Subject: Curiosity or social proof angle
Body: Share a result or testimonial from a buyer. Remind them of the deadline without being aggressive. Add one new piece of value — a bonus tip related to the product.

EMAIL 3 — FINAL HOURS (send 2–4 hours before close):
Subject: Urgency — but honest urgency, not fake
Body: Short. Direct. The sale closes at [TIME]. Here's what they're getting. Here's the link. No fluff.

For each: subject line, preview text, complete body, CTA with deadline language.</div>
    <div class="pc-meta"><span class="pc-tag">⚡ Flash Sale</span><span class="pc-tag">⏰ Urgency</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Always give a reason for your sale. "48-hour sale because I hit 10,000 followers and I want to celebrate with you" converts 3x better than "Limited-time sale." Real reasons feel real.</div></div>
  </div>

  <div class="prompt-card t-orange">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 10</div><div class="pc-title">Email List Growth Strategy</div><div class="pc-use">✅ Best for: Building your email list from your social media audience</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Help me build a complete strategy to grow my email list from my [PLATFORM] audience of [FOLLOWER COUNT] followers.

My niche: [NICHE]
My audience's biggest pain point: [PAIN POINT]
What I currently offer as a freebie (if anything): [FREEBIE OR "NONE YET"]

Answer ALL of the following:

1. LEAD MAGNET IDEAS (give me 8 specific options):
What free resource would my specific audience exchange their email for? For each: name, description, format, and why it would convert.

2. LEAD MAGNET CREATION SHORTCUT:
How can I create the highest-converting lead magnet from the above list in under 3 hours?

3. CONTENT-TO-EMAIL BRIDGE STRATEGY:
What specific types of content on [PLATFORM] drive the most email list signups? Give me 5 content formulas that consistently push people to sign up.

4. LINK-IN-BIO OPTIMIZATION:
How should my bio link page be structured to maximize email signups? What order should things appear?

5. STORIES LIST-BUILDING STRATEGY:
3 specific Story formats that drive email list signups without feeling like a constant sales pitch.

6. LIVE STREAM LIST-BUILDING:
How and when to mention my email list during a live to get signups in real-time.

7. FIRST 30 DAYS PLAN:
Give me a week-by-week plan for my first 30 days of actively growing my list. How many signups should I realistically aim for?

8. MILESTONE BENCHMARKS:
At what list size does email become a meaningful revenue channel for a [NICHE] creator?</div>
    <div class="pc-meta"><span class="pc-tag">📈 List Growth</span><span class="pc-tag">🧲 Lead Magnet</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Your email list is the only audience you truly own. An algorithm can wipe your social reach overnight. 1,000 engaged email subscribers are worth more than 100,000 passive followers.</div></div>
  </div>

  <div class="prompt-card t-orange">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 11</div><div class="pc-title">Email Sequence Diagnostics</div><div class="pc-use">✅ Best for: Fixing an email sequence that's not converting the way it should</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">My email sequence is underperforming. Here are my stats and the sequence:

SEQUENCE TYPE: [Welcome / Sales / Launch / Follow-up / Other]
AVERAGE OPEN RATE: [%] (industry average is ~20–30%)
AVERAGE CLICK RATE: [%] (industry average is ~2–5%)
CONVERSION RATE (if sales sequence): [%]
UNSUBSCRIBE RATE: [%]

HERE IS MY CURRENT SEQUENCE:
Email 1 — Subject: [SUBJECT] — Body summary: [2–3 SENTENCES]
Email 2 — Subject: [SUBJECT] — Body summary: [2–3 SENTENCES]
[Continue for each email...]

Diagnose and fix my sequence:

1. OPEN RATE ISSUES: Are my subject lines causing low opens? Rewrite the 3 weakest ones.

2. CLICK RATE ISSUES: Are my CTAs unclear, buried, or unconvincing? What should change?

3. DROP-OFF ANALYSIS: Where are people stopping opening? What does that tell us?

4. TONE ASSESSMENT: Does my sequence read like a real person or a marketing funnel? What can be more human?

5. VALUE-TO-SELL RATIO: Am I selling too soon? Not soon enough? What's the right balance for my audience?

6. MISSING EMAILS: What email type is absent from my sequence that would significantly improve performance?

7. FULL REWRITE PRIORITY: Which ONE email should I rewrite first to see the biggest improvement? Write the rewrite.</div>
    <div class="pc-meta"><span class="pc-tag">🔧 Diagnostics</span><span class="pc-tag">📊 Optimization</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Low open rates = subject line problem. Low click rates = CTA or value problem. High unsubscribes = relevance or frequency problem. Diagnose before you rewrite everything.</div></div>
  </div>

  <div class="prompt-card t-orange">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 12</div><div class="pc-title">Monthly Email Calendar Builder</div><div class="pc-use">✅ Best for: Planning your entire month of emails so you're never scrambling last minute</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Build me a complete monthly email calendar for [MONTH / YEAR] for a [NICHE] creator.

My email frequency goal: [HOW MANY EMAILS PER WEEK — e.g., 2x/week]
Products I'm promoting this month: [LIST ANY OFFERS WITH DATES]
Seasonal events or relevant dates this month: [HOLIDAYS / AWARENESS DAYS / YOUR PERSONAL MILESTONES]
My audience's current focus: [WHAT THEY'RE THINKING ABOUT THIS TIME OF YEAR]

Build me a week-by-week email plan for the full month:

WEEK 1: [DATES]
— Email 1: Type, topic, goal (value / relationship / promo / re-engage)
— Email 2: Type, topic, goal
— Subject line draft for each

WEEK 2: [DATES]
[Same format]

WEEK 3: [DATES]
[Same format]

WEEK 4: [DATES]
[Same format]

For the full month, ensure:
— The value-to-promo ratio is at least 3:1
— No two consecutive promotional emails
— At least one "reply to me" or relationship email per week
— A logical narrative arc — the month should tell a story, not just be random emails
— Any launch sequence is fully integrated into the calendar

Also give me:
— The 3 most important emails this month and why
— What I should NOT email about this month (topics to avoid)
— One unexpected email idea that would surprise my list in a good way</div>
    <div class="pc-meta"><span class="pc-tag">📅 Planning</span><span class="pc-tag">🗓️ Calendar</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Plan your email calendar at the start of every month in one sitting. Batch-write as many emails as you can in one session. Consistency in email is a superpower — and it's only possible with a plan.</div></div>
  </div>
</div>

<!-- ============================================================ -->
<!-- SECTION 9: CONTENT REPURPOSING PROMPTS -->
<!-- ============================================================ -->
<div class="section-header t-indigo">
  <div class="sh-icon">♻️</div>
  <div>
    <div class="sh-label">SECTION 09</div>
    <div class="sh-title">Content Repurposing Prompts</div>
    <div class="sh-sub">Turn one piece of content into 10 — stop creating from scratch every time</div>
  </div>
</div>
<div class="card-grid">

  <div class="prompt-card t-indigo">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 01</div><div class="pc-title">One Video → 10 Pieces of Content</div><div class="pc-use">✅ Best for: Maximizing every YouTube video, podcast episode, or long-form video you create</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">I just created a [TYPE OF CONTENT — e.g., YouTube video / podcast episode / livestream] titled: "[TITLE OF CONTENT]"

Here is a summary or transcript of the key points:
[PASTE SUMMARY OR KEY POINTS]

Help me repurpose this into 10 different pieces of content across multiple platforms. For each piece, give me the full content or a detailed enough draft that I can post it with minimal editing:

1. SHORT-FORM VIDEO SCRIPT (60 seconds): Hook + key insight + CTA
2. INSTAGRAM CAROUSEL (7 slides): Title slide, 5 insight slides, CTA slide — include slide text for each
3. TWITTER/X THREAD: Opening tweet + 7 supporting tweets + closing tweet with CTA
4. LINKEDIN POST: Professional angle of the same content — longer form, thoughtful
5. FACEBOOK POST: Community-oriented, conversational version for a general audience
6. EMAIL TO MY LIST: Subject line + full email body (value-focused, not promotional)
7. BLOG POST INTRO (300 words): SEO-friendly intro that teases the full content
8. INSTAGRAM CAPTION (for a static post): Hook + value + CTA + hashtags
9. PINTEREST PIN DESCRIPTION: Keyword-rich, curiosity-driven description
10. STORY SEQUENCE (5 frames): Slide-by-slide story arc that drives to the main content

For each piece, adapt the tone and format to the platform. Don't just copy and paste — actively translate the message for where it's being posted.</div>
    <div class="pc-meta"><span class="pc-tag">♻️ Repurposing</span><span class="pc-tag">📱 Multi-Platform</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Run this prompt EVERY time you create a long-form video or episode. One production session can fuel your entire content calendar for a week.</div></div>
  </div>

  <div class="prompt-card t-indigo">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 02</div><div class="pc-title">Blog Post to Full Content Suite</div><div class="pc-use">✅ Best for: Creators who write long-form blog posts and want to maximize every article</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">Here is a blog post I wrote titled "[BLOG POST TITLE]":

[PASTE FULL BLOG POST TEXT]

Turn this blog post into a complete content suite. Give me each of the following with enough detail to post directly:

INSTAGRAM REEL SCRIPT: A punchy, 45-second video script pulling the most shareable insight from this article. Include spoken-word hooks and delivery cues (pause here, emphasize this word, etc.)

CAROUSEL POST (8 slides): Break the article's main points into a swipeable carousel. Include slide title and 2-3 bullet points per slide. Final slide = CTA.

EMAIL NEWSLETTER: Subject line (give me 3 options) + preview text + full newsletter email using the article's insights as the value core

YOUTUBE THUMBNAIL CONCEPT: Describe the visual, text overlay, and emotion it should trigger

YOUTUBE TITLE OPTIONS (5): SEO-optimized but click-worthy

VIDEO SCRIPT OUTLINE: A 5-7 minute YouTube video structure using this article as the backbone — intro hook, main points, conclusion CTA

PINTEREST PIN (3 versions): Title + description for 3 different pin angles targeting different search keywords

QUOTE GRAPHICS (5): Pull 5 quotable lines from the post that would work as standalone graphic posts

RE-POST STRATEGY: How I should re-promote this post over the next 90 days to keep it alive</div>
    <div class="pc-meta"><span class="pc-tag">✍️ Blog</span><span class="pc-tag">♻️ Repurposing</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Your best evergreen blog posts deserve to be repurposed every quarter. Set a reminder — what performed well 6 months ago can perform just as well again with a fresh angle.</div></div>
  </div>

  <div class="prompt-card t-indigo">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 03</div><div class="pc-title">Viral Post → Evergreen Content System</div><div class="pc-use">✅ Best for: Turning your best-performing post into a content system you reuse forever</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">I have a post that went viral / performed really well. Here are the details:

Platform: [WHERE IT PERFORMED]
Content type: [REEL / CAROUSEL / TWEET / EMAIL / etc.]
The content: [PASTE OR DESCRIBE THE CONTENT]
Why I think it worked: [YOUR THEORY — or leave blank if unsure]
Stats: [VIEWS / LIKES / SHARES / COMMENTS / etc.]

Help me turn this one viral piece into an evergreen content system I can use repeatedly.

1. CORE MESSAGE EXTRACTION: What is the underlying message or insight that made this resonate? Articulate it in 2-3 sentences.

2. FORMAT VARIATIONS (5 formats): Rewrite the core message in 5 different content formats — Reel script, carousel, email, long-form post, story series

3. ANGLE VARIATIONS (5 angles): Keep the same format but change the angle — beginner version, advanced version, controversial take, story-driven version, stat-backed version

4. AUDIENCE VARIATIONS: How would this message land differently for [AUDIENCE SEGMENT 1] vs. [AUDIENCE SEGMENT 2]? Write both versions.

5. PLATFORM VARIATIONS: Adapt this content for [PLATFORM 1], [PLATFORM 2], and [PLATFORM 3] — different tone, length, format norms

6. 90-DAY REPOST CALENDAR: Tell me exactly when and how to repost this content over the next 90 days (with slight variations each time) so I can maximize its lifespan without annoying my audience

7. NEXT PIECE: Based on what performed well here, what should my very next piece of content be?</div>
    <div class="pc-meta"><span class="pc-tag">🚀 Viral</span><span class="pc-tag">🔄 System</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Most creators move on after a viral post. Smart creators mine it for 6-12 months. One great idea, executed in many forms, is worth more than 50 new ideas executed once.</div></div>
  </div>

  <div class="prompt-card t-indigo">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 04</div><div class="pc-title">Podcast to Platform Content</div><div class="pc-use">✅ Best for: Podcasters who want to show up everywhere without creating content from scratch</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">I just recorded a podcast episode. Here are the details:

Episode title: [EPISODE TITLE]
Episode number: [NUMBER]
Guest (if any): [GUEST NAME AND TITLE — or "solo episode"]
Key topics covered: [LIST 5-7 MAIN POINTS OR TIMESTAMPS]
Best quotes or moments: [PASTE 3-5 STANDOUT QUOTES OR LINES]
My audience: [WHO LISTENS TO THIS SHOW]

Help me build a full launch package for this episode across every major platform:

SOCIAL MEDIA PACKAGE:
— Instagram caption (post with audiogram/clip)
— Instagram story sequence (5 frames to drive listens)
— TikTok/Reels script (60-second hook-driven highlight)
— Twitter/X thread (7-tweet breakdown of the episode)
— LinkedIn post (professional framing of the key insights)
— Facebook post (community-focused, conversational)

EMAIL PACKAGE:
— Subject line (3 options)
— Preview text
— Full email body (400-600 words, value-heavy, drives to listen)

SHOW NOTES:
— Episode description (150 words, SEO-friendly)
— Key takeaways (5 bullet points)
— Timestamps (formatted properly)
— Resources mentioned section
— Guest bio blurb (if applicable)

YOUTUBE PACKAGE (if cross-posting):
— YouTube title (5 options)
— YouTube description (with chapters)
— Thumbnail concept description

CLIP SELECTION: Which 3 moments from the episode should I clip for short-form? Describe each one and why it will perform.</div>
    <div class="pc-meta"><span class="pc-tag">🎙️ Podcast</span><span class="pc-tag">📦 Launch Package</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Batch this process — run this prompt for 4 episodes at once and schedule everything for the next month. Your podcast can run your entire content calendar.</div></div>
  </div>

  <div class="prompt-card t-indigo">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 05</div><div class="pc-title">Comment Section Mining Prompt</div><div class="pc-use">✅ Best for: Turning your audience's questions and comments into your next 30 pieces of content</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">I want to mine my comment section for content ideas. Here are real comments and questions my audience has left on my content recently:

[PASTE 10-20 REAL COMMENTS OR QUESTIONS]

My niche: [YOUR NICHE]
My content format: [REELS / YOUTUBE / PODCAST / BLOG / etc.]
My audience's biggest pain point: [DESCRIBE IT]

Analyze these comments and do the following:

1. COMMON THEMES: What topics, questions, and pain points come up most often? Group them into 5-7 themes.

2. CONTENT IDEAS (20 pieces): Generate 20 specific content ideas directly inspired by what my audience is asking. Include the topic, angle, and format for each.

3. HIGH-PRIORITY IDEAS: Which 5 ideas should I create FIRST based on engagement potential and audience need? Explain why.

4. HIDDEN DESIRES: What is my audience NOT directly asking for but clearly wants based on how they phrase things? What's the unspoken need behind their questions?

5. OBJECTION MINING: What objections or doubts are hidden in these comments that I should address in future content?

6. TESTIMONIAL POTENTIAL: Are any of these comments structured in a way I could use as a social proof testimonial or before/after story?

7. SERIES POTENTIAL: Is there a comment thread or repeated question complex enough to become a multi-part series?</div>
    <div class="pc-meta"><span class="pc-tag">💬 Comments</span><span class="pc-tag">🔍 Research</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Do this exercise every single month. Your comment section is a real-time focus group that most creators completely ignore. The best ideas come directly from your audience — not from your own head.</div></div>
  </div>

  <div class="prompt-card t-indigo">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 06</div><div class="pc-title">Old Content Revival Prompt</div><div class="pc-use">✅ Best for: Breathing new life into content from 6–24 months ago without starting over</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">I have older content I want to revive and update. Here's what I have:

Original content title/topic: [TITLE OR DESCRIPTION]
When it was created: [APPROXIMATE DATE]
Platform it was originally on: [PLATFORM]
Original performance: [HOW IT DID — good / okay / flopped]
What's changed since then: [TRENDS / PLATFORM SHIFTS / NEW INFO / YOUR OWN GROWTH]

Help me revive this content intelligently:

1. RELEVANCE AUDIT: What parts of this content are still valid and resonant today? What needs to be updated, removed, or reframed?

2. FRESH ANGLE: Give me 3 new angles or hooks I could use to present the same core information in a way that feels completely new

3. UPDATED VERSION: Rewrite the hook/intro with a contemporary angle that reflects current trends and audience sentiment

4. FORMAT UPGRADE: How could I upgrade the format? (e.g., article → video, video → carousel, static post → series)

5. NEW PLATFORM: Which platform is best for this content RIGHT NOW based on current algorithm trends that didn't exist when I first posted?

6. RE-RELEASE STRATEGY: Write the caption/intro I should use when I re-release this — acknowledge it's a revisit (builds trust) but frame it as more valuable than ever

7. COMBINE AND EXPAND: Are there other older pieces of content I could combine with this one to create something more comprehensive?</div>
    <div class="pc-meta"><span class="pc-tag">🔄 Revival</span><span class="pc-tag">📅 Evergreen</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Your archive is a goldmine. Most audiences have completely turned over in 12-18 months — what they've never seen is brand new to them. Don't be afraid to revisit your best work.</div></div>
  </div>

  <div class="prompt-card t-indigo">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 07</div><div class="pc-title">Short-Form → Long-Form Expansion</div><div class="pc-use">✅ Best for: Taking a viral Reel or TikTok and expanding it into a full YouTube video or blog post</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">I have a short-form piece of content that performed well and I want to expand it into a full long-form piece. Here's the original:

Platform: [TIKTOK / INSTAGRAM REELS / YOUTUBE SHORTS / etc.]
Original content (script or description): [PASTE IT]
Performance stats: [VIEWS / LIKES / COMMENTS]
Main insight: [WHAT THE CORE IDEA WAS]
Audience response: [WHAT PEOPLE COMMENTED OR REACTED TO MOST]

Help me expand this into a full-length [YOUTUBE VIDEO / BLOG POST / PODCAST EPISODE]:

TITLE OPTIONS (5): Long-form titles that capitalize on the short-form momentum
THUMBNAIL CONCEPT: Visual concept description for YouTube (if applicable)
INTRO (Hook + Promise): 60-90 second spoken intro that references the viral short-form piece and promises even more depth
MAIN CONTENT STRUCTURE: Full outline with 5-8 sections/chapters, each with talking points
DEPTH ADDITIONS: What can I add to the long-form that I couldn't cover in the short? New examples, research, step-by-step breakdowns, case studies
VIEWER RETENTION TIPS: 3 specific moments or techniques I should include to keep people watching to the end
OUTRO + CTA: How to close the video and what action to direct viewers to take
DESCRIPTION (SEO): Full YouTube/blog description with keywords, timestamps, and links section</div>
    <div class="pc-meta"><span class="pc-tag">📹 Long-Form</span><span class="pc-tag">📈 Expansion</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Short-form that goes viral is market research. It tells you exactly what your audience wants more of. Long-form on the same topic captures high-intent viewers and builds deeper authority.</div></div>
  </div>

  <div class="prompt-card t-indigo">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 08</div><div class="pc-title">Content Batching Master Plan</div><div class="pc-use">✅ Best for: Planning an entire month of content in one sitting so you only batch-create once</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">I want to batch-create an entire month of content in [NUMBER] production days. Help me build the ultimate batching plan.

My niche: [YOUR NICHE]
My posting schedule: [HOW MANY POSTS PER WEEK ON WHICH PLATFORMS]
My content formats: [REELS / CAROUSELS / YOUTUBE / PODCAST / BLOG / etc.]
Production days available: [e.g., 2 days per month]
My current content pillars: [LIST 3-5 CONTENT PILLARS OR THEMES]
Current goals: [GROW FOLLOWERS / BUILD EMAIL LIST / LAUNCH A PRODUCT / etc.]

Build me a complete batching plan:

CONTENT MAP (full month):
— Week 1: [List every piece with topic, format, platform, and goal]
— Week 2: [Same]
— Week 3: [Same]
— Week 4: [Same]

BATCHING SCHEDULE:
— Production Day 1 agenda (time-blocked, hour by hour)
— Production Day 2 agenda (time-blocked, hour by hour)

FILMING ORDER: What should I film/record first, second, third? (Group by location, outfit, topic to minimize setup changes)

ASSET CHECKLIST: What do I need prepared before I sit down to create? (outlines, props, b-roll shots, graphics, etc.)

EDITING ORDER: In what order should content be edited? (prioritize time-sensitive posts first)

SCHEDULING PLAN: What gets posted when, and at what times based on platform best practices?

WHAT TO SKIP THIS MONTH: Is there anything on my plan I should cut to stay realistic and avoid burnout?</div>
    <div class="pc-meta"><span class="pc-tag">📅 Batching</span><span class="pc-tag">⚡ Efficiency</span><div class="pro-tip"><strong>💡 Pro tip:</strong> The secret to consistent content is NOT daily motivation — it's monthly systems. One focused batching day can produce 4 weeks of content. Schedule it like a non-negotiable appointment.</div></div>
  </div>

</div>

<!-- ============================================================ -->
<!-- SECTION 10: MONETIZATION & OFFERS PROMPTS -->
<!-- ============================================================ -->
<div class="section-header t-rose">
  <div class="sh-icon">💸</div>
  <div>
    <div class="sh-label">SECTION 10</div>
    <div class="sh-title">Monetization & Income Strategy Prompts</div>
    <div class="sh-sub">Build real income from your audience — products, services, sponsorships, and beyond</div>
  </div>
</div>
<div class="card-grid">

  <div class="prompt-card t-rose">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 01</div><div class="pc-title">Monetization Roadmap Builder</div><div class="pc-use">✅ Best for: Creators at any stage who want a clear, sequenced plan for turning content into income</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">I want to build a real income from my content creation. Help me build a monetization roadmap customized to my situation.

My niche: [YOUR NICHE]
My current audience size: [PLATFORM + FOLLOWER COUNT for each]
My email list size: [NUMBER — or "none yet"]
My content format: [REELS / YOUTUBE / PODCAST / BLOG / etc.]
Monthly content views/reach: [APPROXIMATE]
How long I've been creating: [TIME]
Skills I have beyond content creation: [LIST ANY — coaching, design, writing, etc.]
Time available to work on monetization: [HOURS PER WEEK]
Income goal in 12 months: [$AMOUNT]

Build me a monetization roadmap in three phases:

PHASE 1 — FOUNDATION (Months 1-3):
What should I set up and prove before trying to make money? What free or low-cost offers build trust?

PHASE 2 — FIRST INCOME (Months 3-6):
What is the easiest, fastest way to start generating income given my current audience size and skills? Give me exact offers, price points, and launch strategy.

PHASE 3 — SCALE (Months 6-12):
Once I'm generating consistent income, how do I scale? What new revenue streams should I add and in what order?

For each phase, also tell me:
— The #1 most important action
— What mistake to avoid
— A realistic income expectation</div>
    <div class="pc-meta"><span class="pc-tag">💰 Roadmap</span><span class="pc-tag">📈 Strategy</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Don't try to monetize everything at once. The creators who build sustainable income focus on one revenue stream until it's reliable, then add the next. Sequence matters more than variety.</div></div>
  </div>

  <div class="prompt-card t-rose">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 02</div><div class="pc-title">Digital Product Idea Generator</div><div class="pc-use">✅ Best for: Creators who want to sell digital products but don't know what to create first</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">I want to create and sell digital products, but I need help figuring out what to build first.

My niche: [YOUR NICHE]
My content topics: [LIST YOUR MAIN CONTENT TOPICS]
My audience's biggest problems: [TOP 3 PAIN POINTS]
My audience's biggest goals: [TOP 3 DESIRES]
My own expertise: [WHAT DO YOU KNOW REALLY WELL]
Price range I want to be in: [e.g., $27-$97]
Time I can spend creating the product: [HOURS / DAYS AVAILABLE]

Generate 10 specific digital product ideas for me. For each one, include:

— Product name and format (template pack, mini-course, ebook, checklist, swipe file, etc.)
— What problem it solves in one sentence
— Who specifically it's for (narrow the audience)
— Why it justifies the price tag
— Estimated creation time
— Sales potential score (low / medium / high) and why
— One sentence pitch: how I'd describe it in my content

Then rank all 10 by: easiest to create, most likely to sell, and highest potential revenue.

Finally, pick the #1 product I should create FIRST and write a full product concept brief for it: name, format, outline, price, delivery method, and launch plan.</div>
    <div class="pc-meta"><span class="pc-tag">🛍️ Digital Products</span><span class="pc-tag">💡 Ideas</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Your first digital product doesn't have to be perfect — it has to be done. Sell it to 10 people, get feedback, improve it. Done beats perfect every single time.</div></div>
  </div>

  <div class="prompt-card t-rose">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 03</div><div class="pc-title">Sponsorship Pitch Email Writer</div><div class="pc-use">✅ Best for: Creators ready to pitch brands and land paid partnerships without sounding desperate</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">I want to pitch a brand for a paid sponsorship. Help me write a compelling pitch email.

Brand I'm pitching: [BRAND NAME]
Why I like this brand: [GENUINE REASON — use their product, aligned with values, etc.]
My platform(s): [PLATFORMS + FOLLOWER COUNTS]
My engagement rate: [AVERAGE LIKES / COMMENTS / VIEWS PER POST]
My audience demographics: [AGE, GENDER, LOCATION, INTERESTS]
Why my audience would connect with this brand: [THE ALIGNMENT]
What I'm proposing: [INTEGRATION TYPE — dedicated video, story mention, product review, etc.]
My rate range: [$XXX - $XXX]

Write me a professional, confident, and personalized pitch email. It should:

— Open with something specific that shows I know the brand (not generic)
— Introduce me and my platform in 2-3 sentences max (confidence, not desperation)
— Lead with VALUE — how does this partnership benefit THEM and their target customer?
— Include my key audience stats in a natural way (not like a resume dump)
— Propose a specific collaboration idea (not "open to any opportunity")
— End with a clear, low-friction call to action

Also give me:
— Subject line (3 options)
— A follow-up email to send 7 days later if no response
— What to include in a media kit for this brand specifically
— What I should NOT say in a brand pitch (common mistakes)</div>
    <div class="pc-meta"><span class="pc-tag">🤝 Sponsorships</span><span class="pc-tag">📧 Pitch</span><div class="pro-tip"><strong>💡 Pro tip:</strong> The best brand pitches lead with audience value, not personal stats. Brands don't care how many followers you have — they care if your audience will buy their product. Prove that, and you'll get the deal.</div></div>
  </div>

  <div class="prompt-card t-rose">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 04</div><div class="pc-title">Membership / Community Offer Design</div><div class="pc-use">✅ Best for: Creators building a paid community, membership site, or subscription offer</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">I want to build a paid membership or community. Help me design the entire offer.

My niche: [YOUR NICHE]
My audience: [WHO THEY ARE AND WHAT THEY WANT]
Current free content I create: [WHAT YOU ALREADY GIVE AWAY]
My skills/expertise: [WHAT YOU CAN TEACH OR FACILITATE]
Competitors or inspiration: [ANY MEMBERSHIPS YOU ADMIRE]
Desired price point: [$X/month or $X/year]
Time I can commit to running it: [HOURS PER WEEK]

Design my full membership offer:

MEMBERSHIP NAME: [3 name options with explanation]

VALUE STACK: What exactly do members get every month? List every deliverable with detail:
— Content (what type, how often, in what format)
— Community access (platform, structure, moderation style)
— Live sessions (calls, workshops, Q&As — frequency and format)
— Resources (templates, tools, trainings)
— Exclusive benefits (bonuses, early access, discounts)

TRANSFORMATION PROMISE: What specific outcome does a committed member achieve in 90 days?

TIER OPTIONS: Should I offer one tier or multiple? If multiple, what's in each tier and at what price?

LAUNCH STRATEGY: How do I get my first 50 paying members? What's the launch sequence?

RETENTION TACTICS: What keeps people subscribed month after month? What makes them want to stay?

CHURN PREVENTION: What do I say to someone who tries to cancel? Write a 3-part save sequence.</div>
    <div class="pc-meta"><span class="pc-tag">👥 Membership</span><span class="pc-tag">🔄 Recurring</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Recurring revenue is the ultimate creator business model. Even 100 members at $47/month = $4,700/month of predictable income. Start small, deliver exceptional value, and grow from there.</div></div>
  </div>

  <div class="prompt-card t-rose">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 05</div><div class="pc-title">Passive Income Content Funnel Designer</div><div class="pc-use">✅ Best for: Creators who want to earn while they sleep by turning their content into a selling machine</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">I want to build a passive income system where my content automatically leads people into my paid offers. Help me design the full funnel.

My niche: [YOUR NICHE]
My primary platform: [WHERE MOST OF YOUR AUDIENCE IS]
My paid offer(s): [WHAT YOU'RE SELLING — price, format]
My lead magnet / freebie (if any): [WHAT YOU GIVE AWAY FREE — or "I don't have one yet"]
My email platform: [CONVERTKIT / MAILCHIMP / FLODESK / etc. — or "I don't have one yet"]

Design my full passive income content funnel:

TOP OF FUNNEL — AWARENESS CONTENT:
What content should I create to attract cold audiences and build awareness? Give me 5 specific content ideas that lead naturally toward my offer.

MIDDLE OF FUNNEL — TRUST CONTENT:
What content converts lurkers into engaged followers? Give me 5 content types that build trust and deepen the relationship.

BOTTOM OF FUNNEL — CONVERSION CONTENT:
What content specifically sells my offer without being salesy? Give me 5 specific content ideas with selling baked in naturally.

LEAD CAPTURE MOMENT:
At what point in the funnel should I offer my freebie/lead magnet? How should I promote it in my content?

EMAIL NURTURE SEQUENCE:
After someone joins my list, what are the first 7 emails they receive? Give me the topic, goal, and one-sentence pitch for each.

AUTOMATION OPPORTUNITIES:
Where can I set up automations so this works while I sleep? List every email trigger and sequence I need.

THE LOOP:
How does my paid content drive back to my free content to keep the flywheel spinning?</div>
    <div class="pc-meta"><span class="pc-tag">💸 Passive Income</span><span class="pc-tag">🔁 Funnel</span><div class="pro-tip"><strong>💡 Pro tip:</strong> A passive income funnel is not built overnight — but once it's built, it compounds. Even a modest funnel converting at 2% with 500 email subs can generate consistent monthly revenue with no extra effort.</div></div>
  </div>

  <div class="prompt-card t-rose">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 06</div><div class="pc-title">Pricing Confidence & Rate Card Builder</div><div class="pc-use">✅ Best for: Creators who undercharge, feel awkward about money, or have never built an official rate card</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">I need help figuring out what to charge and how to present my rates. I currently feel [uncomfortable / unsure / like I'm undercharging] when it comes to pricing.

My niche: [YOUR NICHE]
My platforms and audience size: [LIST EACH]
My content formats: [WHAT I CREATE]
Services I currently offer or want to offer: [e.g., sponsored posts, UGC content, consulting, coaching, courses]
What I currently charge (if anything): [$X for X]
Income goal per month: [$AMOUNT]
Time available for client/brand work per month: [HOURS]

Help me build a confident pricing strategy:

1. MARKET RATE RESEARCH: Based on my platform and audience size, what is the going market rate for each of my service types? (CPM approach, flat fee ranges, etc.)

2. MY RATE CARD: Build me a full rate card for each service type I offer:
— Service name
— What's included
— Deliverables and timeline
— Price (and a premium option)
— What makes it worth that price

3. PRICE ANCHORING: How should I present my prices so clients anchor to my highest tier first?

4. NEGOTIATION SCRIPTS: What do I say when a brand says my rate is "too high"? Give me 3 different responses depending on how much I want the deal.

5. PACKAGE DEALS: Should I bundle services? If so, design 3 packages with names, inclusions, and prices.

6. MINDSET REFRAME: Write me a short paragraph that reframes how I think about charging for my work — to remind myself why I deserve to be paid well.</div>
    <div class="pc-meta"><span class="pc-tag">💰 Pricing</span><span class="pc-tag">📋 Rate Card</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Undercharging doesn't attract better clients — it attracts the ones who will drain you. Your rate is a signal of your value. Charge what you're worth, and the right brands will respect it.</div></div>
  </div>

</div>

<!-- ============================================================ -->
<!-- SECTION 11: CREATOR MINDSET & BURNOUT RECOVERY PROMPTS -->
<!-- ============================================================ -->
<div class="section-header t-teal">
  <div class="sh-icon">🧠</div>
  <div>
    <div class="sh-label">SECTION 11</div>
    <div class="sh-title">Creator Mindset & Burnout Recovery Prompts</div>
    <div class="sh-sub">Get out of your head, out of your slump, and back to creating with clarity</div>
  </div>
</div>
<div class="card-grid">

  <div class="prompt-card t-teal">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 01</div><div class="pc-title">Creator Block Breaker</div><div class="pc-use">✅ Best for: When you're staring at a blank screen with zero ideas and zero motivation</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">I'm completely stuck. I have no ideas, no motivation, and I don't even know where to start. I haven't posted in [X DAYS / WEEKS].

My niche: [YOUR NICHE]
How I'm feeling right now: [BLANK / OVERWHELMED / BORED / BURNT OUT / UNINSPIRED]
What's been going on in my life: [BRIEF CONTEXT — optional but helpful]
The last piece of content I created that I was proud of: [DESCRIBE IT]
The content I used to get excited about: [WHAT USED TO LIGHT YOU UP]

Help me break out of this block with a structured approach:

1. DIAGNOSIS: Based on what I've shared, what type of block do I have? (Creative block, burnout, perfectionism, fear of judgment, lost purpose, etc.) What's likely causing it?

2. QUICK WIN: Give me one tiny, zero-pressure piece of content I could create TODAY in under 30 minutes that would get me back in motion. Something I could post without overthinking.

3. MOMENTUM PLAN: Give me a 7-day back-to-creating plan with one action per day — starting ridiculously small and building up gradually.

4. MINDSET RESET: Write me a short, honest pep talk — not toxic positivity, but real talk — about why this slump is temporary and what it means about my creative journey.

5. EMERGENCY IDEA LIST: Give me 10 content ideas in my niche I can create this week without doing any research. Make them simple enough to do without feeling overwhelmed.

6. PERMISSION SLIP: Write me a short "permission slip" — a statement I can re-read whenever I feel stuck — that gives me permission to create imperfectly and shows up anyway.</div>
    <div class="pc-meta"><span class="pc-tag">🧱 Block</span><span class="pc-tag">💪 Motivation</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Creative block is almost always fear in disguise. The cure isn't waiting for inspiration — it's creating something small and terrible and posting it anyway. Motion creates motivation, not the other way around.</div></div>
  </div>

  <div class="prompt-card t-teal">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 02</div><div class="pc-title">Burnout Recovery Plan</div><div class="pc-use">✅ Best for: When you're exhausted, resentful of creating, and questioning everything about your business</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">I'm burned out. Creating content feels like a chore. I'm [exhausted / resentful / questioning everything / going through the motions]. Help me figure out what's happening and how to recover.

How long I've been creating: [TIME]
My posting schedule: [HOW OFTEN]
How long I've felt burned out: [TIME]
What started feeling wrong: [DESCRIBE THE SHIFT — if you can identify it]
What I'm still enjoying (if anything): [ANY PART THAT STILL FEELS OKAY]
What I've tried to fix it: [ANYTHING YOU'VE ALREADY DONE]

Help me build a real burnout recovery plan:

1. BURNOUT ASSESSMENT: Based on what I've shared, what stage of burnout am I likely in? What does this mean about the changes I need to make?

2. IMMEDIATE ACTIONS (this week): What should I do THIS WEEK — specifically around content — to stop digging the hole deeper?

3. WHAT TO ELIMINATE: What can I immediately cut from my content workflow without ruining my business? What am I doing that's draining me most that I don't actually NEED to do?

4. WHAT TO PROTECT: What parts of content creation do I need to protect and preserve? What first made me love this?

5. SUSTAINABLE SCHEDULE: Design a new content schedule for me that is dramatically more sustainable than what I've been doing — while still maintaining enough consistency to keep growing.

6. IDENTITY RECONNECTION: What questions should I ask myself to reconnect with WHY I started and what I want this business to feel like? Write them out as a short journaling exercise.

7. SUPPORT STRUCTURES: What systems, boundaries, or support could prevent this level of burnout in the future?</div>
    <div class="pc-meta"><span class="pc-tag">🔥 Burnout</span><span class="pc-tag">🛡️ Recovery</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Burnout is not a sign you're not cut out for this — it's a sign you've been running on empty for too long. The creators who last decades are the ones who build rest and recovery into their system, not just their schedule.</div></div>
  </div>

  <div class="prompt-card t-teal">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 03</div><div class="pc-title">Comparison Spiral Interrupt</div><div class="pc-use">✅ Best for: When you're deep in comparison mode, watching competitors blow up while you feel stuck</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">I'm in a bad comparison spiral. I keep watching [ANOTHER CREATOR / COMPETITORS IN MY NICHE] grow faster than me and I'm feeling [defeated / jealous / questioning my work / like I should quit].

My situation: [DESCRIBE WHERE YOU ARE — time creating, current size, recent growth/stagnation]
Who I'm comparing myself to: [DESCRIBE THEM — not their name, just their situation]
What specifically is triggering me: [WHAT ARE THEY DOING THAT'S TRIGGERING THE COMPARISON]

Help me interrupt this spiral and get back to my own lane:

1. REALITY CHECK: Help me see what I'm not seeing. What context am I missing about "overnight success" stories? What's probably going on behind the scenes that I'm not comparing myself to?

2. UNFAIR COMPARISON AUDIT: List all the ways my comparison is unfair or incomplete. (Different starting points, different resources, different timelines, what I don't know about them, etc.)

3. MY UNIQUE ADVANTAGE: Based on what I've shared about myself, what do I likely have that my "competitor" doesn't? Help me see what makes me irreplaceable in my niche.

4. DATA REDIRECT: Instead of looking at their metrics, what are MY metrics I should be focused on this week that are fully within my control?

5. HEALTHY COMPETITION REFRAME: How can I shift from comparison (which drains me) to inspiration (which fuels me)? Write me a new mental model for how to think about other successful creators in my space.

6. MY NEXT MOVE: Instead of thinking about them, what's the one thing I should do for MY content this week that would make ME most proud?</div>
    <div class="pc-meta"><span class="pc-tag">🆚 Comparison</span><span class="pc-tag">🧘 Mindset</span><div class="pro-tip"><strong>💡 Pro tip:</strong> The algorithm doesn't reward the people who spend the most time watching competitors — it rewards the people who spend the most time creating. Every minute in comparison mode is a minute not spent building your own lane.</div></div>
  </div>

  <div class="prompt-card t-teal">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 04</div><div class="pc-title">Content Business Vision Board</div><div class="pc-use">✅ Best for: Reconnecting with your big picture when day-to-day hustle has made you lose the plot</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">I want to reconnect with my vision for this creative business. I've been so focused on the day-to-day that I've lost sight of the bigger picture.

My niche: [YOUR NICHE]
How long I've been creating: [TIME]
Current situation: [WHERE YOU ARE NOW — platform sizes, income, time spent]
Original "why": [WHY YOU STARTED — if you remember]
What you want your life to look like: [DESCRIBE YOUR IDEAL DAILY LIFE — work, freedom, income, impact]
What you're most afraid of: [YOUR BIGGEST FEAR ABOUT THIS PATH]

Help me build a clear, motivating vision for my content business:

1. CRYSTAL CLEAR VISION: Based on what I've shared, articulate my 3-year vision in vivid, concrete detail. What does my business look like? What does my day look like? What impact am I having?

2. THE WHY BEHIND THE WHY: What is the deeper reason behind my goals? What's the real thing I'm chasing — freedom, impact, legacy, security, expression?

3. MILESTONES MAP: What are the 5 key milestones between where I am now and my 3-year vision? Make them specific and sequential.

4. NORTH STAR METRIC: Based on my goals, what is the ONE number I should be focused on most right now? (Not followers — the number that most predicts whether I reach my vision.)

5. DAILY ALIGNMENT QUESTION: Write me one powerful question I should ask myself every morning to make sure my daily actions align with my big vision.

6. DECISION FILTER: Based on my vision, write me a 3-question filter I can apply to every opportunity, collaboration, and content idea — to decide if it's aligned with where I'm going.</div>
    <div class="pc-meta"><span class="pc-tag">🌟 Vision</span><span class="pc-tag">🧭 Direction</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Revisit your vision every 90 days. What felt exciting 6 months ago may have evolved — and that's okay. A clear vision isn't a cage, it's a compass. Update it as you grow.</div></div>
  </div>

  <div class="prompt-card t-teal">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 05</div><div class="pc-title">Fear of Posting Overcome Framework</div><div class="pc-use">✅ Best for: Creators who second-guess every post, overanalyze before hitting publish, or constantly delete drafts</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">I struggle with the fear of posting. I create content, but then I overthink it, second-guess it, or delete it before posting. Sometimes I sit on drafts for days.

What's happening for me: [DESCRIBE YOUR SPECIFIC FEAR — judgment, looking stupid, not being good enough, worried about haters, scared of the algorithm, etc.]
How long this has been a problem: [TIME]
The last time I almost posted but didn't: [DESCRIBE IT — what happened and why you held back]
What I worry people will think: [YOUR SPECIFIC FEAR ABOUT AUDIENCE REACTION]

Help me build a personal framework for overcoming this:

1. FEAR DIAGNOSIS: What specific type of fear is this? Is it imposter syndrome, perfectionism, fear of judgment, fear of success, fear of failure? What is this fear protecting me from?

2. THE COST OF NOT POSTING: Help me see, clearly and concretely, what my fear of posting is actually costing me over time. Make this real — not abstract.

3. WORST CASE REALITY CHECK: Walk me through the realistic worst case if I post something that flops or gets criticism. What would actually happen? Is it survivable?

4. BEST CASE OPPORTUNITY: Walk me through the realistic best case if this post connects. What could it lead to?

5. MY PERSONAL POSTING RULES: Write me 5 personal rules or mantras that I can refer back to every time I'm about to talk myself out of posting.

6. THE 10-MINUTE RULE: Give me a specific ritual or process I can follow in the 10 minutes before I post — to move from hesitation to hitting publish with confidence.

7. POST-PUBLISH PROTOCOL: What should I do AFTER I post to avoid obsessively checking metrics and spiraling?</div>
    <div class="pc-meta"><span class="pc-tag">😨 Fear</span><span class="pc-tag">✅ Confidence</span><div class="pro-tip"><strong>💡 Pro tip:</strong> The post you're most scared to share is often the one that resonates most. Vulnerability and authenticity are magnets — your fear is a signal that you're about to say something real. Post it anyway.</div></div>
  </div>

  <div class="prompt-card t-teal">
    <div class="pc-header"><div class="pc-left"><div class="pc-num">PROMPT 06</div><div class="pc-title">Quarterly Creator Review</div><div class="pc-use">✅ Best for: Doing a deep, honest audit of your last 90 days as a creator so you can improve in the next quarter</div></div><button class="copy-btn" onclick="copyPrompt(this)">📋 Copy</button></div>
    <div class="prompt-box">I want to do a thorough quarterly review of my content business. Here's what happened in the last 90 days:

Platforms and growth: [FOLLOWER COUNTS — start vs. end of quarter]
Email list: [START VS. END]
Revenue generated: [$AMOUNT — from what sources]
Content output: [HOW MANY PIECES ACROSS WHICH PLATFORMS]
Best performing content: [DESCRIBE YOUR TOP 3 PERFORMERS]
Worst performing content: [DESCRIBE YOUR BOTTOM 3]
Goals I set at the start of this quarter: [LIST THEM]
Goals I actually hit: [WHICH ONES]
What I'm most proud of: [YOUR WIN]
What felt hardest: [YOUR STRUGGLE]

Conduct a full quarterly review for me:

1. WINS ANALYSIS: What went right this quarter, and WHY? What can I deliberately repeat next quarter?

2. FAILURES ANALYSIS: What didn't work, and what's the real reason? What's the lesson I need to carry forward?

3. GOAL AUDIT: For every goal I missed, was it because of lack of effort, wrong strategy, or wrong goal? What should I do differently?

4. CONTENT PATTERN ANALYSIS: Based on my best and worst performers, what patterns do you see? What should I do more of, less of, or differently?

5. NEXT QUARTER GOALS: Set 3 specific, measurable, realistic goals for next quarter based on this review. Make them challenging but achievable.

6. ONE THING: If I could only change ONE thing about how I create content next quarter, what should it be based on this review?</div>
    <div class="pc-meta"><span class="pc-tag">📊 Review</span><span class="pc-tag">🔍 Audit</span><div class="pro-tip"><strong>💡 Pro tip:</strong> Do this review every 90 days without fail. Most creators never stop to reflect — they just keep doing what they've always done. The quarterly review is the difference between working hard and working smart.</div></div>
  </div>

</div>

<!-- ============================================================ -->
<!-- CLOSING CTA SECTION -->
<!-- ============================================================ -->
<div style="max-width:860px;margin:60px auto 0;padding:60px 40px;background:linear-gradient(135deg,#1a1a2e 0%,#16213e 50%,#0f3460 100%);border-radius:24px;text-align:center;box-shadow:0 20px 60px rgba(0,0,0,0.4);">
  <div style="font-size:3rem;margin-bottom:16px;">🚀</div>
  <h2 style="font-size:2rem;font-weight:800;color:#fff;margin:0 0 16px;line-height:1.2;">You Now Have 110+ Prompts.<br>What You Do Next Is Everything.</h2>
  <p style="color:#a0aec0;font-size:1.1rem;max-width:600px;margin:0 auto 32px;line-height:1.7;">The creators who transform their content don't hoard tools — they USE them. Pick ONE prompt from this pack right now and create something with it today. Not tomorrow. Today.</p>
  <div style="display:flex;gap:16px;justify-content:center;flex-wrap:wrap;margin-bottom:40px;">
    <div style="background:rgba(255,255,255,0.1);border:1px solid rgba(255,255,255,0.2);border-radius:12px;padding:20px 28px;color:#fff;">
      <div style="font-size:2rem;font-weight:800;">110+</div>
      <div style="font-size:0.85rem;color:#a0aec0;margin-top:4px;">AI Prompts</div>
    </div>
    <div style="background:rgba(255,255,255,0.1);border:1px solid rgba(255,255,255,0.2);border-radius:12px;padding:20px 28px;color:#fff;">
      <div style="font-size:2rem;font-weight:800;">11</div>
      <div style="font-size:0.85rem;color:#a0aec0;margin-top:4px;">Categories</div>
    </div>
    <div style="background:rgba(255,255,255,0.1);border:1px solid rgba(255,255,255,0.2);border-radius:12px;padding:20px 28px;color:#fff;">
      <div style="font-size:2rem;font-weight:800;">∞</div>
      <div style="font-size:0.85rem;color:#a0aec0;margin-top:4px;">Content Ideas</div>
    </div>
  </div>
  <p style="color:#718096;font-size:0.9rem;font-style:italic;">"The best time to use a prompt was yesterday. The second best time is right now."</p>
</div>

<!-- toast notification -->
<div id="toast" style="position:fixed;bottom:32px;right:32px;background:#1a202c;color:#fff;padding:14px 22px;border-radius:12px;font-size:0.9rem;font-weight:600;opacity:0;transform:translateY(20px);transition:all 0.3s ease;z-index:9999;box-shadow:0 8px 32px rgba(0,0,0,0.3);display:flex;align-items:center;gap:10px;">
  <span style="font-size:1.2rem;">✅</span> Prompt copied to clipboard!
</div>

</div><!-- end .container -->
</main>

<footer style="text-align:center;padding:40px 20px;color:#718096;font-size:0.85rem;">
  <p>Your AI Prompt Pack — Built for Digital Content Creators Who Mean Business 💫</p>
</footer>

<script>
function copyPrompt(btn) {
  const card = btn.closest('.prompt-card');
  const box = card.querySelector('.prompt-box');
  const text = box ? box.innerText : '';

  if (!text) return;

  if (navigator.clipboard && navigator.clipboard.writeText) {
    navigator.clipboard.writeText(text).then(function() {
      showToast();
      flashBtn(btn);
    }).catch(function() {
      fallbackCopy(text, btn);
    });
  } else {
    fallbackCopy(text, btn);
  }
}

function fallbackCopy(text, btn) {
  const ta = document.createElement('textarea');
  ta.value = text;
  ta.style.position = 'fixed';
  ta.style.opacity = '0';
  document.body.appendChild(ta);
  ta.focus();
  ta.select();
  try {
    document.execCommand('copy');
    showToast();
    flashBtn(btn);
  } catch(e) {
    alert('Copy failed. Please select and copy manually.');
  }
  document.body.removeChild(ta);
}

function flashBtn(btn) {
  const orig = btn.innerHTML;
  btn.innerHTML = '✅ Copied!';
  btn.style.background = '#48bb78';
  btn.style.borderColor = '#48bb78';
  setTimeout(function() {
    btn.innerHTML = orig;
    btn.style.background = '';
    btn.style.borderColor = '';
  }, 2000);
}

function showToast() {
  const toast = document.getElementById('toast');
  toast.style.opacity = '1';
  toast.style.transform = 'translateY(0)';
  setTimeout(function() {
    toast.style.opacity = '0';
    toast.style.transform = 'translateY(20px)';
  }, 2500);
}

// smooth scroll for any anchor links
document.querySelectorAll('a[href^="#"]').forEach(function(a) {
  a.addEventListener('click', function(e) {
    const target = document.querySelector(this.getAttribute('href'));
    if (target) {
      e.preventDefault();
      target.scrollIntoView({ behavior: 'smooth', block: 'start' });
    }
  });
});
</script>

</body>
</html>
