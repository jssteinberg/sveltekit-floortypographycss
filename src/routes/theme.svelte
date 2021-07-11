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

	<li><code>pre</code> gets a simple background and internal overflow.</li>

	<li>All relevant elements gets an inline-start margin/padding that lines up between them.
</ol>

<ul>
	<li>
	<code>body</code> gets a simple style for page layout and width (this must most likely be changed when a site gets more realized).
	</li>
</ul>
