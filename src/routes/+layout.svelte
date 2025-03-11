<script lang="ts">
	import '../app.css';
	import Footer from '$lib/components/layout/Footer.svelte';
	import Navbar from '$lib/components/layout/Navbar.svelte';
	let { children } = $props();
</script>

<Navbar />
{@render children()}
<Footer />
