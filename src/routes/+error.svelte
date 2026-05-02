<script lang="ts">
	import { page } from '$app/stores';
</script>

<svelte:head>
	<title>{$page.status} — Kernloos</title>
</svelte:head>

<section class="error">
	<div class="inner">
		<span class="mono code">{$page.status}</span>
		<h1>
			{#if $page.status === 404}
				Deze pagina bestaat niet.
			{:else}
				Er ging iets mis.
			{/if}
		</h1>
		<p>
			{#if $page.status === 404}
				Wat u zoekt is hier niet. Misschien nooit geweest. We weten het ook niet.
			{:else}
				{$page.error?.message ?? 'Onbekende fout. Zelfs wij zijn verbaasd.'}
			{/if}
		</p>
		<a href="/" class="btn">Terug naar huis</a>
	</div>
</section>

<style>
	.error {
		min-height: calc(100vh - 64px);
		display: flex;
		align-items: center;
		border-bottom: var(--border);
	}

	.inner {
		max-width: 1200px;
		margin: 0 auto;
		padding: 0 2rem;
		display: flex;
		flex-direction: column;
		gap: 1.5rem;
	}

	.code {
		font-family: var(--font-mono);
		font-size: 11px;
		color: var(--gray-muted);
		letter-spacing: 0.15em;
	}

	h1 {
		font-family: var(--font-display);
		font-weight: 900;
		font-size: clamp(3rem, 8vw, 7rem);
		line-height: 0.95;
		letter-spacing: -0.02em;
	}

	p {
		font-size: 1.1rem;
		color: #3a3832;
		max-width: 420px;
		line-height: 1.7;
	}

	.btn {
		display: inline-block;
		background: var(--black);
		color: var(--white);
		font-family: var(--font-mono);
		font-size: 13px;
		padding: 14px 28px;
		border: 2px solid var(--black);
		transition: background 0.15s, color 0.15s;
		width: fit-content;
	}

	.btn:hover {
		background: var(--yellow);
		color: var(--black);
	}

	.mono {
		font-family: var(--font-mono);
	}
</style>