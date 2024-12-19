<script>
    // 1. Imports first
    import { fade, slide } from 'svelte/transition';


    // 2. Component props and state
    let title = "Conversion-Focused Developer";
    let description = `
        Hi, I'm Amar Hasic. I've been building websites for over a decade, turning a passion for creativity and technology into a career. I focus on crafting solutions that deliver results — whether through intuitive front-end design or customer-focused, conversion-driven experiences.
        I work with tools like HTML/CSS, JavaScript, Svelte, Tailwind, Bootstrap, and content management systems, blending technical skills with creative problem-solving to create impactful digital experiences.
        When I'm not coding, I'm often flying my drone in places I should or shouldn't be.
    `;

    // 3. Fortune cookie functionality
    let showFortune = false;
    let currentFortune = '';
    
    const fortunes = [
"A tiny tweak in your button text can turn a hesitant visitor into a confident clicker.",
"A short, snappy headline is like a beacon that guides your user’s eyes right where they need to go.",
"A gentle prompt in your search bar can whisper, ‘Try typing what you really want.’",
"A sprinkle of friendly language on your signup form can ease the tension of sharing details.",
"A simple phrase near your pricing tables can nudge shoppers toward choosing their best fit.",
"A hint of reassurance in your password field—like ‘We never share your secrets’—can build trust.",
"A well-placed 'Need help?' link can feel like an outstretched hand in a tricky moment.",
"A playful twist on your 404 error can soften the blow when visitors hit a dead end.",
"A little note under a download button can whisper, ‘No worries, it’s safe here.’",
"A tiny reminder on your checkout page can politely say, ‘Just a few clicks left, you got this.’",
"A splash of personality in your newsletter invite can feel like a friendly knock on the door.",
"A gentle nudge beside a login field can say, ‘Forgot something? That’s okay, we’ll help you reset.’",
"A kind suggestion on your contact page can encourage visitors to say hello without hesitation.",
"A calm note on loading screens can reassure, ‘Good things take a moment—hang tight!’",
"A small wink in your call-to-action can make that next step feel like an exciting invitation.",
"A tiny breadcrumb label can show users they’re on the right path, not lost in the woods.",
"A helpful tip hovering over a form field can do the quiet guiding your users didn’t know they needed.",
"A playful thank-you message after a purchase can leave customers feeling valued and seen.",
"A subtle change in button color can nudge a visitor to notice what really matters.",
"A quick hint in your signup form—‘No spam, just updates!’—can put anxious minds at ease.",
"A well-chosen icon next to your call-to-action can help users spot what’s next at a glance.",
"A friendly confirmation message can pat your user on the back for taking that step.",
"A touch of humor in your error prompts can turn minor mishaps into mild amusements.",
"A quiet note under a pricing option can whisper, ‘This plan’s our most popular pick.’",
"A short sentence under your hero headline can point visitors directly toward the good stuff.",
"A reassuring line on your signup page—‘We’ll be quick and painless’—can calm reluctant joiners.",
"A small suggestion on your blog—‘Check out this related post’—can spark further curiosity.",
"A welcoming phrase on your homepage can feel like opening the door to a cozy shop.",
"A gentle reminder after a user hovers can say, ‘Go ahead, give it a click!’",
"A kind note at checkout—‘You’re almost done, just confirm below’—keeps the momentum going.",
"A hint near a video preview—‘Click to peek inside’—can get visitors to press play.",
"A polite prompt in your review form—‘Tell us what you really think’—can invite honest feedback.",
"A subtle nudge near your newsletter box—‘We’ll only send the good stuff’—can help seal the deal.",
"A lighthearted line near product images can say, ‘Zoom in, don’t be shy!’",
"A short message in your navigation menu can whisper, ‘Pick a path and explore.’",
"A calming phrase on a busy page—‘Take your time, we’ll wait here’—can ease decision-making.",
"A friendly wink in tooltips—‘Hover to learn a secret’—can turn features into discoveries.",
"A soft hint beside social icons can say, ‘Follow along to stay in the loop.’",
"A dash of warmth in your signup confirmation—‘Welcome aboard!’—can make users feel at home.",
"A gentle push near your FAQ link—‘Got questions? We’ve got answers’—can encourage exploration.",
"A playful cue on a filter button—‘Sort it your way’—can put control in the user’s hands.",
"A nudge in your footer—‘Still curious? Explore more below’—can keep visitors engaged.",
"A note on your testimonial slider—‘Swipe for more happy stories’—can entice further reading.",
"A casual prompt in your chat widget—‘Need a hint? Just ask!’—can break the ice.",
"A simple reminder near forms—‘Short and sweet works best here’—can streamline input.",
"A cheerful line on your order confirmation—‘Congrats! You made a great pick’—can affirm choices.",
"A subtle heads-up near a trial signup—‘Cancel anytime, stress-free’—can calm doubts.",
"A gentle whisper near a complex feature—‘Take a peek, we’ll guide you through’—can invite discovery.",
"A well-placed suggestion at the end of a page—‘Ready to take the next step?’—can prompt action.",
"A friendly post-purchase note—‘We’ll see you again soon!’—can plant the seed for a return visit."
    ];
    
    // 4. Functions
    function getRandomFortune() {
        const randomIndex = Math.floor(Math.random() * fortunes.length);
        currentFortune = fortunes[randomIndex];
        showFortune = true;
    }
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


