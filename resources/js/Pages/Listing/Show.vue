<template>
	<div class="flex flex-col-reverse md:grid md:grid-cols-12 gap-1">
		<Box class="md:col-span-7 flex items-center w-full">
			<div class="w-full text-center font-medium text-grey-500">NO IMAGE</div>
		</Box>
		<div class="md:col-span-5 flex flex-col gap-1">
			<Box>
				<template #header>
					Basic Info
				</template>
				<Listing :listing="listing" class="text-lg" />
				<ListingItems :listing="listing" class="text-gray-5" />
				<Price :price="listing.price" class="text-lg font-bold" />
			</Box>
			<Box>
				<template #header>
					Offer
				</template>
				Make an Offer
			</Box>
		</div>
	</div>
</template>

<script setup>
import Listing from '@/Components/Listing.vue';
import ListingComponent from '@/Components/Listing.vue';
import ListingItems from '@/Components/ListingItems.vue';
import Price from '@/Components/Price.vue';
import Box from '@/Components/UI/Box.vue';
defineProps({
  listing: Object,
});
</script>

<style>
</style>