<script>

  let projects = [
    {
      title: "copy.directory",
      description: "Find the right word for copywriting.",
      src: "/project1.png", 
      link: "https://www.copy.directory/",
    },
    {
      title: "elmirr.com",
      description: "The official branding page of professional football player.",
      src: "/project2.png",
      link: "https://elmirr.com/",
    },
    {
      title: "eldinrizvanovic.com",
      description: "Athlete's portfolio/personal brand website.",
      src: "/project3.png",
      link: "https://eldinrizvanovic.com/",
    }
  ];

  let upcomingProjects = [
    {
      title: "Word Chain Validator",
      description: "Validate word chains with ease.",
      src: "/word-chain-validator.png", 
      link: "https://ahasic.eu.pythonanywhere.com/",
    },
    {
  title: "NATO Phonetic Alphabet Trainer",
  description: "Learn and practice the NATO phonetic alphabet.",
  src: "/nato-phonetic-trainer.png",
  link: "/nato-phonetic-trainer",
},
  ];
</script>


<!-- About Section -->
<section class="bg-white text-black mb-36">
  <div class="max-w-6xl mx-auto px-6 text-center relative">
    <!-- Name and Subtitle -->
    <h1 class="name-text text-4xl md:text-8xl font-bold font-serif mb-2">Amar Hasic</h1>
    <div class="flex justify-center space-x-6 mb-4">
      <span class="text-gray-500 text-sm tracking-wider uppercase">Content Strategist</span>
      <span class="text-gray-500 text-sm tracking-wider uppercase">Web Dev</span>
    </div>
    <p class="my-description text-sm text-gray-800 md:text-2xl max-w-2xl mx-auto">
      Hi, I'm Amar Hasic, an engineer, developer, maker, and problem solver from Germany.
    </p>

    <!-- Horizontal Line and Icon -->
    <div class="absolute left-1/2 transform -translate-x-1/2 mt-8 flex items-center space-x-4">
      <!-- Horizontal Line -->
      <div class="h-0.5 bg-gray-300 w-96"></div>
      <!-- Blue Icon -->
      <div class="w-16 h-16 bg-blue-600 rounded-full flex items-center justify-center">
        <img src="/code.svg" alt="Icon" class="h-8 w-8" />
      </div>
      <!-- Horizontal Line -->
      <div class="h-0.5 bg-gray-300 w-24"></div>
    </div>
  </div>
</section>


<section class="bg-white text-black py-16 font-sans">
  <div class="max-w-6xl mx-auto px-6">
    <h2 class=" my-tech text-5xl md:text-7xl font-extrabold text-center mb-8">Technologies</h2>
    <img 
      src="/skills.svg" 
      alt="My technology skills and expertise" 
      class="w-full max-w-4xl mx-auto"
    />
  </div>
</section>


<!-- Featured Work Section -->
<section class="bg-[#000E3F] text-white">
  <!-- Header Section -->
  <div class="max-w-6xl mx-auto px-6 py-16">
    <h3 class="text-sm uppercase tracking-widest text-gray-400 mb-4">
      Passionately crafted experiences
    </h3>
    <h1 class="fewo text-5xl md:text-7xl font-extrabold -mb-8">Featured work</h1>
  </div>

  <!-- Projects Grid -->
  <div class="max-w-6xl mx-auto px-6 grid grid-cols-1 md:grid-cols-2 gap-8">
    {#each projects as project}
      <a
        href={project.link}
        target="_blank"
        rel="noopener noreferrer"
        class="block relative bg-gray-800 rounded-lg overflow-hidden shadow-lg group"
      >
        <img
          src={project.src}
          alt={project.title}
          class="w-full h-64 object-cover opacity-80 group-hover:opacity-100 transition-opacity duration-300"
        />
        <div
          class="absolute inset-0 bg-gradient-to-b from-transparent to-black opacity-90 group-hover:opacity-100 transition-opacity duration-300"
        ></div>
        <div class="absolute inset-0 p-6 flex flex-col justify-end">
          <h2 class="text-2xl font-bold mb-2 group-hover:text-white transition-colors duration-300">
            {project.title}
          </h2>
          <p class="text-sm text-gray-400">{project.description}</p>
        </div>
      </a>
    {/each}
  </div>
</section>


<!-- Labours of Love Section -->
<section class="bg-[#000E3F] text-white py-12">
  <div class="max-w-6xl mx-auto px-6">
    <h3 class="text-sm uppercase tracking-widest text-gray-400 mb-4">
      Labours of love
    </h3>
    <h1 class="exp-opso text-5xl md:text-7xl font-extrabold mb-8">Experiments & Open Source</h1>
  </div>

  <!-- Upcoming Projects Grid -->
  <div class="max-w-6xl mx-auto px-6 grid grid-cols-1 md:grid-cols-2 gap-8">
    {#each upcomingProjects as project}
      <a
        href={project.link}
        target="_blank"
        rel="noopener noreferrer"
        class="block relative bg-gray-700 rounded-lg overflow-hidden shadow-lg group"
      >
        <img
          src={project.src}
          alt={project.title}
          class="w-full h-64 object-cover opacity-80 group-hover:opacity-100 transition-opacity duration-300"
        />
        <div
          class="absolute inset-0 bg-gradient-to-b from-transparent to-black opacity-90 group-hover:opacity-100 transition-opacity duration-300"
        ></div>
        <div class="absolute inset-0 p-6 flex flex-col justify-end">
          <h2 class="text-2xl font-bold mb-2 group-hover:text-white transition-colors duration-300">
            {project.title}
          </h2>
          <p class="text-sm text-gray-400">{project.description}</p>
        </div>
      </a>
    {/each}
  </div>
</section>

<style>
  .name-text {
    font-family: 'Playfair Display', serif;
  }

  .my-description {
    font-family: 'Playfair Display', serif;
  }
  .my-tech, .fewo, .exp-opso {
    font-family: 'orbitron';
  }
</style>