<template>
  <div class="container2" :class="{'theme1': theme1Class, 'theme1':initialStateClass, 'theme2':theme2Class, 'theme3':theme3Class}">
    <div class="header">
        <h2>Calc</h2>
        <themeSwitcher @state="stateThemes">
    
        </themeSwitcher>
      </div>
      <calculator></calculator>
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
      initialStateClass:true,
      theme1Class: false,
      theme2Class: false,
      theme3Class: false

    }
  },
  methods:{
    stateThemes(initialState, theme1, theme2, theme3){
      this.initialStateClass = initialState;
      this.theme1Class = theme1;
      this.theme2Class = theme2;
      this.theme3Class = theme3;
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
}
.theme1{
  background-color:  hsl(222, 26%, 31%);
}
.theme2{
  background-color: hsl(0, 0%, 90%);
}
.theme3{
  background-color: hsl(268, 75%, 9%);
}

</style>
