<script lang="ts">
  type Project = {
    id: number;
    title: string;
    category: string;
    thumbnail: string;
    videoUrl: string;
  };

  const projects: Project[] = [
    {
      id: 1,
      title: "Brand Story - Nike",
      category: "Commercial",
      thumbnail: "https://images.unsplash.com/photo-1542291026-7eec264c27ff",
      videoUrl: "https://example.com/video1"
    },
    {
      id: 2,
      title: "Mountain Documentary",
      category: "Documentary",
      thumbnail: "https://images.unsplash.com/photo-1464822759023-fed622ff2c3b",
      videoUrl: "https://example.com/video2"
    },
    {
      id: 3,
      title: "Wedding Highlights",
      category: "Event",
      thumbnail: "https://images.unsplash.com/photo-1519741497674-611481863552",
      videoUrl: "https://example.com/video3"
    },
    {
      id: 4,
      title: "Tech Startup Profile",
      category: "Corporate",
      thumbnail: "https://images.unsplash.com/photo-1504384764586-bb4cdc1707b0",
      videoUrl: "https://example.com/video4"
    },
    {
      id: 5,
      title: "Music Video - The Waves",
      category: "Music",
      thumbnail: "https://images.unsplash.com/photo-1511671782779-c97d3d27a1d4",
      videoUrl: "https://example.com/video5"
    },
    {
      id: 6,
      title: "Short Film - Echoes",
      category: "Film",
      thumbnail: "https://images.unsplash.com/photo-1536440136628-849c177e76a1",
      videoUrl: "https://example.com/video6"
    }
  ];

  const categories = ["All", ...new Set(projects.map(project => project.category))];
  let selectedCategory = "All";
  let hoveredProject: number | null = null;

  $: filteredProjects = selectedCategory === "All" 
    ? projects 
    : projects.filter(project => project.category === selectedCategory);
</script>

<section id="work" class="py-20 bg-black">
  <div class="container mx-auto px-4">
    <h2 class="text-3xl md:text-4xl font-bold text-white text-center mb-12">Our Work</h2>
    
    <!-- Category Filter -->
    <div class="flex flex-wrap justify-center gap-4 mb-12">
      {#each categories as category}
        <button
          class="px-6 py-2 rounded-full transition-colors {selectedCategory === category 
            ? 'bg-white text-black' 
            : 'text-white border border-white hover:bg-white/10'}"
          on:click={() => selectedCategory = category}
        >
          {category}
        </button>
      {/each}
    </div>

    <!-- Project Grid -->
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
      {#each filteredProjects as project}
        <div 
          class="relative aspect-video overflow-hidden rounded-lg cursor-pointer transform transition-transform hover:scale-105"
          on:mouseenter={() => hoveredProject = project.id}
          on:mouseleave={() => hoveredProject = null}
          role="button"
          tabindex="0"
          aria-label="View {project.title} project"
        >
          <img 
            src={project.thumbnail} 
            alt={project.title}
            class="w-full h-full object-cover"
          />
          <div 
            class="absolute inset-0 bg-black/70 flex items-center justify-center transition-opacity {hoveredProject === project.id ? 'opacity-100' : 'opacity-0'}"
          >
            <div class="text-center p-4">
              <h3 class="text-xl font-bold text-white mb-2">{project.title}</h3>
              <p class="text-gray-300 mb-4">{project.category}</p>
              <button 
                class="bg-white text-black px-6 py-2 rounded-full hover:bg-gray-200 transition-colors"
              >
                Watch Video
              </button>
            </div>
          </div>
        </div>
      {/each}
    </div>
  </div>
</section>
