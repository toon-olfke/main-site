<script lang="ts">
	const team = [
		{
			initials: 'MDM',
			name: 'Mike De Mullier',
			role: 'Senior Consultant',
			bio: 'Twintig jaar IT. Heeft genoeg verkeerd zien gaan om te weten wat werkt, en genoeg goede oplossingen gezien om niet te overdrijven.',
			tags: ['Consultancy', 'Microsoft 365', 'Infrastructuur', 'Support']
		},
		{
			initials: 'TDW',
			name: 'Toon De Witte',
			role: 'Infrastructuur & Netwerken',
			bio: 'Houdt netwerken draaiende die niemand opmerkt tot ze dat niet meer doen. Gespecialiseerd in infrastructuur, firewalls en de stille tevredenheid van een schone config.',
			tags: ['pfSense', 'Linux', 'Docker', 'Proxmox', 'Caddy']
		},
	];

	const values = [
		{
			title: 'Eerlijk zijn',
			body: 'Als we iets niet weten, zeggen we dat. Als iets niet gaat lukken, zeggen we dat ook. Dat spaart iedereen tijd.'
		},
		{
			title: 'Uitleggen wat we doen',
			body: 'U hoeft geen 25 jaar IT-ervaring te hebben om te begrijpen wat er met uw systemen gebeurt. Wij vertalen.'
		},
		{
			title: 'Geen verkooppraatjes',
			body: 'We adviseren wat het best past voor uw situatie, niet wat het meest oplevert voor ons. Soms is het antwoord gewoon "dat heeft u niet nodig".'
		},
		{
			title: 'Klein en bereikbaar',
			body: 'U belt ons, wij nemen op. Geen ticketsysteem met 48u responstijd. Wij zijn twee mensen — u weet wie u aan de lijn heeft.'
		}
	];
</script>

<svelte:head>
	<title>Over ons — Kernloos</title>
</svelte:head>

<section class="page-hero">
	<div class="inner">
		<span class="mono tag-small">// over kernloos</span>
		<h1>Klein.<br />Eerlijk.<br />Genoeg.</h1>
	</div>
</section>

<section class="intro-section">
	<div class="inner intro-grid">
		<div class="intro-text">
			<p class="large">Kernloos is opgericht door twee IT-mensen uit Gent die genoeg hadden van hoe IT-bedrijven er vaak bij lopen: grote beloftes, trage reacties, facturen die niemand begrijpt.</p>
			<p>We zijn geen groot consultancybedrijf. We zijn geen managed service provider met een dashboard vol leuke kleurtjes. We zijn twee mensen die goed zijn in wat ze doen en daar eerlijk over zijn.</p>
			<p>De naam "Kernloos" is bewust gekozen. Geen kern van managers, geen hiërarchie, geen onzin. Gewoon werk dat gedaan wordt.</p>
		</div>
		<div class="sidebar-note">
			<div class="note-block">
				<span class="mono note-label">Opgericht</span>
				<span class="note-value">2025</span>
			</div>
			<div class="note-block">
				<span class="mono note-label">Gevestigd</span>
				<span class="note-value">Gent</span>
			</div>
			<div class="note-block">
				<span class="mono note-label">Team</span>
				<span class="note-value">2 mensen</span>
			</div>
			<div class="note-block">
				<span class="mono note-label">Foosballtafel</span>
				<span class="note-value">Nee</span>
			</div>
		</div>
	</div>
</section>

