<script context="module">
	import { dev } from '$app/env';
	export const hydrate = dev;
</script>

<ol>
<li>
<h2>Sveltekit</h2>

<p>
First, initiate a new <a href="https://kit.svelte.dev">Sveltekit</a> project.
</p>
</li>

<li>
<h2>svelte-add</h2>
<p>
Second, add Postcss and Floor typography CSS (the latter requires postcss-import):
</p>

<p><em>Reference <a href="https://github.com/svelte-add/postcss">github.com/svelte-add/postcss</a>.</em></p>

<pre><code>
npx svelte-add@latest postcss
npm i -D floor-typography-css postcss-import
</code></pre>

<p>Add what else you want from <a href="https://github.com/svelte-add/svelte-add">svelte-add</a>.</p>
</li>

<li>
<h2>src/app.postcss</h2>

<p>Third, setup Floor Typography CSS in src/app.postcss—your global (Postcss) stylesheet:</p>

<pre><code>
{`@import 'floor-typography-css/src/reset.css'; /* Core */
@import 'floor-typography-css/src/normalize-style.css'; /* Core */
@import 'floor-typography-css/src/vars.css'; /* Core */
@import 'floor-typography-css/src/headings-font.css';
@import 'floor-typography-css/src/headings-margin.css'; /* Or headings-margin-lg */

:root {
	--spacer: calc(1rem * (1 + var(--added-lead))); /* 1 root line-height---vertical rhythm. */
	--h1-added-lead: .15; /* Adjusts h1's line-height, thus its font-size */
}

main {
	--h1-min-font-size: 2em; /* Bigger h1. Var should be a natural number. */
}`}
</code></pre>

<p>
<strong><code>--spacer</code>.</strong>

A feature of Floor Typography CSS is to use the <code>--spacer</code> variable. It will adjust vertical spacing between elements—particullary noticeable on headings when the "headings-margin" file is imported. Here we are setting it to one 'root' line-height, or <em>leading</em> as it's called in typography.

</p>

<p>
<strong>
<code>--h1-added-lead</code>.
</strong>
Floor Typography CSS provides two ways to adjust headings' font sizes. The first is adjusting a heading's line-height by changing <code>--h[#]added-lead</code>.
</p>

<p>
<strong>
<code>--h1-min-font-size</code>.
</strong>
The second is adjusting a heading's minimum font-size by changing <code>--h[#]-min-font-size</code> to a natural number (N)—no decimals. <em>You can only adjust the minimum font-size because the true size is calculated from a heading's maximum font-size (root line-height * N) divided by its line-height (another reason to use Floor Typography CSS).</em>
</p>
</li>
</ol>

<!--
<aside>
<section>
<h3 class="h1">Illustration of all line-heights adding up to leading * N</h3>

<p>
Notice how the lines in paragraphs between the two columns line up.
</p>
<p>
Since <code>--spacer</code> equals root line-height and Floor Typography CSS calculates headings' font-size plus dynamic line-height to equal root line-height * N, lines will line up like this.
</p>
</section>

<section>
<h3 class="h1">Vertical rythm</h3>

<p>
This is text-book typography for vertical rythm.
</p>
</section>
</aside>
-->

<style>
	/* aside { */
	/* 	display: grid; */
	/* 	grid-template-columns: 1fr 1fr; */
	/* 	gap: var(--spacer, 1rem); */
	/* } */
</style>
