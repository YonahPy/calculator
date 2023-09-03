<template>
    <main>
        <div class="header">
            <h2>Calc</h2>
            <button>Theme</button>
        </div>

        <display class="display" :result="dataEmited" :number="currentValue" :operator="operator">

        </display>

        <keyboard class="keyboard" @buttonClick="handleButtonClick">

        </keyboard>
    </main>
</template>

<script>
import display from './display.vue'
import keyboard from './keyboard.vue'

export default{
    components:{
        display,
        keyboard
    },
    data(){
        return{
            dataEmited: null,
            currentValue: null,
            operator: null,
            lastItem: null
            
        }
    },
    methods:{
        handleButtonClick(value){
            if (/^[0-9]+$/.test(value)){
                if(this.currentValue === null){
                    this.currentValue = Number(value);
                } else{
                    this.currentValue = this.currentValue * 10 + Number(value)
                    
                }
                this.lastItem = "number"
            } else if(/[+\-*/]/.test(value)){
                
                this.operator = value;
                this.dataEmited = this.currentValue + ' ' + this.operator;
                this.currentValue = null
                this.lastItem = "operator"
            } else if (value === '='){
                if(this.currentValue !== null && this.operator !== null){
                    this.performCalculation();
                }
            } else if (value === 'reset'){
                this.dataEmited = null;
                this.currentValue = null;
                this.operator = null;
            } else if (value === 'del'){
                this.deleteLastItem()
                this.lastItem = /[0-9]$/.test(value) ? 'number' : 'operator'
            } 
        },

        performCalculation(){
            const n1 = parseFloat(this.dataEmited)
            const n2 = this.currentValue
            let result = 0

            switch (this.operator){
                case '+':
                    result = n1 + n2;
                    break;
                case '-':
                    result = n1 - n2;
                    break;
                case '*':
                    result = n1 * n2;
                    break;
                case '/':
                    result = n1 / n2;
                    break
            }
            this.dataEmited = result
            this.currentValue = null
            this.operator = null
        },

        deleteLastItem(){
            console.log(this.lastItem)
            
                if (this.lastItem === 'number'){
                    this.currentValue = null;
                } else if (this.lastItem === 'operator'){
                    this.dataEmited = null
                }
            
        }
       
    },
    
}

</script>


<style>

*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

main{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: 100vw;
    height: 100vh;
}

.header, .display, .keyboard{
    background-color:hsl(224, 36%, 15%) ;
    width: 50vw;
    margin-bottom: 30px;

}
.header{
    display: flex;
    justify-content: space-between;
    padding: 10px;
    border-radius: 5px;
    background-color: transparent;
}



</style>