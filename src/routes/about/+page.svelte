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
                I'm a paragraph. Click here to add your own text and edit me. It’s easy. Just click “Edit Text” or double click me and you can start adding your own content and make changes to the font. Feel free to drag and drop me anywhere you like on your page. I’m a great place for you to tell a story and let your users know a little more about you.
            </p>
            <p class="mb-8">
                This is a great space to write long text about your company and your services. You can use this space to go into a little more detail about your company. Talk about your team and what services you provide. Tell your visitors the story of how you came up with the idea for your business and what makes you different from your competitors. Make your company stand out and show your visitors who you are. Tip: Add your own image by double clicking the image and clicking Change Image.
            </p>
            <h1>Our Philosophy</h1>
            <p class="mb-8">
                I'm a paragraph. Click here to add your own text and edit me. It’s easy. Just click “Edit Text” or double click me and you can start adding your own content and make changes to the font. Feel free to drag and drop me anywhere you like on your page. I’m a great place for you to tell a story and let your users know more about you
            </p>
        </div>
        <div class="w-5/12">
            <div class="bg-cover bg-no-repeat bg-center h-full" style="background-image: url('./about-image-1.jpg');"></div>
        </div>
    </div>
</div>
{/if}