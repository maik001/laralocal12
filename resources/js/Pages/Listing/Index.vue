<template>
  <div class="grid grid-cols-1 md:grid-cols-4 gap-4">
    <Index v-for="listing in listings" :key="listing.id" :listing="listing" />
  </div>
</template>

<script setup>
import Index from "@/Components/Listing/Index.vue";
defineProps({
  listings: Array,
});
</script>