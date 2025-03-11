<script lang="ts">
	import { fade, fly } from 'svelte/transition';
	import { ChevronRight } from 'lucide-svelte';
	import * as Card from '$lib/components/ui/card';
	import { Button } from '$lib/components/ui/button';
	import { Badge } from '$lib/components/ui/badge';
</script>

<div class="min-h-screen bg-background">
	<!-- Hero Section -->
	<div class="hero min-h-[60vh] bg-card px-3 md:px-5 lg:px-10">
		<div class="hero-content my-5 flex-col gap-8 lg:flex-row-reverse">
			<div in:fly={{ y: 50, duration: 1000 }} class="max-w-lg">
				<img src="https://placehold.co/600x400" alt="Hero" class="rounded-lg shadow" />
			</div>
			<div in:fade={{ duration: 1000 }} class="text-center lg:text-left">
				<h1 class="text-5xl font-bold">Welcome to Our Platform</h1>
				<p class="py-6 text-muted-foreground lg:w-[80%]">
					Provident cupiditate voluptatem et in. Quaerat fugiat ut assumenda excepturi
					exercitationem quasi.
				</p>
				<Button>
					Get Started
					<ChevronRight class="ml-2 h-4 w-4" />
				</Button>
			</div>
		</div>
	</div>

	<!-- Features Section -->
	<div class="px-4 py-16">
		<div class="mb-12 text-center" in:fade={{ duration: 1000, delay: 200 }}>
			<h2 class="text-3xl font-bold">Our Features</h2>
			<p class="mt-2 text-muted-foreground">Everything you need to get started</p>
		</div>

		<div class="mx-auto grid max-w-7xl grid-cols-1 gap-6 px-4 md:grid-cols-2 lg:grid-cols-3">
			{#each Array(3) as _, i}
				<div in:fly={{ y: 50, duration: 1000, delay: 300 + i * 100 }}>
					<Card.Root class="transition-all duration-300 hover:shadow-lg">
						<Card.Content>
							<Badge class="mb-4 w-fit">Feature {i + 1}</Badge>
							<Card.Title>Amazing Feature</Card.Title>
							<Card.Description>If a dog chews shoes whose shoes does he choose?</Card.Description>
						</Card.Content>
						<Card.Footer class="flex justify-end pt-4">
							<Button variant="ghost" size="sm">
								Learn more <ChevronRight class="ml-2 h-4 w-4" />
							</Button>
						</Card.Footer>
					</Card.Root>
				</div>
			{/each}
		</div>
	</div>

	<!-- CTA Section -->
	<div class="bg-card py-16">
		<div class="mx-auto max-w-3xl px-4 text-center" in:fade={{ duration: 1000, delay: 600 }}>
			<h2 class="mb-6 text-4xl font-bold">Ready to get started?</h2>
			<p class="mb-8 text-muted-foreground">Join thousands of satisfied customers today.</p>
			<div class="flex flex-col justify-center gap-4 sm:flex-row">
				<Button>Sign Up Now</Button>
				<Button variant="outline">Learn More</Button>
			</div>
		</div>
	</div>
</div>
