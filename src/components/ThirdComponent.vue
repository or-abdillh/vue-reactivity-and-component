<template>
    <button @click="emits('transfer-data', 'hi from third component')">Send data to parent</button>
</template>

<script setup>

// emits
const emits = defineEmits(["transfer-data"])

</script>