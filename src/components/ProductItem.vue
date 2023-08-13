<template>
    <button class="content-box">
        <img :src="product.image" alt="" class="content-box__image" ref="image">
        <div class="content-box-info">
            <p class="content-box__title">{{ product.title }}</p>
            <div v-if="product?.props" class="product-props">
                <div v-for="(key, value) in product.props" :key="key" class="product__prop">
                    {{ key }}: <span class="product__prop-value">{{ value }}</span>
                </div>
            </div>
            <p class="product__price">{{ product.price }}</p>
            <div class="product__gift" v-if="product.gift">
                <IconGift class="product__gift-icon" />
                {{ product.gift }}
            </div>
        </div>
    </button>
</template>

<script>
import IconGift from '@/components/Icon/IconGift.vue';

export default {
    components: { IconGift },
    mounted() {
        const image = this.$refs.image;
        const imageWidth = image.clientWidth;
        image.style.height = `${imageWidth}px`;
    },
    props: {
        product: {
            type: Object,
            required: true,
        }
    },
}
</script>

<style scoped>
.product-props {
    --horizontal-gap: 26px;

    display: flex;
    flex-wrap: wrap;
    gap: 12px var(--horizontal-gap);
    font-size: 12px;
    color: var(--secondary-text);
}

.product__prop {
    display: flex;
    align-items: center;
    position: relative;
}

.product__prop:not(:last-child):after {
    content: '';
    position: absolute;
    top: 50%;
    right: calc(var(--horizontal-gap) / -2);
    transform: translate(50%, -50%);
    width: 3px;
    height: 3px;
    border-radius: 3px;
    background-color: var(--secondary-text);
}

.product__prop-value {
    font-weight: 700;
    margin-left: 6px;
}

.product__price {
    font-size: 14px;
    font-weight: 700;
    margin-top: 4px;
}

.product__gift {
    --icon-width: 17px;
    --horizontal-padding: 7px;
    --gap: 24px;

    padding: var(--horizontal-padding) 10px;
    border-radius: 8px;
    background-color: var(--secondary-color);
    display: flex;
    align-items: center;
    gap: 24px;
    color: var(--primary-color);
    font-size: 14px;
    font-weight: 700;
    margin-top: 10px;
    position: relative;
}

.product__gift:after {
    content: '';
    position: absolute;
    top: 50%;
    left: calc(var(--horizontal-padding) + var(--icon-width) + var(--gap) / 2);
    transform: translate(50%, -50%);
    width: 4px;
    height: 4px;
    border-radius: 4px;
    background-color: var(--primary-color);
}

.product__gift-icon {
    width: var(--icon-width);
    height: auto;
}
</style>