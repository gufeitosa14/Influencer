<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Relatório de Frequência — Stories Maio 2026</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=DM+Sans:wght@300;400;500;600&family=DM+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg: #F7F6F2;
    --surface: #FFFFFF;
    --surface2: #F0EEE8;
    --border: rgba(0,0,0,0.08);
    --border-strong: rgba(0,0,0,0.15);
    --text-primary: #1A1916;
    --text-secondary: #6B6A65;
    --text-tertiary: #9B9A96;
    --accent: #1A1916;
    --radius: 12px;
    --radius-sm: 8px;
  }

  body {
    font-family: 'DM Sans', sans-serif;
    background: var(--bg);
    color: var(--text-primary);
    min-height: 100vh;
    padding: 40px 24px 60px;
  }

  .page { max-width: 900px; margin: 0 auto; }

  /* HEADER */
  .page-header { margin-bottom: 36px; padding-bottom: 24px; border-bottom: 1px solid var(--border-strong); }
  .page-header-top { display: flex; align-items: flex-start; justify-content: space-between; gap: 16px; flex-wrap: wrap; }
  .page-tag { font-family: 'DM Mono', monospace; font-size: 11px; font-weight: 500; letter-spacing: 0.08em; text-transform: uppercase; color: var(--text-tertiary); margin-bottom: 8px; }
  .page-title { font-size: 26px; font-weight: 600; color: var(--text-primary); line-height: 1.2; }
  .page-subtitle { font-size: 14px; color: var(--text-secondary); margin-top: 6px; }
  .page-date { font-family: 'DM Mono', monospace; font-size: 12px; color: var(--text-tertiary); background: var(--surface2); padding: 6px 12px; border-radius: var(--radius-sm); white-space: nowrap; align-self: flex-start; margin-top: 4px; }

  /* METRICS */
  .metrics { display: grid; grid-template-columns: repeat(4, 1fr); gap: 12px; margin-bottom: 32px; }
  .metric-card { background: var(--surface); border: 1px solid var(--border); border-radius: var(--radius); padding: 16px 18px; }
  .metric-label { font-size: 11px; font-weight: 500; text-transform: uppercase; letter-spacing: 0.06em; color: var(--text-tertiary); margin-bottom: 6px; }
  .metric-value { font-size: 28px; font-weight: 600; color: var(--text-primary); line-height: 1; }
  .metric-sub { font-size: 12px; color: var(--text-tertiary); margin-top: 4px; }

  /* SECTION TITLES */
  .section-label { font-family: 'DM Mono', monospace; font-size: 11px; font-weight: 500; letter-spacing: 0.08em; text-transform: uppercase; color: var(--text-tertiary); margin-bottom: 12px; }

  /* INFLUENCER CARDS */
  .influencers-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; margin-bottom: 32px; }
  .inf-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: var(--radius);
    padding: 14px 16px;
    cursor: pointer;
    transition: border-color 0.15s, box-shadow 0.15s;
    user-select: none;
  }
  .inf-card:hover { border-color: var(--border-strong); box-shadow: 0 2px 8px rgba(0,0,0,0.06); }
  .inf-card.selected { border-color: var(--text-primary); border-width: 1.5px; box-shadow: 0 2px 12px rgba(0,0,0,0.1); }
  .inf-card.dimmed { opacity: 0.35; }
  .inf-top { display: flex; align-items: center; gap: 10px; margin-bottom: 12px; }
  .avatar { width: 38px; height: 38px; border-radius: 50%; display: flex; align-items: center; justify-content: center; font-size: 12px; font-weight: 600; flex-shrink: 0; letter-spacing: 0.02em; }
  .inf-name { font-size: 14px; font-weight: 500; color: var(--text-primary); line-height: 1.3; }
  .inf-handle { font-family: 'DM Mono', monospace; font-size: 11px; color: var(--text-tertiary); margin-top: 1px; }
  .bar-row { display: flex; align-items: center; gap: 8px; }
  .bar-track { flex: 1; height: 5px; background: var(--surface2); border-radius: 3px; overflow: hidden; }
  .bar-fill { height: 100%; border-radius: 3px; transition: width 0.3s ease; }
  .bar-count { font-family: 'DM Mono', monospace; font-size: 12px; font-weight: 500; color: var(--text-secondary); min-width: 40px; text-align: right; }

  /* CALENDAR */
  .calendar-wrap { background: var(--surface); border: 1px solid var(--border); border-radius: var(--radius); overflow: hidden; margin-bottom: 32px; }
  .cal-top { display: flex; align-items: center; justify-content: space-between; padding: 16px 20px 14px; border-bottom: 1px solid var(--border); flex-wrap: wrap; gap: 10px; }
  .cal-month { font-size: 16px; font-weight: 500; color: var(--text-primary); }
  .legend { display: flex; flex-wrap: wrap; gap: 8px; }
  .legend-item { display: flex; align-items: center; gap: 5px; font-size: 12px; color: var(--text-secondary); padding: 3px 8px; background: var(--surface2); border-radius: 20px; transition: opacity 0.15s; }
  .legend-item.dimmed { opacity: 0.3; }
  .legend-dot { width: 8px; height: 8px; border-radius: 50%; flex-shrink: 0; }
  .cal-weekdays { display: grid; grid-template-columns: repeat(7, 1fr); background: var(--surface2); }
  .cal-weekdays span { font-size: 11px; font-weight: 500; text-transform: uppercase; letter-spacing: 0.05em; color: var(--text-tertiary); text-align: center; padding: 8px 4px; }
  .cal-grid { display: grid; grid-template-columns: repeat(7, 1fr); }
  .cal-day { border-top: 1px solid var(--border); border-right: 1px solid var(--border); min-height: 72px; padding: 8px; }
  .cal-day:nth-child(7n) { border-right: none; }
  .cal-day.empty { background: var(--surface2); opacity: 0.5; }
  .day-num { font-family: 'DM Mono', monospace; font-size: 11px; font-weight: 500; color: var(--text-tertiary); margin-bottom: 5px; }
  .dots { display: flex; flex-wrap: wrap; gap: 3px; }
  .cal-dot { width: 10px; height: 10px; border-radius: 50%; cursor: default; transition: opacity 0.15s, transform 0.1s; }
  .cal-dot:hover { transform: scale(1.3); }
  .cal-dot.dimmed { opacity: 0.12; }

  /* TOOLTIP */
  .tooltip {
    position: fixed;
    background: var(--text-primary);
    color: #fff;
    font-size: 12px;
    padding: 5px 10px;
    border-radius: 6px;
    pointer-events: none;
    z-index: 999;
    white-space: nowrap;
    opacity: 0;
    transition: opacity 0.1s;
  }
  .tooltip.show { opacity: 1; }

  /* TABLE */
  .table-wrap { background: var(--surface); border: 1px solid var(--border); border-radius: var(--radius); overflow: hidden; margin-bottom: 32px; }
  .table-head { display: flex; align-items: center; justify-content: space-between; padding: 14px 20px 12px; border-bottom: 1px solid var(--border); }
  .table-title { font-size: 14px; font-weight: 500; }
  table { width: 100%; border-collapse: collapse; }
  thead th { font-size: 11px; font-weight: 500; text-transform: uppercase; letter-spacing: 0.05em; color: var(--text-tertiary); text-align: left; padding: 10px 16px; background: var(--surface2); border-bottom: 1px solid var(--border); }
  tbody tr { border-bottom: 1px solid var(--border); transition: background 0.1s; }
  tbody tr:last-child { border-bottom: none; }
  tbody tr:hover { background: var(--surface2); }
  tbody td { padding: 11px 16px; font-size: 13px; color: var(--text-primary); vertical-align: middle; }
  td.muted { font-family: 'DM Mono', monospace; font-size: 12px; color: var(--text-tertiary); }
  .rank { font-family: 'DM Mono', monospace; font-size: 11px; color: var(--text-tertiary); }
  .color-badge { display: inline-flex; align-items: center; gap: 6px; }
  .color-badge-dot { width: 8px; height: 8px; border-radius: 50%; }
  .posts-bar-wrap { display: flex; align-items: center; gap: 8px; }
  .posts-bar-track { width: 80px; height: 4px; background: var(--surface2); border-radius: 2px; overflow: hidden; }
  .posts-bar-fill { height: 100%; border-radius: 2px; }
  .posts-num { font-family: 'DM Mono', monospace; font-size: 12px; font-weight: 500; }

  /* FOOTER */
  .footer { font-size: 12px; color: var(--text-tertiary); padding-top: 20px; border-top: 1px solid var(--border); display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 8px; }

  @media (max-width: 620px) {
    .metrics { grid-template-columns: repeat(2, 1fr); }
    .influencers-grid { grid-template-columns: 1fr; }
    .metric-value { font-size: 22px; }
    body { padding: 24px 16px 48px; }
  }
