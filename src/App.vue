<template>
  <div class="component">
    <initial-data @calculateHS="calculateHS"></initial-data>
    <final-data :finalData="finalData"></final-data>
    <hydro-cilinder @calculateHC="calculateHC" :finalData="finalData"></hydro-cilinder>
    <final-HC :finalHC="finalHC"></final-HC>
  </div>
</template>

<script>
import InitialData from './components/InitialData.vue'
import HydroCilinder from './components/HydroCilinder.vue'
import FinalData from './components/FinalData.vue'
import FinalHC from './components/finalHC.vue'

export default {
  name: 'App',
  data () {
    return {
      finalData: {
        torque: 0,
        power: 0,
        expenditure: 0
      },
      finalHC: {
        valuePlunger: 0,
        valueStock: 0,
        workingTime: 0,
        emptyTime: 0,
        force: 0
      }
    }
  },
  components: {
    InitialData,
    HydroCilinder,
    FinalData,
    FinalHC
  },
  methods: {
    calculateHS (data) {      
      this.finalData = data
    },
    calculateHC (data) {      
      this.finalHC = data
    }
  }
}
</script>