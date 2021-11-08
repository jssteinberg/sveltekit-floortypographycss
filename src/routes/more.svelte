<script context="module">
	import { dev } from '$app/env';
	export const hydrate = dev;
</script>

<script>
	const code = '<script context="module">\n\timport { dev } from \'$app/env\';\n\texport const hydrate = dev;\n\texport const router = dev;\n<\/script>';
</script>

<h2>Deploy</h2>
<p>To deploy, install the relevant <a href="https://kit.svelte.dev/docs#adapters">adapter</a>.</p>

<h2>Prefetch routes on hover/touch</h2>

<p>
	Even thought not stated in <a href="https://kit.svelte.dev/docs#anchor-options-sveltekit-prefetch">the docs</a> (at the time of writing this), <code>sveltekit:prefetch</code> will prefetch a route when the user hovers or touches a link even though there is no <code>load</code> function.
</p>

<h2>No/less JS</h2>

<p>
For no/less Javascript on page level, export router and/or hydrate as false (but <code>true</code> when <code>dev</code> since it disables HRM). See <a href="https://kit.svelte.dev/docs#ssr-and-javascript">SSR and Javascript in Sveltekit docs</a>.
</p>

<pre><code>{code}</code></pre>
