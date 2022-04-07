<script lang="ts">
    export let type: "fit" | "fill" = "fill";
    export let idealSize: string = "0px";
    export let gap: string = ".1em";
    export let maxColumnCount: number = Number.MAX_SAFE_INTEGER;
    export let justifyItems: 'center' | 'start' | 'end' |'stretch' = 'center'
</script>

<div style="--ideal-size:{idealSize};--gap:{gap};--type:auto-{type};--max-column-count:{maxColumnCount};--justify-items:{justifyItems}">
    <slot />
</div>

<style>
    div {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(min(max(100% / var(--max-column-count) - var(--gap) / 1.5, var(--ideal-size)), 100%), 1fr));
        gap: var(--gap);
        justify-items: var(--justify-items);
    }
</style>
