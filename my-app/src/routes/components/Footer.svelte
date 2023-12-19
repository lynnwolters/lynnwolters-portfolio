<script>
    import { onMount } from 'svelte'

    onMount(() => {
        const btn = document.querySelector('.button-animation-2')
        const bg = btn.querySelector('.bg-button-animation-2')

        const handleOrigin = (e) => {
            bg.style.left = `${e.pageX - btn.offsetLeft}px`
            bg.style.top = `${e.pageY - btn.offsetTop}px`
        }

        btn.addEventListener('mouseenter', handleOrigin)
        btn.addEventListener('mouseleave', handleOrigin);
    })
</script>

<footer>
    <h2>Want to make awesome things together? Send me an em<span>ail hi@lynnwolters.nl and I will contact a.s.a.p.!</span></h2>
    <button class="button-animation-2">
        <span class="label-button-animation-2">Go to top</span>
        <span class="bg-button-animation-2"></span>
    </button>
    <nav>
        <p>Copyright ©2023 Lynn Wolters</p>
        <ul>
            <li><a class="button-animation-1" href="#">LinkedIn</a></li>
            <li><a class="button-animation-1" href="#">Instagram</a></li>
            <li><a class="button-animation-1" href="#">Twitter</a></li>
        </ul>
    </nav>
</footer>

<style>
    footer {
        height: 75vh;

        display: grid;
        grid-template-columns: repeat(12, 1fr);
        grid-template-rows: repeat(3, 1fr);
        gap: 2.5em;

        margin: 2.5em 5em;
    }

    footer h2 {
        grid-column: span 7;
        grid-row: 2/3;

        font-family: var(--font-family-1);
        font-size: var(--font-size-2);
        font-weight: var(--font-weight-2);
        line-height: 100%;
        color: var(--color-1);
    }

    footer h2 span {
        opacity: .4;
    }

    footer button {
        grid-column: span 12;
        grid-row: 1/2;
        width: 10em;
        aspect-ratio: 1/1;

        justify-self: end;

        border: solid .025em var(--color-4);
        border-radius: 100%;

        background-color: transparent;

        font-family: var(--font-family-1);
        font-size: var(--font-size-4);
        font-weight: var(--font-weight-1);
        color: var(--color-1);
        text-transform: var(--text-transform-uppercase);
    }

    footer nav {
        grid-column: span 12;
        grid-row: 3/4;

        display: flex;
        justify-content: space-between;
        align-items: end;
    }

    footer nav p {
        font-family: var(--font-family-1);
        font-size: var(--font-size-4);
        color: var(--color-1);
        text-transform: var(--text-transform-uppercase);
        text-decoration: none;
    }

    footer nav ul {
        display: flex;
    }

    footer nav ul li {
        list-style: none;
    }

    footer nav ul li a {
        font-family: var(--font-family-1);
        font-size: var(--font-size-4);
        color: var(--color-1);
        text-transform: var(--text-transform-uppercase);
        text-decoration: none;
    }

    footer nav ul li:nth-of-type(1), footer nav ul li:nth-of-type(2) {
        margin: 0 1em;
    }

    footer nav ul li:nth-of-type(3) {
        margin-left: 1em;
    }

    @media (min-width: 1600px) {
        footer {
            margin: 3.5em 12em;
        }

        footer h2 {
            grid-column: span 6;
        }
    }

    @media (max-width: 1000px) {
        footer {
            margin: 2.5em 2.5em;
        }

        footer h2 {
            grid-column: span 9;
        }
    }

    @media (max-width: 650px) {
        footer {
            gap: 1.5em;

            margin: 1.5em 1.5em;
        }

        footer h2 {
            grid-column: span 10;
        }
    }
</style>