<script>
    import { fade } from "svelte/transition";
</script>

<page transition:fade={{delay: 300, duration: 200}}>
    <slot />
</page>

<style>
    page {
        margin: 7px;
        width: 65%;
        color: white;
        padding: .25rem;
        border: 1px solid;
        border-radius: 5px;
        display: flex;
        flex-direction: column;
    }
</style>