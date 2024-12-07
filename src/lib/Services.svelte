<script lang="ts">
  type Service = {
    icon: string;
    title: string;
    description: string;
    features: string[];
  };

  const services: Service[] = [
    {
      icon: "🎥",
      title: "Commercial Production",
      description: "High-impact video content that drives results for your brand",
      features: [
        "Brand storytelling",
        "Product launches",
        "TV commercials",
        "Social media ads",
        "Full production service"
      ]
    },
    {
      icon: "🎬",
      title: "Corporate Videos",
      description: "Professional corporate communications and training content",
      features: [
        "Company culture videos",
        "Training materials",
        "Event coverage",
        "Internal communications",
        "Recruitment videos"
      ]
    },
    {
      icon: "📽️",
      title: "Documentary",
      description: "Compelling storytelling that captures real-life narratives",
      features: [
        "Short documentaries",
        "Feature length films",
        "Behind-the-scenes",
        "Interview series",
        "Documentary series"
      ]
    },
    {
      icon: "🎵",
      title: "Music & Entertainment",
      description: "Creative content for the entertainment industry",
      features: [
        "Music videos",
        "Live event coverage",
        "Concert filming",
        "Artist promotions",
        "Behind-the-scenes"
      ]
    }
  ];
</script>

<section id="services" class="py-20 bg-zinc-900">
  <div class="container mx-auto px-4">
    <h2 class="text-3xl md:text-4xl font-bold text-white text-center mb-4">Our Services</h2>
    <p class="text-gray-400 text-center max-w-2xl mx-auto mb-12">
      Professional video production services tailored to your unique vision and goals
    </p>

    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
      {#each services as service}
        <div class="bg-black p-6 rounded-lg transform hover:scale-105 transition-transform">
          <div class="text-4xl mb-4">{service.icon}</div>
          <h3 class="text-xl font-bold text-white mb-3">{service.title}</h3>
          <p class="text-gray-400 mb-4">{service.description}</p>
          <ul class="space-y-2">
            {#each service.features as feature}
              <li class="flex items-center text-gray-300">
                <svg class="w-4 h-4 mr-2 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
                </svg>
                {feature}
              </li>
            {/each}
          </ul>
        </div>
      {/each}
    </div>

    <!-- Call to Action -->
    <div class="text-center mt-16">
      <a 
        href="#contact"
        class="inline-block bg-white text-black px-8 py-3 rounded-full hover:bg-gray-200 transition-colors"
      >
        Get a Quote
      </a>
    </div>
  </div>
</section>
