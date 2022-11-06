<script setup>
import Menu from '../components/ui/Menu.vue';
import Logo from '../components/icons/Logo.vue';
</script>

<template>
    <div class="section">
        <div class="section--sidebar">
            <Logo class="section--sidebar--logo" />

            <Menu class="section--sidebar--menu" />
        </div>

        <div class="section--content">
            <slot></slot>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.section {
    display: grid;
    grid-template-columns: 120px 1fr;

    &--sidebar {
        height: 100vh;
        display: grid;
        position: sticky;

        &--menu {
            background: #FFFFFF;
        }

        &--logo {
            position: absolute;
            z-index: 10;
            width: 90px;
            height: 62.1px;

            top: 30px;
            left: 15px;
        }
    }

}
</style>