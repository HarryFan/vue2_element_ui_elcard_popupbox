<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <MainTable />

  </div>
</template>

<script>
  import MainTable from './components/MainTable.vue';
  export default {
    name: 'App',
    components: {
      MainTable
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