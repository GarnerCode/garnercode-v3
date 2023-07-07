<template>
    <section id="landing" class="panel">
        <div class="text">
            <h1>Hi, I'm <span class="highlight">Tyler</span></h1>
            <h1>I'm a <span class="highlight">Web Developer</span></h1>
            <p>I bring ideas to life on the web.</p>
        </div>
        <button class="button button-primary">Contact Me</button>
    </section>
</template>

<style lang="scss">
    @media screen and (min-width: 0px) {
        #landing {
            background-color: #3170cf;
            padding: 0.75rem;
            margin: 1rem;
            display: flex;
            flex-direction: column;
            gap: 3rem;
            h1 {
                color: #98B8E7;
                .highlight {
                    color: white;
                }
            }
            p {
                color: white;
            }
        }
    }
</style>