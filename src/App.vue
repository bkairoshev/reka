<script setup>
import DefaultLayout from './layouts/Default.vue';
import Main from './components/sections/Main.vue';
import About from './components/sections/About.vue';
import Brands from './components/sections/Brands.vue';
</script>

<template>
  <Main />
  <DefaultLayout>
    <About />
    <Brands />
  </DefaultLayout>
</template>
