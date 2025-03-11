<script lang="ts">
	import { Eye, EyeOff, ChevronRight } from 'lucide-svelte';
	import Loading from '$lib/components/layout/Loading.svelte';
	import appleLogo from '$lib/assets/apple.png';
	import googleLogo from '$lib/assets/google.png';
	import { Button } from '$lib/components/ui/button';
	import { Input } from '$lib/components/ui/input';
	import { Label } from '$lib/components/ui/label';
	import { Checkbox } from '$lib/components/ui/checkbox';
	import { Separator } from '$lib/components/ui/separator';

	let showPassword = false;
	let loading = false;

	const handleLogin = () => {
		loading = true;
		setTimeout(() => {
			loading = false;
		}, 1500);
	};
</script>

<div class="flex min-h-[calc(100vh-120px)]">
	<!-- Form Section -->
	<div class="flex w-full flex-col justify-center bg-background px-8 py-12 lg:w-1/2 lg:px-20">
		<div class="mx-auto w-full max-w-lg">
			<h2 class="mb-2 text-3xl font-bold">Log in to your account</h2>
			<p class="mb-6 text-muted-foreground">
				Don't have an account? <a href="#top" class="text-primary hover:underline">Create account</a
				>
			</p>

			<form class="space-y-4">
				<div class="space-y-2">
					<Label for="email">Email</Label>
					<Input type="email" id="email" placeholder="Email" />
				</div>

				<div class="space-y-2">
					<Label for="password">Password</Label>
					<div class="relative">
						<Input
							type={showPassword ? 'text' : 'password'}
							id="password"
							placeholder="Password"
							class="pr-10"
						/>
						<Button
							variant="ghost"
							size="icon"
							type="button"
							class="absolute right-0 top-0 h-full px-3 hover:bg-transparent"
							on:click={() => (showPassword = !showPassword)}
						>
							{#if showPassword}
								<Eye class="h-4 w-4" />
							{:else}
								<EyeOff class="h-4 w-4" />
							{/if}
						</Button>
					</div>
				</div>

				<div class="flex items-center justify-between">
					<div class="flex items-center gap-2">
						<Checkbox id="remember" />
						<Label for="remember" class="text-sm font-normal">Remember me</Label>
					</div>
					<a href="#top" class="text-sm text-primary hover:underline">Forgot password?</a>
				</div>

				<Button class="w-full" on:click={handleLogin}>
					{#if loading}
						<Loading />
					{:else}
						Log in
						<ChevronRight class="h-4 w-4" />
					{/if}
				</Button>

				<div class="relative">
					<Separator />
					<div class="absolute inset-x-0 top-1/2 flex -translate-y-1/2 justify-center">
						<span class="bg-background px-2 text-muted-foreground">Or continue with</span>
					</div>
				</div>

				<div class="flex flex-col gap-4 sm:flex-row">
					<Button variant="outline" class="flex-1 gap-2">
						<img src={googleLogo} alt="Google" class="h-8 w-8" />
						Google
					</Button>
					<Button variant="outline" class="flex-1 gap-2">
						<img src={appleLogo} alt="Apple" class="h-7 w-7" />
						Apple
					</Button>
				</div>
			</form>
		</div>
	</div>

	<!-- Gradient Section -->
	<div class="relative hidden w-1/2 bg-gradient-to-t from-primary/20 to-secondary/50 lg:block">
		<div class="absolute bottom-10 left-10">
			<h2 class="mb-2 text-3xl font-bold text-white">Authentication page</h2>
			<h2 class="font-bold text-white">For your new Sveltekit app</h2>
		</div>
	</div>
</div>
