<template>
    <div>
        <h2>Расчет гидросистемы</h2>
            <div class="data">
                <fieldset>
                    <legend>Исходные данные:</legend>
                    <label for="displacement">Рабочий объём насоса, мм<sup>3</sup>: </label>
                    <input type="text" id="displacement" v-model.number="displacement">
                    <span class="error" v-if="typeof(this.displacement) !== 'number'">Введите число</span>
                    <label for="pressure">Давление в системе, бар: </label>
                    <input type="text" id="pressure" v-model.number="pressure">
                    <span class="error" v-if="typeof(this.pressure) !== 'number'">Введите число</span>
                    <label for="rotation">Частота вращения, мин<sup>-1</sup>: </label>
                    <input type="text" id="rotation" v-model.number="rotation">
                    <span class="error" v-if="typeof(this.rotation) !== 'number'">Введите число</span>
                    <label for="efficiency">КПД: </label>
                    <input type="text" id="efficiency" v-model.number="efficiency">
                    <span class="error" v-if="typeof(this.efficiency) !== 'number'">Введите число</span>
                    <button class="btn" @click="calculateSystem">Рассчитать</button>
                </fieldset>
            </div>
    </div>    
</template>

<script>

export default {
    emits: ['calculateHS'],
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
            this.$emit('calculateHS', this.calcData)
        }
    }  
}
</script>