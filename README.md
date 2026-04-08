
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>AI Prompt Pack — Template Vault</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Nunito:wght@400;600;700;800;900&display=swap');
    * { box-sizing: border-box; margin: 0; padding: 0; }
    body { font-family: 'Nunito', sans-serif; background: #07050f; color: #e2e8f0; padding: 0 0 80px 0; }

    /* ═══ GALAXY HERO ═══ */
    .hero {
      background: radial-gradient(ellipse at 20% 50%, #3b0764 0%, transparent 60%),
                  radial-gradient(ellipse at 80% 20%, #1e1b4b 0%, transparent 50%),
                  radial-gradient(ellipse at 60% 80%, #4c0519 0%, transparent 50%),
                  linear-gradient(135deg, #0f0c29 0%, #1a0533 40%, #24043d 70%, #0d0221 100%);
      padding: 60px 40px 80px 40px;
      position: relative; overflow: hidden;
      border-radius: 0 0 50px 50px; text-align: center;
    }
    /* Stars */
    .hero::before {
      content:'';
      position:absolute; inset:0;
      background-image:
        radial-gradient(1px 1px at 10% 15%, rgba(255,255,255,0.9) 0%, transparent 100%),
        radial-gradient(1px 1px at 25% 35%, rgba(255,255,255,0.7) 0%, transparent 100%),
        radial-gradient(1.5px 1.5px at 40% 10%, rgba(255,255,255,0.8) 0%, transparent 100%),
        radial-gradient(1px 1px at 55% 25%, rgba(255,255,255,0.6) 0%, transparent 100%),
        radial-gradient(2px 2px at 70% 5%, rgba(255,255,255,0.9) 0%, transparent 100%),
        radial-gradient(1px 1px at 80% 40%, rgba(255,255,255,0.7) 0%, transparent 100%),
        radial-gradient(1.5px 1.5px at 90% 20%, rgba(255,255,255,0.8) 0%, transparent 100%),
        radial-gradient(1px 1px at 15% 60%, rgba(255,255,255,0.5) 0%, transparent 100%),
        radial-gradient(1px 1px at 35% 75%, rgba(255,255,255,0.6) 0%, transparent 100%),
        radial-gradient(2px 2px at 50% 55%, rgba(255,255,255,0.8) 0%, transparent 100%),
        radial-gradient(1px 1px at 65% 70%, rgba(255,255,255,0.5) 0%, transparent 100%),
        radial-gradient(1.5px 1.5px at 75% 85%, rgba(255,255,255,0.7) 0%, transparent 100%),
        radial-gradient(1px 1px at 88% 65%, rgba(255,255,255,0.6) 0%, transparent 100%),
        radial-gradient(1px 1px at 5% 85%, rgba(255,255,255,0.8) 0%, transparent 100%),
        radial-gradient(2px 2px at 95% 90%, rgba(255,255,255,0.9) 0%, transparent 100%),
        radial-gradient(1px 1px at 30% 90%, rgba(255,255,255,0.5) 0%, transparent 100%),
        radial-gradient(1.5px 1.5px at 60% 95%, rgba(255,255,255,0.6) 0%, transparent 100%);
    }
    /* Nebula glow orbs */
    .hero::after {
      content:'';
      position:absolute;
      width:500px; height:500px;
      background: radial-gradient(circle, rgba(168,85,247,0.15) 0%, transparent 70%);
      border-radius:50%;
      top:-100px; left:-100px;
      pointer-events:none;
    }
    .nebula-orb {
      position:absolute;
      width:400px; height:400px;
      background: radial-gradient(circle, rgba(244,63,94,0.12) 0%, transparent 70%);
      border-radius:50%;
      bottom:-80px; right:-80px;
      pointer-events:none;
    }
    .nebula-orb2 {
      position:absolute;
      width:300px; height:300px;
      background: radial-gradient(circle, rgba(99,102,241,0.10) 0%, transparent 70%);
      border-radius:50%;
      top:40%; left:40%;
      transform:translate(-50%,-50%);
      pointer-events:none;
    }
    .hero-badge {
      display:inline-block;
      background: linear-gradient(135deg, rgba(168,85,247,0.3), rgba(244,63,94,0.3));
      border: 1px solid rgba(168,85,247,0.5);
      color:#e9d5ff;
      font-size:11px; font-weight:800; letter-spacing:2.5px; text-transform:uppercase;
      padding:8px 24px; border-radius:20px; margin-bottom:22px;
      backdrop-filter: blur(10px);
    }
    .hero-icon { font-size:72px; display:block; margin-bottom:14px; filter:drop-shadow(0 0 20px rgba(168,85,247,0.8)); }
    .hero h1 { font-size:52px; font-weight:900; line-height:1.05; margin-bottom:12px;
      background: linear-gradient(135deg, #f9a8d4 0%, #c084fc 40%, #818cf8 70%, #67e8f9 100%);
      -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;
    }
    .hero h1 span { display:block; font-size:21px; font-weight:700;
      background: linear-gradient(90deg, #e2e8f0, #c084fc);
      -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;
      margin-top:12px;
    }
    .hero p { font-size:15.5px; font-weight:600; color:rgba(226,232,240,0.85); max-width:620px; margin:18px auto 28px; line-height:1.8; }
    .hero-pills { display:flex; justify-content:center; gap:10px; flex-wrap:wrap; margin-bottom:18px; }
    .hero-pill {
      background: rgba(168,85,247,0.15);
      border: 1px solid rgba(168,85,247,0.35);
      color:#e9d5ff; font-size:12px; font-weight:700; padding:6px 16px; border-radius:20px;
      backdrop-filter:blur(6px);
    }
    .hero-count {
      display:inline-block;
      background: linear-gradient(135deg, rgba(168,85,247,0.2), rgba(244,63,94,0.2));
      border: 1px solid rgba(168,85,247,0.4);
      color:#e9d5ff; font-size:13px; font-weight:800; padding:10px 30px; border-radius:24px;
      backdrop-filter:blur(10px);
      text-shadow: 0 0 20px rgba(168,85,247,0.5);
    }

    /* ═══ CONTENT WRAPPER ═══ */
    .content { max-width:860px; margin:0 auto; padding:0 26px; }

    /* BACK LINK */
    .back-link { display:inline-flex; align-items:center; gap:8px; font-size:13px; font-weight:800; color:#c084fc; text-decoration:none; margin:30px 0 0; padding:9px 20px; background:rgba(168,85,247,0.1); border-radius:20px; border:1px solid rgba(168,85,247,0.3); }
    .back-link:hover { background:rgba(168,85,247,0.2); }

    /* INTRO BLOCK */
    .intro-block {
      border-left:4px solid #a855f7;
      padding:22px 26px; margin:36px 0 34px;
      background: linear-gradient(135deg, rgba(168,85,247,0.08), rgba(99,102,241,0.05));
      border-radius:0 18px 18px 0;
      font-size:15px; line-height:1.8; color:#cbd5e1;
      box-shadow:0 2px 20px rgba(168,85,247,0.1);
    }
    .intro-block strong { color:#c084fc; }

    /* SECTION HEADING */
    .section-heading { font-size:22px; font-weight:900; margin:48px 0 22px;
      background: linear-gradient(90deg, #f9a8d4, #c084fc);
      -webkit-background-clip:text; -webkit-text-fill-color:transparent; background-clip:text;
    }

    /* HOW TO USE STEPS */
    .steps-grid { display:grid; grid-template-columns:1fr 1fr 1fr 1fr; gap:14px; margin-bottom:30px; }
    .step-card {
      background: linear-gradient(135deg, rgba(168,85,247,0.08), rgba(99,102,241,0.05));
      border-radius:18px; padding:20px 16px; text-align:center;
      border-top:3px solid #a855f7;
      border: 1px solid rgba(168,85,247,0.2);
      border-top:3px solid #a855f7;
    }
    .step-num { display:inline-block; background:rgba(168,85,247,0.2); color:#c084fc; font-size:10px; font-weight:800; letter-spacing:1px; padding:4px 12px; border-radius:20px; margin-bottom:10px; }
    .step-card h4 { font-size:14px; font-weight:900; color:#e9d5ff; margin-bottom:7px; }
    .step-card p { font-size:12.5px; color:#94a3b8; line-height:1.6; }

    /* WARNING BANNER */
    .warning-banner {
      background: linear-gradient(135deg, rgba(244,63,94,0.1), rgba(168,85,247,0.08));
      border:1px solid rgba(244,63,94,0.3);
      border-radius:16px; padding:18px 24px; text-align:center;
      font-size:14px; font-weight:700; color:#fda4af; margin:0 0 38px; line-height:1.65;
    }


    /* ═══ STATS BAR ═══ */
    .stats-bar { display:flex; justify-content:center; flex-wrap:wrap; background:rgba(10,8,25,0.8); border-radius:18px; border:1px solid rgba(168,85,247,0.15); margin-bottom:32px; overflow:hidden; }
    .stat-item { padding:18px 32px; text-align:center; border-right:1px solid rgba(255,255,255,0.06); flex:1; min-width:120px; }
    .stat-item:last-child { border-right:none; }
    .stat-num { font-size:26px; font-weight:900; background:linear-gradient(135deg,#a855f7,#ec4899); -webkit-background-clip:text; -webkit-text-fill-color:transparent; background-clip:text; line-height:1; }
    .stat-lbl { font-size:10px; font-weight:700; color:#475569; text-transform:uppercase; letter-spacing:1.5px; margin-top:4px; }

    /* ═══ SKILL LEVEL BADGES ═══ */
    .tbadge-beginner { background:rgba(59,130,246,0.15); color:#60a5fa; border:1px solid rgba(59,130,246,0.3); }
    .tbadge-inter    { background:rgba(249,115,22,0.15);  color:#fb923c; border:1px solid rgba(249,115,22,0.3); }
    .tbadge-advanced { background:rgba(239,68,68,0.15);   color:#f87171; border:1px solid rgba(239,68,68,0.3); }

    /* ═══ WORKFLOW SECTION ═══ */
    .workflow-section { background:linear-gradient(135deg,#1a0a3d 0%,#2d0a4e 50%,#1a0a3d 100%); border-radius:24px; padding:44px 32px; margin-bottom:36px; border:1px solid rgba(168,85,247,0.2); position:relative; overflow:hidden; }
    .workflow-section::before { content:''; position:absolute; inset:0; background:radial-gradient(ellipse at 50% 50%,rgba(168,85,247,0.1) 0%,transparent 70%); pointer-events:none; }
    .workflow-title { text-align:center; font-size:20px; font-weight:900; margin-bottom:6px; background:linear-gradient(135deg,#fff 0%,#c084fc 50%,#f472b6 100%); -webkit-background-clip:text; -webkit-text-fill-color:transparent; background-clip:text; }
    .workflow-sub { text-align:center; font-size:12.5px; color:rgba(255,255,255,0.5); margin-bottom:36px; }
    .workflow-track { display:flex; align-items:flex-start; justify-content:center; flex-wrap:wrap; gap:6px; }
    .wf-step { display:flex; flex-direction:column; align-items:center; text-align:center; width:140px; }
    .wf-circle { width:68px; height:68px; border-radius:50%; background:rgba(255,255,255,0.05); border:1.5px solid rgba(168,85,247,0.35); display:flex; flex-direction:column; align-items:center; justify-content:center; margin-bottom:12px; }
    .wf-num { font-size:9px; font-weight:800; color:#a855f7; letter-spacing:1px; text-transform:uppercase; }
    .wf-icon { font-size:1.5rem; line-height:1; }
    .wf-label { font-size:12px; font-weight:800; color:#f1f5f9; margin-bottom:3px; }
    .wf-tool  { font-size:10.5px; color:rgba(255,255,255,0.5); line-height:1.5; }
    .wf-arrow { color:rgba(168,85,247,0.6); font-size:1.6rem; margin-top:20px; flex-shrink:0; align-self:flex-start; }
    .ws1 .wf-circle { box-shadow:0 0 18px rgba(168,85,247,0.4); border-color:rgba(168,85,247,0.6); }
    .ws2 .wf-circle { box-shadow:0 0 18px rgba(96,165,250,0.35); border-color:rgba(96,165,250,0.5); }
    .ws3 .wf-circle { box-shadow:0 0 18px rgba(251,191,36,0.35); border-color:rgba(251,191,36,0.5); }
    .ws4 .wf-circle { box-shadow:0 0 18px rgba(244,114,182,0.35); border-color:rgba(244,114,182,0.5); }
    .ws5 .wf-circle { box-shadow:0 0 18px rgba(52,211,153,0.35); border-color:rgba(52,211,153,0.5); }

    /* ═══ LEGEND ═══ */
    .legend-section { background:rgba(10,8,25,0.7); border-radius:20px; padding:32px; margin-bottom:36px; border:1px solid rgba(255,255,255,0.06); }
    .legend-title { font-size:15px; font-weight:900; color:#e2e8f0; margin-bottom:6px; }
    .legend-desc { font-size:12px; color:#475569; margin-bottom:20px; }
    .legend-cards { display:flex; flex-wrap:wrap; gap:12px; }
    .legend-card { display:flex; align-items:center; gap:12px; padding:14px 18px; border-radius:12px; border:1px solid; flex:1; min-width:170px; background:rgba(15,10,30,0.6); }
    .lc-green  { border-color:rgba(74,222,128,0.25); }
    .lc-blue   { border-color:rgba(96,165,250,0.25); }
    .lc-orange { border-color:rgba(251,146,60,0.25); }
    .lc-red    { border-color:rgba(248,113,113,0.25); }
    .legend-dot { width:14px; height:14px; border-radius:50%; flex-shrink:0; }
    .ld-green  { background:#4ade80; box-shadow:0 0 8px rgba(74,222,128,0.6); }
    .ld-blue   { background:#60a5fa; box-shadow:0 0 8px rgba(96,165,250,0.6); }
    .ld-orange { background:#fb923c; box-shadow:0 0 8px rgba(251,146,60,0.6); }
    .ld-red    { background:#f87171; box-shadow:0 0 8px rgba(248,113,113,0.6); }
    .legend-tag-label { font-size:10px; font-weight:800; text-transform:uppercase; letter-spacing:1px; margin-bottom:2px; }
    .lc-green .legend-tag-label  { color:#4ade80; }
    .lc-blue .legend-tag-label   { color:#60a5fa; }
    .lc-orange .legend-tag-label { color:#fb923c; }
    .lc-red .legend-tag-label    { color:#f87171; }
    .legend-meaning { font-size:11px; color:#475569; line-height:1.4; }
    @media(max-width:600px){ .wf-arrow{display:none;} .legend-card{min-width:100%;} .stat-item{min-width:50%;} }

    /* ═══ GALAXY AI TOOLS DIRECTORY ═══ */
    .tools-universe { margin:0 0 48px; }
    .tools-universe > h3 { font-size:20px; font-weight:900; margin-bottom:8px;
      background: linear-gradient(90deg, #67e8f9, #a78bfa);
      -webkit-background-clip:text; -webkit-text-fill-color:transparent; background-clip:text;
    }
    .tools-universe > p { font-size:13.5px; color:#94a3b8; font-weight:600; margin-bottom:22px; line-height:1.6; }

    /* Category label for tool groups */
    .tool-category-label {
      font-size:10px; font-weight:800; letter-spacing:2px; text-transform:uppercase;
      color:#7c3aed; margin:24px 0 12px;
      display:flex; align-items:center; gap:10px;
    }
    .tool-category-label::after { content:''; flex:1; height:1px; background:rgba(124,58,237,0.25); }

    .tools-grid { display:grid; grid-template-columns:1fr 1fr 1fr; gap:12px; margin-bottom:6px; }
    .tool-card {
      background: rgba(15,10,30,0.8);
      border-radius:16px; padding:16px 18px;
      display:flex; align-items:flex-start; gap:14px;
      border:1px solid rgba(255,255,255,0.06);
      transition: border-color 0.2s, box-shadow 0.2s;
    }
    .tool-card:hover { border-color:rgba(168,85,247,0.4); box-shadow:0 0 20px rgba(168,85,247,0.1); }
    .tool-glow { width:12px; height:12px; border-radius:50%; flex-shrink:0; margin-top:4px; box-shadow: 0 0 8px currentColor; }
    .tool-info { flex:1; }
    .tool-name { font-size:13.5px; font-weight:900; color:#e2e8f0; }
    .tool-name a { color:#e2e8f0; text-decoration:none; border-bottom:1px dashed rgba(168,85,247,0.4); transition:color 0.2s, border-color 0.2s; }
    .tool-name a:hover { color:#c084fc; border-bottom-color:rgba(168,85,247,0.9); }
    .tool-desc { font-size:11.5px; font-weight:600; color:#64748b; margin-top:3px; line-height:1.5; }
    .tool-badges { display:flex; gap:6px; margin-top:7px; flex-wrap:wrap; }
    .tbadge { font-size:10px; font-weight:800; padding:2px 8px; border-radius:10px; }
    .tbadge-free  { background:rgba(16,185,129,0.15); color:#6ee7b7; border:1px solid rgba(16,185,129,0.25); }
    .tbadge-paid  { background:rgba(245,158,11,0.12); color:#fcd34d; border:1px solid rgba(245,158,11,0.2); }
    .tbadge-new   { background:rgba(168,85,247,0.15); color:#c084fc; border:1px solid rgba(168,85,247,0.3); }
    .tbadge-hot   { background:rgba(244,63,94,0.15); color:#fda4af; border:1px solid rgba(244,63,94,0.3); }
    .tbadge-galaxy { background:linear-gradient(90deg,rgba(168,85,247,0.2),rgba(99,102,241,0.2)); color:#a5b4fc; border:1px solid rgba(99,102,241,0.3); }

    /* ═══ HOW TO USE EACH AI ═══ */
    .ai-guide-grid { display:grid; grid-template-columns:1fr 1fr; gap:18px; margin-bottom:36px; }
    .ai-guide-card {
      background: rgba(15,10,30,0.85);
      border-radius:20px; padding:22px 24px;
      border:1px solid rgba(255,255,255,0.07);
      transition: border-color 0.2s, box-shadow 0.2s;
    }
    .ai-guide-card:hover { border-color:rgba(168,85,247,0.35); box-shadow:0 0 24px rgba(168,85,247,0.08); }
    .ai-guide-header { display:flex; align-items:center; gap:12px; margin-bottom:14px; }
    .ai-guide-dot { width:14px; height:14px; border-radius:50%; flex-shrink:0; box-shadow:0 0 8px currentColor; }
    .ai-guide-title { font-size:15px; font-weight:900; color:#e2e8f0; }
    .ai-guide-title a { color:#e2e8f0; text-decoration:none; border-bottom:1px dashed rgba(168,85,247,0.4); transition:color 0.2s; }
    .ai-guide-title a:hover { color:#c084fc; }
    .ai-guide-tagline { font-size:11px; font-weight:700; color:#64748b; margin-top:2px; }
    .ai-guide-steps { list-style:none; padding:0; margin:0; }
    .ai-guide-steps li {
      font-size:12.5px; font-weight:600; color:#94a3b8;
      padding:7px 0 7px 22px; border-bottom:1px solid rgba(255,255,255,0.04);
      position:relative; line-height:1.6;
    }
    .ai-guide-steps li:last-child { border-bottom:none; }
    .ai-guide-steps li::before { content:attr(data-num); position:absolute; left:0; color:#a855f7; font-weight:900; font-size:11px; top:8px; }
    .ai-guide-tip {
      margin-top:12px; padding:10px 14px; border-radius:10px;
      background:rgba(168,85,247,0.07); border-left:3px solid #a855f7;
      font-size:11.5px; font-weight:700; color:#c084fc; line-height:1.6;
    }
    .ai-guide-tip span { color:#94a3b8; font-weight:600; }
    @media(max-width:700px){ .ai-guide-grid { grid-template-columns:1fr; } }

    /* MISTAKES SECTION */
    .mistakes-grid { display:grid; grid-template-columns:1fr 1fr; gap:14px; margin-bottom:36px; }
    .mistake-card { border-radius:18px; padding:22px; border:1px solid rgba(255,255,255,0.06); }
    .mistake-card .mk-icon { font-size:28px; margin-bottom:10px; display:block; }
    .mistake-card h4 { font-size:14px; font-weight:900; margin-bottom:8px; }
    .mistake-card p { font-size:13px; color:#94a3b8; line-height:1.65; }
    .mistake-card.bad  { background:rgba(244,63,94,0.06); border-top:3px solid #f43f5e; }
    .mistake-card.bad h4 { color:#fda4af; }
    .mistake-card.good { background:rgba(16,185,129,0.06); border-top:3px solid #10b981; }
    .mistake-card.good h4 { color:#6ee7b7; }

    /* ═══ PROMPT CARDS ═══ */
    .prompt-card {
      background: rgba(15,10,30,0.9);
      border-radius:26px; margin-bottom:30px;
      box-shadow: 0 8px 40px rgba(0,0,0,0.4);
      overflow: hidden;
      border: 1px solid rgba(255,255,255,0.06);
      border-left: 5px solid #a855f7;
    }
    .prompt-header { padding:26px 28px 18px 28px; display:flex; align-items:flex-start; gap:18px; }
    .prompt-emoji-box {
      width:60px; height:60px; border-radius:18px;
      background: rgba(168,85,247,0.12);
      display:flex; align-items:center; justify-content:center;
      font-size:28px; flex-shrink:0;
      border:1px solid rgba(168,85,247,0.2);
    }
    .prompt-header-text { flex:1; }
    .prompt-num { font-size:10px; font-weight:800; letter-spacing:1.5px; background:rgba(168,85,247,0.2); color:#c084fc; padding:4px 12px; border-radius:20px; display:inline-block; margin-bottom:9px; border:1px solid rgba(168,85,247,0.3); }
    .prompt-card h2 { font-size:20px; font-weight:900; color:#f1f5f9; margin-bottom:4px; }
    .prompt-tagline { font-size:13px; font-weight:700; color:#475569; }
    .prompt-body { padding:0 28px 28px 28px; }

    .what-it-does { font-size:14px; color:#94a3b8; line-height:1.8; margin-bottom:18px; padding:16px 18px; border-radius:14px; border-left:3px solid #a855f7; background:rgba(168,85,247,0.06); }

    .when-to-use { margin-bottom:20px; }
    .when-to-use h4 { font-size:10px; font-weight:800; letter-spacing:1.5px; text-transform:uppercase; color:#475569; margin-bottom:10px; }
    .use-tags { display:flex; flex-wrap:wrap; gap:8px; }
    .use-tag { font-size:11.5px; font-weight:700; padding:5px 14px; border-radius:20px; background:rgba(255,255,255,0.04); color:#94a3b8; border:1px solid rgba(255,255,255,0.08); }

    .examples-label { font-size:10px; font-weight:800; letter-spacing:1.5px; text-transform:uppercase; color:#334155; margin-bottom:12px; margin-top:18px; }

    .example-prompt {
      background: #020617;
      border-radius:16px; padding:20px 22px; margin-bottom:14px; position:relative;
      border:1px solid rgba(255,255,255,0.05);
      box-shadow: inset 0 1px 0 rgba(255,255,255,0.04);
    }
    .example-prompt p { font-size:13px; color:#94a3b8; line-height:1.75; font-family:'Courier New',monospace; font-weight:600; }
    .example-prompt .placeholder { color:#f9a8d4; font-style:italic; }
    .example-prompt .instruction  { color:#86efac; }
    .copy-tag { position:absolute; top:12px; right:14px; background:rgba(168,85,247,0.2); color:#c084fc; font-size:10px; font-weight:800; padding:3px 10px; border-radius:10px; letter-spacing:.5px; border:1px solid rgba(168,85,247,0.3); }
    .prompt-type-tag { position:absolute; top:12px; right:14px; font-size:10px; font-weight:800; padding:3px 10px; border-radius:10px; }
    .tag-chatgpt   { background:rgba(16,163,127,0.2);  color:#6ee7b7; }
    .tag-midj      { background:rgba(245,158,11,0.2);  color:#fcd34d; }
    .tag-ideogram  { background:rgba(99,102,241,0.2);   color:#a5b4fc; }
    .tag-perplexity{ background:rgba(14,165,233,0.2);  color:#7dd3fc; }
    .tag-any       { background:rgba(168,85,247,0.2);   color:#c084fc; }
    .tag-galaxy    { background:linear-gradient(90deg,rgba(168,85,247,0.25),rgba(99,102,241,0.25)); color:#a5b4fc; }

    .result-block { background:rgba(255,255,255,0.02); border-radius:14px; padding:16px 20px; margin-bottom:14px; border:1.5px dashed rgba(255,255,255,0.08); }
    .result-block .result-label { font-size:10px; font-weight:800; letter-spacing:1px; color:#334155; text-transform:uppercase; margin-bottom:8px; }
    .result-block p { font-size:13px; color:#64748b; line-height:1.7; font-weight:600; font-style:italic; }

    .pro-tip   { background:rgba(168,85,247,0.07); border-radius:14px; padding:15px 18px; font-size:13.5px; font-weight:600; color:#c084fc; border-left:3px solid #a855f7; margin-bottom:10px; line-height:1.65; }
    .avoid-block { background:rgba(244,63,94,0.06); border-radius:14px; padding:15px 18px; font-size:13.5px; font-weight:600; color:#fda4af; border-left:3px solid #f43f5e; margin-bottom:8px; line-height:1.65; }

    .card-divider { height:1px; background:linear-gradient(90deg,transparent,rgba(168,85,247,0.3),transparent); margin:10px 0 22px; }

    /* Color variants per category */
    .pc-content  { border-left-color:#f43f5e; }
    .pc-hook     { border-left-color:#ec4899; }
    .pc-caption  { border-left-color:#a855f7; }
    .pc-script   { border-left-color:#8b5cf6; }
    .pc-visual   { border-left-color:#f59e0b; }
    .pc-research { border-left-color:#0ea5e9; }
    .pc-offer    { border-left-color:#10b981; }
    .pc-email    { border-left-color:#f97316; }

    .pc-content  .prompt-num { background:rgba(244,63,94,0.2); color:#fda4af; border-color:rgba(244,63,94,0.3); }
    .pc-hook     .prompt-num { background:rgba(236,72,153,0.2); color:#f9a8d4; border-color:rgba(236,72,153,0.3); }
    .pc-caption  .prompt-num { background:rgba(168,85,247,0.2); color:#c084fc; border-color:rgba(168,85,247,0.3); }
    .pc-script   .prompt-num { background:rgba(139,92,246,0.2); color:#a78bfa; border-color:rgba(139,92,246,0.3); }
    .pc-visual   .prompt-num { background:rgba(245,158,11,0.2); color:#fcd34d; border-color:rgba(245,158,11,0.3); }
    .pc-research .prompt-num { background:rgba(14,165,233,0.2); color:#7dd3fc; border-color:rgba(14,165,233,0.3); }
    .pc-offer    .prompt-num { background:rgba(16,185,129,0.2); color:#6ee7b7; border-color:rgba(16,185,129,0.3); }
    .pc-email    .prompt-num { background:rgba(249,115,22,0.2); color:#fdba74; border-color:rgba(249,115,22,0.3); }

    .pc-content  .what-it-does { border-left-color:#f43f5e; background:rgba(244,63,94,0.05); }
    .pc-hook     .what-it-does { border-left-color:#ec4899; background:rgba(236,72,153,0.05); }
    .pc-caption  .what-it-does { border-left-color:#a855f7; background:rgba(168,85,247,0.05); }
    .pc-script   .what-it-does { border-left-color:#8b5cf6; background:rgba(139,92,246,0.05); }
    .pc-visual   .what-it-does { border-left-color:#f59e0b; background:rgba(245,158,11,0.05); }
    .pc-research .what-it-does { border-left-color:#0ea5e9; background:rgba(14,165,233,0.05); }
    .pc-offer    .what-it-does { border-left-color:#10b981; background:rgba(16,185,129,0.05); }
    .pc-email    .what-it-does { border-left-color:#f97316; background:rgba(249,115,22,0.05); }

    .pc-content  .prompt-emoji-box { background:rgba(244,63,94,0.1); border-color:rgba(244,63,94,0.2); }
    .pc-hook     .prompt-emoji-box { background:rgba(236,72,153,0.1); border-color:rgba(236,72,153,0.2); }
    .pc-visual   .prompt-emoji-box { background:rgba(245,158,11,0.1); border-color:rgba(245,158,11,0.2); }
    .pc-research .prompt-emoji-box { background:rgba(14,165,233,0.1); border-color:rgba(14,165,233,0.2); }
    .pc-offer    .prompt-emoji-box { background:rgba(16,185,129,0.1); border-color:rgba(16,185,129,0.2); }
    .pc-email    .prompt-emoji-box { background:rgba(249,115,22,0.1); border-color:rgba(249,115,22,0.2); }

    /* CHEAT SHEET */
    .cheat-sheet { background:rgba(15,10,30,0.9); border-radius:22px; padding:30px; margin-bottom:38px; box-shadow:0 8px 40px rgba(0,0,0,0.3); border:1px solid rgba(168,85,247,0.15); }
    .cheat-sheet h3 { font-size:17px; font-weight:900; color:#e2e8f0; margin-bottom:20px; }
    .cs-row { display:flex; align-items:flex-start; gap:14px; padding:14px 0; border-bottom:1px solid rgba(255,255,255,0.04); }
    .cs-row:last-child { border-bottom:none; }
    .cs-dot { width:10px; height:10px; border-radius:50%; flex-shrink:0; margin-top:5px; box-shadow:0 0 6px currentColor; }
    .cs-label { font-size:13px; font-weight:900; color:#c084fc; min-width:200px; }
    .cs-value { font-size:13px; font-weight:600; color:#64748b; line-height:1.6; }

    /* GOLDEN RULE */
    .golden-rule {
      background: radial-gradient(ellipse at 30% 50%, rgba(168,85,247,0.12) 0%, transparent 70%),
                  radial-gradient(ellipse at 70% 50%, rgba(244,63,94,0.08) 0%, transparent 70%),
                  rgba(15,10,30,0.95);
      border-radius:24px; padding:36px 40px; margin:48px 0 32px; text-align:center;
      border:1px solid rgba(168,85,247,0.2);
      box-shadow:0 0 60px rgba(168,85,247,0.08);
    }
    .golden-rule .gr-emoji { font-size:44px; margin-bottom:16px; display:block; filter:drop-shadow(0 0 12px rgba(168,85,247,0.6)); }
    .golden-rule h3 { font-size:20px; font-weight:900; margin-bottom:14px;
      background: linear-gradient(90deg,#f9a8d4,#c084fc,#818cf8);
      -webkit-background-clip:text; -webkit-text-fill-color:transparent; background-clip:text;
    }
    .golden-rule p { font-size:14.5px; font-weight:600; color:#64748b; line-height:1.85; max-width:620px; margin:0 auto; }
    .golden-rule strong { color:#c084fc; }
    .golden-rule em { color:#818cf8; }

    /* FINAL QUOTE */
    .final-quote {
      background: radial-gradient(ellipse at center, rgba(168,85,247,0.15) 0%, transparent 70%),
                  rgba(15,10,30,0.95);
      border-radius:26px; padding:48px 40px; margin-top:52px; text-align:center;
      border:1px solid rgba(168,85,247,0.2);
    }
    .final-quote .fq-emoji { font-size:50px; margin-bottom:18px; display:block; filter:drop-shadow(0 0 16px rgba(168,85,247,0.7)); }
    .final-quote p { font-size:20px; font-weight:900; line-height:1.6;
      background:linear-gradient(135deg,#f9a8d4,#c084fc,#818cf8,#67e8f9);
      -webkit-background-clip:text; -webkit-text-fill-color:transparent; background-clip:text;
    }
    .final-quote .fq-sub { font-size:14px; font-weight:600; color:#475569; margin-top:14px; }

    @media(max-width:640px){
      .steps-grid { grid-template-columns:1fr 1fr; }
      .tools-grid  { grid-template-columns:1fr 1fr; }
      .mistakes-grid { grid-template-columns:1fr; }
      .hero h1 { font-size:34px; }
      .prompt-header { flex-direction:column; }
      .cs-row { flex-direction:column; gap:6px; }
      .cs-label { min-width:unset; }
    }
  </style>
</head>
<body>

<!-- HERO -->
<div class="hero">
  <div class="nebula-orb"></div>
  <div class="nebula-orb2"></div>
  <div class="hero-badge">✨ TEMPLATE VAULT — RESOURCE 07 ✨</div>
  <span class="hero-icon">🤖</span>
  <h1>
    AI Prompt Pack
    <span>Get 10x more out of every AI tool you use.</span>
  </h1>
  <p>AI tools are only as powerful as the prompts you give them. A vague prompt gets a generic response. A specific, well-structured prompt gets content you can actually use. This prompt pack gives you done-for-you prompts across every major creator use case — so you can get great AI output on the first try, every time.</p>
  <div class="hero-pills">
    <span class="hero-pill">🤖 8 Prompt Categories</span>
    <span class="hero-pill">📋 Copy &amp; Paste Ready</span>
    <span class="hero-pill">✏️ Fill-in-the-Blank</span>
    <span class="hero-pill">⚡ Works with Any AI Tool</span>
    <span class="hero-pill">🌌 30+ AI Tools Covered</span>
    <span class="hero-pill">🆓 Free Options Listed</span>
  </div>
  <div class="hero-count">🌌 The Complete AI Universe for Creators — Updated 2026</div>
</div>

<div class="content">

  <a href="template-vault.html" class="back-link">← Back to Template Vault</a>

  <!-- INTRO -->
  <div class="intro-block">
    Most creators use AI wrong. They type something vague, get garbage output, and conclude "AI doesn't work for me." The truth? <strong>The prompt is everything.</strong> A well-crafted prompt is like having a conversation with the world's most capable assistant — but only if you know how to direct it. This pack gives you <strong>battle-tested, fill-in-the-blank prompts</strong> for every task a creator faces — plus a complete directory of every major AI tool in the galaxy, organized by what it actually does. <strong>The blank page problem stops here.</strong> 🌌
  </div>

  <!-- HOW TO USE -->
  <div class="section-heading">How to Use This Pack 💡</div>
  <div class="steps-grid">
    <div class="step-card">
      <div class="step-num">STEP 01</div>
      <h4>📋 Find &amp; Copy</h4>
      <p>Browse the 8 categories and copy the prompt that matches what you need right now.</p>
    </div>
    <div class="step-card">
      <div class="step-num">STEP 02</div>
      <h4>🔧 Fill the Blanks</h4>
      <p>Replace every <span style="color:#f9a8d4;">[bracket]</span> with your specific niche, topic, or audience. More specific = better output.</p>
    </div>
    <div class="step-card">
      <div class="step-num">STEP 03</div>
      <h4>⚡ Run It</h4>
      <p>Paste into any AI tool. If results aren't perfect, follow up: "make it more [casual / shorter / specific to X]."</p>
    </div>
    <div class="step-card">
      <div class="step-num">STEP 04</div>
      <h4>✨ Make It Human</h4>
      <p>Add your voice, stories, slang. AI gives you the structure — YOU make it convert.</p>
    </div>
  </div>

  <div class="warning-banner">
    ⚠️ <strong>The Golden Rule:</strong> Never post raw AI output. AI is your co-writer, not your ghostwriter. Always read it out loud — if it doesn't sound like something YOU would say, rewrite it. Authentic beats polished every time. ⚠️
  </div>

  <!-- ═══ GALAXY AI TOOLS DIRECTORY ═══ -->
  <!-- STATS BAR -->
  <div class="stats-bar">
    <div class="stat-item"><div class="stat-num">40+</div><div class="stat-lbl">AI Tools</div></div>
    <div class="stat-item"><div class="stat-num">8</div><div class="stat-lbl">Categories</div></div>
    <div class="stat-item"><div class="stat-num">3</div><div class="stat-lbl">Skill Levels</div></div>
    <div class="stat-item"><div class="stat-num">100%</div><div class="stat-lbl">Creator Focused</div></div>
  </div>

  <div class="tools-universe">
    <h3>🌌 The Creator's AI Universe — Complete 2026 Directory</h3>
    <p>Every major AI tool organized by what it does, whether it's free, and what creators actually use it for. Bookmark this section — the AI landscape moves fast and this is your map.</p>

    <!-- WRITING & CHAT AI -->
    <div class="tool-category-label">✍️ Writing, Chat &amp; Scripting AI</div>
    <div class="tools-grid">
      <div class="tool-card">
        <div class="tool-glow" style="background:#10a37f; color:#10a37f;"></div>
        <div class="tool-info">
          <div class="tool-name"><a href="https://openai.com" target="_blank" rel="noopener noreferrer">OpenAI Platform</a></div>
          <div class="tool-desc">The home of ChatGPT, DALL-E, Sora (video), Whisper (voice), and GPT-4o API. One account unlocks the whole ecosystem.</div>
          <div class="tool-badges"><span class="tbadge tbadge-free">Free tier</span><span class="tbadge tbadge-hot">Full ecosystem</span></div>
        </div>
      </div>
      <div class="tool-card">
        <div class="tool-glow" style="background:#10a37f; color:#10a37f;"></div>
        <div class="tool-info">
          <div class="tool-name"><a href="https://chatgpt.com" target="_blank" rel="noopener noreferrer">ChatGPT (GPT-4o)</a></div>
          <div class="tool-desc">The Swiss Army knife. Best for scripts, emails, captions, and bulk content ideas.</div>
          <div class="tool-badges"><span class="tbadge tbadge-free">Free tier</span><span class="tbadge tbadge-hot">Most popular</span></div>
        </div>
      </div>
      <div class="tool-card">
        <div class="tool-glow" style="background:#f43f5e; color:#f43f5e;"></div>
        <div class="tool-info">
          <div class="tool-name"><a href="https://claude.ai" target="_blank" rel="noopener noreferrer">Claude (Anthropic)</a></div>
          <div class="tool-desc">Best for matching your brand voice, nuanced copy, and long-form content that sounds human.</div>
          <div class="tool-badges"><span class="tbadge tbadge-free">Free tier</span><span class="tbadge tbadge-hot">Best voice match</span></div>
        </div>
      </div>
      <div class="tool-card">
        <div class="tool-glow" style="background:#4285f4; color:#4285f4;"></div>
        <div class="tool-info">
          <div class="tool-name"><a href="https://gemini.google.com" target="_blank" rel="noopener noreferrer">Gemini (Google)</a></div>
          <div class="tool-desc">Real-time web access, trend research, and seamless Google Workspace integration.</div>
          <div class="tool-badges"><span class="tbadge tbadge-free">Free tier</span><span class="tbadge tbadge-new">Real-time web</span></div>
        </div>
      </div>
      <div class="tool-card">
        <div class="tool-glow" style="background:#ff6b35; color:#ff6b35;"></div>
        <div class="tool-info">
          <div class="tool-name"><a href="https://grok.com" target="_blank" rel="noopener noreferrer">Grok (xAI)</a></div>
          <div class="tool-desc">Built into X (Twitter). Great for trend-aware content, meme culture, and real-time social context.</div>
          <div class="tool-badges"><span class="tbadge tbadge-free">Free on X</span><span class="tbadge tbadge-new">Image + video gen</span></div>
        </div>
      </div>
      <div class="tool-card">
        <div class="tool-glow" style="background:#0ea5e9; color:#0ea5e9;"></div>
        <div class="tool-info">
          <div class="tool-name"><a href="https://perplexity.ai" target="_blank" rel="noopener noreferrer">Perplexity AI</a></div>
          <div class="tool-desc">Real-time research with citations. Use this instead of Google for niche research and trend discovery.</div>
          <div class="tool-badges"><span class="tbadge tbadge-free">Free tier</span><span class="tbadge tbadge-hot">Best for research</span></div>
        </div>
      </div>
      <div class="tool-card">
        <div class="tool-glow" style="background:#a855f7; color:#a855f7;"></div>
        <div class="tool-info">
          <div class="tool-name"><a href="https://jasper.ai" target="_blank" rel="noopener noreferrer">Jasper AI</a></div>
          <div class="tool-desc">50+ marketing templates. Great for product descriptions, ads, and social content at scale.</div>
          <div class="tool-badges"><span class="tbadge tbadge-paid">Paid</span></div>
        </div>
      </div>
      <div class="tool-card">
        <div class="tool-glow" style="background:#ec4899; color:#ec4899;"></div>
        <div class="tool-info">
          <div class="tool-name"><a href="https://copy.ai" target="_blank" rel="noopener noreferrer">Copy.ai</a></div>
          <div class="tool-desc">Fast social media captions, product copy, and short-form marketing content.</div>
          <div class="tool-badges"><span class="tbadge tbadge-free">Free tier</span></div>
        </div>
      </div>
      <div class="tool-card">
        <div class="tool-glow" style="background:#6366f1; color:#6366f1;"></div>
        <div class="tool-info">
          <div class="tool-name"><a href="https://writesonic.com" target="_blank" rel="noopener noreferrer">Writesonic</a></div>
          <div class="tool-desc">SEO-focused content creation. Great for blog posts and optimized web copy.</div>
          <div class="tool-badges"><span class="tbadge tbadge-free">Free tier</span></div>
        </div>
      </div>
      <div class="tool-card">
        <div class="tool-glow" style="background:#14b8a6; color:#14b8a6;"></div>
        <div class="tool-info">
          <div class="tool-name"><a href="https://grammarly.com" target="_blank" rel="noopener noreferrer">Grammarly AI</a></div>
          <div class="tool-desc">Real-time grammar, tone, and clarity suggestions. Essential for polishing all your content.</div>
          <div class="tool-badges"><span class="tbadge tbadge-free">Free tier</span></div>
        </div>
      </div>
    </div>

    <!-- IMAGE GENERATION -->
    <div class="tool-category-label">🖼️ AI Image Generation</div>
    <div class="tools-grid">
      <div class="tool-card">
        <div class="tool-glow" style="background:#f59e0b; color:#f59e0b;"></div>
        <div class="tool-info">
          <div class="tool-name"><a href="https://midjourney.com" target="_blank" rel="noopener noreferrer">Midjourney</a></div>
          <div class="tool-desc">Unmatched for artistic, stylized, and conceptual imagery. The go-to for brand aesthetics.</div>
          <div class="tool-badges"><span class="tbadge tbadge-paid">Paid</span><span class="tbadge tbadge-hot">Best quality</span></div>
        </div>
      </div>
      <div class="tool-card">
        <div class="tool-glow" style="background:#6366f1; color:#6366f1;"></div>
        <div class="tool-info">
          <div class="tool-name"><a href="https://ideogram.ai" target="_blank" rel="noopener noreferrer">Ideogram</a></div>
          <div class="tool-desc">Best FREE tool for graphics with readable text overlays. Perfect for covers and thumbnails.</div>
          <div class="tool-badges"><span class="tbadge tbadge-free">Free tier</span><span class="tbadge tbadge-hot">Best for text-in-image</span></div>
        </div>
      </div>
      <div class="tool-card">
        <div class="tool-glow" style="background:#f43f5e; color:#f43f5e;"></div>
        <div class="tool-info">
          <div class="tool-name"><a href="https://firefly.adobe.com" target="_blank" rel="noopener noreferrer">Adobe Firefly</a></div>
          <div class="tool-desc">Commercially safe AI images with full IP indemnification. Integrates with Photoshop and Canva.</div>
          <div class="tool-badges"><span class="tbadge tbadge-free">Free tier</span><span class="tbadge tbadge-new">Commercial safe</span></div>
        </div>
      </div>
      <div class="tool-card">
        <div class="tool-glow" style="background:#8b5cf6; color:#8b5cf6;"></div>
        <div class="tool-info">
          <div class="tool-name"><a href="https://leonardo.ai" target="_blank" rel="noopener noreferrer">Leonardo.AI</a></div>
          <div class="tool-desc">150 free daily tokens. Great for product mockups, character art, and realistic images.</div>
          <div class="tool-badges"><span class="tbadge tbadge-free">150 free/day</span></div>
        </div>
      </div>
      <div class="tool-card">
        <div class="tool-glow" style="background:#10a37f; color:#10a37f;"></div>
        <div class="tool-info">
          <div class="tool-name"><a href="https://chatgpt.com" target="_blank" rel="noopener noreferrer">DALL-E 3</a></div>
          <div class="tool-desc">Built into ChatGPT. Great for quick concept images when you're already using ChatGPT.</div>
          <div class="tool-badges"><span class="tbadge tbadge-free">With ChatGPT free</span></div>
        </div>
      </div>
      <div class="tool-card">
        <div class="tool-glow" style="background:#ec4899; color:#ec4899;"></div>
        <div class="tool-info">
          <div class="tool-name"><a href="https://canva.com" target="_blank" rel="noopener noreferrer">Canva AI (Magic Studio)</a></div>
          <div class="tool-desc">20+ AI features in one design tool. Text-to-image, background remover, Magic Expand and more.</div>
          <div class="tool-badges"><span class="tbadge tbadge-free">Free tier</span><span class="tbadge tbadge-hot">Easiest to use</span></div>
        </div>
      </div>
      <div class="tool-card">
        <div class="tool-glow" style="background:#ff6b35; color:#ff6b35;"></div>
        <div class="tool-info">
          <div class="tool-name"><a href="https://grok.com" target="_blank" rel="noopener noreferrer">Grok Imagine</a></div>
          <div class="tool-desc">Built into X (Twitter). Fast image generation with strong real-world context understanding.</div>
          <div class="tool-badges"><span class="tbadge tbadge-free">Free on X</span><span class="tbadge tbadge-new">New in 2025</span></div>
        </div>
      </div>
      <div class="tool-card">
        <div class="tool-glow" style="background:#4285f4; color:#4285f4;"></div>
        <div class="tool-info">
          <div class="tool-name"><a href="https://aitestkitchen.withgoogle.com/tools/image-fx" target="_blank" rel="noopener noreferrer">Google ImageFX</a></div>
          <div class="tool-desc">Free Google image generator powered by Imagen. Clean, photorealistic results.</div>
          <div class="tool-badges"><span class="tbadge tbadge-free">100% Free</span></div>
        </div>
      </div>
    </div>

    <!-- VIDEO AI -->
    <div class="tool-category-label">🎬 AI Video Generation &amp; Editing</div>
    <div class="tools-grid">
      <div class="tool-card">
        <div class="tool-glow" style="background:#10b981; color:#10b981;"></div>
        <div class="tool-info">
          <div class="tool-name"><a href="https://capcut.com" target="_blank" rel="noopener noreferrer">CapCut AI</a></div>
          <div class="tool-desc">The #1 free video editor with AI. Auto captions, AI effects, templates — zero watermark at 1080p.</div>
          <div class="tool-badges"><span class="tbadge tbadge-free">Free</span><span class="tbadge tbadge-hot">Most used by creators</span></div>
        </div>
      </div>
      <div class="tool-card">
        <div class="tool-glow" style="background:#6366f1; color:#6366f1;"></div>
        <div class="tool-info">
          <div class="tool-name"><a href="https://runwayml.com" target="_blank" rel="noopener noreferrer">Runway Gen-4.5</a></div>
          <div class="tool-desc">#1 benchmark for narrative video. Best for cinematic, story-driven AI video content.</div>
          <div class="tool-badges"><span class="tbadge tbadge-paid">From $12/mo</span><span class="tbadge tbadge-hot">Pro quality</span></div>
        </div>
      </div>
      <div class="tool-card">
        <div class="tool-glow" style="background:#a855f7; color:#a855f7;"></div>
        <div class="tool-info">
          <div class="tool-name"><a href="https://pika.art" target="_blank" rel="noopener noreferrer">Pika 2.5</a></div>
          <div class="tool-desc">Speed-optimized for social content. Fast clips, viral-ready, great for trends and meme formats.</div>
          <div class="tool-badges"><span class="tbadge tbadge-free">Free tier</span><span class="tbadge tbadge-new">Fast output</span></div>
        </div>
      </div>
      <div class="tool-card">
        <div class="tool-glow" style="background:#f59e0b; color:#f59e0b;"></div>
        <div class="tool-info">
          <div class="tool-name"><a href="https://klingai.com" target="_blank" rel="noopener noreferrer">Kling 2.6</a></div>
          <div class="tool-desc">Simultaneous audio-visual generation. Creates video + voiceover + sound effects in one pass.</div>
          <div class="tool-badges"><span class="tbadge tbadge-free">Free tier</span><span class="tbadge tbadge-new">Audio+video gen</span></div>
        </div>
      </div>
      <div class="tool-card">
        <div class="tool-glow" style="background:#4285f4; color:#4285f4;"></div>
        <div class="tool-info">
          <div class="tool-name"><a href="https://deepmind.google/technologies/veo/" target="_blank" rel="noopener noreferrer">Google Veo 3</a></div>
          <div class="tool-desc">4K resolution, native audio generation. Rivals the best for cinematic photorealism.</div>
          <div class="tool-badges"><span class="tbadge tbadge-paid">Paid</span><span class="tbadge tbadge-hot">4K quality</span></div>
        </div>
      </div>
      <div class="tool-card">
        <div class="tool-glow" style="background:#ec4899; color:#ec4899;"></div>
        <div class="tool-info">
          <div class="tool-name"><a href="https://opus.pro" target="_blank" rel="noopener noreferrer">Opus Clip</a></div>
          <div class="tool-desc">Repurposes long videos into short clips automatically. Great for turning streams and interviews into Reels.</div>
          <div class="tool-badges"><span class="tbadge tbadge-free">Free tier</span><span class="tbadge tbadge-hot">Best repurposing tool</span></div>
        </div>
      </div>
      <div class="tool-card">
        <div class="tool-glow" style="background:#f43f5e; color:#f43f5e;"></div>
        <div class="tool-info">
          <div class="tool-name"><a href="https://descript.com" target="_blank" rel="noopener noreferrer">Descript</a></div>
          <div class="tool-desc">Edit video by editing the transcript. Removes filler words, repurposes podcasts into clips.</div>
          <div class="tool-badges"><span class="tbadge tbadge-free">Free tier</span></div>
        </div>
      </div>
      <div class="tool-card">
        <div class="tool-glow" style="background:#0ea5e9; color:#0ea5e9;"></div>
        <div class="tool-info">
          <div class="tool-name"><a href="https://veed.io" target="_blank" rel="noopener noreferrer">VEED.io</a></div>
          <div class="tool-desc">Browser-based video editor with subtitles, AI captions, and translation built in.</div>
          <div class="tool-badges"><span class="tbadge tbadge-free">Free tier</span></div>
        </div>
      </div>
      <div class="tool-card">
        <div class="tool-glow" style="background:#ff6b35; color:#ff6b35;"></div>
        <div class="tool-info">
          <div class="tool-name"><a href="https://grok.com" target="_blank" rel="noopener noreferrer">Grok Video</a></div>
          <div class="tool-desc">Text-to-video built into X. 10-second 720p clips, 1B+ videos generated. API available.</div>
          <div class="tool-badges"><span class="tbadge tbadge-free">Free on X</span><span class="tbadge tbadge-new">Launched 2026</span></div>
        </div>
      </div>
    </div>

    <!-- AVATAR & FACELESS -->
    <div class="tool-category-label">🧑‍💻 AI Avatar &amp; Faceless Video</div>
    <div class="tools-grid">
      <div class="tool-card">
        <div class="tool-glow" style="background:#6366f1; color:#6366f1;"></div>
        <div class="tool-info">
          <div class="tool-name"><a href="https://heygen.com" target="_blank" rel="noopener noreferrer">HeyGen</a></div>
          <div class="tool-desc">AI avatar videos in 160+ languages. Create presenter videos without showing your face.</div>
          <div class="tool-badges"><span class="tbadge tbadge-free">Free tier</span><span class="tbadge tbadge-hot">Best avatar tool</span></div>
        </div>
      </div>
      <div class="tool-card">
        <div class="tool-glow" style="background:#8b5cf6; color:#8b5cf6;"></div>
        <div class="tool-info">
          <div class="tool-name"><a href="https://synthesia.io" target="_blank" rel="noopener noreferrer">Synthesia</a></div>
          <div class="tool-desc">Professional AI presenter videos. 160+ languages, custom avatars, teleprompter-style production.</div>
          <div class="tool-badges"><span class="tbadge tbadge-free">Free trial</span></div>
        </div>
      </div>
      <div class="tool-card">
        <div class="tool-glow" style="background:#a855f7; color:#a855f7;"></div>
        <div class="tool-info">
          <div class="tool-name"><a href="https://d-id.com" target="_blank" rel="noopener noreferrer">D-ID</a></div>
          <div class="tool-desc">Animate any photo into a talking avatar. Great for faceless content and personal branding.</div>
          <div class="tool-badges"><span class="tbadge tbadge-free">Free trial</span></div>
        </div>
      </div>
    </div>

    <!-- VOICE & AUDIO -->
    <div class="tool-category-label">🎙️ AI Voice, Audio &amp; Music</div>
    <div class="tools-grid">
      <div class="tool-card">
        <div class="tool-glow" style="background:#a855f7; color:#a855f7;"></div>
        <div class="tool-info">
          <div class="tool-name"><a href="https://elevenlabs.io" target="_blank" rel="noopener noreferrer">ElevenLabs</a></div>
          <div class="tool-desc">The most realistic AI voice generator. Perfect for voiceovers, narrations, and audio content.</div>
          <div class="tool-badges"><span class="tbadge tbadge-free">Free tier</span><span class="tbadge tbadge-hot">Best voice quality</span></div>
        </div>
      </div>
      <div class="tool-card">
        <div class="tool-glow" style="background:#ec4899; color:#ec4899;"></div>
        <div class="tool-info">
          <div class="tool-name"><a href="https://suno.com" target="_blank" rel="noopener noreferrer">Suno</a></div>
          <div class="tool-desc">Generate complete songs with vocals from a text prompt. Background music, jingles, original tracks.</div>
          <div class="tool-badges"><span class="tbadge tbadge-free">Free tier</span><span class="tbadge tbadge-hot">Full songs w/ vocals</span></div>
        </div>
      </div>
      <div class="tool-card">
        <div class="tool-glow" style="background:#f59e0b; color:#f59e0b;"></div>
        <div class="tool-info">
          <div class="tool-name"><a href="https://udio.com" target="_blank" rel="noopener noreferrer">Udio</a></div>
          <div class="tool-desc">Rival to Suno for AI music generation. Different style engine — great for variety.</div>
          <div class="tool-badges"><span class="tbadge tbadge-free">Free tier</span></div>
        </div>
      </div>
    </div>

    <!-- PRODUCTIVITY & RESEARCH -->
    <div class="tool-category-label">🧠 AI Productivity &amp; Research</div>
    <div class="tools-grid">
      <div class="tool-card">
        <div class="tool-glow" style="background:#10b981; color:#10b981;"></div>
        <div class="tool-info">
          <div class="tool-name"><a href="https://notion.so" target="_blank" rel="noopener noreferrer">Notion AI</a></div>
          <div class="tool-desc">AI built into your notes and docs. Summarize, draft, and organize your entire creator workflow.</div>
          <div class="tool-badges"><span class="tbadge tbadge-paid">Add-on</span></div>
        </div>
      </div>
      <div class="tool-card">
        <div class="tool-glow" style="background:#0ea5e9; color:#0ea5e9;"></div>
        <div class="tool-info">
          <div class="tool-name"><a href="https://otter.ai" target="_blank" rel="noopener noreferrer">Otter.ai</a></div>
          <div class="tool-desc">Auto-transcribes meetings, interviews, and voice notes. Great for repurposing audio content.</div>
          <div class="tool-badges"><span class="tbadge tbadge-free">Free tier</span></div>
        </div>
      </div>
      <div class="tool-card">
        <div class="tool-glow" style="background:#6366f1; color:#6366f1;"></div>
        <div class="tool-info">
          <div class="tool-name"><a href="https://fireflies.ai" target="_blank" rel="noopener noreferrer">Fireflies.ai</a></div>
          <div class="tool-desc">AI meeting recorder that summarizes calls and pulls action items automatically.</div>
          <div class="tool-badges"><span class="tbadge tbadge-free">Free tier</span></div>
        </div>
      </div>
    </div>

    <!-- GALAXY AI SECTION -->
    <div class="tool-category-label">🌌 Galaxy AI — All-in-One Platforms</div>
    <div class="tools-grid">
      <div class="tool-card" style="border-color:rgba(168,85,247,0.3); box-shadow:0 0 20px rgba(168,85,247,0.08);">
        <div class="tool-glow" style="background: linear-gradient(135deg,#a855f7,#6366f1); color:#a855f7;"></div>
        <div class="tool-info">
          <div class="tool-name"><a href="https://galaxy.ai" target="_blank" rel="noopener noreferrer">Galaxy.AI</a></div>
          <div class="tool-desc">All-in-one AI hub giving instant access to 5000+ premium AI tools in one app. The ultimate creator toolkit aggregator.</div>
          <div class="tool-badges"><span class="tbadge tbadge-galaxy">🌌 Galaxy Platform</span><span class="tbadge tbadge-new">5000+ tools</span></div>
        </div>
      </div>
      <div class="tool-card" style="border-color:rgba(99,102,241,0.3);">
        <div class="tool-glow" style="background:#6366f1; color:#6366f1;"></div>
        <div class="tool-info">
          <div class="tool-name"><a href="https://www.samsung.com/us/smartphones/galaxy-ai/" target="_blank" rel="noopener noreferrer">Samsung Galaxy AI</a></div>
          <div class="tool-desc">On-device AI built into Samsung devices — Live Translation, Photo Assist, Writing Assist in 41 languages. Free on Galaxy devices.</div>
          <div class="tool-badges"><span class="tbadge tbadge-free">Free on Samsung</span><span class="tbadge tbadge-new">41 languages</span></div>
        </div>
      </div>
      <div class="tool-card">
        <div class="tool-glow" style="background:#ec4899; color:#ec4899;"></div>
        <div class="tool-info">
          <div class="tool-name"><a href="https://www.hootsuite.com/platform/owlywriter-ai" target="_blank" rel="noopener noreferrer">Hootsuite OwlyWriter AI</a></div>
          <div class="tool-desc">Social media AI assistant — captions, post ideas, hashtags, and images all from one dashboard.</div>
          <div class="tool-badges"><span class="tbadge tbadge-paid">With Hootsuite</span></div>
        </div>
      </div>
    </div>


    <!-- MONETIZATION TOOLS -->
    <div class="tool-category-label">💰 AI Monetization &amp; Creator Commerce</div>
    <div class="tools-grid">
      <div class="tool-card">
        <div class="tool-glow" style="background:#a3e635; color:#a3e635;"></div>
        <div class="tool-info">
          <div class="tool-name"><a href="https://stan.store" target="_blank" rel="noopener noreferrer">Stan.store</a></div>
          <div class="tool-desc">All-in-one creator store — sell digital products, courses, and bookings directly from your link-in-bio.</div>
          <div class="tool-badges"><span class="tbadge tbadge-free">Free tier</span><span class="tbadge tbadge-hot">Creator fave</span><span class="tbadge tbadge-beginner">Beginner</span></div>
        </div>
      </div>
      <div class="tool-card">
        <div class="tool-glow" style="background:#f97316; color:#f97316;"></div>
        <div class="tool-info">
          <div class="tool-name"><a href="https://gumroad.com" target="_blank" rel="noopener noreferrer">Gumroad</a></div>
          <div class="tool-desc">Sell PDFs, templates, presets, and digital downloads instantly. No monthly fee — pays on sales only.</div>
          <div class="tool-badges"><span class="tbadge tbadge-free">Free to start</span><span class="tbadge tbadge-beginner">Beginner</span></div>
        </div>
      </div>
      <div class="tool-card">
        <div class="tool-glow" style="background:#8b5cf6; color:#8b5cf6;"></div>
        <div class="tool-info">
          <div class="tool-name"><a href="https://beacons.ai" target="_blank" rel="noopener noreferrer">Beacons.ai</a></div>
          <div class="tool-desc">Creator monetization hub — link-in-bio, store, media kit, email list, and brand deal tracker in one place.</div>
          <div class="tool-badges"><span class="tbadge tbadge-free">Free tier</span><span class="tbadge tbadge-beginner">Beginner</span></div>
        </div>
      </div>
      <div class="tool-card">
        <div class="tool-glow" style="background:#ec4899; color:#ec4899;"></div>
        <div class="tool-info">
          <div class="tool-name"><a href="https://convertkit.com" target="_blank" rel="noopener noreferrer">Kit (ConvertKit)</a></div>
          <div class="tool-desc">Email marketing built for creators. Grow your list, send newsletters, and sell digital products via email.</div>
          <div class="tool-badges"><span class="tbadge tbadge-free">Free up to 10k</span><span class="tbadge tbadge-beginner">Beginner</span></div>
        </div>
      </div>
      <div class="tool-card">
        <div class="tool-glow" style="background:#f59e0b; color:#f59e0b;"></div>
        <div class="tool-info">
          <div class="tool-name"><a href="https://teachable.com" target="_blank" rel="noopener noreferrer">Teachable</a></div>
          <div class="tool-desc">Build and sell online courses and coaching programs. Free plan available for up to 1 course.</div>
          <div class="tool-badges"><span class="tbadge tbadge-free">Free tier</span><span class="tbadge tbadge-inter">Intermediate</span></div>
        </div>
      </div>
      <div class="tool-card">
        <div class="tool-glow" style="background:#10b981; color:#10b981;"></div>
        <div class="tool-info">
          <div class="tool-name"><a href="https://patreon.com" target="_blank" rel="noopener noreferrer">Patreon</a></div>
          <div class="tool-desc">Membership platform for recurring revenue. Offer exclusive content, communities, and perks to paying fans.</div>
          <div class="tool-badges"><span class="tbadge tbadge-free">Free to start</span><span class="tbadge tbadge-beginner">Beginner</span></div>
        </div>
      </div>
      <div class="tool-card">
        <div class="tool-glow" style="background:#6366f1; color:#6366f1;"></div>
        <div class="tool-info">
          <div class="tool-name"><a href="https://kajabi.com" target="_blank" rel="noopener noreferrer">Kajabi</a></div>
          <div class="tool-desc">Premium all-in-one platform — courses, coaching, podcasts, email, and community under one roof.</div>
          <div class="tool-badges"><span class="tbadge tbadge-paid">Paid</span><span class="tbadge tbadge-advanced">Advanced</span></div>
        </div>
      </div>
      <div class="tool-card">
        <div class="tool-glow" style="background:#0ea5e9; color:#0ea5e9;"></div>
        <div class="tool-info">
          <div class="tool-name"><a href="https://thrivecart.com" target="_blank" rel="noopener noreferrer">ThriveCart</a></div>
          <div class="tool-desc">High-converting checkout pages, upsells, and sales funnels. One-time lifetime payment — no monthly fees.</div>
          <div class="tool-badges"><span class="tbadge tbadge-paid">One-time fee</span><span class="tbadge tbadge-inter">Intermediate</span></div>
        </div>
      </div>
    </div>

  </div><!-- end tools-universe -->


  <!-- CREATOR WORKFLOW -->
  <div class="workflow-section">
    <div class="workflow-title">⚡ The Creator AI Workflow</div>
    <div class="workflow-sub">Chain these tools together and go from idea to income in one session</div>
    <div class="workflow-track">
      <div class="wf-step ws1">
        <div class="wf-circle"><div class="wf-num">STEP 1</div><div class="wf-icon">💡</div></div>
        <div class="wf-label">Research</div>
        <div class="wf-tool">Perplexity AI<br>ChatGPT<br>Gemini</div>
      </div>
      <div class="wf-arrow">›</div>
      <div class="wf-step ws2">
        <div class="wf-circle"><div class="wf-num">STEP 2</div><div class="wf-icon">✍️</div></div>
        <div class="wf-label">Script &amp; Copy</div>
        <div class="wf-tool">Claude<br>ChatGPT<br>Jasper</div>
      </div>
      <div class="wf-arrow">›</div>
      <div class="wf-step ws3">
        <div class="wf-circle"><div class="wf-num">STEP 3</div><div class="wf-icon">🖼️</div></div>
        <div class="wf-label">Visuals</div>
        <div class="wf-tool">Midjourney<br>Ideogram<br>Canva AI</div>
      </div>
      <div class="wf-arrow">›</div>
      <div class="wf-step ws4">
        <div class="wf-circle"><div class="wf-num">STEP 4</div><div class="wf-icon">🎬</div></div>
        <div class="wf-label">Video &amp; Audio</div>
        <div class="wf-tool">CapCut AI<br>ElevenLabs<br>HeyGen</div>
      </div>
      <div class="wf-arrow">›</div>
      <div class="wf-step ws5">
        <div class="wf-circle"><div class="wf-num">STEP 5</div><div class="wf-icon">💰</div></div>
        <div class="wf-label">Publish &amp; Sell</div>
        <div class="wf-tool">Stan.store<br>Gumroad<br>Beacons.ai</div>
      </div>
    </div>
  </div>

  <!-- SKILL LEVEL LEGEND -->
  <div class="legend-section">
    <div class="legend-title">🏷️ Skill Level Guide</div>
    <div class="legend-desc">Each tool is tagged so you know exactly where to start based on your experience level.</div>
    <div class="legend-cards">
      <div class="legend-card lc-green">
        <div class="legend-dot ld-green"></div>
        <div><div class="legend-tag-label">Beginner</div><div class="legend-meaning">No experience needed. Set up in minutes and start creating right away.</div></div>
      </div>
      <div class="legend-card lc-orange">
        <div class="legend-dot ld-orange"></div>
        <div><div class="legend-tag-label">Intermediate</div><div class="legend-meaning">Some setup or learning curve. Most creators get results within a week.</div></div>
      </div>
      <div class="legend-card lc-red">
        <div class="legend-dot ld-red"></div>
        <div><div class="legend-tag-label">Advanced</div><div class="legend-meaning">More features and power, but requires time to learn. Worth the investment.</div></div>
      </div>
      <div class="legend-card lc-blue">
        <div class="legend-dot ld-blue"></div>
        <div><div class="legend-tag-label">Free Tier</div><div class="legend-meaning">Usable for free — no credit card required to get started and create.</div></div>
      </div>
    </div>
  </div>

  <!-- HOW TO USE EACH AI -->
  <div class="section-heading">🚀 How to Use Each AI for Content Creation</div>
  <div class="ai-guide-grid">

    <!-- OpenAI / ChatGPT -->
    <div class="ai-guide-card">
      <div class="ai-guide-header">
        <div class="ai-guide-dot" style="background:#10a37f; color:#10a37f;"></div>
        <div>
          <div class="ai-guide-title"><a href="https://openai.com" target="_blank" rel="noopener noreferrer">OpenAI / ChatGPT</a></div>
          <div class="ai-guide-tagline">Best all-rounder for creators — chatgpt.com or openai.com</div>
        </div>
      </div>
      <ul class="ai-guide-steps">
        <li data-num="1">Go to chatgpt.com and sign up free, or log into openai.com for API/Sora/DALL-E access.</li>
        <li data-num="2">Start a new chat. Type your prompt in the message box — be specific about your niche, audience, and tone.</li>
        <li data-num="3">Use the mic button to speak your prompt if typing feels slow.</li>
        <li data-num="4">Hit reply to refine: "make it shorter", "add a hook", "give me 5 variations."</li>
        <li data-num="5">For images, type "/imagine" or switch to DALL-E in the model selector. For video, access Sora at openai.com/sora.</li>
        <li data-num="6">Pin your best chats so your context carries over next time.</li>
      </ul>
      <div class="ai-guide-tip">💡 Pro Tip: <span>Start every chat with "You are a content strategist for [your niche]. My audience is [describe them]." ChatGPT will stay in character for the whole session.</span></div>
    </div>

    <!-- Claude -->
    <div class="ai-guide-card">
      <div class="ai-guide-header">
        <div class="ai-guide-dot" style="background:#f43f5e; color:#f43f5e;"></div>
        <div>
          <div class="ai-guide-title"><a href="https://claude.ai" target="_blank" rel="noopener noreferrer">Claude (Anthropic)</a></div>
          <div class="ai-guide-tagline">Best for writing that sounds like YOU — claude.ai</div>
        </div>
      </div>
      <ul class="ai-guide-steps">
        <li data-num="1">Go to claude.ai and create a free account. No credit card needed to start.</li>
        <li data-num="2">Click "New Chat" and paste your prompt. Claude reads long documents well — upload a script, email, or brand guide to give it context.</li>
        <li data-num="3">Tell Claude your voice: "Write in a casual, direct tone like a Gen Z creator who explains things simply."</li>
        <li data-num="4">Use Projects (paid) to save brand context across sessions so you never repeat yourself.</li>
        <li data-num="5">Ask Claude to rewrite AI-sounding drafts: "Rewrite this to sound less robotic and more like someone texting a friend."</li>
        <li data-num="6">Use it for long-form: email sequences, sales pages, blog posts, captions in bulk.</li>
      </ul>
      <div class="ai-guide-tip">💡 Pro Tip: <span>Claude is the best AI for matching brand voice. Paste 3 of your best-performing captions and say "Write in this style" — the results feel authentically YOU.</span></div>
    </div>

    <!-- Gemini -->
    <div class="ai-guide-card">
      <div class="ai-guide-header">
        <div class="ai-guide-dot" style="background:#4285f4; color:#4285f4;"></div>
        <div>
          <div class="ai-guide-title"><a href="https://gemini.google.com" target="_blank" rel="noopener noreferrer">Gemini (Google)</a></div>
          <div class="ai-guide-tagline">Best for research + Google integration — gemini.google.com</div>
        </div>
      </div>
      <ul class="ai-guide-steps">
        <li data-num="1">Go to gemini.google.com and sign in with your Google account — it's free.</li>
        <li data-num="2">Use it to research trending topics: "What are the top 10 trending creator niches in 2026?"</li>
        <li data-num="3">Connect it to Google Docs, Gmail, and Drive using the Extensions button to pull in real data.</li>
        <li data-num="4">Ask it to summarize YouTube videos, news articles, or competitor content by pasting the URL.</li>
        <li data-num="5">Use Gemini Advanced (paid) for longer outputs, image generation, and deeper research.</li>
        <li data-num="6">Use it to draft content calendars that pull from real-time search trends.</li>
      </ul>
      <div class="ai-guide-tip">💡 Pro Tip: <span>Ask Gemini "What is trending on YouTube this week in [your niche]?" before filming. It pulls live data so you can ride trends while they're hot.</span></div>
    </div>

    <!-- Grok -->
    <div class="ai-guide-card">
      <div class="ai-guide-header">
        <div class="ai-guide-dot" style="background:#ff6b35; color:#ff6b35;"></div>
        <div>
          <div class="ai-guide-title"><a href="https://grok.com" target="_blank" rel="noopener noreferrer">Grok (xAI)</a></div>
          <div class="ai-guide-tagline">Best for social trends + image/video gen — grok.com</div>
        </div>
      </div>
      <ul class="ai-guide-steps">
        <li data-num="1">Go to grok.com or find Grok inside the X (Twitter) app — free on both.</li>
        <li data-num="2">Ask Grok about real-time X trends: "What are creators talking about today in [your niche]?"</li>
        <li data-num="3">For images, type "imagine [your description]" and Grok will generate it using Aurora.</li>
        <li data-num="4">For short video clips, use Grok Video — describe a scene and it generates a 10-second clip.</li>
        <li data-num="5">Use Grok's "Fun mode" for edgy, meme-style captions that perform well on X and TikTok.</li>
        <li data-num="6">Use DeepSearch mode for in-depth research with live X data and web sources.</li>
      </ul>
      <div class="ai-guide-tip">💡 Pro Tip: <span>Use Grok to monitor what your competitors are saying on X. Ask: "What is [creator name] posting about this week?" and use those insights to create timely responses.</span></div>
    </div>

    <!-- Perplexity -->
    <div class="ai-guide-card">
      <div class="ai-guide-header">
        <div class="ai-guide-dot" style="background:#0ea5e9; color:#0ea5e9;"></div>
        <div>
          <div class="ai-guide-title"><a href="https://perplexity.ai" target="_blank" rel="noopener noreferrer">Perplexity AI</a></div>
          <div class="ai-guide-tagline">Best research tool with citations — perplexity.ai</div>
        </div>
      </div>
      <ul class="ai-guide-steps">
        <li data-num="1">Go to perplexity.ai — free to use, no account needed to start.</li>
        <li data-num="2">Type a research question like "What are creators saying about [topic] in 2026?" and get sourced answers instantly.</li>
        <li data-num="3">Click any citation to go to the original source — great for fact-checking before you post.</li>
        <li data-num="4">Use "Focus" to search only YouTube, Reddit, or academic sources for niche deep-dives.</li>
        <li data-num="5">Ask follow-up questions in the same thread to go deeper without losing context.</li>
        <li data-num="6">Use Pro Search (paid) for more detailed multi-step research reports.</li>
      </ul>
      <div class="ai-guide-tip">💡 Pro Tip: <span>Replace Google with Perplexity for all content research. You get summarized answers WITH sources — no more clicking 10 tabs to find one stat for your script.</span></div>
    </div>

    <!-- Midjourney -->
    <div class="ai-guide-card">
      <div class="ai-guide-header">
        <div class="ai-guide-dot" style="background:#f59e0b; color:#f59e0b;"></div>
        <div>
          <div class="ai-guide-title"><a href="https://midjourney.com" target="_blank" rel="noopener noreferrer">Midjourney</a></div>
          <div class="ai-guide-tagline">Best for stunning visual branding — midjourney.com</div>
        </div>
      </div>
      <ul class="ai-guide-steps">
        <li data-num="1">Go to midjourney.com and sign in with Discord or Google. Basic plan starts at $10/mo.</li>
        <li data-num="2">Use the web editor at midjourney.com/imagine — type your prompt in the box and hit generate.</li>
        <li data-num="3">Structure prompts as: [subject], [style], [lighting], [mood], [camera] — e.g. "female content creator, lo-fi aesthetic, soft morning light, cozy, shot on 35mm"</li>
        <li data-num="4">Add "--ar 9:16" for TikTok/Reels vertical format, "--ar 16:9" for YouTube thumbnails.</li>
        <li data-num="5">Use "Vary (Subtle)" to get slight variations of your best image without starting over.</li>
        <li data-num="6">Use /describe to upload a photo and reverse-engineer a prompt from any image style you love.</li>
      </ul>
      <div class="ai-guide-tip">💡 Pro Tip: <span>Save your favorite prompts as "Custom Styles" in Midjourney to keep a consistent brand aesthetic across all your content visuals.</span></div>
    </div>

    <!-- Ideogram -->
    <div class="ai-guide-card">
      <div class="ai-guide-header">
        <div class="ai-guide-dot" style="background:#6366f1; color:#6366f1;"></div>
        <div>
          <div class="ai-guide-title"><a href="https://ideogram.ai" target="_blank" rel="noopener noreferrer">Ideogram</a></div>
          <div class="ai-guide-tagline">Best FREE tool for text-in-image graphics — ideogram.ai</div>
        </div>
      </div>
      <ul class="ai-guide-steps">
        <li data-num="1">Go to ideogram.ai and sign up free — you get 10 free generations per day.</li>
        <li data-num="2">Type a prompt that includes the exact text you want displayed in the image in quotes.</li>
        <li data-num="3">Choose an aspect ratio: 9:16 for stories/reels covers, 1:1 for posts, 16:9 for YouTube thumbnails.</li>
        <li data-num="4">Select a style: Realistic, Design, Illustration, or 3D — "Design" works best for digital product covers.</li>
        <li data-num="5">Click "Edit" on any result to remix — change colors, swap text, or adjust the background.</li>
        <li data-num="6">Download at full resolution free — no watermark on the free plan.</li>
      </ul>
      <div class="ai-guide-tip">💡 Pro Tip: <span>Use Ideogram to create digital product mock-up covers, course thumbnail graphics, and Pinterest pins with bold readable text — all for free.</span></div>
    </div>

    <!-- CapCut AI -->
    <div class="ai-guide-card">
      <div class="ai-guide-header">
        <div class="ai-guide-dot" style="background:#000000; color:#888;"></div>
        <div>
          <div class="ai-guide-title"><a href="https://capcut.com" target="_blank" rel="noopener noreferrer">CapCut AI</a></div>
          <div class="ai-guide-tagline">Best free video editor with built-in AI — capcut.com</div>
        </div>
      </div>
      <ul class="ai-guide-steps">
        <li data-num="1">Go to capcut.com or download the app. Sign up free — the web version works on any computer.</li>
        <li data-num="2">Upload your raw footage and use "Auto Captions" to generate subtitles in seconds.</li>
        <li data-num="3">Use "AI Script to Video" — paste your script and CapCut builds a rough cut with stock footage automatically.</li>
        <li data-num="4">Use "Remove Background" in one click — no green screen needed.</li>
        <li data-num="5">Use "AI Voice" to generate a voiceover from your script text if you don't want to record.</li>
        <li data-num="6">Export at 1080p free — no watermark on the app version (check current terms).</li>
      </ul>
      <div class="ai-guide-tip">💡 Pro Tip: <span>Use CapCut's "Auto Reframe" to instantly resize one video for TikTok (9:16), Instagram square (1:1), and YouTube (16:9) — one edit, three platforms done.</span></div>
    </div>

    <!-- ElevenLabs -->
    <div class="ai-guide-card">
      <div class="ai-guide-header">
        <div class="ai-guide-dot" style="background:#f97316; color:#f97316;"></div>
        <div>
          <div class="ai-guide-title"><a href="https://elevenlabs.io" target="_blank" rel="noopener noreferrer">ElevenLabs</a></div>
          <div class="ai-guide-tagline">Best AI voice generator for creators — elevenlabs.io</div>
        </div>
      </div>
      <ul class="ai-guide-steps">
        <li data-num="1">Go to elevenlabs.io and create a free account — you get 10,000 characters/month free.</li>
        <li data-num="2">Go to "Speech Synthesis" and paste your script into the text box.</li>
        <li data-num="3">Choose a pre-made voice or clone your own voice by uploading 1–3 minutes of clean audio.</li>
        <li data-num="4">Adjust stability and clarity sliders — lower stability = more expressive and natural-sounding.</li>
        <li data-num="5">Download the MP3 and drop it into CapCut, Descript, or any video editor.</li>
        <li data-num="6">Use for faceless content, YouTube narration, podcast intros, or digital product audio.</li>
      </ul>
      <div class="ai-guide-tip">💡 Pro Tip: <span>Clone your own voice once and use it for ALL your faceless content. You stay consistent and recognizable while batching videos without recording every time.</span></div>
    </div>

    <!-- HeyGen -->
    <div class="ai-guide-card">
      <div class="ai-guide-header">
        <div class="ai-guide-dot" style="background:#8b5cf6; color:#8b5cf6;"></div>
        <div>
          <div class="ai-guide-title"><a href="https://heygen.com" target="_blank" rel="noopener noreferrer">HeyGen</a></div>
          <div class="ai-guide-tagline">Best AI avatar video creator — heygen.com</div>
        </div>
      </div>
      <ul class="ai-guide-steps">
        <li data-num="1">Go to heygen.com and sign up — free trial includes 1 video credit.</li>
        <li data-num="2">Choose "AI Avatar" and pick a pre-built avatar or create your own from a 2-minute video recording.</li>
        <li data-num="3">Paste your script into the script box — the avatar will lip-sync to it perfectly.</li>
        <li data-num="4">Choose a background, add your logo, and pick a voice (or clone your own voice).</li>
        <li data-num="5">Click Generate — your video is ready in minutes, no filming, no editing.</li>
        <li data-num="6">Use for YouTube explainers, UGC-style ads, course content, and social media videos at scale.</li>
      </ul>
      <div class="ai-guide-tip">💡 Pro Tip: <span>Create a personal avatar once, then batch 10 videos a week by just swapping scripts. Perfect for digital product promotions without ever appearing on camera.</span></div>
    </div>

    <!-- Notion AI -->
    <div class="ai-guide-card">
      <div class="ai-guide-header">
        <div class="ai-guide-dot" style="background:#e2e8f0; color:#e2e8f0;"></div>
        <div>
          <div class="ai-guide-title"><a href="https://notion.so" target="_blank" rel="noopener noreferrer">Notion AI</a></div>
          <div class="ai-guide-tagline">Best for organizing your entire creator business — notion.so</div>
        </div>
      </div>
      <ul class="ai-guide-steps">
        <li data-num="1">Go to notion.so and sign up free — Notion AI is an add-on for $10/mo.</li>
        <li data-num="2">Create a Content Calendar database and use AI to auto-fill post ideas, captions, and publish dates.</li>
        <li data-num="3">Highlight any text and press Space to open AI — ask it to "improve writing," "make shorter," or "translate."</li>
        <li data-num="4">Use AI to summarize meeting notes, research, or long documents in seconds.</li>
        <li data-num="5">Build a Brand Voice page with your tone, phrases, and examples — paste it as context in every AI prompt.</li>
        <li data-num="6">Use it to create SOPs (Standard Operating Procedures) for your content workflow so you can delegate.</li>
      </ul>
      <div class="ai-guide-tip">💡 Pro Tip: <span>Build a "Content Brain" in Notion — one master doc with your niche, audience, tone, best hooks, and offers. Paste it at the start of any AI prompt for instant on-brand output.</span></div>
    </div>

    <!-- Galaxy.AI -->
    <div class="ai-guide-card">
      <div class="ai-guide-header">
        <div class="ai-guide-dot" style="background:#818cf8; color:#818cf8;"></div>
        <div>
          <div class="ai-guide-title"><a href="https://galaxy.ai" target="_blank" rel="noopener noreferrer">Galaxy.AI</a></div>
          <div class="ai-guide-tagline">Your all-in-one AI tools hub — galaxy.ai</div>
        </div>
      </div>
      <ul class="ai-guide-steps">
        <li data-num="1">Go to galaxy.ai — it's a hub with 5,000+ AI tools organized by category.</li>
        <li data-num="2">Search for the type of tool you need: "caption generator", "thumbnail maker", "video editor."</li>
        <li data-num="3">Browse curated collections like "Top AI tools for content creators" to discover new tools fast.</li>
        <li data-num="4">Bookmark tools you use regularly — it keeps your creator toolkit organized in one place.</li>
        <li data-num="5">Check the "New & Trending" section weekly to stay ahead of new AI releases before they go viral.</li>
        <li data-num="6">Use it as your AI tool directory so you're never stuck searching Google for "best AI tool to [task]."</li>
      </ul>
      <div class="ai-guide-tip">💡 Pro Tip: <span>Bookmark galaxy.ai as your AI home base. Every time a new AI tool drops, it's listed there first — you'll always know what's new before your audience does.</span></div>
    </div>

  </div><!-- end ai-guide-grid -->

  <!-- COMMON MISTAKES -->
  <div class="section-heading">❌ Prompting Mistakes to Avoid</div>
  <div class="mistakes-grid">
    <div class="mistake-card bad">
      <span class="mk-icon">❌</span>
      <h4>Too Vague</h4>
      <p>"Write me a TikTok caption." — AI has no idea who you are, what you're posting, or who you're talking to. Generic input = generic output.</p>
    </div>
    <div class="mistake-card good">
      <span class="mk-icon">✅</span>
      <h4>Specific &amp; Targeted</h4>
      <p>"Write a TikTok caption for a video about why new creators shouldn't buy a ring light first. Audience: beginners. Tone: funny and direct. End with a CTA to follow." — Now THAT works.</p>
    </div>
    <div class="mistake-card bad">
      <span class="mk-icon">❌</span>
      <h4>One-and-Done</h4>
      <p>Accepting the first response. AI improves dramatically when you follow up. Say "make it shorter", "more conversational", or "give me 5 more options."</p>
    </div>
    <div class="mistake-card good">
      <span class="mk-icon">✅</span>
      <h4>Iterate in the Same Chat</h4>
      <p>Keep refining in one conversation. Each follow-up teaches the AI more about what you want. By message 3–4, you're often getting near-perfect output.</p>
    </div>
    <div class="mistake-card bad">
      <span class="mk-icon">❌</span>
      <h4>Posting It Raw</h4>
      <p>Pasting AI output directly into your captions and scripts. Your audience can feel the difference — it damages your authenticity and trust instantly.</p>
    </div>
    <div class="mistake-card good">
      <span class="mk-icon">✅</span>
      <h4>Use It as a First Draft</h4>
      <p>Let AI generate 80% of the structure, then spend 10 minutes adding your voice, stories, slang. That final 20% is what makes it convert.</p>
    </div>
  </div>

  <!-- PROMPT CATEGORIES -->
  <div class="section-heading">📦 Your 8 Prompt Categories</div>

  <!-- ═══ CARD 1: CONTENT IDEA PROMPTS ═══ -->
  <div class="prompt-card pc-content">
    <div class="prompt-header">
      <div class="prompt-emoji-box">💡</div>
      <div class="prompt-header-text">
        <span class="prompt-num">CATEGORY 01</span>
        <h2>Content Idea Prompts</h2>
        <div class="prompt-tagline">Generate 30 content ideas for your niche in under 60 seconds. Includes niche-specific variations.</div>
      </div>
    </div>
    <div class="prompt-body">
      <div class="what-it-does">The #1 reason creators don't post consistently isn't laziness — it's not knowing what to post. These prompts end that problem permanently. Run them once a week and you'll never stare at a blank screen again.</div>
      <div class="when-to-use">
        <h4>Best For 🎯</h4>
        <div class="use-tags">
          <span class="use-tag">Weekly content planning</span><span class="use-tag">Batch filming prep</span><span class="use-tag">Breaking a posting rut</span><span class="use-tag">Building an idea bank</span>
        </div>
      </div>
      <div class="examples-label">Prompt 1 — Bulk Idea Generator 📋</div>
      <div class="example-prompt">
        <span class="copy-tag">COPY THIS</span>
        <p>Generate 30 content ideas for a <span class="placeholder">[TikTok / Instagram / YouTube Shorts]</span> creator in the <span class="placeholder">[your niche]</span> space targeting <span class="placeholder">[your audience, e.g. women 25–35 trying to make money online]</span>.<br><br>
        <span class="instruction">Format:</span> Number 1–30 · Include content type (educational/entertaining/promotional/relatable) · Include a suggested hook · Mix formats: talking head, voiceover, text-on-screen, POV, storytime · Make 5 ideas trend-adjacent.</p>
      </div>
      <div class="examples-label">Prompt 2 — Based on Your Best Content 📋</div>
      <div class="example-prompt">
        <span class="copy-tag">COPY THIS</span>
        <p>I create content about <span class="placeholder">[your topic]</span> for <span class="placeholder">[your audience]</span>. My top-performing content has been about <span class="placeholder">[describe 1–2 videos that did well]</span>.<br><br>Give me 15 new ideas that are similar in style but cover ground I haven't posted yet. For each: the angle, the hook, and why it would resonate.</p>
      </div>
      <div class="examples-label">Prompt 3 — Seasonal &amp; Trend-Based 📋</div>
      <div class="example-prompt">
        <span class="copy-tag">COPY THIS</span>
        <p>What content ideas in the <span class="placeholder">[your niche]</span> space would perform well in <span class="placeholder">[month / season / upcoming holiday]</span>? Give me 10 ideas that tie my niche to this time of year naturally. Include a hook and format suggestion for each.</p>
      </div>
      <div class="card-divider"></div>
      <div class="pro-tip">💡 <strong>Pro Tip:</strong> After getting your idea list, add: "Rank these by likely viral potential for a creator with under 10K followers, and explain why." This tells you exactly where to start.</div>
      <div class="avoid-block">🚫 <strong>Avoid:</strong> Ideas that are too broad. If AI says "post a workout routine" — push back. Say: "Make these more specific, with a unique angle that stands out from other creators posting this."</div>
    </div>
  </div>

  <!-- ═══ CARD 2: HOOK WRITING ═══ -->
  <div class="prompt-card pc-hook">
    <div class="prompt-header">
      <div class="prompt-emoji-box">🎣</div>
      <div class="prompt-header-text">
        <span class="prompt-num">CATEGORY 02</span>
        <h2>Hook Writing Prompts</h2>
        <div class="prompt-tagline">Ask AI to write 10 hooks for any topic using proven hook formulas.</div>
      </div>
    </div>
    <div class="prompt-body">
      <div class="what-it-does">Your hook is the first 1–3 seconds — it determines whether someone watches or scrolls. These prompts generate multiple hooks using the formulas top creators use: curiosity gaps, controversy, results, stories, and direct address.</div>
      <div class="when-to-use">
        <h4>Best For 🎯</h4>
        <div class="use-tags">
          <span class="use-tag">Before filming any video</span><span class="use-tag">A/B testing hooks</span><span class="use-tag">Live stream openers</span><span class="use-tag">Improving watch time</span>
        </div>
      </div>
      <div class="examples-label">Prompt 1 — Multi-Formula Hook Pack 📋</div>
      <div class="example-prompt">
        <span class="copy-tag">COPY THIS</span>
        <p>Write 10 hooks for a video about <span class="placeholder">[your topic]</span> for <span class="placeholder">[your audience]</span>. Two of each type:<br><br>
        1. <span class="instruction">Curiosity</span> — tease something surprising ("Nobody talks about this, but...")<br>
        2. <span class="instruction">Result</span> — lead with outcome ("I went from 0 to 10K in 30 days doing this")<br>
        3. <span class="instruction">Controversy</span> — challenge common belief ("Unpopular opinion: [common advice] is hurting you")<br>
        4. <span class="instruction">Story</span> — open mid-action ("I was scrolling at 2am when I found...")<br>
        5. <span class="instruction">Direct address</span> — call out the viewer ("If you're a [type of person], stop what you're doing")<br><br>
        Each hook under 15 words. No filler. Every word earns its place.</p>
      </div>
      <div class="examples-label">Prompt 2 — A/B Test Hooks 📋</div>
      <div class="example-prompt">
        <span class="copy-tag">COPY THIS</span>
        <p>I want to film the same video 3 times with 3 different hooks for <span class="placeholder">[your topic]</span>. Write one curiosity hook, one result hook, and one controversy hook. Each under 12 words, each creating enough intrigue that someone mid-scroll would stop instantly.</p>
      </div>
      <div class="examples-label">Prompt 3 — Live Stream Openers 📋</div>
      <div class="example-prompt">
        <span class="copy-tag">COPY THIS</span>
        <p>Write 5 live stream opening lines for a <span class="placeholder">[your niche]</span> creator. Each must: (1) greet warmly, (2) state today's topic in one sentence, (3) give viewers a reason to stay ("by the end of this live you'll know exactly how to..."). Under 30 seconds spoken.</p>
      </div>
      <div class="card-divider"></div>
      <div class="pro-tip">💡 <strong>Pro Tip:</strong> After getting hooks, ask: "Which of these 10 has the highest scroll-stop rate for someone watching TikTok at 11pm, and why?" The reasoning teaches you what makes hooks work.</div>
      <div class="avoid-block">🚫 <strong>Avoid:</strong> Hooks starting with "I" or "So" — these are weak openers. Ask AI to rewrite any hook that starts with these words.</div>
    </div>
  </div>

  <!-- ═══ CARD 3: CAPTION WRITING ═══ -->
  <div class="prompt-card pc-caption">
    <div class="prompt-header">
      <div class="prompt-emoji-box">✍️</div>
      <div class="prompt-header-text">
        <span class="prompt-num">CATEGORY 03</span>
        <h2>Caption Writing Prompts</h2>
        <div class="prompt-tagline">Generate engaging captions with CTAs for TikTok, Instagram, and YouTube Shorts.</div>
      </div>
    </div>
    <div class="prompt-body">
      <div class="what-it-does">Captions drive saves, comments, and follows — all of which tell the algorithm your content is worth pushing. These prompts are built for each platform's style and limits.</div>
      <div class="when-to-use">
        <h4>Best For 🎯</h4>
        <div class="use-tags">
          <span class="use-tag">TikTok videos</span><span class="use-tag">Instagram Reels &amp; carousels</span><span class="use-tag">YouTube Shorts descriptions</span><span class="use-tag">Link-in-bio traffic</span>
        </div>
      </div>
      <div class="examples-label">Prompt 1 — TikTok Caption 📋</div>
      <div class="example-prompt">
        <span class="copy-tag">COPY THIS</span>
        <p>Write 3 TikTok captions for a video about <span class="placeholder">[your topic]</span>. Audience: <span class="placeholder">[describe them]</span>. Tone: <span class="placeholder">[casual / educational / motivational / funny]</span>.<br><br>
        Each caption: under 150 characters · 1 question people in my niche would genuinely answer in comments · specific CTA (not just "follow for more") · no hashtags in caption.</p>
      </div>
      <div class="examples-label">Prompt 2 — Instagram Carousel Caption 📋</div>
      <div class="example-prompt">
        <span class="copy-tag">COPY THIS</span>
        <p>Write a full Instagram caption for a carousel about <span class="placeholder">[your topic]</span>.<br><br>
        <span class="instruction">Line 1:</span> Bold scroll-stopping first sentence (shows before "more")<br>
        <span class="instruction">Body:</span> 3–5 punchy value-driven lines — short and skimmable<br>
        <span class="instruction">CTA:</span> Save this post + answer [specific question]<br>
        <span class="instruction">Hashtags:</span> 15 total — 3 mega (1M+), 5 large (100K–1M), 5 medium (10K–100K), 2 niche (&lt;10K)</p>
      </div>
      <div class="examples-label">Prompt 3 — Caption to Drive Link Clicks 📋</div>
      <div class="example-prompt">
        <span class="copy-tag">COPY THIS</span>
        <p>Write a caption for a video promoting my <span class="placeholder">[product / freebie / link]</span>. The video covers <span class="placeholder">[what the video is about]</span>. Create enough curiosity that viewers click my bio link without me being salesy. Tone: <span class="placeholder">[casual / excited / matter-of-fact]</span>. Under 200 characters.</p>
      </div>
      <div class="card-divider"></div>
      <div class="pro-tip">💡 <strong>Pro Tip:</strong> For Instagram, the first line is everything — it shows before "more". Ask AI: "Give me 10 different first-line options that would make someone tap 'more' immediately."</div>
    </div>
  </div>

  <!-- ═══ CARD 4: SCRIPT WRITING ═══ -->
  <div class="prompt-card pc-script">
    <div class="prompt-header">
      <div class="prompt-emoji-box">🎬</div>
      <div class="prompt-header-text">
        <span class="prompt-num">CATEGORY 04</span>
        <h2>Script Writing Prompts</h2>
        <div class="prompt-tagline">Full video script prompts for educational, sales, and story-based content.</div>
      </div>
    </div>
    <div class="prompt-body">
      <div class="what-it-does">Camera paralysis — not knowing what to say when recording — is one of the top reasons creators quit. These prompts generate complete scripts from hook to CTA in multiple formats so you never film blank again.</div>
      <div class="when-to-use">
        <h4>Best For 🎯</h4>
        <div class="use-tags">
          <span class="use-tag">Filming days</span><span class="use-tag">Sales content</span><span class="use-tag">Educational tutorials</span><span class="use-tag">Story content</span><span class="use-tag">UGC ads</span>
        </div>
      </div>
      <div class="examples-label">Prompt 1 — Educational Script (60 sec) 📋</div>
      <div class="example-prompt">
        <span class="copy-tag">COPY THIS</span>
        <p>Write a 60-second TikTok/Reels script about <span class="placeholder">[your topic]</span> for <span class="placeholder">[your audience]</span>.<br><br>
        🎣 <span class="instruction">Hook (0–3 sec):</span> One bold sentence that stops the scroll<br>
        ❓ <span class="instruction">Problem (3–10 sec):</span> Name the specific struggle<br>
        💡 <span class="instruction">Solution (10–45 sec):</span> 3 numbered tips, 1–2 sentences each<br>
        🚀 <span class="instruction">CTA (45–60 sec):</span> One specific action<br><br>
        Tone: conversational, direct. No filler phrases. Write exactly how it should be spoken aloud.</p>
      </div>
      <div class="examples-label">Prompt 2 — Sales Script (90 sec) 📋</div>
      <div class="example-prompt">
        <span class="copy-tag">COPY THIS</span>
        <p>Write a 90-second sales script for my <span class="placeholder">[product name]</span> at <span class="placeholder">[price]</span> for <span class="placeholder">[your audience]</span>.<br><br>
        <span class="instruction">Hook:</span> Open with their #1 pain point<br>
        <span class="instruction">Agitate:</span> Make it feel urgent and real<br>
        <span class="instruction">Solution:</span> Introduce product as the answer<br>
        <span class="instruction">Benefits:</span> 3 specific outcomes (not features)<br>
        <span class="instruction">Social proof:</span> Placeholder for testimonial<br>
        <span class="instruction">Offer + Urgency + CTA</span><br><br>
        Tone: <span class="placeholder">[confident / warm / excited]</span>. No corporate language. Write like talking to a friend.</p>
      </div>
      <div class="examples-label">Prompt 3 — Story-Based Script 📋</div>
      <div class="example-prompt">
        <span class="copy-tag">COPY THIS</span>
        <p>Write a 60–90 second story script about <span class="placeholder">[your personal experience or transformation]</span>.<br><br>
        <span class="instruction">Hook:</span> Start in the middle of the story, not the beginning<br>
        <span class="instruction">Before:</span> Relatable struggle<br>
        <span class="instruction">Turning point:</span> The moment everything changed<br>
        <span class="instruction">After:</span> Where you are now<br>
        <span class="instruction">Lesson + CTA</span><br><br>
        First person, emotionally resonant. Show the messy middle — not just the win.</p>
      </div>
      <div class="card-divider"></div>
      <div class="pro-tip">💡 <strong>Pro Tip:</strong> After the script is written, paste it back and say: "Read this as a TikTok viewer. What's the first moment you'd consider scrolling? Rewrite that section." This catches weak spots before you film.</div>
      <div class="avoid-block">🚫 <strong>Avoid:</strong> Scripts that are too long. 60 seconds = roughly 150 words. Ask AI: "Is this the right length for 60 seconds? Trim it without losing key points."</div>
    </div>
  </div>

  <!-- ═══ CARD 5: VISUAL CREATION ═══ -->
  <div class="prompt-card pc-visual">
    <div class="prompt-header">
      <div class="prompt-emoji-box">🖼️</div>
      <div class="prompt-header-text">
        <span class="prompt-num">CATEGORY 05</span>
        <h2>Visual Creation Prompts</h2>
        <div class="prompt-tagline">Prompts for AI image generators (Midjourney, DALL-E, Ideogram, Grok Imagine) to create on-brand visuals.</div>
      </div>
    </div>
    <div class="prompt-body">
      <div class="what-it-does">No photographer. No designer. No expensive shoot. These prompts are formatted for the top AI image tools — each optimized for that specific tool's syntax to get the best results on the first try.</div>
      <div class="when-to-use">
        <h4>Best For 🎯</h4>
        <div class="use-tags">
          <span class="use-tag">Product covers</span><span class="use-tag">Thumbnails</span><span class="use-tag">Brand graphics</span><span class="use-tag">Lifestyle imagery</span><span class="use-tag">Story backgrounds</span>
        </div>
      </div>
      <div class="examples-label">Prompt 1 — Digital Product Cover (Ideogram) 📋</div>
      <div class="example-prompt">
        <span class="prompt-type-tag tag-ideogram">IDEOGRAM</span>
        <p>Professional digital product cover for an ebook titled "<span class="placeholder">[your product name]</span>" subtitle "<span class="placeholder">[subtitle]</span>". Style: modern, clean, premium. Color palette: <span class="placeholder">[your brand colors]</span>. Bold legible title text centered. Gradient background. Portrait 6x9 ratio. No people. Minimalist. <span class="instruction">text legible</span></p>
      </div>
      <div class="examples-label">Prompt 2 — Lifestyle Creator Flat Lay (Midjourney) 📋</div>
      <div class="example-prompt">
        <span class="prompt-type-tag tag-midj">MIDJOURNEY</span>
        <p>Aesthetic lifestyle flat lay, <span class="placeholder">[brand color palette, e.g. warm neutral tones]</span>, content creator workspace, laptop, iced coffee, notebook with handwritten notes, phone showing social stats, soft window light, clean white desk, overhead shot, magazine quality --ar 4:5 --v 6 --style raw</p>
      </div>
      <div class="examples-label">Prompt 3 — Bold Graphic with Text (Ideogram) 📋</div>
      <div class="example-prompt">
        <span class="prompt-type-tag tag-ideogram">IDEOGRAM</span>
        <p>Bold social media graphic, text overlay reading "<span class="placeholder">[your hook or title]</span>". Background: <span class="placeholder">[vibrant gradient / solid color]</span>. Large bold high-contrast text. Color scheme: <span class="placeholder">[brand colors]</span>. Modern creator aesthetic. 9:16 vertical. <span class="instruction">text legible</span></p>
      </div>
      <div class="examples-label">Prompt 4 — Grok Imagine Quick Visual 📋</div>
      <div class="example-prompt">
        <span class="prompt-type-tag tag-galaxy">GROK IMAGINE</span>
        <p>Create a <span class="placeholder">[aesthetic style, e.g. soft glowy, dark and moody, vibrant colorful]</span> image of <span class="placeholder">[your subject / scene]</span> for a <span class="placeholder">[your niche]</span> creator brand. Color palette: <span class="placeholder">[your brand colors]</span>. Mood: <span class="placeholder">[empowering / cozy / professional / aspirational]</span>. No text in image.</p>
      </div>
      <div class="card-divider"></div>
      <div class="pro-tip">💡 <strong>Pro Tip:</strong> Ideogram is the ONLY free AI tool that reliably puts readable text in images — making it the best choice for covers, thumbnails, and any graphic that needs words. Always end your Ideogram prompts with "text legible."</div>
      <div class="avoid-block">🚫 <strong>Avoid:</strong> Over-specifying every detail. Add "surprise me with the layout while keeping these constraints" — AI often creates better compositions with slight creative freedom.</div>
    </div>
  </div>

  <!-- ═══ CARD 6: RESEARCH ═══ -->
  <div class="prompt-card pc-research">
    <div class="prompt-header">
      <div class="prompt-emoji-box">🔍</div>
      <div class="prompt-header-text">
        <span class="prompt-num">CATEGORY 06</span>
        <h2>Research Prompts</h2>
        <div class="prompt-tagline">Use AI to research your niche, competitors, trending topics, and audience pain points.</div>
      </div>
    </div>
    <div class="prompt-body">
      <div class="what-it-does">The most successful creators deeply understand their audience, niche, and landscape. AI is the fastest research tool ever built. Use these to understand who your audience is, what they struggle with, what's trending, and where the gaps are.</div>
      <div class="examples-label">Prompt 1 — Audience Pain Point Map 📋</div>
      <div class="example-prompt">
        <span class="prompt-type-tag tag-perplexity">USE PERPLEXITY</span>
        <p>I create content for <span class="placeholder">[your target audience, e.g. women in their 20s-30s who want to start making money online]</span>. Give me:<br><br>
        1. Their top 10 fears, frustrations, and limiting beliefs<br>
        2. Their top 5 desired outcomes (what does "winning" look like?)<br>
        3. The exact phrases they use to describe their problems (mirror their words)<br>
        4. Content types that make them say "this creator gets me"<br>
        5. Objections they have to buying products in this space</p>
      </div>
      <div class="examples-label">Prompt 2 — Competitor &amp; Gap Analysis 📋</div>
      <div class="example-prompt">
        <span class="copy-tag">COPY THIS</span>
        <p>Analyze the content landscape for <span class="placeholder">[your niche]</span> creators on TikTok and Instagram:<br><br>
        1. Topics being over-covered (angles I should avoid)<br>
        2. Gaps being under-covered (spaces I could own)<br>
        3. Top 3 creator archetypes and which has room for a new creator<br>
        4. Which content style is least crowded right now<br>
        5. A unique positioning statement to differentiate me from typical creators</p>
      </div>
      <div class="examples-label">Prompt 3 — Trending Topic Finder 📋</div>
      <div class="example-prompt">
        <span class="prompt-type-tag tag-perplexity">USE PERPLEXITY</span>
        <p>What topics and trends in the <span class="placeholder">[your niche]</span> space are getting attention on social media right now? Give me 10 trending angles, why each is trending, and a content angle I could use to enter that conversation with a fresh perspective. Focus on trends relevant for the next 2–4 weeks.</p>
      </div>
      <div class="card-divider"></div>
      <div class="pro-tip">💡 <strong>Pro Tip:</strong> Use Perplexity AI (not ChatGPT) for research — it searches the live internet with citations. Information is current, not from 2023 training data.</div>
      <div class="avoid-block">🚫 <strong>Avoid:</strong> Doing this research once and never revisiting. Run the trending topics prompt weekly and the pain point map monthly. Your audience's language evolves constantly.</div>
    </div>
  </div>

  <!-- ═══ CARD 7: OFFER CREATION ═══ -->
  <div class="prompt-card pc-offer">
    <div class="prompt-header">
      <div class="prompt-emoji-box">💰</div>
      <div class="prompt-header-text">
        <span class="prompt-num">CATEGORY 07</span>
        <h2>Offer Creation Prompts</h2>
        <div class="prompt-tagline">Generate digital product ideas, pricing strategies, and sales copy for your offers.</div>
      </div>
    </div>
    <div class="prompt-body">
      <div class="what-it-does">Most creators wait too long to sell something. These prompts take you from "I don't know what to sell" to "I have a complete offer with a name, price, description, and sales copy" in one session.</div>
      <div class="examples-label">Prompt 1 — Digital Product Generator 📋</div>
      <div class="example-prompt">
        <span class="copy-tag">COPY THIS</span>
        <p>I'm a <span class="placeholder">[your niche]</span> creator who knows about <span class="placeholder">[list 3–5 things you know well]</span>. My audience's #1 struggle is <span class="placeholder">[pain point]</span>.<br><br>
        Generate 10 digital product ideas. For each: catchy name · format (PDF/checklist/template/course) · problem it solves · price ($5–$97) · time to create · which to make first.</p>
      </div>
      <div class="examples-label">Prompt 2 — Product Description That Converts 📋</div>
      <div class="example-prompt">
        <span class="copy-tag">COPY THIS</span>
        <p>Write a product description for "<span class="placeholder">[product name]</span>" at <span class="placeholder">[price]</span>.<br><br>
        Buyer: <span class="placeholder">[describe them]</span> · Struggle before finding this: <span class="placeholder">[the problem]</span> · What's inside: <span class="placeholder">[3–5 things]</span> · Transformation after: <span class="placeholder">[their result]</span><br><br>
        Lead with transformation, not features. Under 200 words. End with a CTA with mild urgency.</p>
      </div>
      <div class="examples-label">Prompt 3 — Bundle &amp; Pricing Strategy 📋</div>
      <div class="example-prompt">
        <span class="copy-tag">COPY THIS</span>
        <p>I have these products: <span class="placeholder">[list your products + prices]</span>. Help me:<br><br>
        1. Create 2–3 bundle offers to increase average order value<br>
        2. Suggest optimal prices based on perceived value<br>
        3. Write a one-sentence pitch for each bundle<br>
        4. Suggest one irresistible low-ticket offer (under $17) to use as a tripwire</p>
      </div>
      <div class="card-divider"></div>
      <div class="pro-tip">💡 <strong>Pro Tip:</strong> Ask AI: "Which of these 10 products would be most likely to go viral as a TikTok, and why?" Products that make great content are often the same ones that sell best.</div>
      <div class="avoid-block">🚫 <strong>Avoid:</strong> Pricing based on effort. Price based on value and transformation. A $17 checklist that saves someone 5 hours a week is worth more than a $97 guide they'll never finish.</div>
    </div>
  </div>

  <!-- ═══ CARD 8: EMAIL WRITING ═══ -->
  <div class="prompt-card pc-email">
    <div class="prompt-header">
      <div class="prompt-emoji-box">📧</div>
      <div class="prompt-header-text">
        <span class="prompt-num">CATEGORY 08</span>
        <h2>Email Writing Prompts</h2>
        <div class="prompt-tagline">Write welcome sequences, promotional emails, and follow-up messages with AI assistance.</div>
      </div>
    </div>
    <div class="prompt-body">
      <div class="what-it-does">Your email list is the only audience you truly own. Social media platforms come and go — but your list is yours forever. These prompts write every email you'll ever need: welcome sequences, launch emails, re-engagement campaigns, and follow-up sequences.</div>
      <div class="examples-label">Prompt 1 — 5-Email Welcome Sequence 📋</div>
      <div class="example-prompt">
        <span class="copy-tag">COPY THIS</span>
        <p>Write a 5-email welcome sequence for new subscribers. Context:<br><br>
        Niche: <span class="placeholder">[your niche]</span> · Audience: <span class="placeholder">[who they are]</span> · Lead magnet: <span class="placeholder">[what they signed up for]</span> · Paid offer: <span class="placeholder">[product + price]</span> · Tone: <span class="placeholder">[conversational / warm / direct]</span><br><br>
        📧 <span class="instruction">Email 1 (Day 0):</span> Deliver lead magnet + warm welcome + what to expect<br>
        📧 <span class="instruction">Email 2 (Day 2):</span> My story — why I'm the right person to help<br>
        📧 <span class="instruction">Email 3 (Day 4):</span> Quick win tip they can use today<br>
        📧 <span class="instruction">Email 4 (Day 6):</span> #1 mistake in this space<br>
        📧 <span class="instruction">Email 5 (Day 8):</span> Soft intro to paid offer<br><br>
        Each email under 250 words. Give 5 subject line options per email.</p>
      </div>
      <div class="examples-label">Prompt 2 — Promotional Launch Email 📋</div>
      <div class="example-prompt">
        <span class="copy-tag">COPY THIS</span>
        <p>Write a promo email for my <span class="placeholder">[product name]</span> at <span class="placeholder">[price]</span>. <span class="placeholder">[Launch sale / limited-time bonus]</span> ends <span class="placeholder">[date]</span>.<br><br>
        Open with relatable story · Bridge to product · 3 specific benefits · Testimonial placeholder · Price + what's included + bonus · Urgency + CTA with link placeholder<br><br>
        Give me 5 subject line options ranging from curiosity-based to urgency-based. Under 300 words.</p>
      </div>
      <div class="examples-label">Prompt 3 — Re-Engagement for Cold Subscribers 📋</div>
      <div class="example-prompt">
        <span class="copy-tag">COPY THIS</span>
        <p>Write a re-engagement email for subscribers who haven't opened in 60+ days. Be honest that I've noticed their inactivity. Offer immediate value (a tip or resource). Give an easy yes/no CTA — either engage or unsubscribe (healthy list hygiene).<br><br>
        Niche: <span class="placeholder">[your niche]</span>. Tone: <span class="placeholder">[casual / warm / slightly cheeky]</span>. Under 150 words. 3 subject line options.</p>
      </div>
      <div class="card-divider"></div>
      <div class="pro-tip">💡 <strong>Pro Tip:</strong> Always generate 5 subject lines per email. Open rates depend almost entirely on the subject line — the email content only matters if they open it first.</div>
      <div class="avoid-block">🚫 <strong>Avoid:</strong> Starting every email with "Hey [first name]!" — it screams mass email. Ask AI: "Write an opening line that sounds like I'm talking to one specific person, not a list."</div>
    </div>
  </div>

  <!-- CHEAT SHEET -->
  <div class="section-heading">🗂️ Quick Reference: Right Tool for the Right Task</div>
  <div class="cheat-sheet">
    <h3>Save this as your go-to guide before opening any AI tool 👇</h3>
    <div class="cs-row">
      <div class="cs-dot" style="background:#10a37f; color:#10a37f;"></div>
      <div class="cs-label">Content ideas &amp; brainstorming</div>
      <div class="cs-value">ChatGPT or Claude — both excellent. Give as much niche context as possible upfront.</div>
    </div>
    <div class="cs-row">
      <div class="cs-dot" style="background:#f43f5e; color:#f43f5e;"></div>
      <div class="cs-label">Writing that sounds like you</div>
      <div class="cs-value">Claude — best at matching brand voice, nuanced tone, and human-sounding copy.</div>
    </div>
    <div class="cs-row">
      <div class="cs-dot" style="background:#0ea5e9; color:#0ea5e9;"></div>
      <div class="cs-label">Current trends &amp; research</div>
      <div class="cs-value">Perplexity AI — real-time internet search with citations. Way better than ChatGPT for research.</div>
    </div>
    <div class="cs-row">
      <div class="cs-dot" style="background:#ff6b35; color:#ff6b35;"></div>
      <div class="cs-label">Social &amp; trend-aware content</div>
      <div class="cs-value">Grok (built into X) — best for content tied to X/Twitter trends, meme formats, and real-time events.</div>
    </div>
    <div class="cs-row">
      <div class="cs-dot" style="background:#6366f1; color:#6366f1;"></div>
      <div class="cs-label">Graphics with text (covers, thumbnails)</div>
      <div class="cs-value">Ideogram — best FREE tool for readable text in AI images. Always add "text legible" to prompts.</div>
    </div>
    <div class="cs-row">
      <div class="cs-dot" style="background:#f59e0b; color:#f59e0b;"></div>
      <div class="cs-label">Artistic &amp; aesthetic visuals</div>
      <div class="cs-value">Midjourney (paid) or Adobe Firefly (free) — unmatched for stylized brand imagery.</div>
    </div>
    <div class="cs-row">
      <div class="cs-dot" style="background:#10b981; color:#10b981;"></div>
      <div class="cs-label">Video editing &amp; repurposing</div>
      <div class="cs-value">CapCut AI (free editing) + Opus Clip (long-to-short repurposing) — the best free combo.</div>
    </div>
    <div class="cs-row">
      <div class="cs-dot" style="background:#a855f7; color:#a855f7;"></div>
      <div class="cs-label">Faceless / avatar video</div>
      <div class="cs-value">HeyGen (free tier) or Synthesia — create presenter videos without showing your face.</div>
    </div>
    <div class="cs-row">
      <div class="cs-dot" style="background:#ec4899; color:#ec4899;"></div>
      <div class="cs-label">AI voiceovers &amp; audio</div>
      <div class="cs-value">ElevenLabs (voice) + Suno (music) — the most realistic voice + the best AI music generator.</div>
    </div>
    <div class="cs-row">
      <div class="cs-dot" style="background: linear-gradient(135deg,#a855f7,#6366f1); color:#a855f7;"></div>
      <div class="cs-label">Access to 5000+ AI tools at once</div>
      <div class="cs-value">Galaxy.AI — all-in-one AI hub. The ultimate aggregator for discovering and using any AI tool fast.</div>
    </div>
  </div>

  <!-- GOLDEN RULE -->
  <div class="golden-rule">
    <span class="gr-emoji">🤖✨</span>
    <h3>The #1 Rule of Using AI as a Creator</h3>
    <p>AI is your <strong>first draft machine</strong>, not your ghostwriter. Use it to kill the blank page and beat creative blocks. Then spend 10–20 minutes rewriting in your voice, adding your real stories, your humor, your specific lived experience. The creators winning with AI right now aren't posting the most AI content — they're using AI to create <em>more human content, faster</em>. That's your unfair advantage.</p>
  </div>

  <!-- FINAL QUOTE -->
  <div class="final-quote">
    <span class="fq-emoji">🌌</span>
    <p>The prompt is the skill.<br/>Master the prompt, master the universe.</p>
    <div class="fq-sub">Now go build something the galaxy has never seen. 🚀💜</div>
  </div>

</div>
</body>
</html>
