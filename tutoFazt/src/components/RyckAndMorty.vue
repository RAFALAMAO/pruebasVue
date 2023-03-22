<template lang="html">
  <div class="rick-body">
    <h1>Componente de Rick y Morty</h1>
    <div v-for="(item, index) in myArray"  :key="index">
      <p> {{ item.title }} </p>
    </div>
    <div class="usersWithImage">
      <div v-for="(user, idx) in users"  :key="idx">
        <img :src="user.image" alt="">
        <p>{{ user.name }}</p>
      </div>
    </div>
  </div>
</template>

<script>
  import axios from 'axios';

  export default {
    data() {
      return {
        users: [],
      }
    },

    // Parecido a un useEffect vacio
    created() {
      axios
        .get('https://rickandmortyapi.com/api/character/1,2,3,183,123,34')
        .then(res => {
          console.log(res.data);
          this.users = res.data;
        })
    }
  }
</script>

<style lang="css">
  .rick-body{
    background: rgb(9, 50, 86);
    color: rgb(183, 255, 189);
    border-radius: 30px;
    padding: 20px;
    margin-top: 20px;
  }
  .usersWithImage {
    display: grid;
    grid-template-columns: 1fr 1fr;
  }
</style>