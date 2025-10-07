<script lang="ts">
	import Menubar from '$lib/components/custom/menubar.svelte';
	import '../app.css';

	let { children } = $props();
</script>

<div class="flex min-h-screen flex-col">
	<Menubar />
	<main class="container mx-auto flex max-w-5xl flex-1 flex-col px-4">
		{@render children?.()}
	</main>
</div>
