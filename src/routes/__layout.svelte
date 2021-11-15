<script>
	import { page } from "$app/stores";
	import "../app.postcss";

	const title = "Sveltekit & Floor Typography CSS";
	const description =
		"A guide to setup Sveltekit and Floor Typography CSS—a postcss library which makes custom text-book typographic CSS easy, and it has updated normalization across browsers.";

	const menu = [
		{ href: "/", label: "Intro", subtitle: title },
		{ href: "/setup", label: "Setup" },
		{ href: "/theme", label: "Theme" },
		{ href: "/more", label: "More" },
	].map((item, index) => {
		// Add index to menu items
		return { ...item, index };
	});

	$: current = menu.filter((x) => {
		return x.href === $page.path;
	})[0];
</script>

<svelte:head>
	{#if typeof title === "string"}
		<title>{title}</title>
		<meta itemprop="name" content={title} />
		<meta property="twitter:title" content={title} />
		<meta property="og:title" content={title} />
	{/if}

	{#if typeof description === "string"}
		<meta name="description" content={description} />
		<meta itemprop="description" content={description} />
		<meta property="twitter:description" content={description} />
		<meta property="og:description" content={description} />
	{/if}
</svelte:head>

<header>
	<p class="site-title h2">
		<a sveltekit:prefetch href="/">{title}</a>
	</p>

	<nav>
		{#each menu as item}
			<a sveltekit:prefetch href={item.href}>{item.label}</a>
		{/each}
	</nav>
</header>

<main class="prose">
	<h1>
		{#if current && current.label}
			{current.label}{#if current.subtitle}:<br aria-hidden="true" /><em class="subtitle">{current.subtitle}</em>{/if}
		{:else}
			…
		{/if}
	</h1>

	<slot />

	{#if current && menu[current.index + 1]}
		<p>
			<a sveltekit:prefetch class="button" href={menu[current.index + 1].href}>
				Next: {menu[current.index + 1].label} &rarr;
			</a>
		</p>
	{/if}
</main>

<style>
	h1 em,
	.site-title {
		font-style: normal;
		font-weight: normal;
	}

	header * {
		margin: 0;
	}

	header a {
		display: inline-block;
		padding: calc(0.25 * var(--spacer, 1rem)) 0;
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
