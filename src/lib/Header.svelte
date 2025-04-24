<script>
  import { onMount } from 'svelte';
  import { fade, slide } from 'svelte/transition';
  
  let isMenuOpen = false;
  let scrollY = 0;
  let headerOpacity = 0.8;
  let headerDarkness = 80;
  
  const toggleMenu = () => isMenuOpen = !isMenuOpen;
  
  onMount(() => {
    const updateScroll = () => {
      scrollY = window.scrollY;
      // Increase opacity and darkness as user scrolls down
      headerOpacity = scrollY > 50 ? 0.9 : 0.8;
      headerDarkness = scrollY > 50 ? 90 : 80;
    };
    
    window.addEventListener('scroll', updateScroll);
    
    return () => {
      window.removeEventListener('scroll', updateScroll);
    };
  });
</script>

<header 
  class="fixed w-full top-0 z-50 transition-all duration-300 ease-in-out"
  style="background-color: rgba(0, 0, 0, {headerOpacity}); backdrop-filter: blur(8px);"
>
  <nav class="container mx-auto px-4 py-4">
    <div class="flex justify-between items-center">
      <a 
        href="/" 
        class="text-2xl font-bold text-white transition-all duration-300 hover:scale-105"
        style="font-family: 'Quicksand', sans-serif; font-weight: 700;"
      >
        KUCARO
      </a>
      
      <button 
        class="md:hidden text-white transition-transform duration-300 hover:scale-110 focus:outline-none" 
        on:click={toggleMenu}
        aria-label={isMenuOpen ? 'Close menu' : 'Open menu'}
      >
        <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          {#if isMenuOpen}
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"/>
          {:else}
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"/>
          {/if}
        </svg>
      </button>

      <div class="hidden md:flex space-x-8 justify-center">
        <a 
          href="#work" 
          class="text-white font-medium transition-all duration-300 hover:text-white hover:scale-110 relative after:absolute after:bottom-0 after:left-0 after:h-0.5 after:w-0 after:bg-white after:transition-all after:duration-300 hover:after:w-full"
          style="font-family: 'Quicksand', sans-serif; font-weight: 600;"
        >
          Work
        </a>
        <a 
          href="#services" 
          class="text-white font-medium transition-all duration-300 hover:text-white hover:scale-110 relative after:absolute after:bottom-0 after:left-0 after:h-0.5 after:w-0 after:bg-white after:transition-all after:duration-300 hover:after:w-full"
          style="font-family: 'Quicksand', sans-serif; font-weight: 600;"
        >
          Services
        </a>
        <a 
          href="#about" 
          class="text-white font-medium transition-all duration-300 hover:text-white hover:scale-110 relative after:absolute after:bottom-0 after:left-0 after:h-0.5 after:w-0 after:bg-white after:transition-all after:duration-300 hover:after:w-full"
          style="font-family: 'Quicksand', sans-serif; font-weight: 600;"
        >
          About
        </a>
        <a 
          href="#contact" 
          class="text-white font-medium transition-all duration-300 hover:text-white hover:scale-110 relative after:absolute after:bottom-0 after:left-0 after:h-0.5 after:w-0 after:bg-white after:transition-all after:duration-300 hover:after:w-full"
          style="font-family: 'Quicksand', sans-serif; font-weight: 600;"
        >
          Contact
        </a>
      </div>
    </div>

    {#if isMenuOpen}
      <div 
        class="fixed inset-0 bg-black/95 flex flex-col items-center justify-center z-50 md:hidden"
        transition:fade={{ duration: 300 }}
      >
        <button 
          class="absolute top-4 right-4 text-white transition-transform duration-300 hover:scale-110 focus:outline-none" 
          on:click={toggleMenu}
          aria-label="Close menu"
        >
          <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"/>
          </svg>
        </button>
        
        <div class="flex flex-col items-center space-y-8">
          <a 
            href="#work" 
            class="text-white text-xl font-medium transition-all duration-300 hover:scale-110"
            style="font-family: 'Quicksand', sans-serif; font-weight: 600;"
            on:click={toggleMenu}
            in:slide={{ delay: 100, duration: 300 }}
          >
            Work
          </a>
          <a 
            href="#services" 
            class="text-white text-xl font-medium transition-all duration-300 hover:scale-110"
            style="font-family: 'Quicksand', sans-serif; font-weight: 600;"
            on:click={toggleMenu}
            in:slide={{ delay: 150, duration: 300 }}
          >
            Services
          </a>
          <a 
            href="#about" 
            class="text-white text-xl font-medium transition-all duration-300 hover:scale-110"
            style="font-family: 'Quicksand', sans-serif; font-weight: 600;"
            on:click={toggleMenu}
            in:slide={{ delay: 200, duration: 300 }}
          >
            About
          </a>
          <a 
            href="#contact" 
            class="text-white text-xl font-medium transition-all duration-300 hover:scale-110"
            style="font-family: 'Quicksand', sans-serif; font-weight: 600;"
            on:click={toggleMenu}
            in:slide={{ delay: 250, duration: 300 }}
          >
            Contact
          </a>
        </div>
      </div>
    {/if}
  </nav>
</header>
