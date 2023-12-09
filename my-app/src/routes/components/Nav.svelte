<nav>
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

<style>
    /* OUTER NAV */
    nav {
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
    nav > ul {
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
    nav > ul > li:nth-of-type(1) {
        list-style: none;
    }

    nav > ul > li:nth-of-type(1) a {
        font-family: var(--font-family-1);
        font-size: var(--font-size-4);
        color: var(--color-1);
        text-transform: var(--text-transform-uppercase);
        text-decoration: none;
    }

    /* LINKS */
    nav > ul > ul {
        display: flex;
    }

    nav > ul > ul li {
        list-style: none;
    }

    nav > ul > ul li button {
        margin: 0 1em;
        border: none;

        background-color: transparent;

        font-family: var(--font-family-1);
        font-size: var(--font-size-4);
        color: var(--color-1);
        text-transform: var(--text-transform-uppercase);
    }

    /* BUTTON */
    nav > ul > li:nth-of-type(2) {
        list-style: none;
    }

    nav > ul > li:nth-of-type(2) button {
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
        nav > ul {
            margin: 0 16em;
        }
    }
</style>