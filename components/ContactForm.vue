<template>
    <section id="contact-form" class="panel">
        <div class="panel-border"></div>
        <form @submit="(e) => handleSubmit(e)" action="https://getform.io/f/607da9e8-ff5a-4f71-9905-0979b0840530" method="POST">
            <div class="field field-name">
                <div class="label-container">
                    <label for="name">Name</label>
                    <div class="error" :class="{'active': !formModel.name.valid && formError}">Name is required</div>
                </div>
                <input :class="{'has-error': !formModel.name.valid && formError}" v-model="formModel.name.value" type="text" name="name">
            </div>
            <div class="field field-email">
                <div class="label-container">
                    <label for="email">Email</label>
                    <div class="error" :class="{'active': !formModel.email.valid && formError}">Email is required</div>
                </div>
                <input :class="{'has-error': !formModel.email.valid && formError}" v-model="formModel.email.value" type="email" name="email">
            </div>
            <div class="field field-phone">
                <div class="label-container">
                    <label for="phone">Phone</label>
                    <div class="error" :class="{'active': !formModel.phone.valid && formError}">Phone is required</div>
                </div>
                <input :class="{'has-error': !formModel.phone.valid && formError}" v-model="formModel.phone.value" type="tel" name="phone">
            </div>
            <div class="field">
                <div class="label-container">
                    <label for="message">Message</label>
                    <div class="error" :class="{'active': !formModel.message.valid && formError}">Message is required</div>
                </div>
                <textarea :class="{'has-error': !formModel.message.valid && formError}" v-model="formModel.message.value" name="message"></textarea>
            </div>
            <button id="submit-button" class="button button-primary">Submit</button>
        </form>
    </section>
</template>

<style lang="scss">
    @keyframes buttonError {
        0% {
            color: var(--color-background);
            background-color: var(--color-error);
            border-color: var(--color-error);
            transform: translateX(0px);
        }
        25% {
            transform: translateX(-10px);
        }
        50% {
            transform: translateX(10px);
        }
        100% {
            transform: translateX(0);
            color: var(--color-background);
            border-color: var(--color-text);
        }
    }
    @media screen and (min-width: 0px) {
        #contact-form {
            background-color: var(--color-panel);
            padding: 0.75rem;
            margin: 1rem;
            margin-top: 0;
            border-top-left-radius: 0;
            border-top-right-radius: 0;
            position: relative;
            opacity: 0;
            animation: fadeInUp 0.5s ease-in-out 1.75s forwards;
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
                margin-right: 0.75rem;
                display: flex;
                flex-direction: row;
                justify-content: space-between;
                .error {
                    display: none;
                    &.active {
                        display: block;
                        color: var(--color-error);
                    }
                }
            }
            .field-phone {
                display: none;
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
                &.has-error {
                    border: 1px solid var(--color-error);
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
                &.button-error {
                    animation: buttonError 0.5s ease-in-out;
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

<script lang="ts">
    import { defineComponent } from 'vue';

    export default defineComponent({
        name: 'ContactForm',
        data: () => {
            return {
                formModel: {
                    name: {
                        value: '',
                        valid: false,
                    },
                    email: {
                        value: '',
                        valid: false,
                    },
                    phone: {
                        value: '',
                        valid: false,
                    },
                    message: {
                        value: '',
                        valid: false
                    }
                },
                formError: false,
            }
        },
        methods: {
            formIsValid(): boolean {
                this.formError = false;

                if (!this.formModel.name.value.length) {
                    this.formModel.name.valid = false;
                    this.formError = true;
                } else {
                    this.formModel.name.valid = true;
                }

                if (!this.formModel.email.value.length) {
                    this.formModel.email.valid = false;
                    this.formError = true;
                } else {
                    this.formModel.email.valid = true;
                }

                if (this.formModel.phone.value.length) {
                    this.formError = true;
                }

                if (!this.formModel.message.value.length) {
                    this.formModel.message.valid = false;
                    this.formError = true;
                } else {
                    this.formModel.message.valid = true;
                }

                if (this.formError) {
                    return false;
                } else {
                    return true;
                }
            },
            buttonErrorAnim(): void {
                document.getElementById('submit-button')?.classList.add('button-error');
                setTimeout(function() {
                    document.getElementById('submit-button')?.classList.remove('button-error');
                }, 500);
            },
            handleSubmit(e: any): void {
                if (!this.formIsValid()) {
                    e.preventDefault();
                    this.buttonErrorAnim();
                }
            }
        }
    })
</script>