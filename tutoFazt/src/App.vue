<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <!-- <HelloWorld msg="Que tal, buenas tardes :v"/> -->
  <Test msg="Hola desde el componente padre" />
  <User />
  <RyckAndMorty/>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue';
import RyckAndMorty from "./components/RyckAndMorty.vue";
import Test from "./components/Test.vue";
import User from "./components/User.vue";

export default {
  name: 'App',
  components: {
    // HelloWorld,
    Test,
    User,
    RyckAndMorty
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
img {
  width: 80px;
}
</style>
