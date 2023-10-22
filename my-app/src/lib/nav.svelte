<script>
    import { createEventDispatcher} from 'svelte';

    const dispatch = createEventDispatcher();

    function hideNavigation() {
        dispatch('hide');
    }
</script>

<div class ="nav is-active" data-ref="nav">

    <div class="nav_background"></div>
    <div class="nav_inner">

        <ul class="nav_list">
            <li class="nav_item t-primary-heading">
                <a class="nav_link is-active" href="/" on:click={hideNavigation}>HOME</a>
            </li>
            <li class="nav_item t-primary-heading">
                <a class="nav_link is-active" href="/trivia" on:click={hideNavigation}>TRIVIA</a>
            </li>
            <li class="nav_item t-primary-heading">
                <a class="nav_link is-active" href="/character_guess" on:click={hideNavigation}>CHARACTER GUESS</a>
            </li>
            <li class="nav_item t-primary-heading">
                <a class="nav_link is-active" href="/episode_guess" on:click={hideNavigation}>EPISODE GUESS</a>
            </li>
        </ul>
    </div>

</div>

<style>

    .t-primary-heading{
        font-family: "Franklin Gothic Medium", "Arial Narrow", Arial, sans-serif;
        font-weight: 500;
        text-transform: uppercase;
    }

    .nav_list{
        list-style: none;
        display: flex;
        flex-direction: column;
    }

    .nav_link{
        display: flex;
    }

    .nav_list a{
        font-size: 6vw;
        text-decoration: none;
        color: green;
        letter-spacing: -0.03em;
    }
</style>