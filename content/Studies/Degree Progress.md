---
publish: true
created: 2026-05-13T14:58:20.232+03:00
modified: 2026-05-26T23:50:10.468+03:00
---

```dataviewjs
// ============================================================
// GUST CS Graduation Planner — DataviewJS
// Paste this block into any Obsidian note with Dataview enabled
// ============================================================

const completed = {
  'ENGL 110': 'B', 'ENGL 112': 'B', 'SPAN 101': 'C-', 'MATH 131': 'C-',
  'CSC 123': 'A', 'MCM 101': 'A', 'ECON 101': 'C+', 'SPAN 102': 'C+',
  'CSC 122': 'B+', 'CSC 125': 'A', 'CSC 225': 'A-', 'CSC 226': 'C-',
  'CSC 230': 'A-', 'CSC 300': 'C', 'CSC 325': 'B', 'PHIL 245': '*',
  'MATH 221': 'C', 'MATH 140': 'ELG'
};

const inProgress = ['BIOL 110','BIOL 110L','CSC 270','CSC 313','CSC 361','MATH 132'];

const prereqMap = {
  'BIOL 110': ['ENGL 110'], 'BIOL 110L': ['BIOL 110'],
  'CSC 270': ['CSC 230'], 'CSC 313': ['CSC 225','CSC 300'],
  'CSC 361': ['CSC 313'], 'MATH 132': ['MATH 131'],
  'CSC 350': ['CSC 226'], 'CSC 451': ['CSC 350','CSC 361','PHIL 245'],
  'CSC 473': ['CSC 313','MATH 221'], 'CSC 476': ['CSC 270'],
  'CSC 477': [], 'CSC 492': ['CSC 473','CSC 361'],
  'MATH 232': ['MATH 132'], 'MATH 331': ['MATH 140','MATH 132','CSC 125'],
  'CSC 271': ['CSC 270'], 'CSC 301': ['CSC 226','CSC 361'],
  'CSC 326': ['CSC 226'], 'CSC 351': ['CSC 350'], 'CSC 371': ['CSC 313'],
  'CSC 380': ['CSC 226','CSC 361'], 'CSC 391': ['CSC 226','MATH 221'],
  'CSC 392': ['CSC 313','MATH 221'], 'CSC 399': [], 'CSC 404': ['CSC 361'],
  'CSC 405': ['CSC 226'], 'CSC 410': ['CSC 350'], 'CSC 420': ['CSC 350'],
  'CSC 428': ['CSC 226','CSC 270'], 'CSC 430': ['CSC 313'],
  'CSC 444': ['CSC 226','MATH 140','MATH 221'], 'CSC 474': ['CSC 473'],
  'CSC 478': ['CSC 477'], 'CSC 479': [], 'CSC 235': ['CSC 225'],
  'CSC 290': ['CSC 125','MATH 221'], 'Arab Heritage': [],
  'PHIL 190': [], 'MCM 105': []
};

const allCourses = [
  { code:'ENGL 110', name:'English Composition I', cat:'Gen Ed — Core' },
  { code:'ENGL 112', name:'English Composition II', cat:'Gen Ed — Core' },
  { code:'SPAN 101', name:'Spanish I', cat:'Gen Ed — Core' },
  { code:'MATH 131', name:'Calculus I', cat:'Gen Ed — Core' },
  { code:'CSC 123', name:'Fundamentals of Web Design', cat:'Gen Ed — Core' },
  { code:'Arab Heritage', name:'Arab Heritage & Cultural Diversity', cat:'Gen Ed — Core' },
  { code:'MCM 101', name:'Media Literacy', cat:'Gen Ed — Explore' },
  { code:'ECON 101', name:'Principles of Microeconomics', cat:'Gen Ed — Explore' },
  { code:'PHIL 245', name:'Ethics and the Computer', cat:'Gen Ed — Explore' },
  { code:'SPAN 102', name:'Spanish II', cat:'Gen Ed — Explore' },
  { code:'MATH 132', name:'Calculus II', cat:'Gen Ed — Explore' },
  { code:'BIOL 110', name:'Biology I', cat:'Gen Ed — Science' },
  { code:'BIOL 110L', name:'Biology I Lab', cat:'Gen Ed — Science' },
  { code:'CSC 122', name:'Computational Problem Solving', cat:'Major Core' },
  { code:'CSC 125', name:'Object Oriented Programming I', cat:'Major Core' },
  { code:'CSC 225', name:'Programming and Data Structures', cat:'Major Core' },
  { code:'CSC 226', name:'Object Oriented Programming II', cat:'Major Core' },
  { code:'CSC 230', name:'Digital Systems', cat:'Major Core' },
  { code:'CSC 300', name:'Discrete Structures', cat:'Major Core' },
  { code:'CSC 325', name:'Concepts of Programming Languages', cat:'Major Core' },
  { code:'CSC 270', name:'Computer Systems: Architecture', cat:'Major Core' },
  { code:'CSC 313', name:'Design and Analysis of Algorithms', cat:'Major Core' },
  { code:'CSC 350', name:'Software Engineering', cat:'Major Core' },
  { code:'CSC 361', name:'Database Management Systems', cat:'Major Core' },
  { code:'CSC 451', name:'Capstone Project', cat:'Major Core' },
  { code:'CSC 473', name:'Computer Networks & Communications', cat:'Major Core' },
  { code:'CSC 476', name:'Operating Systems', cat:'Major Core' },
  { code:'CSC 477', name:'Security in Computing', cat:'Major Core' },
  { code:'CSC 492', name:'Practicum in Computer Science', cat:'Major Core' },
  { code:'MATH 221', name:'Applied Statistics', cat:'Major Math' },
  { code:'MATH 140', name:'Elementary Linear Algebra', cat:'Major Math' },
  { code:'MATH 232', name:'Intro to Differential Equations', cat:'Major Math' },
  { code:'MATH 331', name:'Numerical Analysis', cat:'Major Math' },
  { code:'CSC 235', name:'Programming Challenges', cat:'Major Elective' },
  { code:'CSC 271', name:'Computer Systems: Programming', cat:'Major Elective' },
  { code:'CSC 290', name:'Data Science', cat:'Major Elective' },
  { code:'CSC 301', name:'Web Application Development', cat:'Major Elective' },
  { code:'CSC 326', name:'OO Design Patterns', cat:'Major Elective' },
  { code:'CSC 351', name:'Software Requirements & Biz Analysis', cat:'Major Elective' },
  { code:'CSC 371', name:'Data and Software Security', cat:'Major Elective' },
  { code:'CSC 380', name:'Mobile Application Development', cat:'Major Elective' },
  { code:'CSC 391', name:'Data Visualization', cat:'Major Elective' },
  { code:'CSC 392', name:'Machine Learning', cat:'Major Elective' },
  { code:'CSC 399', name:'Internship in CS', cat:'Major Elective' },
  { code:'CSC 404', name:'Introduction to eCommerce', cat:'Major Elective' },
  { code:'CSC 405', name:'User Interface Development', cat:'Major Elective' },
  { code:'CSC 410', name:'Software Testing & QA', cat:'Major Elective' },
  { code:'CSC 420', name:'Software Maintenance & Re-eng', cat:'Major Elective' },
  { code:'CSC 428', name:'Program Translation Techniques', cat:'Major Elective' },
  { code:'CSC 430', name:'Artificial Intelligence', cat:'Major Elective' },
  { code:'CSC 444', name:'Digital Image Processing', cat:'Major Elective' },
  { code:'CSC 474', name:'Network Security', cat:'Major Elective' },
  { code:'CSC 478', name:'Ethical Hacking', cat:'Major Elective' },
  { code:'CSC 479', name:'Cloud Computing', cat:'Major Elective' },
  { code:'PHIL 190', name:'Philosophy of Art', cat:'Free Elective' },
  { code:'MCM 105', name:'Communication Layout & Design', cat:'Free Elective' },
];

const catLabels = {
  'Gen Ed — Core':    'General Education — Core',
  'Gen Ed — Explore': 'General Education — Explore',
  'Gen Ed — Science': 'Life & Natural Sciences',
  'Major Core':       'Major Core (16 courses)',
  'Major Math':       'Major Math Requirements',
  'Major Elective':   'Major Electives (pick 4)',
  'Free Elective':    'Free Electives (pick 3)',
};

const DONE = 'done', IP = 'inprogress', TODO = 'todo', LOCKED = 'locked';

function getStatus(code) {
  if (completed[code]) return DONE;
  if (inProgress.includes(code)) return IP;
  const prereqs = prereqMap[code] || [];
  return prereqs.every(p => completed[p] || inProgress.includes(p)) ? TODO : LOCKED;
}

// ── CSS ──────────────────────────────────────────────────────
const css = `
.gp-wrap { font-family: var(--font-interface); padding: 0.5rem 0; }
.gp-summary { display: grid; grid-template-columns: repeat(4,1fr); gap: 10px; margin-bottom: 1.2rem; }
.gp-metric { background: var(--background-secondary); border-radius: 8px; padding: 0.75rem 1rem; }
.gp-metric-label { font-size: 11px; color: var(--text-muted); margin-bottom: 3px; }
.gp-metric-value { font-size: 22px; font-weight: 600; color: var(--text-normal); }
.gp-metric-sub { font-size: 11px; color: var(--text-faint); margin-top: 2px; }
.gp-bar-track { background: var(--background-modifier-border); border-radius: 4px; height: 6px; margin-bottom: 1.25rem; overflow: hidden; }
.gp-bar-fill { height: 100%; border-radius: 4px; background: #1D9E75; }
.gp-filters { display: flex; gap: 7px; flex-wrap: wrap; margin-bottom: 1.2rem; align-items: center; }
.gp-filter-label { font-size: 12px; color: var(--text-muted); margin-right: 2px; }
.gp-fbtn { font-size: 12px; padding: 4px 11px; border-radius: 20px; border: 1px solid var(--background-modifier-border); background: transparent; color: var(--text-muted); cursor: pointer; }
.gp-fbtn.gp-active { background: var(--text-normal); color: var(--background-primary); border-color: transparent; }
.gp-section { margin-bottom: 1.4rem; }
.gp-section-hdr { font-size: 11px; font-weight: 600; color: var(--text-muted); letter-spacing: 0.05em; text-transform: uppercase; margin-bottom: 0.6rem; padding-bottom: 5px; border-bottom: 1px solid var(--background-modifier-border); }
.gp-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(190px, 1fr)); gap: 7px; }
.gp-card { background: var(--background-primary); border: 1px solid var(--background-modifier-border); border-radius: 8px; padding: 9px 11px; cursor: pointer; position: relative; transition: border-color 0.15s; }
.gp-card:hover { border-color: var(--interactive-accent); }
.gp-card.done { border-left: 3px solid #1D9E75; }
.gp-card.inprogress { border-left: 3px solid #378ADD; }
.gp-card.locked { opacity: 0.45; }
.gp-card.gp-selected { border-color: #7F77DD; box-shadow: 0 0 0 2px #CECBF620; }
.gp-code { font-size: 12px; font-weight: 600; color: var(--text-normal); }
.gp-name { font-size: 11px; color: var(--text-muted); margin-top: 2px; line-height: 1.4; }
.gp-badge { display: inline-block; font-size: 10px; padding: 2px 6px; border-radius: 3px; margin-top: 5px; font-weight: 500; }
.gp-badge.done    { background: #E1F5EE; color: #0F6E56; }
.gp-badge.inprogress { background: #E6F1FB; color: #185FA5; }
.gp-badge.todo    { background: var(--background-secondary); color: var(--text-muted); }
.gp-badge.locked  { background: #FCEBEB; color: #A32D2D; }
.gp-grade { position: absolute; top: 9px; right: 9px; font-size: 10px; font-weight: 600; color: #0F6E56; background: #E1F5EE; padding: 1px 5px; border-radius: 3px; }
.gp-detail { background: var(--background-secondary); border-radius: 10px; padding: 0.9rem 1.1rem; margin-bottom: 1.2rem; border: 1px solid var(--background-modifier-border-hover); display: none; }
.gp-detail.gp-visible { display: block; }
.gp-detail-title { font-size: 15px; font-weight: 600; color: var(--text-normal); margin-bottom: 3px; }
.gp-detail-code { font-size: 12px; color: var(--text-muted); margin-bottom: 10px; }
.gp-detail-row { display: flex; gap: 1.5rem; flex-wrap: wrap; margin-bottom: 8px; }
.gp-detail-item-label { font-size: 11px; color: var(--text-muted); margin-bottom: 2px; }
.gp-detail-item-value { font-size: 13px; font-weight: 500; color: var(--text-normal); }
.gp-chain { display: flex; flex-wrap: wrap; gap: 5px; margin-top: 6px; align-items: center; }
.gp-chip { font-size: 11px; padding: 2px 7px; border-radius: 3px; border: 1px solid var(--background-modifier-border); color: var(--text-muted); }
.gp-chip.done { border-color: #5DCAA5; color: #0F6E56; background: #E1F5EE; }
.gp-chip.inprogress { border-color: #85B7EB; color: #185FA5; background: #E6F1FB; }
.gp-chip.current { border-color: #AFA9EC; color: #3C3489; background: #EEEDFE; font-weight: 600; }
.gp-arrow { color: var(--text-faint); font-size: 13px; line-height: 1; }
`;

// ── Build DOM ────────────────────────────────────────────────
const root = dv.el('div', '', { cls: 'gp-wrap' });
const styleEl = root.createEl('style');
styleEl.textContent = css;

// Summary cards
const summaryEl = root.createEl('div', { cls: 'gp-summary' });
[
  { label: 'Credits earned', value: '59', sub: 'of 126 required' },
  { label: 'Credits needed', value: '67', sub: '23 courses left' },
  { label: 'CGPA', value: '2.79', sub: 'MPA 3.09' },
  { label: 'Progress', value: '47%', sub: '6 in-progress' },
].forEach(m => {
  const card = summaryEl.createEl('div', { cls: 'gp-metric' });
  card.createEl('div', { cls: 'gp-metric-label', text: m.label });
  card.createEl('div', { cls: 'gp-metric-value', text: m.value });
  card.createEl('div', { cls: 'gp-metric-sub', text: m.sub });
});

// Progress bar
const track = root.createEl('div', { cls: 'gp-bar-track' });
track.createEl('div', { cls: 'gp-bar-fill', attr: { style: 'width:47%' } });

// Filters
const filtersEl = root.createEl('div', { cls: 'gp-filters' });
filtersEl.createEl('span', { cls: 'gp-filter-label', text: 'Show:' });
const filterDefs = [
  { key: 'all', label: 'All courses' },
  { key: 'done', label: 'Completed' },
  { key: 'inprogress', label: 'In progress' },
  { key: 'todo', label: 'Available' },
  { key: 'locked', label: 'Locked' },
];
let currentFilter = 'all';
let selectedCode = null;
const filterBtns = {};
filterDefs.forEach(f => {
  const btn = filtersEl.createEl('button', { cls: 'gp-fbtn' + (f.key === 'all' ? ' gp-active' : ''), text: f.label });
  filterBtns[f.key] = btn;
  btn.addEventListener('click', () => {
    currentFilter = f.key;
    Object.values(filterBtns).forEach(b => b.removeClass('gp-active'));
    btn.addClass('gp-active');
    renderSections();
  });
});

// Detail panel
const detailEl = root.createEl('div', { cls: 'gp-detail' });
const dpTitle = detailEl.createEl('div', { cls: 'gp-detail-title' });
const dpCode  = detailEl.createEl('div', { cls: 'gp-detail-code' });
const dpRow   = detailEl.createEl('div', { cls: 'gp-detail-row' });
const dpStatus = (() => { const d = dpRow.createEl('div'); d.createEl('div',{cls:'gp-detail-item-label',text:'Status'}); return d.createEl('div',{cls:'gp-detail-item-value'}); })();
const dpCat    = (() => { const d = dpRow.createEl('div'); d.createEl('div',{cls:'gp-detail-item-label',text:'Category'}); return d.createEl('div',{cls:'gp-detail-item-value'}); })();
const dpGrade  = (() => { const d = dpRow.createEl('div'); d.createEl('div',{cls:'gp-detail-item-label',text:'Grade'}); return d.createEl('div',{cls:'gp-detail-item-value'}); })();
detailEl.createEl('div', { text: 'Prerequisites', attr: { style: 'font-size:11px;color:var(--text-muted);margin-top:6px;' } });
const dpChain = detailEl.createEl('div', { cls: 'gp-chain' });

function statusLabel(s) {
  return { done:'Completed', inprogress:'In progress', todo:'Available now', locked:'Locked — prereqs needed' }[s];
}

function showDetail(code) {
  if (selectedCode === code) {
    selectedCode = null;
    detailEl.removeClass('gp-visible');
    root.querySelectorAll('.gp-card').forEach(c => c.removeClass('gp-selected'));
    return;
  }
  selectedCode = code;
  const course = allCourses.find(c => c.code === code);
  const status = getStatus(code);
  const prereqs = prereqMap[code] || [];
  dpTitle.textContent = course.name;
  dpCode.textContent  = course.code + ' · ' + course.cat;
  dpStatus.textContent = statusLabel(status);
  dpCat.textContent    = course.cat;
  dpGrade.textContent  = completed[code] || (inProgress.includes(code) ? 'Sem 2502' : '—');
  dpChain.empty();
  if (prereqs.length === 0) {
    dpChain.createEl('span', { text: 'None', attr: { style: 'font-size:12px;color:var(--text-faint)' } });
  } else {
    prereqs.forEach((p, i) => {
      if (i > 0) dpChain.createEl('span', { cls: 'gp-arrow', text: '→' });
      const ps = completed[p] ? 'done' : inProgress.includes(p) ? 'inprogress' : '';
      dpChain.createEl('span', { cls: `gp-chip ${ps}`, text: p });
    });
    dpChain.createEl('span', { cls: 'gp-arrow', text: '→' });
    dpChain.createEl('span', { cls: 'gp-chip current', text: code });
  }
  detailEl.addClass('gp-visible');
  root.querySelectorAll('.gp-card').forEach(c => c.removeClass('gp-selected'));
  root.querySelectorAll(`.gp-card[data-code="${code}"]`).forEach(c => c.addClass('gp-selected'));
}

// Sections container
const sectionsEl = root.createEl('div');

function renderSections() {
  sectionsEl.empty();
  const categories = Object.keys(catLabels);
  categories.forEach(cat => {
    const courses = allCourses.filter(c => c.cat === cat);
    const filtered = currentFilter === 'all' ? courses : courses.filter(c => getStatus(c.code) === currentFilter);
    if (filtered.length === 0) return;
    const doneCount = courses.filter(c => getStatus(c.code) === DONE).length;
    const sec = sectionsEl.createEl('div', { cls: 'gp-section' });
    sec.createEl('div', { cls: 'gp-section-hdr', text: `${catLabels[cat]}  (${doneCount}/${courses.length} done)` });
    const grid = sec.createEl('div', { cls: 'gp-grid' });
    filtered.forEach(course => {
      const status = getStatus(course.code);
      const card = grid.createEl('div', { cls: `gp-card ${status}`, attr: { 'data-code': course.code } });
      if (completed[course.code]) card.createEl('div', { cls: 'gp-grade', text: completed[course.code] });
      card.createEl('div', { cls: 'gp-code', text: course.code });
      card.createEl('div', { cls: 'gp-name', text: course.name });
      const badgeText = { done:'Done', inprogress:'In progress', todo:'Available', locked:'Locked' }[status];
      card.createEl('span', { cls: `gp-badge ${status}`, text: badgeText });
      card.addEventListener('click', () => showDetail(course.code));
    });
  });
}

renderSections();
```
