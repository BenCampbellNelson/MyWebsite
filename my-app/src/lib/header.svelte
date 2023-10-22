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
</script>

<div class="background-image header-container">
    <header class="header">
        <div class="header_inner">
            <button class="button button--menu" data-ref="trigger" aria-label="Toggle navigation" on:click={toggleNavigation}>
                <span>Menu</span>
            </button>
        </div>
    </header>
    
    {#if isNavigationVisible}
        <Nav />
    {/if}
</div>

<style>
    .background-image {
		background-image: url('/images/RickInTheCorner.jpg');
		background-size: cover;
		background-repeat: no-repeat;
	}

    .header-container{
        width: 100%;
        height: 100vh;
    }

</style>

