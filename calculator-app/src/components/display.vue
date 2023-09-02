<template>
    <div class="display">
        {{ value }}
    </div>
</template>

<script>
export default{
    props: ['value'],


    data(){
        dataChecked: null
    },


    methods:{
        valueValidation(){
            this.value
        }
    }
}

</script>



<style scoped>
    .display{
        padding: 25px;
        border-radius: 10px;
        font-size: 32px;

    }

</style>