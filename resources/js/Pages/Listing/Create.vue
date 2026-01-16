<template>
  <form @submit.prevent="create">
    <div class="grid grid-cols-6 gap-2">
      <div class="col-span-2">
        <label class="block mb-1 text-gray-600 dark:text-gray-300 font-medium" for="beds">Beds</label>
        <input type="number" v-model.number="form.beds" class="block w-full p-2 rounded-md border border-gray-300 dark:border-gray-600 text-gray-500" />
        <div v-if="form.errors.beds">{{ form.errors.beds }}</div>
      </div>

      <div class="col-span-2">
        <label class="block mb-1 text-gray-600 dark:text-gray-300 font-medium" for="baths">Baths</label>
        <input type="number" v-model.number="form.baths" class="block w-full p-2 rounded-md border border-gray-300 dark:border-gray-600 text-gray-500" />
        <div v-if="form.errors.baths">{{ form.errors.baths }}</div>
      </div>

      <div class="col-span-2">
        <label class="block mb-1 text-gray-600 dark:text-gray-300 font-medium" for="area">Area</label>
        <input type="number" v-model.number="form.area" class="block w-full p-2 rounded-md border border-gray-300 dark:border-gray-600 text-gray-500" />
        <div v-if="form.errors.area">{{ form.errors.area }}</div>
      </div>

      <div class="col-span-4">
        <label class="block mb-1 text-gray-600 dark:text-gray-300 font-medium" for="city">City</label>
        <input type="text" v-model="form.city" class="block w-full p-2 rounded-md border border-gray-300 dark:border-gray-600 text-gray-500" />
        <div v-if="form.errors.city">{{ form.errors.city }}</div>
      </div>

      <div class="col-span-2">
        <label class="block mb-1 text-gray-600 dark:text-gray-300 font-medium" for="code">Post Code</label>
        <input type="text" v-model="form.code" class="block w-full p-2 rounded-md border border-gray-300 dark:border-gray-600 text-gray-500" />
        <div v-if="form.errors.code">{{ form.errors.code }}</div>
      </div>

      <div class="col-span-4">
        <label class="block mb-1 text-gray-600 dark:text-gray-300 font-medium" for="street">Street</label>
        <input type="text" v-model="form.street" class="block w-full p-2 rounded-md border border-gray-300 dark:border-gray-600 text-gray-500" />
        <div v-if="form.errors.street">{{ form.errors.street }}</div>
      </div>

      <div class="col-span-2">
        <label class="block mb-1 text-gray-600 dark:text-gray-300 font-medium" for="street_nr">Street number</label>
        <input type="text" v-model.number="form.street_nr" class="block w-full p-2 rounded-md border border-gray-300 dark:border-gray-600 text-gray-500" />
        <div v-if="form.errors.street_nr">{{ form.errors.street_nr }}</div>
      </div>

      <div class="col-span-6">
        <label class="block mb-1 text-gray-600 dark:text-gray-300 font-medium" for="price">Price</label>
        <input type="text" v-model.number="form.price" class="block w-full p-2 rounded-md border border-gray-300 dark:border-gray-600 text-gray-500" />
        <div v-if="form.errors.price">{{ form.errors.price }}</div>
      </div>

      <div class="col-span-6">
        <button type="submit" class="bg-blue-700 hover:bg-blue-600 font-medium text-white p-2 rounded-md">Create</button>
      </div>
    </div>
  </form>
</template>

<script setup>
import { useForm } from "@inertiajs/vue3";

const form = useForm({
  beds: 0,
  baths: 0,
  area: 0,
  city: null,
  code: null,
  street: null,
  street_nr: null,
  price: 0,
});

const create = () => form.post(route("listing.store"));
</script>

<style scoped>
label {
  margin-right: 2em;
}

div {
  padding: 2px;
}
</style>
