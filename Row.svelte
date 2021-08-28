<script lang="ts">
    export let idealSize: string = "0px";
    export let maxWidth: string = "100%";
    export let gap: string = ".1em";
</script>

<div style="--ideal-size:{idealSize};--gap:{gap};--max-width:{maxWidth}">
    <slot />
</div>

<style>
    div {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(min(var(--ideal-size), 100%), 1fr));
        gap: var(--gap);
        justify-items: center;
    }

    div > :global(*) {
        max-width: var(--max-width);
    }
</style>
