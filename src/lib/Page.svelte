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
        padding: .4rem;
        border: 1px transparent;
        display: flex;
        flex-direction: column;
        min-height: 500px;
        /*align-items: centre; */
    }

    page :global(h1) {
        font-family: "Redaction";
        text-align: left;
        font-size: 20px;
    }

    page :global(h2) {
        font-family: "Redaction 35";
        text-align: right;
        font-size: 20px;
    }

    page :global(p) {
        text-align: left;
    }

    page :global(.p2) {
        text-align: right;
    }
</style>