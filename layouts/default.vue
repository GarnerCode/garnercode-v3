<template>
    <div class="app">
        <Navbar :userTheme="userTheme"></Navbar>
        <main>
            <Nuxt/>
        </main>
        <Footer></Footer>
    </div>
</template>

<style lang="scss">
    :root {
        --color-background: #e0e0e0;
        --color-text: black;
        --color-panel: #dadada;

        --color-white: #F5F5F7;
        --color-primary: #3959DC;
        --color-secondary: #98B8E7;
        --color-error: rgb(224, 48, 48);
        --border-radius: 28px;
        --font-family-primary: 'Nunito', sans-serif;
        --font-family-secondary: 'PT Sans', sans-serif;
        --transition: all 0.25s ease-in-out;
    }
    :root.dark-theme {
        --color-background: black;
        --color-text: #F5F5F7;
        --color-panel: #111111;
    }
    html {
        scroll-behavior: smooth;
    }
    body {
        background-color: var(--color-background);
        color: var(--color-text);
        margin: 0;
        font-family: var(--font-family-secondary);
        transition: var(--transition);
    }
    .view-container {
        margin-top: calc(2rem + 56px);
    }
    h1, h2, h3 {
        font-family: var(--font-family-primary);
        margin: 0;
    }
    p {
        margin: 0;
    }
    .panel {
        border-radius: var(--border-radius);
    }
    .panel-header {
        color: var(--color-text);
        border-radius: var(--border-radius);
        border: 1px solid var(--color-text);
        padding: 0.5rem 1rem;
        width: fit-content;
        margin-bottom: 1rem;
    }
    .button {
        border: none;
        padding: 0.5rem 1rem;
        border-radius: 28px;
        font-family: var(--font-family-primary);
        font-size: 1.25rem;
        width: fit-content;
        cursor: pointer;
        &.button-theme {
            background-color: var(--color-text);
            color: var(--color-background);
        }
        &.button-theme-secondary {
            border: 1px solid var(--color-text);
            color: var(--color-text);
            transition: var(--transition);
            &:hover {
                background-color: var(--color-text);
                color: var(--color-background);
            }
        }
        &.button-primary {
            background-color: black;
            color: #F5F5F7;
        }
    }
    @keyframes fadeInUp {
        from {
            opacity: 0;
            transform: translateY(3rem);
        }
        to {
            opacity: 1;
            transform: translateY(0);
        }
    }
    @media screen and (min-width: 0px) {
        h1 {
            font-size: 2rem;
        }
    }
</style>

<script lang="ts">
    import { defineComponent } from 'vue';

    export default defineComponent({
        name: 'Layout',
        data: () => {
            return {
                userTheme: 'light-theme',
            }
        },
        mounted() {
            document.addEventListener('themeEvent', () => {
                this.userTheme === "light-theme" ? this.setTheme("dark-theme") : this.setTheme("light-theme");
            });
            let initialTheme = null as any;
            this.getTheme() ? initialTheme = this.getTheme() : initialTheme = this.getMediaPreference();
            this.setTheme(initialTheme);
        },
        methods: {
            getMediaPreference(): string {
                const hasDarkPreference = window.matchMedia(
                    "(prefers-color-scheme: dark)"
                ).matches;
                if (hasDarkPreference) {
                    return "dark-theme";
                } else {
                    return "light-theme";
                }
            },
            setTheme(theme: string): void {
                localStorage.setItem("user-theme", theme);
                this.userTheme = theme;
                document.documentElement.className = theme;
            },
            getTheme() {
                return localStorage.getItem("user-theme");
            }
        }
    })
</script>