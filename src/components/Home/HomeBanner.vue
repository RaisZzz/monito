<template>
    <div class="banner">
        <div class="container">
            <div class="banner-info">
                <h3 class="banner__title">One more friend</h3>
                <h3 class="banner__subtitle">Thousands more fun!</h3>
                <p class="banner__description">Having a pet means you have more joy, a new friend, a happy person who will
                    always be with you to have fun. We have 200+ different pets that can meet your needs!</p>
                <div class="banner-buttons">
                    <button class="button small secondary">
                        View Intro
                        <IconPlay />
                    </button>
                    <button class="button small">Explore Now</button>
                </div>
            </div>
            <div class="banner__bg-wrapper">
                <div class="banner__bg-crumb"></div>
                <div class="banner__bg-crumb"></div>
                <div class="banner__bg-crumb"></div>
                <img src="@/assets/img/banner-bg.png" alt="" class="banner__bg">
            </div>
        </div>
    </div>
</template>

<script>
import IconPlay from '@/components/Icon/IconPlay.vue';

export default {
    components: { IconPlay }
}
</script>

<style scoped>
.banner {
    background: linear-gradient(134deg, var(--secondary-gradient));
    position: relative;
    overflow: hidden;
}

.banner:before {
    content: '';
    position: absolute;
    top: 0;
    left: -520px;
    width: 635px;
    height: 635px;
    background-color: var(--secondary-color);
    z-index: 0;
    border-radius: 99px;
    transform: rotate(25deg) translate(0, -100%);
}

.banner:after {
    content: '';
    position: absolute;
    top: 100%;
    left: 0;
    width: 635px;
    height: 635px;
    background-color: var(--secondary-color);
    z-index: 0;
    border-radius: 99px;
    transform: rotate(56deg);
    opacity: 0.4;
}

.banner .container {
    display: flex;
    justify-content: space-between;
}

.banner-info {
    margin-top: 180px;
    max-width: 475px;
    position: relative;
    z-index: 3;
}

.banner__title {
    font-size: 60px;
    font-weight: 800;
    margin-bottom: 4px;
    color: var(--primary-color);
    position: relative;
}

.banner__title:before {
    content: '';
    position: absolute;
    top: 0;
    left: -10px;
    width: 67px;
    height: 67px;
    transform: rotate(25deg);
    border-radius: 20px;
    background-color: var(--secondary-color);
    z-index: -1;
}

.banner__subtitle {
    font-size: 46px;
    font-weight: 700;
    margin-bottom: 4px;
    color: var(--primary-color);
    margin-bottom: 24px;
}

.banner__description {
    font-size: 16px;
    font-weight: 300;
    margin-bottom: 34px;
}

.banner-buttons {
    display: flex;
    align-items: stretch;
    gap: 20px;
}

.banner__bg-wrapper {
    margin-right: 100px;
    margin-top: 100px;
    position: relative;
    z-index: 3;
    width: 40%;
    line-height: 0;
}

.banner__bg-wrapper:before {
    content: '';
    position: absolute;
    width: 635px;
    height: 635px;
    border-radius: 99px;
    background-color: var(--primary-color);
    bottom: 0;
    left: 0;
    z-index: -1;
    transform: rotate(9deg) translate(-10%, 50%);
}

.banner__bg-wrapper:after {
    content: '';
    position: absolute;
    width: 635px;
    height: 635px;
    border-radius: 99px;
    background-color: var(--secondary-color);
    bottom: 0;
    left: 0;
    z-index: 0;
    transform: rotate(25deg) translate(10%, 40%);
}

.banner__bg-crumb {
    position: absolute;
    z-index: -1;
    background-color: var(--secondary-color);
}

.banner__bg-crumb:nth-child(1) {
    top: 23%;
    left: 0;
    background-color: var(--primary-color);
    z-index: 0;
    width: 21px;
    height: 21px;
    transform: rotate(-43deg);
    border-radius: 6px;
}

.banner__bg-crumb:nth-child(2) {
    top: calc(23% - 10px);
    left: 0;
    width: 27px;
    height: 27px;
    transform: rotate(-22deg);
    border-radius: 9px;
}

.banner__bg-crumb:nth-child(3) {
    top: 10%;
    left: 25px;
    width: 14px;
    height: 14px;
    transform: rotate(20deg);
    border-radius: 4px;
}

.banner__bg {
    width: 100%;
    height: auto;
    position: relative;
    z-index: 1;
}

@media screen and (max-width: 1200px) {
    .banner-info {
        max-width: 350px;
    }

    .banner__title {
        font-size: 40px;
    }

    .banner__subtitle {
        font-size: 24px;
    }
}

@media screen and (max-width: 1020px) {

    .banner__bg-wrapper:before,
    .banner__bg-wrapper:after {
        width: 400px;
        height: 400px;
        border-radius: 50px;
    }

    .banner__bg-wrapper {
        margin-right: 40px;
    }

    .banner-info {
        margin-top: 100px;
    }
}

@media screen and (max-width: 700px) {
    .banner .container {
        flex-direction: column;
        align-items: center;
    }

    .banner-info {
        max-width: 100%;
        width: 100%;
        margin-top: 140px;
    }

    .banner__title {
        font-size: 46px;
    }

    .banner__subtitle {
        font-size: 28px;
        margin-bottom: 12px;
    }

    .banner__description {
        font-size: 12px;
        margin-bottom: 32px;
    }

    .banner-buttons {
        gap: 16px;
    }

    .banner__bg-wrapper {
        margin-top: 25px;
        margin-right: 0;
        width: 100%;
        max-width: 370px;
    }

    .banner__title:before {
        display: none;
    }
}
</style>