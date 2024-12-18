<script>
  import { marked } from 'marked';
  export let data;
</script>

<div class="container mx-auto max-w-4xl p-6">
  <article class="prose lg:prose-xl">
    <h1 class="text-4xl font-bold mb-6">{data.title}</h1>
    <p class="text-gray-500 text-sm">Published on {data.date}</p>

    <div class="prose">
      {@html marked(data.content)}
    </div>
  </article>
</div>

<style>
  :global(.prose h2) {
    margin-top: 2rem;
    margin-bottom: 1rem;
    font-weight: bold;
  }
  :global(.prose p) {
    margin-bottom: 1rem;
  }
</style>