<script>
    export let baseImage
    export let overlayTop = '38%'
    export let overlayShiftX = '0%'
    export let overlayImageSize = '30%'
    export let baseImageSize = '100%'
    export let maxWidth = '100%'
</script>

<div class="overlay-card" {...$$restProps} style="
    --overlay-top: {overlayTop}; 
    --overlay-shift-x: {overlayShiftX}; 
    --overlay-image-size: {overlayImageSize}; 
    --base-image-size: {baseImageSize};
    --max-width: {maxWidth}; ">

    <img class="base" src={baseImage} alt="" aria-hidden="true" />
    <div class="overlay-content">
        <slot />
    </div>
</div>

<style>
    .overlay-card {
        width: clamp(240px, 40vw, 800px);
        max-width: var(--max-width);
        position: relative;
        display: block; 
    }

    .base {
        width: var(--base-image-size); 
        display: block; 
        height: auto; 
        margin: 0 auto;
    }

    .overlay-content {
        position: absolute;
        top: var(--overlay-top); 
        left: var(--overlay-shift-x); 
        width: 100%; 
        height: calc(100% - var(--overlay-top)); 
        
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 8px;
        pointer-events: auto;
        text-align: center;
        justify-content: flex-start; 
    }

    .overlay-content :global(img) {
        width: var(--overlay-image-size); 
        height: auto;
        border-radius: 10px; 
        display: block; 
        margin: 0 auto; 
        transition: transform 250ms ease; 
    }

    .overlay-content :global(img):hover {
        transform: scale(1.15) rotate(-5deg); 
    }
</style>