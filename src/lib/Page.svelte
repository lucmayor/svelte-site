<script>
    import { fade } from "svelte/transition";
</script>

<page transition:fade={{delay: 300, duration: 200}}>
    <slot />
</page>

<style>
    page {
        color: white;
        padding: .25rem;
        border: 1px solid;
        border-radius: 5px;  
    }
</style>