<script setup>
    const props = defineProps(['operation', 'number1', 'number2']);
</script>

<template>
    <div class="operation">
        <h2>Select the operation to get the result</h2>
    </div>
    <div>
        <input @keyup="props.number1" required type="text" placeholder="Enter number 1">
        <select @change="props.operation">
            <option value="+">+</option>
            <option value="-">-</option>
            <option value="*">x</option>
            <option value="/">÷</option>
        </select>
        <input @keyup="props.number2" required type="text" placeholder="Enter number 2">
    </div>
</template>

<style scoped>
    input, 
    select {
        margin: 24px;
        padding: 8px;
        border-radius: 8px;
        border: none;
    }

    h2 {
        font-style: italic;
    }
</style>