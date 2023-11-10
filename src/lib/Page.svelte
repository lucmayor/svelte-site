<script>
    import { fade } from "svelte/transition";
</script>

<page transition:fade={{delay: 300, duration: 200}}>
    <slot />
    
</page>

<style>
    page {
        margin: auto;
        width: 80%;
        color: white;
        padding: .25rem;
        border: 1px solid;
        border-radius: 5px;
        display: flex;
        flex-direction: column;
        min-height: 500px;
        /*align-items: centre; */
    }

    page :global(p){

    }


</style>