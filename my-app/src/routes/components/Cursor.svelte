<script>
    import { onMount } from 'svelte'

    onMount(() => {
        const cursor = document.querySelector('.custom-cursor');
        document.addEventListener('mousemove', function(e){
            var x = e.clientX;
            var y = e.clientY;
            cursor.style.transform = `translate3d(calc(${e.clientX}px - 50%), calc(${e.clientY}px - 50%), 0)`
        });
    })
</script>

<div class="custom-cursor">Click</div>

<style>
    .custom-cursor {
        width: 10em;
        aspect-ratio: 1/1;

        position: fixed;
        top: 0;
        left: 0;
        z-index: 1000;

        display: flex;
        justify-content: center;
        align-items: center;

        border-radius: 100%;

        background-color: var(--color-1);

        font-family: var(--font-family-1);
        font-size: var(--font-size-4);
        font-weight: var(--font-weight-1);
        color: var(--color-2);
        text-transform: var(--text-transform-uppercase);
    }
</style>