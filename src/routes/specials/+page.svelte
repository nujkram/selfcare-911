<script>
    import { onMount } from "svelte";
    import { cubicInOut } from 'svelte/easing';
	import fadeScale from '$lib/utils/svelte-transition-fade-scale';

    let condition = false;

    // Set the condition to true after 1 second
    setTimeout(() => {
        condition = true;
    }, 500);

    let pricingOptions = [
      {
        title: "Basic Plan",
        description: "Lorem ipsum dolor sit amet, consectetur adipiscing elit.",
        price: "$19.99/month",
      },
      {
        title: "Pro Plan",
        description: "Pellentesque ac justo eu augue condimentum interdum.",
        price: "$39.99/month",
      },
      {
        title: "Premium Plan",
        description: "Fusce in ligula nec mauris blandit hendrerit.",
        price: "$59.99/month",
      },
    ];
  
    // Function to set equal height to pricing cards
    function setEqualHeight() {
      const cards = document.querySelectorAll(".pricing-card");
      let maxHeight = 0;
  
      cards.forEach((card) => {
        const cardHeight = card.clientHeight;
        if (cardHeight > maxHeight) {
          maxHeight = cardHeight;
        }
      });
  
      cards.forEach((card) => {
        card.style.height = `${maxHeight}px`;
      });
    }
  
    onMount(() => {
      setEqualHeight();
    });
  </script>
  {#if condition}
  <!-- Pricing Cards -->
  <div class="flex justify-center items-center mt-16" transition:fadeScale={{delay: 250, duration: 1000, easing: cubicInOut, baseScale: 0.5 }}>
    {#each pricingOptions as option (option.price)}
      <div class="max-w-xs rounded-lg overflow-hidden shadow-lg m-4 bg-white pricing-card">
        <div class="px-6 py-4">
          <div class="font-bold text-xl mb-2">{option.title}</div>
          <p class="text-gray-700 text-base">{option.description}</p>
        </div>
        <div class="px-6 py-4">
          <div class="font-bold text-xl mb-2">{option.price}</div>
          <button class="bg-green-600 hover:bg-green-500 text-white font-bold py-2 px-4 rounded-full">
            Get Started
          </button>
        </div>
      </div>
    {/each}
  </div>
  {/if}