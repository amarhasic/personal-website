<script>
    let title = "Conversion-Focused Developer";
    let description = `
        Hi, I’m Amar Hasic. I’ve been building websites for over a decade, turning a passion for creativity and technology into a career. I focus on crafting solutions that deliver results — whether through intuitive front-end design or customer-focused, conversion-driven experiences.
        I work with tools like HTML/CSS, JavaScript, Svelte, Tailwind, Bootstrap, and content management systems, blending technical skills with creative problem-solving to create impactful digital experiences.
        When I’m not coding, I’m often flying my drone in places I should or shouldn't be.


    `;
</script>

<div
    class="relative bg-cover bg-center min-h-screen flex flex-col items-center justify-center px-6 md:px-20 md:flex-row md:justify-between "
    style="background-image: url('/background.svg');"
>
    <!-- Text Section (Stacked on mobile, side-by-side on larger screens) -->
    <div class="flex flex-col items-center md:flex-row md:justify-between w-full">
        <!-- Text Section -->
        <section class=" w-full md:w-1/2 space-y-6 text-black text-center md:text-left mb-6 md:mb-0">
            <h1 class="animate-text bg-gradient-to-r from-blue-500 via-blue-800 to-blue-600 bg-clip-text text-transparent text-3xl font-black md:text-7xl font-bold uppercase leading-tight">
                {title}
            </h1>
            <p class="font-mono font-medium text-lg md:text-xl text-gray-700">
                {description}
            </p>
        </section>

        <!-- Image Section -->
        <div class="brightness-125 w-full md:w-1/3 flex justify-center">
            <img
                src="/profile-photo.png" 
                alt="Portrait of Amar Hasic"
                class="w-48 sm:w-64 md:w-72 lg:w-80 rounded-lg"
            />
        </div>
    </div>
</div>






