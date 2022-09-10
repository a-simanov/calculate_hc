<template>
    <div>
        <h2>Расчет системы</h2>
        <form @submit.prevent="calculate">
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
                    <button class="btn" >Рассчитать</button>
                </fieldset>
            </div>
        </form>
        <div class="data data_final">
            <p>Результат:</p>
            <p>Расчетный расход: {{ expenditure }}</p>
            <p>Крутящий мемент: {{ torque }}</p>
            <p>Мощность: {{ power }}</p>
        </div>
    </div>
    
</template>

<script>

export default {
    data () {
        return {
            displacement: 0,
            pressure: 0,
            rotation: 0,
            efficiency: 0.9,
            expenditure: 0,
            torque: 0,
            power: 0
        }
    },
    methods: {
        calculate () {
            this.expenditure = this.displacement * this.rotation * this.efficiency / 1000
            this.torque = this.displacement * this.pressure / 62
            this.power = this.expenditure * this.pressure / 600
        }
    }
}
</script>

<style scoped>
    .data fieldset {
        display: flex;
        flex-direction: column;
        align-items: center;
    }
</style>