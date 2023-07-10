<template>
    <section id="landing" class="panel">
        <div class="text">
            <h1>Hi, I'm <span class="highlight">Tyler</span></h1>
            <h1>I'm a <span class="highlight">Web Developer</span></h1>
            <p>I bring ideas to life on the web.</p>
        </div>
        <button class="button button-primary">
            <div>Contact Me</div>
            <div class="icon-container">
                <font-awesome-icon icon="fa-solid fa-arrow-right" />
            </div>
        </button>
        <div class="headshot-border headshot-border-top"></div>
        <div class="headshot-border headshot-border-left"></div>
        <div class="headshot-container">
            <img src="images/headshot.webp" alt="Tyler Garner headshot">
        </div>
    </section>
</template>

<style lang="scss">
@keyframes scaleButtonIn {
    from {
        width: 222px;
    }
    to {
        width: 400px;
    }
}
@keyframes scaleButtonOut {
    from {
        width: 400px;
    }
    to {
        width: 222px;
    }
}
    @media screen and (min-width: 0px) {
        #landing {
            background-color: var(--color-primary);
            padding: 0.75rem;
            margin: 1rem;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            gap: 3rem;
            position: relative;
            opacity: 0;
            animation: fadeInUp 0.5s ease-in-out 0.5s forwards;
            h1 {
                color: var(--color-secondary);
                .highlight {
                    color: white;
                }
            }
            p {
                color: white;
            }
            .button {
                display: flex;
                flex-direction: row;
                justify-content: space-between;
                gap: 3rem;
                position: relative;
                z-index: 6;
                height: 40px;
                .icon-container {
                    background-color: var(--color-white);
                    width: 40px;
                    height: 40px;
                    border-radius: 100%;
                    display: flex;
                    flex-direction: column;
                    justify-content: center;
                    align-items: center;
                    position: relative;
                    top: -0.5rem;
                    right: -1rem;
                    svg {
                        color: black;
                    }
                }
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
                transition: var(--transition);
            }
            .headshot-border {
                position: absolute;
                width: 28px;
                height: 28px;
                border-bottom-right-radius: 28px;
                box-shadow: 5px 5px 0 5px var(--color-background);
                background-color: var(--color-primary);
                transition: var(--transition);
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
    @media screen and (min-width: 768px) {
        #landing {
            width: 50%;
            margin: 0 1rem;
        }
    }
    @media screen and (min-width: 1400px) {
        #landing {
            .button {
                transition: var(--transition);
                animation: scaleButtonOut 0.25s ease-in-out forwards;
                &:hover {
                    animation: scaleButtonIn 0.25s ease-in-out forwards;
                }
            }
        }
    }
</style>