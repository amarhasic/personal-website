<script>
  const blogs = [
    {
      slug: 'storytelling-in-web-development',
      title: 'The Power of Storytelling in Web Development: Boosting Conversion and Crafting Better Products',
      description: 'Explore how storytelling transforms web development from mere functionality to captivating user experiences.',
    },
    {
    slug: 'impact-of-css-in-modern-web',
    title: 'The Impact of CSS on Modern Web Development',
    description: 'Dive into how CSS has revolutionized the way we design and build for the web, offering creative freedom and efficiency.',
  },
  ];
</script>

<div class="container mx-auto p-6">
  <h1 class="text-3xl font-bold mb-8 text-center">My Blog</h1>
  
  <div class="space-y-6">
    {#each blogs as blog}
      <div class="bg-white shadow-md rounded-lg p-6">
        <h2 class="text-2xl font-semibold mb-4">
          <a href={`/blog/${blog.slug}`} class="hover:text-blue-600">
            {blog.title}
          </a>
        </h2>
        <p class="text-gray-600 mb-4">{blog.description}</p>
        <a 
          href={`/blog/${blog.slug}`} 
          class="text-blue-500 hover:underline"
        >
          Read more
        </a>
      </div>
    {/each}
  </div>
</div>