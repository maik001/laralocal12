<template>
	<div class="grid grid-cols-1 md:grid-cols-4 gap-4">
		<Box v-for="listing in listings" :key="listing.id">
			<div>
				<Link :href="route('listing.show', [listing.id])">
					<Listing :listing="listing" class="text-lg" />
					<ListingItems :listing="listing" class="text-gray-5" />
					<Price :price="listing.price" class="text-lg font-bold" />
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
import Listing from '@/Components/Listing.vue';
import ListingItems from '@/Components/ListingItems.vue';
import Price from '@/Components/Price.vue';
import Box from '@/Components/UI/Box.vue';
import { Link } from '@inertiajs/vue3';
defineProps({
	listings: Array,
});
</script>