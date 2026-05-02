<script lang="ts">
	let name = '';
	let email = '';
	let message = '';
	let sent = false;
	let sending = false;

	async function handleSubmit() {
		if (!name || !email || !message) return;
		sending = true;
		// Simulate — replace with actual form endpoint (Formspree, SvelteKit action, etc.)
		await new Promise(r => setTimeout(r, 800));
		sending = false;
		sent = true;
	}
</script>

<svelte:head>
	<title>Contact — Kernloos</title>
</svelte:head>

<section class="page-hero">
	<div class="inner">
		<span class="mono tag-small">// contact</span>
		<h1>Vertel ons<br />wat er speelt.</h1>
	</div>
</section>

<section class="contact-section">
	<div class="inner contact-grid">

		<!-- Form -->
		<div class="form-col">
			{#if sent}
				<div class="success-block">
					<span class="success-icon">✓</span>
					<h2>Bericht ontvangen.</h2>
					<p>We lezen het, we denken erover na, en we sturen u een eerlijk antwoord. Dat duurt normaal niet lang.</p>
				</div>
			{:else}
				<form onsubmit={(e) => { e.preventDefault(); handleSubmit(); }}>
					<div class="field">
						<label class="mono" for="name">Naam</label>
						<input id="name" type="text" bind:value={name} placeholder="Jan Janssen" required />
					</div>

					<div class="field">
						<label class="mono" for="email">E-mailadres</label>
						<input id="email" type="email" bind:value={email} placeholder="jan@bedrijf.be" required />
					</div>

					<div class="field">
						<label class="mono" for="message">Bericht</label>
						<textarea id="message" bind:value={message} rows="6" placeholder="Leg uit wat er speelt. Hoe meer context, hoe beter wij kunnen inschatten of en hoe we kunnen helpen." required></textarea>
					</div>

					<button type="submit" class="btn-submit" disabled={sending}>
						{sending ? 'Bezig...' : 'Verstuur bericht'}
					</button>

					<p class="form-note mono">Geen nieuwsbrief. Geen CRM. Uw gegevens gaan nergens naartoe.</p>
				</form>
			{/if}
		</div>

		<!-- Info sidebar -->
		<div class="info-col">
			<div class="info-block">
				<span class="mono info-label">E-mail</span>
				<a href="mailto:hallo@kernloos.be" class="info-value">hallo@kernloos.be</a>
			</div>

			<div class="info-block">
				<span class="mono info-label">Gevestigd</span>
				<span class="info-value">Gent, België</span>
			</div>

			<div class="info-block">
				<span class="mono info-label">Reactietijd</span>
				<span class="info-value">Binnen de dag</span>
			</div>

			<div class="expectation-box">
				<h3>Wat u mag verwachten</h3>
				<ul>
					<li>Een eerlijk antwoord op uw vraag</li>
					<li>Geen verkoopgesprek als u dat niet wil</li>
					<li>Een inschatting of we u kunnen helpen</li>
					<li>En als dat niet zo is, zeggen we dat ook</li>
				</ul>
			</div>
		</div>
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
	}

	.contact-section {
		padding: 5rem 0;
	}

	.contact-grid {
		display: grid;
		grid-template-columns: 1fr 340px;
		gap: 5rem;
		align-items: start;
	}

	/* FORM */
	form {
		display: flex;
		flex-direction: column;
		gap: 1.75rem;
	}

	.field {
		display: flex;
		flex-direction: column;
		gap: 0.5rem;
	}

	label {
		font-size: 11px;
		letter-spacing: 0.1em;
		color: var(--gray-muted);
		text-transform: uppercase;
	}

	input, textarea {
		width: 100%;
		padding: 12px 14px;
		font-family: var(--font-body);
		font-size: 1rem;
		border: var(--border);
		background: var(--white);
		color: var(--black);
		outline: none;
		transition: border-color 0.15s, background 0.15s;
		resize: vertical;
	}

	input:focus, textarea:focus {
		border-color: var(--black);
		background: #fff;
	}

	input::placeholder, textarea::placeholder {
		color: var(--gray-mid);
	}

	.btn-submit {
		align-self: flex-start;
		background: var(--black);
		color: var(--white);
		font-family: var(--font-mono);
		font-size: 13px;
		font-weight: 500;
		padding: 14px 32px;
		border: 2px solid var(--black);
		cursor: pointer;
		letter-spacing: 0.08em;
		transition: background 0.15s, color 0.15s;
	}

	.btn-submit:hover:not(:disabled) {
		background: var(--yellow);
		color: var(--black);
	}

	.btn-submit:disabled {
		opacity: 0.6;
		cursor: not-allowed;
	}

	.form-note {
		font-size: 11px;
		color: var(--gray-muted);
		letter-spacing: 0.05em;
	}

	.success-block {
		display: flex;
		flex-direction: column;
		gap: 1rem;
		padding: 3rem;
		border: var(--border);
		background: var(--yellow);
	}

	.success-icon {
		font-size: 2rem;
	}

	.success-block h2 {
		font-family: var(--font-display);
		font-weight: 700;
		font-size: 2rem;
		letter-spacing: -0.02em;
	}

	.success-block p {
		font-size: 1rem;
		line-height: 1.65;
	}

	/* INFO SIDEBAR */
	.info-col {
		display: flex;
		flex-direction: column;
		gap: 0;
		border: var(--border);
	}

	.info-block {
		display: flex;
		flex-direction: column;
		gap: 4px;
		padding: 1.25rem 1.5rem;
		border-bottom: var(--border);
	}

	.info-label {
		font-size: 10px;
		color: var(--gray-muted);
		letter-spacing: 0.12em;
		text-transform: uppercase;
	}

	.info-value {
		font-family: var(--font-display);
		font-weight: 700;
		font-size: 1.1rem;
		letter-spacing: -0.01em;
		transition: color 0.15s;
	}

	a.info-value:hover {
		color: var(--yellow-dark);
	}

	.expectation-box {
		padding: 1.5rem;
	}

	.expectation-box h3 {
		font-family: var(--font-display);
		font-weight: 700;
		font-size: 0.95rem;
		letter-spacing: -0.01em;
		margin-bottom: 1rem;
	}

	.expectation-box ul {
		list-style: none;
		display: flex;
		flex-direction: column;
		gap: 0.6rem;
	}

	.expectation-box li {
		font-family: var(--font-mono);
		font-size: 12px;
		color: #3a3832;
		padding-left: 1rem;
		position: relative;
	}

	.expectation-box li::before {
		content: '▸';
		position: absolute;
		left: 0;
		color: var(--yellow-dark);
	}

	.mono {
		font-family: var(--font-mono);
	}

	@media (max-width: 900px) {
		.contact-grid {
			grid-template-columns: 1fr;
		}
	}
</style>
