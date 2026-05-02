<script lang="ts">
	const services = [
		{
			number: '01',
			title: 'Infrastructuur',
			description: 'Netwerken, servers, firewalls. De dingen die niemand ziet tot ze kapotgaan.'
		},
		{
			number: '02',
			title: 'Consultancy',
			description: 'We kijken naar uw setup, zeggen wat er fout is, en helpen het recht te zetten. Zonder PowerPoint.'
		},
		{
			number: '03',
			title: 'Ondersteuning',
			description: 'Dingen blijven kapotgaan. Wij blijven er ook. Dat is de deal.'
		}
	];

	const stats = [
		{ value: '2', label: 'mensen' },
		{ value: '0', label: 'foosballtafels' },
		{ value: '100%', label: 'uptijd (ambitie)' },
		{ value: '∞', label: 'koffie gedronken' }
	];
</script>

<svelte:head>
	<title>Kernloos — IT zonder fratsen</title>
</svelte:head>

<!-- HERO -->
<section class="hero">
	<div class="hero-inner">
		<div class="hero-label">
			<span class="mono tag">Infrastructure & Consultancy — Gent</span>
		</div>

		<h1 class="hero-title">
			We<br />
			<span class="yellow-block">fixen</span><br />
			uw IT.
		</h1>

		<div class="hero-right">
			<p class="hero-sub">
				Kernloos is een tweekoppig IT-bedrijf uit Gent. We leggen ons toe op infrastructuur, netwerken en consultancy. Zonder bullshit, zonder onnodig jargon, zonder beloftes die we niet kunnen waarmaken.
			</p>
			<div class="hero-actions">
				<a href="/contact" class="btn-primary">Neem contact op</a>
				<a href="/diensten" class="btn-ghost">Wat we doen →</a>
			</div>
		</div>
	</div>

	<!-- Ticker -->
	<div class="ticker-wrap" aria-hidden="true">
		<div class="ticker">
			{#each Array(3) as _}
				<span>GEEN FOOSBALLTAFEL</span>
				<span class="dot">◆</span>
				<span>WEL EEN OPLOSSING</span>
				<span class="dot">◆</span>
				<span>KERNLOOS IT</span>
				<span class="dot">◆</span>
				<span>GENT, BELGIË</span>
				<span class="dot">◆</span>
				<span>INFRASTRUCTUUR & CONSULTANCY</span>
				<span class="dot">◆</span>
			{/each}
		</div>
	</div>
</section>

<!-- STATS -->
<section class="stats-bar">
	{#each stats as stat}
		<div class="stat">
			<span class="stat-value">{stat.value}</span>
			<span class="stat-label mono">{stat.label}</span>
		</div>
	{/each}
</section>

<!-- SERVICES PREVIEW -->
<section class="services-section">
	<div class="section-inner">
		<div class="section-header">
			<span class="mono section-tag">// wat we doen</span>
			<h2 class="section-title">Diensten</h2>
		</div>

		<div class="services-grid">
			{#each services as s}
				<div class="service-card">
					<span class="service-num mono">{s.number}</span>
					<h3 class="service-title">{s.title}</h3>
					<p class="service-desc">{s.description}</p>
				</div>
			{/each}
		</div>

		<a href="/diensten" class="more-link">Alle diensten bekijken →</a>
	</div>
</section>

<!-- MANIFESTO STRIP -->
<section class="manifesto">
	<div class="manifesto-inner">
		<blockquote>
			"We zijn geen groot IT-bedrijf. We zijn twee mensen die goed zijn in wat ze doen, eerlijk over wat ze niet zijn, en bereikbaar als het erop aankomt."
		</blockquote>
		<a href="/over" class="btn-yellow">Over Kernloos</a>
	</div>
</section>

<!-- CONTACT TEASER -->
<section class="contact-teaser">
	<div class="section-inner">
		<div class="contact-teaser-grid">
			<div>
				<span class="mono section-tag">// klaar om te beginnen?</span>
				<h2 class="section-title">Vertel ons<br />wat er speelt.</h2>
			</div>
			<div class="contact-teaser-right">
				<p>Geen verplichtingen. Geen formulier van 14 pagina's. Gewoon een eerlijk gesprek over wat u nodig heeft.</p>
				<a href="/contact" class="btn-primary">Stuur een bericht</a>
			</div>
		</div>
	</div>
</section>

<style>
	/* HERO */
	.hero {
		border-bottom: var(--border);
		overflow: hidden;
	}

	.hero-inner {
		max-width: 1200px;
		margin: 0 auto;
		padding: 5rem 2rem 4rem;
		display: grid;
		grid-template-columns: 1fr 1fr;
		grid-template-rows: auto 1fr;
		gap: 0 4rem;
		align-items: end;
	}

	.hero-label {
		grid-column: 1 / -1;
		margin-bottom: 1.5rem;
	}

	.tag {
		font-size: 12px;
		letter-spacing: 0.1em;
		background: var(--black);
		color: var(--yellow);
		padding: 4px 10px;
		display: inline-block;
	}

	.hero-title {
		font-family: var(--font-display);
		font-weight: 900;
		font-size: clamp(4rem, 10vw, 9rem);
		line-height: 0.95;
		letter-spacing: -0.02em;
	}

	.yellow-block {
		background: var(--yellow);
		padding: 0 0.15em;
		display: inline-block;
	}

	.hero-right {
		display: flex;
		flex-direction: column;
		justify-content: flex-end;
		padding-bottom: 0.5rem;
	}

	.hero-sub {
		font-size: 1.05rem;
		line-height: 1.7;
		color: #3a3832;
		margin-bottom: 2rem;
	}

	.hero-actions {
		display: flex;
		gap: 1rem;
		flex-wrap: wrap;
		align-items: center;
	}

	/* TICKER */
	.ticker-wrap {
		border-top: var(--border);
		background: var(--yellow);
		overflow: hidden;
		padding: 10px 0;
	}

	.ticker {
		display: flex;
		gap: 2rem;
		white-space: nowrap;
		animation: ticker 22s linear infinite;
		font-family: var(--font-display);
		font-weight: 700;
		font-size: 12px;
		letter-spacing: 0.15em;
	}

	.dot {
		color: var(--black);
		opacity: 0.4;
	}

	@keyframes ticker {
		from { transform: translateX(0); }
		to { transform: translateX(-33.333%); }
	}

	/* STATS */
	.stats-bar {
		display: grid;
		grid-template-columns: repeat(4, 1fr);
		border-bottom: var(--border);
	}

	.stat {
		padding: 2.5rem 2rem;
		border-right: var(--border);
		display: flex;
		flex-direction: column;
		gap: 6px;
	}

	.stat:last-child {
		border-right: none;
	}

	.stat-value {
		font-family: var(--font-display);
		font-weight: 900;
		font-size: 3rem;
		line-height: 1;
	}

	.stat-label {
		font-size: 12px;
		color: var(--gray-muted);
		letter-spacing: 0.05em;
	}

	/* SERVICES */
	.services-section {
		border-bottom: var(--border);
	}

	.section-inner {
		max-width: 1200px;
		margin: 0 auto;
		padding: 5rem 2rem;
	}

	.section-header {
		display: flex;
		align-items: baseline;
		gap: 2rem;
		margin-bottom: 3rem;
		border-bottom: var(--border);
		padding-bottom: 1.5rem;
	}

	.section-tag {
		font-size: 12px;
		color: var(--gray-muted);
		letter-spacing: 0.08em;
	}

	.section-title {
		font-family: var(--font-display);
		font-weight: 900;
		font-size: clamp(2rem, 5vw, 3.5rem);
		line-height: 1;
		letter-spacing: -0.02em;
	}

	.services-grid {
		display: grid;
		grid-template-columns: repeat(3, 1fr);
		gap: 0;
		border: var(--border);
	}

	.service-card {
		padding: 2.5rem 2rem;
		border-right: var(--border);
		transition: background 0.2s;
	}

	.service-card:last-child {
		border-right: none;
	}

	.service-card:hover {
		background: var(--yellow);
	}

	.service-num {
		display: block;
		font-size: 11px;
		color: var(--gray-muted);
		margin-bottom: 1rem;
		letter-spacing: 0.1em;
	}

	.service-title {
		font-family: var(--font-display);
		font-weight: 700;
		font-size: 1.4rem;
		margin-bottom: 1rem;
		letter-spacing: -0.01em;
	}

	.service-desc {
		font-size: 0.95rem;
		color: #3a3832;
		line-height: 1.65;
	}

	.more-link {
		display: inline-block;
		margin-top: 2rem;
		font-family: var(--font-mono);
		font-size: 13px;
		border-bottom: 2px solid var(--black);
		padding-bottom: 2px;
		transition: color 0.15s, border-color 0.15s;
	}

	.more-link:hover {
		color: var(--yellow-dark);
		border-color: var(--yellow-dark);
	}

	/* MANIFESTO */
	.manifesto {
		background: var(--black);
		color: var(--white);
		border-bottom: var(--border);
	}

	.manifesto-inner {
		max-width: 1200px;
		margin: 0 auto;
		padding: 5rem 2rem;
		display: grid;
		grid-template-columns: 1fr auto;
		gap: 4rem;
		align-items: center;
	}

	blockquote {
		font-family: var(--font-body);
		font-style: italic;
		font-size: clamp(1.2rem, 2.5vw, 1.75rem);
		line-height: 1.5;
		color: var(--white);
		border-left: 4px solid var(--yellow);
		padding-left: 2rem;
	}

	/* CONTACT TEASER */
	.contact-teaser {
		border-bottom: var(--border);
	}

	.contact-teaser-grid {
		display: grid;
		grid-template-columns: 1fr 1fr;
		gap: 4rem;
		align-items: center;
	}

	.contact-teaser-right {
		display: flex;
		flex-direction: column;
		gap: 2rem;
	}

	.contact-teaser-right p {
		font-size: 1.05rem;
		color: #3a3832;
		line-height: 1.7;
	}

	/* BUTTONS */
	.btn-primary {
		display: inline-block;
		background: var(--black);
		color: var(--white);
		font-family: var(--font-mono);
		font-size: 13px;
		font-weight: 500;
		padding: 14px 28px;
		border: 2px solid var(--black);
		transition: background 0.15s, color 0.15s;
		letter-spacing: 0.05em;
	}

	.btn-primary:hover {
		background: var(--yellow);
		color: var(--black);
	}

	.btn-ghost {
		font-family: var(--font-mono);
		font-size: 13px;
		color: var(--gray-muted);
		transition: color 0.15s;
		letter-spacing: 0.05em;
	}

	.btn-ghost:hover {
		color: var(--black);
	}

	.btn-yellow {
		display: inline-block;
		background: var(--yellow);
		color: var(--black);
		font-family: var(--font-mono);
		font-size: 13px;
		font-weight: 500;
		padding: 14px 28px;
		border: 2px solid var(--yellow);
		transition: background 0.15s, color 0.15s, border-color 0.15s;
		white-space: nowrap;
	}

	.btn-yellow:hover {
		background: transparent;
		color: var(--white);
		border-color: var(--white);
	}

	.mono {
		font-family: var(--font-mono);
	}

	@media (max-width: 900px) {
		.hero-inner {
			grid-template-columns: 1fr;
		}

		.stats-bar {
			grid-template-columns: repeat(2, 1fr);
		}

		.stat:nth-child(2) {
			border-right: none;
		}

		.stat:nth-child(3) {
			border-top: var(--border);
		}

		.stat:nth-child(4) {
			border-top: var(--border);
			border-right: none;
		}

		.services-grid {
			grid-template-columns: 1fr;
		}

		.service-card {
			border-right: none;
			border-bottom: var(--border);
		}

		.service-card:last-child {
			border-bottom: none;
		}

		.manifesto-inner {
			grid-template-columns: 1fr;
		}

		.contact-teaser-grid {
			grid-template-columns: 1fr;
		}
	}
</style>
