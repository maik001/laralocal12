<template>
    <header class="border-b border-gray-200 dark:border-gray-700 bg-white dark:bg-gray-900 w-full">
        <div class="container mx-auto">
            <nav class="p-4 flex items-center justify-between">
                <div class="text-lg">
                    <Link :href="route('listing.index')">Listings</Link>&nbsp;
                </div>
                <div class="text-xl text-red-600 text-center font-semibold">
                    <Link :href="route('listing.index')">LaraLocal</Link>&nbsp;
                </div>
                <div class="bg-blue-700 hover:bg-blue-600 font-medium text-white p-2 rounded-md">
                    <Link :href="route('listing.create')">+ Add Listing</Link>&nbsp;
                </div>
            </nav>
        </div>
    </header>
    <main class="container mx-auto p-4">
        <div v-if="flashSuccess" class="mb-4 border rounded-md shadow-sm border-green-400 dark:border-green-700 bg-green-50 dark:bg-green-900 p-2">
        {{ flashSuccess }}
        </div>
        <slot></slot>
    </main>
</template>

<script setup>
import {Link, usePage} from '@inertiajs/vue3';
import { computed } from 'vue';

const page = usePage();
const flashSuccess = computed(
    () => page.props.flash.success,
);
</script>