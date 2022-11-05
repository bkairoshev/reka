<script setup>
import { onMounted, ref, watch } from 'vue';
import LogoWhite from '../icons/LogoWhite.vue';
import Logo from '../icons/Logo.vue';
import BurgerMenu from '../icons/BurgerMenu.vue';
import BurgerMenuClose from '../icons/BurgerMenuClose.vue';
import Navbar from '../ui/Navbar.vue';

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
        <LogoWhite class="header--logo" />
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
    background-color: #ffffff;
    top: 0;
    transition: transform .3s ease-in-out;

    &--open {
        transform: translateY(0);
    }

    &--close {
        transform: translateY(-100vh);
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
        transition: transform .3s ease-in-out;
        left: 0;

        &--open {
            transform: translateX(0);
        }

        &--close {
            transform: translateX(-200%);
        }

        &--logo {
            width: 135px;
            height: 93px;
        }

        &--content {
            padding: 36px 100px 90px 60px;
        }
    }
}
</style>