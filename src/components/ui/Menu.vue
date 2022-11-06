<script setup>
import { onMounted, ref, watch } from 'vue';
import LogoWhite from '../icons/LogoWhite.vue';
import Logo from '../icons/Logo.vue';
import BurgerMenu from '../icons/BurgerMenu.vue';
import BurgerMenuClose from '../icons/BurgerMenuClose.vue';
import Navbar from '../ui/Navbar.vue';
import Telegram from '../icons/Telegram.vue';
import Vk from '../icons/Vk.vue';

const open = ref(false)
const menu = ref(null)

function closeIfClickedOutside(event) {
    if (menu.value && !menu.value.contains(event.target)) {
        open.value = false;
    }
}

watch(() => open.value, (isOpen) => {
    if (isOpen) {
        document.addEventListener('click', closeIfClickedOutside);
    } else {
        document.removeEventListener('click', closeIfClickedOutside);
    }
})
</script>

<template>
    <aside ref="menu" class="header">
        <Logo class="header--logo" />
        <button @click="open = !open" class="header--burger">
            <BurgerMenuClose v-show="open" />
            <BurgerMenu v-show="!open" />
            <span>меню</span>
        </button>
        <div class="menu" :class="[open ? 'menu--open' : 'menu--close']">
            <div class="menu--content">
                <Logo class="menu--logo" />

                <Navbar />

                <div class="menu--contacts">
                    <span>+7 987 654 32 10</span>
                    <a href="mailto:info@agro-man.ru">info@agro-man.ru</a>

                    <div class="menu--contacts--social">
                        <Telegram />
                        <Vk />
                    </div>
                </div>
            </div>
        </div>
    </aside>
</template>

<style lang="scss" scoped>
.header {
    display: grid;
    padding: 24px 24px;
    position: relative;

    display: grid;
    grid-auto-flow: column;
    justify-content: space-between;
    align-items: center;

    &--logo {
        display: block;
        width: 92px;
        height: 63px;
    }

    &--burger {
        display: grid;
        justify-self: end;
        position: relative;
        z-index: 20;
        mix-blend-mode: difference;
    }

    &--burger>span {
        display: none;
    }
}

.menu {
    position: absolute;
    width: 100%;
    color: #121715;

    top: 0;
    transition: background-color .3s cubic-bezier(0.46, 0.03, 0.85, 0.5);



    &--open {
        transform: translateY(0);
        background-color: #ffffff;
    }

    &--close {
        transform: translateY(-100vh);
        background-color: transparent;
    }

    &--logo {
        width: 91.45px;
        height: 63px;
    }

    &--content {
        padding: 24px;
    }
}

@media (min-width: 640px) {
    .header {
        align-content: center;
        justify-content: center;
        padding: 0;

        &--logo {
            display: none;
        }

        &--burger {
            grid-template-rows: 50px auto;
            gap: 22px;
            justify-items: center;
            align-items: end;
        }

        &--burger>span {
            display: block;
            text-transform: uppercase;
            writing-mode: tb-rl;
            transform: rotate(-180deg);
        }
    }

    .menu {
        width: max-content;
        padding-left: 120px;
        top: 0;
        bottom: 0;
        left: 0;

        &--open {
            background-color: #ffffff;
        }

        &--close {
            visibility: hidden;
            background-color: transparent;
        }

        &--logo {
            width: 135px;
            height: 93px;
        }

        &--content {
            display: grid;
            grid-template-rows: 3;
            align-content: space-between;
            height: 100%;

            padding: 36px 100px 90px 60px;
        }

        &--contacts {
            font-size: 24px;
            line-height: 30px;

            display: grid;
            gap: 10px;

            &--social {
                margin-top: 40px;

                display: grid;
                gap: 10px;
                grid-auto-flow: column;
                justify-content: start;
            }
        }
    }
}
</style>