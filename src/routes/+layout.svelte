<script lang="ts">
	import '../app.css';
	import favicon from '$lib/assets/favicon.svg';
	import Menubar from '$lib/components/custom/menubar.svelte';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<div class="flex min-h-screen flex-col">
	<Menubar />
	<main class="container mx-auto flex max-w-5xl flex-1 flex-col px-4">
		{@render children?.()}
	</main>
</div>
