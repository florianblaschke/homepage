<script lang="ts">
	import { Separator } from '$lib/components/ui/separator';
	import { formatDistanceToNow } from 'date-fns';

	const experience: {
		title: string;
		description?: string;
		company: string;
		timerange: string;
	}[] = [
		{
			title: 'Developer',
			description: '',
			company: 'for suxess',
			timerange: '01/2024–present'
		}
	];

	const knowledge: string[] = [
		'go',
		'rust',
		'typescript',
		'sql',
		'mongodb',
		'node',
		'aws',
		'google cloud',
		'docker'
	];

	const date = new Date(2024, 0, 1);
	const codingSince = formatDistanceToNow(date, { addSuffix: false });
</script>

<!-- eslint-disable svelte/no-navigation-without-resolve  -->
<section class="py-10">
	<div class="mb-12 space-y-2">
		<h1 class="text-3xl font-bold tracking-tighter sm:text-4xl md:text-5xl">About</h1>
	</div>

	<div class="grid gap-12 md:grid-cols-3">
		<div class="md:col-span-1">
			<div class="sticky top-20">
				<div class="mb-6 aspect-square overflow-hidden rounded-md">
					<enhanced:img src="/static/florian_blaschke.jpeg" alt="Profile" class="object-cover" />
				</div>

				<div class="space-y-4">
					<div class="text-xl font-bold">Connect</div>
					<div class="space-y-2">
						<a
							href="https://github.com/florianblaschke"
							class="flex items-center text-sm hover:underline"
							target="_blank"
							rel="noopener noreferrer"
						>
							GitHub
						</a>
						<a
							href="https://www.linkedin.com/in/florian-blaschke-b3718928a/"
							class="flex items-center text-sm hover:underline"
							target="_blank"
							rel="noopener noreferrer"
						>
							LinkedIn
						</a>
					</div>
				</div>
			</div>
		</div>

		<div class="space-y-12 md:col-span-2">
			<section class="space-y-4">
				<p class="text-muted-foreground">
					I’m a Developer from Germany with {codingSince} of experience. Currently I am working mostly
					with Go building a scalable infrastructure for job imports at
					<a href="https://forsuxess.de" class="underline" target="_blank" rel="noopener"
						>forsuxess.</a
					> In my spare time I try to dig a bit deeper into databases.
				</p>

				<p class="text-muted-foreground">
					I’ve started diving into the
					<a href="https://teachyourselfcs.com" class="underline" target="_blank" rel="noopener"
						>Teach yourself CS</a
					> path to strengthen my computer science foundation and I still like typing…
				</p>
			</section>

			<Separator />

			<section class="space-y-4">
				<h2 class="text-2xl font-bold">Things I know or used in no particular order</h2>
				<ul class="flex flex-wrap gap-2 space-y-1 text-sm text-muted-foreground">
					{#each knowledge as tool (tool)}
						<li>{tool}</li>
					{/each}
				</ul>
			</section>

			<Separator />

			<section class="space-y-4">
				<h2 class="text-2xl font-bold">Experience</h2>
				<div class="space-y-8">
					{#each experience as exp (exp)}
						<div class="space-y-2">
							<div class="flex items-center justify-between">
								<h3 class="text-lg font-bold">
									{exp.title} – {exp.company}
								</h3>
								<span class="text-sm text-muted-foreground">
									{exp.timerange}
								</span>
							</div>
							{#if exp.description}
								<p class="text-sm text-muted-foreground">
									{exp.description}
								</p>
							{/if}
						</div>
					{/each}
				</div>
			</section>
		</div>
	</div>
</section>
