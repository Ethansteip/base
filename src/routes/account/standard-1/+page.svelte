<script lang="ts">
	import { Button } from '$lib/components/ui/button';
	import { Input } from '$lib/components/ui/input';
	import { Label } from '$lib/components/ui/label';
	import {
		Card,
		CardContent,
		CardDescription,
		CardHeader,
		CardTitle
	} from '$lib/components/ui/card';
	import { Separator } from '$lib/components/ui/separator';
	import { Avatar, AvatarFallback, AvatarImage } from '$lib/components/ui/avatar';
	import { Switch } from '$lib/components/ui/switch';

	const userProfile = $state({
		name: 'John Doe',
		email: 'john@example.com',
		avatar: 'https://github.com/shadcn.png',
		notifications: {
			email: true,
			push: false,
			marketing: true
		}
	});
</script>

<div class="container mx-auto max-w-3xl space-y-8 p-4 pt-10">
	<div class="flex flex-col gap-4 md:flex-row md:items-center md:justify-between">
		<div>
			<h1 class="text-3xl font-bold tracking-tight">Account Settings</h1>
			<p class="text-muted-foreground">Manage your account settings and preferences</p>
		</div>
		<Button>Save changes</Button>
	</div>

	<Card>
		<CardHeader class="flex flex-col items-center">
			<CardTitle>Profile</CardTitle>
			<CardDescription>Update your personal information.</CardDescription>
		</CardHeader>
		<CardContent class="space-y-6">
			<div class="flex flex-col items-center gap-6">
				<Avatar class="h-24 w-24">
					<AvatarImage src={userProfile.avatar} alt={userProfile.name} />
					<AvatarFallback>JD</AvatarFallback>
				</Avatar>
				<div class="flex flex-col items-center space-y-2">
					<Button variant="outline">Change avatar</Button>
					<p class="hidden text-center text-xs text-muted-foreground md:flex">
						Recommended: Square JPG, PNG, or GIF, at least 400x400.
					</p>
				</div>
			</div>

			<div class="grid gap-4 sm:grid-cols-2">
				<div class="space-y-2">
					<Label for="name">Name</Label>
					<Input id="name" bind:value={userProfile.name} />
				</div>
				<div class="space-y-2">
					<Label for="email">Email</Label>
					<Input id="email" type="email" bind:value={userProfile.email} />
				</div>
			</div>
		</CardContent>
	</Card>

	<Card>
		<CardHeader>
			<CardTitle>Notifications</CardTitle>
			<CardDescription>Configure how you receive notifications.</CardDescription>
		</CardHeader>
		<CardContent class="space-y-4">
			<div class="flex items-center justify-between">
				<div class="space-y-1">
					<Label>Email notifications</Label>
					<p class="text-sm text-muted-foreground">Receive emails about your account activity.</p>
				</div>
				<Switch bind:checked={userProfile.notifications.email} />
			</div>
			<Separator />
			<div class="flex items-center justify-between">
				<div class="space-y-1">
					<Label>Push notifications</Label>
					<p class="text-sm text-muted-foreground">Receive push notifications on your device.</p>
				</div>
				<Switch bind:checked={userProfile.notifications.push} />
			</div>
			<Separator />
			<div class="flex items-center justify-between">
				<div class="space-y-1">
					<Label>Marketing emails</Label>
					<p class="text-sm text-muted-foreground">
						Receive emails about new products and features.
					</p>
				</div>
				<Switch bind:checked={userProfile.notifications.marketing} />
			</div>
		</CardContent>
	</Card>

	<Card>
		<CardHeader>
			<CardTitle>Danger Zone</CardTitle>
			<CardDescription>Irreversible and destructive actions.</CardDescription>
		</CardHeader>
		<CardContent>
			<div class="space-y-4">
				<div class="space-y-2">
					<h4 class="font-medium">Delete Account</h4>
					<p class="text-sm text-muted-foreground">
						Permanently delete your account and all associated data.
					</p>
				</div>
				<Button variant="destructive">Delete Account</Button>
			</div>
		</CardContent>
	</Card>
</div>
