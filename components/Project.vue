<template>
    <section class="panel project-panel" :class="{'light-text': project.lightText}" v-if="project">
        <div class="feature-text">
            <h2>{{ project.title }}</h2>
            <p>{{ project.description }}</p>
        </div>
        <img :src="`images/${project.image}`" alt="">
        <div class="project-links">
            <a :href="project.link" target="_blank" class="feature-link">
                <font-awesome-icon icon="fa-solid fa-arrow-up-right-from-square" />
            </a>
            <a :href="project.github" target="_blank" class="feature-link">
                <font-awesome-icon icon="fa-brands fa-github" />
            </a>
        </div>
    </section>
</template>

<style lang="scss">
    @media screen and (min-width: 0px) {
        .project-panel {
            margin: 0;
            border-radius: var(--border-radius);
            position: relative;
            color: black;
            &.light-text {
                color: var(--color-white);
                .feature-link {
                    background: none;
                    border: 1px solid var(--color-white);
                    &:hover {
                        background-color: var(--color-white);
                        svg {
                            color: black;
                        }
                    }
                    svg {
                        color: var(--color-white);
                        transition: var(--transition);
                    }
                }
            }
            .feature-text {
                position: absolute;
                top: 0.75rem;
                left: 0.75rem;
            }
            img {
                width: 100%;
                border-radius: var(--border-radius);
            }
            .project-links {
                position: absolute;
                top: 0.75rem;
                right: 0.75rem;
                display: flex;
                flex-direction: column;
                gap: 1rem;
            }
            .feature-link {
                background: none;
                border: 1px solid black;
                width: 40px;
                height: 40px;
                display: flex;
                flex-direction: column;
                justify-content: center;
                align-items: center;
                border-radius: 100%;
                transition: var(--transition);
                &:hover {
                    transform: scale(115%);
                    background-color: black;
                    svg {
                        color: var(--color-white);
                    }
                }
                svg {
                    color: black;
                    transition: var(--transition);
                }
            }
        }
    }
    @media screen and (min-width: 768px) {
        .project-panel {
            width: calc(50% - 0.5rem);
        }
    }
</style>

<script lang="ts">
    import { defineComponent } from 'vue';

    export default defineComponent({
        name: 'Project',
        props: {
            project: {
                type: Object,
            },
        }
    })
</script>