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

    .header_inner{
        background-color: var(--main-colour);
        padding: 20px;
    }
    .button {
        font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
        font-weight: 500;
        text-transform: uppercase;
        background-color: white; /* Updated background color */
        color: #FFFFFF; /* Updated text color */
        padding: 15px 30px; /* Increased padding for a bigger button */
        border: none; /* Remove the button border */
        border-radius: 50px; /* Make the button circular */
        cursor: pointer; 
        transition: background-color 0.3s, color 0.3s; 
        box-shadow: 0px 3px 10px rgba(0, 0, 0, 0.2); 
        font-size: 2em;
        color: black;
    }

    .button:hover {
        background-color: var(--secondary-colour); /* Change background color on hover */
        transform: scale(1.1); /* Add a scaling effect on hover for fun */
    }
</style>




