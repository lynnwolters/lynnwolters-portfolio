<section>
    <div>
        <h2>Work</h2>
    </div>
    <div>
        <article>
            <div>
                <h3>Playheart.io</h3>
                <p>/ 01</p>
            </div>
            <div><img src="images/playheart.png" alt="playheart"></div>
            <ul>
                <li><p>UI/UX design</p></li>
                <li><p>Front-end development</p></li>
                <li><p></p></li>
            </ul>
        </article>
        <article>
            <div>
                <h3>Swapfiets</h3>
                <p>/ 02</p>
            </div>
            <div><img src="images/swapfiets.png" alt="swapfiets"></div>
            <ul>
                <li><p>UI/UX design</p></li>
                <li><p>Illustration</p></li>
                <li><p>Brand design</p></li>
            </ul>
        </article>
        <article>
            <div>
                <h3>Coming soon...</h3>
                <p>/ 03</p>
            </div>
            <div><img src="" alt=""></div>
            <ul>
                <li><p></p></li>
                <li><p></p></li>
                <li><p></p></li>
            </ul>
        </article>
    </div>
</section>

<style>
    section > div:nth-of-type(1) {
        height: 100vh;

        display: flex;
        justify-content: center;
        align-items: center;

        margin: 2.5em 5em;
    }

    section > div:nth-of-type(1) h2 {
        opacity: .1;

        font-family: var(--font-family-2);
        font-size: var(--font-size-1);
        font-weight: var(--font-weight-1);
        line-height: 100%;
        color: var(--color-1);
    }

    section > div:nth-of-type(2) {
        height: 100vh;

        display: grid;
        grid-template-columns: repeat(12, 1fr);
        gap: 2.5em;
        align-items: center;

        margin: 2.5em 5em;
    }

    section > div:nth-of-type(2) article {
        grid-column: span 4;
        height: 40vh;

        display: flex;
        justify-content: space-between;
        flex-direction: column;

        padding: 2.5em;

        border: solid .025em var(--color-4);
        border-radius: 1em;
    }

    section > div:nth-of-type(2) article div:nth-of-type(1) {
        display: flex;
        justify-content: space-between;
    }

    section > div:nth-of-type(2) article div:nth-of-type(1) h3 {
        font-family: var(--font-family-1);
        font-size: var(--font-size-3);
        font-weight: var(--font-weight-2);
        color: var(--color-1);
    }

    section > div:nth-of-type(2) article div:nth-of-type(1) p {
        font-family: var(--font-family-1);
        font-size: var(--font-size-4);
        font-weight: var(--font-weight-1);
        color: var(--color-1);
    }

    section > div:nth-of-type(2) article ul li {
        list-style: none;
    }

    section > div:nth-of-type(2) article ul li p {
        font-family: var(--font-family-1);
        font-size: var(--font-size-4);
        font-weight: var(--font-weight-1);
        color: var(--color-1);
        text-transform: var(--text-transform-uppercase);
    }

    section > div:nth-of-type(2) article:nth-of-type(2) {
        margin-top: 8em;
    }

    /* IMG */
    
    section > div:nth-of-type(2) article div:nth-of-type(2) {    
        overflow: hidden;

        display: flex;
        justify-content: center;
        align-items: center;

        margin: 2em 0;
    }

    section > div:nth-of-type(2) article div:nth-of-type(2) img {
        max-height: 100%;
        max-width: 100%;
    }

    @media (min-width: 1600px) {
        section > div:nth-of-type(1) {
            margin: 2.5em 12em;
        }

        section > div:nth-of-type(2) {
            margin: 2.5em 12em;
        }

        section > div:nth-of-type(2) article {
            height: 60vh;
        }
    }

    @media (max-width: 1000px) {
        section > div:nth-of-type(1) {
            margin: 2.5em 2.5em;
        }

        section > div:nth-of-type(2) {
            height: fit-content;
            
            margin: 2.5em 2.5em;
        }

        section > div:nth-of-type(2) article {
            grid-column: span 6;
        }
        
        section > div:nth-of-type(2) article:nth-of-type(2) {
            margin-top: 0em
        }
    }

    @media (max-width: 650px) {
        section > div:nth-of-type(1) {
            margin: 1.5em 1.5em;
        }

        section > div:nth-of-type(2) {
            gap: 1.5em;

            margin: 1.5em 1.5em;
        }
        
        section > div:nth-of-type(2) article {
            grid-column: span 12;

            padding: 1.5em;

            border-radius: .7em;
        }
    }

    @media (max-width: 480px) {
        section > div:nth-of-type(2) {
            height: fit-content;
        }
    }
</style>