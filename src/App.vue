<template>
  <img alt="Vue logo" src="./assets/logo.png">
  {{ message }}
  <input class="form-control" type="text" ref="book">
  <button class="btn btn-primary" @click="handClic">Click</button>
</template>

<script>

export default {
  name: 'App',
  data(){
    return {
      message: "Prostam"
    }
  },
    methods: {
      handClic(){
        console.log( this.$refs.book.value);
        this.$refs.book.classList.add('active');
        this.$refs.book.focus();

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
