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
            background: linear-gradient(0deg, rgba(0,0,0,1) 25%, rgba(50,50,50,1) 100%);
            padding: 0.75rem;
            border-radius: var(--border-radius);
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