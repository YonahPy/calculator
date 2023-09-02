<template>
<div class="keyboard">
   <button @click="handleButtonClick('7')">7</button>
   <button @click="handleButtonClick('8')">8</button>
   <button @click="handleButtonClick('9')">9</button>
   <button @click="handleButtonClick('Del')">Del</button>
   <button @click="handleButtonClick('4')">4</button>
   <button @click="handleButtonClick('5')">5</button>
    <button @click="handleButtonClick('6')">6</button>
    <button @click="handleButtonClick('+')">+</button>
    <button @click="handleButtonClick('1')">1</button>
    <button @click="handleButtonClick('2')">2</button>
    <button @click="handleButtonClick('3')">3</button>
    <button @click="handleButtonClick('-')">-</button>
    <button @click="handleButtonClick('.')">.</button>
    <button @click="handleButtonClick('0')">0</button>
    <button @click="handleButtonClick('/')">/</button>
    <button @click="handleButtonClick('x')">x</button>
    <button class="reset" @click="handleButtonClick('reset')">RESET</button>
    <button class="result" @click="handleButtonClick('=')">=</button>
</div>    
</template>


<script>
export default{

    methods:{
        handleButtonClick(value){
            this.$emit('buttonClick', value)
        }
    }
}

</script>

<style scoped>
    .keyboard{
        display: grid;
        grid-template-columns: repeat(4, 1fr);
        padding: 25px;
        border-radius: 10px;
        gap: 15px;
    }
    button{
        height: 40px;
        border-radius: 10px;
        border: none;
        font-size: 18px;
    }
    .reset,
    .result {
    grid-column: span 2;
    }

</style>