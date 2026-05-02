<script lang="ts">
	import '../app.css';
	import { page } from '$app/stores';

	let menuOpen = false;

	const nav = [
		{ href: '/', label: 'Home' },
		{ href: '/diensten', label: 'Diensten' },
		{ href: '/over', label: 'Over ons' },
		{ href: '/contact', label: 'Contact' }
	];
</script>

<header>
	<div class="header-inner">
		<a href="/" class="logo">
			<span class="logo-mark">K</span>
			<span class="logo-text">KERNLOOS</span>
		</a>

		<nav class="desktop-nav">
			{#each nav as item}
				<a href={item.href} class:active={$page.url.pathname === item.href}>{item.label}</a>
			{/each}
			<a href="/contact" class="cta-btn">Neem contact op</a>
		</nav>

		<button class="menu-toggle" onclick={() => menuOpen = !menuOpen} aria-label="Menu">
			<span class="bar" class:open={menuOpen}></span>
			<span class="bar" class:open={menuOpen}></span>
		</button>
	</div>

	{#if menuOpen}
		<div class="mobile-menu">
			{#each nav as item}
				<a href={item.href} onclick={() => menuOpen = false}>{item.label}</a>
			{/each}
		</div>
	{/if}
</header>

<main>
	<slot />
</main>

<footer>
	<div class="footer-inner">
		<div class="footer-brand">
			<span class="logo-mark small">K</span>
			<div>
				<p class="brand-name">KERNLOOS</p>
				<p class="brand-tagline">IT zonder fratsen.</p>
			</div>
		</div>
		<div class="footer-links">
			{#each nav as item}
				<a href={item.href}>{item.label}</a>
			{/each}
		</div>
		<div class="footer-meta">
			<p class="mono">© {new Date().getFullYear()} Kernloos BV</p>
			<p class="mono muted">Gent, België</p>
		</div>
	</div>
</footer>

<style>
	header {
		position: sticky;
		top: 0;
		z-index: 100;
		background: var(--white);
		border-bottom: var(--border);
	}

	.header-inner {
		max-width: 1200px;
		margin: 0 auto;
		padding: 0 2rem;
		height: 64px;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}

	.logo {
		display: flex;
		align-items: center;
		gap: 10px;
	}

	.logo-mark {
		width: 36px;
		height: 36px;
		background: var(--black);
		color: var(--yellow);
		font-family: var(--font-display);
		font-weight: 900;
		font-size: 18px;
		display: flex;
		align-items: center;
		justify-content: center;
		flex-shrink: 0;
	}

	.logo-mark.small {
		width: 28px;
		height: 28px;
		font-size: 14px;
	}

	.logo-text {
		font-family: var(--font-display);
		font-weight: 700;
		font-size: 13px;
		letter-spacing: 0.15em;
	}

	.desktop-nav {
		display: flex;
		align-items: center;
		gap: 2rem;
	}

	.desktop-nav a {
		font-family: var(--font-mono);
		font-size: 13px;
		letter-spacing: 0.05em;
		position: relative;
		padding-bottom: 2px;
		transition: color 0.15s;
	}

	.desktop-nav a::after {
		content: '';
		position: absolute;
		bottom: -2px;
		left: 0;
		width: 0;
		height: 2px;
		background: var(--yellow);
		transition: width 0.2s;
	}

	.desktop-nav a:hover::after,
	.desktop-nav a.active::after {
		width: 100%;
	}

	.cta-btn {
		background: var(--yellow) !important;
		color: var(--black) !important;
		padding: 8px 16px !important;
		font-family: var(--font-mono) !important;
		font-size: 12px !important;
		font-weight: 500 !important;
		border: 2px solid var(--black) !important;
		transition: background 0.15s !important;
	}

	.cta-btn::after {
		display: none !important;
	}

	.cta-btn:hover {
		background: var(--black) !important;
		color: var(--yellow) !important;
	}

	.menu-toggle {
		display: none;
		flex-direction: column;
		gap: 5px;
		background: none;
		border: none;
		cursor: pointer;
		padding: 4px;
	}

	.bar {
		display: block;
		width: 24px;
		height: 2px;
		background: var(--black);
		transition: transform 0.2s, opacity 0.2s;
	}

	.bar.open:first-child {
		transform: translateY(7px) rotate(45deg);
	}

	.bar.open:last-child {
		transform: translateY(-0px) rotate(-45deg);
	}

	.mobile-menu {
		border-top: var(--border);
		display: flex;
		flex-direction: column;
	}

	.mobile-menu a {
		padding: 1rem 2rem;
		font-family: var(--font-mono);
		font-size: 14px;
		border-bottom: 1px solid var(--gray-light);
		transition: background 0.1s;
	}

	.mobile-menu a:hover {
		background: var(--yellow);
	}

	footer {
		border-top: var(--border);
		background: var(--black);
		color: var(--white);
	}

	.footer-inner {
		max-width: 1200px;
		margin: 0 auto;
		padding: 3rem 2rem;
		display: grid;
		grid-template-columns: 1fr 1fr 1fr;
		gap: 2rem;
		align-items: start;
	}

	.footer-brand {
		display: flex;
		align-items: center;
		gap: 12px;
	}

	.brand-name {
		font-family: var(--font-display);
		font-weight: 700;
		font-size: 12px;
		letter-spacing: 0.15em;
	}

	.brand-tagline {
		font-family: var(--font-mono);
		font-size: 12px;
		color: var(--gray-mid);
		margin-top: 2px;
	}

	.footer-links {
		display: flex;
		flex-direction: column;
		gap: 0.5rem;
	}

	.footer-links a {
		font-family: var(--font-mono);
		font-size: 13px;
		color: var(--gray-mid);
		transition: color 0.15s;
	}

	.footer-links a:hover {
		color: var(--yellow);
	}

	.footer-meta {
		display: flex;
		flex-direction: column;
		gap: 4px;
	}

	.mono {
		font-family: var(--font-mono);
		font-size: 12px;
	}

	.muted {
		color: var(--gray-mid);
	}

	@media (max-width: 768px) {
		.desktop-nav {
			display: none;
		}

		.menu-toggle {
			display: flex;
		}

		.footer-inner {
			grid-template-columns: 1fr;
		}
	}
</style>
