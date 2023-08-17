<template>
    <ul class="menu" :class="{ small }">
        <li class="menu__item" v-for="(item, index) in menu" :key="index">
            <a class="menu__item-link" :href="item.href">
                {{ item.title }}
            </a>
        </li>
    </ul>
</template>

<script>
export default {
    data: () => {
        return {
            menu: [
                { title: 'Home', href: '#', },
                { title: 'Category', href: '#', },
                { title: 'About', href: '#', },
                { title: 'Contact', href: '#', },
            ],
        }
    },
    props: {
        small: {
            type: Boolean,
            default: false,
        }
    }
}
</script>

<style scoped>
.menu {
    display: flex;
    align-items: center;
    gap: 48px;
}

.menu__item {
    position: relative;
}

.menu__item:after {
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

.menu__item:hover:after {
    width: 100%;
}

.menu__item-link {
    font-weight: bold;
    color: var(--primary-color);
    font-size: 16px;
}

.menu.small .menu__item-link {
    font-weight: 300;
}

@media screen and (max-width: 1200px) {
    .menu {
        gap: 20px;
    }
}
</style>