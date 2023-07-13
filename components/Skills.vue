<template>
    <div id="skills">
        <section class="panel">
            <h2 class="panel-header">Skills</h2>
            <div class="skill-items">
                <div class="skill" v-for="(skill, index) of skills" :key="index">
                    <div class="skill-icon-container">
                        <img class="skill-icon" :src="skill.icon" :alt="`${skill.label} icon`">
                    </div>
                    <p class="skill-label">{{ skill.label }}</p>
                </div>
            </div>
        </section>
    </div>
</template>

<style lang="scss">
    @media screen and (min-width: 0px) {
        #skills {
            opacity: 0;
            animation: fadeInUp 0.5s ease-in-out 1.5s forwards;
            height: fit-content;
            section {
                background-color: #111111;
                color: var(--color-white);
                padding: 0.75rem;
                margin: 0 1rem;
            }
            .skill-items {
                display: flex;
                flex-direction: row;
                flex-wrap: wrap;
                gap: 0.75rem;
            }
            .skill {
                display: flex;
                flex-direction: row;
                align-items: center;
                background-color: black;
                border-radius: var(--border-radius);
                width: fit-content;
            }
            .skill-icon-container {
                background-color: var(--color-white);
                width: 40px;
                height: 40px;
                display: flex;
                flex-direction: column;
                justify-content: center;
                align-items: center;
                border-radius: 100%;
            }
            .skill-icon {
                width: 20px;
            }
            .skill-label {
                margin: 0 0.75rem;
            }
        }
    }
    @media screen and (min-width: 768px) {
        #skills {
            width: calc(50% - 0.5rem);
            margin-top: 1rem;
            section {
                margin: 0;
            }
        }
    }
</style>

<script lang="ts">
    import { defineComponent } from 'vue';
    import { skills } from '@/const/skills';

    export default defineComponent({
        name: 'Skills',
        data: () => {
            return {
                skills,
            }
        }
    })
</script>