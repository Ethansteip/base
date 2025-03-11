<script lang="ts">
	import * as Card from '$lib/components/ui/card';
	import { Button } from '$lib/components/ui/button';
	import { Input } from '$lib/components/ui/input';
	import { Checkbox } from '$lib/components/ui/checkbox';
	import { Separator } from '$lib/components/ui/separator';
	import { Eye, EyeOff, ChevronRight } from 'lucide-svelte';
	import Loading from '$lib/components/layout/Loading.svelte';
	import appleLogo from '$lib/assets/apple.png';
	import googleLogo from '$lib/assets/google.png';

	let showPassword = false;
	let loading = false;

	const handleLogin = () => {
		loading = true;
		setTimeout(() => {
			loading = false;
		}, 1500);
	};
</script>

<div class="flex min-h-[calc(100vh-120px)] items-center justify-center p-4">
	<Card.Root class="w-full max-w-5xl overflow-hidden lg:flex">
		<!-- Image Section -->
		<div class="relative hidden lg:block lg:w-1/2">
			<div class="absolute inset-0 bg-gradient-to-t from-primary/50 to-primary/30">
				<div class="absolute bottom-10 left-10 text-white">
					<h2 class="mb-2 text-3xl font-bold">Authentication page</h2>
					<h2 class="font-bold">For your new Sveltekit app</h2>
				</div>
			</div>
		</div>

		<!-- Form Section -->
		<Card.Content class="p-6 lg:w-1/2 lg:p-8">
			<h2 class="mb-2 text-3xl font-bold lg:pt-6">Log in to your account</h2>
			<p class="mb-6 text-muted-foreground">
				Don't have an account? <a href="#top" class="text-primary hover:underline">Create account</a
				>
			</p>

			<form class="space-y-4">
				<Input type="email" placeholder="Email" />

				<div class="relative">
					<Input type={showPassword ? 'text' : 'password'} placeholder="Password" class="pr-10" />
					<button
						type="button"
						class="absolute right-3 top-1/2 -translate-y-1/2 text-muted-foreground hover:text-foreground"
						on:click={() => (showPassword = !showPassword)}
					>
						{#if showPassword}
							<Eye class="h-5 w-5" />
						{:else}
							<EyeOff class="h-5 w-5" />
						{/if}
					</button>
				</div>

				<div class="flex items-center justify-between">
					<div class="flex items-center gap-2">
						<Checkbox id="remember" />
						<label for="remember" class="text-sm">Remember me</label>
					</div>
					<a href="#top" class="text-sm text-primary hover:underline">Forgot password?</a>
				</div>

				<Button class="w-full" on:click={handleLogin}>
					{#if loading}
						<Loading />
					{:else}
						Log in
						<ChevronRight class="ml-2 h-4 w-4" />
					{/if}
				</Button>

				<div class="relative flex items-center justify-center">
					<Separator class="my-4" />
					<span class="absolute bg-background px-2 text-sm text-muted-foreground">
						Or continue with
					</span>
				</div>

				<div class="flex flex-col gap-3 sm:flex-row">
					<Button variant="outline" class="flex-1 gap-2">
						<img src={googleLogo} alt="Google" class="h-5 w-5" />
						Google
					</Button>
					<Button variant="outline" class="flex-1 gap-2">
						<img src={appleLogo} alt="Apple" class="h-4 w-4" />
						Apple
					</Button>
				</div>
			</form>
		</Card.Content>
	</Card.Root>
</div>
