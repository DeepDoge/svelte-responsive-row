<script lang="ts">
    export let type: "fit" | "fill" = "fill";
    export let idealSize: string = "0px";
    export let gap: string = ".5em";
    export let maxColumnCount: number = Number.MAX_SAFE_INTEGER;
    export let justifyItems: "center" | "start" | "end" | "stretch" = "center";
</script>

<div
    style:--ideal-size={idealSize}
    style:--gap={gap === "0" ? "0px" : gap}
    style:--type="auto-{type}"
    style:--max-column-count={maxColumnCount}
    style:--justify-items={justifyItems}
>
    <slot />
</div>

<style>
    div {
        display: grid;
        grid-template-columns: repeat(var(--type), minmax(min(max(100% / var(--max-column-count) - var(--gap), var(--ideal-size)), 100%), 1fr));
        gap: var(--gap);
        justify-items: var(--justify-items);
    }
</style>
