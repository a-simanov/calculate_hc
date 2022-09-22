<template>
  <div class="component">
    <div class="btnGroup">
      <button class="btnToggle" @click="calculateCheck = true" v-if="!calculateCheck">Расчет гидросистемы &#8618;</button>
      <button class="btnToggle btnToggle_right" @click="calculateCheck = false" v-if="calculateCheck">&#8617; Расчет гидроцилиндра</button>
    </div>
    <initial-data @calculateHS="calculateHS" v-if="calculateCheck"></initial-data>
    <final-data :finalData="finalData" v-if="systemVisibility && calculateCheck"></final-data>
    <hydro-cilinder @calculateHC="calculateHC" :finalData="finalData" v-if="!calculateCheck"></hydro-cilinder>
    <final-HC :finalHC="finalHC" v-if="cilinderVisibility && !calculateCheck"></final-HC>
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
        expenditure: 0,
      },
      finalHC: {
        valuePlunger: 0,
        valueStock: 0,
        workingTime: 0,
        emptyTime: 0,
        force: 0,
      },
      systemVisibility: false,
      cilinderVisibility: false,
      calculateCheck: true
    }
  },
  components: {
    InitialData,
    HydroCilinder,
    FinalData,
    FinalHC,
  },
  methods: {
    calculateHS (data) {      
      this.finalData = data
      this.systemVisibility = true
    },
    calculateHC (data) {      
      this.finalHC = data
      this.cilinderVisibility = true
    }
  }
}
</script>