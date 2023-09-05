<template>
    <div class="display" :class="themes">
     {{ result }} {{ number}} 
       
    </div>
</template>

<script>
export default{
    props: ['result', 'number', 'operator', 'themes'],

}

</script>



<style >
    .display{
        padding: 25px;
        border-radius: 10px;
        font-size: 32px;
    }
    
    

</style>