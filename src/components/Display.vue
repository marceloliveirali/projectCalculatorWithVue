<script setup>
    const props = defineProps(['numbersDisplayEquations', 'numbersDisplayResult']);
</script>

<template>
    <div class="calculator__display">
        <h3 class="calculator__display-equation"> {{ numbersDisplayEquations }} </h3>
        <h2 class="calculator__display-result"> {{ numbersDisplayResult }} </h2>
    </div>
</template>

<style lang="scss">
    @import '../assets/scss/layout.scss';
</style>