<script lang="ts">
	import { buttonVariants } from '$lib/components/ui/button';
</script>

<!-- eslint-disable svelte/no-navigation-without-resolve  -->
<div class="flex flex-grow flex-col items-center justify-center gap-4">
	<article class="space-y-2">
		<h1 class="text-center text-3xl font-bold tracking-tighter sm:text-4xl md:text-5xl lg:text-6xl">
			Hi there!
		</h1>
		<p class="mx-auto max-w-[700px] text-center text-gray-500 md:text-xl dark:text-gray-400">
			I am Florian, a developer based in Germany.
		</p>
	</article>
	<div class="space-x-4">
		<a href="/about" class={buttonVariants({ variant: 'outline' })}> More about me </a>
	</div>
</div>