<div class="bg-white py-12">
    <div class="max-w-4xl mx-auto px-6">
        <div class="cookie-container text-center">
            {#if !showFortune}
                <div class="cookie-closed" on:click={getRandomFortune}>
                    <img 
                        src="/cookie-closed.svg" 
                        alt="Fortune Cookie" 
                        class="w-48 h-48 mx-auto cursor-pointer hover:scale-105 transition-transform"
                    />
                    <p class="fortune-text mt-4 text-xl md:text-3xl font-medium text-[#000E3F] underline decoration-gray-900/30">
                        Curious? Pop this cookie open for a tiny bit of insight about content and design.

                    </p>
                </div>
            {:else}
                <div class="cookie-open">
                    <div class="cookie-animation">
                        <img 
                            src="/cookie-open.svg" 
                            alt="Opened Fortune Cookie" 
                            class="w-48 h-48 mx-auto split-animation"
                        />
                    </div>
                    <div class="fortune-paper" transition:slide={{duration: 600}}>
                        <p class="text-xl md:text-3xl font-medium text-gray-800 italic">"{currentFortune}"</p>
                    </div>
                </div>
            {/if}
        </div>
    </div>
</div>

<style>


    .fortune-text {
        font-family: 'Oregano', cursive;
    }


    .cookie-container {
        perspective: 1000px;
    }
    
    .cookie-animation {
        transform-style: preserve-3d;
    }
    
    .split-animation {
        animation: splitCookie 0.6s ease-out;
    }
    
 
    @keyframes splitCookie {
        0% { transform: rotateX(0deg); }
        50% { transform: rotateX(-45deg); }
        100% { transform: rotateX(0deg); }

        .fortune-paper {
        background: linear-gradient(45deg, #fffdf9, #fff9f2);
        padding: 1.5rem 2rem;
        border-radius: 2px;
        position: relative;
        max-width: 280px;
        margin: -1rem auto 0;
        transform: rotate(-1deg);
        box-shadow: 
            0 1px 1px rgba(0,0,0,0.15),
            inset 0 0 1px rgba(255,255,255,0.8);
        border: 1px solid rgba(210, 180, 140, 0.3);
    }

    .fortune-paper::before {
        content: '';
        position: absolute;
        left: 0;
        top: 0;
        width: 100%;
        height: 100%;
        background: url("data:image/svg+xml,%3Csvg viewBox='0 0 100 100' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.8' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100' height='100' filter='url(%23noise)' opacity='0.05'/%3E%3C/svg%3E");
        opacity: 0.3;
        pointer-events: none;
    }

    .fortune-paper p {
        font-family: 'Courier New', monospace;
        font-size: 0.95rem;
        line-height: 1.6;
        color: #594838;
        text-align: center;
        position: relative;
        text-shadow: 1px 1px 0 rgba(255,255,255,0.5);
    }

    .fortune-paper::after {
        content: '';
        position: absolute;
        left: 50%;
        top: 0;
        width: 1px;
        height: 100%;
        background: linear-gradient(
            to bottom,
            transparent,
            rgba(0,0,0,0.05) 20%,
            rgba(0,0,0,0.05) 80%,
            transparent
        );
    }

    @keyframes paperFloat {
        0%, 100% { transform: rotate(-1deg) translateY(0); }
        50% { transform: rotate(-1deg) translateY(-2px); }
    }

    .fortune-paper {
        animation: paperFloat 3s ease-in-out infinite;
    }

        
    }
</style>