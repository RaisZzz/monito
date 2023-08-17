<template>
    <div class="ui-select">
        <button class="ui-select__label" @click="toggleOpened">
            <component class="ui-select__icon" v-if="value?.icon" :is="value?.icon" />
            <span class="ui-select__label-title">{{ value?.title }}</span>
            <IconBottomArrow class="ui-select__label-arrow" :class="{ opened }" />
        </button>
        <Transition name="fade">
            <div v-if="opened" class="ui-select-values">
                <button v-for="item in values" :key="item.id" class="ui-select__item"
                    :class="{ active: item.value === value?.value }" @click="onSelect(item)">
                    <component class="ui-select__icon" v-if="item.icon" :is="item.icon" />
                    <span class="ui-select__item-title">{{ item.title }}</span>
                </button>
            </div>
        </Transition>
    </div>
</template>

<script>
import IconBottomArrow from '../Icon/IconBottomArrow.vue';

export default {
    data: () => {
        return {
            opened: false,
        };
    },
    methods: {
        toggleOpened() {
            this.opened = !this.opened
        },
        onSelect(value) {
            this.$emit('input', value)
            this.opened = false
        }
    },
    props: {
        values: {
            type: Array,
            required: true,
        },
        value: {
            type: Object || null,
            default: null,
        }
    },
    components: { IconBottomArrow }
}
</script>

<style scoped>
.ui-select {
    position: relative;
}

.ui-select__label {
    padding: 10px 20px 10px 10px;
    display: flex;
    align-items: center;
    justify-content: flex-end;
    cursor: pointer;
    min-width: 110px;
    min-height: 40px;
    height: 100%;
}

.ui-select__icon {
    width: 16px;
    height: auto;
    margin-right: 8px;
}

.ui-select__label-title {
    margin-right: auto;
    font-size: 16px;
    font-weight: 500;
}

.ui-select__label-arrow {
    width: 6px;
    height: auto;
    transition: 0.3s;
    margin-left: 13px;
}

.ui-select__label-arrow.opened {
    transform: rotate(180deg);
}

.ui-select-values {
    position: absolute;
    top: 100%;
    left: 0;
    width: 100%;
    border: 1px solid var(--primary-color);
    border-radius: 0 0 8px 8px;
    overflow: hidden;
}

.ui-select__item {
    display: flex;
    align-items: center;
    padding: 5px;
    transition: var(--transition);
    width: 100%;
}

.ui-select__item:hover,
.ui-select__item.active {
    background-color: var(--primary-color);
    color: var(--ui-bg);
}

.ui-select__item-title {
    font-size: 14px;
    font-weight: 300;
}
</style>