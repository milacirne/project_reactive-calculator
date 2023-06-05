<script setup>
    const props = defineProps(['number1', 'number2', 'result']);
</script>

<template>
    <span v-if="props.number1 && props.number2 != ''"><h2>Result: {{ props.result }}</h2></span>
    <span v-else-if="props.number1 || props.number2 === ''"><h2>Enter number 1 and number 2</h2></span>
</template>

<style scoped>
    span h2 {
        padding-bottom: 40px;
    }
</style>