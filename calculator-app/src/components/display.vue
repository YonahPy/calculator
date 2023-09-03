<template>
    <div class="display">
     {{ result }} {{ number}} 
       
    </div>
</template>

<script>
export default{
    props: ['result', 'number', 'operator'],

}

</script>



<style scoped>
    .display{
        padding: 25px;
        border-radius: 10px;
        font-size: 32px;

    }

</style>