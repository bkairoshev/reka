<script setup>
import { ref } from "vue"

const links = [
    {
        title: "Тепличные комплексы",
        childs: [
            {
                title: 'ТК Сосногорский'
            },
            {
                title: 'ТК Новочебоксарский'
            },
            {
                title: 'ТК Пермский'
            },
            {
                title: 'тк камчатский'
            },
        ]
    },
    {
        title: "Компания"
    },
    {
        title: "Бренды",
        childs: [
            {
                title: '«спелые витамины» '
            },
            {
                title: `«спелые витамины».
                Розовый томат`,
            },
            {
                title: `«спелые витамины».
                        короткоплодный огурец`
            },
        ]
    },
    {
        title: "Вакансии"
    },
    {
        title: "Закупки"
    },
    {
        title: "Контакты"
    },
]


</script>

<template>
    <nav class="nav">
        <ul class="nav--items" id="aaaa">
            <li v-for="(link, i) in links" :key="i" class="nav--item">
                {{ link.title }}
                <ul class="nav--child-items" v-if="link.childs">
                    <li v-for="(child, i) in link.childs" :key="i" class="nav--child-item">
                        <svg width="70" height="1" viewBox="0 0 70 1" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <line y1="0.5" x2="70" y2="0.5" stroke="#121715" />
                        </svg>
                        <a href="#"> {{ child.title }}</a>
                    </li>
                </ul>
            </li>
        </ul>
    </nav>
</template>

<style lang="scss" scoped>
.nav {
    text-transform: uppercase;
    color: #121715;

    &--items {}

    &--item {
        display: grid;
        position: relative;
    }

    &--item:hover {
        color: rgba(18, 23, 21, 0.3);
    }

    &--item:hover>&--child-items {
        grid-template-columns: auto auto;
        gap: 77px;
        display: block;
        transition: opacity .3s;
    }

    &--child-items {
        position: sticky;
        left: 100%;
        position: none;
        display: none;
        color: #121715;
    }

    &--child-item {
        display: grid;
        grid-template-columns: auto 1fr;
        align-items: center;
        gap: 77px;
    }

    &--child-item:hover {
        color: rgba(18, 23, 21, 0.3);
    }
}
</style>