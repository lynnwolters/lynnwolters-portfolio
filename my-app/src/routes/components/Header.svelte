<header>
    <h1>
        <span>Lynn</span>
        <span>Wolters</span>
    </h1>
</header>

<style>
    header {
        height: calc(100vh - 7em);

        display: flex;
        align-items: end;

        margin: 2.5em 5em;
    }

    header h1 {
        width: 100%;

        font-family: var(--font-family-2);
        font-size: var(--font-size-1);
        font-weight: var(--font-weight-1);
        line-height: 100%;
        color: var(--color-1);
    }

    header h1 span:nth-of-type(2) {
        display: flex;
        justify-content: flex-end;
    }

    @media (min-width: 1600px) {
        header {
            margin: 3.5em 12em;
        }
    }

    @media (max-width: 1000px) {
        header {
            margin: 2.5em 2.5em;
        }
    }

    @media (max-width: 650px) {
        header {
            margin: 1.5em 1.5em;
        }
    }

    @media (max-width: 480px) {
        header {
            height: calc(100vh - 3em);
        }
    }
</style>