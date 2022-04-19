<script>
    import { fly } from "svelte/transition";

    export let y = 200;
    export let duration = 500;
    /** @type {"forward"|"backward"} */
    export let direction = "forward";
    $: directionFactor = direction === "forward" ? 1 : -1;
</script>

<div
        class="route-wrapper"
        in:fly={{ y: y * directionFactor, duration }}
        out:fly={{ y: -y * directionFactor, duration }}
>
    <slot />
</div>

<style>
    .route-wrapper {
        position: absolute;
        top: 0;
        left: 0;
    }
</style>