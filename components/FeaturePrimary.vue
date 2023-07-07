<template>
    <section id="feature-primary" class="panel">
        <div class="feature-text">
            <h2>Invoicer</h2>
            <p>Invoicing web application</p>
        </div>
        <img src="images/invoicer.webp" alt="">
        <a href="https://invoicer-blue.vercel.app/" target="_blank" class="feature-link">
            <font-awesome-icon icon="fa-solid fa-arrow-up-right-from-square" />
        </a>
    </section>
</template>

<style lang="scss">
    @media screen and (min-width: 0px) {
        #feature-primary {
            margin: 1rem;
            border-radius: var(--border-radius);
            position: relative;
            color: var(--color-white);
            .feature-text {
                position: absolute;
                top: 0.75rem;
                left: 0.75rem;
            }
            img {
                width: 100%;
                border-radius: var(--border-radius);
            }
            .feature-link {
                position: absolute;
                top: 0.75rem;
                right: 0.75rem;
                background-color: var(--color-white);
                width: 40px;
                height: 40px;
                display: flex;
                flex-direction: column;
                justify-content: center;
                align-items: center;
                border-radius: 100%;
                svg {
                    color: black;
                }
            }
        }
    }
</style>