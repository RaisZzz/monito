<template>
    <div class="email-form">
        <p class="email-form__title">Register now so you don't miss our programs</p>
        <div class="email-form-right">
            <input v-model="email" type="text" class="input secondary email-from__input" placeholder="Enter your Email">
            <button class="button email-from__button" :disabled="emailSucces">Subcribe Now</button>
        </div>
    </div>
</template>

<script>
export default {
    data: () => {
        return {
            email: ''
        }
    },
    computed: {
        emailSucces() {
            const EMAIL_REGEXP = /^(([^<>()[\].,;:\s@"]+(\.[^<>()[\].,;:\s@"]+)*)|(".+"))@(([^<>()[\].,;:\s@"]+\.)+[^<>()[\].,;:\s@"]{2,})$/iu
            return !EMAIL_REGEXP.test(this.email);
        }
    }
}
</script>

<style scoped>
.email-form {
    padding: 32px;
    border-radius: 16px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 20px;
    background-color: var(--primary-color);
}

.email-form__title {
    text-transform: capitalize;
    color: #fff;
    font-size: 24px;
    font-weight: bold;
    max-width: 390px;
}

.email-form-right {
    padding: 12px;
    border-radius: 14px;
    display: flex;
    align-items: stretch;
    gap: 12px;
    background-color: #fff;
    width: 100%;
    flex: 1;
    justify-content: space-between;
}

.email-from__input {
    width: 100%;
    flex: 1;
}

.email-from__button {
    font-weight: 300;
    border-radius: 8px;
}

@media screen and (max-width: 900px) {
    .email-form {
        flex-direction: column;
        align-items: flex-start;
    }

    .email-form__title {
        width: 100%;
        max-width: 100%;
    }
}

@media screen and (max-width: 700px) {
    .email-form {
        padding: 16px;
        gap: 16px;
    }

    .email-form__title {
        font-size: 20px;
    }

    .email-form-right {
        flex-direction: column;
    }
}
</style>