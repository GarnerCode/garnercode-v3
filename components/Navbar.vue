<template>
    <div>
        <nav :class="{'active': navToggled}">
            <div class="logo">
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 301 301">
                    <g id="Layer_2" data-name="Layer 2">
                        <circle class="cls-2" cx="150.5" cy="150.5" r="150"/>
                    </g>
                    <g id="Layer_1" data-name="Layer 1">
                        <path class="cls-1" d="m98.28,104.85c5.52-5.52,12.14-9.73,19.86-12.64,7.62-2.91,16.25-4.41,25.78-4.41h77.75v-25.08h-77.75c-13.04,0-24.98,2.11-35.71,6.42-10.73,4.31-20.06,10.23-27.69,17.96-7.62,7.72-13.74,16.85-17.96,27.69s-6.42,22.67-6.42,35.71,2.11,24.98,6.42,35.71c4.31,10.73,10.23,20.06,17.96,27.69,7.72,7.72,16.95,13.64,27.69,17.96,10.73,4.31,22.67,6.42,35.71,6.42h25.28v-25.08h-25.28c-9.53,0-18.16-1.5-25.88-4.41-7.72-2.91-14.25-7.12-19.86-12.64-5.62-5.52-9.73-12.14-12.64-19.86-2.91-7.72-4.31-16.25-4.31-25.78s1.5-18.16,4.41-25.88c2.91-7.62,7.12-14.25,12.64-19.76Zm123.39,33.11h-107.34l44.04,57.99,6.22,8.23,6.22,8.23.1.2,19.66,25.68h31.1l-25.98-34.11-10.23-13.44-21.17-27.69h57.38v-25.08Z"/>
                        <polygon class="cls-1" points="221.68 163.04 164.29 163.04 185.36 190.73 195.69 204.17 164.69 204.17 158.37 195.95 114.33 137.96 221.68 137.96 221.68 163.04"/>
                        <polygon class="cls-1" points="221.68 238.28 190.58 238.28 171.11 212.6 171.11 190.73 185.36 190.73 195.69 204.17 221.68 238.28"/>
                        <polygon class="cls-1" points="175.43 195.95 175.43 212.4 170.91 212.4 164.69 204.17 158.37 195.95 175.43 195.95"/>
                    </g>
                </svg>
            </div>
            <div class="nav-links">
                <div>Home</div>
                <div>About</div>
                <div>Portfolio</div>
                <div>Contact</div>
                <div class="button button-theme">Resume</div>
            </div>
            <div class="mode-toggle desktop-mode-toggle" @click="emitThemeEvent()">
                <div class="mode-toggle-button" :class="{'active': userTheme === 'light-theme'}">
                    <font-awesome-icon icon="fa-solid fa-sun" />
                </div>
                <div class="mode-toggle-button" :class="{'active': userTheme === 'dark-theme'}">
                    <font-awesome-icon icon="fa-solid fa-moon" />
                </div>
            </div>
            <div class="nav-toggle" @click="navToggled = !navToggled" :class="{'toggled': navToggled}">
                <div class="line1"></div>
                <div class="line2"></div>
                <div class="line3"></div>
            </div>
        </nav>
        <div class="nav-overlay" @click="navToggled = false" v-if="navToggled"></div>
        <div class="nav-menu" v-if="navToggled">
            <div class="nav-items">
                <div>Home</div>
                <div>About</div>
                <div>Portfolio</div>
                <div>Contact</div>
                <div class="button button-theme">Resume</div>
            </div>
            <div class="mode-toggle" @click="emitThemeEvent()">
                <div class="mode-toggle-button" :class="{'active': userTheme === 'light-theme'}">
                    <font-awesome-icon icon="fa-solid fa-sun" />
                </div>
                <div class="mode-toggle-button" :class="{'active': userTheme === 'dark-theme'}">
                    <font-awesome-icon icon="fa-solid fa-moon" />
                </div>
            </div>
        </div>
    </div>
</template>

