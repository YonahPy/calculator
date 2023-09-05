<template>
    <div class="container">
        <div class="numbers">
            <span>1</span>
            <span>2</span>
            <span>3</span>
        </div>
        <div class="button-themes">
            <span class="circle" @click="toggleAnimation" :class="{'animation-one': theme1,'theme-two': theme2, 'theme-three': theme3, 'animation-two': theme2, 'animation-three': theme3}" id="circle">
               
            </span>
        </div>
    </div>
</template>

<script>


export default{

    data(){
        return{
            theme1: false,
            initialState: true,
            theme2:false,
            theme3:false
        }
    },
    methods:{
      toggleAnimation() {
        
        if (this.initialState) {
          this.initialState = false;
          this.theme2 = true;
          this.theme3 = false;
          this.theme1 = false
          
        } else if (this.theme2) {
          this.initialState = false;
          this.theme2 = false;
          this.theme3 = true;
          this.theme1 = false
          
        } else if (this.theme3) {
          this.initialState = true
          this.theme1 = true
          this.theme2 = false;
          this.theme3 = false;
          
        }
        this.$emit('themeChange', this.getCurrentTheme())
        
        
      },
      getCurrentTheme(){
        if (this.theme2) return 'theme-two';
        if (this.theme3) return 'theme-three';
      }
    }}

</script>

<style>
.container{
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 70px;

}
.numbers{
    display: flex;
    gap: 13px;
    margin-bottom: 3px;
}
.button-themes{
    
    width: 100%;
    height: 30px;
    border-radius: 50px;
    display: flex;
    align-items: center;


}
.circle{
    width: 30%;
    height: 20px;
    border-radius: 50%;
    margin-left: 5px;
    
    
}

.animation-two{
  animation: themeTwo 1s ease-out forwards;
  
  
}
.animation-three{
  animation: themeThree 1s ease-out forwards;
  
  
}
.animation-one{
  animation: themeOne 1s ease-out;
  
  
}


p{
    font-size: 14px;
    margin-right: 10px;
}



@keyframes themeTwo{
  0%{
    transform: translateX(0%);
  }
  100%{
    transform: translateX(90%);
  }
  
}
@keyframes themeThree{
  0%{
    transform: translateX(90%);
    
  }
  100%{
    transform: translateX(190%);
  }
}
@keyframes themeOne{
  0%{
    transform: translateX(190%);
  }
  100%{
    transform: translateX(0%);
  }
}
</style>