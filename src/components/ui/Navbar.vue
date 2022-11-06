<script setup>
import { ref } from "vue"

const links = [
    {
        title: "Тепличные комплексы",
        // childs: [
        //     {
        //         title: 'ТК Сосногорский'
        //     },
        //     {
        //         title: 'ТК Новочебоксарский'
        //     },
        //     {
        //         title: 'ТК Пермский'
        //     },
        //     {
        //         title: 'тк камчатский'
        //     },
        // ]
    },
    {
        title: "Компания"
    },
    {
        title: "Бренды",
        // childs: [
        //     {
        //         title: '«спелые витамины» '
        //     },
        //     {
        //         title: `«спелые витамины».
        //         Розовый томат`,
        //     },
        //     {
        //         title: `«спелые витамины».
        //                 короткоплодный огурец`
        //     },
        // ]
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
                <a href="#"> {{ link.title }}</a>

                <ul class="nav--child-items" v-if="link.childs">
                    <li v-for="(child, i) in link.childs" :key="i" class="nav--child-item">
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

    font-size: 24px;
    line-height: 30px;

    &--items {
        display: grid;
        gap: 50px;
    }

    &--item {
        display: grid;
        grid-template-columns: auto 1fr;
        gap: 77px;
        position: relative;
        z-index: 10;
    }

    &--item:hover {
        color: rgba(18, 23, 21, 0.3);
    }

    &--item:hover>&--child-items {
        display: grid;
        gap: 40px;
    }

    &--child-items {
        position: sticky;
        z-index: 20;
        display: none;
        left: 100%;
        top: 0;
    }

    &--child-item {
        top: 0;
        position: relative;
        display: grid;
        grid-template-columns: auto 1fr;
        align-items: center;
        gap: 77px;

        &::before {
            content: "";
            width: 70px;
            height: 0px;
        }

        &:first-child {
            &::before {
                content: "";
                border-top: 1px solid #121715;
                width: 70px;
                height: 0px;
            }
        }
    }



    &--child-item:hover {
        color: rgba(18, 23, 21, 0.3);
    }
}
</style>