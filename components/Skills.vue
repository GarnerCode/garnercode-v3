<template>
    <div id="skills">
        <section class="panel">
            <h2 class="panel-header">Skills</h2>
        </section>
    </div>
</template>

<style lang="scss">
    @media screen and (min-width: 0px) {
        #skills {
            section {
                background-color: var(--color-panel);
                color: var(--color-white);
                padding: 0.75rem;
                margin: 0 1rem;
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