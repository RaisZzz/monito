<template>
    <header class="header">
        <div class="container">
            <div class="header-left">
                <MainLogo class="header__logo" />
                <ul class="header-menu">
                    <li class="header-menu__item" v-for="(item, index) in menu" :key="index">
                        <a class="header-menu__item-link" :href="item.href">
                            {{ item.title }}
                        </a>
                    </li>
                </ul>
            </div>
            <div class="header-right">
                <div class="header__search-wrapper">
                    <IconSearch class="header__search-icon" />
                    <input v-model="search" type="text" class="input header__search" placeholder="Search something here">
                </div>
                <button class="button">Join the community</button>
                <UiSelect v-model="currency" :values="currencies" />
            </div>
        </div>
    </header>
</template>

<script>
import MainLogo from './MainLogo.vue';
import IconSearch from '@/components/Icon/IconSearch.vue';
import UiSelect from '@/components/Ui/UiSelect.vue';
import CurrencyVND from '@/components/Icon/Currency/CurrencyVND.vue';
import CurrencyRUB from './Icon/Currency/CurrencyRUB.vue';

export default {
    components: { MainLogo, IconSearch, UiSelect },
    data: () => {
        return {
            menu: [
                { title: 'Home', href: '#', },
                { title: 'Category', href: '#', },
                { title: 'About', href: '#', },
                { title: 'Contact', href: '#', },
            ],
            search: '',
            currency: null,
            currencies: [
                {
                    title: 'VND',
                    icon: CurrencyVND,
                    value: 'vnd',
                },
                {
                    title: 'RUB',
                    icon: CurrencyRUB,
                    value: 'rub',
                }
            ]
        }
    },
    created() {
        if (this.currencies.length) {
            this.currency = this.currencies[0]
        }
    }
}
</script>

<style scoped>
.header {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    z-index: 9;
}

.header .container {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding-top: 30px;
    padding-bottom: 30px;
}

.header-left {
    display: flex;
    align-items: center;
    gap: 48px;
}

.header-menu {
    display: flex;
    align-items: center;
    gap: 48px;
}

.header-menu__item {
    position: relative;
}

.header-menu__item:after {
    content: '';
    position: absolute;
    bottom: -3px;
    left: 0;
    width: 0;
    height: 2px;
    background-color: var(--primary-color);
    border-radius: 2px;
    transition: var(--transition);
}

.header-menu__item:hover:after {
    width: 100%;
}

.header-menu__item-link {
    font-weight: bold;
    color: var(--primary-color);
}

.header__search-wrapper {
    --icon-width: 20px;

    position: relative;
}

.header__search {
    min-width: 280px;
    padding-left: calc(var(--icon-width) + 28px);
}

.header__search-icon {
    position: absolute;
    top: 50%;
    left: 16px;
    transform: translateY(-50%);
    width: var(--icon-width);
    height: auto;
}

.header-right {
    display: flex;
    align-items: center;
    gap: 14px;
}
</style>