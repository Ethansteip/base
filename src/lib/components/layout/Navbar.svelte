<script lang="ts">
	import { Zap, Bird, Menu } from 'lucide-svelte';
	import * as Sheet from '$lib/components/ui/sheet/index';
	import { Button } from '$lib/components/ui/button';

	let open = false;
</script>

<div class="w-full" id="top">
	<div id="top" class="border-b bg-background">
		<div class="flex h-16 items-center justify-between px-4">
			<!-- Logo and Project Name -->
			<div class="flex w-1/3 items-center gap-2">
				<div class="rounded-lg border p-2 2xl:hidden">
					<Bird class="h-5 w-5" />
				</div>
				<div class="hidden 2xl:block">
					<Zap class="h-5 w-5" />
				</div>
				<h2 class="hidden text-sm font-semibold lg:flex">Testing Testing</h2>
			</div>

			<h2 class="text-sm font-semibold lg:hidden">Testing Testing</h2>

			<!-- Desktop Navigation -->
			<div class="hidden w-1/3 flex-1 items-center justify-center lg:flex">
				<nav class="flex gap-6">
					<Button variant="ghost" size="sm" href="/auth">Sign In</Button>
					<Button variant="ghost" size="sm" href="/account">Account</Button>
					<Button variant="ghost" size="sm" href="#top">Privacy</Button>
				</nav>
			</div>

			<div class="flex w-1/3 items-center justify-end gap-4">
				<Button variant="ghost" size="sm" class="hidden lg:flex">Sign Up</Button>

				<!-- Mobile Menu Button -->
				<Button variant="ghost" size="icon" class="lg:hidden" on:click={() => (open = true)}>
					<Menu class="h-5 w-5" />
				</Button>
			</div>
		</div>
	</div>

	<!-- Mobile Sheet/Drawer -->
	<Sheet.Root bind:open>
		<Sheet.Content side="left" class="w-64 bg-popover">
			<div class="">
				<div class="mb-6 flex items-center justify-start gap-x-3">
					<div class="rounded-lg border p-2">
						<Bird class="h-5 w-5" />
					</div>
					<span class="text-md font-semibold">Menu</span>
				</div>
				<nav class="flex flex-col space-y-1">
					<Button variant="ghost" class="justify-start" href="/auth">Sign In</Button>
					<Button variant="ghost" class="justify-start" href="/account">Account</Button>
					<Button variant="ghost" class="justify-start" href="#top">Contact</Button>
					<Button variant="ghost" class="justify-start" href="#top">Privacy</Button>
				</nav>
			</div>
		</Sheet.Content>
	</Sheet.Root>
</div>
