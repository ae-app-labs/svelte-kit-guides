<script>
import Title from "$lib/Title.svelte";
import '../styles/global.css'

</script>

<header>
    <Title title="Svelte Gaming Guides"/>
</header>

<main>
    <!-- page content -->
    <slot></slot>
</main>

<footer>
    <p>&copy; Copyright 2022 SvelteKit Gaming</p>
</footer>

<style>
    header {
        display: flex;
        justify-content: center;
    }
    main {
        max-width: 960px;
        margin: 20px auto;
    }
    footer {
        text-align: center;
    }
</style>