<script setup>
    import { reactive } from 'vue';
    import Display from './Display.vue';

    const stateKeyboard = reactive({

        currentValue: '',
        currentResult: ''
    });

    function clearDisplay() 
    {
        stateKeyboard.currentValue = '';

        return stateKeyboard.currentResult = '';
    }

    function delLastDisplay() 
    {
        return stateKeyboard.currentValue = stateKeyboard.currentValue.slice(0, -1);
    }

    function insert(event) 
    {
        stateKeyboard.currentValue += event;

        return qntDigit();
    }

    function qntDigit() 
    {
        if (stateKeyboard.currentValue.length <= 12) 
        {
            return stateKeyboard.currentValue;
        }
        else 
        {
            return stateKeyboard.currentResult = 'limite excedido';
        }
    }

    function calculate()
    {
        try 
        {
            const evaluation = eval(stateKeyboard.currentValue.replace(/x/g, '*').replace(/÷/g, '/'));

            return stateKeyboard.currentResult = parseFloat(evaluation.toFixed(4));
        }
        catch (error) 
        {
            return stateKeyboard.currentResult = 'Erro no sistema'; 
        }
    }

    function storeResult() 
    {
        if (stateKeyboard.currentResult !== '') 
        {
            stateKeyboard.currentValue = stateKeyboard.currentResult.toString();

            return stateKeyboard.currentResult = '';
        }
    }

</script>

<template>
    <Display class="calculator__display" v-bind:numbers-display-equations="stateKeyboard.currentValue" 
    v-bind:numbers-display-result="stateKeyboard.currentResult" />

    <div class="calculator__keyboard">
        <button type="button" class="calculator__keyboard-boxReset" @click="clearDisplay()"> C </button>
        <button type="button" class="calculator__keyboard-boxDel" @click="delLastDisplay()"> DEL </button>
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
        <button type="button" class="calculator__keyboard-boxEqual" @click="calculate()"> = </button>
        
        <button type="button" class="calculator__keyboard-box" @click="insert('0')"> 0 </button>
        <button type="button" class="calculator__keyboard-box" @click="insert('.')"> . </button>
        <button type="button" class="calculator__keyboard-boxEnter" @click="storeResult()"> ENTER </button>
    </div>
</template>

<style scoped lang="scss">
    @import '../assets/scss/layout.scss';
</style>