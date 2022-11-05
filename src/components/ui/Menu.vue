<script setup>
import { ref } from 'vue';
import Logo from '../icons/Logo.vue';
import BurgerMenu from '../icons/BurgerMenu.vue';
import BurgerMenuClose from '../icons/BurgerMenuClose.vue';
import Navbar from '../ui/Navbar.vue';

const open = ref(false)
</script>

<template>
    <aside class="sidebar" :class="[open ? 'sidebar--open' : 'sidebar--close']">
        <button @click="open = !open" class="burger">
            <BurgerMenuClose v-if="open" />
            <BurgerMenu v-else />
            <span>меню</span>
        </button>
        <div class="menu" :class="[open ? 'menu--open' : 'menu--close']">
            <div class="menu--content">
                <Logo class="menu--logo" />

                <Navbar/>

                <div class="menu--contacts">

                </div>
            </div>
        </div>
    </aside>
</template>

<style lang="scss" scoped>
.sidebar {
    display: grid;
    align-content: center;
    justify-content: center;

    position: relative;
    color: #FFFFFF;

    &--open {
        color: #000;
    }
}

.menu {
    position: absolute;
    width: max-content;
    padding-left: 120px;
    background-color: #ffffff;
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

.burger {
    display: grid;
    grid-template-rows: 50px auto;
    gap: 22px;
    justify-items: center;
    align-items: end;

    position: relative;
    z-index: 20;
}

.burger>span {
    text-transform: uppercase;
    writing-mode: tb-rl;
    transform: rotate(-180deg);
}
</style>