</style>
</head>
<body>
<div class="page">

  <header class="page-header">
    <div class="page-header-top">
      <div>
        <div class="page-tag">Relatório de frequência · Stories</div>
        <h1 class="page-title">Monitoramento de influenciadores</h1>
        <p class="page-subtitle">Menções em stories por influenciador — período de medição acordado</p>
      </div>
      <div class="page-date">Mai 2026</div>
    </div>
  </header>

  <div class="metrics" id="metrics"></div>

  <p class="section-label">Influenciadores — clique para filtrar</p>
  <div class="influencers-grid" id="inf-list"></div>

  <div class="calendar-wrap">
    <div class="cal-top">
      <span class="cal-month">Maio 2026</span>
      <div class="legend" id="legend"></div>
    </div>
    <div class="cal-weekdays">
      <span>Dom</span><span>Seg</span><span>Ter</span><span>Qua</span><span>Qui</span><span>Sex</span><span>Sáb</span>
    </div>
    <div class="cal-grid" id="cal-grid"></div>
  </div>

  <div class="table-wrap">
    <div class="table-head">
      <span class="table-title">Resumo detalhado</span>
    </div>
    <table id="summary-table">
      <thead>
        <tr>
          <th>#</th>
          <th>Influenciador</th>
          <th>Handle</th>
          <th>Posts</th>
          <th>Datas</th>
        </tr>
      </thead>
      <tbody id="table-body"></tbody>
    </table>
  </div>

  <div class="footer">
    <span>Dados: menções confirmadas em stories · Maio 2026</span>
    <span>Gerado automaticamente</span>
  </div>
