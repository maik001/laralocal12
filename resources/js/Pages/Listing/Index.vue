<template>
	<div v-for="listing in listings" :key="listing.id">
		<div>
			<Link :href="`/listing/${listing.id}`">
				<ListingComponent :listing="listing"></ListingComponent>
			</Link>
		</div>
		<div>
			<Link :href="`listing/${listing.id}/edit`">Edit</Link>
		</div>
	</div>
</template>

<script setup>
import ListingComponent from '@/Components/ListingComponent.vue';
import { Link } from '@inertiajs/vue3';
defineProps({
	listings: Array,
})
</script>