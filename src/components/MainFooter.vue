<template>
    <footer class="footer">
        <div class="container">
            <EmailForm />
            <div class="footer-row">
                <MainMenu small />
                <MainSocial />
            </div>
            <div class="footer-info">
                <p class="footer__text">© 2022 Monito. All rights reserved.</p>
                <MainLogo class="footer__logo" />
                <div class="footer-links">
                    <a href="#" target="_blank" class="footer__text">Terms of Service</a>
                    <a href="#" target="_blank" class="footer__text">Privacy Policy</a>
                </div>
            </div>
        </div>
    </footer>
</template>

<script>
import EmailForm from './EmailForm.vue';
import MainLogo from './MainLogo.vue';
import MainMenu from './MainMenu.vue';
import MainSocial from './MainSocial.vue';

export default {
    components: { EmailForm, MainMenu, MainSocial, MainLogo }
}
</script>

<style scoped>
.footer {
    margin-top: 60px;
    background: linear-gradient(102deg, var(--secondary-gradient));
    padding-top: 80px;
    padding-bottom: 40px;
}

.footer-row {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-top: 40px;
    padding-bottom: 40px;
    border-bottom: 1px solid #CCD1D2;
    gap: 20px;
}

.footer-info {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-top: 40px;
}

.footer-links {
    display: flex;
    align-items: center;
    gap: 24px;
}

.footer__text {
    color: var(--secondary-text);
    font-size: 14px;
    font-weight: 300;
}

@media screen and (max-width: 700px) {
    .footer {
        margin-top: 40px;
        padding-top: 40px;
        padding-bottom: 20px;
    }

    .footer-row {
        flex-direction: column;
        align-items: center;
    }

    .footer-info {
        flex-direction: column;
        align-items: center;
        gap: 8px;
    }

    .footer__logo {
        order: -2;
        margin-bottom: 24px;
    }

    .footer-links {
        order: -1;
    }
}
</style>