<svelte:head>
	<title>Simpson Research</title>
</svelte:head>

<script>
    import Particles from "svelte-particles";
    import { loadFull } from "tsparticles";
    import * as particleData from '$lib/particles.json'
</script>

<!-- Header -->
<h1 class="font-bold flex justify-center mb-8 mx-2 mt-8 text-4xl md:text-7xl text-white ease-in-out">
    Simpson Research
</h1>

<!-- Description -->
<div class="flex justify-center items-center mb-6 mx-2 text-xs md:text-base ease-in-out">
    <p class="text-slate-300">Computer Technologies Research by <mark class="text-violet-500" style="background: none;">Tristan Simpson</mark></p>
</div>

<!-- See Projects Button -->
<div class="justify-center items-center flex mx-2">
    <button 
        on:click={() => window.location.href="/particlejs_portfolio/projects"}
        class="bg-white text-center font-semibold rounded h-10 w-44 hover:bg-violet-700 hover:text-white focus:bg-violet-500 hover:tracking-wide duration-500 ease-in-out">
        See Projects
    </button>
</div>

<!-- Particles.js -->
<Particles
    options={particleData}
    particlesInit={(e) => loadFull(e)}
/>