<section class="team-section">
	<div class="inner">
		<div class="section-header">
			<span class="mono section-tag">// het team</span>
			<h2 class="section-title">Wij zijn dit.</h2>
		</div>

		<div class="team-grid">
			{#each team as person}
				<div class="person-card">
					<div class="person-avatar">{person.initials}</div>
					<div class="person-info">
						<h3 class="person-name">{person.name}</h3>
						<span class="mono person-role">{person.role}</span>
						<p class="person-bio">{person.bio}</p>
						<div class="tags">
							{#each person.tags as tag}
								<span class="tag-chip mono">{tag}</span>
							{/each}
						</div>
					</div>
				</div>
			{/each}
		</div>
	</div>
</section>

<section class="values-section">
	<div class="inner">
		<div class="section-header">
			<span class="mono section-tag">// hoe we werken</span>
			<h2 class="section-title">Onze aanpak.</h2>
		</div>

		<div class="values-grid">
			{#each values as v, i}
				<div class="value-item">
					<span class="mono value-num">0{i + 1}</span>
					<h3>{v.title}</h3>
					<p>{v.body}</p>
				</div>
			{/each}
		</div>
	</div>
</section>

<section class="cta-strip">
	<div class="inner cta-inner">
		<p class="cta-text">Benieuwd of we iets voor u kunnen betekenen?</p>
		<a href="/contact" class="btn-primary">Neem contact op</a>
	</div>
</section>

<style>
	.page-hero {
		border-bottom: var(--border);
		padding: 5rem 0 4rem;
	}

	.inner {
		max-width: 1200px;
		margin: 0 auto;
		padding: 0 2rem;
	}

	.tag-small {
		font-size: 12px;
		color: var(--gray-muted);
		letter-spacing: 0.1em;
		display: block;
		margin-bottom: 1.5rem;
	}

	.page-hero h1 {
		font-family: var(--font-display);
		font-weight: 900;
		font-size: clamp(3.5rem, 9vw, 8rem);
		line-height: 0.95;
		letter-spacing: -0.02em;
	}

	.intro-section {
		border-bottom: var(--border);
		padding: 5rem 0;
	}

	.intro-grid {
		display: grid;
		grid-template-columns: 1fr 280px;
		gap: 5rem;
		align-items: start;
	}

	.intro-text {
		display: flex;
		flex-direction: column;
		gap: 1.25rem;
	}

	.large {
		font-size: 1.2rem;
		line-height: 1.65;
		color: var(--black);
	}

	.intro-text p {
		font-size: 1rem;
		color: #3a3832;
		line-height: 1.75;
	}

	.sidebar-note {
		border: var(--border);
		padding: 1.5rem;
		display: flex;
		flex-direction: column;
		gap: 0;
	}

	.note-block {
		display: flex;
		justify-content: space-between;
		align-items: baseline;
		padding: 0.75rem 0;
		border-bottom: 1px solid var(--gray-light);
	}

	.note-block:last-child {
		border-bottom: none;
	}

	.note-label {
		font-size: 11px;
		color: var(--gray-muted);
		letter-spacing: 0.08em;
	}

	.note-value {
		font-family: var(--font-display);
		font-weight: 700;
		font-size: 1rem;
	}

	.team-section {
		border-bottom: var(--border);
		padding: 5rem 0;
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
		font-size: clamp(2rem, 4vw, 3rem);
		letter-spacing: -0.02em;
	}

	.team-grid {
		display: grid;
		grid-template-columns: 1fr 1fr;
		gap: 0;
		border: var(--border);
	}

	.person-card {
		padding: 2.5rem;
		border-right: var(--border);
		display: flex;
		gap: 1.5rem;
		align-items: start;
	}

	.person-card:last-child {
		border-right: none;
	}

	.person-avatar {
		width: 56px;
		height: 56px;
		background: var(--black);
		color: var(--yellow);
		font-family: var(--font-display);
		font-weight: 900;
		font-size: 16px;
		display: flex;
		align-items: center;
		justify-content: center;
		flex-shrink: 0;
		letter-spacing: 0.05em;
	}

	.person-info {
		display: flex;
		flex-direction: column;
		gap: 0.5rem;
	}

	.person-name {
		font-family: var(--font-display);
		font-weight: 700;
		font-size: 1.25rem;
		letter-spacing: -0.01em;
	}

	.person-role {
		font-size: 11px;
		color: var(--gray-muted);
		letter-spacing: 0.1em;
		display: block;
	}

	.person-bio {
		font-size: 0.9rem;
		color: #3a3832;
		line-height: 1.65;
		margin-top: 0.25rem;
	}

	.tags {
		display: flex;
		flex-wrap: wrap;
		gap: 6px;
		margin-top: 0.5rem;
	}

	.tag-chip {
		font-size: 10px;
		background: var(--gray-light);
		color: var(--gray-muted);
		padding: 3px 8px;
		letter-spacing: 0.08em;
	}

	.values-section {
		border-bottom: var(--border);
		padding: 5rem 0;
	}

	.values-grid {
		display: grid;
		grid-template-columns: 1fr 1fr;
		gap: 0;
		border: var(--border);
	}

	.value-item {
		padding: 2.5rem 2rem;
		border-right: var(--border);
		border-bottom: var(--border);
		display: flex;
		flex-direction: column;
		gap: 0.75rem;
	}

	.value-item:nth-child(2),
	.value-item:nth-child(4) {
		border-right: none;
	}

	.value-item:nth-child(3),
	.value-item:nth-child(4) {
		border-bottom: none;
	}

	.value-num {
		font-size: 11px;
		color: var(--gray-muted);
		letter-spacing: 0.15em;
	}

	.value-item h3 {
		font-family: var(--font-display);
		font-weight: 700;
		font-size: 1.1rem;
		letter-spacing: -0.01em;
	}

	.value-item p {
		font-size: 0.9rem;
		color: #3a3832;
		line-height: 1.65;
	}

	.cta-strip {
		padding: 4rem 0;
	}

	.cta-inner {
		display: flex;
		align-items: center;
		justify-content: space-between;
		gap: 2rem;
	}

	.cta-text {
		font-family: var(--font-display);
		font-weight: 700;
		font-size: 1.75rem;
		letter-spacing: -0.02em;
	}

	.btn-primary {
		display: inline-block;
		background: var(--black);
		color: var(--white);
		font-family: var(--font-mono);
		font-size: 13px;
		padding: 14px 28px;
		border: 2px solid var(--black);
		transition: background 0.15s, color 0.15s;
		white-space: nowrap;
		letter-spacing: 0.05em;
	}

	.btn-primary:hover {
		background: var(--yellow);
		color: var(--black);
	}

	.mono {
		font-family: var(--font-mono);
	}

	@media (max-width: 768px) {
		.intro-grid {
			grid-template-columns: 1fr;
		}

		.team-grid {
			grid-template-columns: 1fr;
		}

		.person-card {
			border-right: none;
			border-bottom: var(--border);
		}

		.values-grid {
			grid-template-columns: 1fr;
		}

		.value-item {
			border-right: none;
			border-bottom: var(--border);
		}

		.value-item:nth-child(4) {
			border-bottom: none;
		}

		.cta-inner {
			flex-direction: column;
			align-items: flex-start;
		}
	}
</style>
