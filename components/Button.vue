<template>
    <button class="text-white duration-200 bg-gradient-to-r from-orange-500 via-orange-600 to-orange-700 hover:bg-gradient-to-br focus:ring-4 focus:outline-none focus:ring-orange-300 dark:focus:ring-orange-800 font-medium rounded text-sm px-5 py-2.5 text-center mr-2 mb-2">
        <NuxtLink :class="'text-lg font-medium'" :to="props.url">{{props.title}}</NuxtLink>
    </button>
</template>

<script setup>
const props = defineProps({
    title:  String,
    url:  String,
})

</script>