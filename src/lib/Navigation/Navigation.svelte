<script lang="ts">
// @ts-nocheck

	import { onMount } from 'svelte';
    
	// @ts-ignore
	let data ;
	let expandedKey = "";
	onMount(async () => {
	  const response = await fetch('./src/devops.json');
	  data = await response.json();
	  console.log(data)
	});

	function toggleExpansion(key) {
		console.log(key)
  expandedKey = expandedKey === key ? null : key;
}

</script>

<nav class="list-nav">
	<ul>
		{#if data}
			{#each Object.keys(data) as key}
				<li>
					<a href="" on:click={() => toggleExpansion(key)} on:keydown on:keyup on:keypress>{key}</a>
					{#if expandedKey === key}
						<ul>
							{#each Object.data(key) as child}
								<li>{child}</li>
							{/each}
						</ul>
					{/if}
				</li>
			{/each}	
		{/if}
	</ul>
<!-- 	<ul>
		<li><a href="/">Homepage</a></li>
		<li><a href="/about">About</a></li>
		<li><a href="/blog">Blog</a></li>
		<li><a href="/contact">Contact</a></li>
	</ul> -->
</nav>