</div>

<div class="tooltip" id="tooltip"></div>

<script>
const influencers = [
  { handle: '@raquelisabela_', name: 'Isabela Raquel', dates: ['2026-05-04','2026-05-06','2026-05-23'], color: '#7F77DD', bg: '#EEEDFE', textColor: '#3C3489', initials: 'IR' },
  { handle: '@Jackebarone', name: 'Jackeline Barone', dates: ['2026-05-15','2026-05-27'], color: '#D4537E', bg: '#FBEAF0', textColor: '#72243E', initials: 'JB' },
  { handle: '@sattojoao_', name: 'João Luiz Sato', dates: ['2026-05-04','2026-05-05','2026-05-07','2026-05-13','2026-05-19','2026-05-27'], color: '#378ADD', bg: '#E6F1FB', textColor: '#0C447C', initials: 'JS' },
  { handle: '@manumoraees_', name: 'Emanuelle Moraes', dates: ['2026-05-04','2026-05-06','2026-05-07','2026-05-12','2026-05-19','2026-05-24','2026-05-25','2026-05-28'], color: '#1D9E75', bg: '#E1F5EE', textColor: '#085041', initials: 'EM' },
  { handle: '@Joaosantos.ind', name: 'João Santos', dates: ['2026-05-05','2026-05-18','2026-05-27','2026-05-28'], color: '#EF9F27', bg: '#FAEEDA', textColor: '#633806', initials: 'JS' },
  { handle: '@laramaddeira', name: 'Lara Madeira', dates: ['2026-05-02','2026-05-06','2026-05-08','2026-05-13','2026-05-19','2026-05-20','2026-05-27','2026-05-28'], color: '#D85A30', bg: '#FAECE7', textColor: '#4A1B0C', initials: 'LM' },
  { handle: '@evellynsantosv', name: 'Evellyn Santos', dates: ['2026-05-05','2026-05-12','2026-05-13','2026-05-14','2026-05-20','2026-05-27','2026-05-29'], color: '#639922', bg: '#EAF3DE', textColor: '#173404', initials: 'ES' },
  { handle: '@by_maricardoso', name: 'Mari Cardoso', dates: ['2026-05-07','2026-05-11','2026-05-17','2026-05-22','2026-05-30'], color: '#888780', bg: '#F1EFE8', textColor: '#2C2C2A', initials: 'MC' },
];

const maxPosts = Math.max(...influencers.map(i => i.dates.length));
let selectedIdx = null;

const tooltip = document.getElementById('tooltip');
document.addEventListener('mousemove', e => {
  tooltip.style.left = (e.clientX + 12) + 'px';
  tooltip.style.top = (e.clientY - 28) + 'px';
});

