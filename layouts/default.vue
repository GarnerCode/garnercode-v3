<template>
    <div>
        <Navbar :userTheme="userTheme"></Navbar>
        <main>
            <Nuxt/>
        </main>
    </div>
</template>

<style lang="scss">
    :root {
        --color-background: #e0e0e0;
        --color-text: black;
        --color-panel: #FFFFFF;

        --border-radius: 50px;
    }
    :root.dark-theme {
        --color-background: black;
        --color-text: #F5F5F7;
        --color-panel: #111111;
    }
    body {
        background-color: var(--color-background);
        color: var(--color-text);
        margin: 0;
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
                this.userTheme === "light-theme" ? this.setTheme("dark-theme") : this.setTheme("light-theme")
            });
            const initialTheme = this.getMediaPreference();
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