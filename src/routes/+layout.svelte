

<script>
    // No need for `export let data` unless you use it
	import "../app.css";
</script>

<header class="bg-transparent text-white px-12 py-6 flex flex-col md:grid md:grid-cols-3 md:items-center">
    <!-- Logo (Centered above on small screens, center column on desktop) -->
    <div class="flex justify-center md:col-start-2 md:row-start-1 mb-4 md:mb-0">
        <a href="/">
            <img
                src="/logo.png"
                alt="Amar Hasic Logo"
                class="h-13"
                style="height: calc(1.3 * 3.5rem);" 
            />
        </a>
    </div>

    <!-- Navigation Links (Left on desktop) -->
    <nav class="flex space-x-12 justify-center md:justify-start md:col-start-1">
        <a href="/highlights" class="text-lg font-semibold uppercase tracking-wide text-gray-800 hover:text-gray-600">Highlights</a>
        <a href="/blog" class="text-lg font-semibold uppercase tracking-wide text-gray-800 hover:text-gray-600">Blog</a>
    </nav>

    <!-- Empty Space (Right on desktop) -->
    <div class="hidden md:block md:col-start-3"></div>
</header>



<!-- Slot to render child content -->
<slot />

<footer class="bg-[#000E3F] text-white px-6 py-12">
    <!-- Footer Content Wrapper -->
    <div class="flex flex-col items-center space-y-6 md:space-y-0 md:flex-row md:justify-between">
        <!-- Contact Details -->
        <div class="text-center md:text-left">
            <h3 class="text-lg font-bold uppercase tracking-widest">Contact Me</h3>
            <p class="text-gray-400 mt-2">
                <a href="mailto:amar@hasic.dev" class="hover:text-gray-300">
                    amar@hasic.dev
                </a>
            </p>
        </div>

        <!-- Social Media Icons -->
        <div class="flex space-x-6">
            <!-- Twitter -->
            <a href="https://x.com/AmarHasik" target="_blank" aria-label="Twitter">
                <img src="/twitter.png" alt="Twitter" class="w-6 h-6 hover:opacity-80 transition" />
            </a>

            <!-- LinkedIn -->
            <a href="https://www.linkedin.com/in/amarhasic/" target="_blank" aria-label="LinkedIn">
                <img src="/linkedin.png" alt="LinkedIn" class="w-6 h-6 hover:opacity-80 transition" />
            </a>

            <!-- Product Hunt -->
            <a href="https://www.producthunt.com/@amarhasik" target="_blank" aria-label="Product Hunt">
                <img src="/producthunt.png" alt="Product Hunt" class="w-6 h-6 hover:opacity-80 transition" />
            </a>

            <!-- Blog -->
            <a href="/blog" aria-label="Blog">
                <img src="/blog.png" alt="Blog" class="w-6 h-6 hover:opacity-80 transition" />
            </a>

            <!-- CodePen -->
            <a href="https://codepen.io/Hasic" target="_blank" aria-label="CodePen">
                <img src="/codepen.png" alt="CodePen" class="w-6 h-6 hover:opacity-80 transition" />
            </a>

            <!-- GitHub -->
            <a href="https://github.com/amarhasic" target="_blank" aria-label="GitHub">
                <img src="/github.png" alt="GitHub" class="w-6 h-6 hover:opacity-80 transition" />
            </a>
        </div>

        <!-- Footer Links -->
        <div class="flex space-x-6 text-center md:text-left">
            <a href="/imprint" class="text-sm text-gray-500 hover:text-gray-400">Imprint</a>
            <a href="/data-protection" class="text-sm text-gray-500 hover:text-gray-400">Data Protection</a>
        </div>
    </div>
</footer>