<script>
	import { page } from '$app/stores';
	import '../app.postcss';

	const menu = [
		{ href: '/', label: 'Intro', subtitle: 'Sveltekit & Floor Typography CSS' },
		{ href: '/setup', label: 'Setup' },
		{ href: '/theme', label: 'Theme' },
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

	{#if current && menu[current.index + 1]}
		<p>
		<a class="button" href="{menu[current.index + 1].href}">Next: {menu[current.index + 1].label} &rarr;</a>
		</p>
	{/if}
</main>

<style>
	header * {
		margin: 0;
	}

	header a {
		display: inline-block;
		padding: calc(.25 * var(--space, 1rem)) 0;
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
</style>
