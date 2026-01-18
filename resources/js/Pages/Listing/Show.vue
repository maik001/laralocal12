<template>
  <div class="flex flex-col-reverse md:grid md:grid-cols-12 gap-1">
    <Box class="md:col-span-7 flex items-center w-full">
      <div class="w-full text-center font-medium text-grey-500">NO IMAGE</div>
    </Box>
    <div class="md:col-span-5 flex flex-col gap-1">
      <Box>
        <template #header> Basic Info </template>
        <Listing :listing="listing" class="text-lg" />
        <ListingItems :listing="listing" class="text-gray-5" />
        <Price :price="listing.price" class="text-lg font-bold" />
      </Box>
      <Box>
        <template #header> Monthly Payment </template>
        <div>
          <label for="rate">Interest Rate ({{ interestRate }} %)</label>
          <input
            type="range"
            min="0.1"
            max="30"
            step="0.1"
            v-model.number="interestRate"
            class="w-full h-4 bg-gray-200 rounded-lg appearance-none cursor-pointer dark:bg-gray-700 mb-4"
          />

          <label for="rate">Duration ({{ duration }} years)</label>
          <input
            type="range"
            min="3"
            max="35"
            step="1"
            v-model.number="duration"
            class="w-full h-4 bg-gray-200 rounded-lg appearance-none cursor-pointer dark:bg-gray-700"
          />

          <div class="text-gray-600 dark:text-gray-300 mt-2">
            <div class="text-gray-400">Your monthly Payment</div>
            <Price :price="monthlyPayment" class="text-2xl font-bold"></Price>
          </div>
        </div>
      </Box>
    </div>
  </div>
</template>

<script setup>
import Listing from "@/Components/Listing/Listing.vue";
import ListingItems from "@/Components/Listing/ListingItems.vue";
import Price from "@/Components/Listing/Price.vue";
import Box from "@/Components/UI/Box.vue";
import { ref } from "vue";
import { useMonthlyPayment } from "@/Composables/useMonthlyPayment";

const interestRate = ref(2.5);
const duration = ref(25);

const props = defineProps({
  listing: Object,
});

const { monthlyPayment } = useMonthlyPayment(
  props.listing.price,
  interestRate,
  duration
);
</script>