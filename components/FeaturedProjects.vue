<template>
    <div id="featured-projects">
        <Project v-for="(project, index) of projects" :key="index" :project="project"></Project>
    </div>
</template>

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