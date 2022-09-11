<template>
    <div class="data data_final">
        <p>Результат:</p>
        <p>Расчетный расход: {{ finalData.expenditure }}</p>
        <p>Крутящий мемент: {{ finalData.torque }}</p>
        <p>Мощность: {{ finalData.power }}</p>
    </div>
</template>

<script>
export default {
    props: ['finalData']
}
</script>