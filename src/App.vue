<script setup>
import { RouterView } from 'vue-router'
import MainLayout from "./layouts/MainLayout.vue"
import './assets/styles/main.scss';
</script>

<template>
  <MainLayout>
    <RouterView></RouterView>
  </MainLayout>
</template>