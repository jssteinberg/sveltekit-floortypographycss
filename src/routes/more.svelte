<h2>Deploy</h2>
<p>To deploy, install the relevant <a href="https://kit.svelte.dev/docs#adapters">adapter</a>.</p>

<h2>No/less JS</h2>

<p>
For no/less Javascript on page level, export router and/or hydrate as false (but <code>true</code> when <code>dev</code> since it disables HRM). See <a href="SSR and Javascript in Sveltekit docs">SSR and Javascript in Sveltekit docs</a>.
</p>

<pre><code>
{`<script context="module">
	import { dev } from '$app/env';
	export const hydrate = dev;
	export const router = dev;
</script>`}
</code></pre>
