<script lang="ts">
	const diensten = [
		{
			number: '01',
			title: 'Netwerkinfrastructuur',
			tag: 'Hardware & Configuratie',
			body: 'Firewalls, switches, access points, VLANs, VPNs. We ontwerpen, installeren en onderhouden netwerken die gewoon werken. Ook als uw vorige leverancier dat niet deed.',
			items: ['pfSense / OPNsense', 'UniFi / managed switches', 'VPN (WireGuard, OpenVPN)', 'VLAN-segmentatie', 'Wifi-optimalisatie']
		},
		{
			number: '02',
			title: 'Serverinfrastructuur',
			tag: 'On-prem & Hybrid',
			body: 'Debian, Proxmox, Docker, backups die ook echt werken. We zetten op, we documenteren, we verdwijnen niet na de installatie.',
			items: ['Linux servers (Debian/Ubuntu)', 'Proxmox virtualisatie', 'Docker & containerisatie', 'Backup & disaster recovery', 'Monitoring (Grafana, Prometheus)']
		},
		{
			number: '03',
			title: 'IT-consultancy',
			tag: 'Advies & Audit',
			body: 'We kijken naar uw huidige setup met frisse ogen en zeggen u eerlijk wat er beter kan. Zonder u te proberen overtuigen van dingen die u niet nodig heeft.',
			items: ['Infrastructuuraudit', 'Migratieadvies', 'Security review', 'Vendor-onafhankelijk advies', 'Technische documentatie']
		},
		{
			number: '04',
			title: 'Ondersteuning & Beheer',
			tag: 'Ongoing Support',
			body: 'Ad hoc of op afspraak. We zijn bereikbaar, we reageren snel, en we leggen uit wat we doen in begrijpelijke taal.',
			items: ['Proactief onderhoud', 'Probleemanalyse', 'Remote support', 'Documentatie & overdracht', 'Geen onzinnige SLA-contracten']
		}
	];
</script>

<svelte:head>
	<title>Diensten — Kernloos</title>
</svelte:head>

<section class="page-hero">
	<div class="inner">
		<span class="mono tag-small">// diensten</span>
		<h1>Wat we<br /><span class="underline-yellow">eigenlijk</span><br />doen.</h1>
		<p class="intro">Geen lijst van buzzwords. Concrete diensten, duidelijke grenzen, eerlijke prijzen.</p>
	</div>
</section>

<section class="diensten-list">
	<div class="inner">
		{#each diensten as d, i}
			<article class="dienst" class:alt={i % 2 === 1}>
				<div class="dienst-header">
					<span class="mono num">{d.number}</span>
					<span class="mono tag-item">{d.tag}</span>
				</div>
				<div class="dienst-body">
					<div class="dienst-left">
						<h2>{d.title}</h2>
						<p>{d.body}</p>
					</div>
					<ul class="dienst-items">
						{#each d.items as item}
							<li>
								<span class="bullet">▸</span>
								{item}
							</li>
						{/each}
					</ul>
				</div>
			</article>
		{/each}
	</div>
</section>

<section class="pricing-note">
	<div class="inner pricing-inner">
		<div>
			<h2>Hoeveel kost dit?</h2>
			<p>We werken op basis van dagtarieven of projectprijzen. Geen verrassingen achteraf, geen mysterieuze bijkomende kosten. Vraag een offerte aan en we zijn eerlijk.</p>
		</div>
		<a href="/contact" class="btn-primary">Vraag offerte aan</a>
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
		font-size: clamp(3rem, 8vw, 7rem);
		line-height: 0.95;
		letter-spacing: -0.02em;
		margin-bottom: 2rem;
	}

	.underline-yellow {
		text-decoration: underline;
		text-decoration-color: var(--yellow);
		text-decoration-thickness: 6px;
		text-underline-offset: 6px;
	}

	.intro {
		font-size: 1.15rem;
		color: #3a3832;
		max-width: 500px;
		line-height: 1.7;
	}

	.diensten-list {
		border-bottom: var(--border);
	}

	.diensten-list .inner {
		padding-top: 0;
		padding-bottom: 0;
	}

	.dienst {
		border-bottom: var(--border);
		padding: 4rem 0;
		transition: background 0.2s;
	}

	.dienst.alt {
		background: var(--gray-light);
		margin: 0 -2rem;
		padding: 4rem 2rem;
	}

	.dienst:last-child {
		border-bottom: none;
	}

	.dienst-header {
		display: flex;
		align-items: center;
		gap: 1.5rem;
		margin-bottom: 2.5rem;
	}

	.num {
		font-size: 11px;
		color: var(--gray-muted);
		letter-spacing: 0.15em;
	}

	.tag-item {
		font-size: 11px;
		background: var(--black);
		color: var(--yellow);
		padding: 3px 10px;
		letter-spacing: 0.1em;
	}

	.dienst-body {
		display: grid;
		grid-template-columns: 1fr 1fr;
		gap: 4rem;
		align-items: start;
	}

	.dienst-left h2 {
		font-family: var(--font-display);
		font-weight: 700;
		font-size: clamp(1.5rem, 3vw, 2.5rem);
		letter-spacing: -0.02em;
		margin-bottom: 1.25rem;
		line-height: 1.1;
	}

	.dienst-left p {
		font-size: 1rem;
		color: #3a3832;
		line-height: 1.7;
	}

	.dienst-items {
		list-style: none;
		display: flex;
		flex-direction: column;
		gap: 0.75rem;
		padding-top: 0.25rem;
	}

	.dienst-items li {
		font-family: var(--font-mono);
		font-size: 13px;
		display: flex;
		gap: 0.75rem;
		align-items: baseline;
		padding-bottom: 0.75rem;
		border-bottom: 1px solid var(--gray-mid);
	}

	.dienst-items li:last-child {
		border-bottom: none;
	}

	.bullet {
		color: var(--yellow-dark);
		flex-shrink: 0;
	}

	.pricing-note {
		padding: 5rem 0;
	}

	.pricing-inner {
		display: grid;
		grid-template-columns: 1fr auto;
		gap: 4rem;
		align-items: center;
	}

	.pricing-inner h2 {
		font-family: var(--font-display);
		font-weight: 700;
		font-size: 2rem;
		letter-spacing: -0.02em;
		margin-bottom: 1rem;
	}

	.pricing-inner p {
		font-size: 1rem;
		color: #3a3832;
		line-height: 1.7;
		max-width: 500px;
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
		.dienst-body {
			grid-template-columns: 1fr;
			gap: 2rem;
		}

		.pricing-inner {
			grid-template-columns: 1fr;
		}
	}
</style>
