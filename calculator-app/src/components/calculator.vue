<template>
    <main>
        <div class="header">
            <h2>Calc</h2>
            <button>Theme</button>
        </div>

        <display class="display" :value="dataEmited">

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
            dataEmited: [],
            
            
        }
    },
    methods:{
        handleButtonClick(value){
            if (/^[1-9]+$/.test(value)){
                const numericValue = Number(value);
                this.dataEmited = numericValue
            } else{
                this.dataEmited = value
            }
        },
       
    }
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