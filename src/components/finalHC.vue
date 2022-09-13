<template>
    <div class="data data_final">
        <p>Результат:</p>
        <p>Объём поршневой части: {{ finalHC.valuePlunger }}, мм<sup>3</sup></p>
        <p>Объём штоковой части: {{ finalHC.valueStock }}, мм<sup>3</sup></p>
        <p>Время рабочего хода: {{ finalHC.workingTime }}, с</p>
        <p>Время холостого хода: {{ finalHC.emptyTime }}, с</p>
        <p>Усилие штока: {{ finalHC.force }}, кг</p>
    </div>
</template>

<script>
export default {
    props: ['finalHC']
}
</script>