<template>
  <div class="component">
    <h1>Расчёт гидроцилиндра.</h1>
    <initial-data @calculate-data="'calculateData'"></initial-data>
    <final-data></final-data>
  </div>
</template>

<script>
import InitialData from './components/InitialData.vue'

export default {
  name: 'App',
  components: {
    InitialData
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
