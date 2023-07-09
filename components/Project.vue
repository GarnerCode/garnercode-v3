<template>
    <section class="panel project-panel" :class="{'light-text': project.lightText}" v-if="project">
        <div class="feature-text">
            <h2>{{ project.title }}</h2>
            <p>{{ project.description }}</p>
        </div>
        <img :src="`images/${project.image}`" alt="">
        <a :href="project.link" target="_blank" class="feature-link">
            <font-awesome-icon icon="fa-solid fa-arrow-up-right-from-square" />
        </a>
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
                    background-color: var(--color-white);
                    svg {
                        color: black;
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
            .feature-link {
                position: absolute;
                top: 0.75rem;
                right: 0.75rem;
                background-color: black;
                width: 40px;
                height: 40px;
                display: flex;
                flex-direction: column;
                justify-content: center;
                align-items: center;
                border-radius: 100%;
                svg {
                    color: var(--color-white);
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