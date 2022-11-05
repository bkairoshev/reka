<script setup>
import Menu from '../components/ui/Menu.vue';
import Logo from '../components/icons/Logo.vue';
</script>

<template>
    <div class="section">
        <Logo class="section--logo" />
        <Menu />

        <slot></slot>
    </div>
</template>

<style lang="scss" scoped>
.section {
    position: relative;
    display: grid;
    grid-template-columns: 120px 1fr;

    &--logo {
        width: 90px;
        height: 62.1px;
        position: absolute;
        top: 30px;
        left: 15px;
    }
}
</style>