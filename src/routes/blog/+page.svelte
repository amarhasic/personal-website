<script>
  const blogs = [

  {
      slug: 'page-load-speed-impact',
      title: 'The Impact of Page Load Speed on SEO and Conversion Rates',
      description: 'Discover how page load speed affects SEO, user engagement, and conversions, and learn actionable strategies to optimize performance for better business outcomes.',
    },

    {
      slug: 'storytelling-in-web-development',
      title: 'The Power of Storytelling in Web Development: Boosting Conversion and Crafting Better Products',
      description: 'Discover how integrating storytelling into web development can engage users emotionally, drive conversions, and create memorable experiences.',
    },
    {
      slug: 'dark-patterns-vs-ethical-persuasion',
      title: 'Dark Patterns vs. Ethical Persuasion: Designing for Trust and Integrity',
      description: 'Learn the differences between deceptive dark patterns and ethical persuasion, and how to build trust with users through transparent design.',
    },
    {
      slug: 'psychology-behind-online-buying',
      title: 'The Psychology Behind Online Buying: Understanding Consumer Behavior',
      description: 'Uncover the psychological triggers that influence online purchases, and how businesses can leverage these insights ethically to boost sales.',
    },
    {
      slug: 'making-websites-succeed',
      title: 'Making Websites Succeed: The Customer-Centric Blueprint for Conversion',
      description: 'A step-by-step approach to optimizing websites with customer-centric strategies that improve user experience and maximize conversions.',
    },
    {
      slug: 'strategies-to-make-ux-work',
      title: 'Strategies to Make UX Work for You: A Practical Guide',
      description: '10 key strategies to create seamless, user-friendly experiences that drive satisfaction, conversions, and long-term business growth.',
    },

    {
  slug: 'copywriting-that-converts',
  title: 'Copywriting That Converts',
  description: 'Learn how to write clear, persuasive copy that connects with users, builds trust, and drives action to boost your conversions.'
   } 
    
  ];
</script>

<!-- Hero Section -->
<div class="bg-gradient-to-r from-[#000E3F] to-blue-700 text-white py-16 px-6 text-center">
  <h1 class="text-5xl md:text-6xl font-extrabold leading-tight">
    These thoughts of mine
  </h1>
  <p class="text-lg md:text-xl mt-4 opacity-90">
    I like to learn stuff and then write on those subjects with a new perspective via <a href="https://en.wikipedia.org/wiki/Conceptual_combination">conceptual combination</a> 
  </p>
</div>

<!-- Blog Cards Section -->
<div class="container mx-auto px-4 py-12">
  <div class="flex flex-col gap-8">
    {#each blogs as blog, i}
      <!-- Blog Card -->
      <div
        class="relative bg-gray-50 rounded-lg shadow-lg group overflow-hidden hover:shadow-2xl transition-shadow duration-300 w-full"
      >
        <!-- Decorative Border -->
        <div class="absolute top-0 left-0 w-full h-1 bg-gradient-to-r from-blue-600 to-[#000E3F]"></div>

        <div class="p-8 md:p-10 relative z-10">
          <!-- Blog Tag -->
          <div class="text-sm uppercase text-blue-600 font-semibold mb-4">
           
          </div>

          <!-- Blog Title -->
          <h2 class="text-3xl md:text-4xl font-extrabold text-gray-800 group-hover:text-blue-700 transition-colors duration-200">
            <a href={`/blog/${blog.slug}`} class="block">{blog.title}</a>
          </h2>

          <!-- Description -->
          <p class="text-gray-600 mt-4 text-lg md:text-xl line-clamp-3 group-hover:text-gray-800 transition-colors duration-200">
            {blog.description}
          </p>

          <!-- Read More -->
          <a
            href={`/blog/${blog.slug}`}
            class="inline-block mt-6 text-blue-600 font-semibold text-lg hover:underline"
          >
            Read more →
          </a>
        </div>

        <!-- Background Visual (Unique) -->
        <div
          class="absolute inset-0 opacity-20 group-hover:opacity-30 transition-opacity duration-300 bg-cover bg-center"
          style="background-image: url('https://source.unsplash.com/random/1600x900?tech,web&{i}');"
        ></div>
      </div>
    {/each}
  </div>
</div>

