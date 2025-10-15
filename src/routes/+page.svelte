<script lang="ts">
	import TitleComp from "$lib/components/main/TitleComp.svelte";
    import Topic from "$lib/components/main/Topic.svelte";
    import Footer from "$lib/components/main/Footer.svelte";
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

<div class="relative h-screen bg-white dark:bg-black transition-colors duration-500">

    <div class="absolute inset-0 flex flex-col items-center justify-center gap-4">
      <div class="flex items-center justify-center">
        <TitleComp bind:this={titleComp} />  
      </div>
  
      <div class="flex flex-col items-center justify-center gap-2">
        <Topic topic="About Me" href="about" />
        <Topic topic="Projects" href="projects" />
        <Topic topic="Socials" href="socials" />
      </div>
    </div>
  
    <div class="absolute bottom-0 left-0 w-full flex justify-center p-2">
      <Footer />
    </div>
  </div>
  