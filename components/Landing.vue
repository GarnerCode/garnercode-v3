<template>
    <section id="landing" class="panel">
        <div class="text">
            <h1>Hi, I'm <span class="highlight">Tyler</span></h1>
            <h1>I'm a <span class="highlight">Web Developer</span></h1>
            <p>I bring ideas to life on the web.</p>
        </div>
        <button class="button button-primary">Contact Me</button>
        <div class="headshot-border headshot-border-top"></div>
        <div class="headshot-border headshot-border-left"></div>
        <div class="headshot-container">
            <img src="images/headshot.webp" alt="Tyler Garner headshot">
        </div>
    </section>
</template>

<style lang="scss">
    @media screen and (min-width: 0px) {
        #landing {
            background-color: #3959DC;
            padding: 0.75rem;
            margin: 1rem;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            gap: 3rem;
            position: relative;
            h1 {
                color: #98B8E7;
                .highlight {
                    color: white;
                }
            }
            p {
                color: white;
            }
            .headshot-container {
                width: 100px;
                height: 100px;
                background-color: var(--color-background);
                display: flex;
                flex-direction: column;
                justify-content: center;
                align-items: center;
                position: absolute;
                bottom: 0;
                right: 0;
                border-top-left-radius: 50px;
            }
            .headshot-border {
                position: absolute;
                width: 28px;
                height: 28px;
                border-bottom-right-radius: 28px;
                box-shadow: 5px 5px 0 5px var(--color-background);
                background-color: #3959DC;
            }
            .headshot-border-top {
                bottom: 100px;
                right: 0;
            }
            .headshot-border-left {
                bottom: 0;
                right: 100px;
            }
            img {
                width: 90px;
                position: relative;
                left: 5px;
                top: 5px;
                border-radius: 100%;
            }
        }
    }
</style>