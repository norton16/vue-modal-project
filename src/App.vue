<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  <h1>{{ title }}</h1>
  <input type="text" ref="name">
  <button @click="handleClick">Click me</button>
  <div v-if="showModal">
    <Modal :header="header" :header2="header2" theme="sale"/>
  </div>
  <button @click="toggleModal">Show modal</button>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Modal from './components/Modal'

export default {
  name: 'App',
  components: {
    Modal
  },
  data() {
    return {
      title: 'My first Vue App',
      header: "example prop",
      header2: [1,2,3],
      showModal: false
    }
  },
  methods: {
    handleClick() {
      // Template ref - take DOM element and store in variable
      console.log(this.$refs.name)
      this.$refs.name.classList.add('active')
    },
    toggleModal() {
      this.showModal = !this.showModal
    }
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
</style>
