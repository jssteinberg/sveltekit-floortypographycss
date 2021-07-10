<script>
	import { page } from '$app/stores';
	import '../app.postcss';

	const menu = [
		{ href: '/', label: 'Intro', subtitle: 'Sveltekit & Floor Typography CSS' },
		{ href: '/setup', label: 'Setup' },
		{ href: '/theme', label: 'Example' },
		{ href: '/more', label: 'More' },
	]
		.map((item, index) => {
			// Add index to menu items
			return { ...item, index };
		});
	$: current = menu.filter((x) => {
		return x.href === $page.path;
	})[0];
</script>

<header>
	<p class="site-title text-h1">
		<em>
		<a href="/">
		Sveltekit & Floor Typography CSS
		</a>
		</em>
	</p>

	<nav>
		{#each menu as item}
			<a href="{item.href}">{item.label}</a>
		{/each}
	</nav>
</header>

<main class="prose">
	<h1>
		{#if current && current.label}
			{current.label}{#if current.subtitle}:<br aria-hidden="true"><em class="subtitle">{current.subtitle}</em>{/if}
		{:else}
			…
		{/if}
	</h1>

	<slot></slot>

	{#if menu[current.index + 1]}
		<p>
		<a class="button" href="{menu[current.index + 1].href}">Next: {menu[current.index + 1].label} &rarr;</a>
		</p>
	{/if}
	
	<footer>
		<h2 class="text-h4"><em>Resources</em></h2>
		<ul>
		<li>
		<a href="https://github.com/svelte-add/postcss">svelte-add/postcss at Github</a>
		</li>
		<li>
		<a href="https://floortypography.vercel.app">Floor typography CSS</a>
		</li>
		<li>
		<a href="https://github.com/postcss/postcss-import">postcss-import at Github</a>
		</li>
		<li>
		<a href="https://kit.svelte.dev/docs">Sveltekit docs</a>
		</li>
		</ul>
	</footer>
</main>

<style>
	header {
		border-top: var(--border-width, .125rem) solid;
	}

	.site-title {
		margin: calc(.5 * var(--space, 1rem)) 0;
	}

	.site-title a {
		text-decoration: none;
		color: inherit;
	}

	nav {
		display: flex;
		flex-wrap: wrap;
		gap: 1rem;
	}

	footer {
		margin: calc(2 * var(--space, 1rem)) 0;
		padding: calc(1 * var(--space, 1rem)) 0;
		border-top: var(--border-width, 1px) solid var(--border-color, currentColor);
	}
</style>
