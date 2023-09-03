<template>
    <div class="container">
        <div class="numbers">
            <span>1</span>
            <span>2</span>
            <span>3</span>
        </div>
        <div class="button-themes">
            <span class="circle" :class="{'circle-animation-1': isAnimating1, 'circle-animation-2': isAnimating2, 'circle-animation-3': isAnimating3}" @click="toggleAnimation">
                
            </span>
        </div>
    </div>
</template>

<script>
export default{

    data(){
        return{
            isAnimating1: false,
            isAnimating2: false,
            isAnimating3: false,
        }
    },
    methods:{
        toggleAnimation() {
            if (!this.isAnimating1 && !this.isAnimating2 && !this.isAnimating3) {
            this.isAnimating1 = true;
            } else if (this.isAnimating1) {
            this.isAnimating1 = false;
            this.isAnimating2 = true;
            } else if (this.isAnimating2) {
            this.isAnimating2 = false;
            this.isAnimating3 = true;
            } else {
            this.isAnimating3 = false;
            this.isAnimating1 = true;
            }
            }
}}

</script>

<style>
.container{
    display: flex;
    flex-direction: column;
    align-items: center;

}
.numbers{
    display: flex;
    gap: 13px;
    margin-bottom: 3px;
}
.button-themes{
    background-color: hsl(224, 36%, 15%);
    width: 70px;
    height: 30px;
    border-radius: 50px;
    display: flex;
    align-items: center;


}
.circle{
    background-color: hsl(6, 63%, 50%);
    width: 20px;
    height: 20px;
    border-radius: 50%;
    margin-left: 5px;
    
}
.circle-animation{
    animation: circle 1s linear;
}
p{
    font-size: 14px;
    margin-right: 10px;
}

@keyframes circle-1 {
  0% {
    transform: translateX(0%);
  }
  100% {
    transform: translateX(0%);
  }
}

@keyframes circle-2 {
  0% {
    transform: translateX(0%);
  }
  100% {
    transform: translateX(50%);
  }
}

@keyframes circle-3 {
  0% {
    transform: translateX(0%);
  }
  100% {
    transform: translateX(100%);
  }
}
</style>