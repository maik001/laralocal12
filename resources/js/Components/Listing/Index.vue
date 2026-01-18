<template>
  <Box>
    <div>
      <Link :href="route('listing.show', [listing.id])">
        <Listing :listing="listing" class="text-lg" />
        <ListingItems :listing="listing" class="text-gray-5" />
        <div class="flex items-center gap-1">
          <Price :price="listing.price" class="text-lg font-bold" />
          <div class="text-xs text-gray-500">
            <Price :price="monthlyPayment">pm</Price>
          </div>
        </div>
      </Link>
    </div>
    <div>
      <Link :href="route('listing.edit', [listing.id])">Edit</Link>
    </div>
    <div>
      <Link :href="route('listing.destroy', [listing.id])" method="delete"
        >Delete</Link
      >
    </div>
  </Box>
</template>

<script setup>
import Listing from "@/Components/Listing/Listing.vue";
import ListingItems from "@/Components/Listing/ListingItems.vue";
import Price from "@/Components/Listing/Price.vue";
import Box from "@/Components/UI/Box.vue";
import { Link } from "@inertiajs/vue3";
import { useMonthlyPayment } from "@/Composables/useMonthlyPayment";

const props = defineProps({ listing: Object });

// default values
const { monthlyPayment } = useMonthlyPayment(props.listing.price, 2.5, 25);
</script>