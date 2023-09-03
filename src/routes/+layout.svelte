<script>
	import Navbar from '$lib/components/Navbar.svelte';
    import '../app.css';
</script>

<main id="main" class="w-full">
    <Navbar />
    <slot />
</main>