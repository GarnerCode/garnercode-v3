<template>
    <section id="about" class="panel">
        <div class="text">
            <h2 class="panel-header">About Me</h2>
            <div class="paragraphs">
                <p>My name is Tyler Garner. I'm a front-end web developer that specializes in Vue.js. With over 5 years of web development experience, I am proficient in developing complex user-interfaces and web applications.</p>
            </div>
        </div>
        <div class="icons-row">
            <div class="column">
                <a href="https://github.com/GarnerCode" target="_blank" class="button button-theme about-link">
                    <font-awesome-icon icon="fa-brands fa-github" />
                </a>
                <a href="https://www.linkedin.com/in/tgarner98/" target="_blank" class="button button-theme about-link">
                    <font-awesome-icon icon="fa-brands fa-linkedin-in" />
                </a>
            </div>
            <a href="https://drive.google.com/file/d/139KydJAvsLkpU2kU7fc9Nb8spMbqozbb/view?usp=sharing" target="_blank" class="button button-theme">
                Resume
            </a>
        </div>
    </section>
</template>

<style lang="scss">
    @media screen and (min-width: 0px) {
        #about {
            background-color: var(--color-panel);
            padding: 0.75rem;
            margin: 0 1rem;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            opacity: 0;
            animation: fadeInUp 0.5s ease-in-out 0.75s forwards;
            transition: var(--transition);
            .paragraphs {
                margin-bottom: 1rem;
                p {
                    color: var(--color-text);
                }
            }
            .icons-row {
                display: flex;
                flex-direction: row;
                justify-content: space-between;
                .column {
                    display: flex;
                    flex-direction: row;
                    gap: 1rem;
                }
                a {
                    text-decoration: none;
                }
                .button {
                    background: none;
                    color: var(--color-text);
                    border: 1px solid var(--color-text);
                    max-height: 40px;
                    padding-top: 0;
                    padding-bottom: 0;
                    display: flex;
                    flex-direction: column;
                    justify-content: center;
                    transition: var(--transition);
                    &:hover {
                        background-color: var(--color-text);
                        color: var(--color-background);
                    }
                    &.about-link {
                        &:hover {
                            transform: scale(115%);
                        }
                    }
                }
            }
            .about-link {
                width: 40px;
                height: 40px;
                background-color: var(--color-background);
                color: var(--color-text);
                padding: 0;
                border-radius: 100%;
                display: flex;
                flex-direction: column;
                justify-content: center;
                align-items: center;
                transition: var(--transition);
            }
        }
    }
    @media screen and (min-width: 768px) {
        #about {
            width: calc(50% - 6rem);
            margin: 0;
        }
    }
</style>

<script lang="ts">

</script>