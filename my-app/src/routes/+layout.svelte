<script>

	import Footer from '../lib/footer.svelte';
    import Header from '../lib/header.svelte';

</script>

<Header />
<div class="backgroundImage"></div>
    <slot />
<Footer />

<style>
     .backgroundImage{
		background-image: url('/images/RickInTheCorner.jpg');
		background-size: cover;
		background-repeat: no-repeat;
        position: absolute;
        z-index: -12;
        width: 100vw;
        height: 100vh;
        background-attachment: fixed; /* Add this line */
	}
</style>