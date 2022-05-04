<template>
  <h1>{{ title }}</h1>
  <teleport to=".modals"  v-if="showModal">
    <Modal :header="header" theme="sale"  @close="showModalHandler" >
      <p>Kru Kotia</p>
    </Modal>
  </teleport>
  <p>Welcome!</p>
  <button @click="showModalHandler">Show Model</button>
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: {
    Modal,
  },
  data() {
    return {
      title: "Hello From Vue!",
      header: "Welcome!",
      showModal: false
    };
  },
  methods:{
    showModalHandler(){
      this.showModal = !this.showModal;
    }
  }
};
</script>

<style>
#app, .modals {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
