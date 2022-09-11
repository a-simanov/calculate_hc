<template>
    <div>
        <h2>Расчет гидроцилиндра</h2>
        <form @submit.prevent="calculateHC">
            <div class="data">
                <fieldset>
                    <legend>Исходные данные</legend>
                    <label for="plungerDiametr">Диаметр поршня: </label>
                    <input type="text" id="plungerDiametr" v-model="plungerDiametr">
                    <label for="workLength">Длина хода: </label>
                    <input type="text" id="workLength" v-model="workLength">                    
                    <label for="stockDiametr">Диаметр штока: </label>
                    <input type="text" id="stockDiametr" v-model="stockDiametr">
                    <button class="btn" >Рассчитать</button>
                </fieldset>
            </div>
        </form>
        <div class="data data_final">
            <p>Результат:</p>
            <p>Объём поршневой части: {{ valuePlunger }}</p>
            <p>Объём штоковой части: {{ valueStock }}</p>
            <p>Время рабочего хода: {{ power }}</p>
            <p>Время холостого хода: {{ power }}</p>
            <p>Усилие штока: {{ power }}</p>
        </div>
    </div>
</template>

<script>
export default {
    data () {
        return {
            plungerDiametr: 0,
            workLength: 0,
            stockDiametr: 0,
            valuePlunger: 0,
            valueStock: 0,

        }
    },
    methods: {
        calculateHC () {
            this.valuePlunger = (Math.pow(this.plungerDiametr, 2)  * Math.PI * this.workLength / 4) / 1000000
            this.valueStock = (((Math.pow(this.plungerDiametr, 2)  * Math.PI / 4) - (Math.pow(this.stockDiametr, 2)  * Math.PI / 4)) * this.workLength) / 1000000
        }
    }
}
</script>
