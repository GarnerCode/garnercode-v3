<template>
    <section id="contact" class="panel">
        <h2 class="panel-header">Contact</h2>
        <p>If you are interested in working with me, contact me today!</p>
        <a href="mailto:tyler@garnercode.io">
            <font-awesome-icon icon="fa-solid fa-envelope" />
        </a>
    </section>
</template>

<style lang="scss">
    @media screen and (min-width: 0px) {
        #contact {
            background-color: var(--color-panel);
            padding: 0.75rem;
            margin: 1rem;
            margin-bottom: 0;
            border-bottom-left-radius: 0;
            border-bottom-right-radius: 0;
            opacity: 0;
            animation: fadeInUp 0.5s ease-in-out 1.75s forwards;
            position: relative;
            z-index: 6;
            a {
                border: 1px solid var(--color-text);
                width: 40px;
                height: 40px;
                display: flex;
                flex-direction: column;
                justify-content: center;
                align-items: center;
                border-radius: 100%;
                color: var(--color-text);
                transition: var(--transition);
                position: absolute;
                top: 0.75rem;
                right: 0.75rem;
                &:hover {
                    background-color: var(--color-text);
                    border-color: var(--color-text);
                    color: var(--color-background);
                    transform: scale(115%);
                }
            }
        }
    }
    @media screen and (min-width: 768px) {
        #contact {
            margin-top: 0;
            border-bottom-left-radius: var(--border-radius);
            border-bottom-right-radius: var(--border-radius);
            border-top-right-radius: 0;
            border-bottom-right-radius: 0;
            margin-right: 0;
            position: relative;
            width: calc(100% - 1rem);
            height: calc(428px - 289px + 4rem);
            a {
                top: calc(100% - 3.25rem);
                bottom: 0.75rem;
                left: 0.5rem;
            }
        }
    }
    @media screen and (min-width: 830px) {
        #contact {
            height: calc(408px - 281px + 6rem);
        }
    }
    @media screen and (min-width: 839px) {
        #contact {
            height: calc(408px - 237px);
        }
    }
    @media screen and (min-width: 936px) {
        #contact {
            height: calc(388px - 245px + 3rem);
        }
    }
    @media screen and (min-width: 956px) {
        #contact {
            height: calc(388px - 241px + 4rem);
        }
    }
</style>