<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  <BigBox/>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import BigBox from './components/BigBox.vue';

export default {
  name: 'App',
  components: {
    BigBox
}
}
</script>

<style>
#app {
  /* font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50; */
  /* margin-top: 60px; */
}
body{
  background-color: rgb(251,182,177);
  padding: 0;
  margin:0;
}
</style>
