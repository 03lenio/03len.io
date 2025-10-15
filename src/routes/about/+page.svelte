<script lang="ts">
    import TopicHeader from "$lib/components/general/TopicHeader.svelte";
    import { onMount } from "svelte";

    // Ensure dark mode is applied before hydration
    if (typeof localStorage !== 'undefined') {
        const savedMode = localStorage.getItem('darkMode');
        if (savedMode === 'enabled') {
            document.documentElement.classList.add('dark');
        }
    }

    onMount(() => {
        // Optional: Reapply dark mode in case of dynamic changes
        const savedMode = localStorage.getItem('darkMode');
        if (savedMode === 'enabled') {
            document.documentElement.classList.add('dark');
        }
    });
</script>

<div class="relative h-screen bg-white dark:bg-black transition-colors duration-500">
    <TopicHeader topicName="ABOUT ME" />
</div>