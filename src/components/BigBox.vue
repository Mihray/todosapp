<template>
<div id="bigbox" class="bigbox">
        <div class="span-div">
            <span>~Today I need do~</span>
        </div>
</div>
</template>
<script>
export default {
  el:'bigbox',
  props: {
  }
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
}
.span-div{
    background-color: aqua;
    top:400px;
}
.span-div span{
    margin-top: 50px;
    font-weight: 600;
}
</style>