<script setup>
    const props = defineProps(['numbersDisplayEquations']);
</script>

<template>
    <div class="calculator__display">
        <h3 class="calculator__display-equation"> {{ numbersDisplayEquations }} </h3>
        <h2 class="calculator__display-result">13</h2>
    </div>
</template>

<style lang="scss">
    @import '../assets/scss/layout.scss';
</style>