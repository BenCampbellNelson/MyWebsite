<!--JAVASCRIPT-->
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

<!--HTML-->
<div class="header-container">
	<header class="header">
		<div class="header_inner">
			<button
				class="button button--menu"
				aria-label="Toggle navigation"
				on:click={toggleNavigation}
			>
				<span>Menu +</span>
			</button>
		</div>
	</header>

	{#if isNavigationVisible}
		<Nav on:hide={hideNavigation} />
	{/if}
</div>


<!--CSS-->
<style>
	.header-container {
		position: relative;
	}

	.header_inner {
		background-color: var(--main-colour);
		padding: 20px;
	}
	.button {
		font-family: var(--main-font-family);
		font-weight: 500;
		text-transform: uppercase;
		background-color: var(--tertiary-colour);
		color: var(--tertiary-colour);
		padding: 15px 30px;
		border: none;
		border-radius: 50px;
		cursor: pointer;
		transition: background-color 0.3s, color 0.3s;
		box-shadow: 0px 3px 10px rgba(0, 0, 0, 0.2);
		font-size: 2em;
		color: black;
	}

	.button:hover {
		background: var(--secondary-colour);
		color: #fff;
		box-shadow: 0 0 5px var(--secondary-colour), 0 0 25px var(--secondary-colour),
			0 0 50px var(--secondary-colour), 0 0 100px var(--secondary-colour);
		transform: scale(1.1);
	}
</style>
