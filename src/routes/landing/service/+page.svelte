<script lang="ts">
	import { fade, fly } from 'svelte/transition';
	import { ChartBar, Lightbulb, TrendingUp, ChevronRight } from 'lucide-svelte';
	import * as Card from '$lib/components/ui/card';
	import Button from '$lib/components/ui/button/button.svelte';
	import { Input } from '$lib/components/ui/input';
	import { Textarea } from '$lib/components/ui/textarea';
	import { Label } from '$lib/components/ui/label';
	import { Avatar, AvatarImage, AvatarFallback } from '$lib/components/ui/avatar';

	const testimonials = [
		{
			name: 'Sarah Johnson',
			role: 'CEO, TechCorp',
			image: 'https://i.pravatar.cc/150?img=1',
			content:
				'Working with this team has transformed our business. The results speak for themselves.'
		},
		{
			name: 'Michael Chen',
			role: 'Director, Innovation Labs',
			image: 'https://i.pravatar.cc/150?img=2',
			content: 'Exceptional service and outstanding results. Highly recommended!'
		},
		{
			name: 'Emma Williams',
			role: 'Operations Manager',
			image: 'https://i.pravatar.cc/150?img=3',
			content: 'The attention to detail and professional approach made all the difference.'
		}
	];

	const services = [
		{
			title: 'Strategic Planning',
			description: 'Custom strategies tailored to your business goals and market position.',
			icon: ChartBar
		},
		{
			title: 'Innovation Consulting',
			description: 'Transform your ideas into actionable business solutions.',
			icon: Lightbulb
		},
		{
			title: 'Growth Solutions',
			description: 'Scale your business with data-driven growth strategies.',
			icon: TrendingUp
		}
	];
</script>

<div class="min-h-screen bg-background">
	<!-- Hero Section -->
	<section class="relative min-h-[70vh] overflow-hidden bg-card p-3 lg:px-10">
		<div class="container mx-auto flex px-4">
			<div class="grid min-h-[70vh] w-full items-center gap-12 md:min-h-[60vh] lg:grid-cols-2">
				<div class="order-2 lg:order-1" in:fade={{ duration: 1000 }}>
					<h1 class="text-center text-4xl font-bold leading-tight lg:text-left lg:text-6xl">
						Innovate.<br />
						Transform.<br />
						Succeed.
					</h1>
					<p class="mt-6 text-center text-lg text-muted-foreground lg:text-left">
						We help businesses grow through strategic consulting, innovative solutions, and proven
						methodologies. Let's build your success story together.
					</p>
					<div
						class="mt-8 flex flex-col items-center justify-center gap-4 lg:flex-row lg:justify-start"
					>
						<Button>Schedule Consultation</Button>
						<Button variant="outline">Our Services</Button>
					</div>
				</div>
				<div class="order-1 flex justify-end lg:order-2" in:fly={{ y: 50, duration: 1000 }}>
					<div class="relative lg:w-[90%] 2xl:w-[80%]">
						<div class="aspect-square overflow-hidden rounded-lg bg-muted">
							<img
								src="https://placehold.co/600x600"
								alt="Placeholder"
								class="h-full w-full object-cover"
							/>
						</div>
						<div
							class="absolute -bottom-4 -right-4 h-full w-full rounded-lg border-4 border-muted"
						></div>
					</div>
				</div>
			</div>
		</div>
	</section>

	<!-- Services Section -->
	<section class="py-20">
		<div class="container mx-auto px-4">
			<div class="mb-12 text-center">
				<h2 class="text-4xl font-bold" in:fade>Our Services</h2>
				<p class="mt-4 text-muted-foreground">
					Comprehensive solutions to drive your business forward
				</p>
			</div>
			<div class="grid gap-8 md:grid-cols-2 lg:grid-cols-3">
				{#each services as service, i}
					<div in:fly={{ y: 50, duration: 1000, delay: i * 200 }}>
						<Card.Root class="h-full transition-all hover:-translate-y-2 hover:shadow-lg">
							<Card.Content class="pt-6">
								<div class="flex items-center gap-4">
									<div class="rounded-full bg-primary/10 p-3">
										<svelte:component this={service.icon} class="h-6 w-6 text-primary" />
									</div>
									<Card.Title>{service.title}</Card.Title>
								</div>
								<p class="mt-4 text-muted-foreground">{service.description}</p>
								<div class="mt-4 flex justify-end">
									<a href="#top" class="flex items-center text-sm font-medium text-primary">
										Learn more <ChevronRight class="ml-1 h-4 w-4" />
									</a>
								</div>
							</Card.Content>
						</Card.Root>
					</div>
				{/each}
			</div>
		</div>
	</section>

	<!-- Testimonials Section -->
	<section class="bg-muted/50 py-20">
		<div class="container mx-auto px-4">
			<h2 class="mb-12 text-center text-4xl font-bold" in:fade>Client Testimonials</h2>
			<div class="grid gap-8 md:grid-cols-2 lg:grid-cols-3">
				{#each testimonials as testimonial, i}
					<div in:fly={{ y: 50, duration: 1000, delay: i * 200 }}>
						<Card.Root class="h-full">
							<Card.Content class="flex h-full flex-col justify-between pt-6">
								<div>
									<div class="flex items-center gap-4">
										<Avatar>
											<AvatarImage src={testimonial.image} alt={testimonial.name} />
											<AvatarFallback>{testimonial.name[0]}</AvatarFallback>
										</Avatar>
										<div>
											<p class="font-semibold">{testimonial.name}</p>
											<p class="text-sm text-muted-foreground">{testimonial.role}</p>
										</div>
									</div>
									<p class="mt-4 text-muted-foreground">"{testimonial.content}"</p>
								</div>
							</Card.Content>
						</Card.Root>
					</div>
				{/each}
			</div>
		</div>
	</section>

	<!-- Contact Section -->
	<section class="py-20">
		<div class="container mx-auto px-4" in:fade={{ duration: 1000 }}>
			<Card.Root class="mx-auto max-w-3xl">
				<Card.Content class="pt-6">
					<h2 class="mb-8 text-center text-4xl font-bold">Get In Touch</h2>
					<form class="space-y-6">
						<div class="grid gap-6 md:grid-cols-2">
							<div class="space-y-2">
								<Label for="name">Name</Label>
								<Input type="text" id="name" placeholder="Your name" />
							</div>
							<div class="space-y-2">
								<Label for="email">Email</Label>
								<Input type="email" id="email" placeholder="Your email" />
							</div>
						</div>
						<div class="space-y-2">
							<Label for="message">Message</Label>
							<Textarea id="message" placeholder="How can we help?" class="h-32" />
						</div>
						<Button class="w-full">Send Message</Button>
					</form>
				</Card.Content>
			</Card.Root>
		</div>
	</section>
</div>
