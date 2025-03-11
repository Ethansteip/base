<script lang="ts">
	import { fade, fly } from 'svelte/transition';
	import { onMount } from 'svelte';
	import { ChevronRight, MessageCircleCode, Shield, Zap, WandSparkles } from 'lucide-svelte';
	import { Button } from '$lib/components/ui/button';
	import { Card, CardContent, CardTitle } from '$lib/components/ui/card';
	import IphoneMockup from '$lib/components/other/IphoneMockup.svelte';

	let mounted = false;

	onMount(() => {
		mounted = true;
	});

	const features = [
		{
			icon: Zap,
			title: 'Lightning Fast',
			description: 'Optimized for speed and performance. Experience instant loading times.'
		},
		{
			icon: Shield,
			title: 'Secure',
			description:
				'Your data is always protected with enterprise-grade security and end-to-end encryption.'
		},
		{
			icon: WandSparkles,
			title: 'Easy To Use',
			description:
				'Intuitive interface designed for everyone. Get started quickly with no learning curve.'
		}
	];

	const stats = [
		{ title: 'Downloads', value: '100K+', desc: 'From App Store & Play Store' },
		{ title: 'Users', value: '50K+', desc: 'Active Monthly Users' },
		{ title: 'Rating', value: '4.8/5', desc: 'Based on 2,000+ reviews' }
	];
</script>

<div id="top" class="min-h-screen bg-background">
	{#if mounted}
		<!-- Hero Section -->
		<div class="bg-muted/50 py-16 md:py-24" in:fade={{ duration: 1000 }}>
			<div
				class="container flex flex-col items-center justify-center gap-12 px-4 lg:flex-row-reverse"
			>
				<!-- Mock phone display -->
				<div in:fly={{ x: 50, duration: 1000, delay: 200 }}>
					<IphoneMockup class="w-full md:w-[16rem] lg:w-[18rem] xl:w-[20rem]" />
				</div>

				<div
					class="max-w-md text-center md:text-left"
					in:fly={{ x: -50, duration: 1000, delay: 400 }}
				>
					<h1 class="text-4xl font-bold text-primary sm:text-5xl">Your App Name</h1>
					<p class="py-4 text-lg text-muted-foreground">
						Simplify your life with our revolutionary app. Experience the future of [your app
						category] today.
					</p>
					<div class="flex justify-center gap-4 lg:justify-start">
						<Button variant="default">
							App Store
							<ChevronRight class="ml-2 h-4 w-4" />
						</Button>
						<Button variant="default">
							Play Store
							<ChevronRight class="ml-2 h-4 w-4" />
						</Button>
					</div>
				</div>
			</div>
		</div>

		<!-- Features Section -->
		<div class="container px-4 py-24" in:fade={{ duration: 1000, delay: 600 }}>
			<h2 class="mb-4 text-center text-3xl font-bold">Why Choose Our App?</h2>
			<p class="mb-16 text-center text-lg text-muted-foreground">
				Discover the features that make our app stand out from the competition
			</p>
			<div class="grid gap-8 md:grid-cols-2 lg:grid-cols-3">
				{#each features as feature, i}
					<div in:fly={{ y: 50, duration: 1000, delay: 800 + i * 200 }}>
						<Card class="transition-all duration-300 hover:shadow-lg">
							<CardContent class="pt-6">
								<div class="flex items-center gap-3">
									<div class="rounded-lg bg-primary/10 p-3">
										<svelte:component this={feature.icon} class="h-6 w-6 text-primary" />
									</div>
									<CardTitle>{feature.title}</CardTitle>
								</div>
								<p class="mt-4 text-muted-foreground">{feature.description}</p>
								<div class="mt-4 flex justify-end">
									<Button variant="link" class="text-primary">
										Learn more
										<ChevronRight class="ml-2 h-4 w-4" />
									</Button>
								</div>
							</CardContent>
						</Card>
					</div>
				{/each}
			</div>
		</div>

		<!-- Stats Section -->
		<div class="bg-muted/50 py-16" in:fade={{ duration: 1000, delay: 1000 }}>
			<div class="container px-4">
				<h2 class="mb-4 text-center text-3xl font-bold">Our Impact</h2>
				<p class="mb-16 text-center text-lg text-muted-foreground">
					See how we're making a difference in the numbers
				</p>
				<div class="mx-auto grid gap-8 md:grid-cols-2 lg:w-[80%] lg:grid-cols-3">
					{#each stats as stat}
						<Card>
							<CardContent class="flex flex-col items-center justify-center py-6">
								<p class="text-sm text-muted-foreground">{stat.title}</p>
								<p class="mt-2 text-3xl font-bold text-primary">{stat.value}</p>
								<p class="text-xs text-muted-foreground">{stat.desc}</p>
							</CardContent>
						</Card>
					{/each}
				</div>
			</div>
		</div>

		<!-- CTA Section -->
		<div in:fly={{ y: 50, duration: 1000, delay: 1200 }}>
			<div class="container px-4 py-16">
				<div class="flex flex-col items-center gap-6 text-center">
					<h2 class="text-3xl font-bold text-primary">Download Now</h2>
					<p class="max-w-md text-lg text-muted-foreground">
						Join thousands of satisfied users and transform your experience today.
					</p>
					<div class="flex gap-4">
						<Button variant="default">
							App Store
							<ChevronRight class="ml-2 h-4 w-4" />
						</Button>
						<Button variant="default">
							Play Store
							<ChevronRight class="ml-2 h-4 w-4" />
						</Button>
					</div>
				</div>
			</div>
		</div>
	{/if}
</div>
