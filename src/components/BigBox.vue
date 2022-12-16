<template>
<div id="bigbox" class="bigbox">
        <span>~Today I need do~</span>
        <!-- <input type="text">
        <button>submit</button> -->
        <InputClick/>
</div>
</template>
<script>
import InputClick from './InputClick.vue';
export default {
    props: {},
    components: { InputClick }
}

</script>
<style scoped>
.bigbox{
    width:400px;
    height:400px;
    background-color:rgb(240,240,240);
    border-radius:10%;
    margin: 0 auto;
    margin-top: 100px;
    border:1px solid rgb(240,240,240);
}
span{
    /* position: absolute; */
    margin-top: 50px;
    font-weight: 600;
    display:block;
    width: 400px;
    text-align: center;
}
</style>