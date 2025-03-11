<script lang="ts">
	import { fade } from 'svelte/transition';
	import { ChevronRight, Cat, Box, Database, MessageCircleCode, Check } from 'lucide-svelte';
	import * as Card from '$lib/components/ui/card';
	import { Button } from '$lib/components/ui/button';
</script>

<div class="min-h-screen">
	<!-- Hero Section -->
	<section class="relative min-h-[70vh] overflow-hidden bg-secondary/10">
		<div class="container absolute inset-0 flex items-center justify-center">
			<div class="max-w-md text-center">
				<div in:fade={{ duration: 1000, delay: 200 }}>
					<h1 class="text-5xl font-bold">Your SaaS Solution</h1>
				</div>
				<div in:fade={{ duration: 1000, delay: 600 }}>
					<p class="py-6 text-muted-foreground">
						Streamline your workflow with our powerful platform. Simple, efficient, and designed for
						modern teams.
					</p>
				</div>
				<div in:fade={{ duration: 1000, delay: 1000 }}>
					<Button variant="default">Get Started <ChevronRight class="ml-2" /></Button>
				</div>
			</div>
		</div>
	</section>

	<!-- Trusted By Section -->
	<section class="py-12">
		<div class="container mx-auto max-w-3xl px-4">
			<h2 class="mb-8 text-center text-2xl font-semibold text-muted-foreground">
				Trusted by innovative teams
			</h2>
			<div class="scroll-container overflow-hidden">
				<div class="scroll-content flex h-auto">
					<!-- First set of logos -->
					<div class="flex items-center gap-8 px-4">
						<div class="flex items-center space-x-3">
							<Cat class="h-8 w-8" />
							<p class="whitespace-nowrap">Company A</p>
						</div>
						<div class="flex items-center space-x-3">
							<Box class="h-8 w-8" />
							<p class="whitespace-nowrap">Company A</p>
						</div>
						<div class="flex items-center space-x-3">
							<Database class="h-8 w-8" />
							<p class="whitespace-nowrap">Company A</p>
						</div>
						<div class="flex items-center space-x-3">
							<MessageCircleCode class="h-8 w-8" />
							<p class="whitespace-nowrap">Company A</p>
						</div>
					</div>
					<!-- Duplicate set for seamless scrolling -->
					<div class="flex items-center gap-8 px-4">
						<div class="flex items-center space-x-3">
							<Cat class="h-8 w-8" />
							<p class="whitespace-nowrap">Company A</p>
						</div>
						<div class="flex items-center space-x-3">
							<Box class="h-8 w-8" />
							<p class="whitespace-nowrap">Company A</p>
						</div>
						<div class="flex items-center space-x-3">
							<Database class="h-8 w-8" />
							<p class="whitespace-nowrap">Company A</p>
						</div>
						<div class="flex items-center space-x-3">
							<MessageCircleCode class="h-8 w-8" />
							<p class="whitespace-nowrap">Company A</p>
						</div>
					</div>
				</div>
			</div>
		</div>
	</section>

	<!-- About Our Product Section -->
	<section class="bg-secondary/10 p-5 lg:p-16">
		<div class="container mx-auto px-4">
			<div class="flex flex-col items-center gap-12 lg:flex-row">
				<div class="space-y-6 text-center lg:w-1/2 lg:text-left">
					<h2 class="text-4xl font-bold text-primary">Transform Your Workflow</h2>
					<p class="text-lg text-muted-foreground">
						<span class="flex 2xl:hidden"
							>Our platform combines powerful features with intuitive design to help teams work
							smarter, not harder.</span
						>
						<span class="hidden 2xl:flex"
							>Our platform combines powerful features with intuitive design to help teams work
							smarter, not harder. Built for modern businesses, we provide the tools you need to
							streamline collaboration, automate repetitive tasks, and drive productivity.</span
						>
					</p>
					<div class="space-y-4">
						<div class="flex items-center justify-center gap-3 lg:justify-start">
							<Check class="text-primary" />
							<span>Automated workflow tools</span>
						</div>
						<div class="flex items-center justify-center gap-3 lg:justify-start">
							<Check class="text-primary" />
							<span>Advanced analytics</span>
						</div>
						<div class="flex items-center justify-center gap-3 lg:justify-start">
							<Check class="text-primary" />
							<span>Secure cloud storage</span>
						</div>
					</div>
				</div>
				<div class="lg:w-1/2">
					<img
						src="https://placehold.co/600x400"
						alt="Product Dashboard"
						class="h-auto w-full rounded-lg shadow-xl"
					/>
				</div>
			</div>
		</div>
	</section>

	<!-- Pricing Section -->
	<section class="py-16">
		<div class="container mx-auto px-4">
			<h2 class="mb-12 text-center text-3xl font-bold">Simple, Transparent Pricing</h2>
			<div class="grid grid-cols-1 gap-8 md:grid-cols-3 lg:px-10">
				<!-- Basic Plan -->
				<Card.Root class="relative flex flex-col justify-between">
					<Card.Header>
						<Card.Title class="text-center text-2xl">Basic</Card.Title>
						<div class="my-4 text-center">
							<span class="text-4xl font-bold">$29</span>
							<span class="text-muted-foreground">/month</span>
						</div>
					</Card.Header>
					<Card.Content class="space-y-3">
						<div class="flex items-center gap-2">
							<Check class="h-5 w-5 text-primary" />
							<span>Up to 5 team members</span>
						</div>
						<div class="flex items-center gap-2">
							<Check class="h-5 w-5 text-primary" />
							<span>Basic analytics</span>
						</div>
						<div class="flex items-center gap-2">
							<Check class="h-5 w-5 text-primary" />
							<span>48-hour support response time</span>
						</div>
						<div class="flex items-center gap-2">
							<Check class="h-5 w-5 text-primary" />
							<span>10GB storage</span>
						</div>
					</Card.Content>
					<Card.Footer class="mt-6">
						<Button variant="default" class="w-full">Get Started</Button>
					</Card.Footer>
				</Card.Root>

				<!-- Pro Plan -->
				<Card.Root class="elative flex flex-col justify-between">
					<Card.Header>
						<Card.Title class="text-center text-2xl">Pro</Card.Title>
						<div class="my-4 text-center">
							<span class="text-4xl font-bold">$99</span>
							<span class="text-muted-foreground">/month</span>
						</div>
					</Card.Header>
					<Card.Content class="space-y-3">
						<div class="flex items-center gap-2">
							<Check class="h-5 w-5 text-primary" />
							<span>Up to 15 team members</span>
						</div>
						<div class="flex items-center gap-2">
							<Check class="h-5 w-5 text-primary" />
							<span>Advanced analytics</span>
						</div>
						<div class="flex items-center gap-2">
							<Check class="h-5 w-5 text-primary" />
							<span>24-hour support response time</span>
						</div>
						<div class="flex items-center gap-2">
							<Check class="h-5 w-5 text-primary" />
							<span>50GB storage</span>
						</div>
						<div class="flex items-center gap-2">
							<Check class="h-5 w-5 text-primary" />
							<span>Custom integrations</span>
						</div>
					</Card.Content>
					<Card.Footer class="mt-6">
						<Button variant="default" class="w-full">Get Started</Button>
					</Card.Footer>
				</Card.Root>

				<!-- Enterprise Plan -->
				<Card.Root class="elative flex flex-col justify-between">
					<Card.Header>
						<Card.Title class="text-center text-2xl">Enterprise</Card.Title>
						<div class="my-4 text-center">
							<span class="text-4xl font-bold">$299</span>
							<span class="text-muted-foreground">/month</span>
						</div>
					</Card.Header>
					<Card.Content class="space-y-3">
						<div class="flex items-center gap-2">
							<Check class="h-5 w-5 text-primary" />
							<span>Unlimited team members</span>
						</div>
						<div class="flex items-center gap-2">
							<Check class="h-5 w-5 text-primary" />
							<span>Advanced analytics & reporting</span>
						</div>
						<div class="flex items-center gap-2">
							<Check class="h-5 w-5 text-primary" />
							<span>1-hour support response time</span>
						</div>
						<div class="flex items-center gap-2">
							<Check class="h-5 w-5 text-primary" />
							<span>Unlimited storage</span>
						</div>
						<div class="flex items-center gap-2">
							<Check class="h-5 w-5 text-primary" />
							<span>Custom integrations</span>
						</div>
						<div class="flex items-center gap-2">
							<Check class="h-5 w-5 text-primary" />
							<span>Dedicated account manager</span>
						</div>
					</Card.Content>
					<Card.Footer class="mt-6">
						<Button variant="default" class="w-full">Contact Sales</Button>
					</Card.Footer>
				</Card.Root>
			</div>
		</div>
	</section>
</div>

<style>
	@keyframes scroll {
		0% {
			transform: translateX(0);
		}
		100% {
			transform: translateX(-50%);
		}
	}

	.scroll-container {
		mask-image: linear-gradient(to right, transparent, black 15%, black 85%, transparent);
	}

	.scroll-content {
		animation: scroll 20s linear infinite;
	}
</style>
