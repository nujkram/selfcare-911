<script>
	import Icon from "./Icon.svelte";

  let showMenu = false;

  function toggleNavbar() {
    showMenu = !showMenu;
  }
</script>

<div class="bg-white">
  <div>
    <nav
      class="container px-6 py-8 mx-auto md:flex md:justify-between md:items-center"
    >
      <div class="flex items-center justify-between">
        <a
          class="text-xl font-bold text-gray-800 md:text-2xl hover:text-blue-400"
          href="/home"
          >
          <!-- insert image logo-1.png -->
            <img src="/logo-3.png" alt="logo"/>
        </a>
        <!-- Mobile menu button -->
        <div role="button" tabindex="0" on:click={toggleNavbar} on:keydown={toggleNavbar} class="flex md:hidden">
          <button
            type="button"
            class="text-gray-800 hover:text-gray-400 focus:outline-none focus:text-gray-400"
          >
            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
            <path stroke-linecap="round" stroke-linejoin="round" d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5" />
          </svg>
          </button>
        </div>
      </div>

      <!-- Mobile Menu open: "block", Menu closed: "hidden" -->
      <div
        class="flex-col mt-8 space-y-4 md:text-md md:flex md:space-y-0 md:flex-row md:items-center md:space-x-10 md:mt-0 {showMenu
          ? 'flex'
          : 'hidden'}"
      >
        <a class="flex gap-2 items-center text-green-400 font-bold hover:text-yellow-400" href="/"><Icon width="18" height="18" name="home" />Home</a>
        <a class="flex gap-2 items-center text-green-400 font-bold hover:text-yellow-400" href="/about"><Icon width="18" height="18" name="about" />The Clinic</a>
        <a class="flex gap-2 items-center text-green-400 font-bold hover:text-yellow-400" href="/services"><Icon width="18" height="18" name="service" />Treatments</a>
        <a class="flex gap-2 items-center text-green-400 font-bold hover:text-yellow-400" href="/specials"><Icon width="18" height="18" name="special" />Specials</a>
        <a class="flex gap-2 items-center text-green-400 font-bold hover:text-yellow-400" href="/contact"><Icon width="18" height="18" name="contact" />Contact</a>
        <a class="flex gap-2 items-center text-green-400 font-bold hover:text-yellow-400" href="/book"><Icon width="18" height="18" name="calendar" />Book Online</a>
      </div>
    </nav>
  </div>
</div>