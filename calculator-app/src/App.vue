<template>
  <div class="container2" :class="themeS">
    <div class="header">
        <h2>Calc</h2>
        <themeSwitcher @themeChange="selectedTheme">
    
        </themeSwitcher>
      </div>
      <calculator :themes="themeS"></calculator>
  </div>
  
</template>

<script>
import calculator from './components/calculator.vue'
import themeSwitcher from './components/themeSwitcher.vue'


export default{
  components:{
    calculator,
    themeSwitcher
  },
  data(){
    return{
      themeS: ''

    }
  },
  methods:{
      selectedTheme(theme){
        this.themeS = theme
    }
  }
}
</script>


<style >

@import url('https://fonts.googleapis.com/css2?family=League+Spartan:wght@700&display=swap');


body{
  
  height: 100vh;
  width: 100vw;
 font-family: 'League Spartan', sans-serif;;
  
}
.header{
    display: flex;
    justify-content: space-between;
    padding: 10px;
    border-radius: 5px;
    background-color: transparent;
    width: 50vw;
    margin-bottom: 30px;
}
.container2{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: 100vw;
    height: 100vh;
    background-color:hsl(222, 26%, 31%);
    color: hsl(0, 0%, 100%);
    
}
.container2 .display{
  background-color:hsl(224, 36%, 15%) ;
}
.container2 .circle{
  background-color: hsl(6, 63%, 50%);
}
.container2 .button-themes{
    background-color: hsl(224, 36%, 15%);
}
.container2 .keyboard{
  background-color: hsl(223, 31%, 20%);
}
.container2 .keyboard > button{
  background-color: white;
  color: hsl(224, 28%, 35%);
}
.container2 .keyboard .result{
  background-color: hsl(6, 63%, 50%);
  color: white;
}
.container2 .keyboard .del-reset{
  background-color: hsl(225, 21%, 49%);
  color: white;
}


.theme-two {
  background-color:hsl(0, 0%, 90%) ;
  color:  hsl(60, 10%, 19%);
}

.theme-two .display{
  background-color: hsl(0, 4%, 77%);
}
.theme-two .circle{
  background-color: hsl(25, 99%, 27%);
}
.theme-two .keyboard > button{
  background-color: hsl(45, 7%, 89%);
  color:  hsl(60, 10%, 19%);
}

.theme-two .keyboard{
  background-color: hsl(0, 5%, 81%);
}
.theme-two .keyboard .result{
  background-color: hsl(25, 99%, 27%);
  color: white;
}
.theme-two .keyboard .del-reset{
  background-color: hsl(185, 42%, 37%);
  color: white;
}



.theme-three{
  background-color: hsl(268, 75%, 9%);
  color: hsl(52, 100%, 62%);
}
.theme-three .display{
  background-color: hsl(268, 71%, 12%);
}
.theme-three .circle{
  background-color: hsl(176, 100%, 44%);
}
.theme-three .keyboard > button{
  background-color:hsl(268, 47%, 21%);
  color: hsl(52, 100%, 62%);
}
.theme-three .keyboard{
  background-color: hsl(268, 71%, 12%);
}
.theme-three .keyboard .result{
  background-color: hsl(176, 100%, 44%);
}
.theme-three .keyboard .del-reset{
  background-color: hsl(285, 91%, 52%);
}


</style>
