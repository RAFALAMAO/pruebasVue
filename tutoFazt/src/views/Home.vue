<template lang="html">
  <div>
    <h1>El Home</h1>
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Que tal, buenas tardes :v"/>
    <RyckAndMorty/>
    <br>
    <router-link to="/about">About</router-link>
  </div>
</template>

<script>
import RyckAndMorty from "@/components/RyckAndMorty.vue";
import HelloWorld from "@/components/HelloWorld.vue";

export default {
  name: 'HomeView',
  components: {
    RyckAndMorty,
    HelloWorld
  }
}
</script>

<style lang="css">

</style>