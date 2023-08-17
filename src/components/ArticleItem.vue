<template>
    <div class="content-box article">
        <img v-if="article.image" :src="article.image" alt="" class="content-box__image article__image">
        <div class="content-box-info article-info">
            <p v-if="article.category" class="article__category">{{ article.category }}</p>
            <h3 v-if="article.title" class="content-box__title">{{ article.title }}</h3>
            <p v-if="article.description" class="article__description" ref="description">{{ description }}</p>
        </div>
    </div>
</template>
<script>
export default {
    data: () => {
        return {
            description: ''
        }
    },
    props: {
        article: {
            type: Object,
            required: true,
        }
    },
    mounted() {
        this.setDescription()
    },
    methods: {
        setDescription() {
            this.description = this.articleDescription
            this.checkHeight()
        },
        checkHeight() {
            this.$nextTick(() => {
                if (this.description) {
                    const description = this.$refs.description
                    const descriptionSplitted = this.description.split(' ')
                    descriptionSplitted.splice(descriptionSplitted.length - 1, 1)
                    this.description = descriptionSplitted.join(' ')

                    if (description.scrollHeight > description.offsetHeight) {
                        this.checkHeight()
                    } else {
                        this.description += '...'
                    }
                }
            })
        }
    },
    computed: {
        articleDescription() {
            return this.article.description
        }
    },
    watch: {
        articleDescription() {
            this.setDescription()
        }
    }
}
</script>

<style scoped>
.article {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    max-height: 410px;
}

.article__image {
    width: 100%;
    height: 240px;
    min-height: 240px;
}

.article-info {
    flex: 1;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    overflow: hidden;
}

.article__category {
    background-color: var(--accent-color);
    border-radius: 28px;
    padding: 2px 10px;
    color: var(--ui-bg);
    font-size: 10px;
    font-weight: 700;
    line-height: 1.6em;
    margin-bottom: 10px;
}

.article__description {
    font-size: 14px;
    font-weight: 300;
    text-overflow: ellipsis;
    overflow: hidden;
    display: -webkit-box;
    -webkit-box-orient: vertical;
    margin-top: 2px;
    flex: 1;
}
</style>