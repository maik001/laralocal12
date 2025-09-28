<template>
        <div>Index</div>
        <div> The Message is {{ message }}</div>
</template>

<script setup>
    defineProps({
        message: String
    });
</script>
