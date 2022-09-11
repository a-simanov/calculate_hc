<template>
  <div class="component">
    <initial-data @calculate="calculate"></initial-data>
    <final-data :finalData="finalData"></final-data>
    <!-- <hydro-cilinder></hydro-cilinder> -->
  </div>
</template>

<script>
import InitialData from './components/InitialData.vue'
//import HydroCilinder from './components/HydroCilinder.vue'
import FinalData from './components/FinalData.vue'

export default {
  name: 'App',
  data () {
    return {
      finalData: {
        torque: 0,
        power: 0,
        expenditure: 0
      }    
    }
  },
  components: {
    InitialData,
    //HydroCilinder,
    FinalData
  },
  methods: {
    calculate (data) {      
      this.finalData = data
    }
  }
}
</script>