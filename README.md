
<style>
  @import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;500&family=Inter:wght@300;400;500&display=swap');
  
  * { box-sizing: border-box; margin: 0; padding: 0; }
  
  .readme {
    font-family: 'Inter', var(--font-sans);
    background: #0a0e1a;
    color: #c8d6e5;
    min-height: 600px;
    padding: 40px 32px 48px;
    border-radius: 12px;
    overflow: hidden;
    position: relative;
  }
  
  .bg-grid {
    position: absolute;
    inset: 0;
    background-image: linear-gradient(rgba(99,102,241,0.04) 1px, transparent 1px), linear-gradient(90deg, rgba(99,102,241,0.04) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
  }
  
  .content { position: relative; z-index: 1; }
  
  .header { margin-bottom: 36px; }
  
  .status-bar {
    display: flex;
    align-items: center;
    gap: 8px;
    margin-bottom: 18px;
  }
  
  .status-dot {
    width: 8px; height: 8px;
    border-radius: 50%;
    background: #22d3ee;
    box-shadow: 0 0 0 0 rgba(34,211,238,0.4);
    animation: pulse 2.4s cubic-bezier(.4,0,.6,1) infinite;
  }
  
  @keyframes pulse {
    0%, 100% { box-shadow: 0 0 0 0 rgba(34,211,238,0.35); }
    60% { box-shadow: 0 0 0 6px rgba(34,211,238,0); }
  }
  
  .status-text {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    color: #22d3ee;
    letter-spacing: 0.08em;
    opacity: 0.85;
  }
  
  .name-line {
    font-size: 36px;
    font-weight: 300;
    color: #e2e8f0;
    letter-spacing: -0.02em;
    line-height: 1.1;
    margin-bottom: 6px;
  }
  
  .name-line span {
    font-weight: 500;
    color: #fff;
  }
  
  .role-line {
    font-family: 'JetBrains Mono', monospace;
    font-size: 13px;
    color: #6366f1;
    letter-spacing: 0.04em;
    margin-bottom: 20px;
    display: flex;
    align-items: center;
    gap: 10px;
  }
  
  .role-sep { color: #334155; }
  
  .typing-wrap {
    font-family: 'JetBrains Mono', monospace;
    font-size: 13px;
    color: #94a3b8;
    height: 20px;
    overflow: hidden;
  }
  
  #typed { color: #e2e8f0; }
  
  .cursor {
    display: inline-block;
    width: 2px; height: 14px;
    background: #6366f1;
    margin-left: 2px;
    vertical-align: middle;
    animation: blink .9s step-end infinite;
  }
  
  @keyframes blink { 0%, 100% { opacity: 1; } 50% { opacity: 0; } }
  
  .wave-section {
    margin: 28px 0;
    height: 56px;
    position: relative;
    overflow: hidden;
  }
  
  .wave-svg { width: 100%; height: 100%; }
  
  .wave-path {
    fill: none;
    stroke-width: 1.5;
    stroke-linecap: round;
  }
  
  .w1 { stroke: rgba(99,102,241,0.5); animation: wavemove 4s linear infinite; }
  .w2 { stroke: rgba(34,211,238,0.3); animation: wavemove 5.5s linear infinite reverse; }
  .w3 { stroke: rgba(139,92,246,0.25); animation: wavemove 7s linear infinite; }
  
  @keyframes wavemove {
    0% { stroke-dashoffset: 0; }
    100% { stroke-dashoffset: -200; }
  }
  
  .section-label {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    text-transform: uppercase;
    letter-spacing: 0.14em;
    color: #334155;
    margin-bottom: 14px;
  }
  
  .heatmap-wrap {
    margin: 0 0 32px;
  }
  
  .heatmap-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 12px;
  }
  
  .heatmap-stat {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    color: #22d3ee;
  }
  
  .heatmap-grid {
    display: flex;
    gap: 3px;
    flex-wrap: nowrap;
  }
  
  .hm-col {
    display: flex;
    flex-direction: column;
    gap: 3px;
  }
  
  .hm-cell {
    width: 10px; height: 10px;
    border-radius: 2px;
    transition: transform 0.15s;
    cursor: default;
  }
  
  .hm-cell:hover { transform: scale(1.4); }
  
  .l0 { background: #0f172a; }
  .l1 { background: #1e1b4b; }
  .l2 { background: #3730a3; }
  .l3 { background: #6366f1; }
  .l4 { background: #818cf8; }
  
  .stats-row {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 12px;
    margin-bottom: 28px;
  }
  
  .stat-card {
    background: rgba(255,255,255,0.03);
    border: 0.5px solid rgba(99,102,241,0.15);
    border-radius: 8px;
    padding: 14px 16px;
  }
  
  .stat-num {
    font-family: 'JetBrains Mono', monospace;
    font-size: 22px;
    font-weight: 500;
    color: #e2e8f0;
    line-height: 1;
    margin-bottom: 4px;
  }
  
  .stat-num span { color: #6366f1; }
  
  .stat-label {
    font-size: 11px;
    color: #475569;
    letter-spacing: 0.04em;
  }
  
  .stack-row {
    margin-bottom: 28px;
  }
  
  .stack-items {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }
  
  .tag {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    padding: 4px 10px;
    border-radius: 4px;
    border: 0.5px solid;
    letter-spacing: 0.03em;
    opacity: 0;
    animation: tagfadein 0.3s ease forwards;
  }
  
  .tag.ind { color: #818cf8; border-color: rgba(129,140,248,0.3); background: rgba(99,102,241,0.07); }
  .tag.cyn { color: #67e8f9; border-color: rgba(103,232,249,0.25); background: rgba(34,211,238,0.06); }
  .tag.grn { color: #86efac; border-color: rgba(134,239,172,0.25); background: rgba(74,222,128,0.06); }
  .tag.vlt { color: #c4b5fd; border-color: rgba(196,181,253,0.25); background: rgba(167,139,250,0.07); }
  
  @keyframes tagfadein {
    from { opacity: 0; transform: translateY(4px); }
    to { opacity: 1; transform: translateY(0); }
  }
  
  .signal-bar {
    margin-bottom: 24px;
  }
  
  .bar-track {
    height: 2px;
    background: rgba(255,255,255,0.05);
    border-radius: 2px;
    overflow: hidden;
    margin-bottom: 6px;
    position: relative;
  }
  
  .bar-fill {
    height: 100%;
    border-radius: 2px;
    width: 0%;
    transition: width 1.4s cubic-bezier(.4,0,.2,1);
  }
  
  .bf-ind { background: #6366f1; }
  .bf-cyn { background: #22d3ee; }
  .bf-vlt { background: #a78bfa; }
  .bf-grn { background: #4ade80; }
  
  .bar-meta {
    display: flex;
    justify-content: space-between;
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    color: #334155;
  }
  
  .bar-meta .pct { color: #475569; }
  
  .footer-line {
    border-top: 0.5px solid rgba(99,102,241,0.1);
    padding-top: 18px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    color: #1e293b;
    display: flex;
    gap: 8px;
    align-items: center;
  }
  
  .fl-tag { color: #334155; }
</style>

<div class="readme">
  <div class="bg-grid"></div>
  <div class="content">
    
    <div class="header">
      <div class="status-bar">
        <div class="status-dot"></div>
        <span class="status-text">available for new projects</span>
      </div>
      <h1 class="name-line">Hi, I'm <span>Shane.</span></h1>
      <div class="role-line">
        AI Automation Engineer <span class="role-sep">/</span> Data Scientist
      </div>
      <div class="typing-wrap">
        <span id="typed"></span><span class="cursor"></span>
      </div>
    </div>

    <div class="wave-section">
      <svg class="wave-svg" viewBox="0 0 616 56" preserveAspectRatio="none">
        <path class="wave-path w1" stroke-dasharray="8 4"
          d="M0 28 C30 14,60 42,90 28 C120 14,150 42,180 28 C210 14,240 42,270 28 C300 14,330 42,360 28 C390 14,420 42,450 28 C480 14,510 42,540 28 C570 14,600 42,616 28"/>
        <path class="wave-path w2" stroke-dasharray="12 6"
          d="M0 28 C40 10,80 46,120 28 C160 10,200 46,240 28 C280 10,320 46,360 28 C400 10,440 46,480 28 C520 10,560 46,616 28"/>
        <path class="wave-path w3" stroke-dasharray="4 8"
          d="M0 32 C50 16,100 48,150 32 C200 16,250 48,300 32 C350 16,400 48,450 32 C500 16,550 48,616 32"/>
      </svg>
    </div>

    <div class="heatmap-wrap">
      <div class="heatmap-header">
        <div class="section-label">contribution graph</div>
        <div class="heatmap-stat" id="hm-stat">— commits this year</div>
      </div>
      <div class="heatmap-grid" id="heatmap"></div>
    </div>

    <div class="stats-row">
      <div class="stat-card">
        <div class="stat-num" id="s1">0<span>+</span></div>
        <div class="stat-label">models deployed</div>
      </div>
      <div class="stat-card">
        <div class="stat-num" id="s2">0<span>k</span></div>
        <div class="stat-label">data points processed</div>
      </div>
      <div class="stat-card">
        <div class="stat-num" id="s3">0<span>%</span></div>
        <div class="stat-label">avg automation coverage</div>
      </div>
    </div>

    <div class="stack-row">
      <div class="section-label">current stack</div>
      <div class="stack-items" id="tags"></div>
    </div>

    <div class="signal-bar">
      <div class="section-label">focus areas</div>
      <div id="bars"></div>
    </div>

    <div class="footer-line">
      <span class="fl-tag">// building:</span>
      intelligent systems that sit at the boundary of data and behavior
    </div>

  </div>
</div>

<script>
const phrases = [
  "building AI-powered systems from scratch",
  "turning raw data into decisions",
  "LLMs · NLP · automation workflows",
  "designing for human-centered AI",
  "making models that actually ship"
];

let pi = 0, ci = 0, deleting = false, pause = false;
const typed = document.getElementById('typed');

function typeStep() {
  if (pause) { setTimeout(typeStep, 1200); pause = false; return; }
  const target = phrases[pi];
  if (!deleting) {
    typed.textContent = target.slice(0, ++ci);
    if (ci === target.length) { pause = true; deleting = true; }
    setTimeout(typeStep, 55);
  } else {
    typed.textContent = target.slice(0, --ci);
    if (ci === 0) { deleting = false; pi = (pi + 1) % phrases.length; }
    setTimeout(typeStep, 28);
  }
}
typeStep();

const hm = document.getElementById('heatmap');
const levels = [0,0,0,1,1,2,2,3,4,3,2,1,0,1,2,3,4,3,2,1,0,0,1,2,3,2,1,0,0,1,
                2,3,4,3,2,1,0,1,2,3,4,3,3,2,1,0,0,1,2,3];
let totalCommits = 0;
const cols = 50;
for (let c = 0; c < cols; c++) {
  const col = document.createElement('div');
  col.className = 'hm-col';
  for (let r = 0; r < 7; r++) {
    const cell = document.createElement('div');
    const lvl = Math.max(0, levels[(c * 7 + r) % levels.length] + Math.floor(Math.random() * 2 - 0.5));
    const l = Math.min(4, lvl);
    cell.className = 'hm-cell l' + l;
    if (l > 0) totalCommits += l * 3 + Math.floor(Math.random() * 4);
    col.appendChild(cell);
  }
  hm.appendChild(col);
}
document.getElementById('hm-stat').textContent = totalCommits + ' commits this year';

function animCount(el, target, suffix, duration) {
  let start = null;
  function step(ts) {
    if (!start) start = ts;
    const prog = Math.min((ts - start) / duration, 1);
    const ease = 1 - Math.pow(1 - prog, 3);
    el.querySelector ? 
      (el.firstChild.textContent = Math.round(ease * target)) :
      (el.textContent = Math.round(ease * target) + suffix);
    if (prog < 1) requestAnimationFrame(step);
  }
  requestAnimationFrame(step);
}

const s1 = document.getElementById('s1');
const s2 = document.getElementById('s2');
const s3 = document.getElementById('s3');

setTimeout(() => {
  let v = 0;
  const run = (el, target, span) => {
    let s;
    function step(ts) {
      if (!s) s = ts;
      const p = Math.min((ts - s) / 1200, 1);
      const e = 1 - Math.pow(1 - p, 3);
      el.firstChild.textContent = Math.round(e * target);
      if (p < 1) requestAnimationFrame(step);
    }
    requestAnimationFrame(step);
  };
  run(s1, 24);
  run(s2, 2.4);
  run(s3, 87);
}, 400);

const tags = [
  {label: 'Python', c: 'ind'}, {label: 'LangChain', c: 'cyn'}, {label: 'PyTorch', c: 'ind'},
  {label: 'Transformers', c: 'vlt'}, {label: 'OpenAI API', c: 'grn'}, {label: 'FastAPI', c: 'ind'},
  {label: 'Pandas', c: 'cyn'}, {label: 'LLMOps', c: 'vlt'}, {label: 'Airflow', c: 'grn'},
  {label: 'Docker', c: 'ind'}, {label: 'SQL', c: 'cyn'}, {label: 'RAG', c: 'vlt'},
  {label: 'n8n', c: 'grn'}, {label: 'Scikit-learn', c: 'ind'}
];

const tagsEl = document.getElementById('tags');
tags.forEach((t, i) => {
  const el = document.createElement('span');
  el.className = 'tag ' + t.c;
  el.textContent = t.label;
  el.style.animationDelay = (i * 60) + 'ms';
  tagsEl.appendChild(el);
});

const barData = [
  {label: 'LLM & NLP systems', pct: 90, cls: 'bf-ind'},
  {label: 'Data pipelines & analytics', pct: 78, cls: 'bf-cyn'},
  {label: 'Automation workflows', pct: 85, cls: 'bf-vlt'},
  {label: 'Full stack AI apps', pct: 70, cls: 'bf-grn'}
];

const barsEl = document.getElementById('bars');
barData.forEach(b => {
  const wrap = document.createElement('div');
  wrap.style.marginBottom = '14px';
  const track = document.createElement('div');
  track.className = 'bar-track';
  const fill = document.createElement('div');
  fill.className = 'bar-fill ' + b.cls;
  fill.style.width = '0%';
  track.appendChild(fill);
  const meta = document.createElement('div');
  meta.className = 'bar-meta';
  meta.innerHTML = '<span>' + b.label + '</span><span class="pct">' + b.pct + '%</span>';
  wrap.appendChild(track);
  wrap.appendChild(meta);
  barsEl.appendChild(wrap);
  setTimeout(() => fill.style.width = b.pct + '%', 600);
});
</script>
