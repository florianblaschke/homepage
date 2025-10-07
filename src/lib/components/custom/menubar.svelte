<script lang="ts">
	import { cn } from '$lib/utils';
	import { page } from '$app/state';

	const paths: { href: string; title: string }[] = [
		{
			href: '/about',
			title: 'About'
		}
	];

	let pathname = $derived(page.route.id);
</script>

<!-- eslint-disable svelte/no-navigation-without-resolve  -->
<header class="sticky top-0 z-10 flex h-14 items-center justify-between bg-white px-4 lg:px-6">
	<a class="flex items-center justify-center" href="/">
		<span class="hidden text-lg font-bold md:block"> Florian Blaschke </span>
		<span class="text-lg font-bold md:hidden">FB</span>
	</a>
	<nav class="flex gap-4 sm:gap-6 md:ml-auto">
		{#each paths as { href, title } (href)}
			<a {href} class={cn('text-sm font-medium hover:underline', pathname === href && 'underline')}>
				{title}
			</a>
		{/each}
	</nav>
</header>
