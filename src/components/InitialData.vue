<template>
    <div>
        <h2>Расчет системы</h2>
        <div>
            <div class="data">
                <fieldset>
                    <legend>Исходные данные</legend>
                    <label for="displacement">Рабочий объём насоса: </label>
                    <input type="text" id="displacement" v-model="displacement">
                    <label for="pressure">Давление в системе: </label>
                    <input type="text" id="pressure" v-model="pressure">
                    <label for="rotation">Частота вращения: </label>
                    <input type="text" id="rotation" v-model="rotation">
                    <label for="efficiency">КПД: </label>
                    <input type="text" id="efficiency" v-model="efficiency">
                    <button class="btn" @click="calculateSystem">Рассчитать</button>
                </fieldset>
            </div>
        </div>
    </div>
    
</template>

<script>

export default {
    emits: ['calculate'],
    data () {
        return {
            displacement: 0,
            pressure: 0,
            rotation: 0,
            efficiency: 0.9,
            calcData: {
                torque: 0,
                power: 0,
                expenditure: 0
            }
        }
    },
    methods: {
        calculateSystem () {
            this.calcData.torque = this.displacement * this.pressure / 62
            this.calcData.expenditure = this.displacement * this.rotation * this.efficiency / 1000
            this.calcData.power =  this.calcData.expenditure * this.pressure / 600            
            this.$emit('calculate', this.calcData)
        }
    }  
}
</script>