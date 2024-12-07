<script lang="ts">
  let videoPlaying = true;
  const toggleVideo = () => {
    videoPlaying = !videoPlaying;
    const video = document.getElementById("bgVideo");
    if (video instanceof HTMLVideoElement) {
      videoPlaying ? video.play() : video.pause();
    }
  };
</script>

<section class="relative h-screen w-full overflow-hidden">
  <!-- Video Background -->
  <div class="absolute inset-0 w-full h-full">
    <video
      id="bgVideo"
      class="object-cover w-full h-full"
      autoplay
      muted
      loop
      playsinline
    >
      <source src="src/assets/KucaroDemoWeb.mp4" type="video/mp4" />
      Your browser does not support the video tag.
    </video>
    <!-- Overlay -->
    <div class="absolute inset-0 bg-black/50"></div>
  </div>

  <!-- Content -->
  <div class="relative h-full flex items-center justify-center text-center">
    <div class="container mx-auto px-4">
      <h1 class="text-4xl md:text-6xl font-bold text-white mb-6">
        Crafting Visual Stories
      </h1>
      <p class="text-xl md:text-2xl text-gray-200 mb-8 max-w-2xl mx-auto">
        Premium video production services for brands that demand excellence
      </p>
      <div class="flex justify-center gap-4">
        <a
          href="#work"
          class="bg-white text-black px-8 py-3 rounded-full hover:bg-gray-200 transition-colors"
        >
          View Our Work
        </a>
        <button
          on:click={toggleVideo}
          class="border-2 border-white text-white px-8 py-3 rounded-full hover:bg-white/10 transition-colors"
        >
          {videoPlaying ? "Pause" : "Play"} Reel
        </button>
      </div>
    </div>
  </div>

  <!-- Scroll Indicator -->
  <div
    class="absolute bottom-8 left-1/2 transform -translate-x-1/2 animate-bounce"
  >
    <svg
      class="w-6 h-6 text-white"
      fill="none"
      stroke="currentColor"
      viewBox="0 0 24 24"
    >
      <path
        stroke-linecap="round"
        stroke-linejoin="round"
        stroke-width="2"
        d="M19 14l-7 7m0 0l-7-7m7 7V3"
      />
    </svg>
  </div>
</section>
