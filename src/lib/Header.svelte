<script>
  let isMenuOpen = false;
  const toggleMenu = () => isMenuOpen = !isMenuOpen;
</script>

<header class="fixed w-full top-0 z-50 bg-black/80 backdrop-blur-sm">
  <nav class="container mx-auto px-4 py-4">
    <div class="flex justify-between items-center">
      <a href="/" class="text-2xl font-bold text-white">KUCARO</a>
      
      <button class="md:hidden text-white" on:click={toggleMenu}>
        <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          {#if isMenuOpen}
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"/>
          {:else}
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"/>
          {/if}
        </svg>
      </button>

      <div class="hidden md:flex space-x-8">
        <a href="#work" class="text-white hover:text-gray-300">Work</a>
        <a href="#services" class="text-white hover:text-gray-300">Services</a>
        <a href="#about" class="text-white hover:text-gray-300">About</a>
        <a href="#contact" class="text-white hover:text-gray-300">Contact</a>
      </div>
    </div>

    {#if isMenuOpen}
      <div class="md:hidden mt-4 space-y-4">
        <a href="#work" class="block text-white hover:text-gray-300">Work</a>
        <a href="#services" class="block text-white hover:text-gray-300">Services</a>
        <a href="#about" class="block text-white hover:text-gray-300">About</a>
        <a href="#contact" class="block text-white hover:text-gray-300">Contact</a>
      </div>
    {/if}
  </nav>
</header>
