<script>
    let openAccordionIndex = null

    function toggleAccordion(index) {
        if (openAccordionIndex === index) {
            openAccordionIndex = null
        } else {
            openAccordionIndex = index 
        }
    }
</script>

<section>
    <h2>While studying, I ga<span>ined over 2,5+ years of work experience in this field.</span></h2>
    <ul>
        <li>
            <button on:click={() => toggleAccordion(0)}>
                <h3>Student Assistent Front-end Development</h3>
                <p>Sept 2023 - Now</p>
            </button>
            {#if openAccordionIndex === 0}
                <div class="accordion">
                    <p>Lorem ipsum dolor sit amet. Et earum galisum qui galisum illum ea atque veritatis et dicta deserunt in odit magnam ut tempora reiciendis. Ut dolore quia cum voluptatum quisquam eos inventore itaque est placeat voluptatem. Et consequuntur sequi aut facere unde et provident rerum. Ut vero tenetur ea facere nobis qui mollitia dolorem sed nemo expedita est doloribus veniam est veniam voluptas.</p>
                </div>
            {/if}
        </li>
        <li>
            <button on:click={() => toggleAccordion(1)}>
                <h3>Intern at Lama Lama</h3>
                <p>Apr 2023 - Jun 2023</p>
            </button>
            {#if openAccordionIndex === 1}
                <div class="accordion">
                    <p>Lorem ipsum dolor sit amet. Et earum galisum qui galisum illum ea atque veritatis et dicta deserunt in odit magnam ut tempora reiciendis. Ut dolore quia cum voluptatum quisquam eos inventore itaque est placeat voluptatem. Et consequuntur sequi aut facere unde et provident rerum. Ut vero tenetur ea facere nobis qui mollitia dolorem sed nemo expedita est doloribus veniam est veniam voluptas.</p>
                </div>
            {/if}
        </li>
        <li>
            <button on:click={() => toggleAccordion(2)}>
                <h3>Intern at Stimmt Digital</h3>
                <p>Sep 2019 - Jan 2020</p>
            </button>
            {#if openAccordionIndex === 2}
                <div class="accordion">
                    <p>Lorem ipsum dolor sit amet. Et earum galisum qui galisum illum ea atque veritatis et dicta deserunt in odit magnam ut tempora reiciendis. Ut dolore quia cum voluptatum quisquam eos inventore itaque est placeat voluptatem. Et consequuntur sequi aut facere unde et provident rerum. Ut vero tenetur ea facere nobis qui mollitia dolorem sed nemo expedita est doloribus veniam est veniam voluptas.</p>
                </div>
            {/if}
        </li>
        <li>
            <button on:click={() => toggleAccordion(3)}>
                <h3>Intern at Nerds & Company</h3>
                <p>Jan 2019 - Jul 2019</p>
            </button>
            {#if openAccordionIndex === 3}
                <div class="accordion">
                    <p>Lorem ipsum dolor sit amet. Et earum galisum qui galisum illum ea atque veritatis et dicta deserunt in odit magnam ut tempora reiciendis. Ut dolore quia cum voluptatum quisquam eos inventore itaque est placeat voluptatem. Et consequuntur sequi aut facere unde et provident rerum. Ut vero tenetur ea facere nobis qui mollitia dolorem sed nemo expedita est doloribus veniam est veniam voluptas.</p>
                </div>
            {/if}
        </li>
        <li>
            <button on:click={() => toggleAccordion(4)}>
                <h3>Freelance</h3>
                <p>2018 - 2019</p>
            </button>
            {#if openAccordionIndex === 4}
                <div class="accordion">
                    <p>Lorem ipsum dolor sit amet. Et earum galisum qui galisum illum ea atque veritatis et dicta deserunt in odit magnam ut tempora reiciendis. Ut dolore quia cum voluptatum quisquam eos inventore itaque est placeat voluptatem. Et consequuntur sequi aut facere unde et provident rerum. Ut vero tenetur ea facere nobis qui mollitia dolorem sed nemo expedita est doloribus veniam est veniam voluptas.</p>
                </div>
            {/if} 
        </li>
    </ul>
</section>

<style>
    section {
        height: 100vh;

        display: flex;
        justify-content: center;
        flex-direction: column;

        margin: 2.5em 5em;
    }

    section h2 {
        width: 60%;

        margin: 0 auto 4em auto;
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

        border: solid .025em var(--color-4);
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

    .accordion {
        padding: 2.5em;

        border: solid .025em var(--color-4);
        border-radius: 1em;

        font-family: var(--font-family-1);
        font-size: var(--font-size-4);
        color: var(--color-1);
    }

    @media (min-width: 1600px) {
        section {
            margin: 2.5em 12em;
        }

        section ul li button {
            height: 7em;

            margin: 1em 0;
        }
    }

    @media (max-width: 1000px) {
        section {
            margin: 2.5em 2.5em;
        }

        section h2 {
            width: 80%;
        }
    }

    @media (max-width: 650px) {
        section {
            margin: 1.5em 1.5em;
        }

        section ul li button {
            height: 3.5em;

            padding: 0 1.5em;;
            
            border-radius: .7em;
        }

        .accordion {
            border-radius: .7em;
        }
    }

    @media (max-width: 480px) {
        section {
            height: 75vh;
        }
    }
</style>