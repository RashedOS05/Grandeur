---
publish: true
created: 2026-05-18T02:24:49.505+03:00
modified: 2026-05-27T16:31:07.867+03:00
---

```dataviewjs
// ============================================================
// IT Systems Analyst — Career Roadmap
// DataviewJS block — paste into any Obsidian note
// ============================================================

const css = `
.rm-wrap { font-family: var(--font-interface); padding: 0.5rem 0; }
.rm-hero { margin-bottom: 1.5rem; }
.rm-hero-title { font-size: 20px; font-weight: 600; color: var(--text-normal); margin-bottom: 4px; }
.rm-hero-sub { font-size: 13px; color: var(--text-muted); line-height: 1.6; }
.rm-summary { display: grid; grid-template-columns: repeat(4,1fr); gap: 10px; margin-bottom: 1.5rem; }
.rm-metric { background: var(--background-secondary); border-radius: 8px; padding: 0.75rem 1rem; }
.rm-metric-label { font-size: 11px; color: var(--text-muted); margin-bottom: 3px; }
.rm-metric-value { font-size: 20px; font-weight: 600; color: var(--text-normal); }
.rm-metric-sub { font-size: 11px; color: var(--text-faint); margin-top: 2px; }
.rm-progress-wrap { margin-bottom: 1.5rem; }
.rm-progress-label { font-size: 11px; color: var(--text-muted); margin-bottom: 5px; display: flex; justify-content: space-between; }
.rm-bar-track { background: var(--background-modifier-border); border-radius: 4px; height: 6px; overflow: hidden; }
.rm-bar-fill { height: 100%; border-radius: 4px; transition: width 0.4s; }
.rm-tabs { display: flex; gap: 6px; flex-wrap: wrap; margin-bottom: 1.25rem; }
.rm-tab { font-size: 12px; padding: 5px 12px; border-radius: 20px; border: 1px solid var(--background-modifier-border); background: transparent; color: var(--text-muted); cursor: pointer; }
.rm-tab.rm-active { background: var(--text-normal); color: var(--background-primary); border-color: transparent; }
.rm-phase { margin-bottom: 1.5rem; display: none; }
.rm-phase.rm-visible { display: block; }
.rm-phase-header { display: flex; align-items: center; gap: 10px; margin-bottom: 1rem; padding-bottom: 8px; border-bottom: 1px solid var(--background-modifier-border); }
.rm-phase-dot { width: 12px; height: 12px; border-radius: 50%; flex-shrink: 0; }
.rm-phase-title { font-size: 15px; font-weight: 600; color: var(--text-normal); }
.rm-phase-period { font-size: 12px; color: var(--text-muted); margin-left: auto; }
.rm-phase-load { font-size: 11px; padding: 2px 8px; border-radius: 3px; font-weight: 500; }
.rm-load-low { background: #E1F5EE; color: #0F6E56; }
.rm-load-med { background: #E6F1FB; color: #185FA5; }
.rm-load-high { background: #FCEBEB; color: #A32D2D; }
.rm-section { margin-bottom: 1.1rem; }
.rm-section-title { font-size: 11px; font-weight: 600; color: var(--text-muted); text-transform: uppercase; letter-spacing: 0.05em; margin-bottom: 0.6rem; }
.rm-items { display: flex; flex-direction: column; gap: 6px; }
.rm-item { display: flex; align-items: flex-start; gap: 10px; background: var(--background-primary); border: 1px solid var(--background-modifier-border); border-radius: 8px; padding: 9px 12px; cursor: pointer; transition: border-color 0.15s; }
.rm-item:hover { border-color: var(--interactive-accent); }
.rm-item.rm-done { border-left: 3px solid #1D9E75; opacity: 0.7; }
.rm-item.rm-done .rm-item-title { text-decoration: line-through; color: var(--text-muted); }
.rm-checkbox { width: 16px; height: 16px; border-radius: 4px; border: 1.5px solid var(--background-modifier-border-hover); flex-shrink: 0; margin-top: 1px; display: flex; align-items: center; justify-content: center; transition: all 0.15s; }
.rm-checkbox.checked { background: #1D9E75; border-color: #1D9E75; }
.rm-checkmark { color: white; font-size: 10px; font-weight: 700; }
.rm-item-body { flex: 1; min-width: 0; }
.rm-item-title { font-size: 13px; font-weight: 500; color: var(--text-normal); margin-bottom: 2px; }
.rm-item-desc { font-size: 11px; color: var(--text-muted); line-height: 1.5; }
.rm-item-tag { display: inline-block; font-size: 10px; padding: 1px 6px; border-radius: 3px; margin-top: 4px; margin-right: 4px; font-weight: 500; }
.rm-tag-cert { background: #EEEDFE; color: #3C3489; }
.rm-tag-academic { background: #E6F1FB; color: #185FA5; }
.rm-tag-career { background: #E1F5EE; color: #0F6E56; }
.rm-tag-brand { background: #FAEEDA; color: #854F0B; }
.rm-tag-free { background: var(--background-secondary); color: var(--text-muted); }
.rm-warn { background: #FAEEDA; border-radius: 8px; padding: 10px 12px; font-size: 12px; color: #854F0B; margin-top: 0.75rem; line-height: 1.6; }
.rm-profile { margin-top: 0.5rem; }
.rm-profile-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 8px; }
.rm-profile-card { background: var(--background-primary); border: 1px solid var(--background-modifier-border); border-radius: 8px; padding: 10px 12px; }
.rm-profile-label { font-size: 11px; color: var(--text-muted); margin-bottom: 4px; font-weight: 600; text-transform: uppercase; letter-spacing: 0.04em; }
.rm-profile-value { font-size: 12px; color: var(--text-normal); line-height: 1.6; }
.rm-risks { margin-top: 0.5rem; display: flex; flex-direction: column; gap: 6px; }
.rm-risk { display: flex; gap: 10px; background: var(--background-primary); border: 1px solid var(--background-modifier-border); border-left: 3px solid #EF9F27; border-radius: 8px; padding: 9px 12px; }
.rm-risk-label { font-size: 12px; font-weight: 500; color: var(--text-normal); margin-bottom: 2px; }
.rm-risk-fix { font-size: 11px; color: var(--text-muted); }
.rm-overview-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 8px; margin-bottom: 1rem; }
.rm-overview-card { background: var(--background-primary); border: 1px solid var(--background-modifier-border); border-radius: 8px; padding: 10px 12px; }
.rm-ov-phase { font-size: 10px; font-weight: 600; text-transform: uppercase; letter-spacing: 0.05em; margin-bottom: 4px; }
.rm-ov-items { font-size: 11px; color: var(--text-muted); line-height: 1.7; }
.rm-ov-done { color: #1D9E75; font-weight: 500; }
`;

// ── Data ─────────────────────────────────────────────────────
const PHASES = [
  {
    id: 'overview',
    label: 'Overview',
    color: '#888780',
  },
  {
    id: 'p1',
    label: 'Phase 1',
    period: 'Summer 2026',
    load: 'low',
    color: '#1D9E75',
    sections: [
      {
        title: 'Academic',
        items: [
          { id: 'p1-a1', title: 'CSC 301 — Web Application Development', desc: 'Treat every assignment as a portfolio piece. Document and push to GitHub.', tags: ['academic'] },
          { id: 'p1-a2', title: 'MATH 140 — Linear Algebra', desc: 'Foundational for data and analytics work later.', tags: ['academic'] },
          { id: 'p1-a3', title: 'ENVR 103', desc: 'Free elective — completes your free elective requirement entirely.', tags: ['academic'] },
        ]
      },
      {
        title: 'Self-Learning',
        items: [
          { id: 'p1-s1', title: 'Google Data Analytics Certificate', desc: 'Coursera, ~2 months, ~$50/month. Covers SQL, spreadsheets, Tableau, R, data storytelling. Fills the data pillar and diversifies credentials away from Meta/Harvard.', tags: ['cert'] },
        ]
      },
      {
        title: 'Personal Brand',
        items: [
          { id: 'p1-b1', title: 'Update LinkedIn headline', desc: '"CS Student | Aspiring IT Systems Analyst | React Native · Web Dev · Data Analytics"', tags: ['brand'] },
          { id: 'p1-b2', title: 'Post CSC 301 project on completion', desc: 'Document what you built, the problem it solved, and tech used.', tags: ['brand'] },
          { id: 'p1-b3', title: 'Post Google cert on completion', desc: 'Keep the consistent posting momentum going.', tags: ['brand'] },
        ]
      }
    ],
    endNote: 'Profile adds: Google Data Analytics cert + CSC 301 GitHub project'
  },
  {
    id: 'p2',
    label: 'Phase 2',
    period: 'Fall 2026',
    load: 'high',
    color: '#378ADD',
    sections: [
      {
        title: 'Academic — Priority',
        items: [
          { id: 'p2-a1', title: 'CSC 350 — Software Engineering', desc: 'Requirements gathering, system design, project lifecycle — this is literally your future job. Pay close attention.', tags: ['academic'] },
          { id: 'p2-a2', title: 'CSC 473 — Computer Networks', desc: 'Systems analysts are expected to understand infrastructure. Don\'t coast through this one.', tags: ['academic'] },
          { id: 'p2-a3', title: 'CSC 476 — Operating Systems', desc: 'Core systems knowledge. Needed for CSC 477 later.', tags: ['academic'] },
          { id: 'p2-a4', title: 'MATH 331 — Numerical Analysis', desc: 'Heavy math. Prioritize passing over perfecting.', tags: ['academic'] },
          { id: 'p2-a5', title: 'PHIL 245 — Ethics and the Computer', desc: 'Required for Capstone eligibility. Don\'t neglect it.', tags: ['academic'] },
        ]
      },
      {
        title: 'Self-Learning — Light Touch Only',
        items: [
          { id: 'p2-s1', title: 'Microsoft Azure Fundamentals (AZ-900)', desc: 'Free via Microsoft Learn. 1–2 hours/week max. Kuwait enterprise runs heavily on Microsoft stack. No exam needed yet — just build familiarity.', tags: ['cert', 'free'] },
        ]
      },
      {
        title: 'Personal Brand',
        items: [
          { id: 'p2-b1', title: 'Post 1–2 times about CSC 350', desc: 'Share what you\'re learning about system design and requirements. Signals analyst-track thinking to recruiters.', tags: ['brand'] },
          { id: 'p2-b2', title: 'Engage consistently — comments over posts', desc: 'Commenting on others\' posts drives more visibility than posting into the void.', tags: ['brand'] },
        ]
      }
    ],
    warn: '⚠️ This is your hardest semester. Academic performance here directly affects CGPA and Capstone eligibility. External learning is strictly secondary.',
    endNote: 'Profile adds: Azure awareness + Software Engineering foundation'
  },
  {
    id: 'p3',
    label: 'Phase 3',
    period: 'Spring 2027',
    load: 'med',
    color: '#7F77DD',
    sections: [
      {
        title: 'Capstone — Your Biggest Career Asset',
        items: [
          { id: 'p3-a1', title: 'Frame Capstone as a real enterprise system', desc: 'Good topics: inventory management, HR workflow automation, procurement tracker, hospital appointment system. Bad topics: generic CRUD apps, games, anything non-business.', tags: ['academic'] },
          { id: 'p3-a2', title: 'Document it like a real systems analyst would', desc: 'Requirements doc, ERD, system diagrams, stakeholder analysis, README on GitHub. This is the centerpiece of every job interview.', tags: ['academic'] },
          { id: 'p3-a3', title: 'CSC 477 — Security in Computing', desc: 'Required for Senior Standing courses. Keep it steady.', tags: ['academic'] },
          { id: 'p3-a4', title: 'CSC 492 — Practicum', desc: 'Needs CSC 473 done from Fall 2026. Confirm coreq status with advisor.', tags: ['academic'] },
        ]
      },
      {
        title: 'Self-Learning',
        items: [
          { id: 'p3-s1', title: 'ECBA Exam Prep — Starweaver (Coursera)', desc: '4.8 stars, 1–4 weeks. Start mid-semester. Prepares you for the actual IIBA exam in Summer 2027.', tags: ['cert'] },
          { id: 'p3-s2', title: 'Microsoft Power Platform Fundamentals (PL-900)', desc: 'Free via Microsoft Learn. Power BI is used heavily in Gulf enterprise for reporting and dashboards. Systems analysts build and interpret these constantly.', tags: ['cert', 'free'] },
        ]
      },
      {
        title: 'Internship',
        items: [
          { id: 'p3-c1', title: 'Apply for CSC 399 — Internship', desc: 'Target: IT department at a bank, telecom, or government body. One semester of enterprise exposure transforms your CV. Use your uncle\'s network as a sounding board even if not a direct referral.', tags: ['career'] },
        ]
      },
      {
        title: 'Personal Brand',
        items: [
          { id: 'p3-b1', title: 'Document Capstone in 2–3 LinkedIn posts', desc: 'Problem you tackled → your process → outcome. Shows real project thinking.', tags: ['brand'] },
          { id: 'p3-b2', title: 'Start connecting with IT managers in Kuwait', desc: 'Specifically systems analysts, IT business analysts, and digital transformation leads at your target employers.', tags: ['brand'] },
        ]
      }
    ],
    endNote: 'Profile adds: Capstone project, ECBA prep done, Power BI awareness, internship (target)'
  },
  {
    id: 'p4',
    label: 'Phase 4',
    period: 'Summer 2027',
    load: 'low',
    color: '#D85A30',
    sections: [
      {
        title: 'Credentials — Finish Strong',
        items: [
          { id: 'p4-s1', title: 'Sit the ECBA Exam', desc: 'Register at iiba.org. IIBA student membership ~$50/year + exam fee ~$90 = ~$140 total. No experience requirement. The only internationally recognized BA cert with no work experience needed.', tags: ['cert'] },
          { id: 'p4-s2', title: 'IBM Business Analyst Professional Certificate', desc: 'Coursera, ~3 months. Covers process modeling, requirements, stakeholder analysis, enterprise tools. IBM name diversifies your credential sources completely (Harvard, Meta, Google, IBM).', tags: ['cert'] },
        ]
      },
      {
        title: 'Job Hunting — Start Now, Not After Graduating',
        items: [
          { id: 'p4-c1', title: 'Build a clean 1-page CV', desc: 'Separate from LinkedIn. Tailored for systems analyst roles. Lead with skills and projects, not just academic history.', tags: ['career'] },
          { id: 'p4-c2', title: 'CITRA — Kuwait Telecom Regulator', desc: 'IT roles, Kuwaitization built in structurally. Stable, government-adjacent, reasonable hours.', tags: ['career'] },
          { id: 'p4-c3', title: 'NBK / Gulf Bank / CBK', desc: 'Banking sector IT analyst roles. Stable, decent pay, structured environment.', tags: ['career'] },
          { id: 'p4-c4', title: 'Agility Logistics', desc: 'Growing fast in Kuwait, tech-forward, less bureaucratic than banks.', tags: ['career'] },
          { id: 'p4-c5', title: 'Zain / Ooredoo', desc: 'Kuwaitization quota works in your favor. Technical profile counters the usual bias against local hires.', tags: ['career'] },
          { id: 'p4-c6', title: 'Kuwait Municipality / MOCI / Ministry of Finance', desc: 'Actively digitizing under Vision 2035. Systems analysts are exactly what they need.', tags: ['career'] },
          { id: 'p4-c7', title: 'Apply via Bayt.com, LinkedIn Jobs, Naukrigulf, Tanqeeb', desc: 'Use all four. Tanqeeb is Arabic-first and catches listings the others miss.', tags: ['career'] },
        ]
      }
    ],
    endNote: 'Graduate. ECBA certified. IBM cert. Applications live.'
  },
  {
    id: 'profile',
    label: 'Final Profile',
    color: '#639922',
  },
  {
    id: 'risks',
    label: 'Risks',
    color: '#BA7517',
  },
];

const PROFILE = [
  { label: 'Degree', value: 'BS Computer Science — GUST' },
  { label: 'Technical', value: 'React Native, Python, Web Dev, Databases, Networks, OS' },
  { label: 'Data', value: 'Google Data Analytics (SQL, Tableau, R, spreadsheets)' },
  { label: 'Enterprise', value: 'Azure Fundamentals, Power Platform (Power BI), IBM Business Analyst' },
  { label: 'Business Analysis', value: 'ECBA certified, CSC 350 Software Engineering foundation' },
  { label: 'Projects', value: 'Capstone enterprise system, CSC 301 web project, CS50P farming sim, GitHub active' },
  { label: 'Work Experience', value: 'Testlio QA contract, CSC 399 internship (target)' },
  { label: 'Credentials', value: 'Harvard CS50P, Meta React Native, Google Data Analytics, IBM BA, ECBA' },
  { label: 'Personal Brand', value: '700+ LinkedIn followers, consistent posting, Kuwaiti national' },
];

const RISKS = [
  { risk: 'Fall 2026 overload causes grade drops', fix: 'Keep external learning minimal — Azure only, 1–2 hrs/week max' },
  { risk: 'Capstone topic is too generic', fix: 'Fight for an enterprise-framed topic early in the semester' },
  { risk: 'CSC 399 internship not available', fix: 'Push hard in Spring 2027, use uncle\'s network as sounding board' },
  { risk: 'Major electives don\'t open', fix: 'Skills gap filled externally — this roadmap accounts for that entirely' },
  { risk: 'CGPA stays at 2.79 or drops', fix: 'Certs + projects + internship compensate; Gulf employers weigh these heavily' },
  { risk: 'Private sector bias against Kuwaiti hires', fix: 'GitHub + certs + internship prove you\'re not the stereotype. Target Kuwaitization-quota employers first.' },
];

// ── State ─────────────────────────────────────────────────────
const checked = JSON.parse(localStorage.getItem('rm_checked') || '{}');

function saveChecked() {
  try { localStorage.setItem('rm_checked', JSON.stringify(checked)); } catch(e) {}
}

function totalItems() {
  let t = 0;
  PHASES.forEach(p => { if (p.sections) p.sections.forEach(s => t += s.items.length); });
  return t;
}

function doneItems() {
  return Object.values(checked).filter(Boolean).length;
}

// ── Build DOM ─────────────────────────────────────────────────
const root = dv.el('div', '', { cls: 'rm-wrap' });
const styleEl = root.createEl('style');
styleEl.textContent = css;

// Hero
const hero = root.createEl('div', { cls: 'rm-hero' });
hero.createEl('div', { cls: 'rm-hero-title', text: '🗺️ IT Systems Analyst — Career Roadmap' });
hero.createEl('div', { cls: 'rm-hero-sub', text: 'Goal: Land an IT Systems Analyst role at a government-adjacent or reputable employer in Kuwait by Summer/Fall 2027' });

// Metrics
const summary = root.createEl('div', { cls: 'rm-summary' });
[
  { label: 'Graduation target', value: 'Summer 2027', sub: '~14 months away' },
  { label: 'Primary role', value: 'Systems Analyst', sub: '#1 in-demand in Kuwait' },
  { label: 'Certs to earn', value: '4', sub: 'Google · Azure · IBM · ECBA' },
  { label: 'Est. cert cost', value: '~$290', sub: 'total across all phases' },
].forEach(m => {
  const card = summary.createEl('div', { cls: 'rm-metric' });
  card.createEl('div', { cls: 'rm-metric-label', text: m.label });
  card.createEl('div', { cls: 'rm-metric-value', text: m.value });
  card.createEl('div', { cls: 'rm-metric-sub', text: m.sub });
});

// Progress bar
const progressWrap = root.createEl('div', { cls: 'rm-progress-wrap' });
const progressLabel = progressWrap.createEl('div', { cls: 'rm-progress-label' });
progressLabel.createEl('span', { text: 'Roadmap completion' });
const progressPct = progressLabel.createEl('span');
const track = progressWrap.createEl('div', { cls: 'rm-bar-track' });
const fill = track.createEl('div', { cls: 'rm-bar-fill' });

function updateProgress() {
  const pct = totalItems() > 0 ? Math.round((doneItems() / totalItems()) * 100) : 0;
  fill.style.width = pct + '%';
  fill.style.background = pct < 30 ? '#378ADD' : pct < 70 ? '#EF9F27' : '#1D9E75';
  progressPct.textContent = pct + '%';
}

// Tabs
const tabs = root.createEl('div', { cls: 'rm-tabs' });
const tabBtns = {};
let activePhase = 'overview';

const tabDefs = [
  { id: 'overview', label: '📋 Overview' },
  { id: 'p1', label: '🟢 Summer 2026' },
  { id: 'p2', label: '🟡 Fall 2026' },
  { id: 'p3', label: '🔵 Spring 2027' },
  { id: 'p4', label: '🔴 Summer 2027' },
  { id: 'profile', label: '🎯 Final Profile' },
  { id: 'risks', label: '⚠️ Risks' },
];

tabDefs.forEach(t => {
  const btn = tabs.createEl('button', { cls: 'rm-tab' + (t.id === activePhase ? ' rm-active' : ''), text: t.label });
  tabBtns[t.id] = btn;
  btn.addEventListener('click', () => {
    activePhase = t.id;
    Object.values(tabBtns).forEach(b => b.removeClass('rm-active'));
    btn.addClass('rm-active');
    renderPhases();
  });
});

// Phases container
const phasesEl = root.createEl('div');

function tagEl(parent, tag) {
  const cls = { cert:'rm-tag-cert', academic:'rm-tag-academic', career:'rm-tag-career', brand:'rm-tag-brand', free:'rm-tag-free' }[tag] || 'rm-tag-free';
  const label = { cert:'Certification', academic:'Academic', career:'Career', brand:'Personal Brand', free:'Free' }[tag] || tag;
  parent.createEl('span', { cls: `rm-item-tag ${cls}`, text: label });
}

function renderItem(parent, item) {
  const isChecked = !!checked[item.id];
  const el = parent.createEl('div', { cls: `rm-item${isChecked ? ' rm-done' : ''}` });
  const box = el.createEl('div', { cls: `rm-checkbox${isChecked ? ' checked' : ''}` });
  if (isChecked) box.createEl('span', { cls: 'rm-checkmark', text: '✓' });
  const body = el.createEl('div', { cls: 'rm-item-body' });
  body.createEl('div', { cls: 'rm-item-title', text: item.title });
  if (item.desc) body.createEl('div', { cls: 'rm-item-desc', text: item.desc });
  const tagsEl = body.createEl('div');
  (item.tags || []).forEach(t => tagEl(tagsEl, t));

  el.addEventListener('click', () => {
    checked[item.id] = !checked[item.id];
    saveChecked();
    el.toggleClass('rm-done', checked[item.id]);
    box.toggleClass('checked', checked[item.id]);
    box.empty();
    if (checked[item.id]) box.createEl('span', { cls: 'rm-checkmark', text: '✓' });
    updateProgress();
  });
}

function renderPhases() {
  phasesEl.empty();

  if (activePhase === 'overview') {
    const grid = phasesEl.createEl('div', { cls: 'rm-overview-grid' });
    [
      { phase: 'Summer 2026', color: '#1D9E75', items: ['Google Data Analytics cert', 'CSC 301 Web Dev', 'MATH 140', 'Update LinkedIn headline'] },
      { phase: 'Fall 2026', color: '#378ADD', items: ['CSC 350 Software Engineering ⚠️', 'CSC 473 Networks', 'CSC 476 OS', 'Azure AZ-900 (light)'] },
      { phase: 'Spring 2027', color: '#7F77DD', items: ['Capstone — enterprise system', 'ECBA prep (Starweaver)', 'Power Platform PL-900', 'CSC 399 Internship'] },
      { phase: 'Summer 2027', color: '#D85A30', items: ['Sit ECBA exam (~$140)', 'IBM Business Analyst cert', 'Build 1-page CV', 'Apply to CITRA, NBK, Agility, Zain…'] },
    ].forEach(p => {
      const card = grid.createEl('div', { cls: 'rm-overview-card' });
      const phaseLabel = card.createEl('div', { cls: 'rm-ov-phase', attr: { style: `color: ${p.color}` } });
      phaseLabel.textContent = p.phase;
      const itemsEl = card.createEl('div', { cls: 'rm-ov-items' });
      p.items.forEach(i => {
        itemsEl.createEl('div', { text: '· ' + i });
      });
    });

    phasesEl.createEl('div', { attr: { style: 'margin-top: 1rem; font-size: 12px; color: var(--text-muted); line-height: 1.8;' }, text: 'Click any phase tab above to see full details, tasks, and check off items.' });
    return;
  }

  if (activePhase === 'profile') {
    const grid = phasesEl.createEl('div', { cls: 'rm-profile-grid' });
    PROFILE.forEach(p => {
      const card = grid.createEl('div', { cls: 'rm-profile-card' });
      card.createEl('div', { cls: 'rm-profile-label', text: p.label });
      card.createEl('div', { cls: 'rm-profile-value', text: p.value });
    });
    phasesEl.createEl('div', { attr: { style: 'margin-top: 1rem; font-size: 12px; color: var(--text-muted); line-height: 1.8;' }, text: 'This is your profile at graduation Summer 2027. Every item here is achievable within the roadmap above.' });
    return;
  }

  if (activePhase === 'risks') {
    const risksEl = phasesEl.createEl('div', { cls: 'rm-risks' });
    RISKS.forEach(r => {
      const el = risksEl.createEl('div', { cls: 'rm-risk' });
      const body = el.createEl('div');
      body.createEl('div', { cls: 'rm-risk-label', text: r.risk });
      body.createEl('div', { cls: 'rm-risk-fix', text: '→ ' + r.fix });
    });
    return;
  }

  const phase = PHASES.find(p => p.id === activePhase);
  if (!phase) return;

  const phaseEl = phasesEl.createEl('div', { cls: 'rm-phase rm-visible' });
  const header = phaseEl.createEl('div', { cls: 'rm-phase-header' });
  header.createEl('div', { cls: 'rm-phase-dot', attr: { style: `background: ${phase.color}` } });
  header.createEl('div', { cls: 'rm-phase-title', text: phase.label + (phase.period ? ' — ' + phase.period : '') });
  if (phase.load) {
    const loadMap = { low: ['Manageable load', 'rm-load-low'], med: ['Moderate load', 'rm-load-med'], high: ['Heavy load ⚠️', 'rm-load-high'] };
    const [text, cls] = loadMap[phase.load];
    header.createEl('span', { cls: `rm-phase-load ${cls}`, text });
  }

  if (phase.sections) {
    phase.sections.forEach(sec => {
      const secEl = phaseEl.createEl('div', { cls: 'rm-section' });
      secEl.createEl('div', { cls: 'rm-section-title', text: sec.title });
      const itemsEl = secEl.createEl('div', { cls: 'rm-items' });
      sec.items.forEach(item => renderItem(itemsEl, item));
    });
  }

  if (phase.warn) {
    phaseEl.createEl('div', { cls: 'rm-warn', text: phase.warn });
  }

  if (phase.endNote) {
    phaseEl.createEl('div', { attr: { style: 'margin-top: 0.75rem; font-size: 12px; color: var(--text-muted); font-style: italic;' }, text: '✓ ' + phase.endNote });
  }
}

renderPhases();
updateProgress();
```
