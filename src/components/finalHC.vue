<template>
    <div class="data data_final">
        <p>Результат:</p>
        <p>Объём поршневой части: {{ finalHC.valuePlunger }}</p>
        <p>Объём штоковой части: {{ finalHC.valueStock }}</p>
        <p>Время рабочего хода: {{ finalHC.workingTime }}</p>
        <p>Время холостого хода: {{ finalHC.emptyTime }}</p>
        <p>Усилие штока: {{ finalHC.force }}</p>
    </div>
</template>

<script>
export default {
    props: ['finalHC']
}
</script>