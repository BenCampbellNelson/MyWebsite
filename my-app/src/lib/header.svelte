<script>
    import { onMount } from 'svelte';
    import Nav from './nav.svelte'; 

    let isNavigationVisible = false;

    // Function to toggle the navigation visibility
    function toggleNavigation() {
        isNavigationVisible = !isNavigationVisible;
    }

    // Close the navigation when the component is mounted
    onMount(() => {
        isNavigationVisible = false;
    });

    function hideNavigation() {
        isNavigationVisible = false;
    }
</script>

<div class="header-container">
    <header class="header">
        <div class="header_inner">
            <button class="button button--menu" aria-label="Toggle navigation" on:click={toggleNavigation}>
                <span>Menu</span>
            </button>
        </div>
    </header>
    
    {#if isNavigationVisible}
        <Nav on:hide={hideNavigation}/>
    {/if}
</div>




