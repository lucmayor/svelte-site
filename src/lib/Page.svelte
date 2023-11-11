<script>
    import { fade } from "svelte/transition";
</script>

<page transition:fade={{delay: 300, duration: 200}}>
    <slot />
</page>

<style>
    page {
        flex-basis: 60%;
        margin: 0%;
        width: 60%;
        padding: .25rem;
        border: 1px transparent;
        display: flex;
        flex-direction: column;
        min-height: 500px;
        /*align-items: centre; */
    }
</style>