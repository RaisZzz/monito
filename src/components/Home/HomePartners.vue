<template>
    <div class="partners">
        <div class="container">
            <div class="partners-top">
                <p class="partners__title">
                    <span class="subtitle">Proud to be part of</span> <span class="title">Pet Sellers</span>
                </p>
                <button class="button small secondary more-btn">
                    View all our sellers
                    <IconRightArrow class="more-btn__icon" />
                </button>
            </div>
            <div class="partners-grid">
                <img v-for="index in partnersCount" :key="index" :src="require(`@/assets/img/partners/${index}.png`)" alt=""
                    class="partners__image">
            </div>
        </div>
    </div>
</template>

<script>
import IconRightArrow from '../Icon/IconRightArrow.vue';

export default {
    components: { IconRightArrow },
    data: () => {
        return {
            partnersCount: 7,
        }
    }
}
</script>

<style>
.partners {
    margin: 60px 0;
}

.partners-top {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 15px;
}

.partners-grid {
    display: grid;
    grid-template-columns: repeat(7, 1fr);
    grid-gap: 20px;
}

.partners__image {
    width: 100%;
    height: 100%;
    object-fit: contain;
    object-position: center;
    padding: 0 20px;
    max-height: 110px;
}
</style>