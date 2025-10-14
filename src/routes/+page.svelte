<script lang="ts">
	import TitleComp from "$lib/components/TitleComp.svelte";
    import Topic from "$lib/components/Topic.svelte";
    import { onMount } from 'svelte';

    
    let titleComp: TitleComp;


    onMount(() => {
        const tooltip = titleComp.getTooltip();
        const savedMode = localStorage.getItem('darkMode');
        if (savedMode === 'enabled') {
            document.documentElement.classList.add('dark');
            tooltip.textContent = 'Go Light';
        }
    });
</script>


<div class="main-div h-screen place-content-center dark:bg-black transition-colors duration-500">
<div class="flex items-center justify-center">
    <TitleComp bind:this={titleComp} />  
</div>
<div class="flex flex-col items-center justify-center gap-2">
    <Topic topic="About Me" href="about"/>
    <Topic topic="Projects" href="projects" />
    <Topic topic="Socials" href="socials" />
  </div>
</div>
