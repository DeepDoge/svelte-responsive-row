<script lang="ts">
    export let idealSize: string = "0px";
    export let maxWidth: string = null;
    export let gap: string = ".1em";
</script>

<div style="--ideal-size:{idealSize};--gap:{gap};{maxWidth !== null ? `--max-width:${maxWidth};` : ''}" class:withMaxWidth={maxWidth !== null}>
    <slot />
</div>

<style>
    div {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(min(var(--ideal-size), 100%), 1fr));
        gap: var(--gap);
        justify-items: center;
    }

    .withMaxWidth > :global(*) {
        max-width: var(--max-width);
    }
</style>
