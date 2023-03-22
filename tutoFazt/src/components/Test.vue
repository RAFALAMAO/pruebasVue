<template>
  <div>
    <h1>Mi primer componente :3</h1>

    <!--  -->
    <h2>Tomado desde la data</h2>
    <p class="nombre">{{ user.firstName }}</p>
    <div v-html="myHtml"/>
    <div v-text="title"/>

    <!--  -->
    <h2>Algunos usos de los inputs</h2>
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
    <h2>Condicional</h2>
    <div v-if="showName">
      <p>El valor de verdadero</p>
    </div>
    <div v-else>
      <p>El valor de falso</p>
    </div>

    <!-- For -->
    <h2>For</h2>
    <div v-for="(item, index) in myArray"  :key="index">
      <p> {{ item.title }} </p>
    </div>

    <!--  -->
    <h2>Imprimiendo desde computado</h2>
    <p class="nombre"> {{ fullName }} </p>

    <!--  -->
    <h2>Imprimiendo desde un prop</h2>
    <p> {{ msg }} </p>


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
        firstName: 'Aarón',
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

  // Se computan automaticamente
  computed: {
    fullName() {
      return `${this.user.firstName} ${this.user.lastName}`
    }
  },

  // Los props de algun componente padre
  props: {
    msg: {
      type: String,
      default: 'el default we'
    }
  }
}
</script>

<style scoped>
  .nombre {
    color: red;
  }
  h2 {
    color: rgb(10, 10, 139);
    text-align: left;
    margin-left: 15%;
  }
</style>