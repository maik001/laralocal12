<template>
	<div class="grid grid-cols-1 md:grid-cols-4 gap-4">
		<Box v-for="listing in listings" :key="listing.id">
			<div>
				<Link :href="route('listing.show', [listing.id])">
					<ListingComponent :listing="listing"></ListingComponent>
				</Link>
			</div>
			<div>
				<Link :href="route('listing.edit', [listing.id])">Edit</Link>
			</div>
			<div>
				<Link :href="route('listing.destroy', [listing.id])" method="delete">Delete</Link>
			</div>
		</Box>
	</div>
</template>

<script setup>
import ListingComponent from '@/Components/ListingComponent.vue';
import Box from '@/Components/UI/Box.vue';
import { Link } from '@inertiajs/vue3';
defineProps({
	listings: Array,
});
</script>