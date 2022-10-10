<svelte:head>
	<title>Simpson Research</title>
</svelte:head>

<script>
    import Particles from "svelte-particles";
    import { loadFull } from "tsparticles";
    import * as particleData from '$lib/particles.json'
</script>

<h1 class="font-bold flex justify-center mb-8 mt-8 text-5xl md:text-7xl text-white ease-in-out">
    Simpson Research
</h1>

<div class="flex justify-center items-center mb-6">
    <p class="text-xs md:text-base text-slate-300 ease-in-out">Simpson Computer Technologies Research by&nbsp;</p>
    <p class="text-xs md:text-base text-violet-500 ease-in-out">Tristan Simpson</p>
</div>

<div class="justify-center items-center flex">
    <button 
        on:click={() => window.location.href="/projects"}
        class="bg-white text-center font-semibold rounded h-10 w-44 hover:bg-violet-700 hover:text-white focus:bg-indigo-500 hover:tracking-wide duration-500 ease-in-out">
        See Projects
    </button>
</div>


<Particles
    id="tsparticles"
    options={particleData}
    particlesInit={(e) => loadFull(e)}
/>
