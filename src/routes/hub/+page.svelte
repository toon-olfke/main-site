<script>
  const tools = [
    {
      name: "Zammad",
      description: "Ticketing & helpdesk",
      url: "http://10.10.1.112:8080",
      tag: "SUPPORT",
      icon: `<svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M21 15a2 2 0 0 1-2 2H7l-4 4V5a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2z"/></svg>`
    },
    {
      name: "Kimai",
      description: "Urenregistratie & facturatie",
      url: "http://10.10.1.112:8001",
      tag: "TIJD",
      icon: `<svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"/><polyline points="12 6 12 12 16 14"/></svg>`
    },
    {
      name: "Twenty CRM",
      description: "Klantenbeheer & pipeline",
      url: "http://10.10.1.112:3002",
      tag: "CRM",
      icon: `<svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M17 21v-2a4 4 0 0 0-4-4H5a4 4 0 0 0-4 4v2"/><circle cx="9" cy="7" r="4"/><path d="M23 21v-2a4 4 0 0 0-3-3.87"/><path d="M16 3.13a4 4 0 0 1 0 7.75"/></svg>`
    }
  ];

  const tagColors = {
    "SUPPORT": "#3b82f6",
    "TIJD": "#10b981",
    "CRM": "#8b5cf6"
  };
</script>

<svelte:head>
  <title>Kernloos — Intern</title>
  <meta name="robots" content="noindex, nofollow">
</svelte:head>

<div class="hub">
  <!-- <header class="hub-header">
    <div class="header-inner">
      <div class="brand">
        <svg class="logo" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 32 32">
          <rect width="32" height="32" fill="#0d0d0d"/>
          <text x="16" y="23" font-family="sans-serif" font-weight="900" font-size="20" text-anchor="middle" fill="#e8d84b">K</text>
        </svg>
        <div>
          <div class="brand-name">KERNLOOS</div>
          <div class="brand-sub">Intern dashboard</div>
        </div>
      </div>
      <div class="header-meta">
        <div class="status-dot"></div>
        <span>Alle systemen operationeel</span>
      </div>
    </div>
  </header> -->

  <main class="hub-main">
    <div class="section-label">TOOLS & SYSTEMEN</div>
    <div class="grid">
      {#each tools as tool}
        <a href={tool.url} target="_blank" rel="noopener" class="card">
          <div class="card-top">
            <div class="card-icon">{@html tool.icon}</div>
            <div class="card-tag" style="background: {tagColors[tool.tag]}22; color: {tagColors[tool.tag]}; border-color: {tagColors[tool.tag]}44;">
              {tool.tag}
            </div>
          </div>
          <div class="card-name">{tool.name}</div>
          <div class="card-desc">{tool.description}</div>
          <div class="card-arrow">
            <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
              <path d="M7 17L17 7M17 7H7M17 7v10"/>
            </svg>
          </div>
        </a>
      {/each}
    </div>
  </main>

  <footer class="hub-footer">
    <span>Kernloos — Intern gebruik</span>
    <span>Niet indexeren — Geen publieke toegang</span>
  </footer>
</div>

<style>
  :global(body) {
    margin: 0;
    background: #0d0d0d;
  }

  .hub {
    min-height: 100vh;
    background: #0d0d0d;
    color: #f4f1ea;
    font-family: 'DM Mono', 'Courier New', monospace;
    display: flex;
    flex-direction: column;
  }

  /* HEADER */
  .hub-header {
    border-bottom: 1px solid #1e1e1e;
    padding: 0 32px;
  }

  .header-inner {
    max-width: 1100px;
    margin: 0 auto;
    height: 64px;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .brand {
    display: flex;
    align-items: center;
    gap: 14px;
  }

  .logo {
    width: 36px;
    height: 36px;
    border: 1px solid #2a2a2a;
  }

  .brand-name {
    font-family: 'Unbounded', sans-serif;
    font-size: 14px;
    font-weight: 900;
    letter-spacing: -0.01em;
    color: #f4f1ea;
    line-height: 1;
  }

  .brand-sub {
    font-size: 9px;
    text-transform: uppercase;
    letter-spacing: 0.1em;
    color: #7a776e;
    margin-top: 3px;
  }

  .header-meta {
    display: flex;
    align-items: center;
    gap: 8px;
    font-size: 11px;
    color: #7a776e;
  }

  .status-dot {
    width: 7px;
    height: 7px;
    border-radius: 50%;
    background: #10b981;
    box-shadow: 0 0 6px #10b981;
    animation: pulse 2s infinite;
  }

  @keyframes pulse {
    0%, 100% { opacity: 1; }
    50% { opacity: 0.4; }
  }

  /* MAIN */
  .hub-main {
    flex: 1;
    max-width: 1100px;
    margin: 0 auto;
    padding: 48px 32px;
    width: 100%;
  }

  .section-label {
    font-size: 9px;
    text-transform: uppercase;
    letter-spacing: 0.15em;
    color: #7a776e;
    margin-bottom: 20px;
    padding-bottom: 12px;
    border-bottom: 1px solid #1e1e1e;
  }

  .grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
    gap: 1px;
    background: #1e1e1e;
    border: 1px solid #1e1e1e;
  }

  .card {
    background: #0d0d0d;
    padding: 24px;
    text-decoration: none;
    color: inherit;
    display: flex;
    flex-direction: column;
    gap: 6px;
    position: relative;
    transition: background 0.15s;
    cursor: pointer;
  }

  .card:hover {
    background: #141414;
  }

  .card:hover .card-arrow {
    opacity: 1;
    transform: translate(2px, -2px);
  }

  .card:hover .card-name {
    color: #e8d84b;
  }

  .card-top {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 8px;
  }

  .card-icon {
    color: #7a776e;
    transition: color 0.15s;
  }

  .card:hover .card-icon {
    color: #e8d84b;
  }

  .card-tag {
    font-size: 8px;
    font-weight: 500;
    text-transform: uppercase;
    letter-spacing: 0.1em;
    padding: 2px 8px;
    border: 1px solid;
    border-radius: 2px;
  }

  .card-name {
    font-family: 'Unbounded', sans-serif;
    font-size: 13px;
    font-weight: 700;
    color: #f4f1ea;
    transition: color 0.15s;
    letter-spacing: -0.01em;
  }

  .card-desc {
    font-size: 11px;
    color: #7a776e;
    line-height: 1.5;
  }

  .card-arrow {
    position: absolute;
    bottom: 20px;
    right: 20px;
    color: #7a776e;
    opacity: 0;
    transition: all 0.15s;
  }

  /* FOOTER */
  .hub-footer {
    border-top: 1px solid #1e1e1e;
    padding: 16px 32px;
    display: flex;
    justify-content: space-between;
    font-size: 10px;
    color: #3a3a3a;
    max-width: 1100px;
    margin: 0 auto;
    width: 100%;
  }

  @media (max-width: 600px) {
    .hub-main { padding: 24px 16px; }
    .hub-header { padding: 0 16px; }
    .header-meta { display: none; }
    .grid { grid-template-columns: 1fr; }
  }
</style>