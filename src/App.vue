<template>
  <MainLayout />
  <div class="mt-10"><Page /></div>
</template>

<script setup>
import MainLayout from '../src/layouts/main.vue'
import Page from '../src/pages/home.vue'
</script>

<style>
html {
  height: fit-content;
  background: linear-gradient(
    90deg,
    rgba(206, 204, 229, 0.5) 0%,
    rgba(200, 200, 244, 0.5) 35%,
    rgba(171, 229, 241, 0.5) 100%
  );
}
</style>
