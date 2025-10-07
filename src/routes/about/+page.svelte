<script lang="ts">
	import { Separator } from '$lib/components/ui/separator';
	import { Github, Linkedin } from '@lucide/svelte';
	import { formatDistanceToNow } from 'date-fns';

	const education: { title: string; org: string; timerange: string }[] = [
		{
			title: 'Advanced React with Typescript',
			org: 'TotalTypescript',
			timerange: '07/2025–09/2025'
		},
		{
			title: 'Advanced Typescript Patterns',
			org: 'TotalTypescript',
			timerange: '03/2025–07/2025'
		},
		{
			title: 'Design Patterns – Elements of Reusable Object-Oriented Software',
			org: 'Erich Gamma, Richard Helm, Ralph Johnson, John Vlissides',
			timerange: '03/2025'
		},
		{ title: 'System Design Interview', org: 'Alex Xu', timerange: '03/2025' },
		{
			title: 'Generics',
			org: 'TotalTypescript',
			timerange: '01/2025–03/2025'
		},
		{
			title: 'Pro Essentials',
			org: 'TotalTypescript',
			timerange: '09/2024–12/2024'
		},
		{
			title: 'Type Transformations',
			org: 'TotalTypescript',
			timerange: '07/2024–08/2024'
		},
		{
			title: 'WebDevelopment',
			org: 'neue fische',
			timerange: '03/2023–09/2023'
		}
	];

	const experience: {
		title: string;
		description: string;
		company: string;
		timerange: string;
	}[] = [
		{
			title: 'Developer',
			description:
				'Building custom tracking dashboards and enabling end-to-end tracking for larger customers. Reducing codebase deployment time by up to 75% through monorepo migration. Built and maintain a full-stack application for employee management.',
			company: 'for suxess',
			timerange: '01/2024–present'
		}
	];

	const tools: string[] = ['next.js', 'react', 'prisma', 'drizzle', 'tailwind', 'trpc'];
	const skills: string[] = [
		'typescript',
		'mongodb',
		'node',
		'postgresql',
		'git',
		'rust (learning)'
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
					<enhanced:img
						src="/static/florian_blaschke.webp"
						alt="Profile"
						class="-translate-y-10 object-cover"
					/>
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
							<Github class="mr-2 h-4 w-4" />
							GitHub
						</a>
						<a
							href="https://www.linkedin.com/in/florian-blaschke-b3718928a/"
							class="flex items-center text-sm hover:underline"
							target="_blank"
							rel="noopener noreferrer"
						>
							<Linkedin class="mr-2 h-4 w-4" />
							LinkedIn
						</a>
					</div>
				</div>
			</div>
		</div>

		<div class="space-y-12 md:col-span-2">
			<section class="space-y-4">
				<p class="text-muted-foreground">
					I’m a Developer from Germany with {codingSince} of experience, specializing in TypeScript and
					React. While I’m still early in my journey, I’ve had the opportunity to work on larger projects
					for major clients, refining my skills in building scalable and efficient applications. Always
					learning – always improving.
				</p>
			</section>

			<Separator />

			<section class="space-y-4">
				<h2 class="text-2xl font-bold">Expertise</h2>
				<div class="grid gap-6 sm:grid-cols-2">
					<div class="space-y-2">
						<h3 class="text-lg font-bold">Tools</h3>
						<ul class="space-y-1 text-sm text-muted-foreground">
							{#each tools as tool (tool)}
								<li>{tool}</li>
							{/each}
						</ul>
					</div>
					<div class="space-y-2">
						<h3 class="text-lg font-bold">Skills</h3>
						<ul class="space-y-1 text-sm text-muted-foreground">
							{#each skills as skill (skill)}
								<li>{skill}</li>
							{/each}
						</ul>
					</div>
				</div>
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
							<p class="text-sm text-muted-foreground">
								{exp.description}
							</p>
						</div>
					{/each}
				</div>
			</section>

			<Separator />

			<section class="space-y-4">
				<h2 class="text-2xl font-bold">Education</h2>
				{#each education as step (step)}
					<div class="space-y-2">
						<div class="flex items-start justify-between">
							<h3 class="max-w-3/4 text-lg font-bold">{step.title}</h3>
							<span class=" text-sm text-muted-foreground">
								{step.timerange}
							</span>
						</div>
						<p class=" text-sm text-muted-foreground">
							{step.org}
						</p>
					</div>
				{/each}
			</section>
		</div>
	</div>
</section>