<style lang="scss">
    @media screen and (min-width: 0px) {
        nav {
            border-radius: var(--border-radius);
            background-color: var(--color-panel);
            padding: 0.5rem 0.5rem;
            margin: 1rem;
            margin-bottom: 0;
            display: flex;
            flex-direction: row;
            justify-content: space-between;
            align-items: center;
            position: absolute;
            top: 0;
            left: 0;
            width: calc(100vw - 3rem);
            z-index: 10;
            &.active {
                border-bottom-left-radius: 0;
                border-bottom-right-radius: 0;
            }
            .logo {
                width: 40px;
                height: 40px;
                svg {
                    width: 40px;
                    height: 40px;
                }
                .cls-1 {
                    fill: var(--color-background);
                    width: 40px;
                    height: 40px;
                }
                .cls-2 {
                    fill: var(--color-text);
                }
            }
            .nav-links {
                display: none;
            }
            .desktop-mode-toggle {
                display: none;
            }
            .nav-toggle {
                background-color: var(--color-text);
                width: 40px;
                height: 40px;
                display: flex;
                flex-direction: column;
                justify-content: center;
                align-items: center;
                gap: 3px;
                border-radius: 100%;
                cursor: pointer;
                div {
                    width: 20px;
                    height: 3px;
                    background-color: var(--color-background);
                    transition: all 0.3s ease;
                    border-radius: 5px;
                }
                &.toggled {
                    .line1 {
                        transform: rotate(-45deg) translate(-4px, 3px);
                    }
                    .line2 {
                        opacity: 0;
                    }
                    .line3 {
                        transform: rotate(45deg) translate(-5px, -5px);
                    }
                }
            }
        }
        .nav-overlay {
            position: absolute;
            z-index: 9;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            background-color: rgba(0, 0, 0, 0.25);
            backdrop-filter: blur(5px);
        }
        .nav-menu {
            background-color: var(--color-panel);
            border-radius: var(--border-radius);
            border-top-left-radius: 0;
            border-top-right-radius: 0;
            margin: 1rem;
            margin-top: 0;
            padding: 0.5rem;
            font-family: var(--font-family-primary);
            position: absolute;
            top: calc(1rem + 56px);
            width: calc(100vw - 3rem);
            left: 0;
            z-index: 10;
            display: flex;
            flex-direction: row;
            justify-content: space-between;
            align-items: flex-end;
            .nav-items {
                display: flex;
                flex-direction: column;
                gap: 1rem;
                div {
                    font-size: 1.25rem;
                    padding: 0.5rem 1rem;
                    &.button {
                        height: 40px;
                        padding-top: 0;
                        padding-bottom: 0;
                        display: flex;
                        flex-direction: column;
                        justify-content: center;
                    }
                }
            }
        }
        .mode-toggle {
            background-color: var(--color-background);
            border-radius: var(--border-radius);
        }
        .mode-toggle-button {
            width: 40px;
            height: 40px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            background-color: var(--color-background);
            color: var(--color-text);
            border-radius: 100%;
            &.active {
                background-color: var(--color-text);
                color: var(--color-background);
            }
        }
    }
    @media screen and (min-width: 768px) {
        nav {
            .nav-toggle {
                display: none;
            }
            .nav-links {
                display: flex;
                flex-direction: row;
                align-items: center;
                gap: 2rem;
                .button {
                    height: 40px;
                    padding-top: 0;
                    padding-bottom: 0;
                    display: flex;
                    flex-direction: column;
                    justify-content: center;
                }
            }
            .desktop-mode-toggle {
                display: flex;
                cursor: pointer;
            }
        }
    }
    @media screen and (min-width: 1400px) {
        nav {
            width: calc(1000px - 3rem);
            margin: 1rem auto;
            left: 0;
            right: 0;
        }
    }
</style>

<script lang="ts">
    import { defineComponent } from 'vue';

    export default defineComponent({
        name: 'Navbar',
        data: () => {
            return {
                navToggled: false,
            }
        },
        props: {
            userTheme: {
                type: String,
            }
        },
        methods: {
            emitThemeEvent(): void {
                const event = new Event('themeEvent');
                document.dispatchEvent(event);
            }
        }
    })
</script>