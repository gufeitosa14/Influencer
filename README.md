<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Relatório Individual — Influenciadores Mai–Jun 2026</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=DM+Sans:wght@300;400;500;600&family=DM+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
:root {
  --bg: #F5F4F0; --surface: #FFFFFF; --surface2: #EEEDE8;
  --border: rgba(0,0,0,0.08); --border-strong: rgba(0,0,0,0.14);
  --text-primary: #18170F; --text-secondary: #6A6960; --text-tertiary: #9A9990;
  --accent: #18170F; --radius: 14px; --radius-sm: 8px;
}
body { font-family: 'DM Sans', sans-serif; background: var(--bg); color: var(--text-primary); min-height: 100vh; }
.layout { display: flex; min-height: 100vh; }
.sidebar {
  width: 220px; flex-shrink: 0; background: var(--surface);
  border-right: 1px solid var(--border); padding: 28px 0;
  position: sticky; top: 0; height: 100vh; overflow-y: auto;
  display: flex; flex-direction: column;
}
.sidebar-brand { padding: 0 20px 20px; border-bottom: 1px solid var(--border); margin-bottom: 16px; }
.sidebar-brand-label { font-family: 'DM Mono', monospace; font-size: 10px; letter-spacing: 0.1em; text-transform: uppercase; color: var(--text-tertiary); margin-bottom: 4px; }
.sidebar-brand-title { font-size: 14px; font-weight: 600; color: var(--text-primary); line-height: 1.3; }
.sidebar-brand-sub { font-size: 11px; color: var(--text-tertiary); margin-top: 2px; }
.nav-label { font-family: 'DM Mono', monospace; font-size: 10px; letter-spacing: 0.08em; text-transform: uppercase; color: var(--text-tertiary); padding: 0 20px; margin-bottom: 6px; }
.nav-item { display: flex; align-items: center; gap: 10px; padding: 9px 20px; cursor: pointer; transition: background 0.12s; border-left: 2px solid transparent; }
.nav-item:hover { background: var(--surface2); }
.nav-item.active { background: var(--surface2); border-left-color: var(--accent); }
.nav-avatar { width: 28px; height: 28px; border-radius: 50%; display: flex; align-items: center; justify-content: center; font-size: 10px; font-weight: 600; flex-shrink: 0; }
.nav-name { font-size: 12px; font-weight: 500; color: var(--text-primary); line-height: 1.2; }
.nav-handle { font-family: 'DM Mono', monospace; font-size: 10px; color: var(--text-tertiary); }
.content-area { flex: 1; display: flex; flex-direction: column; }
.top-bar { display: flex; align-items: center; justify-content: flex-end; padding: 12px 36px 0; }
.btn-export { display: inline-flex; align-items: center; gap: 7px; font-family: 'DM Sans', sans-serif; font-size: 13px; font-weight: 500; background: var(--accent); color: #fff; border: none; border-radius: var(--radius-sm); padding: 9px 16px; cursor: pointer; transition: opacity 0.15s; }
.btn-export:hover { opacity: 0.82; }
.btn-export svg { width: 14px; height: 14px; }
.main { flex: 1; padding: 28px 36px 60px; max-width: 760px; }
.page { display: none; }
.page.active { display: block; }
.page-tag { font-family: 'DM Mono', monospace; font-size: 10px; letter-spacing: 0.1em; text-transform: uppercase; color: var(--text-tertiary); margin-bottom: 6px; }
.profile-header { display: flex; align-items: center; gap: 16px; margin-bottom: 20px; padding-bottom: 20px; border-bottom: 1px solid var(--border-strong); }
.profile-avatar { width: 56px; height: 56px; border-radius: 50%; display: flex; align-items: center; justify-content: center; font-size: 18px; font-weight: 600; flex-shrink: 0; }
.profile-name { font-size: 22px; font-weight: 600; line-height: 1.2; }
.profile-handle { font-family: 'DM Mono', monospace; font-size: 12px; color: var(--text-secondary); margin-top: 3px; }
.month-switcher { display: flex; gap: 6px; margin-bottom: 20px; }
.month-btn { font-family: 'DM Sans', sans-serif; font-size: 13px; font-weight: 500; padding: 7px 16px; border-radius: 20px; border: 1.5px solid var(--border-strong); background: transparent; color: var(--text-secondary); cursor: pointer; transition: all 0.15s; }
.month-btn:hover { background: var(--surface2); }
.month-btn.active { background: var(--accent); color: #fff; border-color: var(--accent); }
.metrics-row { display: grid; grid-template-columns: repeat(4, 1fr); gap: 10px; margin-bottom: 24px; }
.metric-card { background: var(--surface); border: 1px solid var(--border); border-radius: var(--radius); padding: 14px 14px; }
.metric-card.accent-card { background: var(--accent); }
.metric-label { font-size: 10px; font-weight: 500; text-transform: uppercase; letter-spacing: 0.06em; color: var(--text-tertiary); margin-bottom: 6px; }
.accent-card .metric-label { color: rgba(255,255,255,0.5); }
.metric-value { font-size: 22px; font-weight: 600; color: var(--text-primary); line-height: 1; }
.metric-value.money { font-size: 15px; margin-top: 2px; }
.accent-card .metric-value { color: #fff; }
.metric-sub { font-size: 11px; color: var(--text-tertiary); margin-top: 4px; }
.accent-card .metric-sub { color: rgba(255,255,255,0.4); }
.section-label { font-family: 'DM Mono', monospace; font-size: 10px; letter-spacing: 0.08em; text-transform: uppercase; color: var(--text-tertiary); margin-bottom: 10px; }
.cal-wrap { background: var(--surface); border: 1px solid var(--border); border-radius: var(--radius); overflow: hidden; margin-bottom: 20px; }
.cal-header-bar { padding: 13px 18px; border-bottom: 1px solid var(--border); display: flex; align-items: center; justify-content: space-between; }
.cal-title { font-size: 14px; font-weight: 500; }
.cal-count-badge { font-family: 'DM Mono', monospace; font-size: 11px; padding: 3px 10px; border-radius: 20px; }
.cal-legend { display: flex; gap: 12px; padding: 8px 18px; border-bottom: 1px solid var(--border); background: var(--surface2); }
.leg-item { display: flex; align-items: center; gap: 5px; font-size: 11px; color: var(--text-secondary); }
.leg-dot { width: 10px; height: 10px; border-radius: 50%; }
.leg-ring { width: 10px; height: 10px; border-radius: 50%; border: 1.5px solid; background: transparent; }
.cal-weekdays { display: grid; grid-template-columns: repeat(7,1fr); background: var(--surface2); }
.cal-weekdays span { font-size: 10px; font-weight: 500; text-transform: uppercase; letter-spacing: 0.04em; color: var(--text-tertiary); text-align: center; padding: 7px 2px; }
.cal-grid { display: grid; grid-template-columns: repeat(7,1fr); }
.cal-day { border-top: 1px solid var(--border); border-right: 1px solid var(--border); min-height: 48px; padding: 5px 6px; }
.cal-day:nth-child(7n) { border-right: none; }
.cal-day.empty { background: var(--surface2); opacity: 0.4; }
.day-num { font-family: 'DM Mono', monospace; font-size: 10px; color: var(--text-tertiary); margin-bottom: 3px; }
.cal-marker { width: 18px; height: 18px; border-radius: 5px; display: inline-flex; align-items: center; justify-content: center; margin-right: 2px; margin-bottom: 2px; }
.cal-marker span { display: block; width: 7px; height: 7px; border-radius: 50%; }
.feed-marker span { display: none; }
.feed-marker { position: relative; }
.feed-marker::after { content: 'F'; font-size: 8px; font-weight: 700; color: inherit; }
.dates-wrap { background: var(--surface); border: 1px solid var(--border); border-radius: var(--radius); overflow: hidden; margin-bottom: 20px; }
.date-row { display: flex; align-items: center; gap: 10px; padding: 9px 18px; border-bottom: 1px solid var(--border); }
.date-row:last-child { border-bottom: none; }
.date-index { font-family: 'DM Mono', monospace; font-size: 10px; color: var(--text-tertiary); min-width: 24px; }
.date-pill { font-family: 'DM Mono', monospace; font-size: 12px; font-weight: 500; background: var(--surface2); padding: 3px 9px; border-radius: 6px; }
.date-day-name { font-size: 12px; color: var(--text-secondary); flex: 1; }
.type-badge { font-size: 10px; font-weight: 500; padding: 2px 8px; border-radius: 10px; text-transform: uppercase; letter-spacing: 0.04em; }
.story-badge { background: #E8E7F5; color: #4B4690; }
.feed-badge { background: #FDE8D8; color: #7A3010; }
.date-dot { width: 8px; height: 8px; border-radius: 50%; flex-shrink: 0; }
.sales-wrap { background: var(--surface); border: 1px solid var(--border); border-radius: var(--radius); overflow: hidden; margin-bottom: 20px; }
.sales-row { display: flex; align-items: center; justify-content: space-between; padding: 12px 18px; border-bottom: 1px solid var(--border); gap: 12px; }
.sales-row:last-child { border-bottom: none; }
.accent-row { background: #FAFAF8; }
.sales-label { font-size: 13px; color: var(--text-secondary); }
.sales-label-strong { font-size: 13px; font-weight: 600; color: var(--text-primary); }
.sales-note { font-size: 11px; color: var(--text-tertiary); margin-top: 2px; }
.sales-value { font-family: 'DM Mono', monospace; font-size: 14px; font-weight: 500; color: var(--text-primary); white-space: nowrap; }
.sales-value.repasse { font-size: 17px; font-weight: 600; }
.no-sales { padding: 18px 18px; font-size: 13px; color: var(--text-tertiary); font-style: italic; }
/* EVOLUTION */
.evo-section { margin-bottom: 24px; }
.evo-wrap { background: var(--surface); border: 1px solid var(--border); border-radius: var(--radius); overflow: hidden; }
.evo-row { display: flex; align-items: center; gap: 12px; padding: 13px 18px; border-bottom: 1px solid var(--border); }
.evo-row:last-child { border-bottom: none; }
.evo-label { font-size: 12px; color: var(--text-secondary); width: 72px; flex-shrink: 0; }
.evo-col { display: flex; flex-direction: column; align-items: center; min-width: 90px; }
.evo-month { font-family: 'DM Mono', monospace; font-size: 10px; color: var(--text-tertiary); margin-bottom: 3px; text-transform: uppercase; }
.evo-val { font-size: 16px; font-weight: 600; color: var(--text-primary); }
.evo-val.sm { font-size: 13px; }
.evo-arrow { font-size: 16px; color: var(--text-tertiary); }
.evo-delta { flex: 1; text-align: right; }
.delta { font-size: 12px; font-weight: 500; padding: 3px 10px; border-radius: 20px; white-space: nowrap; }
.delta.positive { background: #E2F5EC; color: #0F6B35; }
.delta.negative { background: #FCEAEA; color: #8B1A1A; }
.delta.neutral { background: var(--surface2); color: var(--text-tertiary); }
.footer-note { font-size: 11px; color: var(--text-tertiary); padding-top: 20px; border-top: 1px solid var(--border); line-height: 1.7; margin-top: 8px; }
.mobile-nav { display: none; background: var(--surface); border-bottom: 1px solid var(--border); padding: 12px 20px; position: sticky; top: 0; z-index: 10; }
.mobile-nav select { font-family: "DM Sans", sans-serif; font-size: 14px; font-weight: 500; border: 1px solid var(--border-strong); border-radius: var(--radius-sm); padding: 8px 12px; background: var(--surface); color: var(--text-primary); width: 100%; cursor: pointer; }
@media print {
  .sidebar, .mobile-nav, .top-bar { display: none !important; }
  body { background: #fff; }
  .layout { display: block; }
  .main { padding: 20px; max-width: 100%; }
  .page { display: none !important; }
  .page.print-target { display: block !important; }
}
@media (max-width: 680px) {
  .sidebar { display: none; } .mobile-nav { display: block; }
  .main { padding: 16px 14px 48px; }
  .metrics-row { grid-template-columns: repeat(2,1fr); }
}
</style>
</head>
<body>
<div class="layout">
  <nav class="sidebar">
    <div class="sidebar-brand">
      <div class="sidebar-brand-label">Relatório individual</div>
      <div class="sidebar-brand-title">Mai–Jun 2026</div>
      <div class="sidebar-brand-sub">8 influenciadores</div>
    </div>
    <div class="nav-label">Influenciadores</div>
    <div class="nav-item" data-idx="0" onclick="showPage(0)">
  <div class="nav-avatar" style="background:#EEEDFE;color:#3C3489">IR</div>
  <div><div class="nav-name">Isabela</div><div class="nav-handle">@raquelisabela_</div></div>
</div><div class="nav-item" data-idx="1" onclick="showPage(1)">
  <div class="nav-avatar" style="background:#FBEAF0;color:#72243E">JB</div>
  <div><div class="nav-name">Jackeline</div><div class="nav-handle">@Jackebarone</div></div>
</div><div class="nav-item" data-idx="2" onclick="showPage(2)">
  <div class="nav-avatar" style="background:#E6F1FB;color:#0C447C">JS</div>
  <div><div class="nav-name">João</div><div class="nav-handle">@sattojoao_</div></div>
</div><div class="nav-item" data-idx="3" onclick="showPage(3)">
  <div class="nav-avatar" style="background:#E1F5EE;color:#085041">EM</div>
  <div><div class="nav-name">Emanuelle</div><div class="nav-handle">@manumoraees_</div></div>
</div><div class="nav-item" data-idx="4" onclick="showPage(4)">
  <div class="nav-avatar" style="background:#FAEEDA;color:#633806">JS</div>
  <div><div class="nav-name">João</div><div class="nav-handle">@Joaosantos.ind</div></div>
</div><div class="nav-item" data-idx="5" onclick="showPage(5)">
  <div class="nav-avatar" style="background:#FAECE7;color:#4A1B0C">LM</div>
  <div><div class="nav-name">Lara</div><div class="nav-handle">@laramaddeira</div></div>
</div><div class="nav-item" data-idx="6" onclick="showPage(6)">
  <div class="nav-avatar" style="background:#F1EFE8;color:#2C2C2A">MC</div>
  <div><div class="nav-name">Mari</div><div class="nav-handle">@by_maricardoso</div></div>
</div><div class="nav-item" data-idx="7" onclick="showPage(7)">
  <div class="nav-avatar" style="background:#F3EAF5;color:#4A1A52">GM</div>
  <div><div class="nav-name">Guilherme</div><div class="nav-handle">@gui_madona</div></div>
</div>
  </nav>
  <div class="content-area">
    <div class="mobile-nav"><select id="mobile-select" onchange="showPage(this.value)"><option value="0">Isabela Raquel (@raquelisabela_)</option><option value="1">Jackeline Barone (@Jackebarone)</option><option value="2">João Luiz Sato (@sattojoao_)</option><option value="3">Emanuelle Moraes (@manumoraees_)</option><option value="4">João Santos (@Joaosantos.ind)</option><option value="5">Lara Madeira (@laramaddeira)</option><option value="6">Mari Cardoso (@by_maricardoso)</option><option value="7">Guilherme Madona (@gui_madona)</option></select></div>
    <div class="top-bar">
      <button class="btn-export" onclick="exportPDF()">
        <svg viewBox="0 0 16 16" fill="none"><path d="M3 12.5h10M8 2v7.5M8 9.5l-3-3M8 9.5l3-3" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/></svg>
        Exportar PDF
      </button>
    </div>
    <main class="main"><div class="page" id="page-0">
    <div class="page-tag">Relatório individual · Maio–Junho 2026</div>
    <div class="profile-header">
      <div class="profile-avatar" style="background:#EEEDFE;color:#3C3489">IR</div>
      <div>
        <div class="profile-name">Isabela Raquel</div>
        <div class="profile-handle">@raquelisabela_</div>
      </div>
    </div>

    <div class="month-switcher" id="switcher-isabela_raquel">
      <button class="month-btn active" onclick="switchMonth('isabela_raquel','maio',this)">Maio 2026</button>
      <button class="month-btn" onclick="switchMonth('isabela_raquel','junho',this)">Junho 2026</button>
    </div>

    <div id="tabs-isabela_raquel"><div class="month-tab" id="tab-isabela_raquel-maio" style="display:none;">
          <div class="metrics-row">
            <div class="metric-card">
              <div class="metric-label">Postagens</div>
              <div class="metric-value">3</div>
              <div class="metric-sub">3 stories</div>
            </div>
            <div class="metric-card">
              <div class="metric-label">Total vendido</div>
              <div class="metric-value money">R$ 1.848,07</div>
              <div class="metric-sub">13 pedidos</div>
            </div>
            <div class="metric-card">
              <div class="metric-label">Ticket médio</div>
              <div class="metric-value money">R$ 142,16</div>
              <div class="metric-sub">por pedido</div>
            </div>
            <div class="metric-card accent-card">
              <div class="metric-label">Repasse</div>
              <div class="metric-value money">R$ 184,81</div>
              <div class="metric-sub">10% do total vendido</div>
            </div>
          </div>

          <p class="section-label">Calendário — Maio 2026</p>
          <div class="cal-wrap">
            <div class="cal-header-bar">
              <span class="cal-title">Maio 2026</span>
              <span class="cal-count-badge" style="background:#EEEDFE;color:#3C3489">3 postagens registradas</span>
            </div>
            
            <div class="cal-weekdays"><span>Dom</span><span>Seg</span><span>Ter</span><span>Qua</span><span>Qui</span><span>Sex</span><span>Sáb</span></div>
            <div class="cal-grid"><div class="cal-day empty"></div><div class="cal-day empty"></div><div class="cal-day empty"></div><div class="cal-day empty"></div><div class="cal-day empty"></div><div class="cal-day"><div class="day-num">01</div></div><div class="cal-day"><div class="day-num">02</div></div><div class="cal-day"><div class="day-num">03</div></div><div class="cal-day  has-post"><div class="day-num">04</div><div class="cal-marker story-marker" style="background:#EEEDFE"><span style="background:#7F77DD"></span></div></div><div class="cal-day"><div class="day-num">05</div></div><div class="cal-day  has-post"><div class="day-num">06</div><div class="cal-marker story-marker" style="background:#EEEDFE"><span style="background:#7F77DD"></span></div></div><div class="cal-day"><div class="day-num">07</div></div><div class="cal-day"><div class="day-num">08</div></div><div class="cal-day"><div class="day-num">09</div></div><div class="cal-day"><div class="day-num">10</div></div><div class="cal-day"><div class="day-num">11</div></div><div class="cal-day"><div class="day-num">12</div></div><div class="cal-day"><div class="day-num">13</div></div><div class="cal-day"><div class="day-num">14</div></div><div class="cal-day"><div class="day-num">15</div></div><div class="cal-day"><div class="day-num">16</div></div><div class="cal-day"><div class="day-num">17</div></div><div class="cal-day"><div class="day-num">18</div></div><div class="cal-day"><div class="day-num">19</div></div><div class="cal-day"><div class="day-num">20</div></div><div class="cal-day"><div class="day-num">21</div></div><div class="cal-day"><div class="day-num">22</div></div><div class="cal-day  has-post"><div class="day-num">23</div><div class="cal-marker story-marker" style="background:#EEEDFE"><span style="background:#7F77DD"></span></div></div><div class="cal-day"><div class="day-num">24</div></div><div class="cal-day"><div class="day-num">25</div></div><div class="cal-day"><div class="day-num">26</div></div><div class="cal-day"><div class="day-num">27</div></div><div class="cal-day"><div class="day-num">28</div></div><div class="cal-day"><div class="day-num">29</div></div><div class="cal-day"><div class="day-num">30</div></div><div class="cal-day"><div class="day-num">31</div></div></div>
          </div>

          <p class="section-label">Datas de postagem</p>
          <div class="dates-wrap"><div class="dates-list"><div class="date-row">
  <span class="date-index">01</span>
  <span class="date-pill">04/05/2026</span>
  <span class="date-day-name">Segunda-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#7F77DD"></span>
</div><div class="date-row">
  <span class="date-index">02</span>
  <span class="date-pill">06/05/2026</span>
  <span class="date-day-name">Quarta-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#7F77DD"></span>
</div><div class="date-row">
  <span class="date-index">03</span>
  <span class="date-pill">23/05/2026</span>
  <span class="date-day-name">Sábado</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#7F77DD"></span>
</div></div></div>

          <p class="section-label">Dados de vendas</p>
          <div class="sales-wrap">
        <div class="sales-row"><span class="sales-label">Total vendido</span><span class="sales-value">R$ 1.848,07</span></div>
        <div class="sales-row"><span class="sales-label">Número de pedidos</span><span class="sales-value">13 pedidos</span></div>
        <div class="sales-row"><span class="sales-label">Ticket médio</span><span class="sales-value">R$ 142,16</span></div>
        <div class="sales-row accent-row">
          <div><div class="sales-label-strong">Repasse (10% do total vendido)</div><div class="sales-note">Calculado sobre o valor total de vendas atribuídas</div></div>
          <div class="sales-value repasse" style="color:#7F77DD">R$ 184,81</div>
        </div></div>
        </div><div class="month-tab" id="tab-isabela_raquel-junho" style="display:none;">
          <div class="metrics-row">
            <div class="metric-card">
              <div class="metric-label">Postagens</div>
              <div class="metric-value">6</div>
              <div class="metric-sub">6 stories</div>
            </div>
            <div class="metric-card">
              <div class="metric-label">Total vendido</div>
              <div class="metric-value money">R$ 1.711,70</div>
              <div class="metric-sub">9 pedidos</div>
            </div>
            <div class="metric-card">
              <div class="metric-label">Ticket médio</div>
              <div class="metric-value money">R$ 190,19</div>
              <div class="metric-sub">por pedido</div>
            </div>
            <div class="metric-card accent-card">
              <div class="metric-label">Repasse</div>
              <div class="metric-value money">R$ 171,17</div>
              <div class="metric-sub">10% (vendas acima de R$ 1.000)</div>
            </div>
          </div>

          <p class="section-label">Calendário — Junho 2026</p>
          <div class="cal-wrap">
            <div class="cal-header-bar">
              <span class="cal-title">Junho 2026</span>
              <span class="cal-count-badge" style="background:#EEEDFE;color:#3C3489">6 postagens registradas</span>
            </div>
            
            <div class="cal-weekdays"><span>Dom</span><span>Seg</span><span>Ter</span><span>Qua</span><span>Qui</span><span>Sex</span><span>Sáb</span></div>
            <div class="cal-grid"><div class="cal-day empty"></div><div class="cal-day"><div class="day-num">01</div></div><div class="cal-day  has-post"><div class="day-num">02</div><div class="cal-marker story-marker" style="background:#EEEDFE"><span style="background:#7F77DD"></span></div></div><div class="cal-day"><div class="day-num">03</div></div><div class="cal-day  has-post"><div class="day-num">04</div><div class="cal-marker story-marker" style="background:#EEEDFE"><span style="background:#7F77DD"></span></div></div><div class="cal-day"><div class="day-num">05</div></div><div class="cal-day"><div class="day-num">06</div></div><div class="cal-day"><div class="day-num">07</div></div><div class="cal-day  has-post"><div class="day-num">08</div><div class="cal-marker story-marker" style="background:#EEEDFE"><span style="background:#7F77DD"></span></div></div><div class="cal-day"><div class="day-num">09</div></div><div class="cal-day"><div class="day-num">10</div></div><div class="cal-day"><div class="day-num">11</div></div><div class="cal-day"><div class="day-num">12</div></div><div class="cal-day"><div class="day-num">13</div></div><div class="cal-day"><div class="day-num">14</div></div><div class="cal-day  has-post"><div class="day-num">15</div><div class="cal-marker story-marker" style="background:#EEEDFE"><span style="background:#7F77DD"></span></div></div><div class="cal-day"><div class="day-num">16</div></div><div class="cal-day  has-post"><div class="day-num">17</div><div class="cal-marker story-marker" style="background:#EEEDFE"><span style="background:#7F77DD"></span></div></div><div class="cal-day"><div class="day-num">18</div></div><div class="cal-day"><div class="day-num">19</div></div><div class="cal-day"><div class="day-num">20</div></div><div class="cal-day"><div class="day-num">21</div></div><div class="cal-day"><div class="day-num">22</div></div><div class="cal-day"><div class="day-num">23</div></div><div class="cal-day"><div class="day-num">24</div></div><div class="cal-day"><div class="day-num">25</div></div><div class="cal-day  has-post"><div class="day-num">26</div><div class="cal-marker story-marker" style="background:#EEEDFE"><span style="background:#7F77DD"></span></div></div><div class="cal-day"><div class="day-num">27</div></div><div class="cal-day"><div class="day-num">28</div></div><div class="cal-day"><div class="day-num">29</div></div><div class="cal-day"><div class="day-num">30</div></div></div>
          </div>

          <p class="section-label">Datas de postagem</p>
          <div class="dates-wrap"><div class="dates-list"><div class="date-row">
  <span class="date-index">01</span>
  <span class="date-pill">02/06/2026</span>
  <span class="date-day-name">Terça-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#7F77DD"></span>
</div><div class="date-row">
  <span class="date-index">02</span>
  <span class="date-pill">04/06/2026</span>
  <span class="date-day-name">Quinta-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#7F77DD"></span>
</div><div class="date-row">
  <span class="date-index">03</span>
  <span class="date-pill">08/06/2026</span>
  <span class="date-day-name">Segunda-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#7F77DD"></span>
</div><div class="date-row">
  <span class="date-index">04</span>
  <span class="date-pill">15/06/2026</span>
  <span class="date-day-name">Segunda-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#7F77DD"></span>
</div><div class="date-row">
  <span class="date-index">05</span>
  <span class="date-pill">17/06/2026</span>
  <span class="date-day-name">Quarta-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#7F77DD"></span>
</div><div class="date-row">
  <span class="date-index">06</span>
  <span class="date-pill">26/06/2026</span>
  <span class="date-day-name">Sexta-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#7F77DD"></span>
</div></div></div>

          <p class="section-label">Dados de vendas</p>
          <div class="sales-wrap">
        <div class="sales-row"><span class="sales-label">Total vendido</span><span class="sales-value">R$ 1.711,70</span></div>
        <div class="sales-row"><span class="sales-label">Número de pedidos</span><span class="sales-value">9 pedidos</span></div>
        <div class="sales-row"><span class="sales-label">Ticket médio</span><span class="sales-value">R$ 190,19</span></div>
        <div class="sales-row accent-row">
          <div><div class="sales-label-strong">Repasse (10% (vendas acima de R$ 1.000))</div><div class="sales-note">Calculado sobre o valor total de vendas atribuídas</div></div>
          <div class="sales-value repasse" style="color:#7F77DD">R$ 171,17</div>
        </div></div>
        </div></div>

    <div class="evo-section">
      <p class="section-label" style="margin-bottom:12px;">Evolução Maio → Junho</p>
      <div class="evo-wrap">
    <div class="evo-row">
      <div class="evo-label">Postagens</div>
      <div class="evo-col"><div class="evo-month">Mai</div><div class="evo-val">3</div></div>
      <div class="evo-arrow">→</div>
      <div class="evo-col"><div class="evo-month">Jun</div><div class="evo-val">6</div></div>
      <div class="evo-delta"><span class="delta positive">▲ 3 posts (100%)</span></div>
    </div>
    <div class="evo-row">
      <div class="evo-label">Vendas</div>
      <div class="evo-col"><div class="evo-month">Mai</div><div class="evo-val sm">R$ 1.848,07</div></div>
      <div class="evo-arrow">→</div>
      <div class="evo-col"><div class="evo-month">Jun</div><div class="evo-val sm">R$ 1.711,70</div></div>
      <div class="evo-delta"><span class="delta negative">▼ R$ 136,37 (7%)</span></div>
    </div>
    <div class="evo-row">
      <div class="evo-label">Repasse</div>
      <div class="evo-col"><div class="evo-month">Mai</div><div class="evo-val sm">R$ 184,81</div></div>
      <div class="evo-arrow">→</div>
      <div class="evo-col"><div class="evo-month">Jun</div><div class="evo-val sm">R$ 171,17</div></div>
      <div class="evo-delta"><span class="delta negative">▼ R$ 13,64 (7%)</span></div>
    </div></div>
    </div>

    <div class="footer-note">
      Este relatório é individual e confidencial, gerado para Isabela Raquel (@raquelisabela_).<br>
      Dados de postagem referem-se a menções confirmadas. Junho 2026 parcial — dados até 26/06/2026.
    </div></div><div class="page" id="page-1">
    <div class="page-tag">Relatório individual · Maio–Junho 2026</div>
    <div class="profile-header">
      <div class="profile-avatar" style="background:#FBEAF0;color:#72243E">JB</div>
      <div>
        <div class="profile-name">Jackeline Barone</div>
        <div class="profile-handle">@Jackebarone</div>
      </div>
    </div>

    <div class="month-switcher" id="switcher-jackeline_barone">
      <button class="month-btn active" onclick="switchMonth('jackeline_barone','maio',this)">Maio 2026</button>
      <button class="month-btn" onclick="switchMonth('jackeline_barone','junho',this)">Junho 2026</button>
    </div>

    <div id="tabs-jackeline_barone"><div class="month-tab" id="tab-jackeline_barone-maio" style="display:none;">
          <div class="metrics-row">
            <div class="metric-card">
              <div class="metric-label">Postagens</div>
              <div class="metric-value">2</div>
              <div class="metric-sub">2 stories</div>
            </div>
            <div class="metric-card">
              <div class="metric-label">Total vendido</div>
              <div class="metric-value money">R$ 0,00</div>
              <div class="metric-sub">0 pedidos</div>
            </div>
            <div class="metric-card">
              <div class="metric-label">Ticket médio</div>
              <div class="metric-value money">—</div>
              <div class="metric-sub">por pedido</div>
            </div>
            <div class="metric-card accent-card">
              <div class="metric-label">Repasse</div>
              <div class="metric-value money">R$ 0,00</div>
              <div class="metric-sub">10% do total vendido</div>
            </div>
          </div>

          <p class="section-label">Calendário — Maio 2026</p>
          <div class="cal-wrap">
            <div class="cal-header-bar">
              <span class="cal-title">Maio 2026</span>
              <span class="cal-count-badge" style="background:#FBEAF0;color:#72243E">2 postagens registradas</span>
            </div>
            
            <div class="cal-weekdays"><span>Dom</span><span>Seg</span><span>Ter</span><span>Qua</span><span>Qui</span><span>Sex</span><span>Sáb</span></div>
            <div class="cal-grid"><div class="cal-day empty"></div><div class="cal-day empty"></div><div class="cal-day empty"></div><div class="cal-day empty"></div><div class="cal-day empty"></div><div class="cal-day"><div class="day-num">01</div></div><div class="cal-day"><div class="day-num">02</div></div><div class="cal-day"><div class="day-num">03</div></div><div class="cal-day"><div class="day-num">04</div></div><div class="cal-day"><div class="day-num">05</div></div><div class="cal-day"><div class="day-num">06</div></div><div class="cal-day"><div class="day-num">07</div></div><div class="cal-day"><div class="day-num">08</div></div><div class="cal-day"><div class="day-num">09</div></div><div class="cal-day"><div class="day-num">10</div></div><div class="cal-day"><div class="day-num">11</div></div><div class="cal-day"><div class="day-num">12</div></div><div class="cal-day"><div class="day-num">13</div></div><div class="cal-day"><div class="day-num">14</div></div><div class="cal-day  has-post"><div class="day-num">15</div><div class="cal-marker story-marker" style="background:#FBEAF0"><span style="background:#D4537E"></span></div></div><div class="cal-day"><div class="day-num">16</div></div><div class="cal-day"><div class="day-num">17</div></div><div class="cal-day"><div class="day-num">18</div></div><div class="cal-day"><div class="day-num">19</div></div><div class="cal-day"><div class="day-num">20</div></div><div class="cal-day"><div class="day-num">21</div></div><div class="cal-day"><div class="day-num">22</div></div><div class="cal-day"><div class="day-num">23</div></div><div class="cal-day"><div class="day-num">24</div></div><div class="cal-day"><div class="day-num">25</div></div><div class="cal-day"><div class="day-num">26</div></div><div class="cal-day  has-post"><div class="day-num">27</div><div class="cal-marker story-marker" style="background:#FBEAF0"><span style="background:#D4537E"></span></div></div><div class="cal-day"><div class="day-num">28</div></div><div class="cal-day"><div class="day-num">29</div></div><div class="cal-day"><div class="day-num">30</div></div><div class="cal-day"><div class="day-num">31</div></div></div>
          </div>

          <p class="section-label">Datas de postagem</p>
          <div class="dates-wrap"><div class="dates-list"><div class="date-row">
  <span class="date-index">01</span>
  <span class="date-pill">15/05/2026</span>
  <span class="date-day-name">Sexta-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#D4537E"></span>
</div><div class="date-row">
  <span class="date-index">02</span>
  <span class="date-pill">27/05/2026</span>
  <span class="date-day-name">Quarta-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#D4537E"></span>
</div></div></div>

          <p class="section-label">Dados de vendas</p>
          <div class="sales-wrap"><div class="no-sales">Nenhuma venda registrada para este período.</div></div>
        </div><div class="month-tab" id="tab-jackeline_barone-junho" style="display:none;">
          <div class="metrics-row">
            <div class="metric-card">
              <div class="metric-label">Postagens</div>
              <div class="metric-value">7</div>
              <div class="metric-sub">7 stories</div>
            </div>
            <div class="metric-card">
              <div class="metric-label">Total vendido</div>
              <div class="metric-value money">R$ 0,00</div>
              <div class="metric-sub">0 pedidos</div>
            </div>
            <div class="metric-card">
              <div class="metric-label">Ticket médio</div>
              <div class="metric-value money">—</div>
              <div class="metric-sub">por pedido</div>
            </div>
            <div class="metric-card accent-card">
              <div class="metric-label">Repasse</div>
              <div class="metric-value money">R$ 0,00</div>
              <div class="metric-sub">5% (vendas até R$ 1.000)</div>
            </div>
          </div>

          <p class="section-label">Calendário — Junho 2026</p>
          <div class="cal-wrap">
            <div class="cal-header-bar">
              <span class="cal-title">Junho 2026</span>
              <span class="cal-count-badge" style="background:#FBEAF0;color:#72243E">7 postagens registradas</span>
            </div>
            
            <div class="cal-weekdays"><span>Dom</span><span>Seg</span><span>Ter</span><span>Qua</span><span>Qui</span><span>Sex</span><span>Sáb</span></div>
            <div class="cal-grid"><div class="cal-day empty"></div><div class="cal-day"><div class="day-num">01</div></div><div class="cal-day  has-post"><div class="day-num">02</div><div class="cal-marker story-marker" style="background:#FBEAF0"><span style="background:#D4537E"></span></div></div><div class="cal-day"><div class="day-num">03</div></div><div class="cal-day"><div class="day-num">04</div></div><div class="cal-day  has-post"><div class="day-num">05</div><div class="cal-marker story-marker" style="background:#FBEAF0"><span style="background:#D4537E"></span></div></div><div class="cal-day"><div class="day-num">06</div></div><div class="cal-day"><div class="day-num">07</div></div><div class="cal-day"><div class="day-num">08</div></div><div class="cal-day"><div class="day-num">09</div></div><div class="cal-day"><div class="day-num">10</div></div><div class="cal-day  has-post"><div class="day-num">11</div><div class="cal-marker story-marker" style="background:#FBEAF0"><span style="background:#D4537E"></span></div></div><div class="cal-day"><div class="day-num">12</div></div><div class="cal-day  has-post"><div class="day-num">13</div><div class="cal-marker story-marker" style="background:#FBEAF0"><span style="background:#D4537E"></span></div></div><div class="cal-day"><div class="day-num">14</div></div><div class="cal-day"><div class="day-num">15</div></div><div class="cal-day"><div class="day-num">16</div></div><div class="cal-day"><div class="day-num">17</div></div><div class="cal-day"><div class="day-num">18</div></div><div class="cal-day"><div class="day-num">19</div></div><div class="cal-day"><div class="day-num">20</div></div><div class="cal-day"><div class="day-num">21</div></div><div class="cal-day"><div class="day-num">22</div></div><div class="cal-day  has-post"><div class="day-num">23</div><div class="cal-marker story-marker" style="background:#FBEAF0"><span style="background:#D4537E"></span></div></div><div class="cal-day  has-post"><div class="day-num">24</div><div class="cal-marker story-marker" style="background:#FBEAF0"><span style="background:#D4537E"></span></div></div><div class="cal-day  has-post"><div class="day-num">25</div><div class="cal-marker story-marker" style="background:#FBEAF0"><span style="background:#D4537E"></span></div></div><div class="cal-day"><div class="day-num">26</div></div><div class="cal-day"><div class="day-num">27</div></div><div class="cal-day"><div class="day-num">28</div></div><div class="cal-day"><div class="day-num">29</div></div><div class="cal-day"><div class="day-num">30</div></div></div>
          </div>

          <p class="section-label">Datas de postagem</p>
          <div class="dates-wrap"><div class="dates-list"><div class="date-row">
  <span class="date-index">01</span>
  <span class="date-pill">02/06/2026</span>
  <span class="date-day-name">Terça-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#D4537E"></span>
</div><div class="date-row">
  <span class="date-index">02</span>
  <span class="date-pill">05/06/2026</span>
  <span class="date-day-name">Sexta-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#D4537E"></span>
</div><div class="date-row">
  <span class="date-index">03</span>
  <span class="date-pill">11/06/2026</span>
  <span class="date-day-name">Quinta-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#D4537E"></span>
</div><div class="date-row">
  <span class="date-index">04</span>
  <span class="date-pill">13/06/2026</span>
  <span class="date-day-name">Sábado</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#D4537E"></span>
</div><div class="date-row">
  <span class="date-index">05</span>
  <span class="date-pill">23/06/2026</span>
  <span class="date-day-name">Terça-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#D4537E"></span>
</div><div class="date-row">
  <span class="date-index">06</span>
  <span class="date-pill">24/06/2026</span>
  <span class="date-day-name">Quarta-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#D4537E"></span>
</div><div class="date-row">
  <span class="date-index">07</span>
  <span class="date-pill">25/06/2026</span>
  <span class="date-day-name">Quinta-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#D4537E"></span>
</div></div></div>

          <p class="section-label">Dados de vendas</p>
          <div class="sales-wrap"><div class="no-sales">Nenhuma venda registrada para este período.</div></div>
        </div></div>

    <div class="evo-section">
      <p class="section-label" style="margin-bottom:12px;">Evolução Maio → Junho</p>
      <div class="evo-wrap">
    <div class="evo-row">
      <div class="evo-label">Postagens</div>
      <div class="evo-col"><div class="evo-month">Mai</div><div class="evo-val">2</div></div>
      <div class="evo-arrow">→</div>
      <div class="evo-col"><div class="evo-month">Jun</div><div class="evo-val">7</div></div>
      <div class="evo-delta"><span class="delta positive">▲ 5 posts (250%)</span></div>
    </div>
    <div class="evo-row">
      <div class="evo-label">Vendas</div>
      <div class="evo-col"><div class="evo-month">Mai</div><div class="evo-val sm">R$ 0,00</div></div>
      <div class="evo-arrow">→</div>
      <div class="evo-col"><div class="evo-month">Jun</div><div class="evo-val sm">R$ 0,00</div></div>
      <div class="evo-delta"><span class="delta neutral">—</span></div>
    </div>
    <div class="evo-row">
      <div class="evo-label">Repasse</div>
      <div class="evo-col"><div class="evo-month">Mai</div><div class="evo-val sm">R$ 0,00</div></div>
      <div class="evo-arrow">→</div>
      <div class="evo-col"><div class="evo-month">Jun</div><div class="evo-val sm">R$ 0,00</div></div>
      <div class="evo-delta"><span class="delta neutral">—</span></div>
    </div></div>
    </div>

    <div class="footer-note">
      Este relatório é individual e confidencial, gerado para Jackeline Barone (@Jackebarone).<br>
      Dados de postagem referem-se a menções confirmadas. Junho 2026 parcial — dados até 26/06/2026.
    </div></div><div class="page" id="page-2">
    <div class="page-tag">Relatório individual · Maio–Junho 2026</div>
    <div class="profile-header">
      <div class="profile-avatar" style="background:#E6F1FB;color:#0C447C">JS</div>
      <div>
        <div class="profile-name">João Luiz Sato</div>
        <div class="profile-handle">@sattojoao_</div>
      </div>
    </div>

    <div class="month-switcher" id="switcher-joao_luiz_sato">
      <button class="month-btn active" onclick="switchMonth('joao_luiz_sato','maio',this)">Maio 2026</button>
      <button class="month-btn" onclick="switchMonth('joao_luiz_sato','junho',this)">Junho 2026</button>
    </div>

    <div id="tabs-joao_luiz_sato"><div class="month-tab" id="tab-joao_luiz_sato-maio" style="display:none;">
          <div class="metrics-row">
            <div class="metric-card">
              <div class="metric-label">Postagens</div>
              <div class="metric-value">6</div>
              <div class="metric-sub">6 stories</div>
            </div>
            <div class="metric-card">
              <div class="metric-label">Total vendido</div>
              <div class="metric-value money">R$ 1.352,70</div>
              <div class="metric-sub">9 pedidos</div>
            </div>
            <div class="metric-card">
              <div class="metric-label">Ticket médio</div>
              <div class="metric-value money">R$ 150,30</div>
              <div class="metric-sub">por pedido</div>
            </div>
            <div class="metric-card accent-card">
              <div class="metric-label">Repasse</div>
              <div class="metric-value money">R$ 135,27</div>
              <div class="metric-sub">10% do total vendido</div>
            </div>
          </div>

          <p class="section-label">Calendário — Maio 2026</p>
          <div class="cal-wrap">
            <div class="cal-header-bar">
              <span class="cal-title">Maio 2026</span>
              <span class="cal-count-badge" style="background:#E6F1FB;color:#0C447C">6 postagens registradas</span>
            </div>
            
            <div class="cal-weekdays"><span>Dom</span><span>Seg</span><span>Ter</span><span>Qua</span><span>Qui</span><span>Sex</span><span>Sáb</span></div>
            <div class="cal-grid"><div class="cal-day empty"></div><div class="cal-day empty"></div><div class="cal-day empty"></div><div class="cal-day empty"></div><div class="cal-day empty"></div><div class="cal-day"><div class="day-num">01</div></div><div class="cal-day"><div class="day-num">02</div></div><div class="cal-day"><div class="day-num">03</div></div><div class="cal-day  has-post"><div class="day-num">04</div><div class="cal-marker story-marker" style="background:#E6F1FB"><span style="background:#378ADD"></span></div></div><div class="cal-day  has-post"><div class="day-num">05</div><div class="cal-marker story-marker" style="background:#E6F1FB"><span style="background:#378ADD"></span></div></div><div class="cal-day"><div class="day-num">06</div></div><div class="cal-day  has-post"><div class="day-num">07</div><div class="cal-marker story-marker" style="background:#E6F1FB"><span style="background:#378ADD"></span></div></div><div class="cal-day"><div class="day-num">08</div></div><div class="cal-day"><div class="day-num">09</div></div><div class="cal-day"><div class="day-num">10</div></div><div class="cal-day"><div class="day-num">11</div></div><div class="cal-day"><div class="day-num">12</div></div><div class="cal-day  has-post"><div class="day-num">13</div><div class="cal-marker story-marker" style="background:#E6F1FB"><span style="background:#378ADD"></span></div></div><div class="cal-day"><div class="day-num">14</div></div><div class="cal-day"><div class="day-num">15</div></div><div class="cal-day"><div class="day-num">16</div></div><div class="cal-day"><div class="day-num">17</div></div><div class="cal-day"><div class="day-num">18</div></div><div class="cal-day  has-post"><div class="day-num">19</div><div class="cal-marker story-marker" style="background:#E6F1FB"><span style="background:#378ADD"></span></div></div><div class="cal-day"><div class="day-num">20</div></div><div class="cal-day"><div class="day-num">21</div></div><div class="cal-day"><div class="day-num">22</div></div><div class="cal-day"><div class="day-num">23</div></div><div class="cal-day"><div class="day-num">24</div></div><div class="cal-day"><div class="day-num">25</div></div><div class="cal-day"><div class="day-num">26</div></div><div class="cal-day  has-post"><div class="day-num">27</div><div class="cal-marker story-marker" style="background:#E6F1FB"><span style="background:#378ADD"></span></div></div><div class="cal-day"><div class="day-num">28</div></div><div class="cal-day"><div class="day-num">29</div></div><div class="cal-day"><div class="day-num">30</div></div><div class="cal-day"><div class="day-num">31</div></div></div>
          </div>

          <p class="section-label">Datas de postagem</p>
          <div class="dates-wrap"><div class="dates-list"><div class="date-row">
  <span class="date-index">01</span>
  <span class="date-pill">04/05/2026</span>
  <span class="date-day-name">Segunda-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#378ADD"></span>
</div><div class="date-row">
  <span class="date-index">02</span>
  <span class="date-pill">05/05/2026</span>
  <span class="date-day-name">Terça-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#378ADD"></span>
</div><div class="date-row">
  <span class="date-index">03</span>
  <span class="date-pill">07/05/2026</span>
  <span class="date-day-name">Quinta-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#378ADD"></span>
</div><div class="date-row">
  <span class="date-index">04</span>
  <span class="date-pill">13/05/2026</span>
  <span class="date-day-name">Quarta-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#378ADD"></span>
</div><div class="date-row">
  <span class="date-index">05</span>
  <span class="date-pill">19/05/2026</span>
  <span class="date-day-name">Terça-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#378ADD"></span>
</div><div class="date-row">
  <span class="date-index">06</span>
  <span class="date-pill">27/05/2026</span>
  <span class="date-day-name">Quarta-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#378ADD"></span>
</div></div></div>

          <p class="section-label">Dados de vendas</p>
          <div class="sales-wrap">
        <div class="sales-row"><span class="sales-label">Total vendido</span><span class="sales-value">R$ 1.352,70</span></div>
        <div class="sales-row"><span class="sales-label">Número de pedidos</span><span class="sales-value">9 pedidos</span></div>
        <div class="sales-row"><span class="sales-label">Ticket médio</span><span class="sales-value">R$ 150,30</span></div>
        <div class="sales-row accent-row">
          <div><div class="sales-label-strong">Repasse (10% do total vendido)</div><div class="sales-note">Calculado sobre o valor total de vendas atribuídas</div></div>
          <div class="sales-value repasse" style="color:#378ADD">R$ 135,27</div>
        </div></div>
        </div><div class="month-tab" id="tab-joao_luiz_sato-junho" style="display:none;">
          <div class="metrics-row">
            <div class="metric-card">
              <div class="metric-label">Postagens</div>
              <div class="metric-value">3</div>
              <div class="metric-sub">3 stories</div>
            </div>
            <div class="metric-card">
              <div class="metric-label">Total vendido</div>
              <div class="metric-value money">R$ 1.242,03</div>
              <div class="metric-sub">8 pedidos</div>
            </div>
            <div class="metric-card">
              <div class="metric-label">Ticket médio</div>
              <div class="metric-value money">R$ 155,25</div>
              <div class="metric-sub">por pedido</div>
            </div>
            <div class="metric-card accent-card">
              <div class="metric-label">Repasse</div>
              <div class="metric-value money">R$ 62,10</div>
              <div class="metric-sub">5% fixo</div>
            </div>
          </div>

          <p class="section-label">Calendário — Junho 2026</p>
          <div class="cal-wrap">
            <div class="cal-header-bar">
              <span class="cal-title">Junho 2026</span>
              <span class="cal-count-badge" style="background:#E6F1FB;color:#0C447C">3 postagens registradas</span>
            </div>
            
            <div class="cal-weekdays"><span>Dom</span><span>Seg</span><span>Ter</span><span>Qua</span><span>Qui</span><span>Sex</span><span>Sáb</span></div>
            <div class="cal-grid"><div class="cal-day empty"></div><div class="cal-day  has-post"><div class="day-num">01</div><div class="cal-marker story-marker" style="background:#E6F1FB"><span style="background:#378ADD"></span></div></div><div class="cal-day"><div class="day-num">02</div></div><div class="cal-day"><div class="day-num">03</div></div><div class="cal-day"><div class="day-num">04</div></div><div class="cal-day"><div class="day-num">05</div></div><div class="cal-day"><div class="day-num">06</div></div><div class="cal-day"><div class="day-num">07</div></div><div class="cal-day"><div class="day-num">08</div></div><div class="cal-day"><div class="day-num">09</div></div><div class="cal-day"><div class="day-num">10</div></div><div class="cal-day"><div class="day-num">11</div></div><div class="cal-day"><div class="day-num">12</div></div><div class="cal-day"><div class="day-num">13</div></div><div class="cal-day"><div class="day-num">14</div></div><div class="cal-day"><div class="day-num">15</div></div><div class="cal-day"><div class="day-num">16</div></div><div class="cal-day  has-post"><div class="day-num">17</div><div class="cal-marker story-marker" style="background:#E6F1FB"><span style="background:#378ADD"></span></div></div><div class="cal-day"><div class="day-num">18</div></div><div class="cal-day"><div class="day-num">19</div></div><div class="cal-day"><div class="day-num">20</div></div><div class="cal-day"><div class="day-num">21</div></div><div class="cal-day  has-post"><div class="day-num">22</div><div class="cal-marker story-marker" style="background:#E6F1FB"><span style="background:#378ADD"></span></div></div><div class="cal-day"><div class="day-num">23</div></div><div class="cal-day"><div class="day-num">24</div></div><div class="cal-day"><div class="day-num">25</div></div><div class="cal-day"><div class="day-num">26</div></div><div class="cal-day"><div class="day-num">27</div></div><div class="cal-day"><div class="day-num">28</div></div><div class="cal-day"><div class="day-num">29</div></div><div class="cal-day"><div class="day-num">30</div></div></div>
          </div>

          <p class="section-label">Datas de postagem</p>
          <div class="dates-wrap"><div class="dates-list"><div class="date-row">
  <span class="date-index">01</span>
  <span class="date-pill">01/06/2026</span>
  <span class="date-day-name">Segunda-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#378ADD"></span>
</div><div class="date-row">
  <span class="date-index">02</span>
  <span class="date-pill">17/06/2026</span>
  <span class="date-day-name">Quarta-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#378ADD"></span>
</div><div class="date-row">
  <span class="date-index">03</span>
  <span class="date-pill">22/06/2026</span>
  <span class="date-day-name">Segunda-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#378ADD"></span>
</div></div></div>

          <p class="section-label">Dados de vendas</p>
          <div class="sales-wrap">
        <div class="sales-row"><span class="sales-label">Total vendido</span><span class="sales-value">R$ 1.242,03</span></div>
        <div class="sales-row"><span class="sales-label">Número de pedidos</span><span class="sales-value">8 pedidos</span></div>
        <div class="sales-row"><span class="sales-label">Ticket médio</span><span class="sales-value">R$ 155,25</span></div>
        <div class="sales-row accent-row">
          <div><div class="sales-label-strong">Repasse (5% fixo)</div><div class="sales-note">Calculado sobre o valor total de vendas atribuídas</div></div>
          <div class="sales-value repasse" style="color:#378ADD">R$ 62,10</div>
        </div></div>
        </div></div>

    <div class="evo-section">
      <p class="section-label" style="margin-bottom:12px;">Evolução Maio → Junho</p>
      <div class="evo-wrap">
    <div class="evo-row">
      <div class="evo-label">Postagens</div>
      <div class="evo-col"><div class="evo-month">Mai</div><div class="evo-val">6</div></div>
      <div class="evo-arrow">→</div>
      <div class="evo-col"><div class="evo-month">Jun</div><div class="evo-val">3</div></div>
      <div class="evo-delta"><span class="delta negative">▼ 3 posts (50%)</span></div>
    </div>
    <div class="evo-row">
      <div class="evo-label">Vendas</div>
      <div class="evo-col"><div class="evo-month">Mai</div><div class="evo-val sm">R$ 1.352,70</div></div>
      <div class="evo-arrow">→</div>
      <div class="evo-col"><div class="evo-month">Jun</div><div class="evo-val sm">R$ 1.242,03</div></div>
      <div class="evo-delta"><span class="delta negative">▼ R$ 110,67 (8%)</span></div>
    </div>
    <div class="evo-row">
      <div class="evo-label">Repasse</div>
      <div class="evo-col"><div class="evo-month">Mai</div><div class="evo-val sm">R$ 135,27</div></div>
      <div class="evo-arrow">→</div>
      <div class="evo-col"><div class="evo-month">Jun</div><div class="evo-val sm">R$ 62,10</div></div>
      <div class="evo-delta"><span class="delta negative">▼ R$ 73,17 (54%)</span></div>
    </div></div>
    </div>

    <div class="footer-note">
      Este relatório é individual e confidencial, gerado para João Luiz Sato (@sattojoao_).<br>
      Dados de postagem referem-se a menções confirmadas. Junho 2026 parcial — dados até 26/06/2026.
    </div></div><div class="page" id="page-3">
    <div class="page-tag">Relatório individual · Maio–Junho 2026</div>
    <div class="profile-header">
      <div class="profile-avatar" style="background:#E1F5EE;color:#085041">EM</div>
      <div>
        <div class="profile-name">Emanuelle Moraes</div>
        <div class="profile-handle">@manumoraees_</div>
      </div>
    </div>

    <div class="month-switcher" id="switcher-emanuelle_moraes">
      <button class="month-btn active" onclick="switchMonth('emanuelle_moraes','maio',this)">Maio 2026</button>
      <button class="month-btn" onclick="switchMonth('emanuelle_moraes','junho',this)">Junho 2026</button>
    </div>

    <div id="tabs-emanuelle_moraes"><div class="month-tab" id="tab-emanuelle_moraes-maio" style="display:none;">
          <div class="metrics-row">
            <div class="metric-card">
              <div class="metric-label">Postagens</div>
              <div class="metric-value">8</div>
              <div class="metric-sub">8 stories</div>
            </div>
            <div class="metric-card">
              <div class="metric-label">Total vendido</div>
              <div class="metric-value money">R$ 0,00</div>
              <div class="metric-sub">0 pedidos</div>
            </div>
            <div class="metric-card">
              <div class="metric-label">Ticket médio</div>
              <div class="metric-value money">—</div>
              <div class="metric-sub">por pedido</div>
            </div>
            <div class="metric-card accent-card">
              <div class="metric-label">Repasse</div>
              <div class="metric-value money">R$ 0,00</div>
              <div class="metric-sub">10% do total vendido</div>
            </div>
          </div>

          <p class="section-label">Calendário — Maio 2026</p>
          <div class="cal-wrap">
            <div class="cal-header-bar">
              <span class="cal-title">Maio 2026</span>
              <span class="cal-count-badge" style="background:#E1F5EE;color:#085041">8 postagens registradas</span>
            </div>
            
            <div class="cal-weekdays"><span>Dom</span><span>Seg</span><span>Ter</span><span>Qua</span><span>Qui</span><span>Sex</span><span>Sáb</span></div>
            <div class="cal-grid"><div class="cal-day empty"></div><div class="cal-day empty"></div><div class="cal-day empty"></div><div class="cal-day empty"></div><div class="cal-day empty"></div><div class="cal-day"><div class="day-num">01</div></div><div class="cal-day"><div class="day-num">02</div></div><div class="cal-day"><div class="day-num">03</div></div><div class="cal-day  has-post"><div class="day-num">04</div><div class="cal-marker story-marker" style="background:#E1F5EE"><span style="background:#1D9E75"></span></div></div><div class="cal-day"><div class="day-num">05</div></div><div class="cal-day  has-post"><div class="day-num">06</div><div class="cal-marker story-marker" style="background:#E1F5EE"><span style="background:#1D9E75"></span></div></div><div class="cal-day  has-post"><div class="day-num">07</div><div class="cal-marker story-marker" style="background:#E1F5EE"><span style="background:#1D9E75"></span></div></div><div class="cal-day"><div class="day-num">08</div></div><div class="cal-day"><div class="day-num">09</div></div><div class="cal-day"><div class="day-num">10</div></div><div class="cal-day"><div class="day-num">11</div></div><div class="cal-day  has-post"><div class="day-num">12</div><div class="cal-marker story-marker" style="background:#E1F5EE"><span style="background:#1D9E75"></span></div></div><div class="cal-day"><div class="day-num">13</div></div><div class="cal-day"><div class="day-num">14</div></div><div class="cal-day"><div class="day-num">15</div></div><div class="cal-day"><div class="day-num">16</div></div><div class="cal-day"><div class="day-num">17</div></div><div class="cal-day"><div class="day-num">18</div></div><div class="cal-day  has-post"><div class="day-num">19</div><div class="cal-marker story-marker" style="background:#E1F5EE"><span style="background:#1D9E75"></span></div></div><div class="cal-day"><div class="day-num">20</div></div><div class="cal-day"><div class="day-num">21</div></div><div class="cal-day"><div class="day-num">22</div></div><div class="cal-day"><div class="day-num">23</div></div><div class="cal-day  has-post"><div class="day-num">24</div><div class="cal-marker story-marker" style="background:#E1F5EE"><span style="background:#1D9E75"></span></div></div><div class="cal-day  has-post"><div class="day-num">25</div><div class="cal-marker story-marker" style="background:#E1F5EE"><span style="background:#1D9E75"></span></div></div><div class="cal-day"><div class="day-num">26</div></div><div class="cal-day"><div class="day-num">27</div></div><div class="cal-day  has-post"><div class="day-num">28</div><div class="cal-marker story-marker" style="background:#E1F5EE"><span style="background:#1D9E75"></span></div></div><div class="cal-day"><div class="day-num">29</div></div><div class="cal-day"><div class="day-num">30</div></div><div class="cal-day"><div class="day-num">31</div></div></div>
          </div>

          <p class="section-label">Datas de postagem</p>
          <div class="dates-wrap"><div class="dates-list"><div class="date-row">
  <span class="date-index">01</span>
  <span class="date-pill">04/05/2026</span>
  <span class="date-day-name">Segunda-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#1D9E75"></span>
</div><div class="date-row">
  <span class="date-index">02</span>
  <span class="date-pill">06/05/2026</span>
  <span class="date-day-name">Quarta-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#1D9E75"></span>
</div><div class="date-row">
  <span class="date-index">03</span>
  <span class="date-pill">07/05/2026</span>
  <span class="date-day-name">Quinta-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#1D9E75"></span>
</div><div class="date-row">
  <span class="date-index">04</span>
  <span class="date-pill">12/05/2026</span>
  <span class="date-day-name">Terça-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#1D9E75"></span>
</div><div class="date-row">
  <span class="date-index">05</span>
  <span class="date-pill">19/05/2026</span>
  <span class="date-day-name">Terça-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#1D9E75"></span>
</div><div class="date-row">
  <span class="date-index">06</span>
  <span class="date-pill">24/05/2026</span>
  <span class="date-day-name">Domingo</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#1D9E75"></span>
</div><div class="date-row">
  <span class="date-index">07</span>
  <span class="date-pill">25/05/2026</span>
  <span class="date-day-name">Segunda-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#1D9E75"></span>
</div><div class="date-row">
  <span class="date-index">08</span>
  <span class="date-pill">28/05/2026</span>
  <span class="date-day-name">Quinta-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#1D9E75"></span>
</div></div></div>

          <p class="section-label">Dados de vendas</p>
          <div class="sales-wrap"><div class="no-sales">Nenhuma venda registrada para este período.</div></div>
        </div><div class="month-tab" id="tab-emanuelle_moraes-junho" style="display:none;">
          <div class="metrics-row">
            <div class="metric-card">
              <div class="metric-label">Postagens</div>
              <div class="metric-value">7</div>
              <div class="metric-sub">7 stories</div>
            </div>
            <div class="metric-card">
              <div class="metric-label">Total vendido</div>
              <div class="metric-value money">R$ 52,51</div>
              <div class="metric-sub">1 pedido</div>
            </div>
            <div class="metric-card">
              <div class="metric-label">Ticket médio</div>
              <div class="metric-value money">R$ 52,51</div>
              <div class="metric-sub">por pedido</div>
            </div>
            <div class="metric-card accent-card">
              <div class="metric-label">Repasse</div>
              <div class="metric-value money">R$ 2,63</div>
              <div class="metric-sub">5% (vendas até R$ 1.000)</div>
            </div>
          </div>

          <p class="section-label">Calendário — Junho 2026</p>
          <div class="cal-wrap">
            <div class="cal-header-bar">
              <span class="cal-title">Junho 2026</span>
              <span class="cal-count-badge" style="background:#E1F5EE;color:#085041">7 postagens registradas</span>
            </div>
            
            <div class="cal-weekdays"><span>Dom</span><span>Seg</span><span>Ter</span><span>Qua</span><span>Qui</span><span>Sex</span><span>Sáb</span></div>
            <div class="cal-grid"><div class="cal-day empty"></div><div class="cal-day"><div class="day-num">01</div></div><div class="cal-day  has-post"><div class="day-num">02</div><div class="cal-marker story-marker" style="background:#E1F5EE"><span style="background:#1D9E75"></span></div></div><div class="cal-day"><div class="day-num">03</div></div><div class="cal-day"><div class="day-num">04</div></div><div class="cal-day"><div class="day-num">05</div></div><div class="cal-day"><div class="day-num">06</div></div><div class="cal-day"><div class="day-num">07</div></div><div class="cal-day"><div class="day-num">08</div></div><div class="cal-day"><div class="day-num">09</div></div><div class="cal-day  has-post"><div class="day-num">10</div><div class="cal-marker story-marker" style="background:#E1F5EE"><span style="background:#1D9E75"></span></div></div><div class="cal-day"><div class="day-num">11</div></div><div class="cal-day"><div class="day-num">12</div></div><div class="cal-day"><div class="day-num">13</div></div><div class="cal-day  has-post"><div class="day-num">14</div><div class="cal-marker story-marker" style="background:#E1F5EE"><span style="background:#1D9E75"></span></div></div><div class="cal-day"><div class="day-num">15</div></div><div class="cal-day  has-post"><div class="day-num">16</div><div class="cal-marker story-marker" style="background:#E1F5EE"><span style="background:#1D9E75"></span></div></div><div class="cal-day"><div class="day-num">17</div></div><div class="cal-day"><div class="day-num">18</div></div><div class="cal-day"><div class="day-num">19</div></div><div class="cal-day  has-post"><div class="day-num">20</div><div class="cal-marker story-marker" style="background:#E1F5EE"><span style="background:#1D9E75"></span></div></div><div class="cal-day"><div class="day-num">21</div></div><div class="cal-day"><div class="day-num">22</div></div><div class="cal-day"><div class="day-num">23</div></div><div class="cal-day"><div class="day-num">24</div></div><div class="cal-day  has-post"><div class="day-num">25</div><div class="cal-marker story-marker" style="background:#E1F5EE"><span style="background:#1D9E75"></span></div></div><div class="cal-day  has-post"><div class="day-num">26</div><div class="cal-marker story-marker" style="background:#E1F5EE"><span style="background:#1D9E75"></span></div></div><div class="cal-day"><div class="day-num">27</div></div><div class="cal-day"><div class="day-num">28</div></div><div class="cal-day"><div class="day-num">29</div></div><div class="cal-day"><div class="day-num">30</div></div></div>
          </div>

          <p class="section-label">Datas de postagem</p>
          <div class="dates-wrap"><div class="dates-list"><div class="date-row">
  <span class="date-index">01</span>
  <span class="date-pill">02/06/2026</span>
  <span class="date-day-name">Terça-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#1D9E75"></span>
</div><div class="date-row">
  <span class="date-index">02</span>
  <span class="date-pill">10/06/2026</span>
  <span class="date-day-name">Quarta-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#1D9E75"></span>
</div><div class="date-row">
  <span class="date-index">03</span>
  <span class="date-pill">14/06/2026</span>
  <span class="date-day-name">Domingo</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#1D9E75"></span>
</div><div class="date-row">
  <span class="date-index">04</span>
  <span class="date-pill">16/06/2026</span>
  <span class="date-day-name">Terça-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#1D9E75"></span>
</div><div class="date-row">
  <span class="date-index">05</span>
  <span class="date-pill">20/06/2026</span>
  <span class="date-day-name">Sábado</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#1D9E75"></span>
</div><div class="date-row">
  <span class="date-index">06</span>
  <span class="date-pill">25/06/2026</span>
  <span class="date-day-name">Quinta-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#1D9E75"></span>
</div><div class="date-row">
  <span class="date-index">07</span>
  <span class="date-pill">26/06/2026</span>
  <span class="date-day-name">Sexta-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#1D9E75"></span>
</div></div></div>

          <p class="section-label">Dados de vendas</p>
          <div class="sales-wrap">
        <div class="sales-row"><span class="sales-label">Total vendido</span><span class="sales-value">R$ 52,51</span></div>
        <div class="sales-row"><span class="sales-label">Número de pedidos</span><span class="sales-value">1 pedido</span></div>
        <div class="sales-row"><span class="sales-label">Ticket médio</span><span class="sales-value">R$ 52,51</span></div>
        <div class="sales-row accent-row">
          <div><div class="sales-label-strong">Repasse (5% (vendas até R$ 1.000))</div><div class="sales-note">Calculado sobre o valor total de vendas atribuídas</div></div>
          <div class="sales-value repasse" style="color:#1D9E75">R$ 2,63</div>
        </div></div>
        </div></div>

    <div class="evo-section">
      <p class="section-label" style="margin-bottom:12px;">Evolução Maio → Junho</p>
      <div class="evo-wrap">
    <div class="evo-row">
      <div class="evo-label">Postagens</div>
      <div class="evo-col"><div class="evo-month">Mai</div><div class="evo-val">8</div></div>
      <div class="evo-arrow">→</div>
      <div class="evo-col"><div class="evo-month">Jun</div><div class="evo-val">7</div></div>
      <div class="evo-delta"><span class="delta negative">▼ 1 posts (12%)</span></div>
    </div>
    <div class="evo-row">
      <div class="evo-label">Vendas</div>
      <div class="evo-col"><div class="evo-month">Mai</div><div class="evo-val sm">R$ 0,00</div></div>
      <div class="evo-arrow">→</div>
      <div class="evo-col"><div class="evo-month">Jun</div><div class="evo-val sm">R$ 52,51</div></div>
      <div class="evo-delta"><span class="delta positive">▲ novo</span></div>
    </div>
    <div class="evo-row">
      <div class="evo-label">Repasse</div>
      <div class="evo-col"><div class="evo-month">Mai</div><div class="evo-val sm">R$ 0,00</div></div>
      <div class="evo-arrow">→</div>
      <div class="evo-col"><div class="evo-month">Jun</div><div class="evo-val sm">R$ 2,63</div></div>
      <div class="evo-delta"><span class="delta positive">▲ novo</span></div>
    </div></div>
    </div>

    <div class="footer-note">
      Este relatório é individual e confidencial, gerado para Emanuelle Moraes (@manumoraees_).<br>
      Dados de postagem referem-se a menções confirmadas. Junho 2026 parcial — dados até 26/06/2026.
    </div></div><div class="page" id="page-4">
    <div class="page-tag">Relatório individual · Maio–Junho 2026</div>
    <div class="profile-header">
      <div class="profile-avatar" style="background:#FAEEDA;color:#633806">JS</div>
      <div>
        <div class="profile-name">João Santos</div>
        <div class="profile-handle">@Joaosantos.ind</div>
      </div>
    </div>

    <div class="month-switcher" id="switcher-joao_santos">
      <button class="month-btn active" onclick="switchMonth('joao_santos','maio',this)">Maio 2026</button>
      <button class="month-btn" onclick="switchMonth('joao_santos','junho',this)">Junho 2026</button>
    </div>

    <div id="tabs-joao_santos"><div class="month-tab" id="tab-joao_santos-maio" style="display:none;">
          <div class="metrics-row">
            <div class="metric-card">
              <div class="metric-label">Postagens</div>
              <div class="metric-value">4</div>
              <div class="metric-sub">4 stories</div>
            </div>
            <div class="metric-card">
              <div class="metric-label">Total vendido</div>
              <div class="metric-value money">R$ 609,90</div>
              <div class="metric-sub">5 pedidos</div>
            </div>
            <div class="metric-card">
              <div class="metric-label">Ticket médio</div>
              <div class="metric-value money">R$ 121,98</div>
              <div class="metric-sub">por pedido</div>
            </div>
            <div class="metric-card accent-card">
              <div class="metric-label">Repasse</div>
              <div class="metric-value money">R$ 60,99</div>
              <div class="metric-sub">10% do total vendido</div>
            </div>
          </div>

          <p class="section-label">Calendário — Maio 2026</p>
          <div class="cal-wrap">
            <div class="cal-header-bar">
              <span class="cal-title">Maio 2026</span>
              <span class="cal-count-badge" style="background:#FAEEDA;color:#633806">4 postagens registradas</span>
            </div>
            
            <div class="cal-weekdays"><span>Dom</span><span>Seg</span><span>Ter</span><span>Qua</span><span>Qui</span><span>Sex</span><span>Sáb</span></div>
            <div class="cal-grid"><div class="cal-day empty"></div><div class="cal-day empty"></div><div class="cal-day empty"></div><div class="cal-day empty"></div><div class="cal-day empty"></div><div class="cal-day"><div class="day-num">01</div></div><div class="cal-day"><div class="day-num">02</div></div><div class="cal-day"><div class="day-num">03</div></div><div class="cal-day"><div class="day-num">04</div></div><div class="cal-day  has-post"><div class="day-num">05</div><div class="cal-marker story-marker" style="background:#FAEEDA"><span style="background:#EF9F27"></span></div></div><div class="cal-day"><div class="day-num">06</div></div><div class="cal-day"><div class="day-num">07</div></div><div class="cal-day"><div class="day-num">08</div></div><div class="cal-day"><div class="day-num">09</div></div><div class="cal-day"><div class="day-num">10</div></div><div class="cal-day"><div class="day-num">11</div></div><div class="cal-day"><div class="day-num">12</div></div><div class="cal-day"><div class="day-num">13</div></div><div class="cal-day"><div class="day-num">14</div></div><div class="cal-day"><div class="day-num">15</div></div><div class="cal-day"><div class="day-num">16</div></div><div class="cal-day"><div class="day-num">17</div></div><div class="cal-day  has-post"><div class="day-num">18</div><div class="cal-marker story-marker" style="background:#FAEEDA"><span style="background:#EF9F27"></span></div></div><div class="cal-day"><div class="day-num">19</div></div><div class="cal-day"><div class="day-num">20</div></div><div class="cal-day"><div class="day-num">21</div></div><div class="cal-day"><div class="day-num">22</div></div><div class="cal-day"><div class="day-num">23</div></div><div class="cal-day"><div class="day-num">24</div></div><div class="cal-day"><div class="day-num">25</div></div><div class="cal-day"><div class="day-num">26</div></div><div class="cal-day  has-post"><div class="day-num">27</div><div class="cal-marker story-marker" style="background:#FAEEDA"><span style="background:#EF9F27"></span></div></div><div class="cal-day  has-post"><div class="day-num">28</div><div class="cal-marker story-marker" style="background:#FAEEDA"><span style="background:#EF9F27"></span></div></div><div class="cal-day"><div class="day-num">29</div></div><div class="cal-day"><div class="day-num">30</div></div><div class="cal-day"><div class="day-num">31</div></div></div>
          </div>

          <p class="section-label">Datas de postagem</p>
          <div class="dates-wrap"><div class="dates-list"><div class="date-row">
  <span class="date-index">01</span>
  <span class="date-pill">05/05/2026</span>
  <span class="date-day-name">Terça-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#EF9F27"></span>
</div><div class="date-row">
  <span class="date-index">02</span>
  <span class="date-pill">18/05/2026</span>
  <span class="date-day-name">Segunda-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#EF9F27"></span>
</div><div class="date-row">
  <span class="date-index">03</span>
  <span class="date-pill">27/05/2026</span>
  <span class="date-day-name">Quarta-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#EF9F27"></span>
</div><div class="date-row">
  <span class="date-index">04</span>
  <span class="date-pill">28/05/2026</span>
  <span class="date-day-name">Quinta-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#EF9F27"></span>
</div></div></div>

          <p class="section-label">Dados de vendas</p>
          <div class="sales-wrap">
        <div class="sales-row"><span class="sales-label">Total vendido</span><span class="sales-value">R$ 609,90</span></div>
        <div class="sales-row"><span class="sales-label">Número de pedidos</span><span class="sales-value">5 pedidos</span></div>
        <div class="sales-row"><span class="sales-label">Ticket médio</span><span class="sales-value">R$ 121,98</span></div>
        <div class="sales-row accent-row">
          <div><div class="sales-label-strong">Repasse (10% do total vendido)</div><div class="sales-note">Calculado sobre o valor total de vendas atribuídas</div></div>
          <div class="sales-value repasse" style="color:#EF9F27">R$ 60,99</div>
        </div></div>
        </div><div class="month-tab" id="tab-joao_santos-junho" style="display:none;">
          <div class="metrics-row">
            <div class="metric-card">
              <div class="metric-label">Postagens</div>
              <div class="metric-value">1</div>
              <div class="metric-sub">1 stories</div>
            </div>
            <div class="metric-card">
              <div class="metric-label">Total vendido</div>
              <div class="metric-value money">R$ 0,00</div>
              <div class="metric-sub">0 pedidos</div>
            </div>
            <div class="metric-card">
              <div class="metric-label">Ticket médio</div>
              <div class="metric-value money">—</div>
              <div class="metric-sub">por pedido</div>
            </div>
            <div class="metric-card accent-card">
              <div class="metric-label">Repasse</div>
              <div class="metric-value money">R$ 0,00</div>
              <div class="metric-sub">5% (vendas até R$ 1.000)</div>
            </div>
          </div>

          <p class="section-label">Calendário — Junho 2026</p>
          <div class="cal-wrap">
            <div class="cal-header-bar">
              <span class="cal-title">Junho 2026</span>
              <span class="cal-count-badge" style="background:#FAEEDA;color:#633806">1 postagens registradas</span>
            </div>
            
            <div class="cal-weekdays"><span>Dom</span><span>Seg</span><span>Ter</span><span>Qua</span><span>Qui</span><span>Sex</span><span>Sáb</span></div>
            <div class="cal-grid"><div class="cal-day empty"></div><div class="cal-day"><div class="day-num">01</div></div><div class="cal-day"><div class="day-num">02</div></div><div class="cal-day"><div class="day-num">03</div></div><div class="cal-day"><div class="day-num">04</div></div><div class="cal-day"><div class="day-num">05</div></div><div class="cal-day"><div class="day-num">06</div></div><div class="cal-day"><div class="day-num">07</div></div><div class="cal-day"><div class="day-num">08</div></div><div class="cal-day"><div class="day-num">09</div></div><div class="cal-day"><div class="day-num">10</div></div><div class="cal-day"><div class="day-num">11</div></div><div class="cal-day"><div class="day-num">12</div></div><div class="cal-day"><div class="day-num">13</div></div><div class="cal-day"><div class="day-num">14</div></div><div class="cal-day"><div class="day-num">15</div></div><div class="cal-day"><div class="day-num">16</div></div><div class="cal-day"><div class="day-num">17</div></div><div class="cal-day"><div class="day-num">18</div></div><div class="cal-day"><div class="day-num">19</div></div><div class="cal-day"><div class="day-num">20</div></div><div class="cal-day"><div class="day-num">21</div></div><div class="cal-day"><div class="day-num">22</div></div><div class="cal-day"><div class="day-num">23</div></div><div class="cal-day"><div class="day-num">24</div></div><div class="cal-day  has-post"><div class="day-num">25</div><div class="cal-marker story-marker" style="background:#FAEEDA"><span style="background:#EF9F27"></span></div></div><div class="cal-day"><div class="day-num">26</div></div><div class="cal-day"><div class="day-num">27</div></div><div class="cal-day"><div class="day-num">28</div></div><div class="cal-day"><div class="day-num">29</div></div><div class="cal-day"><div class="day-num">30</div></div></div>
          </div>

          <p class="section-label">Datas de postagem</p>
          <div class="dates-wrap"><div class="dates-list"><div class="date-row">
  <span class="date-index">01</span>
  <span class="date-pill">25/06/2026</span>
  <span class="date-day-name">Quinta-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#EF9F27"></span>
</div></div></div>

          <p class="section-label">Dados de vendas</p>
          <div class="sales-wrap"><div class="no-sales">Nenhuma venda registrada para este período.</div></div>
        </div></div>

    <div class="evo-section">
      <p class="section-label" style="margin-bottom:12px;">Evolução Maio → Junho</p>
      <div class="evo-wrap">
    <div class="evo-row">
      <div class="evo-label">Postagens</div>
      <div class="evo-col"><div class="evo-month">Mai</div><div class="evo-val">4</div></div>
      <div class="evo-arrow">→</div>
      <div class="evo-col"><div class="evo-month">Jun</div><div class="evo-val">1</div></div>
      <div class="evo-delta"><span class="delta negative">▼ 3 posts (75%)</span></div>
    </div>
    <div class="evo-row">
      <div class="evo-label">Vendas</div>
      <div class="evo-col"><div class="evo-month">Mai</div><div class="evo-val sm">R$ 609,90</div></div>
      <div class="evo-arrow">→</div>
      <div class="evo-col"><div class="evo-month">Jun</div><div class="evo-val sm">R$ 0,00</div></div>
      <div class="evo-delta"><span class="delta negative">▼ R$ 609,90 (100%)</span></div>
    </div>
    <div class="evo-row">
      <div class="evo-label">Repasse</div>
      <div class="evo-col"><div class="evo-month">Mai</div><div class="evo-val sm">R$ 60,99</div></div>
      <div class="evo-arrow">→</div>
      <div class="evo-col"><div class="evo-month">Jun</div><div class="evo-val sm">R$ 0,00</div></div>
      <div class="evo-delta"><span class="delta negative">▼ R$ 60,99 (100%)</span></div>
    </div></div>
    </div>

    <div class="footer-note">
      Este relatório é individual e confidencial, gerado para João Santos (@Joaosantos.ind).<br>
      Dados de postagem referem-se a menções confirmadas. Junho 2026 parcial — dados até 26/06/2026.
    </div></div><div class="page" id="page-5">
    <div class="page-tag">Relatório individual · Maio–Junho 2026</div>
    <div class="profile-header">
      <div class="profile-avatar" style="background:#FAECE7;color:#4A1B0C">LM</div>
      <div>
        <div class="profile-name">Lara Madeira</div>
        <div class="profile-handle">@laramaddeira</div>
      </div>
    </div>

    <div class="month-switcher" id="switcher-lara_madeira">
      <button class="month-btn active" onclick="switchMonth('lara_madeira','maio',this)">Maio 2026</button>
      <button class="month-btn" onclick="switchMonth('lara_madeira','junho',this)">Junho 2026</button>
    </div>

    <div id="tabs-lara_madeira"><div class="month-tab" id="tab-lara_madeira-maio" style="display:none;">
          <div class="metrics-row">
            <div class="metric-card">
              <div class="metric-label">Postagens</div>
              <div class="metric-value">8</div>
              <div class="metric-sub">8 stories</div>
            </div>
            <div class="metric-card">
              <div class="metric-label">Total vendido</div>
              <div class="metric-value money">R$ 283,58</div>
              <div class="metric-sub">3 pedidos</div>
            </div>
            <div class="metric-card">
              <div class="metric-label">Ticket médio</div>
              <div class="metric-value money">R$ 94,53</div>
              <div class="metric-sub">por pedido</div>
            </div>
            <div class="metric-card accent-card">
              <div class="metric-label">Repasse</div>
              <div class="metric-value money">R$ 28,36</div>
              <div class="metric-sub">10% do total vendido</div>
            </div>
          </div>

          <p class="section-label">Calendário — Maio 2026</p>
          <div class="cal-wrap">
            <div class="cal-header-bar">
              <span class="cal-title">Maio 2026</span>
              <span class="cal-count-badge" style="background:#FAECE7;color:#4A1B0C">8 postagens registradas</span>
            </div>
            
            <div class="cal-weekdays"><span>Dom</span><span>Seg</span><span>Ter</span><span>Qua</span><span>Qui</span><span>Sex</span><span>Sáb</span></div>
            <div class="cal-grid"><div class="cal-day empty"></div><div class="cal-day empty"></div><div class="cal-day empty"></div><div class="cal-day empty"></div><div class="cal-day empty"></div><div class="cal-day"><div class="day-num">01</div></div><div class="cal-day  has-post"><div class="day-num">02</div><div class="cal-marker story-marker" style="background:#FAECE7"><span style="background:#D85A30"></span></div></div><div class="cal-day"><div class="day-num">03</div></div><div class="cal-day"><div class="day-num">04</div></div><div class="cal-day"><div class="day-num">05</div></div><div class="cal-day  has-post"><div class="day-num">06</div><div class="cal-marker story-marker" style="background:#FAECE7"><span style="background:#D85A30"></span></div></div><div class="cal-day"><div class="day-num">07</div></div><div class="cal-day  has-post"><div class="day-num">08</div><div class="cal-marker story-marker" style="background:#FAECE7"><span style="background:#D85A30"></span></div></div><div class="cal-day"><div class="day-num">09</div></div><div class="cal-day"><div class="day-num">10</div></div><div class="cal-day"><div class="day-num">11</div></div><div class="cal-day"><div class="day-num">12</div></div><div class="cal-day  has-post"><div class="day-num">13</div><div class="cal-marker story-marker" style="background:#FAECE7"><span style="background:#D85A30"></span></div></div><div class="cal-day"><div class="day-num">14</div></div><div class="cal-day"><div class="day-num">15</div></div><div class="cal-day"><div class="day-num">16</div></div><div class="cal-day"><div class="day-num">17</div></div><div class="cal-day"><div class="day-num">18</div></div><div class="cal-day  has-post"><div class="day-num">19</div><div class="cal-marker story-marker" style="background:#FAECE7"><span style="background:#D85A30"></span></div></div><div class="cal-day  has-post"><div class="day-num">20</div><div class="cal-marker story-marker" style="background:#FAECE7"><span style="background:#D85A30"></span></div></div><div class="cal-day"><div class="day-num">21</div></div><div class="cal-day"><div class="day-num">22</div></div><div class="cal-day"><div class="day-num">23</div></div><div class="cal-day"><div class="day-num">24</div></div><div class="cal-day"><div class="day-num">25</div></div><div class="cal-day"><div class="day-num">26</div></div><div class="cal-day  has-post"><div class="day-num">27</div><div class="cal-marker story-marker" style="background:#FAECE7"><span style="background:#D85A30"></span></div></div><div class="cal-day  has-post"><div class="day-num">28</div><div class="cal-marker story-marker" style="background:#FAECE7"><span style="background:#D85A30"></span></div></div><div class="cal-day"><div class="day-num">29</div></div><div class="cal-day"><div class="day-num">30</div></div><div class="cal-day"><div class="day-num">31</div></div></div>
          </div>

          <p class="section-label">Datas de postagem</p>
          <div class="dates-wrap"><div class="dates-list"><div class="date-row">
  <span class="date-index">01</span>
  <span class="date-pill">02/05/2026</span>
  <span class="date-day-name">Sábado</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#D85A30"></span>
</div><div class="date-row">
  <span class="date-index">02</span>
  <span class="date-pill">06/05/2026</span>
  <span class="date-day-name">Quarta-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#D85A30"></span>
</div><div class="date-row">
  <span class="date-index">03</span>
  <span class="date-pill">08/05/2026</span>
  <span class="date-day-name">Sexta-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#D85A30"></span>
</div><div class="date-row">
  <span class="date-index">04</span>
  <span class="date-pill">13/05/2026</span>
  <span class="date-day-name">Quarta-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#D85A30"></span>
</div><div class="date-row">
  <span class="date-index">05</span>
  <span class="date-pill">19/05/2026</span>
  <span class="date-day-name">Terça-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#D85A30"></span>
</div><div class="date-row">
  <span class="date-index">06</span>
  <span class="date-pill">20/05/2026</span>
  <span class="date-day-name">Quarta-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#D85A30"></span>
</div><div class="date-row">
  <span class="date-index">07</span>
  <span class="date-pill">27/05/2026</span>
  <span class="date-day-name">Quarta-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#D85A30"></span>
</div><div class="date-row">
  <span class="date-index">08</span>
  <span class="date-pill">28/05/2026</span>
  <span class="date-day-name">Quinta-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#D85A30"></span>
</div></div></div>

          <p class="section-label">Dados de vendas</p>
          <div class="sales-wrap">
        <div class="sales-row"><span class="sales-label">Total vendido</span><span class="sales-value">R$ 283,58</span></div>
        <div class="sales-row"><span class="sales-label">Número de pedidos</span><span class="sales-value">3 pedidos</span></div>
        <div class="sales-row"><span class="sales-label">Ticket médio</span><span class="sales-value">R$ 94,53</span></div>
        <div class="sales-row accent-row">
          <div><div class="sales-label-strong">Repasse (10% do total vendido)</div><div class="sales-note">Calculado sobre o valor total de vendas atribuídas</div></div>
          <div class="sales-value repasse" style="color:#D85A30">R$ 28,36</div>
        </div></div>
        </div><div class="month-tab" id="tab-lara_madeira-junho" style="display:none;">
          <div class="metrics-row">
            <div class="metric-card">
              <div class="metric-label">Postagens</div>
              <div class="metric-value">11</div>
              <div class="metric-sub">10 stories + 1 feed</div>
            </div>
            <div class="metric-card">
              <div class="metric-label">Total vendido</div>
              <div class="metric-value money">R$ 410,95</div>
              <div class="metric-sub">2 pedidos</div>
            </div>
            <div class="metric-card">
              <div class="metric-label">Ticket médio</div>
              <div class="metric-value money">R$ 205,47</div>
              <div class="metric-sub">por pedido</div>
            </div>
            <div class="metric-card accent-card">
              <div class="metric-label">Repasse</div>
              <div class="metric-value money">R$ 20,55</div>
              <div class="metric-sub">5% (vendas até R$ 1.000)</div>
            </div>
          </div>

          <p class="section-label">Calendário — Junho 2026</p>
          <div class="cal-wrap">
            <div class="cal-header-bar">
              <span class="cal-title">Junho 2026</span>
              <span class="cal-count-badge" style="background:#FAECE7;color:#4A1B0C">11 postagens registradas</span>
            </div>
            <div class='cal-legend'><span class='leg-item'><span class='leg-dot' style='background:#D85A30'></span>Story</span><span class='leg-item'><span class='leg-ring' style='border-color:#D85A30'></span>Feed</span></div>
            <div class="cal-weekdays"><span>Dom</span><span>Seg</span><span>Ter</span><span>Qua</span><span>Qui</span><span>Sex</span><span>Sáb</span></div>
            <div class="cal-grid"><div class="cal-day empty"></div><div class="cal-day  has-post"><div class="day-num">01</div><div class="cal-marker story-marker" style="background:#FAECE7"><span style="background:#D85A30"></span></div></div><div class="cal-day"><div class="day-num">02</div></div><div class="cal-day  has-post"><div class="day-num">03</div><div class="cal-marker story-marker" style="background:#FAECE7"><span style="background:#D85A30"></span></div></div><div class="cal-day"><div class="day-num">04</div></div><div class="cal-day"><div class="day-num">05</div></div><div class="cal-day  has-post"><div class="day-num">06</div><div class="cal-marker story-marker" style="background:#FAECE7"><span style="background:#D85A30"></span></div></div><div class="cal-day"><div class="day-num">07</div></div><div class="cal-day"><div class="day-num">08</div></div><div class="cal-day"><div class="day-num">09</div></div><div class="cal-day  has-post"><div class="day-num">10</div><div class="cal-marker story-marker" style="background:#FAECE7"><span style="background:#D85A30"></span></div></div><div class="cal-day  has-post"><div class="day-num">11</div><div class="cal-marker feed-marker" style="border:1.5px solid #D85A30;background:transparent"><span style="background:#D85A30"></span></div></div><div class="cal-day"><div class="day-num">12</div></div><div class="cal-day"><div class="day-num">13</div></div><div class="cal-day"><div class="day-num">14</div></div><div class="cal-day  has-post"><div class="day-num">15</div><div class="cal-marker story-marker" style="background:#FAECE7"><span style="background:#D85A30"></span></div></div><div class="cal-day"><div class="day-num">16</div></div><div class="cal-day  has-post"><div class="day-num">17</div><div class="cal-marker story-marker" style="background:#FAECE7"><span style="background:#D85A30"></span></div></div><div class="cal-day  has-post"><div class="day-num">18</div><div class="cal-marker story-marker" style="background:#FAECE7"><span style="background:#D85A30"></span></div></div><div class="cal-day"><div class="day-num">19</div></div><div class="cal-day  has-post"><div class="day-num">20</div><div class="cal-marker story-marker" style="background:#FAECE7"><span style="background:#D85A30"></span></div></div><div class="cal-day"><div class="day-num">21</div></div><div class="cal-day  has-post"><div class="day-num">22</div><div class="cal-marker story-marker" style="background:#FAECE7"><span style="background:#D85A30"></span></div></div><div class="cal-day"><div class="day-num">23</div></div><div class="cal-day  has-post"><div class="day-num">24</div><div class="cal-marker story-marker" style="background:#FAECE7"><span style="background:#D85A30"></span></div></div><div class="cal-day"><div class="day-num">25</div></div><div class="cal-day"><div class="day-num">26</div></div><div class="cal-day"><div class="day-num">27</div></div><div class="cal-day"><div class="day-num">28</div></div><div class="cal-day"><div class="day-num">29</div></div><div class="cal-day"><div class="day-num">30</div></div></div>
          </div>

          <p class="section-label">Datas de postagem</p>
          <div class="dates-wrap"><div class="dates-list"><div class="date-row">
  <span class="date-index">01</span>
  <span class="date-pill">01/06/2026</span>
  <span class="date-day-name">Segunda-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#D85A30"></span>
</div><div class="date-row">
  <span class="date-index">02</span>
  <span class="date-pill">03/06/2026</span>
  <span class="date-day-name">Quarta-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#D85A30"></span>
</div><div class="date-row">
  <span class="date-index">03</span>
  <span class="date-pill">06/06/2026</span>
  <span class="date-day-name">Sábado</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#D85A30"></span>
</div><div class="date-row">
  <span class="date-index">04</span>
  <span class="date-pill">10/06/2026</span>
  <span class="date-day-name">Quarta-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#D85A30"></span>
</div><div class="date-row">
  <span class="date-index">05</span>
  <span class="date-pill">15/06/2026</span>
  <span class="date-day-name">Segunda-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#D85A30"></span>
</div><div class="date-row">
  <span class="date-index">06</span>
  <span class="date-pill">17/06/2026</span>
  <span class="date-day-name">Quarta-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#D85A30"></span>
</div><div class="date-row">
  <span class="date-index">07</span>
  <span class="date-pill">18/06/2026</span>
  <span class="date-day-name">Quinta-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#D85A30"></span>
</div><div class="date-row">
  <span class="date-index">08</span>
  <span class="date-pill">20/06/2026</span>
  <span class="date-day-name">Sábado</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#D85A30"></span>
</div><div class="date-row">
  <span class="date-index">09</span>
  <span class="date-pill">22/06/2026</span>
  <span class="date-day-name">Segunda-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#D85A30"></span>
</div><div class="date-row">
  <span class="date-index">10</span>
  <span class="date-pill">24/06/2026</span>
  <span class="date-day-name">Quarta-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#D85A30"></span>
</div><div class="date-row">
  <span class="date-index">F01</span>
  <span class="date-pill">11/06/2026</span>
  <span class="date-day-name">Quinta-feira</span>
  <span class="type-badge feed-badge">feed</span>
  <span class="date-dot" style="border:1.5px solid #D85A30;background:transparent"></span>
</div></div></div>

          <p class="section-label">Dados de vendas</p>
          <div class="sales-wrap">
        <div class="sales-row"><span class="sales-label">Total vendido</span><span class="sales-value">R$ 410,95</span></div>
        <div class="sales-row"><span class="sales-label">Número de pedidos</span><span class="sales-value">2 pedidos</span></div>
        <div class="sales-row"><span class="sales-label">Ticket médio</span><span class="sales-value">R$ 205,47</span></div>
        <div class="sales-row accent-row">
          <div><div class="sales-label-strong">Repasse (5% (vendas até R$ 1.000))</div><div class="sales-note">Calculado sobre o valor total de vendas atribuídas</div></div>
          <div class="sales-value repasse" style="color:#D85A30">R$ 20,55</div>
        </div></div>
        </div></div>

    <div class="evo-section">
      <p class="section-label" style="margin-bottom:12px;">Evolução Maio → Junho</p>
      <div class="evo-wrap">
    <div class="evo-row">
      <div class="evo-label">Postagens</div>
      <div class="evo-col"><div class="evo-month">Mai</div><div class="evo-val">8</div></div>
      <div class="evo-arrow">→</div>
      <div class="evo-col"><div class="evo-month">Jun</div><div class="evo-val">11</div></div>
      <div class="evo-delta"><span class="delta positive">▲ 3 posts (38%)</span></div>
    </div>
    <div class="evo-row">
      <div class="evo-label">Vendas</div>
      <div class="evo-col"><div class="evo-month">Mai</div><div class="evo-val sm">R$ 283,58</div></div>
      <div class="evo-arrow">→</div>
      <div class="evo-col"><div class="evo-month">Jun</div><div class="evo-val sm">R$ 410,95</div></div>
      <div class="evo-delta"><span class="delta positive">▲ R$ 127,37 (45%)</span></div>
    </div>
    <div class="evo-row">
      <div class="evo-label">Repasse</div>
      <div class="evo-col"><div class="evo-month">Mai</div><div class="evo-val sm">R$ 28,36</div></div>
      <div class="evo-arrow">→</div>
      <div class="evo-col"><div class="evo-month">Jun</div><div class="evo-val sm">R$ 20,55</div></div>
      <div class="evo-delta"><span class="delta negative">▼ R$ 7,81 (28%)</span></div>
    </div></div>
    </div>

    <div class="footer-note">
      Este relatório é individual e confidencial, gerado para Lara Madeira (@laramaddeira).<br>
      Dados de postagem referem-se a menções confirmadas. Junho 2026 parcial — dados até 26/06/2026.
    </div></div><div class="page" id="page-6">
    <div class="page-tag">Relatório individual · Maio–Junho 2026</div>
    <div class="profile-header">
      <div class="profile-avatar" style="background:#F1EFE8;color:#2C2C2A">MC</div>
      <div>
        <div class="profile-name">Mari Cardoso</div>
        <div class="profile-handle">@by_maricardoso</div>
      </div>
    </div>

    <div class="month-switcher" id="switcher-mari_cardoso">
      <button class="month-btn active" onclick="switchMonth('mari_cardoso','maio',this)">Maio 2026</button>
      <button class="month-btn" onclick="switchMonth('mari_cardoso','junho',this)">Junho 2026</button>
    </div>

    <div id="tabs-mari_cardoso"><div class="month-tab" id="tab-mari_cardoso-maio" style="display:none;">
          <div class="metrics-row">
            <div class="metric-card">
              <div class="metric-label">Postagens</div>
              <div class="metric-value">5</div>
              <div class="metric-sub">5 stories</div>
            </div>
            <div class="metric-card">
              <div class="metric-label">Total vendido</div>
              <div class="metric-value money">R$ 547,17</div>
              <div class="metric-sub">2 pedidos</div>
            </div>
            <div class="metric-card">
              <div class="metric-label">Ticket médio</div>
              <div class="metric-value money">R$ 273,58</div>
              <div class="metric-sub">por pedido</div>
            </div>
            <div class="metric-card accent-card">
              <div class="metric-label">Repasse</div>
              <div class="metric-value money">R$ 54,72</div>
              <div class="metric-sub">10% do total vendido</div>
            </div>
          </div>

          <p class="section-label">Calendário — Maio 2026</p>
          <div class="cal-wrap">
            <div class="cal-header-bar">
              <span class="cal-title">Maio 2026</span>
              <span class="cal-count-badge" style="background:#F1EFE8;color:#2C2C2A">5 postagens registradas</span>
            </div>
            
            <div class="cal-weekdays"><span>Dom</span><span>Seg</span><span>Ter</span><span>Qua</span><span>Qui</span><span>Sex</span><span>Sáb</span></div>
            <div class="cal-grid"><div class="cal-day empty"></div><div class="cal-day empty"></div><div class="cal-day empty"></div><div class="cal-day empty"></div><div class="cal-day empty"></div><div class="cal-day"><div class="day-num">01</div></div><div class="cal-day"><div class="day-num">02</div></div><div class="cal-day"><div class="day-num">03</div></div><div class="cal-day"><div class="day-num">04</div></div><div class="cal-day"><div class="day-num">05</div></div><div class="cal-day"><div class="day-num">06</div></div><div class="cal-day  has-post"><div class="day-num">07</div><div class="cal-marker story-marker" style="background:#F1EFE8"><span style="background:#888780"></span></div></div><div class="cal-day"><div class="day-num">08</div></div><div class="cal-day"><div class="day-num">09</div></div><div class="cal-day"><div class="day-num">10</div></div><div class="cal-day  has-post"><div class="day-num">11</div><div class="cal-marker story-marker" style="background:#F1EFE8"><span style="background:#888780"></span></div></div><div class="cal-day"><div class="day-num">12</div></div><div class="cal-day"><div class="day-num">13</div></div><div class="cal-day"><div class="day-num">14</div></div><div class="cal-day"><div class="day-num">15</div></div><div class="cal-day"><div class="day-num">16</div></div><div class="cal-day  has-post"><div class="day-num">17</div><div class="cal-marker story-marker" style="background:#F1EFE8"><span style="background:#888780"></span></div></div><div class="cal-day"><div class="day-num">18</div></div><div class="cal-day"><div class="day-num">19</div></div><div class="cal-day"><div class="day-num">20</div></div><div class="cal-day"><div class="day-num">21</div></div><div class="cal-day  has-post"><div class="day-num">22</div><div class="cal-marker story-marker" style="background:#F1EFE8"><span style="background:#888780"></span></div></div><div class="cal-day"><div class="day-num">23</div></div><div class="cal-day"><div class="day-num">24</div></div><div class="cal-day"><div class="day-num">25</div></div><div class="cal-day"><div class="day-num">26</div></div><div class="cal-day"><div class="day-num">27</div></div><div class="cal-day"><div class="day-num">28</div></div><div class="cal-day"><div class="day-num">29</div></div><div class="cal-day  has-post"><div class="day-num">30</div><div class="cal-marker story-marker" style="background:#F1EFE8"><span style="background:#888780"></span></div></div><div class="cal-day"><div class="day-num">31</div></div></div>
          </div>

          <p class="section-label">Datas de postagem</p>
          <div class="dates-wrap"><div class="dates-list"><div class="date-row">
  <span class="date-index">01</span>
  <span class="date-pill">07/05/2026</span>
  <span class="date-day-name">Quinta-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#888780"></span>
</div><div class="date-row">
  <span class="date-index">02</span>
  <span class="date-pill">11/05/2026</span>
  <span class="date-day-name">Segunda-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#888780"></span>
</div><div class="date-row">
  <span class="date-index">03</span>
  <span class="date-pill">17/05/2026</span>
  <span class="date-day-name">Domingo</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#888780"></span>
</div><div class="date-row">
  <span class="date-index">04</span>
  <span class="date-pill">22/05/2026</span>
  <span class="date-day-name">Sexta-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#888780"></span>
</div><div class="date-row">
  <span class="date-index">05</span>
  <span class="date-pill">30/05/2026</span>
  <span class="date-day-name">Sábado</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#888780"></span>
</div></div></div>

          <p class="section-label">Dados de vendas</p>
          <div class="sales-wrap">
        <div class="sales-row"><span class="sales-label">Total vendido</span><span class="sales-value">R$ 547,17</span></div>
        <div class="sales-row"><span class="sales-label">Número de pedidos</span><span class="sales-value">2 pedidos</span></div>
        <div class="sales-row"><span class="sales-label">Ticket médio</span><span class="sales-value">R$ 273,58</span></div>
        <div class="sales-row accent-row">
          <div><div class="sales-label-strong">Repasse (10% do total vendido)</div><div class="sales-note">Calculado sobre o valor total de vendas atribuídas</div></div>
          <div class="sales-value repasse" style="color:#888780">R$ 54,72</div>
        </div></div>
        </div><div class="month-tab" id="tab-mari_cardoso-junho" style="display:none;">
          <div class="metrics-row">
            <div class="metric-card">
              <div class="metric-label">Postagens</div>
              <div class="metric-value">6</div>
              <div class="metric-sub">6 stories</div>
            </div>
            <div class="metric-card">
              <div class="metric-label">Total vendido</div>
              <div class="metric-value money">R$ 688,27</div>
              <div class="metric-sub">3 pedidos</div>
            </div>
            <div class="metric-card">
              <div class="metric-label">Ticket médio</div>
              <div class="metric-value money">R$ 229,42</div>
              <div class="metric-sub">por pedido</div>
            </div>
            <div class="metric-card accent-card">
              <div class="metric-label">Repasse</div>
              <div class="metric-value money">R$ 34,41</div>
              <div class="metric-sub">5% (vendas até R$ 1.000)</div>
            </div>
          </div>

          <p class="section-label">Calendário — Junho 2026</p>
          <div class="cal-wrap">
            <div class="cal-header-bar">
              <span class="cal-title">Junho 2026</span>
              <span class="cal-count-badge" style="background:#F1EFE8;color:#2C2C2A">6 postagens registradas</span>
            </div>
            
            <div class="cal-weekdays"><span>Dom</span><span>Seg</span><span>Ter</span><span>Qua</span><span>Qui</span><span>Sex</span><span>Sáb</span></div>
            <div class="cal-grid"><div class="cal-day empty"></div><div class="cal-day"><div class="day-num">01</div></div><div class="cal-day  has-post"><div class="day-num">02</div><div class="cal-marker story-marker" style="background:#F1EFE8"><span style="background:#888780"></span></div></div><div class="cal-day"><div class="day-num">03</div></div><div class="cal-day"><div class="day-num">04</div></div><div class="cal-day  has-post"><div class="day-num">05</div><div class="cal-marker story-marker" style="background:#F1EFE8"><span style="background:#888780"></span></div></div><div class="cal-day"><div class="day-num">06</div></div><div class="cal-day"><div class="day-num">07</div></div><div class="cal-day"><div class="day-num">08</div></div><div class="cal-day"><div class="day-num">09</div></div><div class="cal-day"><div class="day-num">10</div></div><div class="cal-day  has-post"><div class="day-num">11</div><div class="cal-marker story-marker" style="background:#F1EFE8"><span style="background:#888780"></span></div></div><div class="cal-day"><div class="day-num">12</div></div><div class="cal-day"><div class="day-num">13</div></div><div class="cal-day"><div class="day-num">14</div></div><div class="cal-day"><div class="day-num">15</div></div><div class="cal-day  has-post"><div class="day-num">16</div><div class="cal-marker story-marker" style="background:#F1EFE8"><span style="background:#888780"></span></div></div><div class="cal-day"><div class="day-num">17</div></div><div class="cal-day  has-post"><div class="day-num">18</div><div class="cal-marker story-marker" style="background:#F1EFE8"><span style="background:#888780"></span></div></div><div class="cal-day"><div class="day-num">19</div></div><div class="cal-day"><div class="day-num">20</div></div><div class="cal-day"><div class="day-num">21</div></div><div class="cal-day"><div class="day-num">22</div></div><div class="cal-day"><div class="day-num">23</div></div><div class="cal-day"><div class="day-num">24</div></div><div class="cal-day"><div class="day-num">25</div></div><div class="cal-day  has-post"><div class="day-num">26</div><div class="cal-marker story-marker" style="background:#F1EFE8"><span style="background:#888780"></span></div></div><div class="cal-day"><div class="day-num">27</div></div><div class="cal-day"><div class="day-num">28</div></div><div class="cal-day"><div class="day-num">29</div></div><div class="cal-day"><div class="day-num">30</div></div></div>
          </div>

          <p class="section-label">Datas de postagem</p>
          <div class="dates-wrap"><div class="dates-list"><div class="date-row">
  <span class="date-index">01</span>
  <span class="date-pill">02/06/2026</span>
  <span class="date-day-name">Terça-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#888780"></span>
</div><div class="date-row">
  <span class="date-index">02</span>
  <span class="date-pill">05/06/2026</span>
  <span class="date-day-name">Sexta-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#888780"></span>
</div><div class="date-row">
  <span class="date-index">03</span>
  <span class="date-pill">11/06/2026</span>
  <span class="date-day-name">Quinta-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#888780"></span>
</div><div class="date-row">
  <span class="date-index">04</span>
  <span class="date-pill">16/06/2026</span>
  <span class="date-day-name">Terça-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#888780"></span>
</div><div class="date-row">
  <span class="date-index">05</span>
  <span class="date-pill">18/06/2026</span>
  <span class="date-day-name">Quinta-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#888780"></span>
</div><div class="date-row">
  <span class="date-index">06</span>
  <span class="date-pill">26/06/2026</span>
  <span class="date-day-name">Sexta-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#888780"></span>
</div></div></div>

          <p class="section-label">Dados de vendas</p>
          <div class="sales-wrap">
        <div class="sales-row"><span class="sales-label">Total vendido</span><span class="sales-value">R$ 688,27</span></div>
        <div class="sales-row"><span class="sales-label">Número de pedidos</span><span class="sales-value">3 pedidos</span></div>
        <div class="sales-row"><span class="sales-label">Ticket médio</span><span class="sales-value">R$ 229,42</span></div>
        <div class="sales-row accent-row">
          <div><div class="sales-label-strong">Repasse (5% (vendas até R$ 1.000))</div><div class="sales-note">Calculado sobre o valor total de vendas atribuídas</div></div>
          <div class="sales-value repasse" style="color:#888780">R$ 34,41</div>
        </div></div>
        </div></div>

    <div class="evo-section">
      <p class="section-label" style="margin-bottom:12px;">Evolução Maio → Junho</p>
      <div class="evo-wrap">
    <div class="evo-row">
      <div class="evo-label">Postagens</div>
      <div class="evo-col"><div class="evo-month">Mai</div><div class="evo-val">5</div></div>
      <div class="evo-arrow">→</div>
      <div class="evo-col"><div class="evo-month">Jun</div><div class="evo-val">6</div></div>
      <div class="evo-delta"><span class="delta positive">▲ 1 posts (20%)</span></div>
    </div>
    <div class="evo-row">
      <div class="evo-label">Vendas</div>
      <div class="evo-col"><div class="evo-month">Mai</div><div class="evo-val sm">R$ 547,17</div></div>
      <div class="evo-arrow">→</div>
      <div class="evo-col"><div class="evo-month">Jun</div><div class="evo-val sm">R$ 688,27</div></div>
      <div class="evo-delta"><span class="delta positive">▲ R$ 141,10 (26%)</span></div>
    </div>
    <div class="evo-row">
      <div class="evo-label">Repasse</div>
      <div class="evo-col"><div class="evo-month">Mai</div><div class="evo-val sm">R$ 54,72</div></div>
      <div class="evo-arrow">→</div>
      <div class="evo-col"><div class="evo-month">Jun</div><div class="evo-val sm">R$ 34,41</div></div>
      <div class="evo-delta"><span class="delta negative">▼ R$ 20,30 (37%)</span></div>
    </div></div>
    </div>

    <div class="footer-note">
      Este relatório é individual e confidencial, gerado para Mari Cardoso (@by_maricardoso).<br>
      Dados de postagem referem-se a menções confirmadas. Junho 2026 parcial — dados até 26/06/2026.
    </div></div><div class="page" id="page-7">
    <div class="page-tag">Relatório individual · Maio–Junho 2026</div>
    <div class="profile-header">
      <div class="profile-avatar" style="background:#F3EAF5;color:#4A1A52">GM</div>
      <div>
        <div class="profile-name">Guilherme Madona</div>
        <div class="profile-handle">@gui_madona</div>
      </div>
    </div>

    <div class="month-switcher" id="switcher-guilherme_madona">
      <button class="month-btn active" onclick="switchMonth('guilherme_madona','maio',this)">Maio 2026</button>
      <button class="month-btn" onclick="switchMonth('guilherme_madona','junho',this)">Junho 2026</button>
    </div>

    <div id="tabs-guilherme_madona"><div class="month-tab" id="tab-guilherme_madona-maio" style="display:none;">
          <div class="metrics-row">
            <div class="metric-card">
              <div class="metric-label">Postagens</div>
              <div class="metric-value">0</div>
              <div class="metric-sub">0 stories</div>
            </div>
            <div class="metric-card">
              <div class="metric-label">Total vendido</div>
              <div class="metric-value money">R$ 0,00</div>
              <div class="metric-sub">0 pedidos</div>
            </div>
            <div class="metric-card">
              <div class="metric-label">Ticket médio</div>
              <div class="metric-value money">—</div>
              <div class="metric-sub">por pedido</div>
            </div>
            <div class="metric-card accent-card">
              <div class="metric-label">Repasse</div>
              <div class="metric-value money">R$ 0,00</div>
              <div class="metric-sub">10% do total vendido</div>
            </div>
          </div>

          <p class="section-label">Calendário — Maio 2026</p>
          <div class="cal-wrap">
            <div class="cal-header-bar">
              <span class="cal-title">Maio 2026</span>
              <span class="cal-count-badge" style="background:#F3EAF5;color:#4A1A52">0 postagens registradas</span>
            </div>
            
            <div class="cal-weekdays"><span>Dom</span><span>Seg</span><span>Ter</span><span>Qua</span><span>Qui</span><span>Sex</span><span>Sáb</span></div>
            <div class="cal-grid"><div class="cal-day empty"></div><div class="cal-day empty"></div><div class="cal-day empty"></div><div class="cal-day empty"></div><div class="cal-day empty"></div><div class="cal-day"><div class="day-num">01</div></div><div class="cal-day"><div class="day-num">02</div></div><div class="cal-day"><div class="day-num">03</div></div><div class="cal-day"><div class="day-num">04</div></div><div class="cal-day"><div class="day-num">05</div></div><div class="cal-day"><div class="day-num">06</div></div><div class="cal-day"><div class="day-num">07</div></div><div class="cal-day"><div class="day-num">08</div></div><div class="cal-day"><div class="day-num">09</div></div><div class="cal-day"><div class="day-num">10</div></div><div class="cal-day"><div class="day-num">11</div></div><div class="cal-day"><div class="day-num">12</div></div><div class="cal-day"><div class="day-num">13</div></div><div class="cal-day"><div class="day-num">14</div></div><div class="cal-day"><div class="day-num">15</div></div><div class="cal-day"><div class="day-num">16</div></div><div class="cal-day"><div class="day-num">17</div></div><div class="cal-day"><div class="day-num">18</div></div><div class="cal-day"><div class="day-num">19</div></div><div class="cal-day"><div class="day-num">20</div></div><div class="cal-day"><div class="day-num">21</div></div><div class="cal-day"><div class="day-num">22</div></div><div class="cal-day"><div class="day-num">23</div></div><div class="cal-day"><div class="day-num">24</div></div><div class="cal-day"><div class="day-num">25</div></div><div class="cal-day"><div class="day-num">26</div></div><div class="cal-day"><div class="day-num">27</div></div><div class="cal-day"><div class="day-num">28</div></div><div class="cal-day"><div class="day-num">29</div></div><div class="cal-day"><div class="day-num">30</div></div><div class="cal-day"><div class="day-num">31</div></div></div>
          </div>

          <p class="section-label">Datas de postagem</p>
          <div class="dates-wrap"><div class="dates-list"><div class="date-row"><span class="date-day-name" style="font-style:italic;color:var(--text-tertiary)">Nenhuma postagem registrada neste mês.</span></div></div></div>

          <p class="section-label">Dados de vendas</p>
          <div class="sales-wrap"><div class="no-sales">Nenhuma venda registrada para este período.</div></div>
        </div><div class="month-tab" id="tab-guilherme_madona-junho" style="display:none;">
          <div class="metrics-row">
            <div class="metric-card">
              <div class="metric-label">Postagens</div>
              <div class="metric-value">3</div>
              <div class="metric-sub">2 stories + 1 feed</div>
            </div>
            <div class="metric-card">
              <div class="metric-label">Total vendido</div>
              <div class="metric-value money">R$ 172,60</div>
              <div class="metric-sub">1 pedido</div>
            </div>
            <div class="metric-card">
              <div class="metric-label">Ticket médio</div>
              <div class="metric-value money">R$ 172,60</div>
              <div class="metric-sub">por pedido</div>
            </div>
            <div class="metric-card accent-card">
              <div class="metric-label">Repasse</div>
              <div class="metric-value money">R$ 8,63</div>
              <div class="metric-sub">5% (vendas até R$ 1.000)</div>
            </div>
          </div>

          <p class="section-label">Calendário — Junho 2026</p>
          <div class="cal-wrap">
            <div class="cal-header-bar">
              <span class="cal-title">Junho 2026</span>
              <span class="cal-count-badge" style="background:#F3EAF5;color:#4A1A52">3 postagens registradas</span>
            </div>
            <div class='cal-legend'><span class='leg-item'><span class='leg-dot' style='background:#9B5EA2'></span>Story</span><span class='leg-item'><span class='leg-ring' style='border-color:#9B5EA2'></span>Feed</span></div>
            <div class="cal-weekdays"><span>Dom</span><span>Seg</span><span>Ter</span><span>Qua</span><span>Qui</span><span>Sex</span><span>Sáb</span></div>
            <div class="cal-grid"><div class="cal-day empty"></div><div class="cal-day"><div class="day-num">01</div></div><div class="cal-day"><div class="day-num">02</div></div><div class="cal-day"><div class="day-num">03</div></div><div class="cal-day"><div class="day-num">04</div></div><div class="cal-day"><div class="day-num">05</div></div><div class="cal-day"><div class="day-num">06</div></div><div class="cal-day"><div class="day-num">07</div></div><div class="cal-day"><div class="day-num">08</div></div><div class="cal-day"><div class="day-num">09</div></div><div class="cal-day"><div class="day-num">10</div></div><div class="cal-day"><div class="day-num">11</div></div><div class="cal-day"><div class="day-num">12</div></div><div class="cal-day"><div class="day-num">13</div></div><div class="cal-day"><div class="day-num">14</div></div><div class="cal-day"><div class="day-num">15</div></div><div class="cal-day"><div class="day-num">16</div></div><div class="cal-day"><div class="day-num">17</div></div><div class="cal-day  has-post"><div class="day-num">18</div><div class="cal-marker feed-marker" style="border:1.5px solid #9B5EA2;background:transparent"><span style="background:#9B5EA2"></span></div></div><div class="cal-day"><div class="day-num">19</div></div><div class="cal-day  has-post"><div class="day-num">20</div><div class="cal-marker story-marker" style="background:#F3EAF5"><span style="background:#9B5EA2"></span></div></div><div class="cal-day"><div class="day-num">21</div></div><div class="cal-day  has-post"><div class="day-num">22</div><div class="cal-marker story-marker" style="background:#F3EAF5"><span style="background:#9B5EA2"></span></div></div><div class="cal-day"><div class="day-num">23</div></div><div class="cal-day"><div class="day-num">24</div></div><div class="cal-day"><div class="day-num">25</div></div><div class="cal-day"><div class="day-num">26</div></div><div class="cal-day"><div class="day-num">27</div></div><div class="cal-day"><div class="day-num">28</div></div><div class="cal-day"><div class="day-num">29</div></div><div class="cal-day"><div class="day-num">30</div></div></div>
          </div>

          <p class="section-label">Datas de postagem</p>
          <div class="dates-wrap"><div class="dates-list"><div class="date-row">
  <span class="date-index">01</span>
  <span class="date-pill">20/06/2026</span>
  <span class="date-day-name">Sábado</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#9B5EA2"></span>
</div><div class="date-row">
  <span class="date-index">02</span>
  <span class="date-pill">22/06/2026</span>
  <span class="date-day-name">Segunda-feira</span>
  <span class="type-badge story-badge">story</span>
  <span class="date-dot" style="background:#9B5EA2"></span>
</div><div class="date-row">
  <span class="date-index">F01</span>
  <span class="date-pill">18/06/2026</span>
  <span class="date-day-name">Quinta-feira</span>
  <span class="type-badge feed-badge">feed</span>
  <span class="date-dot" style="border:1.5px solid #9B5EA2;background:transparent"></span>
</div></div></div>

          <p class="section-label">Dados de vendas</p>
          <div class="sales-wrap">
        <div class="sales-row"><span class="sales-label">Total vendido</span><span class="sales-value">R$ 172,60</span></div>
        <div class="sales-row"><span class="sales-label">Número de pedidos</span><span class="sales-value">1 pedido</span></div>
        <div class="sales-row"><span class="sales-label">Ticket médio</span><span class="sales-value">R$ 172,60</span></div>
        <div class="sales-row accent-row">
          <div><div class="sales-label-strong">Repasse (5% (vendas até R$ 1.000))</div><div class="sales-note">Calculado sobre o valor total de vendas atribuídas</div></div>
          <div class="sales-value repasse" style="color:#9B5EA2">R$ 8,63</div>
        </div></div>
        </div></div>

    <div class="evo-section">
      <p class="section-label" style="margin-bottom:12px;">Evolução Maio → Junho</p>
      <div class="evo-wrap">
    <div class="evo-row">
      <div class="evo-label">Postagens</div>
      <div class="evo-col"><div class="evo-month">Mai</div><div class="evo-val">0</div></div>
      <div class="evo-arrow">→</div>
      <div class="evo-col"><div class="evo-month">Jun</div><div class="evo-val">3</div></div>
      <div class="evo-delta"><span class="delta positive">▲ novo</span></div>
    </div>
    <div class="evo-row">
      <div class="evo-label">Vendas</div>
      <div class="evo-col"><div class="evo-month">Mai</div><div class="evo-val sm">R$ 0,00</div></div>
      <div class="evo-arrow">→</div>
      <div class="evo-col"><div class="evo-month">Jun</div><div class="evo-val sm">R$ 172,60</div></div>
      <div class="evo-delta"><span class="delta positive">▲ novo</span></div>
    </div>
    <div class="evo-row">
      <div class="evo-label">Repasse</div>
      <div class="evo-col"><div class="evo-month">Mai</div><div class="evo-val sm">R$ 0,00</div></div>
      <div class="evo-arrow">→</div>
      <div class="evo-col"><div class="evo-month">Jun</div><div class="evo-val sm">R$ 8,63</div></div>
      <div class="evo-delta"><span class="delta positive">▲ novo</span></div>
    </div></div>
    </div>

    <div class="footer-note">
      Este relatório é individual e confidencial, gerado para Guilherme Madona (@gui_madona).<br>
      Dados de postagem referem-se a menções confirmadas. Junho 2026 parcial — dados até 26/06/2026.
    </div></div></main>
  </div>
</div>
<script>
let currentIdx = 0;
const influencers = [{"name":"Isabela Raquel","slug":"isabela_raquel","handle":"@raquelisabela_"},{"name":"Jackeline Barone","slug":"jackeline_barone","handle":"@Jackebarone"},{"name":"João Luiz Sato","slug":"joao_luiz_sato","handle":"@sattojoao_"},{"name":"Emanuelle Moraes","slug":"emanuelle_moraes","handle":"@manumoraees_"},{"name":"João Santos","slug":"joao_santos","handle":"@Joaosantos.ind"},{"name":"Lara Madeira","slug":"lara_madeira","handle":"@laramaddeira"},{"name":"Mari Cardoso","slug":"mari_cardoso","handle":"@by_maricardoso"},{"name":"Guilherme Madona","slug":"guilherme_madona","handle":"@gui_madona"}];

function switchMonth(slug, month, btn) {
  document.querySelectorAll(`#tabs-${slug} .month-tab`).forEach(t => t.style.display = 'none');
  document.getElementById(`tab-${slug}-${month}`).style.display = 'block';
  document.querySelectorAll(`#switcher-${slug} .month-btn`).forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
}

function showPage(idx) {
  idx = parseInt(idx);
  currentIdx = idx;
  document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
  document.querySelectorAll('.nav-item').forEach(n => n.classList.remove('active'));
  document.getElementById(`page-${idx}`).classList.add('active');
  document.querySelector(`.nav-item[data-idx="${idx}"]`)?.classList.add('active');
  document.getElementById('mobile-select').value = idx;
  window.scrollTo(0,0);
  // activate first month tab on switch
  const slug = influencers[idx].slug;
  const maio = document.getElementById(`tab-${slug}-maio`);
  const junho = document.getElementById(`tab-${slug}-junho`);
  if (maio) maio.style.display = 'block';
  if (junho) junho.style.display = 'none';
  document.querySelectorAll(`#switcher-${slug} .month-btn`).forEach((b,i) => b.classList.toggle('active', i===0));
}

function exportPDF() {
  const inf = influencers[currentIdx];
  document.querySelectorAll('.page').forEach(p => p.classList.remove('print-target'));
  document.getElementById(`page-${currentIdx}`).classList.add('print-target');
  const orig = document.title;
  document.title = `Relatorio_${inf.name.replace(/ /g,'_')}_Mai-Jun2026`;
  setTimeout(() => { window.print(); document.title = orig; }, 120);
}

// init
document.addEventListener('DOMContentLoaded', () => {
  showPage(0);
});
</script>
</body>
</html>
