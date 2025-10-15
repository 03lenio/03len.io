<script lang="ts">
    export let topicName: string;

    function goBack() {
        history.back();
    }
</script>

<div class="text-center relative">
    <!-- Display the topic name -->
    <span class="text-[5em] font-arial text-white dark:text-black leading-none italic">
        {topicName}
    </span>
    <!-- Tooltip below the text -->
    <div 
        onclick={goBack} 
        class="mt-2 text-black dark:text-white bg-gray-200 dark:bg-gray-800 font-mono text-sm text-center p-2 rounded opacity-0 transition-opacity duration-300 ease-in-out hover:opacity-100 cursor-pointer"
    >
        Back
    </div>
</div>