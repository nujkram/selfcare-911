<script>
    import { cubicInOut } from 'svelte/easing';
	import fadeScale from '$lib/utils/svelte-transition-fade-scale';


    function redirect() {
        window.open("https://www.schedulicity.com/scheduling/SC9Q6U");
    }

    let condition = false;

    // Set the condition to true after 1 second
    setTimeout(() => {
        condition = true;
    }, 500);
</script>

{#if condition}
<div class="container mx-auto relative h-screen border-[45px] border-white shadow-2xl" transition:fadeScale={{
    delay: 250,
    duration: 1000,
    easing: cubicInOut,
    baseScale: 0.5
}}>
    <img src="/bg-image.jpg" class="absolute w-full h-full object-cover" alt="Scented glass with flower and hexagon background" />
    <div class="absolute inset-0 flex items-center justify-center sm:w-[50%] w-full">
        <div class="bg-white p-14 px-12 bg-opacity-80 text-green-600 h-full xl:text-3xl lg:text-2xl md:text-xl sm:text-base">
            <p>Welcome to <span class="font-bold text-green-700">Self Care 911</span> health and wellness, your one-stop-shop for all your self-care needs. We are a medical spa that specializes in enhancing and nourishing your skin, helping you to look and feel your best. Our expert team is dedicated to providing you with the best possible care, using state-of-the-art equipment and techniques.</p>
            <button class="bg-green-600 p-4 text-sm rounded-2xl mt-10 text-white hover:bg-green-500" on:click={redirect}>Schedule Appointment</button>
        </div>
    </div>
</div>
{/if}
