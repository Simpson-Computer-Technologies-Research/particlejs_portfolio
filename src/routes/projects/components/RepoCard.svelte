<script>
    export let title;
    export let description;
    export let image;
    export let redirect;
</script>

<a href={redirect} target="_blank">
    <div class="bg-white px-3 py-3 mt-6 mb-6 rounded-xl h-26 w-[300px] sm:w-[500px] md:w-[700px] lg:w-[1000px] duration-500 ease-in-out shadow-lg hover:tracking-wide pr-12 focus:bg-black hover:bg-slate-50">
        <div class="flex items-center">
        
            <!-- Repo Image -->
            <img class="rounded-full bg-white bg-opacity-0 h-10 w-10 outline-slate-900 outline-3 outline ml-2 mt-2" alt="" src={image}>
    
            <!-- Repo Title and Description -->
            <div class="flex-col mx-4">
                <h4 class="text-slate-900 font-bold text-left text-lg">{title}</h4>
                <p class="text-slate-400 cursor-pointer">{description}</p> 
            </div>
        </div>
    </div>
</a>
