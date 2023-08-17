<template>
    <header class="header" :class="{ opened: menuOpened }">
        <div class="container">
            <div class="header-left">
                <button class="header__menu-button" @click="toggleMenu">
                    <span class="header__menu-button-line"></span>
                    <span class="header__menu-button-line"></span>
                    <span class="header__menu-button-line"></span>
                </button>
                <MainLogo class="header__logo" />
                <MainMenu class="header__menu" />
            </div>
            <div class="header-right">
                <div class="header__search-wrapper">
                    <IconSearch class="header__search-icon" />
                    <input v-model="search" type="text" class="input header__search" placeholder="Search something here">
                </div>
                <button class="button header__join">Join the community</button>
                <UiSelect class="header__currency" v-model="currency" :values="currencies" />
                <button class="header__search-button">
                    <IconSearch class="header__search-button-icon" />
                </button>
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
import MainMenu from './MainMenu.vue';

export default {
    components: { MainLogo, IconSearch, UiSelect, MainMenu },
    data: () => {
        return {
            search: '',
            currency: null,
            menuOpened: false,
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
    methods: {
        toggleMenu() {
            this.menuOpened = !this.menuOpened
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
    align-items: stretch;
    gap: 14px;
}

.header__search-button,
.header__menu-button {
    display: none;
}

.header__menu-button {
    width: 32px;
    min-width: 32px;
    height: 32px;
    padding: 9px 6px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-between;
}

.header__search-button {
    width: 32px;
    min-width: 32px;
    height: 32px;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 5px;
}

.header__search-button-icon {
    width: 100%;
    height: auto;
}

.header__menu-button-line {
    width: 100%;
    height: 2px;
    border-radius: 2px;
    background-color: var(--primary-color);
}

@media screen and (max-width: 1200px) {
    .header-left {
        gap: 20px;
    }

    .header__search {
        min-width: 0;
    }
}

@media screen and (max-width: 1020px) {
    .header.opened {
        position: fixed;
        top: 0;
        left: 0;
        width: 100vw;
        height: 100vh;
        z-index: 99;
        background-color: var(--secondary-color);
    }

    .header.opened .container {
        flex-direction: column;
        align-items: flex-start;
        gap: 24px;
    }

    .header.opened .header-left,
    .header.opened .header-right {
        flex-direction: column;
        align-items: flex-start;
    }

    .header.opened .header__logo {
        margin: 0;
    }

    .header:not(.opened) .header__menu,
    .header:not(.opened) .header__search-wrapper,
    .header:not(.opened) .header__join,
    .header:not(.opened) .header__currency {
        display: none;
    }

    .header__search-button,
    .header__menu-button {
        display: flex;
    }

    .header.opened .header__search-button {
        display: none;
    }

    .header-left {
        width: 100%;
        flex: 1;
    }

    .header__logo {
        margin: 0 auto;
    }
}
</style>