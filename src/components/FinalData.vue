<template>
    <div class="data data_final">
        <p>Результат:</p>
        <p>Расчетный расход: {{ finalData.expenditure }}, л/мин</p>
        <p>Крутящий момент: {{ finalData.torque }}, Нм</p>
        <p>Мощность: {{ finalData.power }}, кВт</p>
    </div>
</template>

<script>
export default {
    props: ['finalData']
}
</script>