<script setup>
import Display from './Display.vue';
import Keyboard from './Keyboard.vue';


</script>

<template>
    <div class="calculator" scoped>
        <p class="calculator__title">MOL - 5988</p>
        <Display class="calculator__display" />
        <Keyboard class="calculator__keyboard" />
    </div>
</template>

<style lang="scss">
    @import '../assets/scss/layout.scss';
</style>