function buildMetrics() {
  const total = influencers.reduce((s, i) => s + i.dates.length, 0);
  const avg = (total / influencers.length).toFixed(1);
  const top = influencers.reduce((a, b) => a.dates.length >= b.dates.length ? a : b);
  const uniqueDays = new Set(influencers.flatMap(i => i.dates)).size;
  document.getElementById('metrics').innerHTML = `
    <div class="metric-card"><div class="metric-label">Total de postagens</div><div class="metric-value">${total}</div><div class="metric-sub">todos os influenciadores</div></div>
    <div class="metric-card"><div class="metric-label">Média por influenciador</div><div class="metric-value">${avg}</div><div class="metric-sub">posts em maio</div></div>
    <div class="metric-card"><div class="metric-label">Mais ativo</div><div class="metric-value" style="font-size:18px;margin-top:4px;">${top.name.split(' ')[0]}</div><div class="metric-sub">${top.dates.length} postagens</div></div>
    <div class="metric-card"><div class="metric-label">Dias com postagem</div><div class="metric-value">${uniqueDays}</div><div class="metric-sub">de 31 dias do mês</div></div>
  `;
}

function buildInfluencers() {
  const el = document.getElementById('inf-list');
  el.innerHTML = influencers.map((inf, idx) => {
    const pct = Math.round((inf.dates.length / maxPosts) * 100);
    const isDimmed = selectedIdx !== null && selectedIdx !== idx;
    return `<div class="inf-card${selectedIdx === idx ? ' selected' : ''}${isDimmed ? ' dimmed' : ''}" onclick="selectInf(${idx})">
      <div class="inf-top">
        <div class="avatar" style="background:${inf.bg};color:${inf.textColor}">${inf.initials}</div>
        <div><div class="inf-name">${inf.name}</div><div class="inf-handle">${inf.handle}</div></div>
      </div>
      <div class="bar-row">
        <div class="bar-track"><div class="bar-fill" style="width:${pct}%;background:${inf.color}"></div></div>
        <span class="bar-count">${inf.dates.length} posts</span>
      </div>
    </div>`;
  }).join('');
}

function buildLegend() {
  document.getElementById('legend').innerHTML = influencers.map((inf, idx) => {
    const isDimmed = selectedIdx !== null && selectedIdx !== idx;
    return `<span class="legend-item${isDimmed ? ' dimmed' : ''}">
      <span class="legend-dot" style="background:${inf.color}"></span>${inf.name.split(' ')[0]}
    </span>`;
  }).join('');
}

function buildCalendar() {
  const grid = document.getElementById('cal-grid');
  const startDay = new Date('2026-05-01').getDay();
  let cells = '';
  for (let i = 0; i < startDay; i++) cells += `<div class="cal-day empty"></div>`;
  for (let d = 1; d <= 31; d++) {
    const dateStr = `2026-05-${String(d).padStart(2,'0')}`;
    const posters = influencers.filter(inf => inf.dates.includes(dateStr));
    const dotHtml = posters.map((inf, infIdx) => {
      const globalIdx = influencers.indexOf(inf);
      const isDimmed = selectedIdx !== null && selectedIdx !== globalIdx;
      return `<div class="cal-dot${isDimmed ? ' dimmed' : ''}" style="background:${inf.color}"
        onmouseenter="showTip('${inf.name} · ${d}/05')"
        onmouseleave="hideTip()"></div>`;
    }).join('');
    cells += `<div class="cal-day"><div class="day-num">${String(d).padStart(2,'0')}</div><div class="dots">${dotHtml}</div></div>`;
  }
  grid.innerHTML = cells;
}

function buildTable() {
  const sorted = [...influencers].sort((a, b) => b.dates.length - a.dates.length);
  document.getElementById('table-body').innerHTML = sorted.map((inf, i) => {
    const pct = Math.round((inf.dates.length / maxPosts) * 100);
    const datesFormatted = inf.dates.map(d => {
      const parts = d.split('-');
      return `${parts[2]}/${parts[1]}`;
    }).join(', ');
    return `<tr>
      <td class="rank">${String(i+1).padStart(2,'0')}</td>
      <td><span class="color-badge"><span class="color-badge-dot" style="background:${inf.color}"></span>${inf.name}</span></td>
      <td class="muted">${inf.handle}</td>
      <td><div class="posts-bar-wrap"><div class="posts-bar-track"><div class="posts-bar-fill" style="width:${pct}%;background:${inf.color}"></div></div><span class="posts-num">${inf.dates.length}</span></div></td>
      <td class="muted" style="font-size:11px;">${datesFormatted}</td>
    </tr>`;
  }).join('');
}

function selectInf(idx) {
  selectedIdx = selectedIdx === idx ? null : idx;
  buildInfluencers();
  buildLegend();
  buildCalendar();
}

function showTip(text) {
  tooltip.textContent = text;
  tooltip.classList.add('show');
}
function hideTip() {
  tooltip.classList.remove('show');
}

buildMetrics();
buildInfluencers();
buildLegend();
buildCalendar();
buildTable();
</script>
</body>
</html>
