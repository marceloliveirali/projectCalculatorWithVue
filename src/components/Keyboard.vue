<script setup>
    import { reactive } from 'vue';
    import Display from './Display.vue';

    const stateKeyboard = reactive({

        currentValue: '123',
    });

    function clearDisplay() 
    {

        return this.stateKeyboard.currentValue = ' '; 
    }

</script>

<template>
    <Display class="calculator__display" v-bind:numbers-display-equations="stateKeyboard.currentValue" />

    <div class="calculator__keyboard">
        <button type="button" class="calculator__keyboard-boxReset" @click="clearDisplay"> C </button>
        <button type="button" class="calculator__keyboard-boxDel" @click="insert('DEL')"> DEL </button>
        <button type="button" class="calculator__keyboard-boxSignal" @click="insert('÷')"> ÷ </button>
        <button type="button" class="calculator__keyboard-boxSignal" @click="insert('x')"> x </button>

        <button type="button" class="calculator__keyboard-box" @click="insert('7')"> 7 </button>
        <button type="button" class="calculator__keyboard-box" @click="insert('8')"> 8 </button>
        <button type="button" class="calculator__keyboard-box" @click="insert('9')"> 9 </button>
        <button type="button" class="calculator__keyboard-boxSignal" @click="insert('-')"> - </button>

        <button type="button" class="calculator__keyboard-box" @click="insert('4')"> 4 </button>
        <button type="button" class="calculator__keyboard-box" @click="insert('5')"> 5 </button>
        <button type="button" class="calculator__keyboard-box" @click="insert('6')"> 6 </button>
        <button type="button" class="calculator__keyboard-boxSignal" @click="insert('+')"> + </button>

        <button type="button" class="calculator__keyboard-box" @click="insert('1')"> 1 </button>
        <button type="button" class="calculator__keyboard-box" @click="insert('2')"> 2 </button>
        <button type="button" class="calculator__keyboard-box" @click="insert('3')"> 3 </button>
        <button type="button" class="calculator__keyboard-boxEqual" @click="insert('=')"> = </button>
        
        <button type="button" class="calculator__keyboard-box" @click="insert('0')"> 0 </button>
        <button type="button" class="calculator__keyboard-box" @click="insert('.')"> . </button>
        <button type="button" class="calculator__keyboard-boxEnter" @click="insert('ENTER')"> ENTER </button>
    </div>
</template>

<style scoped lang="scss">
    @import '../assets/scss/layout.scss';
</style>