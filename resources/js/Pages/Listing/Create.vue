<template>
  <form @submit.prevent="create">
    <div>
      <label for="beds">Beds</label>
      <!-- .number grants number type hinting --> 
      <input type="number" v-model.number="form.beds" />
    </div>

    <div>
      <label for="baths">Baths</label>
      <input type="number" v-model.number="form.baths" />
    </div>

    <div>
      <label for="area">Area</label>
      <input type="number" v-model.number="form.area"/>
    </div>

    <div>
      <label for="city">City</label>
      <input type="text" v-model="form.city" />
    </div>

    <div>
      <label for="code">Code</label>
      <input type="text" v-model="form.code" />
    </div>

    <div>
      <label for="street">Street</label>
      <input type="text" v-model="form.street"/>
    </div>

    <div>
      <label for="street_br">Street number</label>
      <input type="text" v-model.number="form.street_nr" />
    </div>

    <div>
      <label for="price">Price</label>
      <input type="text" v-model.number="form.price"/>
    </div>

    <div>
      <button type="submit">Create</button>
    </div>
  </form>
</template>

<script setup>
import { useForm } from '@inertiajs/vue3';

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

const create = () => form.post('/listing');
</script>

<style scoped>
label {
  margin-right: 2em;
}

div {
  padding: 2px;
}
</style>
