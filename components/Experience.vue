<template>
    <div id="experience">
        <section class="panel experience-panel">
            <h2 class="panel-header">Experience</h2>
            <div class="experience-item panel" v-for="(item, index) of experience" :key="index">
                <h2>{{ item.title }}</h2>
                <div class="row">
                    <h3 class="company">{{ item.company }}</h3>
                    <p class="fine">{{ item.dates }}</p>
                </div>
                <p class="description">Worked with design and QA teams to develop and debug consumer home-buying websites and client applications.</p>
                <div class="credit-img-border credit-img-border-top"></div>
                <div class="credit-img-border credit-img-border-right"></div>
                <div class="credit-img-container">
                    <img :src="item.creditImg" alt="">
                </div>
                <div class="quote-container">
                    <p class="quote">"{{ item.quote }}"</p>
                    <h3 class="quote-credit">{{ item.credit }}</h3>
                </div>
            </div>
        </section>
    </div>
</template>

<style lang="scss">
    @media screen and (min-width: 0px) {
        #experience {
            opacity: 0;
            animation: fadeInUp 0.5s ease-in-out 1.25s forwards;
            position: relative;
            z-index: 6;
            .experience-panel {
                background: var(--color-panel);
                color: var(--color-text);
                margin: 1rem;
                padding: 0.75rem;
            }
            .experience-item {
                background-color: var(--color-primary);
                color: var(--color-white);
                border-radius: var(--border-radius);
                padding: 0.75rem;
                position: relative;
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
            .company, .fine {
                color: var(--color-secondary);
            }
            .description {
                margin: 1rem 0;
            }
            .credit-img-border {
                position: absolute;
                width: 28px;
                height: 28px;
                border-bottom-left-radius: var(--border-radius);
                background-color: var(--color-primary);
                box-shadow: -5px 5px 0 5px var(--color-panel);
                &.credit-img-border-top {
                    bottom: 100px;
                    left: 0;
                }
                &.credit-img-border-right {
                    bottom: 0;
                    left: 100px;
                }
            }
            .credit-img-container {
                position: absolute;
                bottom: 0;
                left: 0;
                width: 100px;
                height: 100px;
                background-color: var(--color-panel);
                display: flex;
                flex-direction: column;
                justify-content: center;
                align-items: center;
                border-top-right-radius: 50px;
                img {
                    border-radius: 100%;
                    width: 90px;
                    position: relative;
                    top: 5px;
                    right: 5px;
                }
            }
            .quote {
                margin-bottom: 3rem;
                font-style: italic;
                color: var(--color-secondary);
            }
            .quote-credit {
                margin-top: 0.75rem;
                margin-left: 100px;
            }
            .quote, .quote-credit {
                position: relative;
                z-index: 6;
            }
        }
    }
    @media screen and (min-width: 768px) {
        #experience {
            width: 100%;
            .experience-panel {
                margin-right: 0;
            }
            .quote {
                margin: 0;
                margin-left: 100px;
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