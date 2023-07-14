<template>
    <section id="contact-form" class="panel">
        <div class="panel-border"></div>
        <form>
            <div class="field">
                <div class="label-container">
                    <label for="name">Name</label>
                </div>
                <input type="text" name="name">
            </div>
            <div class="field">
                <div class="label-container">
                    <label for="email">Email</label>
                </div>
                <input type="email" name="email">
            </div>
            <div class="field">
                <div class="label-container">
                    <label for="message">Message</label>
                </div>
                <textarea name="message"></textarea>
            </div>
            <button class="button button-primary">Submit</button>
        </form>
    </section>
</template>

<style lang="scss">
    @media screen and (min-width: 0px) {
        #contact-form {
            background-color: var(--color-panel);
            padding: 0.75rem;
            margin: 1rem;
            margin-top: 0;
            border-top-left-radius: 0;
            border-top-right-radius: 0;
            position: relative;
            .panel-border {
                position: absolute;
                top: calc(134px - 28px);
                left: -28px;
                width: 28px;
                height: 28px;
                background-color: var(--color-background);
                border-bottom-right-radius: var(--border-radius);
                box-shadow: 5px 5px 0 5px var(--color-panel);
                z-index: 5;
                display: none;
                transition: var(--transition);
            }
            form {
                display: flex;
                flex-direction: column;
                gap: 1rem;
            }
            .label-container {
                margin-bottom: 0.75rem;
                margin-left: 0.75rem;
            }
            input, textarea {
                padding: 0.75rem;
                font-size: 16px;
                background-color: var(--color-background);
                color: var(--color-text);
                border-radius: 14px;
                border: none;
                resize: none;
                width: calc(100% - 1.75rem);
                border: 1px solid var(--color-panel);
                transition: var(--transition);
                &:focus {
                    outline: none;
                    border-color: var(--color-text);
                }
            }
            button {
                border: 1px solid var(--color-text);
                color: var(--color-text);
                background: none;
                transition: var(--transition);
                &:hover {
                    background-color: var(--color-text);
                    border-color: var(--color-background);
                    color: var(--color-background);
                }
            }
        }
    }
    @media screen and (min-width: 768px) {
        #contact-form {
            margin-top: 1rem;
            margin-right: 0;
            border-top-left-radius: var(--border-radius);
            border-top-right-radius: var(--border-radius);
            border-bottom-left-radius: 0;
            width: calc(100% - 1.5rem);
            .panel-border {
                display: block;
                top: calc(134px - 20px);
            }
        }
    }
    @media screen and (min-width: 830px) {
        #contact-form {
            .panel-border {
                top: calc(134px - 40px);
            }
        }
    }
    @media screen and (min-width: 839px) {
        #contact-form {
            .panel-border {
                top: calc(134px + 12px);
            }
        }
    }
    @media screen and (min-width: 936px) {
        #contact-form {
            .panel-border {
                top: calc(134px - 8px);
            }
        }
    }
    @media screen and (min-width: 956px) {
        #contact-form {
            .panel-border {
                top: calc(134px - 28px);
            }
        }
    }
</style>