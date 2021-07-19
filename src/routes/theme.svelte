<script context="module">
	import { dev } from '$app/env';
	export const hydrate = dev;
</script>

<p>
For a simple theme <a href="https://github.com/jssteinberg/sveltekit-floortypographycss/blob/main/src/app.postcss">see the stylesheet for this site at Github</a>. The styling in summary:
</p>

<ol>
	<li>
		<code>h1</code> is a bit bigger than <code>h2</code>, and bigger still in <code>main</code>.
		<ul>
			<li>The former using <code>--h1-added-lead</code>.</li>
			<li>The latter using <code>--h1-min-font-size</code>.</li>
		</ul>
	</li>

	<li>
		<code>font-family</code> gets system fonts so code blocks and body font has some general similarities (in size as well, which is a plus).
	</li>

	<li>
		<code>.prose</code> class where all relevant elements gets an inline-start margin/padding based on the same size of a root line-height, including:
		<ul>
			<li>
				<code>ol</code>, <code>ul</code>, and they are more universal
			</li>
			<li>
				<code>pre</code>, which also gets a simple background and internal overflow
			</li>
			<li>
				<code>blockquote</code>
			</li>
		</ul>
	</li>
</ol>

<ul>
	<li>
		<code>body</code> gets a simple style for page layout and width (this must most likely be changed when a site gets more realized).
	</li>
</ul>

<h2>Headings</h2>

<p class="text-h1">Heading One (h1)</p>

<p>
There should only be one <code>&lt;h1&gt;</code> per HTML document. This is good for SEO.
</p>

<p class="text-h2">Heading Two (h2)</p>

<p>A following paragraph to give a more realistic look.</p>

<p class="text-h3">Heading Three (h3)</p>

<p>A following paragraph to give a more realistic look.</p>

<p class="text-h4">Heading Four (h4)</p>

<p>A following paragraph to give a more realistic look.</p>

<p class="text-h5">Heading Five (h5)</p>

<p><code>&lt;h5&gt;</code> should rarely be used. Many say avoided actually.</p>

<p class="text-h6">Sixth Heading (h6)</p>

<p><code>&lt;h6&gt;</code> should very rarely be used. Perhaps "Never!" one should say.</p>

<h2><code>blockquote</code></h2>

<blockquote>
Family owned, operated & argued over
</blockquote>

<p>
—Sierra Nevada Brewing Co.
</p>

