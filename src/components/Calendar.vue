<script setup>
import AppleIcon from './icons/AppleIcon.vue';
</script>

<template>
    <div class="logo-space">
        <AppleIcon class="icon"></AppleIcon>
    <h1>Aplikacja do liczenia kalorii</h1>
    </div>
    
</template>

<style lang="scss" scoped>
    .logo-space{
        display: flex;
        background: var(--color-primary-green);
        svg{
           margin: auto 0 auto 0; 
        }
    }
</style>