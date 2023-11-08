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
			<li class="nav_item heading">
				<a class="nav_link is-active" href="/" on:click={hideNavigation}>HOME</a>
			</li>
			<li class="nav_item heading">
				<a class="nav_link is-active" href="/trivia" on:click={hideNavigation}>TRIVIA</a>
			</li>
			<li class="nav_item heading">
				<a class="nav_link is-active" href="/character_guess" on:click={hideNavigation}
					>CHARACTER GUESS</a
				>
			</li>
			<li class="nav_item heading">
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
        position: absolute;
        z-index: 2;
	}

	.heading {
		font-family: var(--main-font-family);
		font-weight: 500;
		text-transform: uppercase;

	}

	.nav_list {
		list-style: none;
		display: flex;
		flex-direction: column;
        margin: 0;
	}

	.nav_link {
		display: inline-block;
	}

	.nav_list a {
		font-size: 7.5vw;
		text-decoration: none;
		color: white;
		letter-spacing: -0.03em;
        transition: color 0.3s, transform 0.5s;
	}

    .nav_list a:hover {
		transform: scale(1.02);
        color: var(--secondary-colour);
	}

    @media (max-width: 1200px) {
        .background-image{
            background-size: contain;
        }
    }
</style>
