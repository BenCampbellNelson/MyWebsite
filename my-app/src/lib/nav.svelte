<script>
	import { createEventDispatcher } from 'svelte';

	const dispatch = createEventDispatcher();

	function hideNavigation() {
		dispatch('hide');
	}
</script>

<div class="nav background-image is-active" data-ref="nav">
	<div class="nav_background" />
	<div class="nav_inner">
		<ul class="nav_list">
			<li class="nav_item t-primary-heading">
				<a class="nav_link is-active" href="/" on:click={hideNavigation}>HOME</a>
			</li>
			<li class="nav_item t-primary-heading">
				<a class="nav_link is-active" href="/trivia" on:click={hideNavigation}>TRIVIA</a>
			</li>
			<li class="nav_item t-primary-heading">
				<a class="nav_link is-active" href="/character_guess" on:click={hideNavigation}
					>CHARACTER GUESS</a
				>
			</li>
			<li class="nav_item t-primary-heading">
				<a class="nav_link is-active" href="/episode_guess" on:click={hideNavigation}
					>EPISODE GUESS</a
				>
			</li>
		</ul>
	</div>
</div>

<style>
	.nav {
		width: 100%;
		height: 100vh;
	}

	.background-image {
		background-image: url('/images/RickInTheCorner.jpg');
		background-size: cover;
		background-repeat: no-repeat;
		z-index: 2;
	}

	.t-primary-heading {
		font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
		font-weight: 500;
		text-transform: uppercase;

	}

	.nav_list {
		list-style: none;
		display: flex;
		flex-direction: column;
	}

	.nav_link {
		display: inline-block;
	}

	.nav_list a {
		font-size: 8vw;
		text-decoration: none;
		color: white;
		letter-spacing: -0.03em;
        transition: color 0.3s, transform 0.5s;
	}

    .nav_list a:hover {
		transform: scale(1.02);
        color: #00ff00;
	}

    @media (max-width: 1200px) {

    }
</style>
