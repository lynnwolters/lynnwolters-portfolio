<section>
    <h2>My goal is to help clients stand out in the digital wor<span>ld by creating unique online experiences.</span></h2>
    <p>My name is Lynn and I am a 23 year old Communication & Multimedia Design student in Amsterdam. I am specialized in creating creative, accessible and user-friendly digital products.</p>
    <div>
        <img src="images/me.jpg" alt="me">
    </div>
</section>

<style>
    section {
        height: 100vh;

        display: grid;
        grid-template-columns: repeat(12, 1fr);
        grid-template-rows: repeat(3, 1fr);
        gap: 2.5em;

        margin: 2.5em 5em;
    }

    section h2 {
        grid-column: span 7;
        grid-row: 1/2;

        font-family: var(--font-family-1);
        font-size: var(--font-size-2);
        font-weight: var(--font-weight-2);
        line-height: 100%;
        color: var(--color-1);
    }

    section h2 span {
        opacity: .4;
    }

    section p {
        grid-column-start: 8;
        grid-column-end: 13;
        grid-row: 2/3;

        font-family: var(--font-family-1);
        font-size: var(--font-size-4);
        color: var(--color-1);
    }

    section div {
        grid-column: span 2;
        grid-row: 3/4;

        display: flex;
        align-items: end;
    }

    section div img {
        width: 100%;

        border-radius: 1em;
    }

    @media (min-width: 1600px) {
        section {
            margin: 2.5em 16em;
        }
    }
</style>