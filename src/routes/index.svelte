<script>
	import Prism from 'prismjs';
	// console.log(Prism);
	// import 'prism-svelte';

	const source = `
<script>
  let count = 0;
<\/script>

<button on:click={ () => count++ }>Hello</button>

<h1>{ count }</h1>

<ul>
  {#each Array(10).map((_, i) => i) as }
    <li on:click={() => count = i}>Set count to {i}</li>
  {/each}
</ul>
`;

	const highlighted = Prism.highlight(source, Prism.languages.svelte, 'svelte');
</script>

<h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>

<pre>
{@html highlighted}
</pre>
