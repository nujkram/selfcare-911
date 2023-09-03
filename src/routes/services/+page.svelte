<script>
    import { cubicInOut } from 'svelte/easing';
	import fadeScale from '$lib/utils/svelte-transition-fade-scale';

    let condition = false;

    // Set the condition to true after 1 second
    setTimeout(() => {
        condition = true;
    }, 500);
</script>
{#if condition}
<div class="container mx-auto" transition:fadeScale={{delay: 250, duration: 1000, easing: cubicInOut, baseScale: 0.5 }}>
    <div class="flex bg-white opacity-75 px-12 py-8 gap-12">
        <div class="w-7/12">
            <h1>The Clinic</h1>
            <p class="mb-8">
                At Selfcare 911 health and wellness, we offer a range of treatments to help you look and feel your best. Our services are designed to enhance and nourish your skin, leaving you with a healthy, youthful glow. From relaxing facials to advanced laser treatments, our team of experts will help you achieve your beauty goals. Our services include: • Facials: Relaxing and rejuvenating treatments tailored to your skin's needs. • Laser Treatments: Advanced laser treatments to address a range of skin concerns, including fine lines, wrinkles, sun damage, and acne. • Botox and Fillers: We offer a range of injectable treatments to help smooth wrinkles and restore volume to your face. • Vein Treatments: Our spider vein treatments use the latest technology to safely and effectively reduce the appearance of spider veins. • Microdermabrasion: A non-invasive treatment that exfoliates and brightens your skin, leaving it looking and feeling refreshed. Book a consultation with one of our experts today to learn more about how we can help you achieve your beauty goals.
            </p>
        </div>
        <div class="w-5/12">
            <div class="bg-cover bg-no-repeat bg-center h-full" style="background-image: url('./service-image-1.jpg');"></div>
        </div>
    </div>
</div>
{/if}