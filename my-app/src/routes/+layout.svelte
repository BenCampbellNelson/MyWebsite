<!--JAVASCRIPT-->
<script>
    import Footer from '../lib/footer.svelte';
    import Header from '../lib/header.svelte';
</script>

<!--HTML-->
<Header />
<div class="backgroundImage"></div>

    <slot />

<Footer />

<!--CSS-->
<style>
.backgroundImage {
    background-image: url('/images/RickInTheCorner.jpg');
    background-size: cover;
    background-repeat: no-repeat;
    background-attachment: fixed;
    position: fixed; 
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: -1; 
}

</style>