<script>
    import { onMount } from 'svelte'

    onMount(() => {
        let openMobileMenu = document.querySelector('.open-mobile-menu')
        let closeMobileMenu = document.querySelector('.close-mobile-menu')

        openMobileMenu.addEventListener('click', toggleMenu)
        closeMobileMenu.addEventListener('click', toggleMenu)

        function toggleMenu() {
            console.log('click')
            let mobileMenu = document.querySelector('.open-menu')
            mobileMenu.classList.toggle('open')
        }
    })
</script>

<nav class="desktop-menu">
    <ul>
        <li><a href="#">Portfolio ©2023</a></li>
        <ul>
            <li><button>About</button></li>
            <li><button>Skills</button></li>
            <li><button>Experience</button></li>
            <li><button>Work</button></li>
        </ul>
        <li><button>Contact</button></li>
    </ul>
</nav>

<nav class="mobile-menu">
    <ul>
        <a href="#">Portfolio ©2023</a>
        <button class="open-mobile-menu">Menu</button>
        <ul class="open-menu">
            <button class="close-mobile-menu">Close</button>
            <li><a href="#">Link</a></li>
            <li><a href="#">Link</a></li>
            <li><a href="#">Link</a></li>
        </ul>
    </ul>
</nav>

<style>
    /* OUTER NAV */
    .desktop-menu {
        width: 100vw;
        height: 5em;

        position: fixed;
        z-index: 999;

        display: flex;
        justify-content: space-between;
        align-items: center;

        backdrop-filter: blur(8px);
    }

    /* INNER NAV */
    .desktop-menu > ul {
        width: 100%;
        height: 100%;

        display: flex;
        justify-content: space-between;
        align-items: center;

        margin: 0 5em;
        padding: 0 2.5em;

        border: solid .025em var(--color-1);
        border-radius: 1em;
    }

    /* LOGO */
    .desktop-menu > ul > li:nth-of-type(1) {
        list-style: none;
    }

    .desktop-menu > ul > li:nth-of-type(1) a {
        font-family: var(--font-family-1);
        font-size: var(--font-size-4);
        color: var(--color-1);
        text-transform: var(--text-transform-uppercase);
        text-decoration: none;
    }

    /* LINKS */
    .desktop-menu > ul > ul {
        display: flex;
    }

    .desktop-menu > ul > ul li {
        list-style: none;
    }

    .desktop-menu > ul > ul li button {
        margin: 0 1em;
        border: none;

        background-color: transparent;

        font-family: var(--font-family-1);
        font-size: var(--font-size-4);
        color: var(--color-1);
        text-transform: var(--text-transform-uppercase);
    }

    /* BUTTON */
    .desktop-menu > ul > li:nth-of-type(2) {
        list-style: none;
    }

    .desktop-menu > ul > li:nth-of-type(2) button {
        width: 8em;
        height: 3em;

        border: none;
        border-radius: .5em;

        background-color: var(--color-1);

        font-family: var(--font-family-1);
        font-size: var(--font-size-4);
        color: var(--color-2);
        text-transform: var(--text-transform-uppercase);
    }

    @media (min-width: 1600px) {
        .desktop-menu > ul{
            margin: 0 16em;
        }
    }

    @media (max-width: 1000px) {
        .desktop-menu > ul {
            margin: 0 2.5em;
        }
    }

    @media (max-width: 900px) {
        .desktop-menu > ul {
            height: 4em;
        }
    }

    @media (max-width: 650px) {
        .desktop-menu > ul {
            height: 3.5em;
        }

        .desktop-menu > ul {
            margin: 0 1.5em;
            padding: 0 1.5em;

            border-radius: .7em;
        }
    }

    @media (min-width: 480px) {
        .mobile-menu {
            display: none;
        }
    }

    @media (max-width: 480px) {
        .desktop-menu {
            display: none;
        }

        .mobile-menu {
            width: 100vw;
            height: 3.5em;

            position: fixed;
            z-index: 999;

            display: flex;
            justify-content: space-between;
            align-items: center;

            backdrop-filter: blur(8px);
        }

        .mobile-menu > ul {
            width: 100%;
            height: 100%;

            display: flex;
            justify-content: space-between;
            align-items: center;

            margin: 0 1.5em;
            padding: 0 1.5em;

            border: solid .025em var(--color-1);
            border-radius: .5em;
        }

        .mobile-menu > ul > a {
            font-family: var(--font-family-1);
            font-size: var(--font-size-4);
            color: var(--color-1);
            text-transform: var(--text-transform-uppercase);
            text-decoration: none;
        }

        .mobile-menu > ul > button {
            width: 8em;
            height: 3em;

            border: none;
            border-radius: .5em;

            background-color: var(--color-1);

            font-family: var(--font-family-1);
            font-size: var(--font-size-4);
            color: var(--color-2);
            text-transform: var(--text-transform-uppercase);
        }

        .open-menu {
            width: 100vw;
            height: 50vh;

            position: fixed;
            top: 0;
            left: 0;
            bottom: 0;
            right: 0;

            transform: translateX(-100%);
            transition: 1s ease-in-out;

            background-color: red;

            z-index: 1000;
        }

        .open-menu button {
            width: 8em;
            height: 3em;

            border: none;
            border-radius: .5em;

            background-color: var(--color-1);

            font-family: var(--font-family-1);
            font-size: var(--font-size-4);
            color: var(--color-2);
            text-transform: var(--text-transform-uppercase);
        }

        .open-menu li {
            list-style: none;
        }

        .open-menu li a {
            font-family: var(--font-family-1);
            font-size: var(--font-size-2);
            color: var(--color-1);
            text-transform: var(--text-transform-uppercase);
            text-decoration: none;
        }

        .open-menu.open {
            transform: translateX(75%);
            transition: 1s ease-in-out;
        }
    }
</style>