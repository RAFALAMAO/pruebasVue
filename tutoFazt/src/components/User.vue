<template lang="html">
  <div class="users">
    <h1>Componente user</h1>
    <ul>
      <li v-for="(user, idx) in users" :key="idx">
        {{user.name}} - {{user.email}}
        <button v-on:click="delUser(user)">X</button>
      </li>
    </ul>

    <form v-on:submit.prevent="addUser">
      <input type="text" v-model="newUser.name" placeholder="Nombre">
      <input type="email" v-model="newUser.email" placeholder="Email">
      <button type="submit">Agregar</button>
    </form>
  </div>
</template>

<script>
export default {
  name: 'UserTest',

  data() {
    return {
      users: [
        {
          name: 'Joe',
          email: 'joe@mail.com',
          contacted: false,
        },
        {
          name: 'Ryan',
          email: 'ryan@mail.com',
          contacted: false,
        },
        {
          name: 'Donna',
          email: 'donna@mail.com',
          contacted: true,
        }
      ],
      newUser: {}
    }
  },

  methods: {
    addUser() {
      this.users.push({
        name: this.newUser.name,
        email: this.newUser.email,
        contacted: false,
      });
      this.newUser = {};
    },
    delUser(user) {
      this.users.splice(this.users.indexOf(user), 1);
    }
  },
}
</script>

<style lang="css">
  .users {
    background: rgb(7, 7, 65);
    color: aliceblue;
    border-radius: 30px;
    padding: 20px;
  }
</style>