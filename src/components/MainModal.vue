<template>
  <div class="backdrop" @click.self="clickHandler()">
    <div class="modal" :class="theme">
      <h1>{{header}}</h1>
      <p>{{content}}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: ['header', 'content', 'theme'],

  methods: {
    clickHandler(){
      this.$emit('close')
    }
  }
};
</script>

<style scoped>
.backdrop {
  position: fixed;
  top: 0;
  background: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100%;
}

.modal {
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  background-color: aliceblue;
  border-radius: 10px;
}

.success{
  color: aliceblue;
  background-color: darkcyan;
}

.danger{
  color: black;
  background-color: firebrick;
}
</style>