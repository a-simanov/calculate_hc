<template>
  <div class="component">
    <initial-data @calculate-data="'calculateData'"></initial-data>
    <hydro-cilinder></hydro-cilinder>
  </div>
</template>

<script>
import InitialData from './components/InitialData.vue'
import HydroCilinder from './components/HydroCilinder.vue'

export default {
  name: 'App',
  components: {
    InitialData,
    HydroCilinder
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
