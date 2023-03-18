<template>
  <div>
    <h1>Mi primer componente xd</h1>
    <h2>{{ user.firstName }}</h2>
    <div v-html="myHtml"/>
    <div v-text="title"/>

    <input type="text" v-model="user.firstName">
    <input type="text" name="perro" v-on:keyup="typing">
    <input type="text" name="perros" v-on:keyup.enter="EnterWord">
    <button
      type="button"
      v-on:click="justPrint(user.firstName)"
    >
      CLICK ME
    </button>

    <!-- Condicionales -->
    <div v-if="showName">
      <p>El valor de verdadero</p>
    </div>
    <div v-else>
      <p>El valor de falso</p>
    </div>

    <!-- For -->
    <div v-for="(item, index) in myArray"  :key="index">
      <p> {{ item.title }} </p>
    </div>


  </div>
</template>

<script>
export default {
  name: 'TestMy',
  // Se simula un objeto de data
  data() {
    return {
      title: 'Hola desde data',
      user: {
        firstName: 'joe',
        lastName: 'Juarez'
      },
      myHtml: `
        <p>Buenas desde el objeto xd<p/>
      `,
      showName: false,
      myArray: [
        { title: 'Comer' },
        { title: 'Correr' },
        { title: 'Respirar' },
      ],
      fullData: {}
    }
  },

  // Metodos
  methods: {
    justPrint(name) {
      console.log(`Clic we ${name}`)
    },
    typing({ target }) {
      console.log(target.value);
    },
    EnterWord(){
      console.log('Se dio el enter we')
    },
  },
}
</script>

<style scoped>
  
</style>