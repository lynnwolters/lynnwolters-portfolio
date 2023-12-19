<script>
    import { onMount } from 'svelte'

    onMount(() => {
        const customCursorEl = document.querySelector('.custom-cursor')
        
        document.addEventListener('mousemove', customCursor)

        function customCursor({ clientX, clientY }) {
            customCursorEl.style.transform = `translate3d(calc(${clientX}px - 50%), calc(${clientY}px - 50%), 0)`
        }
    })
</script>

<div class="custom-cursor"></div>

<style>
    .custom-cursor {
        width: 3em;
        aspect-ratio: 1/1;

        position: fixed;
        top: 0;
        left: 0;
        transform: translate(-50%, -50%);
        z-index: 1000;

        pointer-events: none;

        background-image: url('images/cursor.svg');
        background-repeat: no-repeat;
        background-size: contain;
        background-position: center center;

        transition: all 400ms ease-out;
    }
</style>