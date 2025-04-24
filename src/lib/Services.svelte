<script lang="ts">
  type Service = {
    iconPath: string;
    title: string;
    description: string;
    features: string[];
    color: string;
    accentColor: string;
  };

  const services: Service[] = [
    {
      iconPath: "M7 4v16M17 4v16M3 8h4m10 0h4M3 12h18M3 16h4m10 0h4M4 20h16a1 1 0 001-1V5a1 1 0 00-1-1H4a1 1 0 00-1 1v14a1 1 0 001 1z",
      title: "Commercial Production",
      description: "High-impact video content that drives results for your brand",
      features: [
        "Brand storytelling",
        "Product launches",
        "TV commercials",
        "Social media ads",
        "Full production service"
      ],
      color: "from-purple-600 to-indigo-700",
      accentColor: "purple-400"
    },
    {
      iconPath: "M15 10l4.553-2.276A1 1 0 0121 8.618v6.764a1 1 0 01-1.447.894L15 14M5 18h8a2 2 0 002-2V8a2 2 0 00-2-2H5a2 2 0 00-2 2v8a2 2 0 002 2z",
      title: "Corporate Videos",
      description: "Professional corporate communications and training content",
      features: [
        "Company culture videos",
        "Training materials",
        "Event coverage",
        "Internal communications",
        "Recruitment videos"
      ],
      color: "from-blue-600 to-cyan-700",
      accentColor: "blue-400"
    },
    {
      iconPath: "M15 5v2m0 4v2m0 4v2M5 5a2 2 0 00-2 2v3a2 2 0 110 4v3a2 2 0 002 2h14a2 2 0 002-2v-3a2 2 0 110-4V7a2 2 0 00-2-2H5z",
      title: "Documentary",
      description: "Compelling storytelling that captures real-life narratives",
      features: [
        "Short documentaries",
        "Feature length films",
        "Behind-the-scenes",
        "Interview series",
        "Documentary series"
      ],
      color: "from-red-600 to-pink-700",
      accentColor: "red-400"
    },
    {
      iconPath: "M9 19V6l12-3v13M9 19c0 1.105-1.343 2-3 2s-3-.895-3-2 1.343-2 3-2 3 .895 3 2zm12-3c0 1.105-1.343 2-3 2s-3-.895-3-2 1.343-2 3-2 3 .895 3 2zM9 10l12-3",
      title: "Music & Entertainment",
      description: "Creative content for the entertainment industry",
      features: [
        "Music videos",
        "Live event coverage",
        "Concert filming",
        "Artist promotions",
        "Behind-the-scenes"
      ],
      color: "from-amber-500 to-orange-700",
      accentColor: "amber-400"
    }
  ];
</script>

<section id="services" class="py-20 bg-gradient-to-b from-zinc-900 to-black">
  <div class="container mx-auto px-4">
    <div class="text-center mb-16">
      <h2 class="text-3xl md:text-5xl font-bold text-white mb-4 relative inline-block">
        Our Services
        <span class="absolute -bottom-2 left-1/2 transform -translate-x-1/2 w-24 h-1 bg-gradient-to-r from-purple-500 to-pink-500"></span>
      </h2>
      <p class="text-gray-300 text-lg max-w-2xl mx-auto mt-6">
        Professional video production services tailored to your unique vision and goals
      </p>
    </div>

    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
      {#each services as service, i}
        <div class="relative overflow-hidden rounded-xl group">
          <!-- Background gradient -->
          <div class="absolute inset-0 bg-gradient-to-br {service.color} opacity-90 z-0"></div>
          
          <!-- Content -->
          <div class="relative z-10 p-8 h-full flex flex-col">
            <!-- Icon container -->
            <div class="mb-6 p-4 rounded-full bg-black bg-opacity-30 w-16 h-16 flex items-center justify-center">
              <svg class="w-8 h-8 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="{service.iconPath}" />
              </svg>
            </div>
            
            <h3 class="text-2xl font-bold text-white mb-3">{service.title}</h3>
            <p class="text-gray-100 mb-6 opacity-90">{service.description}</p>
            
            <div class="mt-auto">
              <ul class="space-y-3">
                {#each service.features as feature}
                  <li class="flex items-start text-white">
                    <svg class="w-5 h-5 mr-2 text-{service.accentColor} mt-0.5 flex-shrink-0" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z" />
                    </svg>
                    <span>{feature}</span>
                  </li>
                {/each}
              </ul>
            </div>
            
            <!-- Hover effect overlay -->
            <div class="absolute inset-0 bg-black opacity-0 group-hover:opacity-20 transition-opacity duration-300 z-0"></div>
          </div>
        </div>
      {/each}
    </div>

    <!-- Call to Action -->
    <div class="text-center mt-16">
      <a 
        href="#contact"
        class="inline-block bg-gradient-to-r from-purple-600 to-pink-600 text-white px-8 py-4 rounded-full font-medium shadow-lg hover:shadow-xl transform hover:-translate-y-1 transition-all duration-300"
      >
        Get a Free Quote
      </a>
    </div>
  </div>
</section>
