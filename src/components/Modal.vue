<template>
  <div class="backdrop" @click="closeModal">
    <div class="modal" :class="{sale: theme === 'sale'}" >
      <h2>{{header}}</h2>
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Modal',
  props: ['header', 'text', 'theme'],
  methods: {
    closeModal(){
      this.$emit('close');
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.modal{
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  background: white;
  border-radius: 10px;
}
.backdrop{
  top: 0;
  position: fixed;
  background: rgba(0,0,0,0.5);
  width: 100%;
  height: 100%;
}
.modal.sale{
  background: rgb(238, 146, 165);
}
</style>
