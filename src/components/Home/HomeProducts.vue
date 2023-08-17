<template>
    <div class="products">
        <div class="container">
            <div class="products-top" v-if="showTitle || !withoutMore">
                <div v-if="showTitle" class="products-top-title">
                    <p v-if="subtitle?.length" class="subtitle">{{ subtitle }}</p>
                    <p v-if="title?.length" class="title">{{ title }}</p>
                </div>
                <button v-if="!withoutMore" class="button small secondary more-btn" @click="more">
                    View more
                    <IconRightArrow class="more-btn__icon" />
                </button>
            </div>
            <div v-if="!articles" class="products-grid">
                <ProductItem v-for="(product, index) in products" :key="index" :product="product" />
            </div>
            <div v-else class="products-grid articles">
                <ArticleItem v-for="(article, index) in products" :key="index" :article="article" />
            </div>
            <button v-if="!withoutMore" class="button small secondary more-btn mobile" @click="more">
                View more
                <IconRightArrow class="more-btn__icon" />
            </button>
        </div>
    </div>
</template>

<script>
import IconRightArrow from '@/components/Icon/IconRightArrow.vue';
import ProductItem from '@/components/ProductItem.vue';
import ArticleItem from '../ArticleItem.vue';

export default {
    components: { IconRightArrow, ProductItem, ArticleItem },
    computed: {
        showTitle() {
            return this.subtitle?.length || this.title?.length
        }
    },
    methods: {
        more() {
            this.$emit('more')
        }
    },
    props: {
        subtitle: {
            type: String,
            default: '',
        },
        title: {
            type: String,
            default: '',
        },
        withoutMore: {
            type: Boolean,
            default: false,
        },
        products: {
            type: Array,
            default: () => []
        },
        articles: {
            type: Boolean,
            default: false,
        }
    }
}
</script>

<style scoped>
.products {
    margin: 60px 0;
}

.products-top {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 28px;
}

.products-grid {
    width: 100%;
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-gap: 20px;
}

.products-grid.articles {
    grid-template-columns: repeat(3, 1fr);
}

.more-btn.mobile {
    display: none;
    margin-top: 16px;
    width: 100%;
}

@media screen and (max-width: 1000px) {
    .products-grid {
        grid-template-columns: repeat(3, 1fr);
    }
}

@media screen and (max-width: 700px) {
    .products {
        margin: 40px 0;
    }

    .products-grid {
        grid-template-columns: repeat(2, 1fr);
        grid-gap: 12px;
    }

    .more-btn {
        display: none;
    }

    .products-top {
        margin-bottom: 20px;
    }

    .product__price {
        font-size: 16px;
    }

    .more-btn.mobile {
        display: flex;
    }

    .products-grid.articles {
        grid-template-columns: 1fr;
    }
}
</style>