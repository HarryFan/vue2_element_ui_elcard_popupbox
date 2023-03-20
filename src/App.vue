<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <MainTable />
    <ElCardPopUpBox />
  </div>
</template>

<script>
import ElCardPopUpBox from './components/ElCardPopUpBox.vue';
import MainTable from './components/MainTable.vue';
export default {
  name: 'App',
  components: {
    MainTable,
    ElCardPopUpBox
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
