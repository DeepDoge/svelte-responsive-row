<script lang="ts">
    export let idealSize: string = "0px";
    export let gap: string = '.1em';
</script>

<div style="--ideal-size:{idealSize};--gap:{gap}">
    <slot />
</div>

<style>
    div {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(min(var(--ideal-size), 100%), 1fr));
        gap: var(--gap);
    }
</style>