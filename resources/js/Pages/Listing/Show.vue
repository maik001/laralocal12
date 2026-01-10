<template>
  	<ListingComponent :listing="listing"></ListingComponent>
</template>

<script setup>
import ListingComponent from '@/Components/Listing.vue';
defineProps({
  listing: Object,
});
</script>

<style>
</style>