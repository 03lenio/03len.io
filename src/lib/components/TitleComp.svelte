<script lang="ts">

    let tooltip: HTMLDivElement;
    
    export function getTooltip() {
        return tooltip;
    }

    function toggleDarkMode() {
        const isDarkMode = document.documentElement.classList.toggle('dark');
        if (isDarkMode) {
            tooltip.textContent = 'Go Light';
        } else {
            tooltip.textContent = 'Go Dark';
        }
        localStorage.setItem('darkMode', isDarkMode ? 'enabled' : 'disabled');
    }
    
    // Apply the saved theme on page load
   
</script>

<div class="title-container flex flex-col cursor-pointer mb-[6.5em] relative group">
    <!-- Outer stretched text -->
    <span class="font-outer text-[5em] font-times text-black dark:text-white scale-y-[2.7] leading-none block text-center">
    03LENIO
    </span>
    <!-- Inner normal text -->
    <span class="font-inner absolute inset-0 flex items-center justify-center text-[5em] font-arial text-black dark:text-white scale-[0.95,0.7] leading-none">
    03LENIO
    </span>
    <!-- Tooltip -->
    <div onclick={toggleDarkMode} bind:this={tooltip} class="tooltiptext absolute bottom-[-4em] text-black dark:text-white left-0 w-[5em] opacity-0 bg-transparent font-mono text-center p-[5px_0] rounded transition-opacity duration-300 ease-in-out z-[1] group-hover:opacity-100">
    Go Dark
    </div>
</div>