<template lang="html">
  <div>
    <h1>El about</h1>
    <Test msg="Hola desde el componente padre" />
    <User />
    <br>
    <router-link to="/">Home</router-link>
  </div>
</template>

<script>
import Test from '@/components/Test.vue';
import User from '@/components/User.vue';

export default {
  name: 'AboutView',
  components: {
    Test,
    User,
  }
}
</script>

<style lang="css">

</style>