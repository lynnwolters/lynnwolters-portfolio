<script>
    let isMobileMenuOpen = false

    function toggleMobileMenu() {
        isMobileMenuOpen = !isMobileMenuOpen
    }
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
        <li><a href="#">Portfolio ©2023</a></li>
        <li><button on:click={toggleMobileMenu}>Menu</button></li>
    </ul>

    {#if isMobileMenuOpen}
        <ul>
            <li><a href="#">About</a></li>
            <li><a href="#">Skills</a></li>
            <li><a href="#">Experience</a></li>
            <li><a href="#">Work</a></li>
            <li><a href="#">Contact</a></li>
        </ul>
    {/if}  

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

    @media (min-width: 481px) {
        .mobile-menu {
            display: none;
        }
    }

    @media (max-width: 480px) {
        .desktop-menu {
            display: none;
        }

        .mobile-menu {
            width: calc(100vw - 6em);

            position: fixed;
        }

        .mobile-menu ul:nth-of-type(1) {
            width: 100%;
            height: 3.5em;

            z-index: 999;

            display: flex;
            justify-content: space-between;
            align-items: center;

            margin: 0 1.5em;
            padding: 0 1.5em;

            border: solid .025em var(--color-1);
            border-radius: .7em;

            backdrop-filter: blur(8px);
        }

        .mobile-menu ul:nth-of-type(1) li {
            display: flex;
            align-items: center;

            list-style: none;
        }

        .mobile-menu ul:nth-of-type(1) li a {
            font-family: var(--font-family-1);
            font-size: var(--font-size-4);
            color: var(--color-1);
            text-transform: var(--text-transform-uppercase);
            text-decoration: none;
        }

        .mobile-menu ul:nth-of-type(1) li button {
            width: 8em;
            height: 3em;

            border: none;
            border-radius: .5em;

            background-color: var(--color-1);

            font-family: var(--font-family-1);
            font-size: var(--font-size-4);
            color: var(--color-2);
            text-transform: var(--text-transform-uppercase);
            text-decoration: none;
        }

        .mobile-menu ul:nth-of-type(2) {
            width: 100%;
            height: fit-content;

            z-index: 998;

            display: flex;
            flex-direction: column;

            margin: 0 1.5em;
            margin-top: .5em;
            padding: 1.5em 1.5em;

            border: solid .025em var(--color-1);
            border-radius: .7em;

            backdrop-filter: blur(8px);
        }

        .mobile-menu ul:nth-of-type(2) li {
            margin: .2em 0;

            list-style: none;
        }

        .mobile-menu ul:nth-of-type(2) li a {
            font-family: var(--font-family-1);
            font-size: var(--font-size-2);
            font-weight: var(--font-weight-2);
            line-height: 100%;
            color: var(--color-1);
            text-decoration: none;
        }
    }
</style>