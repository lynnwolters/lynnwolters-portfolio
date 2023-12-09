<section>
    <h2>While studying, I ga<span>ined over 2,5+ years <br> of work experience in this field.</span></h2>
    <ul>
        <li>
            <button>
                <h3>Student Assistent</h3>
                <p>Apr 2023 - Jun 2023</p>
            </button>
        </li>
        <li>
            <button>
                <h3>Student Assistent</h3>
                <p>Apr 2023 - Jun 2023</p>
            </button>
        </li>
        <li>
            <button>
                <h3>Student Assistent</h3>
                <p>Apr 2023 - Jun 2023</p>
            </button>
        </li>
        <li>
            <button>
                <h3>Student Assistent</h3>
                <p>Apr 2023 - Jun 2023</p>
            </button>
        </li>
        <li>
            <button>
                <h3>Student Assistent</h3>
                <p>Apr 2023 - Jun 2023</p>
            </button>
        </li>
    </ul>
</section>

<style>
    section {
        height: 100vh;

        margin: 2.5em 5em;
    }

    section h2 {
        height: 20%;

        text-align: center;

        font-family: var(--font-family-1);
        font-size: var(--font-size-2);
        font-weight: var(--font-weight-2);
        line-height: 100%;
        color: var(--color-1);
    }

    section h2 span {
        opacity: .4;
    }

    section ul {
        height: 80%;

        display: flex;
        justify-content: center;
        flex-direction: column;
    }

    section ul li {
        list-style: none;
    }

    section ul li button {
        width: 100%;
        height: 5em;

        display: flex;
        justify-content: space-between;
        align-items: center;
    
        margin: .5em 0;
        padding: 0 2.5em;;

        border: solid .025em var(--color-1);
        border-radius: 1em;

        background-color: transparent;
    }

    section ul li button h3 {
        font-family: var(--font-family-1);
        font-size: var(--font-size-3);
        font-weight: var(--font-weight-2);
        color: var(--color-1);
    }

    section ul li button p {
        font-family: var(--font-family-1);
        font-size: var(--font-size-4);
        font-weight: var(--font-weight-1);
        color: var(--color-1);
        text-transform: var(--text-transform-uppercase);
    }

    @media (min-width: 1600px) {
        section {
            margin: 2.5em 16em;
        }
    }
</style>