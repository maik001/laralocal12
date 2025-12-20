<template>
  	<ListingComponent :listing="listing"></ListingComponent>
</template>

<script setup>
import ListingComponent from '@/Components/ListingComponent.vue';
defineProps({
  listing: Object,
});
</script>

<style>
</style>