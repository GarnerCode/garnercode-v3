<template>
    <div id="featured-projects">
        <h2 class="panel-header">Featured Projects</h2>
        <div class="projects-container">
            <Project v-for="(project, index) of projects" :key="index" :project="project"></Project>
        </div>
    </div>
</template>

<style lang="scss">
    @media screen and (min-width: 0px) {
        #featured-projects {
            display: block;
            gap: 1rem;
            margin: 1rem;
            margin-bottom: 0;
            background: #111111;
            padding: 0.75rem;
            border-radius: var(--border-radius);
            opacity: 0;
            animation: fadeInUp 0.5s ease-in-out 1s forwards;
            .projects-container {
                display: flex;
                flex-direction: column;
                gap: 1rem;
            }
        }
    }
    @media screen and (min-width: 768px) {
        #featured-projects {
            .projects-container {
                flex-direction: row;
                flex-wrap: wrap;
            }
        }
    }
</style>

<script lang="ts">
    import { defineComponent } from 'vue';
    import { projects } from '@/const/projects';

    export default defineComponent({
        name: 'FeaturedProjects',
        data: () => {
            return {
                projects,
            }
        }
    })
</script>