<template>
    <div class="container info-container">
        <div class="info-banner" :class="{ secondary }">
            <img v-if="image" :src="image" alt="" class="info__image">
            <div class="info">
                <h3 v-if="title?.length" class="info__title">{{ title }}</h3>
                <p v-if="subtitle?.length" class="info__subtitle">{{ subtitle }}</p>
                <p v-if=description?.length class="info__description">{{ description }}</p>
                <div class="info-buttons">
                    <button class="button small secondary info__button">
                        View Intro
                        <IconPlay class="info__button-icon" />
                    </button>
                    <button class="button small">Explore Now</button>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import IconPlay from '../Icon/IconPlay.vue';

export default {
    props: {
        title: {
            type: String,
            default: '',
        },
        subtitle: {
            type: String,
            default: '',
        },
        description: {
            type: String,
            default: '',
        },
        secondary: {
            type: Boolean,
            default: false,
        },
        image: {
            type: String,
            default: '',
        },
    },
    components: { IconPlay }
}
</script>

<style scoped>
.info-container {
    margin-top: 60px;
    margin-bottom: 60px;
}

.info-banner {
    display: flex;
    align-items: center;
    justify-content: flex-end;
    background-color: var(--primary-color);
    border-radius: 20px;
    overflow: hidden;
    position: relative;
    padding: 60px 85px;
}

.info-banner.secondary {
    justify-content: flex-start;
    background-color: #FFB775;
}

.info-banner:before {
    content: '';
    position: absolute;
    bottom: -600px;
    left: -200px;
    width: 780px;
    height: 780px;
    border-radius: 99px;
    transform: rotate(28deg);
    background-color: #002A48;
    z-index: 0;
}

.info-banner.secondary:before {
    right: -200px;
    left: auto;
    bottom: -620px;
    transform: rotate(151deg);
    background: linear-gradient(102deg, var(--secondary-gradient));
    opacity: 0.3;
}

.info {
    width: 50%;
    position: relative;
    z-index: 3;
    text-align: right;
    display: flex;
    flex-direction: column;
    align-items: flex-end;
}

.info-banner.secondary .info {
    text-align: left;
    align-items: flex-start;
}

.info:before {
    content: '';
    position: absolute;
    top: -300px;
    right: -300px;
    width: 780px;
    height: 635px;
    border-radius: 99px;
    transform: rotate(25deg);
    background-color: #FCEED5;
    z-index: -1;
}

.info-banner.secondary .info:before {
    left: -300px;
    right: auto;
    transform: rotate(154deg);
}

.info__title {
    font-size: 52px;
    font-weight: 800;
    margin-bottom: 2px;
    line-height: 1.3em;
    color: var(--primary-color);
}

.info__subtitle {
    font-size: 36px;
    font-weight: 700;
    margin-bottom: 8px;
    line-height: 1.3em;
    color: var(--primary-color);
}

.info__description {
    font-size: 12px;
    line-height: 1.5em;
    font-weight: 300;
    max-width: 400px;
}

.info-buttons {
    display: flex;
    align-items: stretch;
    justify-content: flex-end;
    gap: 20px;
    margin-top: 24px;
}

.info__image {
    height: 100%;
    width: auto;
    position: absolute;
    bottom: 0;
    left: 20%;
    z-index: 1;
    transform: translateX(-50%);
}

.info-banner.secondary .info__image {
    left: auto;
    right: 20%;
    transform: translateX(50%);
}
</style>