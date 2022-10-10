<svelte:head>
	<title>Simpson Research - Projects</title>
</svelte:head>

<script>
    import { onMount } from "svelte";
    import RepoCard from "./components/RepoCard.svelte";

    // Github Repo Data
    var researchRepos = [];
    var APCRepos = [];
    onMount(() => {
        fetch("https://api.github.com/users/Simpson-Computer-Technologies-Research/repos")
            .then(response => response.json())
            .then(json => {
                for (let i = 0; i < json.length; i++) {
                    var newMap = {
                        name: json[i].name,
                        description: json[i].description,
                        icon_url: json[i].owner.avatar_url,
                        redirect: json[i].html_url
                    }
                    if (json[i].name.includes("APC")) {
                        APCRepos = [newMap, ...APCRepos]
                    } else {
                        researchRepos = [...researchRepos, newMap]
                    }
                }
            })
            .catch(error => {
                console.log(error);
                return [];
            });
    });
</script>

<!-- Header -->
<a href="/" class="font-bold flex justify-center mb-2 mt-8 mx-2 text-4xl md:text-7xl hover:underline">
    Simpson Research
</a>

<!-- Main Github Repositories -->
<div class="flex justify-center items-center">
    <div>
        <h2 class="text-2xl font-bold flex justify-center mt-8">
            Github Repositories
        </h2>
        {#each researchRepos as data}
            <RepoCard title={data.name} description={data.description} image={data.icon_url} redirect={data.redirect}/>
        {/each}
    </div>
</div>

<!-- Advanced Programming Club Repositories -->
<div class="flex justify-center items-center">
    <div>
        <h2 class="text-2xl font-bold flex justify-center mt-6">
            Advanced Programming Club
        </h2>
        {#each APCRepos as data}
            <RepoCard title={data.name} description={data.description} image={data.icon_url} redirect={data.redirect}/>
        {/each}
    </div>
</div>

<!-- Bottom Footer-->
<div class="flex justify-center items-center mt-16 mb-4">
    <p class="text-base text-slate-600">Simpson Computer Technologies Research</p>
</div>