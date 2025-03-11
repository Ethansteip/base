<script lang="ts">
	import { Eye, EyeOff, ChevronRight } from 'lucide-svelte';
	import appleLogo from '$lib/assets/apple.png';
	import googleLogo from '$lib/assets/google.png';
	import Loading from '$lib/components/layout/Loading.svelte';
	import * as Card from '$lib/components/ui/card';
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

<div class="flex min-h-[80vh] items-center justify-center p-4">
	<Card.Root class="w-full max-w-md">
		<Card.Content class="pt-6">
			<h2 class="mb-2 text-3xl font-bold">Log in to your account</h2>
			<p class="mb-6 text-muted-foreground">
				Don't have an account? <a href="#top" class="text-primary hover:underline">Create account</a
				>
			</p>

			<form class="space-y-4">
				<div class="space-y-2">
					<Input type="email" placeholder="Email" />
				</div>

				<div class="relative space-y-2">
					<Input type={showPassword ? 'text' : 'password'} placeholder="Password" class="pr-10" />
					<Button
						variant="ghost"
						size="icon"
						type="button"
						class="absolute right-0 top-0"
						on:click={() => (showPassword = !showPassword)}
					>
						{#if showPassword}
							<Eye class="h-4 w-4" />
						{:else}
							<EyeOff class="h-4 w-4" />
						{/if}
					</Button>
				</div>

				<div class="flex items-center justify-between">
					<div class="flex items-center space-x-2">
						<Checkbox id="remember" />
						<Label for="remember">Remember me</Label>
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

				<div class="relative">
					<div class="absolute inset-0 flex items-center">
						<Separator class="my-4" />
					</div>
					<div class="relative flex justify-center text-xs uppercase">
						<span class="bg-background px-2 text-muted-foreground">Or continue with</span>
					</div>
				</div>

				<div class="grid gap-4 sm:grid-cols-2">
					<Button variant="outline" class="gap-2">
						<img src={googleLogo} alt="Google" class="h-8 w-8" />
						Google
					</Button>
					<Button variant="outline" class="gap-2">
						<img src={appleLogo} alt="Apple" class="h-7 w-7" />
						Apple
					</Button>
				</div>
			</form>
		</Card.Content>
	</Card.Root>
</div>
