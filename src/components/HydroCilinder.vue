<template>
    <div class="data data_final">
        <p>Расчетный расход: {{ expenditure }}</p>
    </div>
</template>

<script>
export default {
    data () {
        return {
            expenditure: 0
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