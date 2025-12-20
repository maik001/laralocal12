<template>
	<div v-for="listing in listings" :key="listing.id">
		<Link :href="`/listing/${listing.id}`">
			<ListingComponent :listing="listing"></ListingComponent>
		</Link>
	</div>
</template>

<script setup>
import ListingComponent from '@/Components/ListingComponent.vue';
import { Link } from '@inertiajs/vue3';
defineProps({
	listings: Array,
})
</script>