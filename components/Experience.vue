<template>
    <div id="experience">
        <section class="panel experience-panel" v-for="(item, index) of experience" :key="index">
            <div class="feature-text">
            <h2>{{ item.title }}</h2>
            <div class="row">
                <h3>{{ item.company }}</h3>
                <p class="fine">{{ item.dates }}</p>
            </div>
            <p>Worked with design and QA teams to develop and debug consumer home-buying websites and client applications.</p>
        </div>
        </section>
    </div>
</template>

<style lang="scss">
    #experience {
        .experience-panel {
            background: var(--color-primary);
            color: var(--color-white);
            margin: 1rem;
            padding: 0.75rem;
        }
        .row {
            display: flex;
            flex-direction: row;
            align-items: center;
            gap: 1rem;
            .fine {
                font-size: 12px;
                font-style: italic;
            }
        }
    }
</style>

<script lang="ts">
    import { defineComponent } from 'vue';
    import { experience } from '@/const/experience';

    export default defineComponent({
        name: 'Experience',
        data: () => {
            return {
                experience
            }
        }
    })
</script>