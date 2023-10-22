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
                <span>Menu +</span>
            </button>
        </div>
    </header>
    
    {#if isNavigationVisible}
        <Nav on:hide={hideNavigation}/>
    {/if}
</div>

<style>
    .header-container {
        position: relative;
    }

    .button {
        font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
        font-weight: 500;
        text-transform: uppercase;
        background-color: #000; /* Background color */
        color: #00ff00; /* Text color */
        padding: 10px 20px; /* Padding for the button */
        border: none; /* Remove the button border */
        border-radius: 5px; /* Add some rounded corners */
        cursor: pointer; /* Show a pointer cursor on hover */
        transition: background-color 0.3s, color 0.3s; /* Add a smooth transition effect */
    }

    .button:hover {
        background-color: #00ff00; /* Change background color on hover */
        color: #000; /* Change text color on hover */
    }
</style>




